{
    "title": "Manage the FTP server",
    "linkTitle": "Manage the FTP server",
    "weight": "100"
}In this topic you will learn how to:

-   <a href="#Add" class="MCXref xref">Add an FTP server</a>
-   <a href="#Start" class="MCXref xref">Start and stop a server</a>
-   <a href="#Edit" class="MCXref xref">Edit FTP server settings</a>
-   <a href="#Delete" class="MCXref xref">Delete a FTP server</a>

<span id="Add"></span>

## Add an FTP server

To add a FTP server, go to the extended *Server Control* page and on the *FTP Servers* pane, click **Actions &gt; Add Server**.

The following table presents all parameters and expected values associated with your new FTP server.

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
         <td>Enable FTP         </td>
         <td>Select to enable FTP transfers: you must select this option if you want to enable secure FTP (FTPS) transfers.         </td>
      </tr>
      <tr>
         <td>Enable FTPS         </td>
         <td><p>Select to enable FTPS transfers.</p>
<blockquote>
<p><strong>Note:</strong></p>
<p>Caution  
When uploading files to SecureTransport Server via FTPS, the FTP client is required to indicate that the transfer is complete by sending a close_notify message. If a close_notify message is not sent by the client, the file transfer will fail.</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td>Enable FIPS         </td>
         <td>Select to enable <a href="../../../c_st_fipstransfermode" class="MCXref xref">FIPS transfer mode</a> for FTPS connections.
<p>By selecting this option, the <strong>Enabled FIPS Ciphers</strong> field becomes editable.</p>         </td>
      </tr>
      <tr>
         <td>Port         </td>
         <td>Enter the port number of your FTP or FTPS server.         </td>
      </tr>
      <tr>
         <td>Host         </td>
         <td>Enter the IP address of your external FTP (or FTPS) host server. Leave this option blank if you do not need an external host.         </td>
      </tr>
      <tr>
         <td>SSL Key Alias         </td>
         <td>Select an
SSL Key Alias
from the drop-down list, for example,
<code>ftpd</code>.         </td>
      </tr>
      <tr>
         <td>Enabled Protocols         </td>
         <td><p>Enter a comma-separated list of SSL protocol versions.</p>
<p>Default value for newly created FTPS servers after updating to SecureTransport 5.5-20210930: <code>TLSv1.2, TLSv1.3</code>.</p>
<p>Default value for existing FTPS servers: <code>TLSv1, TLSv1.1, TLSv1.2</code>. For instructions on how to enable TLSv1.3 protocol support, refer to the <span class="mc-variable axway_variables.Component_Short_Name variable" style="font-style: italic;">SecureTransport</span> <span class="mc-variable axway_variables.Release_Number variable" style="font-style: italic;">5.5</span> <em>Security guide</em>.</p>
<blockquote>
<p><strong>Note:</strong></p>
<p>TLS v1.3 no longer supports DSA certificates. If a server is configured to use DSA certificates and TLS v1.3 is enabled on both the client and the server, the handshake fails.</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td>Key Algorithm         </td>
         <td><p>Enter the Key Algorithm (<code>SunX509</code> by default). Note that with <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> running on AIX systems, the default value is <code>IbmX509</code>.</p>         </td>
      </tr>
      <tr>
         <td>SSL Protocol         </td>
         <td>Enter the used SSL protocol group: <code>SSL</code> or <code>TLS</code> (<code>TLS</code> by default). Note that with <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> running on AIX systems, the default value is <code>SSL_TLS</code>.         </td>
      </tr>
      <tr>
         <td>SSL Trust Algorithm         </td>
         <td>Enter the SSL Trust Algorithm (<code>SunX509</code> by default). Note that with <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> running on AIX systems, the default value is <code>IbmX509</code>.         </td>
      </tr>
      <tr>
         <td>Enabled Ciphers         </td>
         <td><p>Enter the cipher suites to be used with your FTPS server.</p>
