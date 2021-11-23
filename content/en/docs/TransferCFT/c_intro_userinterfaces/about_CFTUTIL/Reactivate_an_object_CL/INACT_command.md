{
    "title": "           INACT  - Deactivate an object",
    "linkTitle": "INACT - Deactivating objects",
    "weight": "270"
}<span id="kanchor63"></span>

This page describes the INACT command and its parameters. You can use the INACT command to deactivate:

-   One or more partners (CFTPART)
-   Sentinel notifications
-   CRON object (CFTCRON)
-   Folder object (CFTFOLDER)

> **Note:**
>
> This command cannot be applied to partners whose definition was provided
> or modified by a directory EXIT.

Command guide: [INACT](../../../command_summary#INACT)

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Parameter         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/id">ID</a> </p>         </td>
         <td><p>Identifier for the object to be deactivated. To deactivate several objects with a single command,
use wildcard
characters or meta characters.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/type">TYPE</a> </p>         </td>
         <td><p>Object to be deactivated:</p>
<ul>
<li>PART</li>
<li>TRK</li>
<li>CRON</li>
<li>FOLDER</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/mode">MODE</a> </p>         </td>
         <td><p>Mode to be deactivated on partners (only when TYPE=PART object):</p>
<ul>
<li>BOTH (default)</li>
<li>REQUESTER</li>
<li>SERVER</li>
</ul>
<p>You can use the shortcuts B, R and S in place of the keywords.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/force">FORCE</a></p>         </td>
         <td><ul>
<li>YES: Stops any transfers in progress involving the deactivated
partners.</li>
<li>NO: Default value, transfers progress normally.</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

## Using the INACT command

Using CFTUTIL you can perform the following commands.

### Deactivate a partner

Syntax



    INACT TYPE=PART,ID=<CFTPART_ID>,MODE=<mode>,FORCE=<NO | YES>

Where:

-   `CFTPART_ID` is the identifier of the partner to deactivate. To deactivate several partners with a single command, use wildcard characters or meta characters.
-   is the mode to be deactivated, with values: "BOTH" , "B", "REQUESTER", "R" , "SERVER", "S"
-   When `FORCE `is set to `YES`, stops any transfers in progress involving the deactivated partners.

Example

to deactivate the partner called PARIS in requester mode, enter:



    INACT TYPE=PART, ID=PARIS, MODE=REQUESTER

Returning the following output:



    CFTU20I Part=PARIS : ACTIVEBOTH -> ACTIVESERV
    CFTU00I INACT _ Correct (TYPE=PART,ID=PARIS,MODE=REQUESTER)

When a partner is deactivated, transfers awaiting processing are:

-   Suspended in requester mode
-   Refused in server mode

The state of a transfer request awaiting execution in requester mode
for a deactivated partner remains **D**,
with a diagnostic code 430 and a protocol diagnostic INACT.

The state of a transfer request awaiting execution in server mode for
a deactivated partner remains <span style="font-weight: bold;">D</span>,
with a diagnostic code 930 and a protocol diagnostic RCO 312, or ABO 312
if the session is already open.

The state of transfers that are interrupted by an INACT command when
FORCE=YES is <span style="font-weight: bold;">H</span>, with a diagnostic
code 121 and a protocol diagnostic OPER.

### Deactivate Sentinel notifications

Syntax



    INACT TYPE=TRK

All notifications to Sentinel are suspended.

### Deactivate cron object

Syntax



    INACT TYPE=CRON,ID=<CFTCRON_ID>

Where `CFTCRON_ID` is the identifier of the CRON object to deactivate. To deactivate several CRON objects with a single command, use wildcard characters or meta characters.

Example

To deactivate the CRON referenced by CRON1, enter:



    INACT TYPE=CRON,ID=CRON1

Returning the following output:



    CFTU20I Cronjob=CRON1 : ACTIVE -> NOACTIVE
    CFTU00I INACT _ Correct (id=cron1,type=cron)

### Deactivate folder object

Syntax



    INACT TYPE=FOLDER,ID=<CFTFOLDER_ID>

Where `CFTFOLDER_ID` is the identifier of the folder object to deactivate. To deactivate several folder objects with a single command, use wildcard characters or meta characters.

Example

To deactivate the folder referenced by USER1, enter:



    INACT TYPE=FOLDER,ID=USER1

Returning the following output:



    CFTU20I Folder=USER1 : ACTIVE -> NOACTIVE
    CFTU00I INACT _ Correct (TYPE=FOLDER,ID=USER1)
