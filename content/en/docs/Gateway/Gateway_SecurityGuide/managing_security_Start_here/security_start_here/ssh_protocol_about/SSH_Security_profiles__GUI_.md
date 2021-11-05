{
    "title": "Managing SSH Security Profiles",
    "linkTitle": "Managing SSH Security Profiles",
    "weight": "220"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Security

An SSH Security Profile contains all security configuration elements used to establish an SSH connection.

To import an SSH Profile, use the <span class="code" style="font-weight: bold;">[secadm import\_sshprof](../managing_ssh_security_profiles_cli#secadm_import_sshprof)</span> online command.

<span id="Defining_SSH_Profiles"></span>

## Defining SSH Security Profiles

To add a new SSH Security Profile to the profile database:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:  
    **Security Management > Transfer Security Management > Security Profile**  
     
2.  Right-click the <span style="font-weight: bold;">SSH Profile</span> sub-node, and then select <span style="font-weight: bold;">New</span> from the context menu.  
    Gateway displays the <span style="font-style: italic;">New SSH Profile</span> window.  
     
3.  Complete the fields of the following tabs as described below:
    -   [General](#SSH_Profile_General_tab)
    -   [Authentication](#SSH_Profile_Authentication_tab)
    -   [PassPort PS](#PassPort_tab)

<span id="SSH_Profile_General_tab"></span>

### SSH Profile: General tab

The <span style="font-weight: bold;">General</span> tab contains the parameters for:

-   Key exchange algorithms
-   Encryption algorithms
-   MAC algorithms
-   Public key algorithms

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">Field</span></p>         </td>
         <td><p>Description</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Name</span></p>         </td>
         <td><p>Enter a unique name for the SSH Profile.<br />
Maximum: 31 alphanumeric characters.</p>
<p>The Profile is referenced with this name in the Remote Site, the Network Profile, and in log messages.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Profile type</span></p>         </td>
         <td><p>This option limits the use of a Profile to incoming or outgoing calls.</p>
<p>From the drop-down list, select CLIENT or SERVER.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Enable</span></p>         </td>
         <td><p>Check this option to enable the SSH Profile.</p>
<p>A deactivated Profile cannot be used and any operation calling it fails (except for activation).</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Key exchange algorithms</span></p>         </td>
         <td><p>Click to access list of available key exchange algorithms.</p>
<p>This parameter is negotiated between the client and the server.</p>
<p>Select one or both of the following:</p>
<ul>
<li>DH_GROUP1_SHA1 <strong>(**)</strong></li>
<li>DH_GROUP_EXCHANGE_SHA1 <strong>(*) (**)</strong></li>
<li><p><strong>DH_GROUP_EXCHANGE_SHA256 (recommended)</strong></p></li>
<li><p>DH_GROUP14_SHA1 <strong>(**)</strong></p></li>
<li><p>ECDH_SHA2_NISTP256 <strong>(*)</strong></p></li>
<li><p>ECDH_SHA2_NISTP384 <strong>(*)</strong></p></li>
<li><p>ECDH_SHA2_NISTP521 <strong>(*)</strong></p></li>
<li><p>CURVE25519 <strong>(*)</strong></p></li>
</ul>
<p><span style="font-weight: bold;">(*) </span><span style="font-weight: normal;">These cipher suites</span><span style="font-weight: bold;"> cannot </span><span style="font-weight: normal;">be used with</span><span style="font-weight: bold;"> Secure Relay </span><span style="font-weight: normal;">if you use</span><span style="font-weight: bold;"> SSH termination in the DMZ.</span></p>
<p>(**) SHA1 <span style="font-weight: normal;">is a weak key exchange algorithm</span> (not recommended)</p>
<strong>Selection order :</strong> The default Key Exchange Algorithm selection order is the first Key Exchange Algorithm in common, using the client preferred order. To change this behavior and select Key Exchange Algorithm in server preferred order, please use the global static setting [ssh]ssh_cs_server_order:
<ul>
<li><p><strong>0</strong> (default value): client preferred order (the Key Exchange Algorithm order in the Client message)</p></li>
<li><p><strong>1</strong> server preferred order, the Key Exchange Algorithm order in the SSH server profile</p></li>
</ul>
<p>This parameter also affects the order for the Encryption algorithm, Mac algorithm and Public Key algorithm.</p>
<p><strong>Requirement</strong>: this change of algorithms order requires a Client version of at least Gateway 6.16.1-SP9 or Gateway 6.17.3-SP5.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Encryption algorithms</span></p>         </td>
         <td><p>Click to access the list of available encryption algorithms.</p>
<p>This parameter is negotiated between the client and the server.</p>
<p>Select one or more of the following:</p>
<ul>
<li>NONE</li>
<li>AES128_CBC</li>
<li>3DES_CBC</li>
<li>AES256_CBC</li>
<li><p>AES_128CTR</p></li>
<li>AES_256CTR</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">MAC algorithms</span></p>         </td>
         <td><p>Click to access the list of available MAC algorithms.</p>
<p>This parameter is negotiated between the client and the server.</p>
<p>Select one or more of the following:</p>
<ul>
<li>NONE</li>
<li>HMAC-SHA1 <strong>(**)</strong></li>
<li>HMAC-MD5</li>
<li>HMAC-SHA1-96 <strong>(**)</strong></li>
<li>HMAC-MD5-96</li>
<li><p>HMAC_SHA256</p></li>
</ul>
<p><strong>(**)</strong> <strong>SHA1</strong> is a weak key exchange algorithm (<strong>not recommended</strong>)</p>
<blockquote>
<p><strong>Note:</strong></p>
<p>Restrictions apply to this list in FIPS mode. For more details see Using FIPS.</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Public key algorithms</span></p>         </td>
         <td><p>Click to access the list of available public key algorithms.</p>
<p>The server uses this algorithm to authenticate itself to the client. The client only uses it if the negotiated Authentication method is public key (refer to <span style="font-weight: bold;">Client authentication methods</span>).</p>
<p>This parameter is negotiated between the client and the server.</p>
<p>Select one or more of the following:</p>
<ul>
<li>SSH-DSS</li>
<li>SSH-RSA</li>
<li>X509V3-SIGN-RSA (*) (see below)</li>
<li><p>ECDSA_NISTP256</p></li>
<li><p>ECDSA_NISTP384</p></li>
<li><p>ECDSA_NISTP521</p></li>
<li>ED25519 (**)</li>
</ul>
<p>(*) This key algorithm cannot be used with Secure Relay if you use SSH termination in the DMZ.</p>
<p>(**) This key algorithm cannot be used with Secure Relay if you use SSH termination in the DMZ, nor with Passport PS as key repository</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Client authentication methods</span></p>         </td>
         <td><p>This option defines the client authentication method(s).</p>
<p>In server mode, the client must authenticate itself by one of the methods defined.</p>
<p>In client mode, authentication occurs as requested by the server, on condition that the requested method is available.</p>
<p>From the drop-down list, select one of the following:</p>
<ul>
<li>Anonymous</li>
<li>Password</li>
<li>Public key</li>
<li>Password or Public key</li>
<li><p>Password and Public key</p></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span id="key_renegotiation"></span>Key renegotiation</p>
<p>Specify the time and data volume limits for <a href="../#ssh_renegotiation">SSH renegotiation</a>. Gateway initiates a key renegotiation when either of these two limits is reached.</p>
<p>Notes:</p>
<ul>
<li>The quantities in MB correspond to SI recommendations: 1 MB = 1 000 000 bytes and 1 GB = 1000 MB.</li>
<li>The default values correspond to the maximum recommended limits defined by the RFC.</li>
<li>The parameters are valid for both the server and the client.</li>
<li>Even if these parameters are set to 0, Gateway responds to Key renegotiation requests.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Minutes before New Keys</p>         </td>
         <td><p>Specify the time limit for SSH renegotiation.</p>
<p>Value between 0 and 1440 (24 hours). 0 = No limit. Default: 60 (1 hour).</p>         </td>
      </tr>
      <tr>
         <td><p>MB before New Keys</p>         </td>
         <td><p>Specify the data volume limit for SSH renegotiation.</p>
<p>Value between 0 and 2000 (2 GB). 0 = No limit. Default: 1000 (1 GB).</p>         </td>
      </tr>
      <tr>
         <td><strong>GEX no compatibility mode</strong>         </td>
         <td><p>The type of request to use in the key exchange, when Gateway is SSH client and one of the DH group exchange algorithms is selected:</p>
<ul>
<li>checked: use SSH2_MSG_KEX_DH_GEX_REQUEST</li>
<li>unchecked (default): use SSH2_MSG_KEX_DH_GEX_REQUEST_OLD</li>
</ul>
<blockquote>
<p><strong>Note:</strong></p>
<p>most SSH servers (Gateway included) accept both types of requests for compatibility reasons. So using the default should be OK. But some implementers (such as OpenSSH 6.9 and newer) completely removed the OLD version of the request.</p>
</blockquote>
<blockquote>
<p><strong>Note:</strong></p>
<p>this setting does not impact the SSH with XSR security termination case</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>Exit scheduling</p>         </td>
         <td><p>Check this option to indicate that the Security server must schedule user exits when this Profile is used (the configuration file parameter <span class="code">exit_scheduling</span> must also be set to Yes).</p>         </td>
      </tr>
      <tr>
         <td><p>Data compression</p>         </td>
         <td><p>Check this option to select SSH data compression.</p>
<p>When this option is selected, the SSH parameter<span class="code"> compression_algos = ZLIB NONE</span>. Otherwise,<span class="code"> compression_algos = NONE</span>.</p>
<p>When ZLIB is negotiated between partners (available on both sides), data is compressed in transfers. If not, no data is compressed.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="SSH_Profile_Authentication_tab"></span>

### SSH Profile: Authentication tab

The fields on this tab are only available if you select one or more Public key algorithms on the <span style="font-weight: bold;">General</span> tab. You can complete the <span style="font-weight: bold;">Local authentication</span> fields in both the SFTP Sites and SSH Profiles. However, it is highly recommended that you complete these fields in the:

-   SSH Profile in <span style="font-style: italic;">server mode</span>
-   Remote Site object in <span style="font-style: italic;">client mode</span>

In addition, the fields in the <span style="font-weight: bold;">Remote authentication</span> section are only available if you set the <span style="font-weight: bold;">Client authentication method</span> to include Public key.

Also refer to [SSH authentication](../ssh_authentication).

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>Field</p>         </td>
         <td><p>Description</p>         </td>
      </tr>
      <tr>
         <td><p>Local authentication</p>
<p>This section is used for local authentication to the partner. The authentication mechanism will use either the private key alias or the certificate alias, depending on the public key algorithm negotiated.</p>         </td>
      </tr>
      <tr>
         <td><p>Private key alias</p>         </td>
         <td><p>Enter the alias of your private key.<br />
Maximum: 31 alphanumeric characters.</p>
<p>Alternatively, select a private key alias from the drop-down list.</p>
<p>You must ensure that the algorithms provided in the list of <span style="font-weight: bold;">Public key algorithms</span> of the SSH Profile are compatible with the key that you specify here.</p>
<p>Gateway provides the public part of the key to the partner if the public key algorithm negotiated is SSH_DSS, SSH_RSA, ECDSA_NISTP256, ECDSA_NISTP384 or ECDSA_NISTP521.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Certificate alias</span></p>         </td>
         <td><p>Enter your certificate alias.<br />
Maximum: 31 alphanumeric characters.</p>
<p>Alternatively, select a certificate alias from the drop-down list.</p>
<p>Gateway uses this certificate if the public key algorithm negotiated is X509V3_SIGN_RSA.</p>
<p>If you do not enter a certificate name, you must not include the algorithm X509V3_SIGN_RSA in the list of <span style="font-weight: bold;">Public key algorithms</span> of the SSH Profile.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Remote authentication</span></p>         </td>
      </tr>
      <tr>
         <td><p><span id="Trust_hosted_public_keys"></span>Trust hosted public keys</p>         </td>
         <td><p>The term <span style="font-weight: bold;">hosted</span> applies to a public key (or certificate) hosted in the Gateway database. The origin (owner of the associated private key) is known and is authorized to connect via SSH.</p>
<p>Check this option to accept authentication of a partner if any public key (or certificate) belonging to the partner is already present in the Gateway database in the state ENABLED.</p>
<p>Refer to <a href="../managing_keys_and_certificates_in_ssh#Trusting_hosted_keys">Trusting hosted keys</a>.</p>         </td>
      </tr>
      <tr>
         <td><p><span id="Automatic_import_of_partner_keys"></span>Automatic import of partner keys</p>         </td>
         <td><p>Check this option to allow the automatic import of unknown public keys presented by partners that are authenticating themselves for the first time (or that have changed keys).</p>
<p>Before any key import operation, Gateway checks (with the hash) that the key does not already exist in the database.</p>
<p>Refer to <a href="../managing_keys_and_certificates_in_ssh#Importing_key_pairs_automatically">Importing key pairs automatically</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>Remote certificate filter</p>
<p>The following parameters are used to check the authenticity of a partner. Complete these fields if the public key algorithm negotiated is a certificate algorithm.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Issuer certificate alias</span></p>         </td>
         <td><p>From the drop-down list, select the issuer (CA) certificate alias to use to authenticate the partner certificate.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Subject name pattern</span></p>         </td>
         <td><p>Enter the subject distinguished name pattern.<br />
Maximum: 512 alphanumeric characters.<br />
You can use wildcard characters (* and ?) to filter accepted certificates.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Issuer name pattern</span></p>         </td>
         <td><p>Enter the issuer distinguished name pattern.<br />
Maximum: 512 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Trust hosted certificates only</span></p>         </td>
         <td><p>Similar to <span style="font-weight: bold;">Trust hosted public keys</span>.</p>
<p>Refer to <a href="../ssh_authentication">SSH authentication</a>.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Automatic import of partner certificates, depending on SSH Profile and Site filters</span></p>         </td>
         <td><p>Similar to <span style="font-weight: bold;">Automatic import of partner keys</span>.</p>
<p>Refer to <a href="../ssh_authentication">SSH authentication</a>.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="PassPort_tab"></span>

### SSH Profile: PassPort PS tab

Enter values in the fields of the <span style="font-weight: bold;">PassPort PS</span> tab if you are using PassPort security functions for connections with partners defined in [PassPort PS](../../../../../gateway_userguide/connectors_about/passport_pm_connector/passport_ps_connector).

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>Field</p>         </td>
         <td><p>Description</p>         </td>
      </tr>
      <tr>
         <td><p>Local entity</p>         </td>
      </tr>
      <tr>
         <td><p>Name</p>         </td>
         <td><p>Enter the local entity name for access to the PassPort PS server.</p>         </td>
      </tr>
      <tr>
         <td><strong>Set password</strong>         </td>
         <td>This button opens a dialog box, where you enter the password associated to the entity name.         </td>
      </tr>
      <tr>
         <td><p>Confirmation</p>         </td>
         <td><p>Confirm the password.</p>         </td>
      </tr>
      <tr>
         <td><strong>Object Type</strong>         </td>
         <td><p>Passport PS object type of the entity. Can be one of the following:</p>
<ul>
<li><em>Passport PS entity</em></li>
<li><em>Passport PS certificate</em></li>
</ul>
<p>For profiles used with the <span class="code">XSR </span>termination, the only valid selection is <em>Passport PS entity.</em></p>         </td>
      </tr>
      <tr>
         <td><p>Partner entity</p>         </td>
      </tr>
      <tr>
         <td><p>Name</p>         </td>
         <td><p>Identity of the PassPort partner as provided by the PassPort PS server.</p>         </td>
      </tr>
      <tr>
         <td><strong>Object Type</strong>         </td>
         <td><p>Passport PS object type of the entity. Can be one of the following:</p>
<ul>
<li><em>Passport PS entity</em></li>
<li><em>Passport PS certificate</em></li>
</ul>
<p>For profiles used with the <span class="code">XSR </span>termination, the only valid selection is <em>Passport PS entity.</em></p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[SSH protocol](../)

[Managing Keys and Certificates in SSH](../managing_keys_and_certificates_in_ssh)

[Using SSH](../using_ssh)

[SSH authentication](../ssh_authentication)

[Managing SSH Security Profiles (command line)](../managing_ssh_security_profiles_cli)

[SSH user exits](../../../../../gateway_userguide/customizing_gw_about/user_exits_about/user_exits_external/user_exits_ssh)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
