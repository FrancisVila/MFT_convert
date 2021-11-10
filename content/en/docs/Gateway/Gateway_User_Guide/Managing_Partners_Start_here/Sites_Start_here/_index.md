{
    "title": "Managing site objects",
    "linkTitle": "Managing Site objects",
    "weight": "130"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Partners

## About Site objects

### Overview

This topic introduces Site objects and explains the difference between static Sites (local and remote) and dynamic (template) Sites.

In Gateway, to define the parameters of a file transfer, you require a description of the partner for the file exchange. You specify the characteristics of partner sites in <span style="font-style: italic;">Site objects</span>.

A Site object specifies either the destination or the origin of a file transfer. Each Site:

-   Is specific to a given transfer protocol
-   Can communicate across multiple types of network: TCP/IP, LU 6.2,...

A transfer begins with the physical connection of two Sites. One Site is the file Sender and one is the Receiver. In Gateway, the terms <span style="font-style: italic;">Initiator</span> and <span style="font-style: italic;">Responder</span> are used in place of the standard terms Client and Server. The Initiator Site requests the connection, and the Responder Site responds to the connection request. The Initiator and Responder can both be Sender and Receiver. During the connection phase, the Initiator sends its identification. If the Responder is an Axway MFT product, it checks the Initiator identification to see if they correspond to elements specified in its Remote Site attributes.

<span id="Static_Sites"></span>

### Static Sites

A static Site is a Site that is defined as an object and stored in the Gateway database. FTP, SFTP and HTTP server products, Axway Transfer products, Axway EndPoint, and Gateway itself are all examples of static Sites.

A static Site in Gateway is either:

-   A <span style="font-weight: bold;">Local Site</span> - an exchange Site located on the Gateway system, or
-   A <span style="font-weight: bold;">Remote Site</span> - a partner Site defined as a Site object on another machine

A Local Site is associated with a Remote Site via the Remote Site parameter: <span style="font-weight: bold;">Partner local alias</span> (<span class="code">-partner\_loc\_alias</span>).

To define a Site, you specify the following parameters:

-   Name
-   Authorized mode: sender/receiver, Initiator/Responder
-   Transfer protocol (PeSIT, FTP, HTTP, and so on)
-   Communication type (TCP/IP, LU 6.2) and network address for main and backup paths

<span id="Dynamic_Sites"></span>

### Dynamic Sites

#### Template Site definition

To exchange files in client mode, Gateway requires a complete description (including network parameters such as IP address and SAP) of the connection partner and the file exchange process.

When multiple client stations exist, the task of redefining a new Remote Site for each and every file exchange partner may become long and time-consuming. To overcome this, Gateway provides a dynamic Site creation feature that enables you to accelerate the Site definition process and exchange files with unrecognized client stations.

When you submit a Transfer Request for which no defined Remote Site exists, Gateway dynamically creates a Site that is based on one of the Template Sites provided with the product. A Template Site is like any Remote Site, but some of its protocol and network attributes remain empty.

Gateway automatically creates the following Template Sites when you install the product:

-   TFTP (for generic access from FTP clients)
-   THTTP (for generic access from HTTP clients)
-   TFTP\_HTTP (special bi-protocol Template Site for generic access from clients that use either HTTP or FTP)
-   TSFTP (for generic access from SFTP clients)
-   TODT (for generic access from OFTP clients)
-   TPEL (for generic access from PEL clients)
-   TPHSD (for generic access from PeSIT HS D clients)
-   TPHSE (for generic access from PeSIT HS E clients, such as Axway EndPoint)
-   TAS2 (for generic access from EDIINT AS2 clients)
-   TAS3 (for generic access from EDIINT AS3 clients)
-   TRN\_HTTP (for generic access from RosettaNet HTTP clients)

#### Dynamic Site creation

You can associate each client workstation with a physical profile. At the time of connection, the client workstation inherits the attributes of the Template Site.

At the protocol connection level, Gateway analyzes the CGateGroup definition and checks whether a Template Site is specified. If the connection requires the use of a Template Site, Gateway:

-   Dynamically creates a Remote Site from the Template Site definition
-   Completes the Site definition with the received connection parameters

The lifetime of a dynamic Site lasts as long as a reference to the Site is contained in a Mailbox record of a transfer. When you delete all Mailbox records containing a reference to the dynamic Site, Gateway automatically removes the dynamic Site.

The dynamic Site alias is a concatenation of the following strings:

"$": indicates that the current Remote Site is a dynamic Site

Protocol prefix: current connection protocol prefix which can take the following values:

-   <span style="font-weight: bold;">D</span>: PeSIT HS D connections
-   <span style="font-weight: bold;">E</span>: PeSIT HS E connections
-   <span style="font-weight: bold;">P</span>: PEL connections
-   <span style="font-weight: bold;">F</span>: FTP connections
-   <span style="font-weight: bold;">H</span>: HTTP connections
-   <span style="font-weight: bold;">T</span>: bi-protocol (HTTP & FTP) connections
-   <span style="font-weight: bold;">S</span>: SFTP connections
-   <span style="font-weight: bold;">O</span>: OFTP (Odette) connections

"\_" : separator character

"<span style="font-style: italic;">connected client identifier</span>" protocol-dependent string:

-   PHSE, PEL, OFTP: client identifier sent by the connected client
-   HTTP, FTP and bi-protocol (HTTP & FTP): user login sent by the connected client

Related topics

[Overview: Transfer Sites](../../ov_gateway/ov_transfer_sites)

[Working with Local Sites](managing_local_sites)

[Working with Remote Sites](managing_remote_sites)

[Address configuration for Remote Sites](managing_remote_sites/site_objects_address_config)

[Working with Local Sites (command line)](managing_local_sites_cli)

[Working with Remote Sites (command line)](managing_local_sites_cli/managing_remote_sites_cli)

[Site objects: Parameters List](managing_local_sites_cli/sites_parameter_list)

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
