{
    "title": "New Remote Site: SFTP tab",
    "linkTitle": "SFTP tab",
    "weight": "280"
}{{< Gateway/componentlongname  >}}: Managing Partners

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Field</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><strong>Parameters to connect to Remote Site</strong></p>         </td>
      </tr>
      <tr>
         <td><p>User name</p>
<p>(mandatory)</p>         </td>
         <td><p>Enter the client user name to send to the Remote Site during the connection phase. This field serves to authenticate the client.<br />
Maximum: 25 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>SSH Profile</p>         </td>
         <td><p>Enter the name of the SSH profile to use for the outgoing connection. This parameter is only used in client mode. The SSH Profile that you specify must be of the type CLIENT and must be enabled.</p>         </td>
      </tr>
      <tr>
         <td><strong>Set password to send to partner</strong>         </td>
         <td><p>Opens a dialog box to enter the password to send to the Remote Site during the connection phase.<br />
Maximum: 15 alphanumeric characters.<br />
The password is only required if the server requests the PASSWORD authentication method.</p>         </td>
      </tr>
      <tr>
         <td><p>Private key alias</p>         </td>
         <td><p>Select the private key alias to use to authenticate your Site to the remote partner.</p>
<p>This field is mandatory if the server requests the PUBLIC KEY authentication method.</p>
<blockquote>
<p><strong>Note:</strong></p>
<p>Restrictions apply to this list in FIPS mode.
See the Security Guide for further information.</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td><p>Certificate alias</p>         </td>
         <td><p>Select the certificate alias to use to authenticate your Site to the partner.</p>
<blockquote>
<p><strong>Note:</strong></p>
<p>Restrictions apply to this list in FIPS mode.
See the Security Guide for further information.</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td><strong>Disable SFTPv6<br />
</strong>         </td>
         <td><ul>
<li>If <strong>checked, SFTPv6</strong> will <strong>not</strong> be negotiated (server role - not advertised, client role - not selected) nor accepted (server role, when client is starting directly with SFTPv6, Gateway server will respond with SFTPv3). Only <strong>SFTPv3</strong> will be used for this remote site.</li>
<li>If <strong>unchecked</strong>, <strong>SFTPv6</strong> is preferred whenever available</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><strong>Remote Site parameters to check</strong></p>         </td>
      </tr>
      <tr>
         <td><p>User name</p>
<p>(mandatory)</p>         </td>
         <td><p>Enter the user identifier that corresponds to the protocol identifier.<br />
Maximum: 25 alphanumeric characters.</p>
<p>In Responder mode, Gateway uses this value to check the user name that it receives from the client.</p>         </td>
      </tr>
      <tr>
         <td><strong>Set password</strong>         </td>
         <td><p>Opens a dialog box to enter the client password.<br />
Maximum: 14 characters.</p>
<p>In Responder mode, Gateway uses this value to check the user password that it receives from the client.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Remote Site authentication (Initiator and Responder mode)</strong></p>
<p>The remote client uses the values that you enter in the <em>Remote Site authentication</em> section to authenticate the server. Complete the Public key fields if the public key algorithm negotiated is a key pair algorithm.</p>
<p>The parameters that you set in the Remote Site take precedence over the same parameters set in the SSH Profile.</p>         </td>
      </tr>
      <tr>
         <td><p>Public key alias</p>         </td>
         <td><p>Select the public key alias to use to authenticate the partner.</p>
<p>When Gateway receives a key from a remote server, it compares the key with the public key alias that you specify here.</p>         </td>
      </tr>
      <tr>
         <td><p>Public key group</p>         </td>
         <td><p>Enter the public key group name.<br />
Maximum: 31 alphanumeric characters.</p>
<p>When you import a key automatically, it is associated with the group that you specify here. If you do not specify a group in this field, the key is associated with the group GDEFAULT.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Remote certificate filter</strong></p>
<p>The following parameters are used to check the authenticity of a partner. Complete these fields if the public key algorithm negotiated is a certificate algorithm.</p>         </td>
      </tr>
      <tr>
         <td><p>Subject certificate alias</p>         </td>
         <td><p>Select the certificate alias used to authenticate the partner.</p>
<p>If you select to authenticate the partner by a certificate, you do not need to complete the <strong>Public key alias</strong> and <span style="font-weight: bold;">Public key group</span> fields.</p>         </td>
      </tr>
      <tr>
         <td><p>Issuer certificate alias</p>         </td>
         <td><p>Select the issuer (CA) certificate alias to use to authenticate the partner certificate.</p>         </td>
      </tr>
      <tr>
         <td><p>Subject name pattern</p>         </td>
         <td><p>Enter the subject distinguished name pattern.<br />
