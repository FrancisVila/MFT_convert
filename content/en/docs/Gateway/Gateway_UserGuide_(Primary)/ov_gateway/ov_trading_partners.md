{
    "title": "Trading Partners",
    "linkTitle": "Trading Partners",
    "weight": "130"
}{{< Gateway/componentlongname  >}}: Overview

As described in previous topics, you can use Gateway to transfer files between two or more machines using many different protocols. The processes that Gateway uses to execute a transfer vary according to the protocol that you specify for the transfer. Gateway uses the information contained in different objects to carry out these processes.

Gateway includes a special set of services for the transfer of files via EDIINT (Electronic Data Interchange over the INTernet), S/MIME, RosettaNet, OFTP R2.0 and SWIFTNet.

To transfer a file using EDIINT, the Gateway that originates the transfer performs a set of operations defined by the transport level protocol, and additionally performs compression, signature, encryption and encapsulation operations defined by the S/MIME protocol.

The Gateway that receives the transfer performs the reverse operations to extract the information contained in the body of the message. If necessary, the receiving Gateway then sends a reception acknowledgment known as a *receipt* to the originating Gateway.

To provide Gateway with the information necessary for the transport layer services that support higher level EDIINT and S/MIME services you create Site objects. These objects are identical to the Site objects you might create for standard SMTP/POP3, HTTP or FTP transfers.

Additionally, to provide the information to Gateway necessary for compression, signature, encryption and encapsulation operations you create a *Trading Partner object*.

The following illustration shows the relationship between the services provided at different protocol layers, and shows the Gateway objects that provides information for those services.

 

![](/Images/Gateway/EDIINT_Object_Layers_756x412.png)

To execute an EDIINT or S/MIME transfer between two Gateways you require Trading Partner objects for both the originating and receiving machines.

For each Trading Partner object you create, you can specify the Gateway behavior on sending or receiving an EDIINT or S/MIME transfer.

For locally originating transfers, use the Trading Partner object to specify:

-   Originating machine name
-   Message format:
    -   S/MIME
    -   EDIINT: AS1, AS2 or AS3
    -   RosettaNet
    -   OFTP (for OFTP R2.0 security services)
    -   SWIFTNet
-   Security (signing, encryption type, certificate)
-   Compression characteristics
-   Receipt characteristics

For the reception of EDIINT or S/MIME transfers, use the Trading Partner object to specify:

-   Confirmation of receipt delivery
-   Obligatory signing (yes/no option)
-   Obligatory encryption (yes/no option)

[Next topic](../ov_events)

Related topics

[About EDIINT](../../protocols_about/ediint_about)

[Trading Partner objects](../../managing_partners_start_here/trading_partners_start_here)

 

Links to documentation set for Axway Gateway {{< Gateway/releasenumber  >}}:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
