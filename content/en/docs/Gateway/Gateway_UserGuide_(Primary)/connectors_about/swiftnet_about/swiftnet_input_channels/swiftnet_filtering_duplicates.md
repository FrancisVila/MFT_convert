{
    "title": "SWIFTNet filtering duplicates for queues and output channels",
    "linkTitle": "SWIFTNet filtering duplicates for queues and output channels",
    "weight": "300"
}{{< Gateway/componentlongname  >}}: Connectors

The following sections describe SWIFTNet filtering duplicates for queues and output channels.

<span id="Dynamica"></span>

## Dynamically filtering duplicates for queues and output channels

Pay attention when creating, updating or importing Remote Sites with queues or output channels. Doing so avoids possible inconsistencies when there are duplicate queues and output channel definitions in several Remote Sites.

{{< Gateway/componentshortname  >}} verifies all sites at startup and takes action when it encounters duplicate definitions of queues or output channels.

**Note:** Output sessions are the dynamic representation of queues and output channels from acquiring queues or opening output channels.

Filtering is dynamic. A global list of output sessions is created at {{< Gateway/componentshortname  >}} startup and updated as sites are started or stopped. {{< Gateway/componentshortname  >}} checks each new potential session for conflicts with existing sessions:

-   At startup {{< Gateway/componentshortname >}} checks all active SWIFTNet Remote Sites in the order from the database. If a site has a queue or output channel that conflicts with the global list, the site is disabled.
-   At manual start of a Remote Site, if a conflict with the global list is detected for a Remote Site queue or output channel, the site is disabled.

Because the disabled state is an internal state, a user can know a site became unusable only from logs.

Every 30 seconds a check is made of disabled sites to determine whether conflicts persist with the global list. If no conflicts are identified, the site is restarted.

A user cannot use a disabled site until the conflict is resolved.

## Static configuration behaviors

The following are details of the conflicting situations described in the preceding section.

About the notations in the following examples:

-   For example, Q1, Q2 for legacy queues (SWIFT 6 version) definitions
-   For example, Q1:C1, Q2:C2 for output channels definitions (channel-queue pairs)

### 1. Same queue present in different or same sites

#### Example 1

Site1: Q1, Q1, Q2

**Action**: (Site1 stopped) {{< Gateway/componentshortname  >}} start or manual start of Site1.

**Result**: Site1 is not allowed to start and is disabled.

#### Example 2

Site1 (first in database): Q1, Q2

Site2: Q2, Q3

**Action**: (both sites stopped) {{< Gateway/componentshortname  >}} start or manual start of Site1 followed immediately by a manual start of Site2.

**Result**: Site2 is not allowed to start and is disabled.

#### Example 3

Site1 (first in database): Q1, Q2

Site2: Q2, Q3

**Action**: (both sites stopped) Manual start of Site2 followed by manual start of Site1 after the log message:

Site2 site has been started

**Result**: Site1 is not allowed to start and is disabled.

### 2. Same output channel present in different or same sites

#### Example 1

Site1: Q1:C1, Q1:C1

**Action**: (Site1 stopped) {{< Gateway/componentshortname  >}} start or manual start of Site1.

**Result**: Site1 is not allowed to start and is disabled.

#### Example 2

Site1 (first in database): C1:Q1, C2:Q2

Site2: C2:Q2, C3: Q3

**Action**: (both sites stopped) {{< Gateway/componentshortname  >}} start or manual start of Site1 followed immediately by a manual start of Site2.

**Result**: Site2 is not allowed to start and is disabled.

#### Example 3

Site1 (first in database): C1:Q1, C2:Q2

Site2: C2:Q2, C3: Q3

**Action**: (both sites stopped) Manual start of Site2 followed by manual start of Site1 after the log message:

Site2 site has been started

**Result**: Site1 is not allowed to start and becomes disabled.

<span id="Mixed_queue_or_output_channel_present_in_different_or_same_sites"></span>

### 3. Mixed queue or output channel present in different or same sites

#### Example 1

Site1: Q1, Q2, C3:Q1

**Action**: (Site1 stopped) {{< Gateway/componentshortname  >}} start or manual start of Site1.

**Result**: Site1 is not allowed to start and is disabled.

#### Example 2

Site1: C1:Q1, C1:Q2

**Action**: (Site1 stopped) {{< Gateway/componentshortname  >}} start or manual start of Site1.

**Result**: Site1 is not allowed to start and is disabled.

#### Example 3

Site1: C1:Q1 (first in database)

Site2: C1:Q2

**Action**: (both sites stopped) {{< Gateway/componentshortname  >}} start or manual start of Site1 followed immediately by a manual start of Site2.

**Result**: Site1 is not allowed to start and is disabled.

#### Example 4

Site1 (first in database): C1:Q1, C2:Q2

