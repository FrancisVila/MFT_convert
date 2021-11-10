{
    "title": "Working with applications",
    "linkTitle": "Working with applications",
    "weight": "170"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Transfers

[Creating a new Application object](#Creating_a_new_Application_object)

[Displaying a list of Application objects](#Displaying_a_list_of_Application_objects)

[Displaying a list of selected Application objects](#Displaying_a_selected_list_of_application_objects)

[Displaying the attributes of a specified Application object](#Viewing_attributes_of_Application_objects)

[Modifying an Application object](#Modifying_Application_objects)

[Deleting an Application object](#Deleting_Application_objects)

<span id="Creating_a_new_Application_object"></span>

## Creating a new Application object

To create a new Application object:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:  
    <span style="font-weight: bold;">Transfer Management > Parameters</span>
2.  Right-click the <span style="font-weight: bold;">Application</span> sub-node, then from the context menu select <span style="font-weight: bold;">New</span>.  
    Gateway displays the <span style="font-style: italic;">New Application</span> window with the following tabs:
    -   [General](#General_tab)
    -   [Physical file attributes](#Physical_file_attributes)
    -   [Transfer attributes](#Transfer_attributes)
    -   [Options](#Options)
    -   [PeSIT E / OFTP](#PeSIT_HS_E)
    -   [SMTP/POP3](#SMTP_POP3)
3.  Complete the tabs according to your transfer requirements. The following tables describe the parameters and possible values you can attribute in each tab.

<span id="General_tab"></span>

### New Application: General tab

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Field</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Name</p>         </td>
         <td><p>Enter the Application name.<br />
Maximum:</p>
<ul>
<li>8 alphanumeric characters for PEL</li>
<li>27 alphanumeric characters for all other protocols</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Group</p>         </td>
         <td><p>Enter the Group name.<br />
Maximum: 15 alphanumeric characters.<br />
Default = <span style="font-weight: bold;">GDEFAULT</span>.</p>         </td>
      </tr>
      <tr>
         <td><p>Model</p>         </td>
         <td><p>Enter the Model name used to create the Transfer Request.<br />
Maximum: 25 alphanumeric characters.</p>
<p>Alternatively, select a Model from the drop-down list.</p>         </td>
      </tr>
      <tr>
         <td><p>Comments</p>         </td>
         <td><p>Enter a free-text description of the Application.<br />
Maximum: 80 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Direction</p>         </td>
         <td><p>Select one or both of the following Transfer directions:</p>
<ul>
<li>Send</li>
<li>Receive</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

<span id="Physical_file_attributes"></span>

### New Application: Physical file attributes tab

Use the fields on the <span style="font-weight: bold;">Physical file attributes</span> tab to define the attributes of files stored locally.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Field</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><strong>Reception</strong></p>         </td>
      </tr>
      <tr>
         <td><p>Directory for received files</p>         </td>
         <td><p>Enter the name of the storage directory for received files.<br />
Maximum: 127 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Received file name</p>         </td>
         <td><p>Enter the name for the received file.<br />
Maximum: 127 alphanumeric characters.</p>
<p>You can use <a href="../../../../managing_events_start_here/defining_decision_rule_conditions#Using_symbolic_variables">symbolic variables</a> in this field. For example, you could specify the received file with the following path and name:</p>
<p>   C:\&lt;Gateway installation directory&gt;<br />
\run_time\tmp\&amp;(x_file_name)<br />
\D&amp;(x_destination)L&amp;(x_file_label)I&amp;(x_local_ident).txt</p>         </td>
      </tr>
      <tr>
         <td><p>Encrypt received files</p>         </td>
         <td><p>Select this option to encrypt received files.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Local file attributes</strong></p>         </td>
      </tr>
      <tr>
         <td><p>Organization</p>         </td>
         <td><p>Select the type of local file organization:</p>
<ul>
<li>Sequential</li>
<li>Indexed</li>
<li>Relative</li>
<li>Undefined</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Record format</p>         </td>
         <td><p>Select the record format for the local file:</p>
<ul>
<li>Variable Text</li>
<li>Variable</li>
<li>Fixed Text</li>
<li>Fixed</li>
<li>Stream</li>
<li>Stream Text</li>
<li>Undefined</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Record length</p>         </td>
         <td><p>Specify the record length for the local file.<br />
Integer: <span style="font-weight: bold;">0 - 32 768</span>. Default = <span style="font-weight: bold;">1024</span>.</p>
<p>The value that you enter in this field must be less than or equal to the <span style="font-weight: bold;">Maximum data block size</span> parameter (<span class="code" style="font-weight: bold;">-</span><span class="code">data_size_max)</span> defined in the corresponding Remote Site.</p>         </td>
      </tr>
      <tr>
         <td><p>Data code</p>         </td>
         <td><p>Select the data type for the local file.</p>         </td>
      </tr>
      <tr>
         <td><p>Padding character (Hexa)</p>         </td>
         <td><p>Specify the padding character.<br />
Hexadecimal number: <span style="font-weight: bold;">00 - FF</span>. Default = <span style="font-weight: bold;">00</span>.</p>         </td>
      </tr>
      <tr>
         <td><p>Check records</p>         </td>
         <td><p>This option determines whether or not records are checked in RFD (Real File Directory) mode.</p>
<p>Deselect this option to skip the record checking phase. This is useful if the check takes too long (for example, with large ASCII files) and there is the risk of a time-out on the client side.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Transfer_attributes"></span>

### New Application: Transfer attributes tab

Use the fields on the <span style="font-weight: bold;">Transfer attributes</span> tab to define the attributes of files that you transfer over the network.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Field</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><strong>Transfer attributes</strong></p>         </td>
      </tr>
      <tr>
         <td><p>Organization</p>         </td>
         <td><p>Select the type of file organization:</p>
<ul>
<li>Sequential</li>
<li>Indexed</li>
<li>Relative</li>
<li>Undefined</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Record format</p>         </td>
         <td><p>Select the record format for the transferred file:</p>
<ul>
<li>Variable</li>
<li>Fixed</li>
<li>Stream</li>
<li><span style="font-weight: bold;">Text</span> (<span style="font-style: italic;">OFTP only</span>)</li>
<li>Undefined</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Record length</p>         </td>
         <td><p>Specify the record length for the transferred file.<br />
Integer: <span style="font-weight: bold;">0 -</span> <span style="font-weight: bold;">32768</span>. Default = <span style="font-weight: bold;">1024</span>.</p>         </td>
      </tr>
      <tr>
         <td><p>Data code</p>         </td>
         <td><p>Select the data type for the Transfer.</p>         </td>
      </tr>
      <tr>
         <td><p>Compression</p>         </td>
         <td><p>Select the compression option:</p>
<ul>
<li>No</li>
<li>Horizontal</li>
<li>Vertical</li>
<li>Both</li>
<li>Zlib</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><strong>Responder mode</strong></p>         </td>
      </tr>
      <tr>
         <td><p>Local file name</p>         </td>
         <td><p>Only complete this field if you are in <span style="font-weight: bold;">Responder</span> mode.</p>
<p>Specify the protocol name of the file sent or received.<br />
Maximum: 127 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Local directory (VFD)</p>         </td>
         <td><p>Only complete this field if:</p>
<ul>
<li>the connection mode is <span style="font-weight: bold;">Responder</span> and the direction is <span style="font-weight: bold;">Send</span></li>
<li>the file transfer protocol is FTP, SFTP or HTTP</li>
</ul>
<p>Specify the VFD absolute path of the local directory that stores the file to send.<br />
Maximum: 127 alphanumeric characters.</p>
<p>Alternatively, click the <span style="font-weight: bold;">Browse</span> button to select a directory from the <span style="font-style: italic;">VFD browse</span> window.</p>         </td>
      </tr>
      <tr>
         <td><p>Local directory alias</p>         </td>
         <td><p>Only complete this field if:</p>
<ul>
<li>you did not complete the <span style="font-weight: bold;">Local directory</span> field</li>
<li>the connection mode is <span style="font-weight: bold;">Responder</span> and the direction is <span style="font-weight: bold;">Send</span></li>
<li>the file transfer protocol is FTP, SFTP or HTTP</li>
</ul>
<p>Specify the VFD alias of the local directory that stores the file to send.<br />
Maximum: 32 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Initiator mode</strong></p>         </td>
      </tr>
      <tr>
         <td><p>Remote file name</p>         </td>
         <td><p>Only complete this field if you are in <span style="font-weight: bold;">Initiator</span> mode.</p>
<p>Enter the protocol name of the file sent to, or received from, the Remote Site.<br />
Maximum: 127 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Remote directory</p>         </td>
         <td><p>Enter the absolute path of the remote directory for the file sent or received.<br />
Maximum: 127 alphanumeric characters.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Options"></span>

### New Application: Options tab

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Field</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><strong>Physical file attributes</strong></p>         </td>
      </tr>
      <tr>
         <td><p>System file type</p>         </td>
         <td><p>Specify the file type depending on the system: BULL, AS400, GCOS and TANDEM machines.</p>         </td>
      </tr>
      <tr>
         <td><p>Physical block size</p>         </td>
         <td><p>Specify the block size in bytes. Default = <span style="font-weight: bold;">1024</span>.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>User parameters</strong></p>         </td>
      </tr>
      <tr>
         <td><p>Param 1</p>         </td>
         <td><p>Enter user parameter 1.<br />
Maximum: 40 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Param 2</p>         </td>
         <td><p>Enter user parameter 2.<br />
Maximum: 40 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Sentinel</strong></p>         </td>
      </tr>
      <tr>
         <td><p>Sentinel Transfer Filter</p>         </td>
         <td><p>Use this option to send a record of Transfer state changes to Sentinel.<br />
Select one of the following:</p>
<ul>
<li><span style="font-weight: bold;">All</span>: sends all Transfer state changes to Sentinel</li>
<li><span style="font-weight: bold;">Summary</span>: sends a summary of Transfer state changes (canceled, ended, acked, created, to begin)</li>
<li><span style="font-weight: bold;">None</span>: sends no Transfer state changes</li>
<li><span style="font-weight: bold;">Undefined</span>: Gateway searches for the definition first in the Remote Site, and then in the configuration file</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

<span id="PeSIT_HS_E"></span>

### New Application: PeSIT E / OFTP tab

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Field</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><strong>Sender</strong></p>         </td>
      </tr>
      <tr>
         <td><p>User ID</p>         </td>
         <td><p>Specify the sender User name.<br />
Maximum: 8 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Application ID</p>         </td>
         <td><p>Specify the sender Application name.<br />
Maximum: 8 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Message text</p>         </td>
         <td><p>Enter a free-text description for the sender.<br />
Maximum: 8 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Receiver</strong></p>         </td>
      </tr>
      <tr>
         <td><p>User ID</p>         </td>
         <td><p>Specify the receiver User name.<br />
Maximum: 8 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Application ID</p>         </td>
         <td><p>Specify the receiver Application name.<br />
Maximum: 8 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Message text</p>         </td>
         <td><p>Enter a free-text description for the receiver.<br />
Maximum: 8 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Receiving a pre-existing file</strong><br />
Presence-check indicator of the transferred file. The values in this section define the action of the monitor if the file being transferred already exits.</p>         </td>
      </tr>
      <tr>
         <td><p>File availability</p>         </td>
         <td><p>Select one of the following values:</p>
<ul>
<li>Undefined</li>
<li>New</li>
<li>Old</li>
<li>Both</li>
</ul>
<p>Gateway responds to the various possible pre-existing file conditions depending on the values of the <span style="font-weight: bold;">File availability</span> and <span style="font-weight: bold;">File action</span> parameters.</p>
<p>Refer to the description of the <span style="font-weight: bold;">File action</span> parameter below.</p>         </td>
      </tr>
      <tr>
         <td><p>File action</p>         </td>
         <td><p>Select one of the following values:</p>
<ul>
<li>Undefined</li>
<li>Erase</li>
<li>Delete</li>
<li>Verify</li>
</ul>
<p>To determine how to handle a pre-existing file, Gateway interprets the <span style="font-weight: bold;">File availability</span> and <span style="font-weight: bold;">File action</span> parameter values as follows:</p>
<p>If <span style="font-weight: bold;">File availability</span> is set to:</p>
<ul>
<li><span style="font-weight: bold;">NEW</span> and a valid file with the same file name already exists, then:
<ul>
<li><strong>ERASE</strong> = refuse</li>
<li><strong>DELETE</strong> = refuse</li>
<li><strong>VERIFY</strong> = refuse</li>
</ul></li>
<li><span style="font-weight: bold;">NEW</span> and a file with the same file name does not already exist, then:
<ul>
<li><strong>ERASE</strong> = accept</li>
<li><strong>DELETE</strong> = accept</li>
<li><strong>VERIFY</strong> = accept</li>
</ul></li>
<li><span style="font-weight: bold;">OLD</span> and a valid file with the same file name already exists, then:
<ul>
<li><strong>ERASE</strong> = accept</li>
<li><strong>DELETE</strong> = accept</li>
<li><strong>VERIFY</strong> = accept if empty, refuse if not empty</li>
</ul></li>
<li><span style="font-weight: bold;">OLD</span> and a file with the same file name does not already exist, then:
<ul>
<li><strong>ERASE</strong> = refuse</li>
<li><strong>DELETE</strong> = refuse</li>
<li><strong>VERIFY</strong> = refuse</li>
</ul></li>
<li><span style="font-weight: bold;">BOTH</span> and a valid file with the same file name already exists, then:
<ul>
<li><strong>ERASE</strong> = accept</li>
<li><strong>DELETE</strong> = accept</li>
<li><strong>VERIFY</strong> = accept if empty, refuse if not empty</li>
</ul></li>
<li><span style="font-weight: bold;">BOTH</span> and a file with the same file name does not already exist, then:
<ul>
<li><strong>ERASE</strong> = accept</li>
<li><strong>DELETE</strong> = accept</li>
<li><strong>VERIFY</strong> = accept</li>
</ul></li>
</ul>
<p>where:</p>
<p>   accept = accept the transferred file</p>
<p>   refuse = refuse the transferred file</p>         </td>
      </tr>
   </tbody>
</table>

<span id="SMTP_POP3"></span>

### New Application: SMTP/POP3 tab

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Field</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Attach/extract file</p>         </td>
         <td><p>Use this field to indicate whether Gateway must create an email and attach the file or not. Gateway checks the Application object first for the <span style="font-weight: bold;">Extract file</span> parameter, and then the Remote Site.</p>
<p><span style="font-weight: bold;">Note:</span> If this value is defined in the Transfer Request, the Transfer Request definition overrides the value that you enter here.</p>
<p>Select one of the following options:</p>
<ul>
<li><span style="font-weight: bold;">Yes</span> indicates that the file is included on transmission as an attachment and extracted on reception.</li>
<li><span style="font-weight: bold;">No</span> indicates a file to transfer that is already formatted as an email. (The MIME header and body are complete and well-formed.)</li>
<li><span style="font-weight: bold;">Undefined</span> - Gateway retrieves the value of the <span style="font-weight: bold;">Extract file</span> field defined in the Remote Site <a href="../../../../managing_partners_start_here/sites_start_here/managing_remote_sites/remote_site_pop3_tab">POP3 tab</a>.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Add Gateway specific parameters to subject</p>         </td>
         <td><p>Use this option to add the following specific Gateway parameters to the email subject:</p>
<ul>
<li>destination (<span class="code" style="font-weight: bold;">-dest</span>)</li>
<li>origin (<span class="code" style="font-weight: bold;">-org</span>)</li>
<li>protocol file name (<span class="code" style="font-weight: bold;">-file_name</span>)</li>
<li>application (<span class="code" style="font-weight: bold;">-appli</span>)</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

<span id="Displaying_a_list_of_Application_objects"></span>

## Displaying all Application objects

To display a list of all Application objects stored in the database:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:  
    **Transfer Management > Parameters**
2.  Click the <span style="font-weight: bold;">Application</span> sub-node.  
    Gateway displays a list of all existing Application objects in the right (display) pane.

<span id="Displaying_a_selected_list_of_application_objects"></span>

## Displaying a list of selected Application objects

You can reduce the number of Application objects listed in the display pane by applying selection criteria to the display.

To display a selected list of Application objects:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:  
    **Transfer Management > Parameters**
2.  Right-click the <span style="font-weight: bold;">Application</span> sub-node, then choose <span style="font-weight: bold;">Select</span>... from the context menu.  
    Gateway displays the <span style="font-style: italic;">Select Applications</span> window.
3.  In the <span style="font-style: italic;">Select Applications</span> window, use the data fields to enter criteria for Application display selection. You can use one or more of the following selection criteria:
    -   Application name
    -   Site
    -   Group
4.  Click <span style="font-weight: bold;">OK</span>.  
    Gateway regenerates the right window Application display, taking into account your selection criteria.

<span id="Viewing_attributes_of_Application_objects"></span>

## Viewing the attributes of an Application object

To view the attributes of a specific Application object:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:  
    **Transfer Management > Parameters**
2.  Click the <span style="font-weight: bold;">Application</span> sub-node.  
    Gateway displays a list of all existing Application objects in the right (display) pane.
3.  In the right pane, right-click the name of the Application object you want to view. Select <span style="font-weight: bold;">View...</span> from the context menu.  
    Gateway displays the<span style="font-style: italic;"> Application (read only)</span> window. This window provides you with a view of all attributes for the selected Application.
4.  When you have finished viewing the information, click <span style="font-weight: bold;">Close</span> to quit the window.

<span id="Modifying_Application_objects"></span>

## Modifying an Application object

To modify the attributes of an existing Application object:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:  
    **Transfer Management > Parameters**
2.  Click the <span style="font-weight: bold;">Application</span> sub-node.  
    Gateway displays a list of all existing Application objects in the right (display) pane.
3.  In the display frame (right frame), right-click the Application object that you want to modify. Then in the context menu click <span style="font-weight: bold;">Modify...</span>  
    Gateway opens the <span style="font-style: italic;">Application</span> editing window.
4.  Modify the value fields of the tabs according to your requirements.
5.  Click <span style="font-weight: bold;">OK</span> to confirm changes and complete the modification procedure.

<span id="Deleting_Application_objects"></span>

## Deleting an Application object

To delete an existing Application object:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:  
    **Transfer Management > Parameters**
2.  Click the <span style="font-weight: bold;">Application</span> sub-node.  
    Gateway displays a list of all existing Application objects in the right (display) pane.
3.  In the right pane, right-click the name of the Application object you want to delete. Select <span style="font-weight: bold;">Delete...</span> from the context menu.  
    Gateway displays a confirmation dialog box.
4.  In the confirmation dialog box, click <span style="font-weight: bold;">Yes</span> to confirm the delete operation.  
    Alternatively, click <span style="font-weight: bold;">No</span> or <span style="font-weight: bold;">Cancel</span> to abandon the operation.  
    Gateway deletes the Application object from the database and removes the entry from the display window.

Related topics

[About Applications](../)

[Working with Applications (command line)](../working_with_applications_cli)

[Application Objects: Parameters List](../working_with_applications_cli/application_object_parameter_list)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
