{
    "title": "EDIINT",
    "linkTitle": "EDIINT",
    "weight": "220"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Protocols

[EDIINT](#ediint_intro)

[General operating principles](#operating_principles)

[Generic EDIINT transfer example](#transfer_example)

<span id="ediint_intro"></span>

## EDIINT Introduction

### What is EDI?

<span style="font-weight: bold;">E</span>lectronic <span style="font-weight: bold;">D</span>ata <span style="font-weight: bold;">I</span>nterchange (<span style="font-weight: bold;">EDI</span>) is a set of protocols for performing data exchanges between business organizations. EDI provides the processes that enable companies to buy and sell material, and to trade information. Businesses can use EDI, for example, to transfer:

-   Purchase orders
-   Invoices
-   Shipping notices
-   Insurance claims
-   Medical records
-   Clinical data
-   Retail reports
-   CAD drawings

Historically, companies who use EDI have relied on Value Added Networks (VANs) to exchange information. As the use of a VAN implies per transaction or per volume billing rates, the deployment of EDI in a high-volume business-exchange environment can be very expensive. The increased development of large and cost-free Internet bandwidth has led to the application of Internet protocols and security standards to the transport of EDI data.

### What is EDIINT?

<span style="font-weight: bold;">E</span>lectric<span style="font-weight: bold;"> D</span>ata<span style="font-weight: bold;"> I</span>nterchange over the<span style="font-weight: bold;"> INT</span>ernet (<span style="font-weight: bold;">EDIINT</span>) is a Working Group of the Internet Engineering Task Force (IETF). This working group is chartered by the IETF to create a set of secure protocols for conducting inter-business information exchanges using Internet protocols.

Businesses that exchange large volumes of documents with partners require solutions that reduce information transfer costs. EDIINT makes use of existing Internet technology to significantly reduce the costs of EDI document transfers between trading partners.

Although EDIINT specifications evolved from EDI, they are not payload specific. EDIINT specifications are transport specifications that you can use to transmit any data as long you use the appropriate MIME content type.

EDIINT exists primarily as a solution for the upgrade of legacy EDI networks from VAN-based technology to the Internet. A major consideration of the IETF in developing EDIINT was ensuring adequate security for exchanges over the Internet. The IETF has invented an acronym to describe the EDIINT security solution, PAIN:

-   <span style="font-weight: bold;">P</span>: Privacy
-   <span style="font-weight: bold;">A</span>: Authentication
-   <span style="font-weight: bold;">I</span>: Integrity
-   <span style="font-weight: bold;">N</span>: Non-repudiation of message reception

To provide these security features, EDIINT encapsulates user data in S/MIME envelopes that enable encryption and signed receipts. Note, that the use of EDIINT security features remains optional. It is possible to transmit user data without applying encryption and/or without requesting or receiving a signed receipt.

### What is an AS?

In EDIINT terminology, <span style="font-weight: bold;">AS</span> stands for <span style="font-weight: bold;">A</span>pplicability <span style="font-weight: bold;">S</span>tatement. An AS is a set of recommendations that shows how to apply existing standards to facilitate secure reliable EDI transport over the Internet. The recommendations include a small number of additions to the existing standards, primarily to provide more precise coordination between the existing standards.

EDIINT has currently produced three sets of AS recommendations:

-   <span style="font-weight: bold;">AS1</span>: The AS1 specifications describe how current Internet standards can be used to achieve document transfers as a mail attachment. AS1 is based on SMTP and POP3. It was the first of the Application Statements to be developed, and does not provide the same level of reliability as AS2 and AS3.  
    AS1 security features include signatures for transferred objects and object-based encryption only.
-   <span style="font-weight: bold;">AS2</span>: The AS2 specifications describe how to package the information in an envelope and transfers the document via HTTP using an S/MIME standard.  
    For AS2, S/MIME provides both authentication and privacy. AS2 provides for an authenticated acknowledgment on reception of a message.  
    Security in AS2 includes signatures for transferred objects, and both session and object encryption.
-   <span style="font-weight: bold;">AS3</span>: The AS3 specifications offers data transfers similar to AS1 and AS2, but performs these transfers using FTP.  
    Security in AS3 includes signatures for transferred objects, and both session and object encryption.

All EDIINT AS versions use TCP/IP as the network-level protocol.

<span id="operating_principles"></span>

## General operating principles

### Message characteristics

EDIINT makes the distinction between the file you transfer using EDIINT protocols and the package that envelops the transferred file. EDIINT encapsulates user data and returned receipts in S/MIME envelopes and assigns headers to enable the handling of the envelope by the intended receiver. The total volume of transferred data, contents and headers combined, is called a <span style="font-style: italic;">message</span>. EDIINT, in fact, is composed of transport protocols that are indifferent to the type of data that is transported.

### Network security

EDIINT protocols enable you to transfer documents over the Internet. To avoid malicious attacks you require a network security strategy, such as the deployment of a firewall.

<span id="EDIINT_Certificates"></span>

### Certificates

To use EDIINT you need to manage security certificates. You have the option between using self-signed certificates or using certificates offered by a Certificate Authority.

Before initializing an EDIINT exchange, the exchange partners must agree on the certificates they will use, and either exchange certificates or agree on a common PKI.

In Gateway, you have the option of using:

-   No certificates
-   A single certificate for signing and encryption operation (on each machine)
-   Dual certificates: one for signing and another for encryption (on each machine)

The following diagram illustrates a dual certificate agreement between two exchange partners. In this case, a complete EDIINT exchange including transfer and receipt generation requires four certificates (with their associated public keys).

![](/Images/Gateway/EDIINT_Certifs_756x616.png)

See the *Security Guide &gt; [Certificates and Keys](#)* for further information (requires login).

For details on how to specify certificates and certificate types for an EDIINT transfer, refer to:

-   [Working with Trading Partner objects](../../managing_partners_start_here/trading_partners_start_here/working_with_trading_partners_(gui))
-   [Working with Trading Partner objects (command line)](../../managing_partners_start_here/trading_partners_start_here/working_with_trading_partners_cli)

### Transport layer protocols

The transport-layer protocol you use with EDIINT depends on the AS version you are using:

-   AS1: SMTP/POP3
-   AS2: HTTP or HTTPS
-   AS3: FTP or FTPS

Gateway includes native processes that handle SMTP/POP3, HTTP, HTTPS FTP and FTPS transfers. However, to execute Gateway transfers using EDIINT, you must activate support for dedicated EDIINT versions of these protocols in the Gateway configuration menu. Additionally, you must specify the EDIINT AS version in the related Site object, Trading Partner object and Transfer Request.

#### Managing service layers in Gateway

To specify the transport layer protocols for a Gateway EDIINT transfer, you create and manage [Site objects](../../ov_gateway/ov_transfer_sites). In your Transfer Request you associate the Site object with a Trading Partner object. The Trading Partner object contains specifications for the S/MIME level handling of the EDIINT message. The following illustration shows the relationship of these two objects and the services they define.

![](/Images/Gateway/EDIINT_Object_Layers_756x412.png)

### Receipts

EDIINT uses S/MIME functions to return reception acknowledgments known as <span style="font-weight: bold;">receipts</span> to the entity from which a transfer originated. The sent message contains information specifying the type of receipt that is to be returned.

Receipt requests always come from the entity that sends the EDIINT message. The returned receipt can be positive or negative.

You can use the Gateway Trading Partner object to specify any of the following receipt types:

-   <span style="font-weight: bold;">None</span>: No signature. This option excludes the possibility of later proof of reception
-   <span style="font-weight: bold;">Signed</span>
-   <span style="font-weight: bold;">Unsigned</span>

<span id="Receipt_synchronization"></span>

#### Synchronous and asynchronous receipt processes

Additionally, in the Trading Partner object, for AS2-type transfers you can choose between synchronous and asynchronous receipt processing:

-   Synchronous receipts: The receiving partner returns a receipt immediately on file reception and unpacking in the same HTTP protocol session, using the standard HTTP response mechanism.

 

![](/Images/Gateway/EDIINT_Synch_Receipt_756x552.png)

 

-   Asynchronous receipts: The receiving partner generates a reception receipt in a protocol session independent of the original HTTP transfer session.

![](/Images/Gateway/EDIINT_AsynchReceip_756x917.png)

#### Managing receipts in Gateway

You manage receipt activation and receipt characteristics via the Gateway Trading Partner object.

#### Monitoring receipts in Gateway

Gateway provides monitoring features that enable you to follow the status of EDIINT receipts. The emission and reception of a receipt is itself a type of transfer. By selecting the transfer record in the Gateway Mailbox that corresponds to the transfer of the receipt, you can view details of the transfer, including status, signature, encryption and signing details.

Refer to [Viewing and managing Mailbox contents](../../transfers_start_here/monitoring_transfers_start_here/viewing_and_managing_mailbox_contents_(gui)).

### Encryption Algorithm

Gateway offers the following data encryption algorithms for EDIINT:

-   <span style="font-weight: bold;">AES-128</span>
-   **AES-256** *(for AS2 only)*
-   **ARC4** *(for AS2 only)*
-   <span style="font-weight: bold;">DES</span>
-   <span style="font-weight: bold;">3DES</span>

In Gateway, you specify the encryption algorithm to use with the transfer, in the Trading Partner object that you associate with the transfer. Alternatively, you can choose not to encrypt the data.

<span style="font-weight: bold;">Note:</span> The partner in the transfer must imperatively support the same encryption algorithm. It is necessary to know before initiating the transfer, which algorithms the partner can use.

#### Managing encryption algorithms in Gateway

You manage encryption algorithms via the Gateway Trading Partner object.

### Signing Algorithm

You can select to sign a file that is transferred via EDIINT, to reinforce the protection of the data integrity and security. The signature coupled with RSA key encryption enables the receiver to confirm that the message effectively came from the sender.

Gateway offers the choice of one of three signing algorithm options:

-   <span style="font-weight: bold;">None</span>: no certificate (default)
-   <span style="font-weight: bold;">SHA1 with RSA</span> (recommended by EDIINT)
-   <span style="font-weight: bold;">MD5 with RSA</span>

In Gateway, you specify the signing algorithm to use for the transfer, in the Trading Partner object that you associate with the transfer.

#### Managing signing algorithms in Gateway

You manage signing algorithms via the Gateway Trading Partner object.

### Compression

In EDIINT, compression reduces the size of a file or group of files in order to reduce transmission time.

Gateway currently offers the ZLIB compression option, which you can activate in the Trading Partner object.

#### Managing compression in Gateway

You manage EDIINT compression via the Gateway Trading Partner object.

<span id="transfer_example"></span>

## Generic EDIINT transfer example

The following example illustrates the sequence of events that occur in a typical EDIINT AS2 or AS3 transfer exchange.

 

![](/Images/Gateway/EDIINTexample_756x510.png)

The illustration shows the main steps of an EDIINT transfer:

1.  The originating Gateway encodes and formats the data to be sent, constructing a MIME-format envelope. During this process, Gateway encrypts and signs the data using standardized S/MIME processes. The resulting S/MIME envelope and its content is an EDIINT data message.
2.  The originating Gateway sends the secured envelope to the target business partner using one of the three following protocols:
    -   SMTP/POP3 for AS1
    -   HTTP or HTTPS for AS2
    -   FTP or FTPS for AS3
3.  The destination application receives the secured EDIINT data message. Before handling the message, the application checks to see that any <span style="font-style: italic;">forcing</span> requirements (predetermined reception requirements) are fulfilled.
4.  The destination application extracts data from the fields of the header and unpacks the data from the envelope, uncompressing and decrypting as necessary. These processes restore the data to its original format.
5.  When the destination application has restored the data, if the originating Gateway has asked for a receipt, the receiving application constructs a receipt. This may be signed by the application that has received the EDIINT data message.
6.  The destination application encrypts and formats the receipt.
7.  The destination application sends the EDIINT receipt back to the originating Gateway via the protocol decided in the Trading Partner Agreement.
8.  The Gateway that originated the EDIINT data message, receives the secured receipt. Before handling the return receipt, the application checks to see that any <span style="font-style: italic;">forcing</span> requirements (predetermined reception requirements) are fulfilled.
9.  Gateway extracts data from the fields of the header and unpacks the receipt from the envelope. If a signature was included in the envelope, Gateway decrypts the signature.

Related topics

[Configuring and using EDIINT](ediint_config)

[Overview: Trading Partners](../../ov_gateway/ov_trading_partners)

[Transfer Examples: EDIINT AS2 transfer](../../transfer_examples/transfer_example_ediint_as2)

[Working with Trading Partner objects](../../managing_partners_start_here/trading_partners_start_here/working_with_trading_partners_(gui))

[Working with Trading Partner objects (command line)](../../managing_partners_start_here/trading_partners_start_here/working_with_trading_partners_cli)

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