Site2: C2:Q2, C3: Q3

**Action**: (both sites stopped) Manual start of Site2 followed by manual start of Site1 after the log message:

Site2 site has been started

**Result**: Site1 is not allowed to start and is disabled.

#### Example 5

Site1 (first in database): Q1, Q2

Site2: C2:Q2, C3: Q3

**Action**: (both sites stopped) {{< Gateway/componentshortname  >}} start or manual start of Site1 followed immediately by a manual start of Site2.

**Result**: Site1 is not allowed to start and is disabled.

#### Example 6

Site1 (first in database): Q1, Q2

Site2: C2:Q2, C3: Q3

**Action**: (both sites stopped) Manually start Site2 and manually start Site1 after the log message:

Site2 site has been started

**Result**: Site1 is not allowed to start and is disabled.

### Observation

Next site configuration (Site1: C1:Q1, C2:Q1) is permitted, but the success of opening the output channels depends on the queue-sharing mode. A shared queue can only be opened with one or more distinct output channels, but cannot be acquired in legacy mode. An exclusive queue can be acquired in legacy mode or opened with one output channel.

## Using duplicate queues and output channels with backup sites

If a nominal site contains definitions of queues or output channels, define the same queues or channels in the backup site. Normally, duplicate definitions of queues or output channels between standard sites should not exist. {{< Gateway/componentshortname  >}} treats such definitions specially (see <a href="#Dynamica" class="MCXref xref">Dynamically filtering duplicates for queues and output channels</a>). Backup sites, however, should define the same queues and output channels as their nominal site.

### Queues

Queue definitions are shared between the nominal and backup site. This means all queues are acquired through the nominal site and, only when the nominal site is stopped, the same queues are acquired through the backup site.

### Output channels

Output channels (channel-queue pairs) are shared between nominal and backup sites. This means all output channels are opened through the nominal site and, only when the nominal site is stopped, the same output channels are opened through the backup site.

Only common declarations between nominal and backup sites are allowed. Mixed queues with output channel definitions are forbidden.

### Queues tables

About the notations in the tables:

-   For example, Q1, Q2 for legacy queues (SWIFT 6 version) definitions
-   For example, Q1:C1, Q2:C2 for output channels definitions (channel-queue pairs)
-   For example, S(Q1), S(Q1:C1) for output sessions (dynamic representation of queues and output channels resulting from acquiring queues or opening output channels)

#### Table 1

In the following table are examples of common definitions of queues and output channels for a nominal and backup site. The {{< Gateway/componentshortname  >}} actions and results are included.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">No.         </th>
<th class="HeadE-Column1-Header1">Static configuration example         </th>
<th class="HeadE-Column1-Header1">Site status         </th>
<th class="HeadD-Column1-Header1">Action and result         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>1         </td>
         <td><p>Nominal1 – Q1, Q2, C3:Q3, C4:Q4</p>
<p>Backup1 – Q1, Q5, C4:Q4, C6:Q6</p>         </td>
         <td>Both sites stopped         </td>
         <td><p><strong>Action</strong>: {{< Gateway/componentshortname  >}} start
or manual start of Nominal1, followed immediately by a manual start of Backup1.</p>
<p><strong>Result</strong>: Nominal site has all its sessions active.</p>
<p>Nominal1 – S(Q1), S(Q2), S(C3:Q3), S(C4:Q4)</p>
<p>Backup1 – S(Q5), S(C6:Q6)</p>         </td>
      </tr>
      <tr>
         <td>2         </td>
         <td><p>Nominal1 – Q1, Q2, C3:Q3, C4:Q4</p>
<p>Backup1 – Q1, Q5, C4:Q4, C6:Q6</p>         </td>
         <td>Both sites stopped         </td>
         <td><p><strong>Action</strong>: Manual start of Backup1 followed by a manual start of Nominal1
after
the log message:</p>
<p><code>Backup1 site has been started</code></p>
<p><strong>Result</strong>: Initially, Backup1 opens all its sessions, but Nominal1 takes back and owns the duplicates.</p>
<p>Nominal1 – S(Q1), S(Q2), S(C3:Q3), S(C4:Q4)</p>
<p>Backup1 – S(Q5), S(C6:Q6)</p>         </td>
      </tr>
      <tr>
         <td>3         </td>
         <td><p>Nominal1 – Q1, Q2, C3:Q3, C4:Q4</p>
<p>Backup1 – Q1, Q5, C4:Q4, C6:Q6</p>         </td>
         <td><p>Both sites started</p>
<p>Nominal1 – S(Q1), S(Q2), S(C3:Q3), S(C4:Q4)</p>
<p>Backup1 – S(Q5), S(C6:Q6)</p>         </td>
         <td><p><strong>Action</strong>: Stop Nominal1.</p>
