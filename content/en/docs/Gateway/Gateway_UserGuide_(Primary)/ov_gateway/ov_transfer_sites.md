{
    "title": "Transfer Sites",
    "linkTitle": "Transfer Sites",
    "weight": "80"
}{{< Gateway/componentlongname  >}}: Overview

As described in the [previous topic](../ov_file_transfers), Gateway operations generally involve the transfer of files between two or more computers. In order to process a Transfer, Gateway needs information about the originating and destination computers. In Gateway terminology, originating and destination computers are known as *Sites*. You describe the characteristics of sites to Gateway by creating *Site objects*.

Each Transfer Request requires the definition of two Site objects:

-   **Local Site object** - provides the characteristics of the computer that hosts your Gateway. In many cases, Gateway automatically collects the necessary information about your local Site from information you provide during installation and configuration.
-   <span style="font-weight: bold;">Remote Site object</span> - provides the characteristics of the computer with which the local computer is exchanging the file or files. In most cases, you specify the remote site that is the partner in a transfer, and specify the properties of the site in the Remote Site object.

## Site characteristics

### Site alias

You attribute a unique name to every Site object you create. This unique name is known as the <span style="font-style: italic;">Site Alias</span>.

### Site role

In a given Transfer, one of the two sites is the Sender site and the other is the Receiver site. Additionally, one of the two sites is the Initiator (client) and the other is the Responder (server).

Therefore, for a given transfer, a Remote Site can fill one of four possible roles:

-   <span style="font-weight: bold;">Initiator/Sender:</span> The Remote Site acts as a client and initiates a transfer towards the local Gateway.
-   <span style="font-weight: bold;">Initiator/Receiver:</span> The Remote Site acts as a client, requesting the transfer from the local Gateway.
-   <span style="font-weight: bold;">Responder/Sender:</span> The Remote Site acts as a server responding to a request for a transfer from the local Gateway.
-   <span style="font-weight: bold;">Responder/Receiver:</span> The Remote Site acts as a server, accepting a transfer from the local Gateway.

### Site protocol

In a given Transfer, the sending and receiving sites have to agree on a protocol to use for the Transfer.

#### Remote Site

You specify the protocol you want to use for a Transfer in the Remote Site object. The Remote Site must support the protocol you specify, or the transfer attempt will fail.

#### Local Site

You must also configure your Local Site to handle the specified protocol. Typically this means that you must activate the protocol in the configuration menu and, if your local machine is acting as a server, in a CGate (Connection Gate) object. You do not need to specify the protocol to use in the Local Site object.

### Additional Site object characteristics

In addition to the basic information described above, you can specify other characteristics of Site objects. These parameters can improve the performance and security of your transfers. The information you can enter varies according to the type of transfer you choose to execute.

## Dynamic Sites

To exchange files in client mode, Gateway requires a complete description (including network parameters such as IP address and SAP) of the connection partner and the file exchange process.

However, when multiple client stations exist, the task of redefining a new Remote Site for each and every file exchange partner may become long and time-consuming. Gateway provides the <span style="font-style: italic;">dynamic site creation</span> feature that enables you to accelerate the site definition process and exchange files with unrecognized client stations.

When you submit a Transfer Request for which no defined Remote Site exists, Gateway dynamically creates a site that is based on one of the <span style="font-style: italic;">Template Sites</span> provided with the product. A Template Site is like any Remote Site, but some of its protocol and network attributes remain empty.

When Gateway dynamically creates a Site, the lifetime of the Site continues as long as there is a reference to the Site in an active Request or in one of the records contained in the Mailbox (repository of transfer records). If no Requests or Request records are associated with this Site at the end of the session, Gateway automatically deletes the dynamic Site.

Gateway automatically creates several Template Sites when you install the product. For example:

-   TFTP (for generic access from FTP clients)
-   THTTP (for generic access from HTTP clients)
-   TFTP\_HTTP (for generic access from clients using either HTTP or FTP protocol)
-   TODT (for generic access from OFTP clients)
-   TAS2 (for generic access from AS2 clients)

Additionally, Gateway provides a set of Template Sites for generic access to servers (for example, when using PassPort PM):

-   AS2
-   AS3
-   ETB3
-   ETB5
-   FTP
-   HTTP
-   ODT
-   PEL
-   PHSD
-   PHSE
-   SFTP
-   RosettaNet

At the protocol connection level, Gateway analyzes the CGateGroup definition and checks whether a Template Site is specified. If the connection requires the use of a Template Site, Gateway:

-   Dynamically creates a Remote Site based on the relevant Template definition
-   Uses the received connection parameters to complete the Site definition

[Next topic](../ov_applications)

Related topics

[About Site objects](../../managing_partners_start_here/sites_start_here)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
