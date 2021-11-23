{
    "title": "Connections: Parameters List",
    "linkTitle": "Connections: Parameters List",
    "weight": "270"
}{{< Gateway/componentlongname  >}}: Managing Transfers

## Connections: Command parameters

The following table lists all Connection object **command parameters** in alphabetical order. The corresponding field name in the Gateway GUI is shown in <span style="font-weight: bold;font-style: italic;">italics</span>.

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
<p>Connection time/ Start</p>         </td>
         <td><p>Date and time <span style="font-style: italic;">after</span> which the Connection started.</p>         </td>
         <td><p>Format: <span style="font-style: italic;">YYMMDD HHMMSS</span></p>         </td>
      </tr>
      <tr>
         <td><p>-connected_before (-cb)</p>
<p>Connection time/ End</p>         </td>
         <td><p>Date and time <span style="font-style: italic;">before</span> which the Connection started.</p>         </td>
         <td><p>Format: <span style="font-style: italic;">YYMMDD HHMMSS</span></p>         </td>
      </tr>
      <tr>
         <td><p>-connection_id (-ci)</p>
<p>Connection ID</p>         </td>
         <td><p>Connection identifier.</p>         </td>
         <td><p>Integer that exclusively identifies the Connection.</p>         </td>
      </tr>
      <tr>
         <td><p>-mode (-m)</p>
<p>Mode</p>         </td>
         <td><p>Connection mode of Gateway for the current Connection.</p>         </td>
         <td><ul>
<li><span style="font-weight: bold;">I</span> = Initiator</li>
<li><span style="font-weight: bold;">R</span> = Responder</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-state (-s)</p>
<p>State</p>         </td>
         <td><p>Connection state.</p>         </td>
         <td><ul>
<li><span style="font-weight: bold;">T</span> = Transferring</li>
<li><span style="font-weight: bold;">S</span> = Still</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

<span id="return_paras"></span>

## Connections: Return parameters

The following table lists all Connection object <span style="font-weight: bold;">returned values</span> in alphabetical order. The corresponding field name in the Gateway GUI is shown in <span style="font-weight: bold;font-style: italic;">italics</span>.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p><span style="font-weight: bold;">Parameter</span></p>         </th>
<th class="HeadD-Column1-Header1"><p>Meaning</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>average_speed</p>
<p>Speed</p>         </td>
         <td><p>Average transfer speed for this Connection.</p>
<p>Only significant transfers (more than one second) are taken into account.</p>         </td>
      </tr>
      <tr>
         <td><p>connected_user</p>
<p>Connected user</p>         </td>
         <td><p>Connected User responsible for the Connection.</p>         </td>
      </tr>
      <tr>
         <td><p>connection_id</p>
<p>ID</p>         </td>
         <td><p>Connection identifier.</p>         </td>
      </tr>
      <tr>
         <td><p>connection_state</p>
<p>State</p>         </td>
         <td><p>Connection state:</p>
<ul>
<li><span style="font-weight: bold;">T</span> = Transferring</li>
<li><span style="font-weight: bold;">S</span> = Still</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>current_transfer_ident</p>         </td>
         <td><p>If any, the identifier of an active transfer using this Connection.</p>         </td>
      </tr>
      <tr>
         <td><p>date_connected</p>         </td>
         <td><p>Date and time the Connection started.</p>
<p>Format: <span style="font-style: italic;">YYMMDD HHMMSS</span></p>         </td>
      </tr>
      <tr>
         <td><p>downloads_count</p>
<p>Downloads</p>         </td>
         <td><p>Number of downloaded files during this Connection.</p>         </td>
      </tr>
      <tr>
         <td><p>errors_count</p>         </td>
         <td><p>Number of transfer errors during this Connection.</p>         </td>
      </tr>
      <tr>
         <td><p>mode</p>         </td>
         <td><p>Connection mode of Gateway for the current Connection:</p>
<ul>
<li><span style="font-weight: bold;">I</span> = Initiator</li>
<li><span style="font-weight: bold;">R</span> = Responder</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>protocol</p>         </td>
         <td><p>Protocol name.</p>         </td>
      </tr>
      <tr>
         <td><p>remote_address</p>         </td>
         <td><p>Outgoing Connection network address.</p>         </td>
      </tr>
      <tr>
         <td><p>transfer_date</p>         </td>
         <td><p>Date and time the transfer started.</p>
<p>Format: <span style="font-style: italic;">YYMMDD HHMMSS</span></p>         </td>
      </tr>
      <tr>
         <td><p>uploads_count</p>
<p>Uploads</p>         </td>
         <td><p>Number of uploaded files during this Connection.</p>         </td>
      </tr>
      <tr>
         <td><p>x_bytes</p>
<p>Data</p>         </td>
         <td><p>Cumulated transferred data volume for this Connection.</p>         </td>
      </tr>
   </tbody>
</table>

 

Related topics

[Monitoring Connections (command line)](../monitoring_connections_cli)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
