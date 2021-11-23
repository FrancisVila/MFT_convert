{
    "title": "Configuring protocols: TCP advanced options",
    "linkTitle": "TCP advanced options",
    "weight": "210"
}{{< Gateway/componentlongname  >}}: Configuration

Gateway opens the *TCP advanced options* window if you click the **Advanced...** button when configuring any protocol that uses TCP/IP.

1.  Modify the TCP parameters as follows:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Parameter</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Maximum number of connections in initiator mode</p>         </td>
         <td><p>Maximum number of simultaneous initiated connections allowed for the selected protocol.</p>
<p><span style="font-weight: bold;">1 - 999</span>. Default: <span style="font-weight: bold;">100</span>.</p>         </td>
      </tr>
      <tr>
         <td><p>Maximum number of connections in responder mode</p>         </td>
         <td><p>Maximum number of simultaneous responded connections allowed for the selected protocol.</p>
<p><span style="font-weight: bold;">1 - 999</span>. Default: <span style="font-weight: bold;">100</span>.</p>         </td>
      </tr>
      <tr>
         <td><p>Use SSL/TLS</p>         </td>
         <td><p><span style="font-style: italic;">Not for SFTP</span></p>
<p>Select this option to secure TCP/IP connections with SSL/TLS protocols.</p>         </td>
      </tr>
      <tr>
         <td><p>Dynamic client processes<span style="font-weight: normal;"> (outgoing connections)</span></p>         </td>
      </tr>
      <tr>
         <td><p>Active</p>         </td>
         <td><p>Select this option if you require a pool of dynamic processes for outgoing (client) connections.</p>         </td>
      </tr>
      <tr>
         <td><p>No. processes min</p>         </td>
         <td><p>Minimum number of processes to maintain in the pool.</p>         </td>
      </tr>
      <tr>
         <td><p>No. processes max</p>         </td>
         <td><p>Maximum number of processes allowed in the pool.</p>         </td>
      </tr>
      <tr>
         <td><p>Balance ratio</p>         </td>
         <td><p>You can distribute outgoing connections between different processes.</p>
<p>If you set the value to 0, all incoming connections are directed to the first process until it is full. Subsequent processes are then directed to the second process and so on.</p>
<p>Percentage: 0 - 100.</p>         </td>
      </tr>
      <tr>
         <td><p>Dynamic server processes<span style="font-weight: normal;"> (incoming connections)</span></p>
<p>not for all protocols</p>         </td>
      </tr>
      <tr>
         <td><p>Active</p>         </td>
         <td><p>Select this option if you require a pool of dynamic processes for incoming (server) connections.</p>         </td>
      </tr>
      <tr>
         <td><p>No. processes min</p>         </td>
         <td><p>Minimum number of processes to maintain in the pool.</p>         </td>
      </tr>
      <tr>
         <td><p>No. processes max</p>         </td>
         <td><p>Maximum number of processes allowed in the pool.</p>         </td>
      </tr>
      <tr>
         <td><p>Balance ratio</p>         </td>
         <td><p>You can distribute incoming connections between different processes.</p>
<p>If you set the value to 0, all incoming connections are directed to the first process until it is full. Subsequent processes are then directed to the second process and so on.</p>
<p>Percentage: 0 - 100.</p>         </td>
      </tr>
   </tbody>
</table>

1.  Click <span style="font-weight: bold;">OK</span> to confirm the <span style="font-style: italic;">TCP advanced options.</span>

Related topics

[Configuring protocols](../config_protocols)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
