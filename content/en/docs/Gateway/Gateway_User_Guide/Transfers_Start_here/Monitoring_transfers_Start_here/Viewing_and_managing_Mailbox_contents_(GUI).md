{
    "title": "Viewing and managing Mailbox contents",
    "linkTitle": "Viewing and managing Mailbox contents",
    "weight": "160"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Transfers

[About Mailbox contents](#About)

[Viewing Mailbox contents](#Viewing_Mailbox_contents)

[Managing the Mailbox display](#Managing_Mailbox_display)

[Displaying Transfer Request record details](#Displaying_addl_transfer_info)

[Managing Mailbox contents](#Managing_Mailbox_contents)

[Purging Transfer Request records contained in the Mailbox](#Purging_mailbox)

<span id="About"></span>

## About Mailbox contents

You can use the Mailbox display and its associated context menus to view and manage the Mailbox contents.

Each time Gateway processes a Transfer Request it creates a record of the Request and stores it in the Mailbox. These records remain in the Mailbox until you:

-   Select and delete records
-   Purge the Mailbox
-   Reinitialize Gateway using <span class="code" style="font-weight: bold;">[pelmon init\_base](../viewing_and_managing_mailbox_contents_cli/managing_mailbox_cli#pelmon_init_base)</span>

<span id="Viewing_Mailbox_contents"></span>

## Viewing Mailbox contents

To view the Transfer Request records currently stored in the Mailbox:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Transfer Management</span> node.
2.  Click the <span style="font-weight: bold;">Transfers</span> node.  
    Gateway displays all currently stored Mailbox records in a table in the display pane. By default, Gateway displays a set of columns containing information about each transfer. The table columns contain the following information for each recorded Transfer (if the data exists for that transfer).  
    <span style="font-weight: bold;">Hint:</span> If you do not see the columns containing transfer details in your display, select <span style="font-weight: bold;">View/Details</span> from the GUI [Menu bar](../../../user_interfaces_about/gui_using#View_menu).

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Column heading</p>         </th>
<th class="HeadD-Column1-Header1"><p>Meaning</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Local ident</p>         </td>
         <td><p>Local Transfer Identifier: The number attributed by Gateway to identify the transfer.</p>
<p>Gateway begins by attributing the number 1, and increments the number by 1 for each successive transfer.</p>         </td>
      </tr>
      <tr>
         <td><p>File name</p>         </td>
         <td><p>According to the transfer context, this name can be the:</p>
<ul>
<li>Name of the Application object associated with the transfer</li>
<li>Name of the transferred file</li>
<li>Name of the local Gateway system (VFD)</li>
<li>Physical or logical name of the file on the remote system</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Dir name</p>         </td>
         <td><p>For HTTP, FTP and SFTP only</p>
<p>The absolute path of the directory that contains the file to transfer. The location of the directory depends on the mode:</p>
<ul>
<li>Initiator mode: a directory on the remote system</li>
<li>Responder mode: a directory in the VFD</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Remote agent</p>         </td>
         <td><p>Alias of the associated Remote Site</p>         </td>
      </tr>
      <tr>
         <td><p>Originator</p>         </td>
         <td><p>Originator protocol identifier</p>         </td>
      </tr>
      <tr>
         <td><p>Destination</p>         </td>
         <td><p>Destination protocol identifier</p>         </td>
      </tr>
      <tr>
         <td><p>Application</p>         </td>
         <td><p>The name of the Application object associated with the transfer</p>         </td>
      </tr>
      <tr>
         <td><p>Protocol</p>         </td>
         <td><p>Protocol supporting the transfer</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Transfer type</p>
<p>Gateway displays one of the following values:</p>
<ul>
<li>TRANS</li>
<li>LIST</li>
<li>POLL</li>
<li>LOTS</li>
<li>EERP</li>
<li>SELECT</li>
<li>MSG</li>
<li>DIR</li>
<li>MDN</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Mode</p>         </td>
         <td><p>Connection mode for the transfer (Initiator/Responder)</p>         </td>
      </tr>
      <tr>
         <td><p>Direction</p>         </td>
         <td><p>Transfer direction (Send/Receive)</p>         </td>
      </tr>
      <tr>
         <td><p>Xfer ident</p>         </td>
         <td><p>Protocol identifier of the Transfer.</p>
<p>In Initiator mode, the identifier is the local protocol identifier.</p>
<p>In Responder mode, the identifier is the partner protocol identifier.</p>         </td>
      </tr>
      <tr>
         <td><p>State</p>         </td>
         <td><p>Transfer state</p>
<p>One of:</p>
<ul>
<li>Frozen (F)</li>
<li>Delayed (D)</li>
<li>To_Begin (B)</li>
<li>Processing (P)</li>
<li>To_Restart (R)</li>
<li>Suspended (S)</li>
<li>Ended (E)</li>
<li>Canceled (C)</li>
<li>Interrupted (I)</li>
<li>serVicing (V)</li>
<li>Acked (A)</li>
<li>CreaTed (T)</li>
<li>Deleted (Z)</li>
<li>Ended_to_ack (W)</li>
<li>To_SiGn (G)</li>
<li>Nacked_User (U)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>File component</p>         </td>
         <td><p>Local name of the transferred file.</p>
<p>The default the reception file identity is a seven-character number in the forma: <span class="code">F[local identity number]</span>. For example, the first transfer has the number <span class="code">F000001</span></p>         </td>
      </tr>
      <tr>
         <td><p>Dir path</p>         </td>
         <td><p>Local directory path of the transferred file</p>         </td>
      </tr>
      <tr>
         <td><p>Size</p>         </td>
         <td><p>Size in bytes of the transferred file</p>         </td>
      </tr>
      <tr>
         <td><p>Route state</p>         </td>
         <td><p>Routing state</p>
<ul>
<li>TO_ROUTE</li>
<li>ROUTED</li>
<li>FAILED</li>
<li>ACKNOWLEDGED</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>User state</p>         </td>
         <td><p>User state field managed by the user application. Gateway does not interpret this field</p>         </td>
      </tr>
      <tr>
         <td><p>Param1</p>         </td>
         <td><p>User parameter 1</p>         </td>
      </tr>
      <tr>
         <td><p>Param2</p>         </td>
         <td><p>User parameter 2</p>         </td>
      </tr>
      <tr>
         <td><p>Model</p>         </td>
         <td><p>Model used to submit the Transfer Request</p>         </td>
      </tr>
      <tr>
         <td><p>File label</p>         </td>
         <td><p>Protocol label of the file, for PeSIT HS only (PI 37)</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Managing_Mailbox_display"></span>

## Managing the Mailbox display

As described in the previous section, when you click the <span style="font-weight: bold;">Transfers</span> node of the Directory tree structure, you display a list of the Transfer Request records that are contained in the Mailbox.

To manage the contents of the display, right-click anywhere in the display pane (except in the <span style="font-style: italic;">Local Ident</span> column). Gateway displays the following context menu:

<img src="/Images/Gateway/mailbox_display_menu.gif" width="182" height="112" />

The following table lists and describes the commands you can use in this context menu to manage the display of Transfer Request records.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Menu command</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Open</p>         </td>
         <td><p>Displays the view of the Mailbox contents in a separate window. This enables you call up a view of the Mailbox contents while viewing other windows of the GUI.</p>
<p>Example: Use this command to generate a separate window display of the Mailbox records, then click the <span style="font-weight: bold;">Log</span> icon to display the list of log messages in the display pane. You can now view the Mailbox as needed by selecting the Transfer window name from the drop-down list of the <span style="font-weight: bold;">Window</span> menu in the GUI Menu bar.</p>         </td>
      </tr>
      <tr>
         <td><p>Find...</p>         </td>
         <td><p>Opens the search window, enabling you to search record entries for a given word or number.</p>         </td>
      </tr>
      <tr>
         <td><p>Select...</p>         </td>
         <td><p>Opens <span style="font-style: italic;">Select Transfer</span> window, enabling you to filter the display of Transfer Request Records by one or more criteria.</p>
<p>Alternatively, to open this window, in the left pane right-click <span style="font-weight: bold;">Transfers</span> and then choose <span style="font-weight: bold;">Select</span> from the context menu.</p>
<p>Use any combination of the following criteria to generate a filtered list:</p>
<ul>
<li>Protocol</li>
<li>Direction (Send/Receive)</li>
<li>Mode (Send/Receive)</li>
<li>File name</li>
<li>Application</li>
<li>Model</li>
<li>Originator Site Alias</li>
<li>Destination Site Alias</li>
<li>Originator Site Protocol ID</li>
<li>Destination Site Protocol ID</li>
<li>Transfer ID</li>
<li>Diffusion Request ID</li>
<li>Rank</li>
<li>Permanent transfer</li>
<li>User state</li>
<li>User parameter 1</li>
<li>User parameter 2</li>
<li>Creation date and time</li>
<li>Transfer status</li>
<li>Route status</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Refresh</p>         </td>
         <td><p>Refreshes the display of Transfer Request records, taking into account the most recently processed records.</p>         </td>
      </tr>
      <tr>
         <td><p>Automatic refresh...</p>         </td>
         <td><p>Opens the Refresh dialog box, enabling you to set an automatic refresh interval in increments of 10 seconds.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Displaying_addl_transfer_info"></span>

## Displaying additional Transfer Request information

To obtain additional information about a Transfer Request, double-click the row representing the Transfer Request record in the display pane.

Gateway displays the <span style="font-style: italic;">Transfer Request Detail</span> window.

Alternatively, to open this window you can right-click the status icon at the beginning of the row that represents the Transfer Request you want to view. Then select <span style="font-weight: bold;">View</span> from the context menu that appears.

The window contains several tabs. Each tab displays a specific set of information about the Transfer Request, as summarized in the following table.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Tab name</p>         </th>
<th class="HeadD-Column1-Header1"><p>Contains...</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>General</p>         </td>
         <td><p>General information about the Transfer Request:</p>
<ul>
<li>Local identifier (identity of the transfer)</li>
<li>Transfer type</li>
<li>Mode (initiator or receiver)</li>
<li>Protocol type</li>
<li>Associated Application object</li>
<li>Group name of Application object</li>
<li>Transfer processing state</li>
<li>acknowledgment option status</li>
<li>Purge option status</li>
<li>Associated transfer model</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Attributes</p>         </td>
         <td><p>Information about the transferred file:</p>
<ul>
<li>File formatting:
<ul>
<li>Padding</li>
<li>Truncating</li>
</ul></li>
<li>Local attributes:
<ul>
<li>Directory path</li>
<li>File component</li>
<li>Record format</li>
<li>Record length</li>
<li>Data code</li>
<li>Text option status</li>
</ul></li>
<li>Transfer attributes:
<ul>
<li>Transfer identifier</li>
<li>RFD directory option status</li>
<li>Directory name</li>
<li>File name</li>
<li>Record format</li>
<li>Record length</li>
<li>New line convention</li>
<li>Data code</li>
<li>Compression option status</li>
</ul></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>User</p>         </td>
         <td><p>Information about the local user:</p>
<ul>
<li>User name</li>
<li>User state</li>
<li>User processed</li>
<li>End transfer script</li>
<li>User specific parameters 1 and 2</li>
<li>attached message on send</li>
<li>attached message on receive</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Security</p>         </td>
         <td><p>Security-related information:</p>
<ul>
<li>Local encryption:
<ul>
<li>File encryption status</li>
</ul></li>
<li>TLS:
<ul>
<li>Security profile name</li>
<li>Cipher suite name</li>
<li>Client authentication option status</li>
<li>Server authentication option status</li>
</ul></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Link</p>         </td>
         <td><p>Routing characteristics:</p>
<ul>
<li>Routing
<ul>
<li>Route state</li>
<li>Route from</li>
<li>Route to</li>
<li>Reply by</li>
<li>Reply to</li>
</ul></li>
<li>Diffusion list
<ul>
<li>Local identifier</li>
<li>Next local ID</li>
</ul></li>
<li>Generic reception
<ul>
<li>Local identifier</li>
<li>Previous local ID</li>
<li>Next local ID</li>
<li>Maximum requests</li>
<li>Maximum files</li>
<li>Total requests</li>
<li>Total files</li>
</ul></li>
<li>Permanent
<ul>
<li>Permanent option status</li>
<li>Duplicated from</li>
</ul></li>
<li>Connection parameters
<ul>
<li>Called address</li>
<li>Called SAP</li>
<li>HTTP Host Name</li>
</ul></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Sentinel</p>         </td>
         <td><p>Sentinel-related information:</p>
<ul>
<li>Transfer filter</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Statistics</p>         </td>
         <td><p>Statistical information about transfer processing:</p>
<ul>
<li>General data:
<ul>
<li>Last end reason</li>
<li>Last end diag (last protocol error)</li>
<li>Maximum number of retries</li>
<li>Number of retries</li>
<li>Number of bytes</li>
<li>Number of bytes transferred</li>
<li>File size</li>
<li>Number of records</li>
<li>Allocation size</li>
<li>Creation date</li>
<li>Extraction date</li>
</ul></li>
<li>Timing data:
<ul>
<li>Priority</li>
<li>Earliest start date</li>
<li>Latest start date</li>
<li>Creation date and time</li>
<li>End date and time</li>
<li>Beginning date and time</li>
<li>Day of year (n/365)</li>
</ul></li>
<li>Diffusion Lists</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>[<span style="font-style: italic;">protocol name</span>]</p>         </td>
         <td><p>The contents of this tab vary depending on the protocol used for the transfer.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Managing_Mailbox_contents"></span>

## Managing Mailbox contents

In the right (display) pane of the GUI main window, right-click the status icon located at the beginning of the row that represents any Transfer Request. Gateway opens the following context menu.

<img src="/Images/Gateway/mailbox_context_menu_2.gif" width="268" height="253" />

The commands that are available to you depend on the characteristics of the Mailbox record you have selected. In the above example, some commands are deactivated because they do not relate to the Mailbox record of the Transfer Request.

The following table lists and describes the commands you can use in this context menu to manage your Mailbox contents.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Menu command</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>View...</p>         </td>
         <td><p>Opens the <span style="font-style: italic;">Transfer Request Detail</span> window, enabling you to view details of the Transfer Request record.</p>         </td>
      </tr>
      <tr>
         <td><p>Modify...</p>         </td>
         <td><p>Opens an editing window that enables you to modify the following data related to the Transfer Request record:</p>
<ul>
<li>General information:
<ul>
<li>User parameter 1</li>
<li>User parameter 2</li>
<li>User state</li>
<li>Purge option</li>
<li>User processed state</li>
</ul></li>
<li>Timing parameters
<ul>
<li>Earliest date and time or relative time</li>
<li>Latest date and time or relative time</li>
</ul></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span id="Delete"></span>Delete</p>         </td>
         <td><p>Opens the <span style="font-style: italic;">Delete confirmation</span> window, enabling you to confirm or abandon the deletion of a Transfer Request record.</p>         </td>
      </tr>
      <tr>
         <td><p>Cancel a transfer</p>         </td>
         <td><p>Cancels the transfer (if the selected record represents a transfer in a state that permits cancellation).</p>         </td>
      </tr>
      <tr>
         <td><p>Restart a transfer</p>         </td>
         <td><p>Restarts the transfer (if the selected record represents a transfer in a state that permits restarting).</p>         </td>
      </tr>
      <tr>
         <td><p>Suspend a transfer</p>         </td>
         <td><p>Suspends the transfer (if the selected record represents a transfer in a state that permits suspension of processing).</p>         </td>
      </tr>
      <tr>
         <td><p>Ack a transfer</p>         </td>
         <td><p>Opens the <span style="font-style: italic;">New acknowledgment message</span> window (if the selected record represents a transfer in a state that permits acknowledgment). You can use the <span style="font-style: italic;">New acknowledgment message</span> window to create and send an acknowledgment.</p>
<p>Refer to <a href="../../submitting_transfer_requests_start_here/working_with_ack_messages">Working with acknowledgment Messages</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>Expand Diffusion List...</p>         </td>
         <td><p>This command is active in the menu when you right-click the record of a Transfer Request with a Diffusion List selected as destination alias.</p>
<p>When you select this command Gateway regenerates the Mailbox display to show the records of transfers to each member of the Diffusion List.</p>         </td>
      </tr>
      <tr>
         <td><p>Associated routed transfer...</p>         </td>
         <td><p>This command is active in the menu when you right-click the record of a Transfer Request that is linked via a Decision Rule to the deposit of a new Transfer Request.</p>
<p>When you select this command, Gateway displays a new window that contains details of the associated Transfer Request.</p>         </td>
      </tr>
      <tr>
         <td><p>Associated permanent transfer...</p>         </td>
         <td><p>This command is active in the menu when you right-click the record of a Transfer Request that was made with the <span style="font-style: italic;">Permanent</span> option active (Permanent = Yes).</p>
<p>When Gateway acts as a server, in normal mode (Permanent = No) Gateway makes a specified file available file only to the first client that deposits a Transfer Request for the file. When you activate the Permanent option (Permanent = Yes) Gateway responds to each client Transfer Request by sending a copy of the requested file, keeping the original in the database available for subsequent client Transfer Requests.</p>
<p>When you right-click any client Transfer Request record for a file that is referenced by a Permanent server Transfer Request, Gateway displays the original server Transfer Request containing the Permanent option selection.</p>
<p>Use this command, for example, when you want to locate and terminate the Transfer Request that makes a given file permanently available to one or more clients.</p>         </td>
      </tr>
      <tr>
         <td><p>Associated log messages</p>         </td>
         <td><p>When you select this command, Gateway displays log messages of the associated Transfer Request in the Log display pane.</p>         </td>
      </tr>
      <tr>
         <td><p>Print the selection</p>         </td>
         <td><p>Prints the selected record(s) as displayed in the Mailbox frame.</p>         </td>
      </tr>
      <tr>
         <td><p>Copy the selection onto the clipboard</p>         </td>
         <td><p>Copies the selected records to the clipboard.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Purging_mailbox"></span>

## Purging records of Transfer Requests

To purge one or more Transfer Request records from the Gateway Mailbox:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Transfer Management</span> node.
2.  Right-click <span style="font-weight: bold;">Transfers</span>, and then select <span style="font-weight: bold;">Purge...</span> from the context menu.  
    Gateway opens the <span style="font-style: italic;">Purge Transfer Requests</span> window.
3.  Complete the <span style="font-weight: bold;">Purge Options</span> tab. (See table below.)
4.  Complete the <span style="font-weight: bold;">Select Transfer</span> tab. (See table below.)
5.  Click <span style="font-weight: bold;">OK</span> to validate and apply the selection criteria.  
    Gateway executes the purge based on all criteria entered in both tabs and regenerates the Mailbox display to show the new results.

<span id="Purge_Options"></span>

### Purge Transfer Requests: Purge Options tab

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Field</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Purge Request Name</p>         </td>
         <td><p>Enter a name for the Purge request.</p>
<p>Gateway uses this name in any log messages concerning the purge operation.</p>         </td>
      </tr>
      <tr>
         <td><p>Keep transfers more recent</p>         </td>
         <td><p>Enter the number of days that you want to keep transfer records.</p>
<p>Gateway deletes all records older than this specified period.</p>         </td>
      </tr>
      <tr>
         <td><p>Purge the file sent or received</p>         </td>
         <td><p>Select this option to delete the sent or received file as well as the associated record.
There is an exception when only the associated record is deleted, and not the files sent or received: when the transfer is routed to Integrator.</p>
<p>For more information, refer to <a href="../../../connectors_about/integrator_about/integrator_connector#Purging">Purging for transfers routed from Gateway to Integrator</a></p>         </td>
      </tr>
      <tr>
         <td><p>Purge generated XPR script and output files</p>         </td>
         <td><p>For transfers that are associated with XPR scripts that create output files on end of transfer, select this option to purge the generated output files.</p>         </td>
      </tr>
      <tr>
         <td><strong>Purge only temporary files</strong>         </td>
         <td>Select this option to delete only the temporary files related to the transfers.         </td>
      </tr>
      <tr>
         <td><p>Create archive file</p>         </td>
         <td><p>Select this option to generate an archive of the deleted Mailbox records.</p>         </td>
      </tr>
      <tr>
         <td><strong>Keep mailbox entries</strong>         </td>
         <td>Select this option to keep xfer records in mailbox.         </td>
      </tr>
   </tbody>
</table>

<span id="Select_Transfer_tab"></span>

### Purge Transfer Requests: Select Transfer tab

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Field</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Protocol</p>         </td>
         <td><p>Select a protocol as criteria for the purge operation.</p>
<p>To choose all protocols, select <span style="font-weight: bold;">(empty)</span>.</p>         </td>
      </tr>
      <tr>
         <td><p>Direction</p>         </td>
         <td><p>Click to select one or both of the transfer directions:</p>
<ul>
<li>Send</li>
<li>Receive</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Mode</p>         </td>
         <td><p>Click to select one or both of the transfer modes:</p>
<ul>
<li>Initiator</li>
<li>Responder</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>File Name</p>         </td>
         <td><p>Enter the name of a transferred file to use as criteria for the purge operation.</p>         </td>
      </tr>
      <tr>
         <td><p>Application</p>         </td>
         <td><p>Select the name of an Application to use as criteria for the purge operation.</p>         </td>
      </tr>
      <tr>
         <td><p>Model</p>         </td>
         <td><p>Select the name of an Application to use as criteria for the purge operation.</p>         </td>
      </tr>
      <tr>
         <td><p>Sites Alias:</p>         </td>
      </tr>
      <tr>
         <td><p>Originator</p>         </td>
         <td><p>Select an Originating Site alias to use as criteria for the purge operation.</p>         </td>
      </tr>
      <tr>
         <td><p>Destination</p>         </td>
         <td><p>Select a Destination Site alias to use as criteria for the purge operation.</p>         </td>
      </tr>
      <tr>
         <td><p>Sites Protocol Identifier:</p>         </td>
      </tr>
      <tr>
         <td><p>Originator</p>         </td>
         <td><p>Select an Originating Site protocol identifier to use as criteria for the purge operation.</p>         </td>
      </tr>
      <tr>
         <td><p>Destination</p>         </td>
         <td><p>Select a Destination Site protocol identifier to use as criteria for the purge operation.</p>         </td>
      </tr>
      <tr>
         <td><p>Creation Date</p>         </td>
         <td><p>Use the two date selection boxes to specify a date range for the purge operation.</p>
<ul>
<li>Beginning Date: Click to select this box, then enter a beginning date limit. To use a calendar to select the beginning date, click the down arrow displayed in the box. Messages created before this limiting date are not selected for the purge operation.</li>
<li>Ending Date box: Click to select this box, then an ending date limit. To use a calendar to select the ending date, click the down arrow displayed in the box. Messages created after this limiting date are not selected for the purge operation.</li>
</ul>
<p>You can use only one of the two boxes to set only a beginning or only and ending date selection criteria.</p>
<p>If you enter dates in both boxes, messages with creation dates that fall within this range are selected for purging.</p>         </td>
      </tr>
      <tr>
         <td><p>Transfer status</p>         </td>
         <td><p>To use a transfer status as message selection criteria, select one or more options from the displayed list.</p>
<p>To select records of all terminated transfers in the Mailbox, select <span style="font-weight: bold;">all terminated transfers</span>.</p>         </td>
      </tr>
      <tr>
         <td><p>Route status</p>         </td>
         <td><p>To use a routing status as message selection criteria for the purge operation, click to select one or more statuses from the displayed list.</p>
<p>To select records of all routed transfers in the Mailbox, select <span style="font-weight: bold;">All</span>.</p>         </td>
      </tr>
      <tr>
         <td><p>Transfer ID</p>         </td>
         <td><p>Use the two <strong>Transfer ID</strong> boxes to create a range of ID numbers as selection criteria for the purge operation. Enter the minimum range limit number in the left box, and the maximum range limit number in the right box.</p>         </td>
      </tr>
      <tr>
         <td><p>Rank</p>         </td>
         <td><p>Use the two <strong>Rank</strong> boxes to create a range of rank numbers as selection criteria for the purge operation. Enter the minimum rank range number in the left box, and the maximum rank range number in the right box.</p>         </td>
      </tr>
      <tr>
         <td><p>User State</p>         </td>
         <td><p>Enter a user state as message selection criteria for the purge operation.</p>         </td>
      </tr>
      <tr>
         <td><p>Param 1</p>         </td>
         <td><p>Enter a User Parameter1 as message selection criteria for the purge operation.</p>         </td>
      </tr>
      <tr>
         <td><p>Param 2</p>         </td>
         <td><p>Enter a User Parameter2 as message selection criteria for the purge operation.</p>         </td>
      </tr>
      <tr>
         <td><p>Permanent Transfer</p>         </td>
         <td><p>To select all permanent transfers for the purge operation, select this option.</p>         </td>
      </tr>
      <tr>
         <td><p>Diffusion request ID</p>         </td>
         <td><p>Enter a Diffusion List type ID number as selection criteria for the purge operation.</p>         </td>
      </tr>
   </tbody>
</table>

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
