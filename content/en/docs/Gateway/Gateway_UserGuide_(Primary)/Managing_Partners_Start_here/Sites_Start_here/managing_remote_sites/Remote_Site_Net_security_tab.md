{
    "title": "New Remote Site: Net security tab",
    "linkTitle": "Net security tab",
    "weight": "300"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Partners

Use the <span style="font-weight: bold;">Net security</span> tab to define security options for this Site.

This tab is not available for SFTP.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Network security option</p>         </td>
         <td><p>Select one of the following:</p>
<ul>
<li>None</li>
<li><span style="font-weight: bold;">TLS</span> (if you select this option, the following TLS security fields are displayed)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>TLS security</p>         </td>
      </tr>
      <tr>
         <td><p>Security profile for outgoing connection</p>         </td>
         <td><p>Enter the name of the outgoing TLS Security Profile.<br />
Maximum: 30 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Security profile for incoming connection</p>         </td>
         <td><p>Enter the name of the incoming TLS Security Profile.<br />
Maximum: 30 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Remote certificate filter (Only FTP/HTTP)</p>         </td>
      </tr>
      <tr>
         <td><p>Subject certificate alias</p>         </td>
         <td><p>Select the certificate alias used to authenticate the partner.</p>
<p>If you select to authenticate the partner by a certificate, you do not need to complete the <span style="font-weight: bold;">Public key alias</span> and <span style="font-weight: bold;">Public key group</span> fields.</p>
<blockquote>
<p><strong>Note:</strong></p>
<p>Restrictions apply to this list in FIPS mode.
See the Security Guide for further information.</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td><p>Issuer certificate alias</p>         </td>
         <td><p>Select the issuer (CA) certificate alias to use to authenticate the partner certificate.</p>
<blockquote>
<p><strong>Note:</strong></p>
<p>Restrictions apply to this list in FIPS mode.
See the Security Guide for further information.</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td><p>Subject name pattern</p>         </td>
         <td><p>Enter a name pattern to use as a filter for accepted subject certificates. For example:</p>
<p>This value can contain wildcard characters (* and ?).</p>         </td>
      </tr>
      <tr>
         <td><p>Issuer name pattern</p>         </td>
         <td><p>Enter a name pattern to use as a filter for the Issuer distinguished name.<br />
Maximum: 512 alphanumeric characters.</p>
<p>This value can contain wildcard characters (* and ?).</p>         </td>
      </tr>
      <tr>
         <td><p>Remote PassPort PS partner entity filter</p>         </td>
      </tr>
      <tr>
         <td><p>Name</p>         </td>
         <td><p>When Gateway operates in server mode with a partner defined in PassPort, enter the identity of the PassPort partner.</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>Transport security in SecureRelay for outgoing connection</p>         </td>
         <td><p>Select this option if you require client TLS termination in the DMZ.</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Working with Remote Sites](../)

[Site objects: Parameters List](../../managing_local_sites_cli/sites_parameter_list)

[Axway PassPort PS connector](../../../../connectors_about/passport_pm_connector/passport_ps_connector)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
