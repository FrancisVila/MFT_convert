{
    "title": "Manage the FTP\u00a0server",
    "linkTitle": "Manage the FTP\u00a0server",
    "weight": "110"
}In this topic you will learn how to:

-   [Add an FTP server](#add)
-   [Start and stop a server](#start)
-   [Edit FTP server settings](#edit)
-   [Delete a FTP server](#delete)

## <span id="Add"></span>Add an FTP server

To add a FTP server, go to the extended *Server Control* page and on the *FTP Servers* pane, click **Actions &gt; Add Server**.

The following table presents all parameters and expected values associated with your new FTP server.

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Field</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td colspan="2"><span>General</span>
         </td>
      </tr>
      <tr>
         <td>Server Name         </td>
         <td>Enter a unique name of your server.          </td>
      </tr>
      <tr>
         <td>Enable FTP         </td>
         <td>Select to enable FTP transfers: you must select this option if you want to enable secure FTP (FTPS) transfers.         </td>
      </tr>
      <tr>
         <td>Enable FTPS         </td>
         <td>
            <p>Select to enable FTPS transfers.</p>
            <p>&amp;&amp;&amp; ïïï ùùù</p>
         </td>
      </tr>
      <tr>
         <td>Enable FIPS         </td>
         <td>Select to enable <a href="../../../c_st_fipstransfermode">FIPS transfer mode</a> for FTPS connections.             <p>By selecting this option, the <b>Enabled FIPS Ciphers</b> field becomes editable.</p>         </td>
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
         <td>Enter a comma-separated list of SSL protocol versions (<code>TLSv1, TLSv1.1, TLSv1.2</code> by default).         </td>
      </tr>
      <tr>
         <td>Key Algorithm         </td>
         <td>
            <p>Enter the Key Algorithm (<code>SunX509</code> by default). Note that with <span>SecureTransport</span> running on AIX systems, the default value is <code>IbmX509</code>.</p>
         </td>
      </tr>
      <tr>
         <td>SSL Protocol         </td>
         <td>Enter the used SSL protocol group: <code>SSL</code> or <code>TLS</code> (<code>TLS</code> by default). Note that with <span>SecureTransport</span> running on AIX systems, the default value is <code>SSL_TLS</code>.         </td>
      </tr>
      <tr>
         <td>SSL Trust Algorithm         </td>
         <td>Enter the SSL Trust Algorithm (<code>SunX509</code> by default). Note that with <span>SecureTransport</span> running on AIX systems, the default value is <code>IbmX509</code>.         </td>
      </tr>
      <tr>
         <td>Enabled Ciphers         </td>
         <td>
            <p>Enter the cipher suites to be used with your FTPS server. </p>
            <p>For more information on cipher suites, refer to the <span>SecureTransport</span><i> Cipher suites</i> topic, part of the <i><a alt="SecureTransport 5.4 Security guide" href="https://docs.axway.com/bundle/SecureTransport_54_SecurityGuide_allOS_en_HTML5/page/Content/SecurityGuide/STSecurityGuideStartPage.htm" title="SecureTransport 5.4 Security guide"><span>SecureTransport</span> <span>5.5</span> Security guide</a></i>.</p>
         </td>
      </tr>
      <tr>
         <td>Enabled FIPS Ciphers         </td>
         <td>
            <p>Modify the cipher suite set to be used with your FTP server in FIPS mode. </p>
            <p>By default, this field is populated with all FIPS  compliant TLS cipher suites supported by <span>SecureTransport</span>. For the complete list, see <a href="../../../c_st_fipstransfermode/r_st_required_ciphers_cipher_suites">Advertised ciphers and cipher suites</a>.</p>
            <p>Click the "down arrow" icon on the right to access a drop-down menu with options to select and deselect all items, reset to defaults, and reload  the previously saved selection.</p>
            <p>For the default FTP server, the list of allowed cipher suites in FIPS mode is determined by the <code>Ftp.FIPS.Listeners.Ssl.EnabledCipherSuites</code> configuration option.</p>
         </td>
      </tr>
      <tr>
         <td>Client Certificate          </td>
         <td>
            <p>This drop-down list presents the options to define support for certificate use for FTP authentication. Possible values are:</p>
            <ul>
               <li><code>Disabled</code> – no certificate authentication is required               </li>
               <li><code>Required</code> – the client must authenticate using a certificate                </li>
               <li><code>Optional</code> – the client can authenticate either using a certificate or a password               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td colspan="2"><span>FTP Passive Mode</span>
         </td>
      </tr>
      <tr>
         <td>Base Port         </td>
         <td>Enter the passive mode base port (<code>0</code> by default: this means that <span>SecureTransport</span> will use a random port for FTP passive mode transfers).         </td>
      </tr>
      <tr>
         <td>Number of Ports         </td>
         <td>The passive mode port range.         </td>
      </tr>
   </tbody>
</table>

Once you are finished entering the parameters of your FTP server, click **Save** to create it; or **Cancel** to discard all changes and return to the *Server Control* page.

## <span id="Start"></span>Start and stop a server

You can easily start and stop your FTP server.

-   Start your server by clicking the "play" icon:![](trashcan-icon.png)  
    A box with a success message pops up on your screen and your server status changes to *Running*.
-   To stop your server, click the "stop" icon:![](trashcan-icon.png)  
    A box with a success message pops up on your screen and your server status changes to *Stopped*.

You can only start the FTP daemon once the Ftp Default server is operating (enabled). Stopping the daemon will stop all underlying started servers. During daemon start, only the enabled servers will be started. In case of FTP, an "enabled server" means that you have at least selected the **Enable FTP** option.

## <span id="Edit"></span>Edit FTP server settings

You can change any of the FTP server property values. Note that you can change the server name only when the server is stopped. To update an FTP server, click the corresponding "gear" icon:![](trashcan-icon.png)

A new modal box with the FTP settings pops up. Add your changes and click **Save** to apply your changes; or **Cancel** to discard them.

## <span id="Delete"></span>Delete a FTP server

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Caution  </b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Caution  &lt;/b&gt;" valign="top">When uploading files to <span>SecureTransport</span> Server via FTPS, the FTP client is required to indicate that the transfer is complete by sending a <code>close_notify</code> message. If a <code>close_notify</code> message is not sent by the client, the file transfer will fail.         </td>
      </tr>
</table>

You can only delete a server once it is stopped. You cannot delete a server in *Running* status.

To delete a server, locate it on the *Server Control* page, make sure it is stopped and click the corresponding "trashcan" icon:![](trashcan-icon.png)
