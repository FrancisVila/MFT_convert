{
    "title": "About Secure Relay",
    "linkTitle": "About Secure Relay",
    "weight": "160"
}{{< Gateway/componentlongname  >}}: Managing Security

[About Secure Relay](#About_Secure_Relay)

[Global architecture](#Global_architecture)

[Secure Relay components](#Components)

[Communication interfaces](#Communication_interfaces)

[Physical connections](#Physical_connections)

[Security features](#Security_features)

<span id="About_Secure_Relay"></span>

## About Secure Relay (formerly XSR)

To provide secure links between Gateway and file-exchange partners over the Internet, you can deploy Gateway in a DMZ protected architecture.

Gateway includes the Secure Relay components. These components enable you to securely exchange transfers with remote partners via a DMZ.

Secure Relay is a secure, multi-protocol, front-end component that prevents external Internet partners from directly accessing Gateway for file exchanges.

For a general description of the role of Secure Relay in Gateway, refer to [Overview: DMZ deployment](../../../../gateway_userguide_(primary)/ov_gateway/ov_dmz_deployment).

<span id="Global_architecture"></span>

## Global architecture

The following illustration shows the general principles of Secure Relay deployment.

<img src="/Images/Gateway/XSR_Archi2.png" class="maxWidth" />

<span id="Components"></span>

## Secure Relay components

Secure Relay is composed of two main components:

-   Secure Relay Master Agent
-   Secure Relay Router Agent

### Secure Relay Master Agent

The Secure Relay Master Agent (Secure Relay MA) is a Secure Relay component residing with, and fully integrated in, Gateway. All of the processes that support the functioning of Secure Relay MA are automatically included in Gateway on installation.

During installation, the installation program installs Secure Relay related files in the directory `<Gateway installation directory>/run_time/xsr`.

After installation, you need to [configure and activate the Secure Relay Master Agent](../working_with_secure_relay#Configuring_Secure_Relay).

### Secure Relay Router Agent

The Secure Relay Router Agent (Secure Relay RA) is a stand-alone component of Secure Relay. You install Secure Relay RA on a machine located in the DMZ, independent of Gateway.

<span id="Communication_interfaces"></span>

## Communication interfaces

Communication between Gateway and the Secure Relay components relies on the following two interfaces:

-   Hot channel interface
-   Communication channel interface

### Hot channel interface

The Hot channel (or Admin channel) interface provides secure connections for dynamic exchanges of orders/responses. Gateway uses these exchanges to drive the physical connections as follows:

-   For incoming calls, Secure Relay accepts and streams connections to the protected area, or alternatively, denies the connections
-   For outgoing calls, Secure Relay opens connections from the DMZ to external partners

The Hot channel is a single secure TCP/IP connection between a Secure Relay MA and a Secure Relay RA. The Secure Relay MA always opens this connection towards the Secure Relay RA.

The following types of data travel back and forth over the Hot channel:

-   Secure Relay configuration settings that Gateway sends on startup (including the static ports to which the Secure Relay RAs must listen for incoming connections)
-   Request/Response exchanges that enable Gateway to dynamically:
    -   Manage data connections for FTP (either in passive or active mode)
    -   Open new connections for outgoing calls
    -   Analyze incoming connection indications to indicate that a partner is opening a new TCP/IP connection and that a new logical data streaming channel (through one of the Communication channels) must be started
    -   Allow or deny incoming connections based on SSL parameters or protocol authentication

#### Hot channel security

SSL

The Hot channel TCP/IP connection is secured using TLS transport security.

By using X.509 certificates (strong authentication) on both Gateway and Secure Relay RA sides, TLS ensures that:

-   Only Gateway (via Secure Relay MA) and the Secure Relay RA can communicate with each other, avoiding communication hijacking.
-   No one can interfere with the orders sent by Secure Relay MA to the Secure Relay RA.
-   No one can even sniff the network, or understand what operation is being processed and try to take advantage of it

Firewall-friendly features

You define TCP/IP connections via address/port couples on each communicating site.

You can fully configure the address/port couple for the Hot channel either in the Gateway configuration menu or the Secure Relay configuration file. This facility guarantees that the file-exchange solution (comprising both Gateway and Secure Relay in a distributed system) can be deployed in environments with the most restrictive Firewall management rule policy.

### Communication channel interface

Communication channels are a predefined set of TCP/IP physical connections opened between Secure Relay MA and Secure Relay RA to handle the streaming of incoming and outgoing data flows from the DMZ to the protected network and vice versa. Communication channels are always initiated from the Gateway side (Secure Relay MA).

The Communication channel (or Data channel) provides an Axway proprietary protocol that enables you to convert any number of physical multiplexed stream connections established between the DMZ and the outside world into a fixed set of physical connections.

#### Communication channel security

Communication channel security relies on an administration-oriented dialog that Gateway and Secure Relay establish via the Hot channel.

SSL

The Communication channel TCP/IP connection can be secured using TLS transport security.

By using X.509 certificates (strong authentication) on both Gateway and Secure Relay RA sides, TLS ensures that:

-   Only Gateway (via Secure Relay MA) and the Secure Relay RA can communicate with each other, avoiding communication hijacking.
-   No one can interfere with the data exchanged between Secure Relay MA and the Secure Relay RA.
-   No one can even sniff the network, or understand what operation is being processed and try to take advantage of it.

Because you can configure the number of Communication channels in the Gateway configuration menu and can also define (and restrict) the local port range used on the Gateway host machine, Communication channels are also firewall-friendly.

It should be noted that securing the Communication channels between Secure Relay and Gateway using mutual authentication and encryption may have an impact on the performance of the solution.

<span id="Physical_connections"></span>

## Physical connections

The following figure illustrates the physical connections established between the DMZ and the protected zone using the {{< Gateway/securerelayname  >}} solution.

<img src="/Images/Gateway/XSR_ArchiConnections.png" class="maxWidth" />

<span id="Security_features"></span>

## Security features

<span id="TLS_termination_in_DMZ"></span>

### TLS termination in DMZ

The Secure Relay Router Agent is able to handle the whole TLS dialog and security for incoming and outgoing connections for the FTP, HTTP and PeSIT E protocols. It authenticates the remote partner by using PassPort PKI services (located in the intranet) via the Secure Relay Master Agent (Secure Relay MA). Only then, is the incoming connection forwarded to the corporate network. It also uses PassPort PKI services to authenticate itself to the remote partner.

In the case of FTP, both implicit and explicit termination are now supported by the Secure Relay Router Agent (Secure Relay RA).

-   In the case of FTP, both implicit and explicit termination are supported by the Secure Relay Router Agent (Secure Relay RA).
-   for the SecureRelay security termination, the communication with the PKI server (PassPort) is done through the Master Agent

To activate this feature:

-   Set up the TLS profile to use in Secure Relay when [configuring your listening ports](../../../../gateway_userguide_(primary)/configuration_start_here/config_protocols_about/config_sap_parameters) in the Gateway configuration menu, and
-   Select **Transport security in SecureRelay for outgoing connection** in the [Remote Site object (Net security tab)](../../../../gateway_userguide_(primary)/managing_partners_start_here/sites_start_here/managing_remote_sites/remote_site_net_security_tab)

Delegating the TLS termination to the Secure Relay component may have an impact on the performance of the solution.

### Connection to PassPort

The Master Agent will read the configuration for the connection to PassPort from the <span class="code">advanced.properties</span> file located inside the <span class="code">run\_time/xsr</span> folder.

A sample <span class="code">advanced.properties </span>file is available in <span class="code">samples/xsr</span> folder

You can copy this file to the <span class="code">run\_time/xsr</span> folder and edit it with the relevant configuration information.

<span id="Login_termination_in_DMZ"></span>

### 

### Login termination in DMZ (protocol login)

As with SSL termination in the DMZ, it can be useful for protocols that have a built-in login mechanism to verify the credentials associated with an incoming connection in the DMZ. The Secure Relay Router Agent (Secure Relay RA) is then able to delay the establishment of the connection with its associated Master Agent until the credentials have been accepted by the Gateway server, using its standard security checking procedure. By using this feature, you ensure that the only connections accessing the Gateway server in your corporate network through Secure Relay RA are those matching the security parameters defined in the server.

The currently-supported protocols and authentication methods are:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Protocol</p>         </th>
<th class="HeadD-Column1-Header1"><p>Authentication methods</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>HTTP</p>         </td>
         <td><p>http basic, CGI user/password, CGI sessionId, cookie user/password, cookie sessionId</p>         </td>
      </tr>
      <tr>
         <td><p>FTP</p>         </td>
         <td><p>user/password</p>         </td>
      </tr>
   </tbody>
</table>

Activate this feature by checking the <span style="font-weight: bold;">Protocol login in SecureRelay</span> option in the Secure Relay SAP configuration for HTTP and FTP.

<span style="font-weight: bold;">Warning:</span> If DMZ login termination is active, you can only activate TLS on the Router Agent side (not on the Gateway server).

Delegating the login termination to the Secure Relay component may have an impact on the performance of the solution.

<span id="SFTP_termination_in_DMZ"></span>

### SFTP termination in DMZ

The Secure Relay Router Agent (Secure Relay RA) is able to perform SFTP connection authentication in the DMZ. It can handle the whole SSH dialog and security for incoming and outgoing connections for SFTP. The authentication is done at both transport level (ciphers and certificates) and application level (user names and passwords). It authenticates the remote partner by using PassPort PKI services (located in the intranet) via the Secure Relay Master Agent. Only then, is the incoming connection forwarded to the corporate network. It also uses PassPort PKI services to authenticate itself to the remote partner.

By using this feature, you ensure that the only connections accessing the Gateway server in your corporate network through Secure Relay RA are those matching the security parameters defined in the server.

Secure Relay RA supports password and public key authentication, in both server and client modes.

The following subset of SSH parameters is supported by Secure Relay RA:

Key exchange algorithms:

-   DH\_GROUP1\_SHA1

Cipher algorithms:

-   AES128\_CBC
-   3DES\_CBC
-   NONE

Message authentication code (MAC) algorithms:

-   HMAC\_SHA1
-   HMAC\_MD5
-   HMAC\_SHA1\_96
-   HMAC\_MD5\_96
-   NONE

Public key algorithms:

-   SSH\_RSA
-   SSH-DSS

To activate this feature:

-   Set up the SSH profile to use in Secure Relay when [configuring your listening ports](../../../../gateway_userguide_(primary)/configuration_start_here/config_protocols_about/config_sap_parameters) in the Gateway configuration menu, and
-   Select <span style="font-weight: bold;">Transport security in SecureRelay for outgoing connection</span> in the [Remote Site object (SFTP tab)](../../../../gateway_userguide_(primary)/managing_partners_start_here/sites_start_here/managing_remote_sites/remote_site_sftp_tab)

<span style="font-weight: bold;">Warning:</span> The selected SSH profile must provide PassPort entities to properly set up Secure Relay RA termination. Using the Gateway internal security server (SECS) is not supported.

Delegating the SFTP termination to the Secure Relay component may have an impact on the performance of the solution.

### PKI exit

You can override Secure Relay’s default PKI behavior for secure Communication channels and Hot channel. To do this, declare your own implementations of JSSE <span class="code">X509ExtendedKeyManager</span> and <span class="code">X509TrustManager</span> (<span class="code">javax.net.ssl</span> package) in Secure Relay. Secure Relay then uses your implementations instead of its own to manage X.509 certificates and private keys.

Refer to the samples in <span class="code">&lt;Secure Relay RA directory>/exit</span>.

Refer to the Javadoc <span class="code">index.html</span> in <span class="code">&lt;Secure Relay RA directory>/exit/doc</span>.

### Password exit

You can override the Secure Relay Router Agent’s default method of managing passwords. Declare your implementation of <span class="code">com.axway.xsr.security.pki.PasswordManager</span> in Secure Relay. Secure Relay then calls your interface instead of reading or writing its standard password file.

Refer to the samples in <span class="code">&lt;Secure Relay RA directory>/exit</span>.

Refer to the Javadoc <span class="code">index.html</span> in <span class="code">&lt;Secure Relay RA directory>/exit/doc</span>.

### Management of JCE providers

Secure Relay does not explicitly use a particular security provider. It uses the standard Java JCE infrastructure. Therefore, you can set up your JRE to use any of your security providers, and Secure Relay will use it as well.

<span id="multiple_RAs"></span>

### Management of multiple Secure Relay Router Agents

You can set up multiple instances of Secure Relay RA (eight maximum) running simultaneously on several machines. For high availability, the Secure Relay Master Agent automatically recovers errors that occur on any instance of Secure Relay RA. It also balances outgoing connections between available instances of Secure Relay RA.

You can not set up more than one Secure Relay RA per machine: the Secure Relay Master Agent sends the same configuration to every Secure Relay RA, so that every instance of Secure Relay RA listens on every TCP port you configured for Gateway’s protocol connectors.

To configure Secure Relay RAs, refer to [Configuration: Connectivity parameters](../../../../gateway_userguide_(primary)/configuration_start_here/config_connectivity_paras#olh_connectivity_Secure_Relay).

For outbound transfers you can select the Secure Relay Router Agents to use for each partner. You make the selection in the Remote Site:

-   On the **Network address** tab, use the [**Allowed Router Agents**](../../../../gateway_userguide_(primary)/managing_partners_start_here/sites_start_here/managing_remote_sites/remote_site_network_address_tab#allowed_RAs) parameter, or
-   With online commands, use the <span class="code">peladm update\_site</span> command and the <span class="code" style="font-weight: bold;">[-xsr\_allowed\_ra\_list (-xsr\_arl)](../../../../gateway_userguide_(primary)/managing_partners_start_here/sites_start_here/managing_local_sites_cli/sites_parameter_list#_xsr_arl)</span> parameter.

### Logging in the DMZ

You can carry out logging in the DMZ. Accessing log files can provide valuable information when troubleshooting a given setup.

For security reasons, this feature is disabled by default (the logs can contain data that can be useful for an attacker). To enable logging in the DMZ, edit the Secure Relay RA configuration file as described in the <span style="font-style: italic;">Axway Secure Relay Router Agent Administrator's Guide</span>.

Related topics

[Overview: DMZ deployment](../../../../gateway_userguide_(primary)/ov_gateway/ov_dmz_deployment)

[Working with Secure Relay](../working_with_secure_relay)

[About configuring Gateway](../../../../gateway_userguide_(primary)/configuration_start_here)

[Configuration: Connectivity parameters](../../../../gateway_userguide_(primary)/configuration_start_here/config_connectivity_paras#olh_connectivity_Secure_Relay)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
