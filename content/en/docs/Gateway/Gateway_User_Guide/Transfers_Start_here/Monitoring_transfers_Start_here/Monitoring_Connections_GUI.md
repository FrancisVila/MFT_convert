{
    "title": "Monitoring Connections",
    "linkTitle": "Monitoring Connections",
    "weight": "170"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Transfers

[Viewing all Connections](#viewing)

[Filtering displayed Connections](#filtering)

[Refreshing the Connections display](#refreshing)

<span id="viewing"></span>

## Viewing all Connections

To view information about the currently open connections on Gateway:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:

Transfer Management &gt; Monitoring

1.  Click the <span style="font-weight: bold;">Connection</span> node.

Gateway displays all currently open Connections in a table in the display pane. The table columns contain the following information for each Connection.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Column</p>         </th>
<th class="HeadD-Column1-Header1"><p>Contents</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>ID</p>         </td>
         <td><p>Connection identifier.</p>         </td>
      </tr>
      <tr>
         <td><p>State</p>         </td>
         <td><p>Status of the connections:</p>
<ul>
<li><span style="font-weight: bold;">T</span> = Transferring</li>
<li><span style="font-weight: bold;">S</span> = Still</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Connected user</p>         </td>
         <td><p>The Connected User responsible for the Connection.</p>         </td>
      </tr>
      <tr>
         <td><p>Speed</p>         </td>
         <td><p>Average transfer speed for this Connection. Only significant transfers (more than one second) are taken into account.</p>         </td>
      </tr>
      <tr>
         <td><p>Data</p>         </td>
         <td><p>Cumulated transferred data volume for this Connection.</p>         </td>
      </tr>
      <tr>
         <td><p>Downloads</p>         </td>
         <td><p>Number of files downloaded during this Connection.</p>         </td>
      </tr>
      <tr>
         <td><p>Uploads</p>         </td>
         <td><p>Number of files uploaded during this Connection.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="filtering"></span>

## Filtering displayed Connections

To reduce the number of Connections presented in the display pane, or to obtain for a particular display result, you can apply filtering criteria to the display of Connections:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:

Transfer Management &gt; Monitoring

1.  Right-click the <span style="font-weight: bold;">Connection</span> node.

Gateway displays the <span style="font-style: italic;">Connection</span> context menu.

1.  In the context menu, click <span style="font-weight: bold;">Select...</span>

Gateway displays the <span style="font-style: italic;">Select Connections</span> dialog box.

Use one or more of the fields in the <span style="font-style: italic;">Select Connections</span> dialog box to create selection criteria for the display of Connections:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Field</p>         </th>
<th class="HeadD-Column1-Header1"><p>Use</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Connection ID</p>         </td>
         <td><p>Enter a connection ID number to select a specific Connection for display</p>         </td>
      </tr>
      <tr>
         <td><p>Connection time</p>         </td>
      </tr>
      <tr>
         <td><p>Start</p>         </td>
         <td><p>You can select either starting time or starting date criteria, or combine the two.</p>
<p>You can combine starting time and/or starting date criteria with ending time and/or ending date criteria.</p>
<p>To <span style="font-weight: bold;">set a starting date</span> as selection criteria:</p>
<ol>
<li>Click the down arrow on the starting date field displaying the current date.</li>
</ol>
<p>Gateway displays the calendar selection tool.</p>
<ol start="2">
<li>Use the calendar selection tool to navigate to the start month and start date of your choice.</li>
</ol>
<p>To <span style="font-weight: bold;">set a starting time</span> as selection criteria:</p>
<ol>
<li>Click the check box next to the starting time selection field.</li>
</ol>
<p>Gateway converts the time display from grayed out to normal text to indicate that it is activated.</p>
<ol start="2">
<li>Click to select the time unit you want to modify: hour, minute or second.</li>
</ol>
<p>Gateway highlights the time unit.</p>
<ol start="3">
<li>Type a valid number or use the up and down arrows to set the time unit.</li>
<li>Select and set the other time units (hour, minute, second) as required.</li>
</ol>         </td>
      </tr>
      <tr>
         <td><p>End</p>         </td>
         <td><p>You can set either ending time or ending date criteria, or combine the two.</p>
<p>You can combine ending time and/or ending date criteria with starting time and/or starting date criteria.</p>
<p>To <span style="font-weight: bold;">set an ending date</span> as selection criteria:</p>
<ol>
<li>Click the down arrow on the ending date field displaying the current date.</li>
</ol>
<p>Gateway displays the calendar selection tool.</p>
<ol start="2">
<li>Use the calendar selection tool to navigate to the end month and end date of your choice.</li>
</ol>
<p>To <span style="font-weight: bold;">set an ending time</span> as selection criteria:</p>
<ol>
<li>Click the check box next to the ending time selection field.</li>
</ol>
<p>Gateway converts the time display from grayed out to normal text to indicate that it is activated.</p>
<ol start="2">
<li>Click to select the time unit you want to modify: hour, minute or second.</li>
</ol>
<p>Gateway highlights the time unit.</p>
<ol start="3">
<li>Type a valid number or use the up and down arrows to set the time unit.</li>
<li>Select and set the other time units (hour, minute, second) as required.</li>
</ol>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>State</p>         </td>
         <td><p>To select a Connection state as display selection criteria:</p>
Click the down arrow located in the <span style="font-weight: bold;">State</span> field.
Select the state to use as display selection criteria:
<ul>
<li>Inactive</li>
<li>Transferring</li>
<li>Both</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Mode</p>         </td>
         <td><p>To select a Site mode as display selection criteria:</p>
Click the down arrow located in the <span style="font-weight: bold;">Mode</span> field.
Select the Site mode you want to use as display selection criteria:
<ul>
<li>Initiator</li>
<li>Responder</li>
<li>Both</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

1.  Click <span style="font-weight: bold;">OK</span>.

Gateway applies your criteria and regenerates the display results.

<span id="refreshing"></span>

## Refreshing the Connections display

To refresh the display of Connections to take into account the most recent network events, do one of the following:

-   In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes <span style="font-weight: bold;">Transfer Management > Monitoring</span>. Then right-click <span style="font-weight: bold;">Connection</span>. In the displayed context menu, select <span style="font-weight: bold;">Refresh</span>.
-   Press <span style="font-weight: bold;">F5</span>.

Related topics

[Monitoring Connections (command line)](../viewing_and_managing_mailbox_contents_cli/monitoring_connections_cli)

[Monitoring Transfers](../)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
