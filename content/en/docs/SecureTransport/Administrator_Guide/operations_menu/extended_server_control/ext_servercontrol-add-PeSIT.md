{
    "title": "Manage the PeSIT server",
    "linkTitle": "Manage the PeSIT server",
    "weight": "140"
}In this topic you will learn how to:

-   <a href="#Add" class="MCXref xref">Add a PeSIT server</a>
-   <a href="#Start" class="MCXref xref">Start and stop a server</a>
-   <a href="#Edit" class="MCXref xref">Edit PeSIT server settings</a>
-   <a href="#Delete" class="MCXref xref">Delete a PeSIT server</a>

<span id="Add"></span>

## Add a PeSIT server

To add a PeSIT server, go to the extended *Server Control* page and on the *PeSIT Servers* pane, click **Actions &gt; Add Server**.

The following table presents all parameters and expected values associated with your new PeSIT server.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><span style="font-weight: normal; font-style: italic;">General</span>         </td>
      </tr>
      <tr>
         <td>Server Name         </td>
         <td>Enter a unique name of your server.         </td>
      </tr>
      <tr>
         <td>Enable PeSIT over Plain Socket         </td>
         <td>Select to enable non-secure PeSIT transfers.         </td>
      </tr>
      <tr>
         <td>Enable PeSIT over Secured Socket         </td>
         <td>Select to enable secure PeSIT transfers.         </td>
      </tr>
      <tr>
         <td>Enable PeSIT over Secured Socket (legacy)         </td>
         <td>Select to enable transfers with remote partners using SSL Legacy.         </td>
      </tr>
      <tr>
         <td>Enable PeSIT over Secured Socket (legacy § comp)         </td>
         <td><p>Select to enable the automatic detection of the used SSL/TLS
mode (Legacy or Comp) when <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> acts as a server. Information about the
detected mode is logged in the server log under <strong>Level &gt; Debug</strong>.</p>
<p>The PeSIT listener used for communication with partners in both TLS Comp and TLS Legacy modes is configured using the following server configuration parameters:</p>
<ul>
<li><code>Pesit.Autodetect.Tls.Mode.Enabled </code>- enables or disables the listener</li>
<li><code>Pesit.Autodetect.Tls.Mode.Port </code>- specifies the port number of the listener</li>
<li><code>Pesit.Listeners.Autodetect.Tls.Mode.keyAlgorithm</code> - specifies the key algorithm</li>
<li><code>Pesit.Listeners.Autodetect.Tls.Mode.keyAlias</code> - specifies the key alias of the listener</li>
<li><code>Pesit.Listeners.Autodetect.Tls.Mode.protocol </code>- specifies the protocol of the listener</li>
<li><code>Pesit.Listeners.Autodetect.Tls.Mode.trustAlgorithm</code> - specifies the trust algorithm<br />
</li>
</ul>         </td>
      </tr>
      <tr>
         <td>Enable PeSIT over pTCP plain socket         </td>
         <td>Select to enable non-secure PeSIT transfers over pTCP.         </td>
      </tr>
      <tr>
         <td>Enable PeSIT over pTCP secure socket         </td>
         <td>Select to enable secure PeSIT transfers over pTCP.         </td>
      </tr>
      <tr>
         <td>Enable FIPS Transfer Mode         </td>
         <td>Select to enable <a href="../../../c_st_fipstransfermode" class="MCXref xref">FIPS transfer mode</a> for PeSIT connections.
<p>By selecting this option, the <strong>Enabled FIPS Ciphers</strong> field becomes editable.</p>         </td>
      </tr>
      <tr>
         <td>Port         </td>
         <td>Enter the port number of your PeSIT server.         </td>
      </tr>
      <tr>
         <td>SSL port         </td>
         <td>Enter the SSL port number for secure connection to your PeSIT server.         </td>
      </tr>
      <tr>
         <td>Host         </td>
         <td>Enter the IP address of your external PeSIT (or PeSIT) host server. Leave this option blank if you do not need an external host.         </td>
      </tr>
      <tr>
         <td>Key Exchange Algorithms         </td>
         <td><p>Enter the Key Algorithm (<code>SunX509</code> by default). Note that with <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> running on AIX systems, the default value is <code>IbmX509</code>.</p>         </td>
      </tr>
      <tr>
         <td>SSL Key Alias         </td>
         <td>Select an
