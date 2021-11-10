{
    "title": "New Remote Site: Options tab",
    "linkTitle": "Options tab",
    "weight": "200"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Partners

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Maximum data block size (in bytes)</p>         </td>
         <td><p>Specify the maximum data block size in bytes.<br />
Integer: 128 - 32768. Default = 4000.</p>         </td>
      </tr>
      <tr>
         <td><p>Maximum number of simultaneous connections to this Site</p>         </td>
         <td><p>Specify the maximum number of connections to this Site.<br />
Integer: 0 - 999. Default = 1.</p>
<p>For POP3 Sites, this value is always set to 1.</p>         </td>
      </tr>
      <tr>
         <td><p>Maximum number of simultaneous connections from this Site</p>         </td>
         <td><p>Specify the maximum number of connections from this Site.<br />
Integer: 0 - 999. Default = 1.</p>
<p>For POP3 Sites, this value is always set to 0.</p>         </td>
      </tr>
      <tr>
         <td><p>Maximum number of connection retries before time limit</p>         </td>
         <td><p>Specify the maximum number of times the software tries to connect before stopping the Site.<br />
Integer: 0 - 999. Default = 10.</p>         </td>
      </tr>
      <tr>
         <td><p>Time before first retry (in seconds)</p>         </td>
         <td><p>Specify the minimum delay before the first connection retry.<br />
Integer: 1 - 9999. Default = 10.</p>
<p>Each subsequent retry doubles the time that you enter here. For example, if you enter 10 seconds, the first retry occurs after 10 seconds, the second after 20 seconds, the third after 40 seconds, and so on until either:</p>
<ul>
<li>The maximum interval between retries is reached; <strong>or</strong></li>
<li>The maximum number of connection retries is reached</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Maximum interval between retries (in seconds)</p>         </td>
         <td><p>Specify the maximum interval between connection retries. The value that you enter here must be greater than or equal to the value entered in the <span style="font-weight: bold;">Time before first retry</span> field.<br />
Integer: 1 - 9999. Default = 1800.</p>
<p>For example, if you enter 30 in this field, 10 in the <span style="font-weight: bold;">Time before first retry</span> field and 10 in the <span style="font-weight: bold;">Maximum number of connection retries</span> field, then the first retry occurs after 10 seconds, the second after 20 seconds and the third after 30 seconds since this is the maximum interval allowed. Each subsequent retry occurs after 30 seconds until the maximum number of retries is reached, in this case 10.</p>         </td>
      </tr>
      <tr>
         <td><p>Sentinel:<br />
Transfer Filter</p>         </td>
         <td><p>Use this option to send a record of Transfer state changes to Sentinel. Select one of the following:</p>
<ul>
<li><span style="font-weight: bold;">All</span> = sends all Transfer state changes to Sentinel</li>
<li><span style="font-weight: bold;">Summary</span> = sends a summary of Transfer state changes. Summary Transfer states are: canceled, ended, acked, created, to begin</li>
<li><span style="font-weight: bold;">None</span> = sends no Transfer state changes</li>
<li><span style="font-weight: bold;">Undefined</span> = Gateway uses the value set in the configuration menu</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Working with Remote Sites](../)

[Site objects: Parameters List](../../managing_local_sites_cli/sites_parameter_list)

[About Axway Sentinel](../../../../connectors_about/sentinel_about)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
