{
    "title": "Manage the SSH server",
    "linkTitle": "Manage the SSH server",
    "weight": "150"
}In this topic you will learn how to:

-   <a href="#Add" class="MCXref xref">Add an SSH server</a>
-   <a href="#Start" class="MCXref xref">Start and stop an SSH server</a>
-   <a href="#Edit" class="MCXref xref">Edit SSH server settings</a>
-   <a href="#Delete" class="MCXref xref">Delete an SSH server</a>

<span id="Add"></span>

## Add an SSH server

To add an SSH server, go to the *Server Control* page and on the *SSH Servers* panel, click **Actions &gt; Add Server**.

The following table presents all parameters and expected values associated with your new SSH server.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Server Name         </td>
         <td>Enter a unique name of your server.         </td>
      </tr>
      <tr>
         <td>Enable SCP         </td>
         <td>Select to enable SCP (Secure Copy) support with transfers using your current SSH server.         </td>
      </tr>
      <tr>
         <td>Enable SFTP         </td>
         <td>Select to enable SFTP transfers with using your current SSH server.         </td>
      </tr>
      <tr>
         <td>Enable FIPS         </td>
         <td><p>Select to enable <a href="../../../../c_st_fipstransfermode">FIPS transfer mode</a> for SSH connections. By selecting this option, the following fields become editable:</p>
<ul>
<li><a href="#FIPS_KEX">FIPS Exchange Algorithms</a></li>
<li><a href="#FIPS_PK">FIPS Public Keys</a></li>
<li><a href="#FIPS_MAC">FIPS MAC Algorithms</a></li>
<li><a href="#FIPS_ciphers">Enabled FIPS Ciphers</a></li>
</ul>         </td>
      </tr>
      <tr>
         <td>Port         </td>
         <td>Enter the port number of your SSH server.         </td>
      </tr>
      <tr>
         <td>Host         </td>
         <td>Enter the host address of your SSH server.         </td>
      </tr>
      <tr>
         <td>SSH Key Alias         </td>
         <td>Select an
SSH Key Alias
from the drop-down list, for example,
<code>admind</code>.         </td>
      </tr>
      <tr>
         <td>Client Certificate         </td>
         <td><p>This drop-down list presents the options to define support for certificate use for SSH authentication. Possible values are:</p>
<ul>
<li><code>Disabled</code> – no certificate authentication is required</li>
<li><code>Required</code> – the client must authenticate using a certificate</li>
<li><code>Optional</code> – the client can authenticate either using a certificate or a password</li>
</ul>         </td>
      </tr>
      <tr>
         <td>Client Password         </td>
         <td><p>When <strong>Client Certificate</strong> is set to <code>Required</code>, you can also specify the authentication methods that the SSH server offers to the SSH client:</p>
<ul>
<li><code>Default</code> – the server sends the authentication methods set in <strong>Authentication &gt; Login Settings &gt; End-user login options</strong></li>
<li><code>Disabled</code> – the server sends only "publickey"</li>
</ul>         </td>
      </tr>
      <tr>
         <td>Key Exchange Algorithms         </td>
         <td><p>Enter the Diffie-Hellman exchange hashing algorithms, for example: <code>diffie-hellman-group14-sha1,diffie-hellman-group-exchange-sha256</code>.</p>         </td>
      </tr>
      <tr>
         <td><span id="FIPS_KEX"></span>FIPS Exchange Algorithms         </td>
         <td><p>Specify the KEX algorithms to be used with your SSH server in FIPS mode.</p>
<p>By default, this field is populated with all FIPS compliant KEX algorithms supported by {{< SecureTransport/securetransportname  >}}. For the complete list, see <a href="../../../../c_st_fipstransfermode/r_st_required_ciphers_cipher_suites" class="MCXref xref">Advertised ciphers and cipher suites</a>.</p>
<p>Click the "down arrow" icon on the right to access a drop-down menu with options to select and deselect all items, reset to defaults, and reload the previously saved selection.</p>
<p>For the default SSH server, the list of allowed KEX algorithms in FIPS mode is determined by the <code>Ssh.FIPS.KeyExchangeAlgorithms</code> configuration option.</p>         </td>
      </tr>
      <tr>
         <td>Minimum key size for Diffie-Hellman exchange algorithms group:         </td>
         <td>Enter the minimum exchange key size in bits: <code>128</code> bit is the minimum (least secure) and <code>4096</code> is the maximum (most secure).         </td>
      </tr>
      <tr>
         <td>Public Keys         </td>
         <td><p>Enter the certificate type for your public keys and signature algorithm in the following format:<br />
<code>ssh-rsa,ssh-dss,x509v3-sign-rsa,x509v3-sign-rsa-sha1</code></p>         </td>
      </tr>
      <tr>
         <td><span id="FIPS_PK"></span>FIPS Public Keys         </td>
         <td><p>Specify the public key algorithms to be used with your SSH server in FIPS mode.</p>