<p><strong>Result</strong>: Common active sessions pass to Backup1.</p>
<p>Nominal1 --</p>
<p>Backup1 – S(Q1), S(C4:Q4) S(Q5), S(C6:Q6)</p>         </td>
      </tr>
      <tr>
         <td>4         </td>
         <td><p>Nominal1 – Q1, Q2, C3:Q3, C4:Q4</p>
<p>Backup1 – Q1, Q5, C4:Q4, C6:Q3</p>
<p>Q3 should be shared to have two channels opened with success for the same queue.</p>         </td>
         <td>Both sites stopped         </td>
         <td><p><strong>Action</strong>: {{< Gateway/componentshortname  >}} start or
manual start of Nominal1 followed immediately by a manual start of Backup1.</p>
<p><strong>Result</strong>: Nominal site has all its active sessions.</p>
<p>Nominal1 – S(Q1), S(Q2), S(C3:Q3), S(C4:Q4)</p>
<p>Backup1 – S(Q5), S(C6:Q3)</p>         </td>
      </tr>
   </tbody>
</table>

#### Table 2

In the following table are examples of duplicated definitions of queues and output channels, generating conflicts between nominal and backup sites. The {{< Gateway/componentshortname  >}} actions and results are included.

Resolve the conflicts in the logs to enable a site to start and become operational.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">No.         </th>
<th class="HeadE-Column1-Header1">Static configuration example         </th>
<th class="HeadE-Column1-Header1">Site status         </th>
<th class="HeadD-Column1-Header1">Action and result         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>1         </td>
         <td><p>Nominal1 – Q1, <strong>Q2</strong>, C3:Q3, C4:Q4
(first in database)</p>
<p>Backup1 – Q1, Q5, C4:Q4, <strong>C2:Q2</strong></p>         </td>
         <td>Both sites stopped         </td>
         <td><p><strong>Action</strong>: {{< Gateway/componentshortname  >}} start or
manual start of Nominal1 followed immediately by a manual start of Backup1.</p>
<p><strong>Result</strong>: Backup1 is not allowed to start. It becomes disabled because a conflict was identified (bold items).</p>         </td>
      </tr>
      <tr>
         <td>2         </td>
         <td><p>Nominal1 – Q1, <strong>Q2</strong>, C3:Q3, C4:Q4</p>
<p>Backup1 – Q1, Q5, C4:Q4, <strong>C2:Q2</strong></p>         </td>
         <td>Both sites stopped         </td>
         <td><p><strong>Action</strong>: Manual start of Backup1 followed by a manual start of Nominal1 after the log message:</p>
<p><code>Backup1 site has been started</code></p>
<p><strong>Result</strong>: Nominal1 is not allowed to start. It becomes disabled because a conflict was identified (bold items).</p>         </td>
      </tr>
      <tr>
         <td>3         </td>
         <td><p>Site1 – <strong>Q1</strong>, <strong>Q3</strong>, C5:Q4 (first in database)</p>
<p>Nominal1 – Q1, Q2, <strong>C3:Q3</strong>, C4:Q4 (second in database)</p>
<p>Backup1 – <strong>Q1</strong>, Q5, C4:Q4, C6:Q6</p>
<p>Q3 should be shared to have two channels opened with success for the same queue</p>         </td>
         <td>All sites stopped         </td>
         <td><p><strong>Action</strong>: {{< Gateway/componentshortname  >}} start or
manual start of Site1, then Nominal1, then Backup1 (starting order is database order)
.</p>
<p><strong>Result</strong>: Nominal1 and Backup1 are not allowed to start. They are disabled because a conflict was identified (bold items).</p>         </td>
      </tr>
      <tr>
         <td>4         </td>
         <td><p>Site1 – <strong>Q1</strong>, Q3, C5:Q4 (first in database)</p>
<p>Nominal1 – Q1, Q2, C3:Q3, C4:Q4</p>
<p>Backup1 – <strong>Q1</strong>, Q5, C4:Q4, C6:Q6</p>
<p>Q3 should be shared to have two channels opened with success for the same queue</p>         </td>
         <td>All sites stopped         </td>
         <td><p><strong>Action</strong>: Manual start of Site1, followed by a manual start of Backup1 after the
log message:</p>
<p><code>Site1 site has been started</code></p>
<p><strong>Result</strong>: Backup1 is not allowed to start and is disabled because a conflict was identified (bold items).</p>         </td>
      </tr>
   </tbody>
</table>

Do not allow nominal and backup sites to have the same message partner, SNL and event endpoint on same SAG. When receiving multiple SnF transfers on a common queue or output channel, Swift balances the transfers among all server processes (nominal and backup). This creates inconsistencies for duplicates and routing.

Links to documentation set for Axway Gateway {{< Gateway/releasenumber  >}}:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
