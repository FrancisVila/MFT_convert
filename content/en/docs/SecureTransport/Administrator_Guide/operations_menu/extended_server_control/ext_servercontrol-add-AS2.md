{
    "title": "Manage the  AS2 server",
    "linkTitle": "Manage the  AS2 server",
    "weight": "130"
}In this topic you will learn how to:

-   [Add an AS2 Server](#add)
-   [Start and stop an AS2 server](#start)
-   [Edit AS2 server settings](#edit)
-   [Delete an AS2 server](#delete)

AS2 (Applicability Statement 2) is a specification about how to transport data securely and reliably over the Internet. Security is achieved by using digital certificates and encryption. The AS2 specification describes how to exchange business data securely and reliably using HTTP as an underlying transport. The data is packaged using standard MIME content types so you can use XML, EDI, binary data, and any other data describable in MIME. Message security (authentication, confidentiality) is implemented using S/MIME. Message reliability is enabled through the use of MDNs. Nonrepudiation and Nonrepudiation of Receipt are business and legal concepts that build upon the security and reliability components in AS2.

If an AS2 license is available, enable the AS2 server. In cluster setup, specify the AS2 settings on both SecureTransport Server and SecureTransport Edge.

## <span id="Add"></span>Add an AS2 Server

To add an AS2 server, go to the extended *Server Control* page and on the *AS2 Servers* pane, click **Actions &gt; Add Server**.

The following table presents all parameters and expected values associated with your new AS2 server.

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
         <td colspan="2">General         </td>
      </tr>
      <tr>
         <td>Server Name         </td>
         <td>Enter a unique name of your server.          </td>
      </tr>
      <tr>
         <td>Enable Receiver         </td>
         <td>Select to enable receiving of your current AS2 server.         </td>
      </tr>
      <tr>
         <td colspan="2">
<p colspan="2">non-SSL Settings</p>
         </td>
      </tr>
      <tr>
         <td>Enable AS2 (non-SSL)         </td>
         <td>
            <p>Select to enable  insecure AS2 transfers with your current AS2 server. By selecting this option, the <b>non-SSL Port</b> and <b>non-SSL Host</b> options become editable. </p>
            <p>&amp;&amp;&amp; ïïï ùùù</p>
         </td>
      </tr>
      <tr>
         <td>non-SSL Port         </td>
         <td>Enter the port number of your non-secure AS2 server.         </td>
      </tr>
      <tr>
         <td>non-SSL Host         </td>
         <td>Enter the host address of your non-secure AS2 server.         </td>
      </tr>
      <tr>
         <td colspan="2">SSL Settings         </td>
      </tr>
      <tr>
         <td>Enable AS2 (SSL)         </td>
         <td>
            <p>Select to enable  <i>secure</i> AS2 transfers with your current AS2 server. By selecting this option, the remaining options become editable. </p>
         </td>
      </tr>
      <tr>
         <td>Enable HSTS         </td>
         <td>
            <p>Select to enable HSTS to always send the <code>"Strict-Transport-Security"</code> HTTPS response header to redirect plain HTTP connections to HTTPS.</p>
            <p>With this functionality, two dedicated Server Configuration options for HSTS are added:</p>
            <ul>
               <li><code>As2.Security.Hsts.enabled</code> - Enable or disable HSTS for the AS2 server. Serves the same purpose as the check-box. Possible values are: <strong>true</strong> or <strong>false</strong>. It is only editable from the <em>Server Configuration</em> page. The default value is <strong>true</strong>.               </li>
               <li><code>As2.Security.Hsts.max-age</code> - HSTS header maximum age attribute value for the AS2 server measured in seconds. The default value is 6-months which is equivalent to <strong>15768000 seconds</strong>.               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>Enable FIPS         </td>
         <td>Select to enable <a href="../../../c_st_fipstransfermode">FIPS transfer mode</a> for AS2 connections.             <p>By selecting this option, the <b>Enabled FIPS Ciphers</b> field becomes editable.</p>         </td>
      </tr>
      <tr>
         <td>SSL Port         </td>
         <td>Enter the port number of your AS2 server.         </td>
      </tr>
      <tr>
         <td>SSL Host         </td>
         <td>Enter the host address of your AS2 server.         </td>
      </tr>
      <tr>
         <td>SSH Key Alias         </td>
         <td>Select an
SSL Key Alias
from the drop-down list, for example,
<code>admind</code>.         </td>
      </tr>
      <tr>
         <td>Key Exchange Algorithms         </td>
         <td>Enter the Key Algorithm (<code>SunX509</code> by default). Note that with <span>SecureTransport</span> running on AIX systems, the default value is <code>IbmX509</code>.         </td>
      </tr>
      <tr>
         <td>Enabled SSL Protocols         </td>
         <td>Enter a comma-separated list of SSL protocol versions (<code>TLSv1, TLSv1.1, TLSv1.2</code> by default).         </td>
      </tr>
      <tr>
         <td>Enabled Ciphers         </td>
         <td>
            <p>Enter the cipher suites to be used with your AS2 server. </p>
            <p>For more information on Cipher suites, refer to the <span>SecureTransport</span><i> </i><span>5.5</span><i> Security guide</i></p>
         </td>
      </tr>
      <tr>
         <td>Enabled FIPS Ciphers         </td>
         <td>
            <p>Modify the cipher suite set to be used with your AS2 server in FIPS mode. </p>
            <p>By default, this field is populated with all FIPS  compliant TLS cipher suites supported by <span>SecureTransport</span>. For the complete list, see <a href="../../../c_st_fipstransfermode/r_st_required_ciphers_cipher_suites">Advertised ciphers and cipher suites</a>.</p>
            <p>Click the "down arrow" icon on the right to access a drop-down menu with options to select and deselect all items, reset to defaults, and reload  the previously saved selection.</p>
            <p>For the default AS2 server, the list of allowed cipher suites in FIPS mode is determined by the <code>As2.FIPS.Listeners.Ssl.EnabledCipherSuites</code> configuration option.</p>
         </td>
      </tr>
   </tbody>
</table>

Once you are finished entering the parameters of your AS2 server, click **Save** to create it; or **Cancel** to discard all changes and return to the *Server Control* page.

For information about more AS2 settings, see [Configure AS2 server settings](../../../c_st_setup/t_st_as2serverconfiguration).

## <span id="Start"></span>Start and stop an AS2 server

You can easily start and stop your AS2 server.

-   Start your server by clicking the "play" icon: ![](trashcan-icon.png)  
    A box with a success message pops up on your screen and your server status changes to *Running*.
-   To stop your server, click the "stop" icon. ![](trashcan-icon.png)  
    A box with a success message pops up on your screen and your server status changes to *Stopped*.

You can only start the AS2 daemon once the As2 Default server is operating (enabled). Stopping the daemon will stop all underlying started servers. During daemon start, only the enabled servers will be started. In case of AS2, an "enabled server" means that you have at least selected either option: **Enable AS2 (non-SSL)** or **Enable AS2 (SSL)**.

## <span id="Edit"></span>Edit AS2 server settings

You can change any of the selected AS2 server property values. Note that you can change the server name only when the server is stopped. To update an AS2 server, click the corresponding "gear" icon:![](trashcan-icon.png)

A new modal box with the AS2 settings pops up. Add your changes and click **Save** to apply your changes; or **Cancel** to discard them.

## <span id="Delete"></span>Delete an AS2 server

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top"><span>To enable AS2 without SSL, you must create an SSL encryption entry for a user class with SSL encryption optional. See </span><a href="../../../c_st_accesscontrol/c_st_sslaccess_new/t_st_sslaccess_new">Manage SSL access</a>.
                                     </td>
      </tr>
</table>

You can only delete a server once it is stopped. You cannot delete a server in *Running* status.

To delete a server, locate it on the *Server Control* page, make sure it is stopped and click the corresponding "trashcan" icon: ![](trashcan-icon.png)
