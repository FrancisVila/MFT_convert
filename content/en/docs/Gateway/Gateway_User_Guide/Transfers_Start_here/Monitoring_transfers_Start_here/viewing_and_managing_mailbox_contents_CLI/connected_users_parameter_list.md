{
    "title": "Connected Users: Parameters List",
    "linkTitle": "Connected Users: Parameters List",
    "weight": "280"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Transfers

## Connected Users: command parameters

The following table lists all Connected User object <span style="font-weight: bold;">command parameters</span> in alphabetical order. The corresponding field name in the Gateway GUI is shown in <span style="font-weight: bold;font-style: italic;">italics</span>.

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><span style="font-weight: bold;">Parameter</span>         </th>
<th class="HeadE-Column1-Header1"><p>Meaning</p>         </th>
<th class="HeadD-Column1-Header1"><p>Possible values</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>-connected_after (-ca)</p>
<p>First connection time/ Start</p>         </td>
         <td><p>Date and time <span style="font-style: italic;">after</span> which the Connection started.</p>         </td>
         <td><p>Format: <span style="font-style: italic;">YYMMDD HHMMSS</span></p>         </td>
      </tr>
      <tr>
         <td><p>-connected_before (-cb)</p>
<p>First connection time/ End</p>         </td>
         <td><p>Date and time <span style="font-style: italic;">before</span> which the Connection started.</p>         </td>
         <td><p>Format: <span style="font-style: italic;">YYMMDD HHMMSS</span></p>         </td>
      </tr>
      <tr>
         <td><p>-connected_user_id (-cui)</p>
<p>Connected user</p>         </td>
         <td><p>Connected User identifier.</p>         </td>
         <td><p>Integer that exclusively identifies the Connected User.</p>
<p>Max 31 alphanumeric characters.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="return_paras"></span>

## Connected Users: Return parameters

The following table lists all Connected User object <span style="font-weight: bold;">returned values</span> in alphabetical order. The corresponding field name in the Gateway GUI is shown in <span style="font-weight: bold;font-style: italic;">italics</span>.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><span style="font-weight: bold;">Parameter</span>         </th>
<th class="HeadD-Column1-Header1"><p>Meaning</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>active_connections</p>
<p>Connections count</p>         </td>
         <td><p>Number of currently active (transferring data) Connections.</p>         </td>
      </tr>
      <tr>
         <td><p>average_speed</p>
<p>Speed</p>         </td>
         <td><p>Average transfer speed for this Connected User.</p>
<p>Only significant transfers (more than one second) are taken into account.</p>         </td>
      </tr>
      <tr>
         <td><p>command_credit_used</p>
<p>Command credit used</p>         </td>
         <td><p>FTP (defense against hammer attacks).</p>
<p>Percentage of command credit used.</p>         </td>
      </tr>
      <tr>
         <td><p>conn_max</p>
<p>Max connections</p>         </td>
         <td><p>Maximum number of Connections allowed for this Connected User.</p>         </td>
      </tr>
      <tr>
         <td><p>connected_user_id</p>
<p>Connected user name</p>         </td>
         <td><p>Connected User responsible for the Connection.</p>         </td>
      </tr>
      <tr>
         <td><p>download_requests_used</p>
<p>Download requests used</p>         </td>
         <td><p>FTP (defense against hammer attacks).</p>
<p>Number of download requests used within the user quota.</p>         </td>
      </tr>
      <tr>
         <td><p>download_size_used</p>
<p>Download size used</p>         </td>
         <td><p>FTP (defense against hammer attacks).</p>
<p>Percentage of upload data size used within the user quota.</p>         </td>
      </tr>
      <tr>
         <td><p>downloads_count</p>
<p>Downloads count</p>         </td>
         <td><p>Number of downloaded files for this Connected User.</p>         </td>
      </tr>
      <tr>
         <td><p>errors_count</p>
<p>Errors count</p>         </td>
         <td><p>Number of transfer errors for this Connected User.</p>         </td>
      </tr>
      <tr>
         <td><p>last_connection_date</p>
<p>Last connection date</p>         </td>
         <td><p>Date and time the last Connection started.</p>
<p>Format: <span style="font-style: italic;">YYMMDD HHMMSS</span></p>         </td>
      </tr>
      <tr>
         <td><p>last_remote_address</p>
<p>Last remote address</p>         </td>
         <td><p>Outgoing network address of the last Connection.</p>         </td>
      </tr>
      <tr>
         <td><p>upload_requests_used</p>
<p>Upload requests used</p>         </td>
         <td><p>FTP (defense against hammer attacks).</p>
<p>Number of upload requests used within the user quota.</p>         </td>
      </tr>
      <tr>
         <td><p>upload_size_used</p>
<p>Upload size used</p>         </td>
         <td><p>FTP (defense against hammer attacks).</p>
<p>Percentage of upload data size used within the user quota.</p>         </td>
      </tr>
      <tr>
         <td><p>uploads_count</p>
<p>Uploads count</p>         </td>
         <td><p>Number of uploaded files for this Connected User.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-family: monospace;font-weight: normal;">x_bytes</span></p>
<p>Data count</p>         </td>
         <td><p>Cumulated transferred data volume for this Connected User.</p>         </td>
      </tr>
   </tbody>
</table>

 

Related topics

[Monitoring Connected Users (command line)](../monitoring_connected_users_cli)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
