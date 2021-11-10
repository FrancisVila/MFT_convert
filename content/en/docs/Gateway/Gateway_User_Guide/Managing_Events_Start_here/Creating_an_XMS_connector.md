{
    "title": "Creating an Axway Messaging connector ",
    "linkTitle": "Creating an XMS connector",
    "weight": "150"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Events

[About Axway Messaging connectors](#About)

[Creating an Axway Messaging IN connector](#Defining_IN_connector)

[Creating an Axway Messaging OUT connector](#Defining_OUT_connector)

<span id="About"></span>

## About Axway Messaging connectors

Before you create an XMS-type Decision Rule or XMS-type Rule Table, you need to create an Axway Messaging connector in the GUI. You can create either an <span style="font-style: italic;">IN connector</span> or an <span style="font-style: italic;">OUT connector</span>, as described in the sections below.

After you create a connector, it is visible as a node in the left pane Directory tree structure of the Gateway main window, under the <span style="font-weight: bold;">Event Management</span> node. The connector is listed under either the <span style="font-weight: bold;">XMS Connector In</span> or <span style="font-weight: bold;">XMS Connector Out</span> sub-node.

<span id="Defining_IN_connector"></span>

## Creating an Axway Messaging IN connector

To create a new Axway Messaging IN connector:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Event Management</span> node.  
    Gateway expands the node to display the following sub-nodes:
    -   Scheduling
    -   Directory Scanning
    -   Transfer Change State
    -   XMS

    Each sub-node represents a [Decision Rule / Rule Table category](../#Types_of_triggering_events).
2.  Click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">XMS</span> sub-node.
3.  Right-click <span style="font-weight: bold;">Connector</span><span style="font-weight: bold;">In</span>, then select <span style="font-weight: bold;">New</span> from the context menu.  
    Gateway displays the <span style="font-style: italic;">XMS Connector In</span> window.
4.  Complete the fields of the <span style="font-style: italic;">XMS Connector In</span> window using the information in the following table.
5.  Click <span style="font-weight: bold;">OK</span> to confirm the data you have entered.  
    Gateway:
    -   closes the <span style="font-style: italic;">XMS Connector In</span> window
    -   creates the connector
    -   displays a new entry in the Directory tree structure with the assigned connector name
    -   displays a new line entry in the <span style="font-style: italic;">Connector In</span> list in the main window

### XMS Connector In window

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Element</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">Name</span></p>         </td>
         <td><p>Enter a unique name for the connector.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Type</span></p>         </td>
         <td><p>You cannot modify this field.</p>
<p>This field displays the value <span style="font-style: italic;">In,</span> indicating that you are creating an IN type connector.</p>         </td>
      </tr>
      <tr>
         <td><p>Active</p>         </td>
         <td><p>Click the check box to activate or deactivate the connector.</p>         </td>
      </tr>
      <tr>
         <td><p>XMS (Axway Messaging) server</p>         </td>
      </tr>
      <tr>
         <td><p>Name</p>         </td>
         <td><p>Enter the name of the Axway Messaging server to which you are connecting.</p>         </td>
      </tr>
      <tr>
         <td><p>Port</p>         </td>
         <td><p>Enter the Axway Messaging server access port number.</p>         </td>
      </tr>
      <tr>
         <td><p>Login</p>         </td>
      </tr>
      <tr>
         <td><p>Identifier</p>         </td>
         <td><p>Enter the login identifier that Gateway uses to log in to the Axway Messaging server.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Set password</span></p>         </td>
         <td><p>This button opens a dialog box to enter the password that you want to associate with the Identifier.</p>         </td>
      </tr>
      <tr>
         <td><p>Messages</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Select one of the values:</p>
<ul>
<li><span style="font-weight: bold;">XMS message</span> = the connector handles Axway Messaging messages</li>
<li><span style="font-weight: bold;">XMS notif error</span> = the connector handles Axway Messaging error and acknowledgment messages</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Standard size</p>         </td>
         <td><p>Enter the maximum message size to be handled.</p>         </td>
      </tr>
      <tr>
         <td><p>Queue name</p>         </td>
         <td><p>Enter the name of the Axway Messaging queue in which the Gateway reads messages.</p>         </td>
      </tr>
      <tr>
         <td><p>Reception directory</p>         </td>
         <td><p>Enter the directory in which Gateway stores Axway Messaging data content before redirecting it.</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>Log level</p>         </td>
         <td><p>Select one of the Axway Messaging logging level values:</p>
<ul>
<li><span style="font-weight: bold;">No log</span> = logging deactivated</li>
<li><span style="font-weight: bold;">Short</span> = short logs</li>
<li><span style="font-weight: bold;">Full</span> = detailed logs</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Backup message</p>         </td>
         <td><p>Select this option if you want to save a copy of messages that were filtered and not handled by Decision Rules and Rule Tables. Messages are saved to the Axway Messaging file <span class="code">XMSReceptionQueue bck</span>.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Defining_OUT_connector"></span>

## Creating an Axway Messaging OUT connector

To create a new Axway Messaging OUT connector:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Event Management</span> node.  
    Gateway expands the node to display the following sub-nodes:
    -   Scheduling
    -   Directory Scanning
    -   Transfer Change State
    -   XMS

    Each sub-node represents a [Decision Rule / Rule Table category](../#Types_of_triggering_events).
2.  Click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">XMS</span> sub-node.
3.  Right-click <span style="font-weight: bold;">Connector</span><span style="font-weight: bold;">Out</span>, then select <span style="font-weight: bold;">New</span> from the context menu.  
    Gateway displays the <span style="font-style: italic;">XMS Connector Out</span> window.
4.  Complete the fields of the <span style="font-style: italic;">XMS Connector Out</span> window using the information in the following table.
5.  Click <span style="font-weight: bold;">OK</span> to confirm the data you have entered.
    Gateway:
    -   closes the <span style="font-style: italic;">XMS Connector Out</span> window
    -   creates the connector
    -   displays a new entry in the Directory tree structure with the assigned connector name
    -   displays a new line entry in the <span style="font-style: italic;">Connector Out</span> list in the main window

### XMS Connector Out window

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Element</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">Name</span></p>         </td>
         <td><p>Enter a unique name for the connector.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Type</span></p>         </td>
         <td><p>You cannot modify this field.</p>
<p>This field displays the value <span style="font-style: italic;">Out,</span> indicating that you are creating an OUT type connector.</p>         </td>
      </tr>
      <tr>
         <td><p>Active</p>         </td>
         <td><p>Click the check box to activate or deactivate the connector.</p>         </td>
      </tr>
      <tr>
         <td><p>XMS (Axway Messaging) server</p>         </td>
      </tr>
      <tr>
         <td><p>Name</p>         </td>
         <td><p>Enter the name of the Axway Messaging server to which you are connecting.</p>         </td>
      </tr>
      <tr>
         <td><p>Port</p>         </td>
         <td><p>Enter the Axway Messaging server access port number.</p>         </td>
      </tr>
      <tr>
         <td><p>Login</p>         </td>
      </tr>
      <tr>
         <td><p>Identifier</p>         </td>
         <td><p>Enter the login identifier that Gateway uses to log in to the Axway Messaging server.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Set password</span></p>         </td>
         <td><p>This button opens a dialog box to enter the password that you want to associate with the Identifier.</p>         </td>
      </tr>
      <tr>
         <td><p>Messages</p>         </td>
      </tr>
      <tr>
         <td><p>Compression</p>         </td>
         <td><p>Select this option if you want incoming files transferred to Axway Messaging to be compressed.</p>
<p>If you do not want to use the message compression function, leave this box unselected.</p>         </td>
      </tr>
      <tr>
         <td><p>Persistent</p>         </td>
         <td><p>Select this option if you want the Axway Messaging server to operate in persistent mode.</p>
<p><span style="font-weight: bold;">Persistent mode</span>:</p>
<p>Until the receiving application consumes the message, the receiving server stores a copy of the message in the Axway Messaging Log. If the connection between the receiving application and the receiving server fails, the receiving server does not lose the message.</p>
<p><span style="font-weight: bold;">Non-persistent mode</span>:</p>
<p>The receiving server <span style="font-style: italic;">does not</span> store a copy of the message in the Axway Messaging Log. If the connection between the receiving application and the receiving server fails, the receiving server loses the message.</p>         </td>
      </tr>
      <tr>
         <td><p>Priority</p>         </td>
         <td><p>Select one of the following values to indicate the priority an application uses for getting messages from a source:</p>
<ul>
<li><span style="font-weight: bold;">High</span></li>
<li><span style="font-weight: bold;">Normal</span></li>
<li><span style="font-weight: bold;">Low</span></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>Log level</p>         </td>
         <td><p>Select one of the Axway Messaging logging level values:</p>
<ul>
<li><span style="font-weight: bold;">No log</span> = logging deactivated</li>
<li><span style="font-weight: bold;">Short</span> = short logs</li>
<li><span style="font-weight: bold;">Full</span> = detailed logs</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
