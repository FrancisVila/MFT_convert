{
    "title": "Manage the SSH server",
    "linkTitle": "Manage the SSH server",
    "weight": "160"
}In this topic you will learn how to:

-   [Add an SSH server](#add)
-   [Start and stop an SSH server](#start)
-   [Edit SSH server settings](#edit)
-   [Delete an SSH server](#delete)

## <span id="Add"></span>Add an SSH server

To add an SSH server, go to the *Server Control* page and on the *SSH Servers* panel, click **Actions &gt; Add Server**.

The following table presents all parameters and expected values associated with your new SSH server.

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
         <td>
            <p>Select to enable  <a href="../../../../c_st_fipstransfermode">FIPS transfer mode</a> for SSH connections. By selecting this option, the following fields become editable:</p>
            <ul>
               <li><a href="#fips_kex">FIPS Exchange Algorithms</a>
               </li>
               <li><a href="#fips_pk">FIPS Public Keys</a>
               </li>
               <li><a href="#fips_mac">FIPS MAC Algorithms</a>
               </li>
               <li><a href="#fips_ciphers">Enabled FIPS Ciphers</a>
               </li>
            </ul>
         </td>
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
         <td>Client Certificate          </td>
         <td>
            <p>This drop-down list presents the options to define support for certificate use for SSH authentication. Possible values are:</p>
            <ul>
               <li><code>Disabled</code> – no certificate authentication is required               </li>
               <li><code>Required</code> – the client must authenticate using a certificate                </li>
               <li><code>Optional</code> – the client can authenticate either using a certificate or a password               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>Client Password         </td>
         <td>
            <p>When <b>Client Certificate</b> is set to <code>Required</code>, you can also specify the  authentication methods that the SSH server offers to the SSH client:</p>
            <ul>
               <li><code>Default</code> – the server sends the authentication methods set in <b>Authentication &gt; Login Settings &gt; End-user login options</b>               </li>
               <li><code>Disabled</code> – the server sends only "publickey"                </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>Key Exchange Algorithms         </td>
         <td>
            <p>Enter the Diffie-Hellman exchange hashing algorithms, for example: <code>diffie-hellman-group14-sha1,diffie-hellman-group-exchange-sha256</code>.</p>
         </td>
      </tr>
      <tr>
         <td><a name="FIPS_KEX"></a>FIPS Exchange Algorithms         </td>
         <td>
            <p>Specify the KEX algorithms to be used with your SSH server in FIPS mode. </p>
            <p>By default, this field is populated with all FIPS  compliant KEX algorithms supported by <span>SecureTransport</span>. For the complete list, see <a href="../../../../c_st_fipstransfermode/r_st_required_ciphers_cipher_suites">Advertised ciphers and cipher suites</a>.</p>
            <p>Click the "down arrow" icon on the right to access a drop-down menu with options to select and deselect all items, reset to defaults, and reload  the previously saved selection.</p>
            <p>For the default SSH server, the list of allowed KEX algorithms  in FIPS mode is determined by the <code>Ssh.FIPS.KeyExchangeAlgorithms</code> configuration option.</p>
         </td>
      </tr>
      <tr>
         <td>
Minimum key size for Diffie-Hellman exchange algorithms group:
         </td>
         <td>Enter the minimum exchange key size in bits: <code>128</code> bit is the minimum (least secure) and <code>4096</code> is the maximum (most secure).         </td>
      </tr>
      <tr>
         <td>Public Keys         </td>
         <td>
            <p>Enter the certificate type for your public keys and signature algorithm in the following format:<br/><code>ssh-rsa,ssh-dss,x509v3-sign-rsa,x509v3-sign-rsa-sha1</code></p>
         </td>
      </tr>
      <tr>
         <td><a name="FIPS_PK"></a>FIPS Public Keys         </td>
         <td>
            <p>Specify the public key algorithms  to be used with your SSH server in FIPS mode. </p>
            <p>By default, this field is populated with all FIPS  compliant public keys supported by <span>SecureTransport</span>. For the complete list, see <a href="../../../../c_st_fipstransfermode/r_st_required_ciphers_cipher_suites">Advertised ciphers and cipher suites</a>.</p>
            <p>Click the "down arrow" icon on the right to access a drop-down menu with options to select and deselect all items, reset to defaults, and reload  the previously saved selection.</p>
            <p>For the default SSH server, the list of allowed public key algorithms  in FIPS mode is determined by the <code>Ssh.FIPS.PublicKeys</code> configuration option.</p>
         </td>
      </tr>
      <tr>
         <td>MAC Algorithms         </td>
         <td>Enter the MAC algorithm that warrants the integrity of the transfer using your current SSH server.         </td>
      </tr>
      <tr>
         <td><a name="FIPS_MAC"></a>FIPS MAC Algorithms         </td>
         <td>
            <p>Specify the MAC algorithms to be used with your SSH server in FIPS mode. </p>
            <p>By default, this field is populated with all FIPS  compliant MACs supported by <span>SecureTransport</span>. For the complete list, see <a href="../../../../c_st_fipstransfermode/r_st_required_ciphers_cipher_suites">Advertised ciphers and cipher suites</a>.</p>
            <p>Click the "down arrow" icon on the right to access a drop-down menu with options to select and deselect all items, reset to defaults, and reload  the previously saved selection.</p>
            <p>For the default SSH server, the list of allowed MAC algorithms in FIPS mode is determined by the <code>Ssh.FIPS.AllowedMacs</code> configuration option.</p>
         </td>
      </tr>
      <tr>
         <td>Enabled Ciphers         </td>
         <td>
            <p>Enter the cipher suites to be used with your SSH server. </p>
            <p>For more information on Cipher suites, refer to the <span>SecureTransport</span><i> </i><span>5.5</span><i> Security guide</i></p>
         </td>
      </tr>
      <tr>
         <td><a name="FIPS_ciphers"></a>Enabled FIPS Ciphers         </td>
         <td>
            <p>Specify the ciphers to be used with your SSH server in FIPS mode. </p>
            <p>By default, this field is populated with all FIPS  compliant ciphers supported by <span>SecureTransport</span>. For the complete list, see <a href="../../../../c_st_fipstransfermode/r_st_required_ciphers_cipher_suites">Advertised ciphers and cipher suites</a>.</p>
            <p>Click the "down arrow" icon on the right to access a drop-down menu with options to select and deselect all items, reset to defaults, and reload  the previously saved selection.</p>
            <p>For the default SSH server, the list of allowed public key algorithms  in FIPS mode is determined by the <code>Ssh.FIPS.Ciphers</code> configuration option.</p>
         </td>
      </tr>
   </tbody>
</table>

Once you are finished entering the parameters of your SSH server, click **Save** to create it; or **Cancel** to discard all changes and return to the *Server Control* page.

## <span id="Start"></span>Start and stop an SSH server

You can easily start and stop your SSH server.

-   Start your server by clicking the "play" icon: ![](trashcan-icon.png)  
    A box with a success message pops up on your screen and your server status changes to *Running*.
-   To stop your server, click the "stop" icon. ![](trashcan-icon.png)  
    A box with a success message pops up on your screen and your server status changes to *Stopped*.

You can only start the SSH daemon once the Ssh Default server is operating (enabled). Stopping the daemon will stop all underlying started servers. During daemon start, only the enabled servers will be started. In case of SSH, an "enabled server" means that you have at least selected either option: **Enable Secure File Transfer Protocol (SFTP)** or **Enable Secure Copy (SCP)**.

## <span id="Edit"></span>Edit SSH server settings

You can change any of the SSH server property values. Note that you can change the server name only when the server is stopped. To update an SSH server, click the corresponding "gear" icon: ![](trashcan-icon.png)

A new modal box with the SSH settings pops up. Add your changes and click **Save** to apply your changes; or **Cancel** to discard them.

## <span id="Delete"></span>Delete an SSH server

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">You cannot delete or change the name of the "Ssh Default" server from the <span>SecureTransport</span> Administration Tool.         </td>
      </tr>
</table>

You can only delete a server once it is stopped. You cannot delete a server in *Running* status.

To delete a server, locate it on the *Server Control* page, make sure it is stopped and click the corresponding "trashcan" icon: ![](trashcan-icon.png)

[Back to Top](#)