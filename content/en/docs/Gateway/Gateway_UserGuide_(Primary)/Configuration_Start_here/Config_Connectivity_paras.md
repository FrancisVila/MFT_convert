{
    "title": "Configuration: connectivity parameters",
    "linkTitle": "Connectivity parameters",
    "weight": "100"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Configuration

[Activating/deactivating protocols and connectors](#Activating_deactivating)

[Navigator server](#olh_connectivity_guiserver)

[Secure Relay](#olh_connectivity_Secure_Relay)

<span id="Activating_deactivating"></span>

## Activating/deactivating protocols and connectors

To enable a protocol or connector in Gateway, click <span style="font-weight: bold;">Activate</span>.

If you no longer want to use a protocol or connector, click <span style="font-weight: bold;">Deactivate</span> to disable it.

<span id="olh_connectivity_guiserver"></span>

## 

## Configure Passport with SecureRelay

Starting from <span class="mc-variable suite_variables.GatewayName variable">Gateway</span> version 6.16.0, the <span class="mc-variable suite_variables.SecureRelayName variable">Secure Relay</span> Router Agent no longer connects to <span class="mc-variable suite_variables.PassPortName variable">PassPort</span>, so the settings for the PKI server (used when using <span class="mc-variable suite_variables.SecureRelayName variable">Secure Relay</span> with termination) are no longer set on the Router Agent, but rather on the Master Agent.

Use the following parameters to set up the Navigator server (GUI server) for the support of remote network clients over TCP/IP

-   On Router Agent: set the PKI server type to `Generic`
-   On <span class="mc-variable suite_variables.GatewayName variable">Gateway</span>: fill the following fields using the `peluconf` command:

\[xsr\]pki\_server\_type='None'

\[xsr\]pki\_server\_host='&lt;NO VALUE SET>'

\[xsr\]pki\_server\_port='7101'

\[xsr\]pki\_server\_use\_tls='yes'

\[xsr\]pki\_server\_login\_user='&lt;NO VALUE SET>'

\[xsr\]pki\_password\_dkfile='%p\_xsr\_dir%\\pkidkfile.dat'

\[xsr\]pki\_password\_saltfile='%p\_xsr\_dir%\\pkisaltfile.dat'

\[xsr\]pki\_password\_datafile='%p\_xsr\_dir%\\pkipwd.dat'

\[xsr\]pki\_ca\_cert\_file='%p\_home\_dir%\\extras\\PassPort\\PassportCA.crt'

These are the default settings; when using <span class="mc-variable suite_variables.PassPortName variable">PassPort</span>, the type is <span class="code">PassPort</span>.

The password files should be generated using the `pelencpass `tool provided with <span class="mc-variable suite_variables.GatewayName variable">Gateway</span>.

## Connectivity &gt; Navigator server

1.  Use the following parameters to set up the Navigator server (GUI server) for the support of remote network clients over TCP/IP.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Parameter</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Listening port</p>
<p>(<span style="font-style: italic;">mandatory</span>)</p>         </td>
         <td><p>Enter the port number assigned to the Gateway Navigator server. The port number must be in decimal format and unique on the operating system.</p>
<p>Default = <span style="font-weight: bold;">6390</span></p>         </td>
      </tr>
      <tr>
         <td><p>Network interface</p>
<p>(<span style="font-style: italic;">mandatory</span>)</p>         </td>
         <td><p>Enter the local IP address in dotted format, or the local host name as defined in the HOST file.</p>         </td>
      </tr>
      <tr>
         <td><p>The following fields are optional. You can activate the Navigator server without using the TLS option.</p>         </td>
      </tr>
      <tr>
         <td><p>Use TLS</p>         </td>
         <td><p>Select this option to use TLS/SSL and then complete the following parameters.</p>
<p>TLS versions: the preferred TLS version is TLS 1.2, but Gateway Server also supports TLS 1.1 and TLS 1.0. There is no configurable option for choosing the TLS version. If an older client (Navigator or XIB) connects to Gateway using lower TLS versions, the server will fallback to the client's version (provided the connection is allowed - please see the "API version check" parameter in this table).</p>         </td>
      </tr>
      <tr>
         <td><p>X509 certificate</p>         </td>
         <td><p>Enter the name of file that contains the X.509 certificate to be used by the Navigator server. Typically, this is a file in PKCS 12 format.</p>         </td>
      </tr>
      <tr>
         <td>Password dk file         </td>
         <td>Enter the name of the file containing the derived key for decrypting the password to the X.509 certificate. This file should be one of the outputs of the <span class="code">pelencpass </span>command.         </td>
      </tr>
      <tr>
         <td>Password enc file         </td>
         <td>Enter the name of the file containing the encrypted password to the X.509 certificate. This file should be one of the outputs of the <span class="code">pelencpass </span>command.         </td>
      </tr>
      <tr>
         <td><strong>Server max</strong>         </td>
         <td>Maximum number of client connections. This includes connections from Gateway Navigator, but also from Integrator (which is using Gateway's C API to connect)         </td>
      </tr>
      <tr>
         <td><strong>API version check</strong>         </td>
         <td><p>Checks whether client &amp; server API versions match.</p>
<ul>
<li>If <em>not active</em>, the server will allow the connection, regardless of the API versions on server and client.</li>
<li>If <em>active</em> and the client version is <em>newer</em> than the server one, connection is rejected.</li>
<li>If <em>active</em>, and if the client version is <em>older</em> than the server version, and if <code>User access control</code> is other than <em>None</em>: the user's right to connect depends on per-user settings. See the <a href="#">Security Guide</a> for further information (requires login).</li>
<li>If <em>active</em>, and if the client version is <em>older</em> than the server version, and if <code>User access control</code> is equal to <em>None</em>: the connection is allowed automatically. (There can be no API version check without some form of User access control).</li>
</ul>
<p><strong>Note</strong>: when using Passport AM for authentication, to allow older API version clients to connect (i.e. XIB): add <span class="code">LOGIN_XIB </span>privilege to the user's role.</p>         </td>
      </tr>
   </tbody>
</table>

1.  Click <span style="font-weight: bold;">Activate</span> to enable the Navigator server.

<span id="olh_connectivity_Secure_Relay"></span>

## Connectivity &gt; Secure Relay

1.  Use the following parameters to set certificate, address and port information for the Master Agent and Router Agent components of Secure Relay.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Parameter</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Outgoing calls bypass Secure Relay for address mask</p>         </td>
         <td><p>For Gateway outgoing connections to local network entities.</p>
<p>Enter an alphanumeric mask number enabling local network calls to bypass Secure Relay.</p>
<p>You can enter up to 32 masks, separated by a blank space or a semi-colon.</p>
<p>You can use the following wild-card symbols:</p>
<ul>
<li><span style="font-weight: bold;">*</span> = integer between 0 and 255</li>
<li><span style="font-weight: bold;">?</span> = integer between 0 and 9</li>
</ul>
<p>Examples of legitimate mask numbers are:</p>
<ul>
<li>178.14.*.*</li>
<li>199.0.2??.*</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Master Agent</p>         </td>
      </tr>
      <tr>
         <td><p>Certificate file</p>         </td>
         <td><p>Enter the name of the security certificate for the Secure Relay Master Agent.</p>
<p>Click the browse button to help you locate a certificate on your machine.</p>
<p><strong>Note</strong>: No sample certificate is provided with Gateway. By default this parameter is empty and you need to explicitly provide a value.</p>         </td>
      </tr>
      <tr>
         <td><p>Certificate password</p>         </td>
         <td><p>Enter the password for access to the Secure Relay Master Agent certificate.</p>
<p><strong>Note:</strong> For additional security you can encrypt the password stored in the Gateway configuration file. Refer to the <em>Security guide &gt; <a href="#">Working with Secure Relay</a></em> for further information (requires login).</p>         </td>
      </tr>
      <tr>
         <td><p>CA Certificate file</p>         </td>
         <td><p>Enter the name of the CA certificate file.</p>
<p>Click the browse button to help you locate a certificate file on your machine.</p>
<p><strong>Note</strong>: No sample CA certificate is provided with Gateway. By default this parameter is empty and you need to explicitly provide a value.</p>         </td>
      </tr>
      <tr>
         <td><p>Router Agents</p>
<p>This pane lists the Router Agents that are currently configured. You can use up to eight Router Agents.</p>
<p>To update the list of Router Agents, use the <span style="font-weight: bold;">Modify</span> button:</p>         </td>
      </tr>
      <tr>
         <td><p>Modify</p>         </td>
         <td><p>Double-click a Router Agent in the list to modify the <a href="../../../gateway_securityguide/managing_security_start_here/config_secure_relay_ra_paras">Router Agent parameters</a>.</p>
<p>Click <span style="font-weight: bold;">Modify</span> to configure a new Router Agent.</p>         </td>
      </tr>
      <tr>
         <td><p>Activate</p>         </td>
         <td><p>Select a Router Agent in the list.</p>
<p>Click <span style="font-weight: bold;">Activate</span> to activate or deactivate this Router Agent.</p>         </td>
      </tr>
   </tbody>
</table>

1.  Click <span style="font-weight: bold;">Advanced...</span> to access <span style="font-style: italic;">[Secure Relay advanced options](../../../gateway_securityguide/managing_security_start_here/config_secure_relay_adv_options)</span>.
2.  Click <span style="font-weight: bold;">Activate</span> to enable Secure Relay Master Agent processes.

Related topics

[Configuration: Procedure](../config_procedure)

[Configuring protocols](../config_protocols_about/config_protocols)

[Configuring connectors](../config_connectors)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
