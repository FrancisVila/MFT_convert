{
    "title": "Configuring Secure Relay Router Agent parameters",
    "linkTitle": "Configuring Secure Relay Router Agent parameters",
    "weight": "160"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Configuration

This topic lists the Secure Relay Router Agent parameters that you can modify in the <span style="font-style: italic;">Router Agent parameters</span> window. Gateway opens this window if you click the <span style="font-weight: bold;">Modify</span> button when configuring Secure Relay.

1.  Complete the fields of the <span style="font-style: italic;">Router Agent parameters</span> window as follows:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Parameter</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>General</p>         </td>
      </tr>
      <tr>
         <td><p>Active</p>         </td>
         <td><p>Select this option to activate the Router Agent.</p>         </td>
      </tr>
      <tr>
         <td><p>Name</p>         </td>
         <td><p>Enter the name you want to assign to the Router Agent.</p>         </td>
      </tr>
      <tr>
         <td><p>Address</p>         </td>
         <td><p>Enter the network address of the Router Agent.</p>         </td>
      </tr>
      <tr>
         <td><p>Admin port</p>         </td>
         <td><p>Enter the Router Agent connection port to use for administrative exchanges with the Master Agent.</p>
<p>Default = <span style="font-weight: bold;">6810</span></p>         </td>
      </tr>
      <tr>
         <td><p>Comm port</p>         </td>
         <td><p>Define the Router Agent connection port to use for file exchanges with the Master Agent.</p>
<p>Default = <span style="font-weight: bold;">6811</span></p>         </td>
      </tr>
      <tr>
         <td><p>Advanced</p>         </td>
      </tr>
      <tr>
         <td><p><span id="Number_of_mux_connections"></span>Number of multiplexed connections between Master and Router</p>         </td>
         <td><p>Specify the number of simultaneous connections that can be created between the Master Agent and Router Agent.</p>
<p>Integer: 1 - 100</p>
<p>Default = <span style="font-weight: bold;">5</span></p>         </td>
      </tr>
      <tr>
         <td><p>Data channel ciphering</p>         </td>
         <td><p>Select this option to cipher the Communication channels between this Router Agent and the Master Agent in TLS.</p>
<p>This internal ciphering is completely independent of whether the transported data is ciphered or not.</p>         </td>
      </tr>
      <tr>
         <td><p>Incall network interface</p>         </td>
         <td><p>Network interface to bind to in order to accept incoming connections.</p>         </td>
      </tr>
      <tr>
         <td><p>Incall data port range</p>         </td>
         <td><p>FTP and AS3 only</p>
<p>Port range for data connections in client active and server passive mode.</p>
<p>Enter the lower limit in the <strong>Min</strong> field and the upper limit in the <strong>Max</strong> field.</p>         </td>
      </tr>
      <tr>
         <td><p>Outcall network interface</p>         </td>
         <td><p>Network interface to bind to when connecting to a partner (for example, 123.123.123.123).</p>         </td>
      </tr>
      <tr>
         <td><p>Outcall data port range</p>         </td>
         <td><p>Port range for data connections in client passive mode.</p>
<p>Enter the lower limit in the <strong>Min</strong> field and the upper limit in the <strong>Max</strong> field.</p>         </td>
      </tr>
   </tbody>
</table>

1.  Click <span style="font-weight: bold;">OK</span> to confirm the <span style="font-style: italic;">Router Agent parameters.</span>

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