<p>For more information on cipher suites, refer to the <span class="mc-variable axway_variables.Component_Short_Name variable" style="font-style: italic;">SecureTransport</span> <em>Cipher suites</em> topic, part of the <em><a href="https://docs.axway.com/bundle/SecureTransport_54_SecurityGuide_allOS_en_HTML5/page/Content/SecurityGuide/STSecurityGuideStartPage.htm" class="MCXref xref" title="SecureTransport 5.4 Security guide"><span class="mc-variable axway_variables.Component_Short_Name variable" style="font-style: italic;">SecureTransport</span> <span class="mc-variable axway_variables.Release_Number variable" style="font-style: italic;">5.5</span> Security guide</a></em>.</p>         </td>
      </tr>
      <tr>
         <td>Enabled FIPS Ciphers         </td>
         <td><p>Modify the cipher suite set to be used with your FTP server in FIPS mode.</p>
<p>By default, this field is populated with all FIPS compliant TLS cipher suites supported by <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span>. For the complete list, see <a href="../../../c_st_fipstransfermode/r_st_required_ciphers_cipher_suites" class="MCXref xref">Advertised ciphers and cipher suites</a>.</p>
<p>Click the "down arrow" icon on the right to access a drop-down menu with options to select and deselect all items, reset to defaults, and reload the previously saved selection.</p>
<p>For the default FTP server, the list of allowed cipher suites in FIPS mode is determined by the <code>Ftp.FIPS.Listeners.Ssl.EnabledCipherSuites</code> configuration option.</p>         </td>
      </tr>
      <tr>
         <td>Client Certificate         </td>
         <td><p>This drop-down list presents the options to define support for certificate use for FTP authentication. Possible values are:</p>
<ul>
<li><code>Disabled</code> – no certificate authentication is required</li>
<li><code>Required</code> – the client must authenticate using a certificate</li>
<li><code>Optional</code> – the client can authenticate either using a certificate or a password</li>
</ul>         </td>
      </tr>
      <tr>
         <td><span style="font-weight: normal; font-style: italic;">FTP Passive Mode</span>         </td>
      </tr>
      <tr>
         <td>Base Port         </td>
         <td>Enter the passive mode base port (<code>0</code> by default: this means that <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> will use a random port for FTP passive mode transfers).         </td>
      </tr>
      <tr>
         <td>Number of Ports         </td>
         <td>The passive mode port range.         </td>
      </tr>
   </tbody>
</table>

Once you are finished entering the parameters of your FTP server, click **Save** to create it; or **Cancel** to discard all changes and return to the *Server Control* page.

<span id="Start"></span>

## Start and stop a server

You can easily start and stop your FTP server.

-   Start your server by clicking the "play" icon:![](/Images/SecureTransport/play-icon.png)  
    A box with a success message pops up on your screen and your server status changes to *Running*.
-   To stop your server, click the "stop" icon:![](/Images/SecureTransport/stop-icon.png)  
    A box with a success message pops up on your screen and your server status changes to *Stopped*.

You can only start the FTP daemon once the Ftp Default server is operating (enabled). Stopping the daemon will stop all underlying started servers. During daemon start, only the enabled servers will be started. In case of FTP, an "enabled server" means that you have at least selected the **Enable FTP** option.

<span id="Edit"></span>

## Edit FTP server settings

You can change any of the FTP server property values. Note that you can change the server name only when the server is stopped. To update an FTP server, click the corresponding "gear" icon:![](/Images/SecureTransport/gearwheel-icon.png)

A new modal box with the FTP settings pops up. Add your changes and click **Save** to apply your changes; or **Cancel** to discard them.

<span id="Delete"></span>

## Delete a FTP server

> **Note:**
>
> You cannot delete or change the name of the "Ftp Default" server from the SecureTransport Administration Tool.

You can only delete a server once it is stopped. You cannot delete a server in *Running* status.

To delete a server, locate it on the *Server Control* page, make sure it is stopped and click the corresponding "trashcan" icon:![](/Images/SecureTransport/trashcan-icon.png)