SSL Key Alias
from the drop-down list, for example,
<code>PeSITd</code>.         </td>
      </tr>
      <tr>
         <td>PeSIT SSL Protocol         </td>
         <td>Enter the used SSL protocol group: <code>SSL</code> or <code>TLS</code> (<code>TLS</code> by default). Note that with <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> running on AIX systems, the default value is <code>SSL_TLS</code>.         </td>
      </tr>
      <tr>
         <td>Enabled SSL Protocols         </td>
         <td>Enter a comma-separated list of SSL protocol versions to be enabled.
<p>Default value for newly created PeSIT servers after updating to SecureTransport 5.5-20210930: <code>TLSv1.2, TLSv1.3</code>.</p>
<p>Default value for existing PeSIT servers: <code>TLSv1, TLSv1.1, TLSv1.2</code>.<br />
For instructions on how to enable TLSv1.3 protocol support, refer to the <span class="mc-variable axway_variables.Component_Short_Name variable" style="font-style: italic;">SecureTransport</span> <span class="mc-variable axway_variables.Release_Number variable" style="font-style: italic;">5.5</span> <em>Security guide</em>.</p>         </td>
      </tr>
      <tr>
         <td><span style="font-weight: normal; font-style: italic;">Common SSL Settings</span>         </td>
      </tr>
      <tr>
         <td>PeSIT Trust algorithms         </td>
         <td><p>Enter the key trust algorithm (<code>SunX509</code> by default). Note that with <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> running on AIX systems, the default value is <code>IbmX509</code>.</p>         </td>
      </tr>
      <tr>
         <td>Enabled Ciphers         </td>
         <td><p>Enter the cipher suites to be used with your PeSIT server.</p>
<p>For more information on cipher suites, refer to the <span class="mc-variable axway_variables.Component_Short_Name variable" style="font-style: italic;">SecureTransport</span> <em>Cipher suites</em> topic, part of the <em><a href="https://docs.axway.com/bundle/SecureTransport_55_SecurityGuide_allOS_en_HTML5/page/Content/SecurityGuide/STSecurityGuideStartPage.htm" class="MCXref xref" title="SecureTransport 5.5 Security guide"><span class="mc-variable axway_variables.Component_Short_Name variable" style="font-style: italic;">SecureTransport</span> <span class="mc-variable axway_variables.Release_Number variable" style="font-style: italic;">5.5</span> Security guide</a></em>.</p>         </td>
      </tr>
      <tr>
         <td>Enabled FIPS Ciphers         </td>
         <td><p>Modify the cipher suite set to be used with your PeSIT server in FIPS mode.</p>
<p>By default, this field is populated with all FIPS compliant TLS cipher suites supported by <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span>. For the complete list, see <a href="../../../c_st_fipstransfermode/r_st_required_ciphers_cipher_suites" class="MCXref xref">Advertised ciphers and cipher suites</a>.</p>
<p>Click the "down arrow" icon on the right to access a drop-down menu with options to select and deselect all items, reset to defaults, and reload the previously saved selection.</p>
<p>For the default PeSIT server, the list of allowed cipher suites in FIPS mode is determined by the <code>Pesit.FIPS.Listeners.Ssl.EnabledCipherSuites</code> configuration option.</p>         </td>
      </tr>
      <tr>
         <td>Client Certificate         </td>
         <td><p>This drop-down list presents the options to define support for certificate use for PeSIT authentication. Possible values are:</p>
<p><code>Disabled</code> – no certificate authentication is required</p>
<p><code>Required</code> – the client must authenticate using a certificate</p>
<p><code>Optional</code> – the client can authenticate either using a certificate or a password</p>         </td>
      </tr>
      <tr>
         <td><span style="font-weight: normal; font-style: italic;">PeSIT over pTCP</span> <span style="font-weight: normal;">– to enable editing these options, you must select at least one of the <strong>Enable PeSIT over pTCP</strong> options listed above</span>         </td>
      </tr>
      <tr>
         <td>Port         </td>
         <td>Enter the port number for your PeSIT over pTCP connection.         </td>
      </tr>
      <tr>
         <td>SSL port         </td>
         <td>Enter the SSL port number for secure PeSIT over pTCP connection.         </td>
      </tr>
      <tr>
         <td>Key Exchange Algorithms         </td>
         <td><p>Enter the Key Algorithm (<code>SunX509</code> by default). Note that with <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> running on AIX systems, the default value is <code>IbmX509</code>.</p>         </td>
      </tr>
      <tr>
         <td>SSL Key Alias         </td>
         <td>Select an
