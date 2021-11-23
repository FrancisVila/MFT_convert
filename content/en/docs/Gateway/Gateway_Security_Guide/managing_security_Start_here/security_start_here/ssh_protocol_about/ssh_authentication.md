{
    "title": "SSH authentication",
    "linkTitle": "SSH authentication",
    "weight": "230"
}{{< Gateway/componentlongname  >}}: Managing Security

This topic describes the server and client authentication processes in chronological order.

[Server authentication](#Server_authentication)

[Client verification](#Client_verification)

[Client authentication](#Client_authentication)

[Server verification](#Server_verification)

<span id="Server_authentication"></span>

## Server authentication

Authentication is the primary function of the SSH protocol. Although the client always initiates the connection, the server authentication occurs first. The server uses an RSA, ECDSA or DSS key or an X.509 certificate for its authentication.

**When Gateway is server:**

Gateway uses a parameter from the Authentication Alias section of the SSH Profile selected during the incoming connection. The two options are <span style="font-weight: bold;">Private key alias</span> and <span style="font-weight: bold;">Certificate alias</span>.

\[AuthenticationAlias\]

private\_key\_alias = "KEY\_SRV01\_PRV"

certificate\_alias = ""

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>If the negotiated public key algorithm is a...</p>         </td>
         <td><p>Then...</p>         </td>
      </tr>
      <tr>
         <td><p>Key algorithm</p>
<ul>
<li>SSH_DSS</li>
<li>SSH_RSA</li>
<li>ECDSA_NISTP256</li>
<li>ECDSA_NISTP384</li>
<li>ECDSA_NISTP521</li>
</ul>         </td>
         <td><p>Gateway uses a private key defined in the <span style="font-weight: bold;">Private key alias</span> field to authenticate itself.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Note:</span> At least one of the available private keys must have the same algorithm as the key negotiated. Therefore any key algorithm provided in the list of <span style="font-weight: bold;">public key algorithms</span> in the SSH Profile must have a compatible <span style="font-weight: bold;">Private key alias</span>. Otherwise, the Security server will cancel the connection and return an error.</p>         </td>
      </tr>
      <tr>
         <td><p>Certificate algorithm</p>
<ul>
<li>X509V3_SIGN_RSA</li>
</ul>         </td>
         <td><p>Gateway uses the certificate indicated in the <span style="font-weight: bold;">Certificate alias</span> field.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Note:</span> If the <span style="font-weight: bold;">Certificate alias</span> is not completed, you must not include the algorithm X509V3_SIGN_RSA in the list of <span style="font-weight: bold;">public key algorithms</span> in the SSH Profile. Otherwise, the Security server will cancel the connection and return an error.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Client_verification"></span>

## Client verification

The client receives a public key (or a certificate) from the server.

<span style="font-weight: bold;">When Gateway is client:</span>

The verification is performed with the Authentication Control.

Set the following parameters in the [Remote Site SFTP tab](../../../../../gateway_userguide_(primary)/managing_partners_start_here/sites_start_here/managing_remote_sites/remote_site_sftp_tab) that represents the server:

-   Public key alias
-   Public key group
-   Subject certificate alias
-   Issuer certificate alias
-   Subject name pattern
-   Issuer name pattern

<span style="font-weight: bold;">Note:</span> You can also set the Authentication Control parameters in the SSH Profile used for the connection. However the Site object parameters have priority over the same parameters contained in the SSH Profile. The SSH Profile only supplies the fields that are not completed in the Site.

Set the following parameters (used in both client and server mode for partner verification) in the SSH profile:

-   [Trust hosted public keys](../ssh_security_profiles__gui_#Trust_hosted_public_keys)
-   [Automatic import of partner keys](../ssh_security_profiles__gui_#Automatic_import_of_partner_keys)

#### In client mode: Verification procedure

If you are using keys rather than certificates, Gateway handles processing in two ways:

<table>
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">Case 1:</span> You previously specified the <span style="font-weight: bold;">Public key alias</span> in the Authentication Control of the Remote Site.</p>         </td>
      </tr>
      <tr>
         <td><p>Gateway receives a key from a Remote Server and compares the received key with the key (defined by the <span style="font-weight: bold;">Public key alias</span>) that you specified in the Remote Site (a hosted public key).</p>
<ul>
<li>If the keys match, Gateway accepts the connection.</li>
<li>Otherwise, it returns an error.</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

<table>
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">Case 2:</span> You did not previously specify a <span style="font-weight: bold;">Public key alias</span> in the Authentication Control of the Remote Site.</p>         </td>
      </tr>
      <tr>
         <td><p>Gateway receives a key from a Remote Server and checks the setting of <span style="font-weight: bold;">trustHostedPublicKeys</span>.</p>
<ul>
<li>If <span style="font-weight: bold;">trustHostedPublicKeys</span> is set to yes, Gateway searches for a hosted key equivalent to the one it is receiving, and accepts the connection if they match. Otherwise it disconnects.</li>
<li>If <span style="font-weight: bold;">trustHostedPublicKeys</span> is set to no, Gateway disconnects.</li>
</ul>
<p>Before Gateway disconnects, it checks the setting of <span style="font-weight: bold;"><a href="../ssh_security_profiles__gui_#Automatic_import_of_partner_keys">Automatic import of partner keys</a></span> and imports the key if this parameter is enabled and the same key is not already in the database.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Client_authentication"></span>

## Client authentication

If the client's server verification is successful, it is the client’s turn to authenticate itself.

<span style="font-weight: bold;">When Gateway is client:</span>

The client always sends a User name to the server, regardless of the Authentication method defined. The server defines the Authentication method, previously specified in the General section of the SSH Profile.

-   <span style="font-weight: bold;">User to send</span> (<span class="code">-login\_ident</span>) in the SFTP Remote Site

In addition to the user name, the client also sends:

-   <span style="font-weight: bold;">Password to send</span> (<span class="code">-login\_password</span>) of the SFTP Site, if the server requests the PASSWORD method
-   <span style="font-weight: bold;">Key</span> (the public part of the private key specified in <span style="font-weight: bold;">Private key alias</span>) if the server requests the PUBLIC\_KEY method

Use the <span style="font-weight: bold;">Authentication Alias</span> of the SFTP Site (or of the SSH Profile if it is not completed in the SFTP Site).

\[AuthenticationAlias\]

private\_key\_alias = "KEY\_CLI01\_PRV"

certificate\_alias = ""

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>If the negotiated public key algorithm is a...</p>         </td>
         <td><p>Then...</p>         </td>
      </tr>
      <tr>
         <td><p>Key algorithm</p>
<ul>
<li>SSH_DSS</li>
<li>SSH_RSA</li>
<li>ECDSA_NISTP256</li>
<li>ECDSA_NISTP384</li>
<li>ECDSA_NISTP521</li>
</ul>         </td>
         <td><p>Gateway uses a private key defined in the <span style="font-weight: bold;">Private key alias</span> field to authenticate itself.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Note:</span> At least one of the available private keys must have the same algorithm as the key negotiated. Therefore any key algorithm provided in the list of <span style="font-weight: bold;">public key algorithms</span> in the SSH Profile must have a compatible <span style="font-weight: bold;">Private key alias</span>. Otherwise, the Security server will cancel the connection and return an error.</p>         </td>
      </tr>
      <tr>
         <td><p>Certificate algorithm</p>
<ul>
<li>X509V3_SIGN_RSA</li>
</ul>         </td>
         <td><p>Gateway uses the certificate indicated in the <span style="font-weight: bold;">Certificate alias</span> field.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Note:</span> If the <span style="font-weight: bold;">Certificate alias</span> is not completed, you must not include the algorithm X509V3_SIGN_RSA in the list of <span style="font-weight: bold;">public key algorithms</span> in the SSH Profile. Otherwise, the Security server will cancel the connection and return an error.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Server_verification"></span>

## Server verification

The server receives a public key (or a certificate) from the client.

<span style="font-weight: bold;">When Gateway is server:</span>

The process is slightly different from when a client checks the authenticity of the server, because the Security server does not recognize the SFTP Site associated with the client. It therefore sends a login request to the supervisor to obtain from the Site the data required to authenticate the client.

The supervisor uses CGates and Template Sites to process this request, depending on the client login user name.

In return, the supervisor provides the Security server with the authentication control data found in the Site. If the user is not known or not authorized, the supervisor can also return a negative response and end the connection.

Gateway performs the verification using the Authentication Control structure from the Remote Site object representing the client (the one that the supervisor returned).

<span style="font-weight: bold;">Note:</span> Authentication Control is also available in the SSH Profile selected on connection, but not recommended since it is not partner-specific in most implementations. The SSH Profile only supplies the fields that are not completed in the Site.

Set the following parameters in the [Remote Site SFTP tab](../../../../../gateway_userguide_(primary)/managing_partners_start_here/sites_start_here/managing_remote_sites/remote_site_sftp_tab) representing the client:

-   <span style="font-weight: bold;">Username to check</span> (<span class="code">-check\_login\_ident</span>)
-   <span style="font-weight: bold;">Password to check</span> (<span class="code">-check\_login\_password</span>)
-   <span style="font-weight: bold;">Public key alias</span>
-   <span style="font-weight: bold;">Public key group</span>
-   <span style="font-weight: bold;">Subject certificate alias</span>
-   <span style="font-weight: bold;">Issuer certificate alias</span>
-   <span style="font-weight: bold;">Subject name pattern</span>
-   <span style="font-weight: bold;">Issuer name pattern</span>

The following parameters (used in both client and server mode for partner verification) are configured in the SSH Profile:

-   [Trust hosted public keys](../ssh_security_profiles__gui_#Trust_hosted_public_keys)
-   [Automatic import of partner keys](../ssh_security_profiles__gui_#Automatic_import_of_partner_keys)

#### In server mode: Verification procedure

If you are using keys rather than certificates, Gateway handles processing in two ways:

<table>
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">Case 1:</span> You previously specified the <span style="font-weight: bold;">Public key alias</span> in the Authentication Control of the Remote Site.</p>         </td>
      </tr>
      <tr>
         <td><p>Gateway receives a key from a Remote Server and compares the received key with the key (defined in the <span style="font-weight: bold;">Public key alias</span>) that you have defined in the Remote Site (a hosted public key).</p>
<ul>
<li>If the keys match, Gateway accepts the connection.</li>
<li>Otherwise, it returns an error.</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

<table>
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">Case 2:</span> You did not previously specify a <span style="font-weight: bold;">Public key alias</span> in the Authentication Control of the Remote Site.</p>         </td>
      </tr>
      <tr>
         <td><p>Gateway receives a key from a Remote Server and checks the setting of <span style="font-weight: bold;"><a href="../ssh_security_profiles__gui_#Trust_hosted_public_keys">Trust hosted public keys</a></span>.</p>
<ul>
<li>If <span style="font-weight: bold;">Trust hosted public keys</span> is set to yes, Gateway searches for a hosted key equivalent to the one it is receiving, and accepts the connection if they match. Otherwise it disconnects.</li>
<li>If <span style="font-weight: bold;">Trust hosted public keys</span> is set to no, Gateway disconnects.</li>
</ul>
<p>Before Gateway disconnects, it checks the setting of <span style="font-weight: bold;"><a href="../ssh_security_profiles__gui_#Automatic_import_of_partner_keys">Automatic import of partner keys</a></span> and imports the key if this parameter is enabled and the same key is not already in the database.</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[SSH protocol](../)

[Managing Keys and Certificates in SSH](../managing_keys_and_certificates_in_ssh)

[Using SSH](../using_ssh)

[Managing SSH Security Profiles](../ssh_security_profiles__gui_)

[Managing SSH Security Profiles (command line)](../managing_ssh_security_profiles_cli)

[SSH user exits](../../../../../gateway_userguide_(primary)/customizing_gw_about/user_exits_about/user_exits_external/user_exits_ssh)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
