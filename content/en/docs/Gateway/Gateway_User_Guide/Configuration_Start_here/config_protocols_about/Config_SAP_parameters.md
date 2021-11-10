{
    "title": "Configuring protocols: SAP parameters",
    "linkTitle": "SAP parameters",
    "weight": "180"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Configuration

This topic lists the parameters that you can modify in the <span style="font-style: italic;">SAP parameters</span> window. Gateway opens this window if you click the <span style="font-weight: bold;">New</span> or <span style="font-weight: bold;">Modify</span> button when configuring a protocol.

The choices available in this window depend on the value chosen in <span style="font-weight: bold;">SecureRelay access policy</span> for this protocol.

1.  Complete the fields of the <span style="font-style: italic;">SAP parameters</span> window as follows:

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
         <td><p>Gateway listen port</p>         </td>
         <td><p>Enter the TCP port number on which Gateway listens.</p>         </td>
      </tr>
      <tr>
         <td><p>Gateway</p>         </td>
         <td><p>Enter the Gateway network interface.</p>         </td>
      </tr>
      <tr>
         <td><p>SecureRelay listen port</p>         </td>
         <td><p>Enter the TCP port number on which Secure Relay listens.</p>         </td>
      </tr>
      <tr>
         <td><p>SecureRelay</p>         </td>
         <td><p>Enter the SecureRelay network interface.</p>         </td>
      </tr>
      <tr>
         <td><strong>Master side listen port</strong>         </td>
         <td><p><em>Optional</em></p>
<p>Specify the port you want to open on XSR Master Agent side.</p>         </td>
      </tr>
      <tr>
         <td><p>Listen port range in server passive mode</p>         </td>
         <td><p>Optional</p>
<p>Specify the range of ports (<span style="font-weight: bold;">Min</span> to <span style="font-weight: bold;">Max</span>) for data connections in server passive mode attached to a session established on this Gateway listen port.</p>         </td>
      </tr>
      <tr>
         <td><strong>Bypass data port range</strong>         </td>
         <td><p><em>Optional</em></p>
<p>If checked (<em>true</em>) then the setting for the <em>Listen port range in server passive mode</em> (the general setting, see above) will be overwritten by the <em>per-XSR-RA</em> Incall Data Port Range setting (the specific setting). If not checked (<em>false</em>, default value) the above setting will be used.</p>         </td>
      </tr>
      <tr>
         <td><strong>Advanced</strong>         </td>
      </tr>
      <tr>
         <td><strong>Disable IP filtering in <span class="mc-variable suite_variables.SecureRelayName variable">Secure Relay</span></strong>         </td>
         <td>Select this option to specifically disable the IP filtering on the current Sap, on all <span class="mc-variable suite_variables.SecureRelayName variable">Secure Relay</span> instances.
This option is available only when general IP filtering is enabled in <a href="../../../../gateway_security_guide/managing_security_start_here/config_secure_relay_adv_options" class="MCXref xref">Configuring Secure Relay advanced options</a>.         </td>
      </tr>
      <tr>
         <td><p>Transport security in <span class="mc-variable suite_variables.SecureRelayName variable">Secure Relay</span></p>         </td>
         <td><p>Select this option if you require TLS termination in the DMZ.</p>         </td>
      </tr>
      <tr>
         <td><p>Security profile</p>         </td>
         <td><p>Select the required security profile.</p>         </td>
      </tr>
      <tr>
         <td><p>Protocol login in <span class="mc-variable suite_variables.SecureRelayName variable">Secure Relay</span></p>         </td>
         <td><p>FTP, HTTP only</p>
<p>Select this option if you require Login termination in the DMZ (protocol login).</p>         </td>
      </tr>
   </tbody>
</table>

1.  Click <span style="font-weight: bold;">OK</span> to confirm the SAP parameters.

Related topics

[Configuration: Connectivity parameters](../../config_connectivity_paras#olh_connectivity_Secure_Relay)

[Configuring protocols](../config_protocols)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