<p>By default, this field is populated with all FIPS compliant public keys supported by {{< SecureTransport/securetransportname  >}}. For the complete list, see <a href="../../../../c_st_fipstransfermode/r_st_required_ciphers_cipher_suites" class="MCXref xref">Advertised ciphers and cipher suites</a>.</p>
<p>Click the "down arrow" icon on the right to access a drop-down menu with options to select and deselect all items, reset to defaults, and reload the previously saved selection.</p>
<p>For the default SSH server, the list of allowed public key algorithms in FIPS mode is determined by the <code>Ssh.FIPS.PublicKeys</code> configuration option.</p>         </td>
      </tr>
      <tr>
         <td>MAC Algorithms         </td>
         <td>Enter the MAC algorithm that warrants the integrity of the transfer using your current SSH server.         </td>
      </tr>
      <tr>
         <td><span id="FIPS_MAC"></span>FIPS MAC Algorithms         </td>
         <td><p>Specify the MAC algorithms to be used with your SSH server in FIPS mode.</p>
<p>By default, this field is populated with all FIPS compliant MACs supported by {{< SecureTransport/securetransportname  >}}. For the complete list, see <a href="../../../../c_st_fipstransfermode/r_st_required_ciphers_cipher_suites" class="MCXref xref">Advertised ciphers and cipher suites</a>.</p>
<p>Click the "down arrow" icon on the right to access a drop-down menu with options to select and deselect all items, reset to defaults, and reload the previously saved selection.</p>
<p>For the default SSH server, the list of allowed MAC algorithms in FIPS mode is determined by the <code>Ssh.FIPS.AllowedMacs</code> configuration option.</p>         </td>
      </tr>
      <tr>
         <td>Enabled Ciphers         </td>
         <td><p>Enter the cipher suites to be used with your SSH server.</p>
<p>For more information on Cipher suites, refer to the {{< SecureTransport/componentshortname  >}} <em></em> {{< SecureTransport/releasenumber  >}} <em>Security guide</em></p>         </td>
      </tr>
      <tr>
         <td><span id="FIPS_ciphers"></span>Enabled FIPS Ciphers         </td>
         <td><p>Specify the ciphers to be used with your SSH server in FIPS mode.</p>
<p>By default, this field is populated with all FIPS compliant ciphers supported by {{< SecureTransport/securetransportname  >}}. For the complete list, see <a href="../../../../c_st_fipstransfermode/r_st_required_ciphers_cipher_suites" class="MCXref xref">Advertised ciphers and cipher suites</a>.</p>
<p>Click the "down arrow" icon on the right to access a drop-down menu with options to select and deselect all items, reset to defaults, and reload the previously saved selection.</p>
<p>For the default SSH server, the list of allowed public key algorithms in FIPS mode is determined by the <code>Ssh.FIPS.Ciphers</code> configuration option.</p>         </td>
      </tr>
   </tbody>
</table>

Once you are finished entering the parameters of your SSH server, click **Save** to create it; or **Cancel** to discard all changes and return to the *Server Control* page.

<span id="Start"></span>

## Start and stop an SSH server

You can easily start and stop your SSH server.

-   Start your server by clicking the "play" icon: ![](/Images/SecureTransport/play-icon.png)  
    A box with a success message pops up on your screen and your server status changes to *Running*.
-   To stop your server, click the "stop" icon. ![](/Images/SecureTransport/stop-icon.png)  
    A box with a success message pops up on your screen and your server status changes to *Stopped*.

You can only start the SSH daemon once the Ssh Default server is operating (enabled). Stopping the daemon will stop all underlying started servers. During daemon start, only the enabled servers will be started. In case of SSH, an "enabled server" means that you have at least selected either option: **Enable Secure File Transfer Protocol (SFTP)** or **Enable Secure Copy (SCP)**.

<span id="Edit"></span>

## Edit SSH server settings

You can change any of the SSH server property values. Note that you can change the server name only when the server is stopped. To update an SSH server, click the corresponding "gear" icon: ![](/Images/SecureTransport/gearwheel-icon.png)

A new modal box with the SSH settings pops up. Add your changes and click **Save** to apply your changes; or **Cancel** to discard them.

<span id="Delete"></span>

## Delete an SSH server

> **Note:**
>
> You cannot delete or change the name of the "Ssh Default" server from the SecureTransport Administration Tool.

You can only delete a server once it is stopped. You cannot delete a server in *Running* status.

To delete a server, locate it on the *Server Control* page, make sure it is stopped and click the corresponding "trashcan" icon: ![](/Images/SecureTransport/trashcan-icon.png)

[Back to Top](#)