SSL Key Alias
from the drop-down list, for example,
<code>PeSITd</code>.         </td>
      </tr>
      <tr>
         <td>SSL Protocol         </td>
         <td>Enter the used SSL protocol group: <code>SSL</code> or <code>TLS</code> (<code>TLS</code> by default). Note that with <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> running on AIX systems, the default value is <code>SSL_TLS</code>.         </td>
      </tr>
      <tr>
         <td>Trust Algorithms         </td>
         <td>Enter the SSL Trust Algorithm (<code>SunX509</code> by default). Note that with <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> running on AIX systems, the default value is <code>IbmX509</code>.         </td>
      </tr>
      <tr>
         <td><span style="font-weight: normal; font-style: italic;">PeSIT over Secured Socket (legacy)</span><span style="font-weight: normal;">,</span> <span style="font-weight: normal; font-style: italic;">PeSIT over Secured Socket (legacy &amp; comp)</span> - <span style="font-weight: normal;"> to enable editing these options, you must select the corresponding option listed above</span>         </td>
      </tr>
      <tr>
         <td>SSL port         </td>
         <td>Enter the SSL port number for secure PeSIT connection.         </td>
      </tr>
      <tr>
         <td>Key Exchange Algorithms         </td>
         <td><p>Enter the Key Algorithm (<code>SunX509</code> by default). Note that with <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> running on AIX systems, the default value is <code>IbmX509</code>.</p>         </td>
      </tr>
      <tr>
         <td>SSL Key Alias         </td>
         <td>Select an
SSL Key Alias
from the drop-down list, for example,
<code>PeSITd</code>.         </td>
      </tr>
      <tr>
         <td>SSL Protocol         </td>
         <td>Enter the used SSL protocol group: <code>SSL</code> or <code>TLS</code> (<code>TLS</code> by default). Note that with <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> running on AIX systems, the default value is <code>SSL_TLS</code>.         </td>
      </tr>
      <tr>
         <td>Trust Algorithms         </td>
         <td>Enter the SSL Trust Algorithm (<code>SunX509</code> by default). Note that with <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> running on AIX systems, the default value is <code>IbmX509</code>.         </td>
      </tr>
   </tbody>
</table>

Once you are finished entering the parameters of your PeSIT server, click **Save** to create it; or **Cancel** to discard all changes and return to the *Server Control* page.

<span id="Start"></span>

## Start and stop a server

You can easily start and stop your PeSIT server.

-   Start your server by clicking the "play" icon: ![](/Images/SecureTransport/play-icon.png)  
    A box with a success message pops up on your screen and your server status changes to *Running*.
-   To stop your server, click the "stop" icon. ![](/Images/SecureTransport/stop-icon.png)  
    A box with a success message pops up on your screen and your server status changes to *Stopped*.

You can only start the PeSIT daemon once the Pesit Default server is operating (enabled). Stopping the daemon will stop all underlying started servers. During daemon start, only the enabled servers will be started. In case of PeSIT, an "enabled server" means that you have at least selected either of the available "Enable PeSIT" options.

<span id="Edit"></span>

## Edit PeSIT server settings

You can change any of the PeSIT server property values. Note that you can change the server name only when the server is stopped. To update a PeSIT server, click the corresponding "gear" icon:![](/Images/SecureTransport/gearwheel-icon.png)

A new modal box with the PeSIT settings pops up. Add your changes and click **Save** to apply your changes; or **Cancel** to discard them.

<span id="Delete"></span>

## Delete a PeSIT server

> **Note:**
>
> You cannot delete or change the name of the "Pesit Default" server from the SecureTransport Administration Tool.

You can only delete a server once it is stopped. You cannot delete a server in *Running* status.

To delete a server, locate it on the *Server Control* page, make sure it is stopped and click the corresponding "trashcan" icon: ![](/Images/SecureTransport/trashcan-icon.png)
