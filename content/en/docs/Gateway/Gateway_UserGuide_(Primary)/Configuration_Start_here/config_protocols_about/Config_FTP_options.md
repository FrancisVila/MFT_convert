{
    "title": "Configuring FTP options",
    "linkTitle": "FTP options",
    "weight": "180"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Configuration

For FTP and EDIINT AS3 protocols

This topic lists the FTP parameters that you can modify in the <span style="font-style: italic;">FTP options</span> window. Gateway opens this window if you click the <span style="font-weight: bold;">Options...</span> button when configuring the FTP or EDIINT AS3 protocol.

1.  Complete the fields of the <span style="font-style: italic;">FTP options</span> window as follows:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Parameter</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Quota window size</p>         </td>
         <td><p>FTP / SFTP only</p>
<p>Enter the time (in minutes) for which the sliding quota window is active.</p>
<p>Default: <span style="font-weight: bold;">0</span> (all defenses are disabled, irrespective of the quota values defined).</p>         </td>
      </tr>
      <tr>
         <td><p>First failed connection interval</p>         </td>
         <td><p>Enter the time (in seconds) between the first failed connection attempt and the second. The time that you enter in this field is doubled for each subsequent connection attempt.</p>
<p>Minimum: <span style="font-weight: bold;">0</span>. Default: <span style="font-weight: bold;">2</span>.</p>         </td>
      </tr>
      <tr>
         <td><p>Maximum login attempts</p>         </td>
         <td><p>Enter the maximum number of times a User can try to log in.</p>
<p>Minimum: <span style="font-weight: bold;">0</span>. Default: <span style="font-weight: bold;">3</span>.</p>         </td>
      </tr>
      <tr>
         <td><p>Send allocation request (client mode)</p>         </td>
         <td><p>Client mode only</p>
<p>Select this option to send an Allocation Request to the server. If the server refuses the request, the Transfer is rejected.</p>         </td>
      </tr>
      <tr>
         <td><p>Force final EOF on receipt</p>         </td>
         <td><p>Select this option to force final End-of-File on file reception.</p>         </td>
      </tr>
   </tbody>
</table>

1.  Click <span style="font-weight: bold;">Advanced...</span> to access <span style="font-style: italic;">[TCP advanced options](../config_tcp_adv_options)</span>.
2.  Click <span style="font-weight: bold;">OK</span> to confirm the <span style="font-style: italic;">FTP options.</span>

Related topics

[Configuring protocols](../config_protocols)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