You can use wildcard characters (* and ?) to filter accepted certificates.<br />
Maximum: 512 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Issuer name pattern</p>         </td>
         <td><p>Enter the issuer distinguished name pattern.<br />
Maximum: 512 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Remote PassPort PS partner entity filter</span></p>         </td>
      </tr>
      <tr>
         <td><p>Name</p>         </td>
         <td><p>When Gateway operates in server mode with a partner defined in PassPort, enter the identity of the PassPort partner.</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>Newline convention</p>         </td>
         <td><p>Set the end-of-line code, depending on the remote system type. Conversion only occurs in text mode and not in binary mode. </p>
<p>Select one of the following values:</p>
<ul>
<li><span style="font-weight: bold;">UNIX<br />
<span class="mc-variable axway_variables.Component_Short_Name variable" style="font-weight: normal;">Gateway</span></span>searches for the <strong>LF</strong> sequence to detect end-of-lines<span style="font-weight: bold;"> </span>(EOL)<span style="font-weight: bold;">.<br />
</span></li>
<li><span style="font-weight: bold;">Windows<br />
<span class="mc-variable axway_variables.Component_Short_Name variable" style="font-weight: normal;">Gateway</span></span>searches for the <span style="font-weight: bold;"><strong>CRLF</strong></span> sequence to detect EOLs<span style="font-weight: bold;"><br />
</span></li>
<li><span style="font-weight: bold;">(Empty)<br />
</span>When the line ending convention is set to Empty no line ending conversions occur. <span style="font-weight: bold;"></span></li>
</ul>
<p>Once the EOL is identified, Gateway converts the EOL from the incoming data to the native system EOL of the system Gateway is installed on (Windows:CRLF, Unix:LF).</p>
<p>UNIX: to prevent occurrences of CRLF becoming CRCRLF, Gateway verifies the character in front of each LF character it finds. If it finds a CR, it automatically replaces the whole CRLF sequence with the native EOL.</p>
<p><span style="font-weight: bold;">Note:</span> You can also set this parameter in the <strong>Transfer Request</strong>. The value set in the Transfer Request takes priority over the value set in the Remote Site.</p>
<p><strong>Known limitations:</strong></p>
<ul>
<li>when using an application in Text Mode with Record length = 1, the line ending is no longer included in the text file</li>
<li>when using an application in Text Mode with Record length = 2, the CRLF -&gt; CRCRLF is no longer compensated</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Application method</p>         </td>
         <td><p>Select the method to use to retrieve the Application object:</p>
<ul>
<li><span style="font-weight: bold;">User exit</span></li>
<li><span style="font-weight: bold;">File name</span></li>
<li><span style="font-weight: bold;">User message field</span></li>
</ul>         </td>
      </tr>
      <tr>
         <td><strong>Pipeline level</strong>         </td>
         <td><p>Set the maximum number of outstanding buffers (non-acknowledged) that the client may send to the server before waiting for an acknowledgment.</p>
<p>Possible values: <strong>0</strong> - <strong>255</strong>.</p>
<p>Default = <strong>0</strong> (the values <span style="font-weight: bold;">0</span> and <span style="font-weight: bold;">1</span> are equivalent.)</p>
<p>This parameter is used in client mode only (outgoing transfers).</p>         </td>
      </tr>
      <tr>
         <td><p>Transport security in SecureRelay for outgoing connection</p>         </td>
         <td><p>Select this option to use SSH termination in Secure Relay.</p>         </td>
      </tr>
      <tr>
         <td><strong>Disable Gateway specific behavior</strong>         </td>
         <td>Select this option to disable the use of SFTP commands specific to Gateway (<span class="code">SSH_FXP_OPEN@axway.com </span>and <span class="code">SSH_FXP_OPENDIR@axway.com</span>). These specific commands are useful in the context of an exchange between Gateway and Gateway SFTP.         </td>
      </tr>
   </tbody>
</table>

Related topics

[Working with Remote Sites](../)

[Site objects: Parameters List](../../managing_local_sites_cli/sites_parameter_list)

[About SFTP](../../../../protocols_about/sftp_about)

[Axway PassPort PS connector](../../../../connectors_about/passport_pm_connector/passport_ps_connector)

Security guide &gt; [SSH authentication](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/Managing_Security/SSH/ssh_authentication.htm)

Security guide &gt;
[About Secure Relay](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/Managing_Security/DMZs_and_Firewalls/secure_relay_about.htm)

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
