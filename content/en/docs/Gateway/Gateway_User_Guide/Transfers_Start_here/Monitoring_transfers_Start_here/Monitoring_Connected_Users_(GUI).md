{
    "title": "Monitoring Connected Users",
    "linkTitle": "Monitoring Connected Users",
    "weight": "180"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Transfers

[Viewing all Connected Users](#viewing)

[Filtering displayed Connected Users](#filtering)

[Refreshing the Connected Users display](#refreshing)

<span id="viewing"></span>

## Viewing all Connected Users

To view information about the user entities that are currently using connections on the Gateway:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:

Transfer Management &gt; Monitoring

1.  Click the <span style="font-weight: bold;">Connected User</span> node.

Gateway displays all Connected Users in a table in the display pane. The table columns contain the following information for each Connected User.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Column</p>         </th>
<th class="HeadD-Column1-Header1"><p>Contents</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Connected user name</p>         </td>
         <td><p>Identity of the Connected User.</p>         </td>
      </tr>
      <tr>
         <td><p>Upload size used</p>         </td>
         <td><p>Percentage of upload data size used within the user quota.</p>
<p>This parameter is related to FTP defense against hammer attacks.</p>         </td>
      </tr>
      <tr>
         <td><p>Download size used</p>         </td>
         <td><p>Percentage of download data size used within the user quota.</p>
<p>This parameter is related to FTP defense against hammer attacks.</p>         </td>
      </tr>
      <tr>
         <td><p>Upload requests used</p>         </td>
         <td><p>Number of upload requests used within the user quota.</p>
<p>This parameter is related to FTP defense against hammer attacks.</p>         </td>
      </tr>
      <tr>
         <td><p>Download requests used</p>         </td>
         <td><p>Number of download requests used within the user quota.</p>
<p>This parameter is related to FTP defense against hammer attacks.</p>         </td>
      </tr>
      <tr>
         <td><p>Command credits used</p>         </td>
         <td><p>Percentage of command credit used.</p>
<p>This parameter is related to FTP defense against hammer attacks.</p>         </td>
      </tr>
      <tr>
         <td><p>Connections count</p>         </td>
         <td><p>Number of currently active (transferring data) Connections.</p>         </td>
      </tr>
      <tr>
         <td><p>Max connections</p>         </td>
         <td><p>Maximum number of Connections allowed for this Connected User.</p>         </td>
      </tr>
      <tr>
         <td><p>Data count</p>         </td>
         <td><p>Cumulated transferred data volume for this Connected User.</p>         </td>
      </tr>
      <tr>
         <td><p>Uploads count</p>         </td>
         <td><p>Number of uploaded files for this Connected User.</p>         </td>
      </tr>
      <tr>
         <td><p>Downloads count</p>         </td>
         <td><p>Number of downloaded files for this Connected User.</p>         </td>
      </tr>
      <tr>
         <td><p>Last remote address</p>         </td>
         <td><p>Outgoing network address of the last Connection.</p>         </td>
      </tr>
      <tr>
         <td><p>Speed</p>         </td>
         <td><p>Average transfer speed for this Connected User. Only takes into account significant transfers (more than one second).</p>         </td>
      </tr>
      <tr>
         <td><p>Errors count</p>         </td>
         <td><p>Number of transfer errors for this Connected User.</p>         </td>
      </tr>
      <tr>
         <td><p>Last connection date</p>         </td>
         <td><p>Date and time the last Connection started.</p>
<p>Format <span style="font-style: italic;">YYMMDD HHMMSS</span></p>         </td>
      </tr>
   </tbody>
</table>

<span id="filtering"></span>

## Filtering displayed Connected Users

To reduce the number of Connected Users listed in the display pane, or to obtain for a particular display result, you can apply filtering criteria to the display of Connected Users.

To select filter criteria for the display of Connected Users:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:

Transfer Management &gt; Monitoring

1.  Right-click the <span style="font-weight: bold;">Connected User</span> node.

Gateway displays the <span style="font-style: italic;">Connected User</span> context menu

1.  In the context menu, click <span style="font-weight: bold;">Select...</span>

Gateway displays the <span style="font-style: italic;">Select Connected Users</span> dialog box.

Use the fields of the <span style="font-style: italic;">Select Connected Users</span> dialog box to create selection criteria for the display of Connections. You can use one or more of the fields described in the following table.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Field</p>         </th>
<th class="HeadD-Column1-Header1"><p>Use</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Connected user</p>         </td>
         <td><p>Enter the identification number of the Connected User to display.</p>         </td>
      </tr>
      <tr>
         <td><p>First connection time</p>         </td>
      </tr>
      <tr>
         <td><p>Start</p>         </td>
         <td><p>You can set either starting time or starting date criteria to filter results. You can also combine the starting date and starting time as criteria.</p>
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
<li>Click the check  box next to the ending time selection field.</li>
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
   </tbody>
</table>

1.  When you have set the criteria that you want to use to filter the display results, click <span style="font-weight: bold;">OK</span>.

Gateway applies your criteria to regenerate the display results.

<span id="refreshing"></span>

## Refreshing the Connected Users display

To refresh the display of Connected Users to take into account the most recent network events, do one of the following:

-   In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes <span style="font-weight: bold;">Transfer Management > Monitoring</span>. Then right-click <span style="font-weight: bold;">Connected Users</span>. In the displayed context menu, select <span style="font-weight: bold;">Refresh</span>.
-   In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes <span style="font-weight: bold;">Transfer Management > Monitoring</span>. Click <span style="font-weight: bold;">Connected Users</span>. Then press <span style="font-weight: bold;">F5</span>.

Related topics

[Monitoring Connected Users (command line)](../viewing_and_managing_mailbox_contents_cli/monitoring_connected_users_cli)

[Monitoring Transfers](../)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
