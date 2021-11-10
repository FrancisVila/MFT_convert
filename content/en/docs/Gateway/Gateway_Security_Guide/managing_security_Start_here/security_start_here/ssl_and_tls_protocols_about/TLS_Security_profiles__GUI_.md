{
    "title": "Managing TLS Security Profiles",
    "linkTitle": "Managing TLS Security Profiles",
    "weight": "240"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Security

A TLS Security Profile contains all the security configuration elements used to establish a TLS connection.

To import a TLS Profile, use the <span class="code" style="font-weight: bold;">[secadm import\_sprof](../managing_tls_security_profiles_cli#secadm_import_sprof)</span> online command.

[Defining TLS Security Profiles](#Defining_TLS_Profiles)

[Deleting a TLS Security Profile](#Deleting_a_TLS_Profile)

[Certificate templates](#Certificate_templates)

<span id="Defining_TLS_Profiles"></span>

## Defining TLS Security Profiles

To add a new TLS Profile to the profile database:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:  
    <span style="font-weight: bold;">Security Management > Transfer Security Management > Security Profile</span>
2.  Right-click the <span style="font-weight: bold;">TLS Profile</span> sub-node, and then select <span style="font-weight: bold;">New</span> from the context menu.  
    Gateway displays the <span style="font-style: italic;">New TLS Profile</span> window.
3.  Complete the fields of the following tabs as described below:
    -   [General](#TLS_Profile_General_tab)
    -   [Details](#TLS_Profile_Details_tab)
    -   [PassPort PS](#PassPort_tab)

<span id="TLS_Profile_General_tab"></span>

### TLS Profile: General tab

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Name         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Name</p>         </td>
         <td><p>Enter a unique name for the TLS Profile.<br />
Maximum: 31 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Profile type</p>         </td>
         <td><p>Select the type of connection to use with the Security Profile.</p>
<ul>
<li>CLIENT</li>
<li>SERVER</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Client authentication</p>         </td>
         <td><p>Indicates whether <a href="../managing_tls#Client_authentication_policy">client authentication</a> is mandatory, forbidden or optional.</p>
<p>Select one of the following options:</p>
<ul>
<li>TLS_AUT_ANONYMOUS</li>
<li>TLS_AUT_OPTIONAL</li>
<li>TLS_AUT_MANDATORY</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Accepted SSL versions</p>         </td>
         <td><p>List of accepted protocol versions.</p>
<p>Select one or more of the following SSL/TLS versions:</p>
<ul>
<li><p>TLSV1.1</p></li>
<li><p>TLSV1.2</p></li>
<li><p>TLSV1</p></li>
<li><p>SSLV3</p></li>
<li><p>SSL2HELLO</p></li>
</ul>
<p><strong>Note</strong>: when creating a new TLS profile, TLSV1.1 and TLSV1.2 are selected by default.</p>
<p><strong>Note</strong>: SSL2HELLO has been added for backwards compatibility with older Java applications.</p>         </td>
      </tr>
      <tr>
         <td><p>Accepted cipher suites</p>         </td>
         <td><p>List of cipher suites that you can use to secure the connection. The list must be in <span style="font-style: italic;">decreasing order</span> of preference. Note that Gateway only displays a cipher suite if it is supported by all the selected SSL/TLS versions. You can select up to 32 cipher suites.</p>
<p>For an overview of accepted values for the list elements, see <a href="../tls_cipher_suites" class="MCXref xref">TLS cipher suites</a>.</p>
<p><strong>Note</strong>: The default cipher suite selection order, in the case Gateway is the TLS server, is to choose the first cipher in common, using the client preferred (proposed) order. To change this behavior and select ciphers in server preferred order, please use the global static setting [tls]tls_cs_server_order:</p>
<ul>
<li>0 (default value): client preferred order (the cipher order in the ClientHello message)</li>
<li>1: server preferred order, the cipher order in the TLS server profile.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Accepted authorities (server only)</p>         </td>
         <td><p>List of local certificate names.</p>
<p>Server Use Only: certificate local names of the accepted authorities (CA) whose DER-encoded subject names are sent to the client. The client must then send a certification path that matches one of the authorities provided.</p>
<p>Refer to <a href="../managing_tls#Accepted_authorities_list">Accepted authorities list</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>Certificate templates</p>         </td>
         <td><p>Add <a href="#Certificate_templates">certificate templates</a> to use to customize verification of received certification paths. You can add USER, CA, or ROOT certificate templates.</p>         </td>
      </tr>
      <tr>
         <td><p>Trust hosted certificates only</p>         </td>
         <td><p>The term <span style="font-weight: bold;">hosted</span> applies to a certificate (or public key) hosted in the Gateway database. The origin (owner of the associated private key) is known and is authorized to connect via TLS.</p>
<p>Check this option to accept authentication of a partner if any certificate (or public key) belonging to the partner is already present in the Gateway database in the state ENABLED.</p>         </td>
      </tr>
      <tr>
         <td><p>Automatic import of partner certificate chains</p>         </td>
         <td><p>Check this option to allow the automatic import of unknown certificates presented by partners that are authenticating themselves for the first time (or that have changed certificates).</p>
<p>Before any certificate import operation, Gateway checks (with the hash) that the certificate does not already exist in the database.</p>         </td>
      </tr>
      <tr>
         <td><p>User certificates</p>         </td>
         <td><p>Server and client use: Set of certificate local names, first step of the certification path to send to the remote partner.</p>
<p>You can either select a single user certificate or, alternatively, multiple certificates (up to ten).</p>
<p>Refer to <a href="../managing_tls#Defining_User_Certificate_list">Defining User Certificate list</a>.</p>
<p>Gaetway has a new way of building certificate paths, both in server and client mode. It is an implementation of the Internet X.509 Public Key Infrastructure: Certification Path Building specification, also known as RFC4158.</p>
<p>This mode of operation can be configured on individual security profiles using the attribute <code>sprof_path_build_mode</code>, (short version <code>sppbm </code>), having 2 possible values:</p>
<ul>
<li><em>legacy</em></li>
<li><em>rfc4158</em></li>
</ul>         </td>
      </tr>
   </tbody>
</table>

<span id="TLS_Profile_Details_tab"></span>

### TLS Profile: Details tab

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Name         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Cache enabled</p>         </td>
         <td><p>Check this option to enable reuse of the session security parameters.</p>         </td>
      </tr>
      <tr>
         <td><p>Renegotiate enabled</p>         </td>
         <td><p>Check this option to enable cipher key renegotiation.</p>
<p>Select one of the following options: disabled, unrestricted, secure, legacy. For details, see the section <a href="../managing_tls#Secure">Secure renegotiation in TLS</a>.</p>
<p><span style="font-weight: bold;">Note:</span> This feature may not be compatible with certain systems.</p>         </td>
      </tr>
      <tr>
         <td><strong>Refuse legacy partners</strong>         </td>
         <td>Close a connection from a TLS un-upgraded partner from the start (from the initial TLS handshake)         </td>
      </tr>
      <tr>
         <td><p>Exit scheduling</p>         </td>
         <td><p>Check this option to enable the use of an external manager. If you check this option, subsequent parameters are ignored.</p>         </td>
      </tr>
      <tr>
         <td><p>Close notify disabled (FTP and HTTP)</p>         </td>
         <td><p>Check this option to <a href="../managing_tls#Disabling_close_notify_messages_in_TLS">disable the use of close notify messages</a>. Enables inter-operability with products that do not support this feature.</p>         </td>
      </tr>
      <tr>
         <td><p>Certificate path</p>         </td>
         <td><p>Enter the maximum number of certificates accepted in a certification chain. Any certification chain that contains more elements is rejected.</p>         </td>
      </tr>
      <tr>
         <td><p>User param</p>         </td>
         <td><p>Enter a user parameter. This parameter is provided to SECS and Xfer exits.<br />
Maximum: 31 characters.</p>         </td>
      </tr>
      <tr>
         <td><strong>Protocol packet header policy in TLS</strong>         </td>
         <td><p>Usage of protocol packet headers for TLS. Possible values:</p>
<ul>
<li><strong>Unused</strong> - <span class="mc-variable suite_variables.GatewayName variable">Gateway</span> will not use protocol packet headers</li>
<li><strong>Used</strong> - always use protocol packet headers for TLS</li>
<li><strong>Detect</strong> - auto detect mode (depending on how the partner is sending)</li>
</ul>
<p>When using non-stream protocols over TLS (PeSIT, Odette FTP), it is recommended to set the value to <strong>Used</strong> (or at least Detect).</p>
<p>This is because, for non-stream protocols, when transported over a TLS encrypted connection, Gateway may add (when transmitting) or expect (when receiving) some protocol packet headers. These headers are meant to delimit the different protocol units (ex FPDUs) inside a TLS stream. As a TLS stream works in 16K records, it may happen that a TLS record is not exactly fitting a protocol packet. Moreover, if TLS is not done inside Gateway (ex: TLS termination in XSR), the TLS record may be intentionally fragmented (also fragmenting the FPDU inside).</p>
<p>For the Odette protocol, the RFC clearly states that this mechanism should be used over TLS, for PeSIT it is not clear from specification, so it depends on the implementation if the partner will support this mechanism or not.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Protocol packet header policy in TLS</strong></p>         </td>
         <td><p>Usage of protocol packet headers for TLS. Possible values:</p>
<ul>
<li><strong>Unused</strong> - do <em>NOT</em> use protocol packet headers</li>
<li><strong>Used</strong> - <em>always</em> use protocol packet headers for TLS</li>
<li><strong>Detect</strong> - auto detect mode (depending on how the partner is sending)</li>
</ul>
<blockquote>
<p><strong>Note:</strong></p>
<p>When using non-stream protocols over TLS, (PeSIT or Odette FTP), it is recommended to set the value to Used, or at least to Detect.</p>
</blockquote>
<p>This is because Gateway may add (when transmitting) or expect (when receiving) some protocol packet headers when using non-stream protocols Odette and PeSIT transported over a TLS encrypted connection.</p>
<p>These headers delimit the different protocol units (ex FPDUs) inside a TLS stream. As TLS streams use 16K records, it may happen that a TLS record is not exactly fitting a protocol packet. Moreover, if TLS is not done inside Gateway (for example, a TLS termination in XSR), the TLS record may be intentionally fragmented (also fragmenting the FPDU inside).</p>
<p>This is why, when using non stream protocols over TLS (PeSIT, Odette FTP), it is recommended to set the value to "Used" (or at least Detect).
While for the Odette protocol, the RFC clearly states that this mechanism should be used over TLS, for PeSIT it is not clear from specification, so it depends on the implementation if the partner will support this mechanism or not.</p>         </td>
      </tr>
      <tr>
         <td><p>FTP/SMTP/HTTP:</p>         </td>
      </tr>
      <tr>
         <td><p>Connection securing mode</p>         </td>
         <td><p>You can configure Gateway to handle incoming connections in <em>implicit</em> mode or <em>explicit</em> mode.<br />
FTP and SMTP security in a Gateway client can be implemented in either <em>implicit</em> or <em>explicit</em> mode.<br />
HTTP security must be set to <em>implicit</em> on both the client and server profiles.</p>
<p>Select one of the following options:</p>
<ul>
<li><span style="font-weight: bold;">Implicit:</span> Gateway uses TLS in implicit mode by default. In implicit mode, a secure port is used before the connection takes place and the control session is opened directly in SSL/TLS.<br />
<span style="font-weight: bold;">Note:</span> This type of 'negotiation' has been deprecated and is no longer recommended by the IETF.</li>
<li><span style="font-weight: bold;">Explicit:</span> In explicit mode, the connection occurs on a non-encrypted port, and the decision to connect in SSL/TLS is made by negotiation once the session is established.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Global session policy</p>         </td>
         <td><p>This field is only available if you set the <span style="font-weight: bold;">Connection securing mode</span> to Explicit.</p>
<p>Use this option to define whether control session security is mandatory or optional.</p>         </td>
      </tr>
      <tr>
         <td><p>FTP data session policy</p>         </td>
         <td><p>This field is only available if you set the <span style="font-weight: bold;">Connection securing mode</span> to Explicit.</p>
<p>Use this option to define whether data session security is mandatory, optional, or disabled.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="PassPort_tab"></span>

### TLS Profile: PassPort PS tab

Enter values in the fields of the <span style="font-weight: bold;">PassPort PS</span> tab if you are using PassPort security functions for connections with partners defined in [PassPort PS](../../../../../gateway_userguide_(primary)/connectors_about/passport_pm_connector/passport_ps_connector).

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Name         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Local entity</p>         </td>
      </tr>
      <tr>
         <td><p>Name</p>         </td>
         <td><p>Enter the local entity name for access to the PassPort PS server.</p>         </td>
      </tr>
      <tr>
         <td><p>Set Password</p>         </td>
         <td><p>Opens a dialog box to enter the password corresponding to the entity name.</p>         </td>
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
<p>For profiles used with the <span class="code">XSR </span>termination, <em></em>the only valid selection is <em>Passport PS entity</em>.</p>         </td>
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
<p>For profiles used with the <span class="code">XSR </span>termination, <em></em>the only valid selection is <em>Passport PS entity.</em></p>         </td>
      </tr>
   </tbody>
</table>

<span id="Deleting_a_TLS_Profile"></span>

## Deleting a TLS Security Profile

Equivalent online command: <span class="code" style="font-weight: bold;">[secadm delete\_sprof](../managing_tls_security_profiles_cli#secadm_delete_sprof)</span>.

To delete a TLS Profile from the profile database:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:  
    <span style="font-weight: bold;">Security Management > Transfer Security Management > Security Profile</span>
2.  Click to select the <span style="font-weight: bold;">TLS Profile</span> sub-node.  
    Gateway displays all existing TLS Profiles in the right pane.
3.  In the right pane, right-click the TLS Profile that you want to delete. Select <span style="font-weight: bold;">Delete...</span> from the context menu.  
    Gateway displays a confirmation window.
4.  Click <span style="font-weight: bold;">Yes</span>.  
    Gateway deletes the TLS Profile.

<span id="Certificate_templates"></span>

## Certificate templates

Certificate Templates enable you to customize the verification of a received certification path.

For each certificate path, the Certificate Template:

-   <span style="font-style: italic;">Determines</span> the certificate type (User, Intermediary CA or Root CA).
-   <span style="font-style: italic;">Parses</span> the current Security Profile object.
-   <span style="font-style: italic;">Checks</span> the corresponding <span style="font-style: italic;">Template List</span> (respectively RemoteUserCertificate, RemoteCaCertificate, and RemoteRootCertificate). If the list is not empty (which means that the certificate is accepted by default), the certificate must match one of the template records.

The matching criteria proposed for a template record are:

-   <span style="font-weight: bold;">Certificate name:</span> If this field is completed, the certificate received must be present in the local database and is referenced here by its name.
-   <span style="font-weight: bold;">Pattern matching:</span> If a certificate name is not present, the certificate issuer and subject distinguished names must match the following certificate template fields:
    -   <span style="font-style: italic;">subject\_name</span>: pattern that contains the substitution characters <span style="font-weight: bold;">\*</span> and <span style="font-weight: bold;">?</span>
    -   <span style="font-style: italic;">issuer\_name</span>: pattern that contains the substitution characters <span style="font-weight: bold;">\*</span> and <span style="font-weight: bold;">?</span>
    -   <span style="font-style: italic;">alternative</span>

<span id="Adding_a_Certificate_template"></span>

### Adding a certificate template

To add a certificate template:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:  
    <span style="font-weight: bold;">Security Management > Transfer Security Management > Security Profile</span>
2.  Click to select the <span style="font-weight: bold;">TLS Profile</span> sub-node.  
    Gateway displays all existing TLS Profiles in the right pane.
3.  In the right pane, right-click an existing Profile. Select <span style="font-weight: bold;">Modify...</span> from the context menu.  
    Gateway opens the <span style="font-style: italic;">TLS Profile</span> window.
4.  In the <span style="font-weight: bold;">General</span> tab of the <span style="font-style: italic;">TLS Profile</span> window, click the <span style="font-weight: bold;">Certificate templates</span> button.
5.  In the <span style="font-weight: bold;">Certificate Templates</span> tab, select from:
    -   **USER**
    -   **CA**
    -   **ROOT**
6.  Click <span style="font-weight: bold;">Add</span>.  
    Gateway displays the <span style="font-style: italic;">Template</span> window.
7.  Select from either:
    -   <span style="font-weight: bold;">Match the local certificate whose name is:</span> enter the certificate name.
    -   <span style="font-weight: bold;">Match the DN criteria:</span> complete the listed fields.
8.  Click <span style="font-weight: bold;">OK</span> to confirm and close the <span style="font-style: italic;">Template</span> window.

You can also remove a certificate in the <span style="font-weight: bold;">Certificate Templates</span> tab. Select the certificate and click <span style="font-weight: bold;">Remove</span>.

## Certification path building mode in TLS

Gaetway has a new way of building certificate paths, both in server and client mode. It is an implementation of the Internet X.509 Public Key Infrastructure: Certification Path Building specification, also known as RFC4158.

This mode of operation can be configured on individual security profiles using the attribute `sprof_path_build_mode`, (short version `sppbm `), having 2 possible values:

-   *legacy*
-   *rfc4158*

Related topics

<a href="../tls_cipher_suites" class="MCXref xref">TLS cipher suites</a>

<a href="../managing_tls" class="MCXref xref">Managing TLS</a>

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
