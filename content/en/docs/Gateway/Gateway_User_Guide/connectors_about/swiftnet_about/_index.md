{
    "title": "SWIFTNet",
    "linkTitle": "SWIFTNet",
    "weight": "230"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Connectors

## SWIFTNet Introduction

SWIFTNet is the SWIFT organization's IP-based network. SWIFTNet services enable the secure and reliable transfer of financial information and transactional data.

Many institutions frequently need to manage separate interfaces, standards and security models for each market infrastructure used, and for various types of communication with correspondents and customers. With SWIFTNet, you connect only once. Single window connectivity delivers a single communications infrastructure to access multiple service providers, correspondents and customers. Other advantages are automation and straight-through processing within a financial organization.

The Gateway/SWIFTNet connector supports the following SWIFTNet services:

-   InterAct messaging
-   FileAct file transfer

### SWIFTNet message types

Originally SWIFT used FIN messaging. More recently, with SWIFTNet, the XML-based InterAct and FileAct message types have been introduced.

#### InterAct

InterAct is SWIFT's interactive messaging service that supports the exchange of messages between two parties.

With InterAct, institutions and communities can exchange messages in an automated and interactive way — an application sends a request message to another application and receives an immediate response message.

Each message exchange consists of a request and a reply message. Request messages usually contain either information to be sent from a sender to a receiver or a request for information which is sent from sender to receiver. Reply messages contain either the confirmation that the receiver has received the sender's message or a reply on a sender's request.

InterAct is used to exchange time-critical and short to medium length messages (such as securities orders, payment instructions) between parties.

Each InterAct message consists of two parts:

-   The <span style="font-style: italic;">payload</span> that contains the business contents, such as an investment funds order
-   The <span style="font-style: italic;">envelope</span> that contains the technical information which is required for the SWIFT network to send the message (such as requester and receiver, PKI information, SnF mode, etc.)

InterAct messages can be validated, for example for XML compliance and correct semantics, within SWIFTNet according to the message specification.

#### FileAct

FileAct allows the secure and reliable transfer of files between parties via SWIFTNet.

FileAct supports tailored solutions for market infrastructure communities, closed user groups and financial institutions. FileAct is particularly suitable for bulk payments, batches of structured financial messages and large reports.

Files are usually created in batch processes and should not be time critical. Files are typically large. There is no validation of FileAct messages. They can be free formatted, even binary data can be transmitted.

### SWIFTNet delivery modes

SWIFTNet provides two different delivery modes:

-   <span style="font-style: italic;">Real Time</span> (RT) mode exchanges messages and files between parties in real time. In this case both sender and receiver have to be connected to the SWIFT network at the same time.
-   <span style="font-style: italic;">Store-and-Forward</span> (SnF) mode allows the sender's message to be stored within the SWIFT network until the receiver is able to receive the message. The sender and receiver do not need to be connected at the same time. SnF relies on queues managed by SWIFT.

### SWIFTNet software

SWIFT provides the following software to connect to SWIFTNet:

-   SWIFTNet Link (SNL). This is the low-level connection software that manages access to SWIFTNet. A client may have more than one instance of SNL for reasons of performance and reliability. SNL connects gateway applications such as SAG to SWIFTNet.
-   SWIFT Alliance Gateway (SAG). SAG acts as concentrator and allows multiple applications to be connected to SWIFTNet. Examples are: automated file transfer, distant applications using SWIFTNet RA (Remote API) and applications using MQ-series queues. Flows coming from SWIFTNet to these applications are routed according to configurable criteria.

### SWIFTNet message and file limitations

Gateway fully supports the SWIFTNet InterAct and FileAct protocols within the size limits established by SWIFT. For the current limits, refer to the official SWIFTNet documentation.

Related topics

[SWIFTNet connector](swiftnet_connector)

[SWIFTNet system recovery](swiftnet_sig_list/swiftnet_system_recovery)

 

More information

Gateway is just part of the Axway Financial Exchange solution. Using Axway products to deploy a full SWIFTNet solution is outside the scope of this document. For more information on Axway products, go to [www.axway.com](http://www.axway.com).

For more information on SWIFTNet, refer to:

-   The SWIFT (Society for Worldwide Interbank Financial Telecommunication) website: [www.swift.com](http://www.swift.com)
-   The SWIFTNet documentation delivered with the product

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
