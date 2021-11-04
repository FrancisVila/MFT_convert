{
    "title": "SWIFTNet queues and output channels",
    "linkTitle": "SWIFTNet queues and output channels",
    "weight": "280"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Connectors

[About SWIFTNet output channels](#about)

[Configuring SWIFTNet output channels](#config)

[Modifying SWIFTNet output channels configured in Gateway](#modify)

[Exporting and importing Site data](#export)

[Controlling output channels](#control_op)

[Displaying information about output channels](#display_op)

[Monitoring output sessions](#monitoring)

[Controlling SnF session behavior](#control_snf)

[Displaying information about queues](#display_queue)

<span id="about"></span>

## About SWIFTNet output channels

SWIFT release 7.0 introduces the concept of *output channels.*

Output channels are an extension of the previously-implemented Store-and-Forward (SnF) queue mechanism which allows the opening of multiple sessions for the same queue (queue sharing). The output channel is used when the SWIFT network pushes transfers to the messaging interface (Gateway). Output channels apply to both InterAct & FileAct. For more details about output channels, output sessions, queues and queue sharing, refer to the official SWIFT documentation.

<span id="Output"></span>

### Output channels, queues and output sessions

*Output sessions* existed already before the concept of output channels was introduced. Output sessions were in fact *queue sessions*. At a given time only one session existed for a given queue.

Starting an output session was equivalent to acquiring the queue. Stopping an output session was equivalent to releasing the queue.

The concept of *output channel* allows multiple output sessions on a queue in such a way that these output sessions are easily identified and managed. Indeed, without output channels, there is only one output session possible at a given time for a queue.

### The need for output channels

The reason for using output channels is to be able to have multiple sessions on a queue.

Multiple sessions are required to be able to deliver messages from the same queue in parallel to several endpoints to achieve:

-   High availability of output from a queue, where messages can still be delivered even when one of the sessions fails for whatever reason (typically connectivity problems or a problem at the receiving system)
-   Higher performance, where in order to spread the traffic load messages from a queue can be handled by several messaging interfaces or by several SWIFTNet Link

When SWIFT provisions a queue, SWIFT automatically creates a corresponding output channel with the same name. Therefore, the creation of additional output channels is only required when queue sharing is used.

### Naming output channels

For each queue, a default output channel with the same name is created by SWIFT.

The default output channel can be used in the case of an exclusive queue for example. When using a shared queue, several output channels can be used to start a session on the same queue. The output channels used for queue sharing should be named according to SWIFT rules (for example, when using alphabetic characters, only use lower case).

Here are some examples of how you could name output channels:

-   bic8\_oc1, bic8\_oc2, ... for live output channels
-   bic8\_oc1!p, bic8\_oc2!p, ... for pilot output channels

<span id="config"></span>

## Configuring SWIFTNet output channels

In Gateway, you configure SWIFTNet output channels in the Remote Site.

### Creating a Remote Site using the Gateway GUI

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:  
    Partner Management > Sites
2.  Right-click the <span style="font-weight: bold;">Remote Site</span> sub-node, then select <span style="font-weight: bold;">New</span> to display the <span style="font-style: italic;">New Remote Site</span> window.
3.  Complete the fields on the <span style="font-weight: bold;">[General](../../../../managing_partners_start_here/sites_start_here/managing_remote_sites/remote_site_general_tab)</span> tab. In the <span style="font-weight: bold;">Protocol</span> field, make sure you select <span style="font-weight: bold;">SWIFTNet</span>.
4.  Complete the fields on the <span style="font-weight: bold;">[Options](../../../../managing_partners_start_here/sites_start_here/managing_remote_sites/remote_site_options_tab)</span> tab.
5.  Complete the fields on the <span style="font-weight: bold;">[SWIFTNet](../../../../managing_partners_start_here/sites_start_here/managing_remote_sites/remote_site_swiftnet_tab)</span> tab, including any required fields on the **General** sub-tab.
6.  Select the **SnF** sub-tab.
7.  Click **New**.
8.  Complete the *Output Channel Parameters* window.
9.  *Optional* Click **Select subset** and select and re-order the information in the *Output Channel Subset* window.
10. Click <span style="font-weight: bold;">OK</span> to close each window.  
    Gateway creates a new Remote Site with the specified characteristics.

### Creating a Remote Site using command line

Create a Remote Site using the <span class="code" style="font-weight: bold;">[peladm create\_site](../../../../managing_partners_start_here/sites_start_here/managing_local_sites_cli/managing_remote_sites_cli#peladm_create_site)</span> online command.


    peladm create_site
       -add_channel
       -queue_name QUEUENAME
       -channel_name CHANNELNAME
       -window_size WINDOWSIZE
       -channel_subset SUBSETS

For details of parameters, refer to the table at the end of this section.

When creating a Site, only one output channel can be specified. Afterwards you can add additional output channels using the <span class="codeBold_in_para">peladm update\_site -add\_channel</span> command.

**Note:** Even though <span class="codeBold_in_para">delete\_queue</span> and <span class="codeBold_in_para">delete\_channel</span> are shown as subcommands of <span class="codeBold_in_para">peladm create\_site</span> (when you enter <span class="codeBold_in_para">peladm create\_site</span>), they are available only for <span class="codeBold_in_para">peladm update\_site</span>.

### Example


    peladm create_site
       –alias SWIFT_REMOTE_SITE  –protocol SWIFTNET
       -login_ident swift_user_name  -login_password swift_user_password
       -add_channel  -queue_name bic8_q1  -channel_name bic8_oc1
       -window_size 10  -channel_subset "InterAct_Urgent FileAct_Urgent"

<span id="swift_op_ch_paras"></span>

### Remote Site parameters specific to SWIFTNet output channels

In this table, the corresponding field name in the Gateway UI is shown in <span style="font-weight: bold;font-style: italic;">italics</span>.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Parameter         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>-add_channel</p>
<p><strong>New</strong> button on <strong>SnF</strong> sub-tab</p>         </td>
         <td><p>Indicates that you are adding a channel.</p>         </td>
      </tr>
      <tr>
         <td><p>-channel_name (-chnname)</p>
<p>Channel name</p>         </td>
         <td><p>The name of the output channel.</p>         </td>
      </tr>
      <tr>
         <td><p>-new_channel_name (-newcn)</p>         </td>
         <td><p>The new name for the output channel (when renaming the output channel).</p>         </td>
      </tr>
      <tr>
         <td><p>-new_queue_name (-newqn)</p>         </td>
         <td><p>The new output channel's queue name (when renaming the queue).</p>         </td>
      </tr>
      <tr>
         <td><p>-queue_name (-qname)</p>
<p>Queue name</p>         </td>
         <td><p>The output channel's queue name.</p>         </td>
      </tr>
      <tr>
         <td><p>-window_size (-wndsz)</p>
<p>Window size</p>         </td>
         <td><p><em>Optional</em></p>
<p>The output channel window size.</p>
<p>In SWIFT, the window size is an optional element that is used to limit the number of concurrent messages or files sent by SWIFT on a push session. If the element is not present, then a default value is used for the window size (specified in SWIFT documentation). SWIFT adjusts the window size to the maximum value in case the application requests a higher value than the maximum allowed value.</p>
<p>Normally you do not need to change the default value. Only specify the window size if you want to restrict the value.</p>         </td>
      </tr>
      <tr>
         <td><p>-channel_subset (-chnsbs)</p>
<p>Select subset...</p>         </td>
         <td><p><em>Optional</em></p>
<p>A string describing the output channel subset elements. This string can contain <em>up to six</em> subset elements.</p>
<p>Enclose the string between quotes and use a space to separate elements.</p>
<p><strong>Example:</strong></p>
<p>-channel_subset "InterAct_Urgent FileAct_Urgent"</p>
<p>Possible values:</p>
<ul>
<li>InterAct</li>
<li>FileAct</li>
<li>System</li>
<li>Urgent</li>
<li>Normal</li>
<li>InterAct_Urgent</li>
<li>InterAct_Normal</li>
<li>FileAct_Urgent</li>
<li>FileAct_Normal</li>
<li>System_Urgent</li>
<li>System_Normal</li>
</ul>
<p><strong>Notes:</strong></p>
<p>These values are case sensitive.</p>
<p>The order in which the subsets appear is important.</p>
<p>If no subset is shown, the output channel will receive all types of message of all priorities, in a first in, first out order.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-receive_retrieved_messages
(-rcvretrmsg)</span></p>
<p>Receive retrieved messages</p>         </td>
         <td><p>Optional</p>
<p>Enable the attribute in order to receive retrieved messages.</p>
<p>By setting this parameter, the output channel will be opened having the element “<span class="code">protocolLevel</span>” set to value “<span class="code">2</span>”, as indicated in the SWIFT documentation.
Example:
<span class="code">-receive_retrieved_messages "Y"</span></p>
<p><span class="bold_in_para">Note</span>: To receive retrieved messages, the queue for which the session is started:</p>
<ul>
<li>Must have been defined for service “<span class="code">swift.snf.system (!p, !x)</span>”.</li>
<li>Must have been used on the retrieval request payload.</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

#### Example display (SWIFTNet-related data only)

<span id="modify"></span>

## Modifying SWIFTNet output channels configured in Gateway

**Note:** The following operations only affect the configuration of the output channels in Gateway. This does not automatically modify the output channels or the queues defined on the SWIFT network side!

This section explains how to:

-   Add a channel on a queue
-   Delete a channel
-   Update a channel
-   Rename a queue
-   Delete a queue

### Modifying a Remote Site using the Gateway GUI

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:  
    Partner Management > Sites
2.  Click the <span style="font-weight: bold;">Remote Site</span> sub-node.  
    Gateway displays a list of all Remote Sites in the right pane.
3.  In the right pane, right-click the name of the Remote Site for which you want to modify the output channel. Select <span style="font-weight: bold;">Modify...</span> from the context menu.  
    Gateway displays the <span style="font-style: italic;">Remote Site</span> editing window.
4.  On the <span style="font-weight: bold;">[SWIFTNet](../../../../managing_partners_start_here/sites_start_here/managing_remote_sites/remote_site_swiftnet_tab)</span> tab, select the **SnF** sub-tab.
5.  Select the required output channel and click **Modify**.
6.  Complete the *Output Channel Parameters* window and (if required) the *Output Channel Subset* window.
7.  Click <span style="font-weight: bold;">OK</span> to close each window.

### Modifying a Remote Site using command line

Modify a Remote Site using one of the following [<span class="code" style="font-weight: bold;">peladm update\_site</span>](../../../../managing_partners_start_here/sites_start_here/managing_local_sites_cli/managing_remote_sites_cli#peladm_delete_site) online commands.

For details of parameters, refer to the table [above](#swift_op_ch_paras).

#### Adding a channel


    peladm update_site  -add_channel
       -alias SITE_NAME
       -queue_name QUEUENAME
       -channel_name CHANNELNAME
       -window_size VALUE
       -channel_subset SUBSETS

#### Deleting a channel


    peladm update_site  -delete_channel
       -alias SITE_NAME
       -queue_name QUEUENAME
       -channel_name CHANNELNAME

#### Updating a channel


    peladm update_site  -update channel
       -alias SITE_NAME
       -channel_name CHANNELNAME
       -new_channel_name NEWCHANNELNAME
       -window_size VALUE
       -channel_subset SUBSETS

**Current limitations:**

-   You cannot move a channel from one queue to another queue.
-   You cannot have the same queue name in two different channels.

#### Renaming a queue


    peladm update_site  -rename_queue
       -alias SITE_NAME
       -queue_name QUEUENAME
       -new_queue_name NEWQUEUENAME

**Note:** This affects the configuration of Gateway only (not the configuration on the SWIFT network side).

#### Deleting a queue


    peladm update_site  -delete_queue
       -alias SITE_NAME
       -queue_name QUEUENAME

**Notes:**

When you delete a queue, all the channels associated with that queue will be deleted. This affects the configuration of Gateway only (not the configuration on the SWIFT network side).

<span id="export"></span>

## Exporting and importing Site data

You can use the <span class="codeBold_in_para">pelbase export\_site</span> and <span class="codeBold_in_para">pelbase import</span> commands to export or import SWIFTNet output channel data, in addition to all other Site data.

### pelbase export\_site

Use <span class="codeBold_in_para">[pelbase export\_site](../../../../starting_and_stopping_server/importing_and_exporting_objects#pelbase_export_site)</span> to export Site data, including SWIFTNet output channel information (if defined for the specified Site).

For each output channel, a line is displayed in the following format:

s\_output\_channel\_info = channel\_name queue\_name \[window\_size\] \[subset1...\[subset6\]\] \[receive\_retrieved\_messages\]

For details of parameters, refer to the table [above](#swift_op_ch_paras).

#### Example display (SWIFTNet-related data only)

\[...\]

s\_ra\_instance='Ra3'

s\_message\_partner='rnd1\_mp'

s\_event\_end\_point='rnd1\_eep'

s\_snf\_queues='bic1\_rnd1roqasfiafatf!x bic2\_rnd1roqasfiafatfdn!x'

s\_snl\_end\_point='rnd1\_sep'

s\_ra\_pathname=''

s\_ra\_config\_file=''

s\_sign\_ident\_list=''

s\_decrypt\_ident\_list=''

s\_backup\_site=''

s\_output\_channel\_info='bic3\_oc1!x bic4\_rnd1roqasfiafatf!x 10 InterAct FileAct\_Urgent N'

### pelbase import

Use <span class="codeBold_in_para">[pelbase import](../../../../starting_and_stopping_server/importing_and_exporting_objects#pelbase_import)</span> to import Site data, including SWIFTNet output channel information, from an importable object file

The format in which the output channel information must appear in the import file is:

channel\_name  queue\_name  \[window\_size\]  \[subset1...\[subset6\]\] \[receive\_retrieved\_messages\]

Notes:

-   <span class="code">channel\_name</span> and <span class="code">queue\_name</span> are mandatory
-   <span class="code">window\_size</span> and <span class="code">subset</span> are optional. If specified, they must appear in this order.

<span id="control_op"></span>

## Controlling output channels

You can use the following commands to control output channels:

-   <span class="codeBold_in_para">pelctl open\_output\_channel</span>
-   <span class="codeBold_in_para">pelctl close\_output\_channel</span>
-   <span class="codeBold_in_para">pelctl create\_output\_channel</span>
-   <span class="codeBold_in_para">pelctl delete\_output\_channel</span>

### pelctl open\_output\_channel


    pelctl  open_output_channel

       -outputchannel_name (-ocn) CHANNELNAME
       -queue_name (-qn) QUEUENAME
       [-site (-si) SITENAME]

This command opens the output channel with the name CHANNELNAME, for the queue QUEUENAME. You can use the optional <span class="code">site</span> parameter to specify the name of a Remote Site associated with the output channel.

### pelctl close\_output\_channel


    pelctl  close_output_channel

       -outputchannel_name (-ocn) CHANNELNAME
       [-site (-si) SITENAME]

This command closes the output channel with the name CHANNELNAME. You can use the optional <span class="code">site</span> parameter to specify the name of a Remote Site associated with the output channel.

<span id="pelctl_create_output_channel"></span>

### pelctl create\_output\_channel


    pelctl  create_output_channel

       [-site (-si) SITENAME]
       -outputchannel_name (-ocn) CHANNELNAME

This command creates the output channel on the specified site with the specified name.

#### Example

pelctl create\_output\_channel –site SWIFT7 -outputchannel\_name ptsafrkk\_outchannel1!x

<span id="pelctl_delete_output_channel"></span>

### pelctl delete\_output\_channel


    pelctl  delete_output_channel

       [-site (-si) SITENAME]
       -outputchannel_name (-ocn) CHANNELNAME

This command deletes the output channel on the specified site with the specified name.

#### Example

pelctl delete\_output\_channel –site SWIFT7 -outputchannel\_name ptsafrkk\_outchannel1!x

<span id="display_op"></span>

## Displaying information about output channels

### peldsp display\_site

Use <span class="codeBold_in_para">[peldsp display\_site](../../../../managing_partners_start_here/sites_start_here/managing_local_sites_cli/managing_remote_sites_cli#peldsp_display_site)</span> to display Site data, including SWIFTNet output channel information (if defined for the specified Site).

For each output channel, a line is displayed in the following format:

s\_output\_channel\_info = channel\_name queue\_name \[window\_size\] \[subset1...\[subset6\]\] \[receive\_retrieved\_messages\]

For details of parameters, refer to the table [above](#swift_op_ch_paras).

#### Example display (SWIFTNet-related data only)

\[...\]

s\_ra\_instance='Ra3'

s\_message\_partner='rnd1\_mp'

s\_event\_end\_point='rnd1\_eep'

s\_snf\_queues='bic1\_rnd1roqasfiafatf!x bic2\_rnd1roqasfiafatfdn!x'

s\_snl\_end\_point='rnd1\_sep'

s\_ra\_pathname=''

s\_ra\_config\_file=''

s\_sign\_ident\_list=''

s\_decrypt\_ident\_list=''

s\_backup\_site=''

s\_output\_channel\_info='bic3\_oc1!x bic4\_rnd1roqasfiafatf!x 10 InterAct FileAct\_Urgent N'

<span id="peldsp_status_swoutputsession"></span>

### peldsp status\_swoutputsession

Use <span class="codeBold_in_para">peldsp status\_swoutputsession</span> to display the status of an output session.


    peldsp  status_swoutputsession

       [-site (-si) SITENAME]
       [-queue_name (-qn) QUEUENAME]
       [-outputchannel_name (-ocn) CHANNELNAME]

#### peldsp status\_swoutputsession parameters

The following parameters (all optional) enable you to filter the response.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Parameter         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>-site (-si)</p>         </td>
         <td><p>Specify a Site name to get the status for this Site only.</p>         </td>
      </tr>
      <tr>
         <td><p>-queue_name (-qn)</p>         </td>
         <td><p>Specify a queue name to get the status for this queue only.</p>         </td>
      </tr>
      <tr>
         <td><p>-outputchannel_name (-ocn)</p>         </td>
         <td><p>Specify an output channel name to get the status for this output channel only.</p>         </td>
      </tr>
   </tbody>
</table>

#### Command output

For each output session, the <span class="codeBold_in_para">peldsp status\_swoutputsession</span> command displays several parameters:

-   Queue name
-   Output channel defined for that queue (if any)
-   The Site on which the queue is defined
-   <span class="code">sw\_snl\_status</span> – the actual status of the output session returned by the SAG (response to status request from SWIFT). Possible values:
    -   Active
    -   Acquiring
    -   TimedOut
    -   Closed

<!-- -->

-   <span class="code">sw\_gtw\_status</span> – the internal status of the output session. Possible values:
    -   Shut down
    -   Starting
    -   Running
    -   Asked to be closed
    -   Broken
    -   Stopped
    -   Status checking

#### Example output

sw\_queue\_name='bic1\_rndnrottsfiafa!x'

sw\_outputchannel\_name='bic2\_rndnrottsfiafa!x'

sw\_session\_id='bic3\_rndnrottsfiafa!x:p:000142'

sw\_site='SAGLIVE\_RNDN'

sw\_snl\_status='Active'

sw\_gtw\_status='Running'

sw\_queue\_name='bic4\_rndnrottsfiafadn!x'

sw\_outputchannel\_name='bic5\_rndnrottsfiafadn!x'

sw\_session\_id='bic6\_rndnrottsfiafadn!x:p:000098'

sw\_site='SAGLIVE\_RNDN'

sw\_snl\_status='Active'

sw\_gtw\_status='Running'

<span id="monitoring"></span>

## Monitoring output sessions

Currently there are two ways of monitoring output sessions:

-   **Subscribing to receive unsolicited events**  
    When Gateway starts up, during initialization, it subscribes to an EventEP (defined in the Remote Site **Event end point**/ <span class="code">event\_end\_point</span> parameter) which enables output session events to be received. Currently there is only one event, generated each time SNL detects that an output session (queue session or output channel session) was closed by SWIFT. Every time this event is received, it is logged by Gateway.
-   **Requesting status for each output session**  
    Gateway requests the status for each output session automatically. You can specify the time interval at which Gateway initiates the requests in the **[SnF check timer](../../../../configuration_start_here/config_connectors#snf_check_timer)** parameter in the configuration menu.

<span id="control_snf"></span>

## Controlling SnF session behavior

You can modify the following parameters in the configuration menu according to your SnF session requirements:

-   **[SnF check timer](../../../../configuration_start_here/config_connectors#snf_check_timer)**: Specify the time interval (in seconds) during which Gateway checks the status of the acquired SnF session or opened SnF sessions in case no activity has been noticed on that queue or output channel in that time interval.
-   **[Reacquire SnF session automatically](../../../../configuration_start_here/config_connectors#reacquire_snf)**: Select whether or not an SnF session should be reacquired/reopened automatically if it is lost.

### Controlling queues

For queues, you can use the following commands to control the queue operations manually:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Command         </th>
<th class="HeadD-Column1-Header1">Function         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><a href="#pelctl_acquire_swqueue">pelctl acquire_swqueue</a></p>         </td>
         <td><p>Acquire a queue</p>         </td>
      </tr>
      <tr>
         <td><p><a href="#pelctl_release_swqueue">pelctl release_swqueue</a></p>         </td>
         <td><p>Release a queue</p>         </td>
      </tr>
   </tbody>
</table>

<span id="pelctl_acquire_swqueue"></span>

#### pelctl acquire\_swqueue

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>Syntax</p>         </td>
         <td><p>pelctl  acquire_swqueue  {-queue_name (-n)}  [-site (-si)]  [-force (-f)]</p>         </td>
      </tr>
      <tr>
         <td><p>Description</p>         </td>
         <td><p>Use this command to trigger the acquisition of a registered queue.</p>         </td>
      </tr>
      <tr>
         <td><p>Mandatory parameters</p>         </td>
         <td><p><span class="code">-queue_name (-n)</span>: Enter the name of the queue.</p>         </td>
      </tr>
      <tr>
         <td><p>Optional parameters</p>         </td>
         <td><p><span class="code">-site (-si)</span>: Enter the name of the Site through which the queue is to be acquired (the same queue can be defined on more than one Site, in a nominal-backup relationship).</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-force (-f)</span>: Use this parameter to force the acquisition of the queue.</p>
<p>You can issue an acquire request but the queue may already be acquired. In that case Gateway checks the status of the current session. If the session is reported as Active then nothing further is done. If not, the queue is reacquired. When using the <span class="code">-force</span> parameter, the SnF session is renewed.</p>         </td>
      </tr>
      <tr>
         <td><p>Example</p>         </td>
         <td><p>pelctl  acquire_swqueue  -n ptsafrkk_crfa!x  -f</p>
<p>OK. Queue scheduled for operation.</p>
<p>SNET031I  19.09.2008  14:32:46  SWIFTLIVE_SNF_NT(CRNTSNFMP)      acquired queue ptsafrkk_crfa!x session ptsafrkk_crfa!x:p:631215.</p>
<p>SNET039I  19.09.2008  14:31:44  SWIFTLIVE_SNF_NT(CRNTSNFMP)      SnF session ptsafrkk_crfa!x:p:630940 returned status Active.</p>
<p>SNET103W  19.09.2008  14:31:43  Initiating queue status request for ptsafrkk_crfa!x:p:630940.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="pelctl_release_swqueue"></span>

#### pelctl release\_swqueue

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>Syntax</p>         </td>
         <td><p>pelctl  release_swqueue  {-queue_name (-n)}  [-site (-si)]</p>         </td>
      </tr>
      <tr>
         <td><p>Description</p>         </td>
         <td><p>Use this command to release the current SnF session of a specified queue.</p>         </td>
      </tr>
      <tr>
         <td><p>Mandatory parameters</p>         </td>
         <td><p><span class="code">-queue_name (-n)</span>: Enter the name of the queue.</p>         </td>
      </tr>
      <tr>
         <td><p>Optional parameters</p>         </td>
         <td><p><span class="code">-site (-si)</span>: Enter the name of the Site. This is useful if a queue is registered on multiple Sites (in a nominal-backup relationship).</p>         </td>
      </tr>
      <tr>
         <td><p>Usage</p>         </td>
         <td><p>Once an SnF session has been released manually, the queue is no longer monitored or reacquired, unless:</p>
<ul>
<li>The Site on which the queue is registered is restarted</li>
<li>Gateway is restarted</li>
<li>The queue is manually reacquired using the <span class="code" style="font-weight: bold;">pelctl acquire_swqueue</span> command</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Example</p>         </td>
         <td><p>pelctl  release_swqueue  -n ptsafrkk_crfa!x</p>
<p>OK. Queue scheduled for operation</p>
<p>SNET032I  19.09.2008  14:38:03  SWIFTLIVE_SNF_NT(CRNTSNFMP)      released session ptsafrkk_crfa!x:p:631215.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="display_queue"></span>

## Displaying information about queues

Use <span class="code">peldsp display\_site</span> to display Site data, including SWIFTNet queue information (if defined for the specified Site).

For the queue list, a line is displayed in the following format:

s\_snf\_queues='bic1\_rnd1roqasfiafatf!x bic2\_rnd1roqasfiafatfdn!x'

Use <span class="codeBold_in_para">[peldsp status\_swoutputsession](#peldsp_status_swoutputsession)</span> to display the status of a queue session.

<span id="more_info"></span>

## More information

For more information about SWIFTNet output channels, refer to the SWIFT official documentation.

Related topics

[SWIFTNet connector](../../swiftnet_connector)

[Configuring the <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>/SWIFTNet environment](../../swiftnet_connector/swiftnet_configuring)

[SWIFTNet queue sharing](../swiftnet_queue_sharing)

[Site objects: Parameters List](../../../../managing_partners_start_here/sites_start_here/managing_local_sites_cli/sites_parameter_list)

[Importing and exporting objects](../../../../starting_and_stopping_server/importing_and_exporting_objects)

[SWIFTNet (SNET) log messages](../../../../log_messages_about/swiftnet_messages_(snet))

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
