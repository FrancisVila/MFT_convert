{
    "title": "DMZ deployment",
    "linkTitle": "DMZ deployment",
    "weight": "190"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Overview

When you link your enterprise network to the Internet, you can enhance local isolation and security by deploying Gateway in a DMZ configuration.

Axway offers two solutions for deploying Gateway in DMZ architectures:

-   [<span class="mc-variable axway_variables.Company_Name variable">Axway</span> <span class="mc-variable suite_variables.SecureRelayName variable">Secure Relay</span>](#secure_relay)
-   [Paired <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>s](#paired_gateways)

<span id="secure_relay"></span>

## <span class="mc-variable axway_variables.Company_Name variable">Axway</span> <span class="mc-variable suite_variables.SecureRelayName variable">Secure Relay</span> (formerly XSR)

The components of <span class="mc-variable suite_variables.SecureRelayName variable">Secure Relay</span>, delivered with Gateway, enable you to deploy Gateway in a DMZ architecture. Secure Relay is a secure, multi-protocol, front-end product that prevents external partners from directly accessing Gateway for file exchange. Secure Relay processes data streaming of external connections from the outside world to Gateway without any data storage (even temporary) in the DMZ. Secure Relay is compatible with any Gateway supported protocol that uses a TCP/IP network.

When you use Gateway with Secure Relay, you derive the following specific benefits:

-   All of your data is stored in your local network, protected by your firewall
-   Connections from outside the protected area are refused
-   Configuration data, including private server keys, are never stored in the DMZ
-   No decryption occurs within the DMZ
-   You can adapt the connection parameters of your Gateway to conform to the policies you establish in the DMZ

### Distribution of functions

Native Gateway functions work together with the specific Secure Relay functions to provide DMZ security.

In a Secure Relay / DMZ configuration:

-   Gateway:
    -   Manages streaming connections with the Secure Relay Router Agent situated in the DMZ
    -   Manages user access to file resources (workspaces, downloads and uploads)
    -   Handles the file transfer protocol dialog with partners
    -   Manages file transfer scheduling and monitoring
    -   Can terminate transport security communication (either SSL or SSH for SFTP) to ensure a transparent link between partner identities (X.509 certificate) and file operations
    -   Generates links with internal IT system applications by either routing files to other destinations or by direct integration
    -   Handles physical file management operations

<!-- -->

-   Secure Relay:
    -   Manages connections with the outside world for file exchange, depending on the Gateway directives
    -   Handles data streaming of flows to and from the Internet
    -   Can terminate transport security communication (either SSL or SSH for SFTP) to ensure a transparent link between partner identities (X.509 certificate) and file operations

### Secure Relay architecture

<span class="mc-variable suite_variables.SecureRelayName variable">Secure Relay</span> is divided into two basic components parts:

-   <span style="font-weight: bold;">Secure Relay Master Agent</span>  
    The Secure Relay Master Agent is a component that resides with and is fully integrated in the Gateway product. All of the processes that support Secure Relay Master Agent functions are automatically included in Gateway on installation.
-   <span style="font-weight: bold;">Secure Relay Router Agent</span>  
    The Secure Relay Router Agent is a stand-alone component. You install the Secure Relay Router Agent on a machine located in the DMZ, independently of Gateway.

<img src="/Images/Gateway/XSR_Archi1.png" class="mediumWidth" />

<span id="paired_gateways"></span>

## Paired <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>s

Alternatively, to secure your local network when connecting to the Internet, you can deploy paired Gateways in a bridged private/public DMZ configuration.

The following diagram illustrates the use of Gateways in a DMZ bridge configuration.

 

<img src="/Images/Gateway/DMZ_2GTW.png" class="maxWidth" />

With this configuration you can:

-   Filter and control access attempts from the Internet
-   Ensure secure end-to-end file data integrity and confidentiality on both sending and receiving transfers (transfer acknowledgments and monitoring)
-   Scan received files for viruses
-   Route files from the sender to the final destination

### Operating principles

The paired Gateway DMZ operates according to the following principles:

#### Private Gateway

A Gateway serving as a <span style="font-style: italic;">private</span> Gateway contains definitions that enable the applications situated in your corporate network to act as servers and clients for exchanges with Internet partners.

The files that the private Gateway receives from Internet partners are decrypted and scanned for viruses before being forwarded to the destination application in your corporate intranet.

In your private Gateway, to control the identity of your corporate partners, you create a Remote Site object definition for each partner.

In the private Gateway you create a Decision Rule that handles all transfer flow originating from your corporate network and directed towards the Internet. You use this Decision Rule apply a Routing Model that directs the transfer to the public Gateway via a secured protocol.

In the private Gateway you can also create a Decision Rule to handle the reception of files forwarded from the Internet by the public Gateway.

#### Public Gateway

A Gateway serving as a <span style="font-style: italic;">public</span> Gateway contains definitions of all external Internet partners.

The temporary files that the public Gateway stores and all Gateway internal files (administration and Mailbox files) are ciphered to protect against malicious intrusion.

In your public Gateway, to establish the identities and control possible connection attempts of your external Internet partners, you create:

-   Remote Site object definitions for Internet partners acting as servers
-   CGate object definitions for Internet partners acting as clients

Additionally, in your public Gateway, you create a Decision Rule that handles all transfer flow originating from Internet partners. You use this Decision Rule to apply a Routing Model that directs the transfer to the private Gateway via a secured protocol.

#### Exchanges between Gateways

The public and private Gateways communicate via the PeSIT protocol (secured by SSL/TLS) or via SFTP.

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
