{
    "title": "New Remote Site: Network address tab",
    "linkTitle": "Network address tab",
    "weight": "210"
}{{< Gateway/componentlongname  >}}: Managing Partners

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Field</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Communication address</p>         </td>
         <td><p>You can define up to four communication addresses for the Remote Site. You must define the properties for the Main address first.</p>
<p>To view an existing definition, or define the properties for a new address, select one of the communication paths used to connect to the Site:</p>
<ul>
<li><strong>Main address</strong> (default)</li>
<li>Alternative address n°1</li>
<li>Alternative address n°2</li>
<li>Alternative address n°3</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Network type</p>         </td>
         <td><p>Select one of the following:</p>
<ul>
<li>TCP/IP</li>
<li>LU 6.2</li>
<li><span style="font-weight: bold;">Empty</span> (default)</li>
</ul>
<p>The fields displayed in the right pane depend on the type of network that you select in this field.</p>         </td>
      </tr>
      <tr>
         <td><p>Initial communication path</p>         </td>
         <td><p>This field displays the initial address used to connect to the Site. By default this field is set to <span style="font-weight: bold;">Main address</span> and is grayed out. However, if an error occurs on the Main address, you can select another communication address from the drop-down list.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Right pane - TCP/IP specific fields:</strong><br />
For more information, refer to <a href="../site_objects_address_config#TCP_IP">Address configuration for Remote Sites</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>IP address or machine name</p>         </td>
         <td><p>Enter the IP address.<br />
Maximum: 63 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Port number</p>         </td>
         <td><p>Enter the port number.</p>         </td>
      </tr>
      <tr>
         <td><p>Network Proxy</p>         </td>
         <td><p>This field displays a list of Proxies whose protocol is either SOCKS4 or HTTPS. This field is available for all protocols.</p>
<p>Select a Proxy from the drop-down list.</p>         </td>
      </tr>
      <tr>
         <td><p>FTP/HTTP Proxy</p>         </td>
         <td><p>FTP and HTTP only</p>
<p>This field displays the list of available FTP or HTTP Proxies, depending on the type of site.</p>
<p>Select a corresponding Proxy from the drop-down list.</p>         </td>
      </tr>
      <tr>
         <td><p><span id="allowed_RAs"></span>Allowed Router Agents</p>         </td>
         <td><p>Select the Secure Relay Router Agents that are allowed to connect to this Site.</p>         </td>
      </tr>
      <tr>
         <td><strong>Bypass XSR</strong>         </td>
         <td>If enabled: Bypass XSR for outgoing calls. Outgoing connections are made directly.         </td>
      </tr>
      <tr>
         <td><p><strong>Right pane - LU 6.2 specific fields:</strong><br />
For more information, refer to <a href="../site_objects_address_config#SNA_LU62">Address configuration for Remote Sites</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>Destination</p>
<p>(mandatory)</p>         </td>
         <td><p>Enter the CPI-C symbolic destination defined in the SNA configuration database.<br />
Maximum: 8 alphanumeric characters.</p>
<p>The symbolic destination identifies the SNA resources to use to connect to the Remote Site. This field contains a definition of all the other parameters on this tab. Any values that you enter in the other fields on this tab will override the values in the CPI-C symbolic destination.</p>         </td>
      </tr>
      <tr>
         <td><p>User identification</p>         </td>
         <td><p>Enter the login user ID.</p>         </td>
      </tr>
      <tr>
         <td><p>Password</p>         </td>
         <td><p>Enter the login user password.</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Enter the conversation type. This version of the product supports <span style="font-style: italic;">Basic Conversation</span> only.</p>         </td>
      </tr>
      <tr>
         <td><p>Mode</p>         </td>
         <td><p>Enter the LU 6.2 mode name to use. The Mode Name determines the session parameters to use.</p>         </td>
      </tr>
      <tr>
         <td><p>LU Partner</p>         </td>
         <td><p>Enter the Logical Unit for the Remote partner.</p>         </td>
      </tr>
      <tr>
         <td><p>LU Local</p>         </td>
         <td><p>Enter the Logical Unit for the Local partner.</p>         </td>
      </tr>
      <tr>
         <td><p>Transaction</p>         </td>
         <td><p>Enter the name of the CPI-C Transaction program that you want to invoke.</p>         </td>
      </tr>
      <tr>
         <td><p>PIP</p>         </td>
         <td><p>Enter the Program Initialization Parameters.</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Working with Remote Sites](../)

[Address configuration for Remote Sites](../site_objects_address_config)

[Site objects: Parameters List](../../managing_local_sites_cli/sites_parameter_list)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
