{
    "title": "Manage the AS2 server",
    "linkTitle": "Manage the  AS2 server",
    "weight": "120"
}In this topic you will learn how to:

-   <a href="#Add" class="MCXref xref">Add an AS2 Server</a>
-   <a href="#Start" class="MCXref xref">Start and stop an AS2 server</a>
-   <a href="#Edit" class="MCXref xref">Edit AS2 server settings</a>
-   <a href="#Delete" class="MCXref xref">Delete an AS2 server</a>

AS2 (Applicability Statement 2) is a specification about how to transport data securely and reliably over the Internet. Security is achieved by using digital certificates and encryption. The AS2 specification describes how to exchange business data securely and reliably using HTTP as an underlying transport. The data is packaged using standard MIME content types so you can use XML, EDI, binary data, and any other data describable in MIME. Message security (authentication, confidentiality) is implemented using S/MIME. Message reliability is enabled through the use of MDNs. Nonrepudiation and Nonrepudiation of Receipt are business and legal concepts that build upon the security and reliability components in AS2.

If an AS2 license is available, enable the AS2 server. In cluster setup, specify the AS2 settings on both <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server and <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge.

<span id="Add"></span>

## Add an AS2 Server

To add an AS2 server, go to the extended *Server Control* page and on the *AS2 Servers* pane, click **Actions &gt; Add Server**.

The following table presents all parameters and expected values associated with your new AS2 server.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>General         </td>
      </tr>
      <tr>
         <td>Server Name         </td>
         <td>Enter a unique name of your server.         </td>
      </tr>
      <tr>
         <td>Enable Receiver         </td>
         <td>Select to enable receiving of your current AS2 server.         </td>
      </tr>
      <tr>
         <td><p>non-SSL Settings</p>         </td>
      </tr>
      <tr>
         <td>Enable AS2 (non-SSL)         </td>
         <td><p>Select to enable insecure AS2 transfers with your current AS2 server. By selecting this option, the <strong>non-SSL Port</strong> and <strong>non-SSL Host</strong> options become editable.</p>
<blockquote>
<p><strong>Note:</strong></p>
<p>To enable AS2 without SSL, you must create an SSL encryption entry for a user class with SSL encryption optional. See Manage SSL access.</p>
</blockquote>         </td>
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
         <td>SSL Settings         </td>
      </tr>
      <tr>
         <td>Enable AS2 (SSL)         </td>
         <td><p>Select to enable <em>secure</em> AS2 transfers with your current AS2 server. By selecting this option, the remaining options become editable.</p>         </td>
      </tr>
      <tr>
         <td>Enable HSTS         </td>
         <td><p>Select to enable HSTS to always send the <code>"Strict-Transport-Security"</code> HTTPS response header to redirect plain HTTP connections to HTTPS.</p>
<p>With this functionality, two dedicated Server Configuration options for HSTS are added:</p>
<ul>
<li><code>As2.Security.Hsts.enabled</code> - Enable or disable HSTS for the AS2 server. Serves the same purpose as the check-box. Possible values are: <strong>true</strong> or <strong>false</strong>. It is only editable from the <em>Server Configuration</em> page. The default value is <strong>true</strong>.</li>
<li><code>As2.Security.Hsts.max-age</code> - HSTS header maximum age attribute value for the AS2 server measured in seconds. The default value is 6-months which is equivalent to <strong>15768000 seconds</strong>.</li>
</ul>         </td>
      </tr>
      <tr>
         <td>Enable FIPS         </td>
         <td>Select to enable <a href="../../../c_st_fipstransfermode" class="MCXref xref">FIPS transfer mode</a> for AS2 connections.
<p>By selecting this option, the <strong>Enabled FIPS Ciphers</strong> field becomes editable.</p>         </td>
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
         <td>Enter the Key Algorithm (<code>SunX509</code> by default). Note that with <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> running on AIX systems, the default value is <code>IbmX509</code>.         </td>
      </tr>
      <tr>
         <td>Enabled SSL Protocols         </td>
         <td>Enter a comma-separated list of SSL protocol versions to be enabled.
