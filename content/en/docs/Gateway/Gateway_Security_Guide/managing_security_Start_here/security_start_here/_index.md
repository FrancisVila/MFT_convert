{
    "title": "Transfer Security Management ",
    "linkTitle": "Transfer Security Management",
    "weight": "130"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Security

Gateway integrates a set of objects that you can use to manage your transfer security requirements.

-   [Certificates and keys](certificates_and_keys_start_here): to authenticate the remote party
-   [Network Profiles](network_profiles_start_here): to determine whether or not to associate an incoming connection with a Security Profile (either TLS or SSH)
-   [TLS Security Profiles](ssl_and_tls_protocols_about/tls_security_profiles__gui_): to secure a connection with TLS protocol
-   [SSH Security Profiles](ssh_protocol_about/ssh_security_profiles__gui_): to secure a connection with SSH protocol (only used with SFTP)

You can manage these objects using either the GUI or command lines.

This book describes the Gateway functions and components that are specifically devoted to operations security.

This topic introduces Gateway profile processes. This book is divided into sub-books that describe the architecture and management of the Security Server (SECS) module of Gateway and how to create, manage and monitor the objects listed above:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Sub-book</p>         </th>
<th class="HeadD-Column1-Header1"><p>Describes...</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><a href="security_server_(secs)_architecture">Security Server (SECS)</a></p>         </td>
         <td><p>The role of the Security Server in the Gateway architecture, and how to manage it using online commands.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="certificates_and_keys_start_here">Certificates and keys</a></p>         </td>
         <td><p>The use and management of security certificates and keys.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="network_profiles_start_here">Network Profiles</a></p>         </td>
         <td><p>The use and management of Network Profiles.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="ssh_protocol_about">SSH Protocol</a></p>         </td>
         <td><p>Features of the SSH protocol and how to deploy them via Gateway.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="ssl_and_tls_protocols_about">TLS Protocol</a></p>         </td>
         <td><p>Features of the TLS protocol and how to deploy them via Gateway.</p>         </td>
      </tr>
   </tbody>
</table>

 

<span id="How_Gateway_establishes_security"></span>

## How Gateway establishes security

Gateway uses <span style="font-weight: bold;">Network Profile</span> objects to determine whether an incoming connection must be secured. Network Profiles contain matching rules that Gateway applies to the incoming connection parameters (origin address, SAP, and so on). From the Network Profile that best matches the incoming connection, Gateway determines which Security Profile to use that provides all required security elements.

The <span style="font-weight: bold;">Security Profile</span>, either TLS or SSH, is used to establish security for both incoming and outgoing connections. The Security Profile is a configuration set that determines which security protocol to use, which encryption method, and so on.

### Incoming connections

In most cases, when you use TLS/SSL or SSH protocols, the connection is secured as soon as you establish a network connection.

When an incoming connection occurs, Gateway must determine whether to use TLS/SSL or SSH, otherwise data received may be misunderstood.

Incoming connections use Security Profiles twice:

-   Once to secure the connection when the connection is established
-   Once during connected Site authentication, to check that the parameters assigned to the Remote Site match the established level of security

In an incoming connection, only the process of identification of the Security Profile is common to TLS/SSL and SSH.

### Outgoing connections

The Remote Site configuration determines whether or not to secure an outgoing connection.

If you specified a Security Profile in the outgoing <span style="font-weight: bold;">Security Profile</span> field (<span class="code">tls\_sprof\_out</span>) of the Site, then this Security Profile is used to secure the connection.

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
