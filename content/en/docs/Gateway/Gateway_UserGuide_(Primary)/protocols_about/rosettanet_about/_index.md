{
    "title": "RosettaNet",
    "linkTitle": "RosettaNet",
    "weight": "230"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Protocols

[The RosettaNet protocol](#rosettanet_protocol)

[Gateway/RosettaNet message processing](#message_processing)

<span id="rosettanet_protocol"></span>

## About the RosettaNet protocol

RosettaNet is an exchange protocol that provides standards for business exchanges.

Within RosettaNet, there are sets of RosettaNet <span style="font-style: italic;">specifications</span>. These <span style="font-style: italic;">RosettaNet Implementation Framework</span> (RNIF) specifications describe how documents can be packaged to create RosettaNet envelopes. The RosettaNet envelope can then be transmitted over the network, for example the Internet.

So far, two versions of the RNIF specifications have been published: RNIF V1.1 and RNIF V2.0. While both of these versions rely on XML as the standard format for payloads, the resulting envelopes differ slightly, and are called:

-   RosettaNet Objects for RNIF V1.1
-   RosettaNet Messages for V2.0

For more information on RosettaNet and RNIFs, refer to the [www.rosettanet.org](http://www.rosettanet.org) website.

<span id="About_RosettaNet_PIP"></span>

### RosettaNet PIP

Before you can understand how RosettaNet functions, you first need to become familiar with the concept of PIPs. A PIP, Partner Interface Process, is a set of processes that defines business exchanges between trading partners. This set of generic, standardized processes specifies business document structure and format for trading partners.

A variety of PIP are available, each of which outlines a different business process exchange. The user selects the PIPs that are appropriate for his business needs. RosettaNet then provides the packaging and security.

For example, suppose that Business Partner A wants to send a Purchase Order to Business Partner B using RosettaNet. (This exchange is described in detail in the PIP 3A4 <span style="font-style: italic;">Request Purchase Order</span>.) According to this particular PIP, a process similar to the following sequence could occur:

-   Partner A sends a <span style="font-style: italic;">Purchase Order Request</span> message to Partner B
-   Partner B must acknowledge the order within 2 hours (if not, Partner A resends the Purchase Order)
-   Partner B responds to Partner A by sending back a <span style="font-style: italic;">Purchase Order Confirmation</span> message within the predefined time period
-   Partner A acknowledges the response by sending an ACK, <span style="font-style: italic;">Receipt Acknowledgment Message</span>, to Partner B

The precise actions that occur depend on the specific PIP that these Business Partners chose. Additionally, for each of the above actions, the PIP can include information as to the level of security to be used, need for a signature, security for the message contents, need for an acknowledgment, time frames for these exchanges, and so on. In this sense, each PIP is unique and serves a separate business need.

### RosettaNet exchanges

A RosettaNet exchange revolves around the concept of PIPs, as described in the previous section. The RNIF, RosettaNet Implementation Framework, deals with 'packaging' the PIP. This packaging process consists of encapsulating the XML-formatted PIP, the XML headers, and any attachments in a in a MIME package. When the security is added to this package, you have a RosettaNet message.

After the RosettaNet message is encapsulated and encrypted, it is then sent over the network. When it is received, the message is unpacked and decrypted. If the message contains an attachment, the receiver saves the attachment. Depending on the PIP and trading partner, the request is processed and a message is returned to the message originator.

All of these processes occur between defined Trading Partners. In this Trading Partner environment, RosettaNet PIPs aid in business transactions, and help determine the best course of action between business partners.

### RosettaNet and Gateway

RosettaNet functions in Gateway at the transport layer. Gateway adds security and HTTP or SMTP/POP3 formatting. (Gateway does not manage or process PIPs.) It is one product of the <span class="mc-variable axway_variables.Platform_or_Suite_Long_Name variable">Axway Platform</span> offering RosettaNet services.

Using Axway products to deploy a full RosettaNet solution is outside the scope of this document. For more information on how to use Axway products with RosettaNet, contact your Axway Sales Representative at [www.axway.com](http://www.axway.com).

<span id="message_processing"></span>

## Gateway/RosettaNet message processing

This section explains the message processing that is performed by Gateway when a RosettaNet message arrives:

When an incoming transfer arrives, Gateway performs the following steps:

-   Removes protocol envelope (HTTP/SMTP)
-   Removes S/MIME envelope
-   Performs a validation process

### The XFBCONN interface

When applicable, the XFBCONN interface is used by Gateway to:

-   Notify Integrator of the outgoing messages processing status
-   Inform Integrator incoming message arrivals, and their associated parameters

For details of the functioning of the Integrator product, refer to the Axway Integrator documentation.

<span id="Outbound_ROSETTANET_message_processing"></span>

### Outgoing RosettaNet message processing

#### Outgoing RosettaNet Request/Response

A RosettaNet message request is processed in multiple phases:

1.  The transfer request undergoes validation checking (checks only the Preamble, DeliveryHeader and ServiceHeader). If the check is unsuccessful, the transfer is returned to the caller.
2.  The transfer request is accepted and queued in the Gateway Mailbox. It is then scheduled for packaging.
3.  After the RosettaNet message is successfully encoded, it is scheduled for network transport. If a communication error occurs, and transfer retry count is exhausted by successive retrials, the transfer is cancelled.
4.  After the message is successfully sent to the partner, the transfer is flagged as ENDED.

<span id="Inbound_ROSETTANET_message_processing"></span>

### Incoming RosettaNet message processing

The processing steps for an incoming RosettaNet message consist of removing the S/MIME envelope, and extracting the RosettaNet component parts and attachments from the package.

The RosettaNet component parts include:

-   &lt;Preamble>
-   &lt;DeliveryHeader> (version dependent)
-   &lt;ServiceHeader>

These elements must be validated for an incoming message. If an error occurs during the validation procedure, the message status is reported. The faulty message is then discarded. If no error occurs during these initial steps, the complete message is constructed as an XML file.

The incoming messaging processing occurs as follows:

1.  For a signed message, the signature envelope is removed and the signature is verified.
2.  The &lt;Preamble> element is extracted and validated.
3.  The &lt;DeliveryHeader> element is extracted and validated.
4.  If the &lt;ServiceHeader> is encrypted, it is decrypted.
5.  The &lt;ServiceHeader> element is extracted and validated.
6.  The &lt;ServiceContent> element is extracted but is not validated.

At this point, Gateway has completed its processing. The message is sent to the next RosettaNet component. The process may continue by interpreting the message, sending a receipt acknowledgment, an exception, a Notification of Failure PIP, a response, and so on.

If a decoding error occurs, the MIME may be incomplete and contain only a partial RosettaNet message. An exception signal is returned to the partner <span style="font-style: italic;">if</span> transport debug headers were sent by the partner, and are allowed by the local security policy. If transport debug headers were not sent by the partner, no exception signal is sent.

Related topics

[Configuring the RosettaNet environment](rosettanet_config)

[Using RosettaNet](rosettanet_using)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