<p>Default value for newly created AS2 servers after updating to SecureTransport 5.5-20210930: <code>TLSv1.2, TLSv1.3</code>.</p>
<p>Default value for existing AS2 servers: <code>TLSv1, TLSv1.1, TLSv1.2</code>.<br />
For instructions on how to enable TLSv1.3 protocol support, refer to the <span class="mc-variable axway_variables.Component_Short_Name variable" style="font-style: italic;">SecureTransport</span> <span class="mc-variable axway_variables.Release_Number variable" style="font-style: italic;">5.5</span> <em>Security guide</em>.</p>         </td>
      </tr>
      <tr>
         <td>Enabled Ciphers         </td>
         <td><p>Enter the cipher suites to be used with your AS2 server.</p>
<p>For more information on Cipher suites, refer to the <span class="mc-variable axway_variables.Component_Short_Name variable" style="font-style: italic;">SecureTransport</span> <em></em> <span class="mc-variable axway_variables.Release_Number variable" style="font-style: italic;">5.5</span> <em>Security guide</em>.</p>         </td>
      </tr>
      <tr>
         <td>Enabled FIPS Ciphers         </td>
         <td><p>Modify the cipher suite set to be used with your AS2 server in FIPS mode.</p>
<p>By default, this field is populated with all FIPS compliant TLS cipher suites supported by <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span>. For the complete list, see <a href="../../../c_st_fipstransfermode/r_st_required_ciphers_cipher_suites" class="MCXref xref">Advertised ciphers and cipher suites</a>.</p>
<p>Click the "down arrow" icon on the right to access a drop-down menu with options to select and deselect all items, reset to defaults, and reload the previously saved selection.</p>
<p>For the default AS2 server, the list of allowed cipher suites in FIPS mode is determined by the <code>As2.FIPS.Listeners.Ssl.EnabledCipherSuites</code> configuration option.</p>         </td>
      </tr>
   </tbody>
</table>

Once you are finished entering the parameters of your AS2 server, click **Save** to create it; or **Cancel** to discard all changes and return to the *Server Control* page.

For information about more AS2 settings, see <a href="../../../c_st_setup/t_st_as2serverconfiguration#SetupMenu_1217491348_1046982" class="MCXref xref">Configure AS2 server settings</a>.

<span id="Start"></span>

## Start and stop an AS2 server

You can easily start and stop your AS2 server.

-   Start your server by clicking the "play" icon: ![](/Images/SecureTransport/play-icon.png)  
    A box with a success message pops up on your screen and your server status changes to *Running*.
-   To stop your server, click the "stop" icon. ![](/Images/SecureTransport/stop-icon.png)  
    A box with a success message pops up on your screen and your server status changes to *Stopped*.

You can only start the AS2 daemon once the As2 Default server is operating (enabled). Stopping the daemon will stop all underlying started servers. During daemon start, only the enabled servers will be started. In case of AS2, an "enabled server" means that you have at least selected either option: **Enable AS2 (non-SSL)** or **Enable AS2 (SSL)**.

<span id="Edit"></span>

## Edit AS2 server settings

You can change any of the selected AS2 server property values. Note that you can change the server name only when the server is stopped. To update an AS2 server, click the corresponding "gear" icon:![](/Images/SecureTransport/gearwheel-icon.png)

A new modal box with the AS2 settings pops up. Add your changes and click **Save** to apply your changes; or **Cancel** to discard them.

<span id="Delete"></span>

## Delete an AS2 server

> **Note:**
>
> You cannot delete or change the name of the "AS2 Default" server from the SecureTransport Administration Tool.

You can only delete a server once it is stopped. You cannot delete a server in *Running* status.

To delete a server, locate it on the *Server Control* page, make sure it is stopped and click the corresponding "trashcan" icon: ![](/Images/SecureTransport/trashcan-icon.png)
