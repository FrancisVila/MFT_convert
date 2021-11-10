{
    "title": "OFTP (Odette)",
    "linkTitle": "OFTP (Odette)",
    "weight": "180"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Protocols

## About OFTP

[OFTP](#oftp_intro)

[Gateway objects used for OFTP](#gw_objects)

[OFTP services](#oftp_services)

[How OFTP processing works](#oftp_processing)

<span id="oftp_intro"></span>

### OFTP Introduction

OFTP (Odette File Transfer Protocol) is an end-to-end protocol designed to transfer files between two partners, irrespective of the network support, hardware, and software architecture of the host computers.

Gateway implements RFC5024, the Internet standard specification for OFTP. It supports OFTP versions R2.0 and all preceding versions (R1.2, R1.3 and R1.4).

<span id="gw_objects"></span>

### Gateway objects used for OFTP

#### Site

In Gateway, the Site represents a communication entity.

A Local Site represents the communication entity on the local platform, while a Remote Site represents the communication entity on the remote platform. Each Site is characterized by a set of attributes such as:

-   Protocol Identifier (for example; OFTP SSID and password)
-   Physical network address (IP address)
-   Protocol session parameters (Data Exchange buffer size, send/receive capability, restart capability, flow control windows size, secured authentication, and so on)
-   Authentication certificate

OFTP allows data transfers in both directions: the Site initiating the connection establishment is termed <span style="font-style: italic;">Initiator</span>, the other is <span style="font-style: italic;">Responder</span>. The Site sending the data is termed the <span style="font-style: italic;">Sender</span>, the other is the <span style="font-style: italic;">Receiver</span>. Each Site has one of the following roles:

-   Initiator/Sender
-   Initiator/Receiver
-   Responder/Sender
-   Responder/Receiver

You can define as many Local Sites and Remote Sites as required.

#### Trading Partner

A Trading Partner is the original file sender or the final file receiver (destination).

A <span style="font-weight: bold;">local</span> Trading Partner is located on the local platform. A <span style="font-weight: bold;">remote</span> Trading Partner is located on the remote platform.

In OFTP, the Trading Partner is essentially associated with file security services (file signature, file encryption, file compression, and signed end-to-end response). Each Trading Partner has a set of attributes concerning these services, such as:

-   Trading Partner ID (for example OFTP SSID)
-   Signing certificate and algorithm to use
-   Encryption certificate and algorithm to use
-   Compress algorithm to apply
-   Constraints on the required file security

#### Application

An Application object is used to indicate the file attributes of the transmitted file and any possible desired transformation (transcoding, padding, and so on) to apply to the data before its transmission to the underlying network. Its main purpose is to allow Gateway to transform a local platform-specific physical file into a platform-independent OFTP virtual file for transmission or vice versa.

<span id="oftp_services"></span>

### OFTP services

#### Supported OFTP functions

OFTP provides the following functions:

-   File transmission and reception
-   Transfer restart
-   Data compression
-   Change Direction (CD)
-   Flow control
-   End-to-End-Response (EERP) – signed and non-signed
-   Mutual authentication
-   File security services (encryption, signature, compression)

The following table describes each of these functions and indicates the parameters to set for the required Gateway objects.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Function</p>         </th>
<th class="HeadE-Column1-Header1"><p>Description</p>         </th>
<th class="HeadD-Column1-Header1"><p>Gateway object &amp; parameter</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>File transmission</p>         </td>
         <td><p>To transfer data, you must first establish a logical link with the remote partner.</p>         </td>
         <td><p>Remote Site:</p>
<p><span style="font-weight: bold;">Role</span>: Select <span style="font-style: italic;">Initiator/Receiver</span> or <span style="font-style: italic;">Responder/Receiver</span></p>         </td>
      </tr>
      <tr>
         <td><p>File reception</p>         </td>
         <td><p>Remote Site:</p>
<p><span style="font-weight: bold;">Role</span>: Select <span style="font-style: italic;">Initiator/Sender</span> or <span style="font-style: italic;">Responder/Sender</span>.</p>         </td>
      </tr>
      <tr>
         <td><p>Transfer restart</p>         </td>
         <td><p>You can restart a transfer that is interrupted before completion. Interruption closes the file and disables the protocol and network connections. The Initiator always initiates the restart, and the Responder decides on the synchronization point from which to resume the transfer.</p>         </td>
         <td><p>Remote Site:</p>
<p>Select the <span style="font-weight: bold;">Restart allowed</span> option.</p>         </td>
      </tr>
      <tr>
         <td><p>Data compression</p>         </td>
         <td><p>OFTP provides horizontal data compression (suppression of repeated characters in a record).</p>         </td>
         <td><p>Remote Site:</p>
<p>Select the <span style="font-weight: bold;">Compression allowed</span> option.</p>         </td>
      </tr>
      <tr>
         <td><p>Change Direction (CD)</p>         </td>
         <td><p>Enables you to change the transfer direction dynamically. CD can be seen as a <span style="font-style: italic;">token</span> exchanged between partners. The protocol uses the token to change the direction of file transmission within a session, reversing the roles of the partners involved (Sender becomes Receiver, and Receiver becomes Sender). Only the partner with the token (the Initiator) has the right to send a file (to the Responder).</p>
<p>The OFTP file transfer stack in Gateway is half duplex, which means that the same Site can be used for consecutive file transfers in both directions.</p>
<p>Gateway connects as Initiator/Sender (as defined by the protocol) and follows with a Change Direction command that allows the Responder to send a file.</p>         </td>
         <td><p>Transfer Request:</p>
<p>To receive a transfer in Initiator mode, you must specify <span style="font-weight: bold;">Mode</span> = <span style="font-style: italic;">Initiator</span> and <span style="font-weight: bold;">Direction</span> = <span style="font-style: italic;">Receive</span>.</p>         </td>
      </tr>
      <tr>
         <td><p>Flow control</p>         </td>
         <td><p>OFTP uses a <span style="font-weight: bold;">Credit</span> feature as an acknowledgment mechanism for regulating data flow. The credit limit specifies the number of Data Exchange Buffers that can be sent before the Initiator has to wait for a <span style="font-weight: bold;">Credit</span> command from the Responder.</p>         </td>
         <td><p>Remote Site:</p>
<p>Credit limit is negotiated in the start session phase, and defined via the <span style="font-weight: bold;">Network credit</span> parameter.</p>         </td>
      </tr>
      <tr>
         <td><p>End-to-End Response (EERP)</p>         </td>
         <td><p>An OFTP session has two possible EERP styles: French and International. These describe the position of the destination and originator fields in the EERP:</p>
<ul>
<li>French mode: the originator field precedes the destination field</li>
<li>International mode: the destination field precedes the originator field</li>
</ul>
<p>There are two methods of sending the EERP:</p>
<ul>
<li>Automatic EERP sending by its final destination can be activated via the <span style="font-weight: bold;">acknowledgment option</span> parameter in the Remote Site.</li>
<li>Manual EERP sending can be initiated via submitting an EERP request through API, command line or GUI.</li>
</ul>         </td>
         <td><p>Remote Site:</p>
<p>Set the <span style="font-weight: bold;">EERP Style</span> to <span style="font-style: italic;">French</span> or <span style="font-style: italic;">International</span>.</p>
<p>Set the <span style="font-weight: bold;">acknowledgment option</span> to <span style="font-style: italic;">By monitor</span> or <span style="font-style: italic;">By user</span> to activate automatic EERP sending by final destination.</p>         </td>
      </tr>
      <tr>
         <td><p>Mutual authentication</p>         </td>
         <td><p>Only for OFTP R2.0 or higher.</p>
<p>Enables mutual authentication of the Initiator and Responder.</p>         </td>
         <td><p>Local Site <span style="font-weight: bold;">and</span> Remote Site:</p>
<p>Specify the authentication certificate to use in <span style="font-weight: bold;">Authentication certificate: Type</span> and <span style="font-weight: bold;">Name</span>.</p>         </td>
      </tr>
      <tr>
         <td><p>File security</p>         </td>
         <td><p>Only for OFTP R2.0 or higher.</p>
<p>Enables user payload to be signed, encrypted, and/or compressed by the sender and the payload signature to be verified, decrypted and/or decompressed by the receiver.</p>         </td>
         <td><p>Trading Partner:</p>
<p>Define a Trading Partner for the sender and the receiver with appropriate security parameters.</p>         </td>
      </tr>
   </tbody>
</table>

#### Session establishment

The transfer begins with the physical connection of two Sites, using the network address information defined in the Remote Site.

Once the network connection is established, the protocol session follows. During this phase, the Initiator and Responder send their identification and password in turn to mutually identify themselves.

#### Session secured authentication

If the Remote Site is OFTP R2.0 or higher, and an authentication certificate has been specified, OFTP continues with the mutual authentication phase.

Using the Initiator's public authentication certificate key, the Responder sends an encrypted challenge to the Initiator. The Initiator decrypts this challenge with its own authentication certificate, and sends back the decrypted challenge to authenticate itself.

The process is then repeated but this time to authenticate the Responder. Using the Responder's authentication certificate, the Initiator sends an encrypted challenge to the Responder. The Responder decrypts this challenge with its own authentication certificate, and sends back the decrypted challenge to authenticate itself.

#### File security services

The actual file transfer starts with a file identification phase, where the sender specifies the files characteristics, its originator and its destination, and whether any file security services are in use.

The user payload (file to be transferred) can be secured via file security services. The sender can ask for the file to be signed, encrypted, and/or compressed before its transmission. Upon reception, the receiver can automatically verify the payloads signature, decrypt and/or decompress its content.

You can only use file security if:

-   The Remote Site supports OFTP R2.0 or higher
-   The originator and destination are predefined Trading Partners

#### Transfer identification

OFTP uses the following information to uniquely identify a transfer:

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Parameter</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>File name</p>         </td>
         <td><p>26-character string associated with each transfer</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Date</span> and <span style="font-weight: bold;">Time</span></p>         </td>
         <td><p>Date and time of the Transfer Request</p>         </td>
      </tr>
      <tr>
         <td><p>Destination</p>         </td>
         <td><p>Protocol name of the receiver Site</p>         </td>
      </tr>
      <tr>
         <td><p>Originator</p>         </td>
         <td><p>Protocol name of the sender Site</p>         </td>
      </tr>
   </tbody>
</table>

#### File and transfer attributes

The file contents are transmitted over the network in data blocks that you define in the Application object. Automatic code conversion of the file contents can be carried out if required in the Application object.

#### Routing

OFTP provides automatic Store-and-Forward, allowing a transfer from one end Site to another via intermediate Sites. In other words, if the current file receiver is not the final destination, the file can be automatically routed to the next node. With Store-and-Forward, an end-to-end transfer acknowledgment is supplied (via an EERP command) by the final destination to notify the initial sender that the file has reached its final destination.

#### File transfer phases

OFTP processes file transfers in the following sequence:

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>1</p>         </td>
         <td><p>Protocol connection</p>
<p>After the establishment of the network connection, the Responder sends an OFTP Ready Message. The Initiator sends its identification code and password to identify itself. The Responder then identifies itself in the same way.</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Authentication</p>
<p>This phase only applies to OFTP R2.0.</p>
<p>During the authentication phase, Initiator and Responder mutually authenticate each other using their respective authentication certificates.</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Selection of the information set to be transferred</p>
<p>Requested by the Initiator, and validated and negotiated by the server. The selection phase incorporates file-opening services.</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Data transfer</p>
<p>After selection, the data is sent with a header and flow control regulation, if requested.</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>End of transfer</p>
<p>When the data is sent, a command containing checking information (including number of records, and bytes) informs the receiver of the end of data transfer. The receiver checks the validity of the information received and then accepts or rejects the file. The end of transfer phase incorporates file closing and de-selection services.</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Protocol connection release</p>
<p>Initiated by the sender, after an end of transfer, Change Direction, or EERP protocol message.</p>         </td>
      </tr>
   </tbody>
</table>

In a typical file transfer sequence, phases 3 to 5 are repeated until all the files are transferred.

#### How to use a Gateway Application object with OFTP

At the beginning of the transfer, OFTP sends a start file identification command (SFID) comprising two text fields, FILE DATASET NAME and USER MESSAGE, available for use by the client Application. As other user Applications may already reserve these two fields, Gateway supplies the user exit function [ExitOdtGetAppli()](../../customizing_gw_about/user_exits_about/user_exits_internal#ExitOdtGetAppli) as an alternative for transmitting the Application name to the receiver.

#### Summary of methods to transmit the Application name

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Application method</p>         </th>
<th class="HeadE-Column1-Header1"><p>Application name is retrieved from</p>         </th>
<th class="HeadD-Column1-Header1"><p>Comment</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>User message field</p>         </td>
         <td><p>USER MESSAGE field of the SFID command</p>         </td>
         <td><p>If the Application transmitted with the SFID command does not exist, the Transfer Request is rejected.</p>         </td>
      </tr>
      <tr>
         <td><p>File name</p>         </td>
         <td><p>FILE DATASET NAME field of the SFID command</p>         </td>
      </tr>
      <tr>
         <td><p>User exit</p>         </td>
         <td><p>Exit function</p>         </td>
         <td><p>Use this method when <span style="font-weight: bold;">User message field</span> and <span style="font-weight: bold;">File name</span> are not available.</p>         </td>
      </tr>
   </tbody>
</table>

Specify the method to use via the Remote Site <span style="font-weight: bold;">Application method</span> (<span class="code">-get\_appli\_method</span>) parameter.

<span id="partner_identification"></span>

#### OFTP partner identification

OFTP partner identification uses a structure based on the ISO - IS6523 specifications. The SIO (Structure for the Identification of Organization) is given in the table below. The format is not mandatory, but you must complete the <span style="font-weight: bold;">Protocol identifier</span> field (<span class="code">-proto\_ident</span> parameter) in the Remote Site.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Field</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>OFTP Identifier</p>         </td>
         <td><p>Value <span style="font-weight: bold;">O</span> (1 byte)</p>         </td>
      </tr>
      <tr>
         <td><p>Organization Identifier:</p>
<ul>
<li>ICD (International Code Designator)</li>
<li>Organization Code (*)</li>
<li>CSA (Computer Sub Address)</li>
</ul>
<p>(*) Code provided by the OFTP codification Group (Group 7)</p>         </td>
         <td><p>Generally, the company registration number:</p>
<ul>
<li>4 bytes (numeric)</li>
<li>14 bytes (A to Z, 0 to 9, space and hyphen)</li>
<li>6 bytes (at the discretion of the company)</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

You can use this structure in prefixed or non-prefixed notation. Non-prefixed notation comprises only the Organization Code and the CSA.

##### Examples

prefixed notation: O1207SOPRA-PARIS UNIX12

non-prefixed notation: SOPRA-PARIS UNIX12

<span id="oftp_processing"></span>

## How OFTP processing works

#### OFTP protocol messages

OFTP protocol messages comprise commands and responses called File Protocol Data Units (FPDUs). Each FPDU starts with a single ASCII character representing its identification, followed by the fields defined by the OFTP protocol. The following table lists the OFTP FPDUs:

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>OFTP FPDU</p>         </th>
<th class="HeadE-Column1-Header1"><p>Meaning</p>         </th>
<th class="HeadE-Column1-Header1"><p>Header (ASCII)</p>         </th>
<th class="HeadE-Column1-Header1"><p>Sent by</p>         </th>
<th class="HeadD-Column1-Header1"><p>Usage</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>SSRM</p>         </td>
         <td><p>Ready Message</p>         </td>
         <td><p>I</p>         </td>
         <td><p>Responder</p>         </td>
         <td><p>Notify that server is ready</p>         </td>
      </tr>
      <tr>
         <td><p>SSID</p>         </td>
         <td><p>Identification Password &amp; Profile</p>         </td>
         <td><p>X</p>         </td>
         <td><p>Initiator &amp; Responder</p>         </td>
         <td><p>Identification and protocol negotiations</p>         </td>
      </tr>
      <tr>
         <td><p>CD</p>         </td>
         <td><p>Change Direction</p>         </td>
         <td><p>R</p>         </td>
         <td><p>Sender</p>         </td>
         <td><p>Change session direction</p>         </td>
      </tr>
      <tr>
         <td><p>ESID</p>         </td>
         <td><p>End of Session</p>         </td>
         <td><p>F</p>         </td>
         <td><p>Sender</p>         </td>
         <td><p>Terminate session</p>         </td>
      </tr>
      <tr>
         <td><p>SFID</p>         </td>
         <td><p>Start File Information</p>         </td>
         <td><p>H</p>         </td>
         <td><p>Sender</p>         </td>
         <td><p>Start file transfer</p>         </td>
      </tr>
      <tr>
         <td><p>SFPA</p>         </td>
         <td><p>Send File Positive Answer</p>         </td>
         <td><p>2</p>         </td>
         <td><p>Receiver</p>         </td>
         <td><p>Acknowledge file transfer</p>         </td>
      </tr>
      <tr>
         <td><p>SFNA</p>         </td>
         <td><p>Send File Negative Answer</p>         </td>
         <td><p>3</p>         </td>
         <td><p>Receiver</p>         </td>
         <td><p>Refuse file transfer</p>         </td>
      </tr>
      <tr>
         <td><p>DATA</p>         </td>
         <td><p>File Data</p>         </td>
         <td><p>D</p>         </td>
         <td><p>Sender</p>         </td>
         <td><p>Send file data</p>         </td>
      </tr>
      <tr>
         <td><p>EFID</p>         </td>
         <td><p>End of File Information</p>         </td>
         <td><p>T</p>         </td>
         <td><p>Sender</p>         </td>
         <td><p>End file transfer</p>         </td>
      </tr>
      <tr>
         <td><p>EFPA</p>         </td>
         <td><p>End of File Positive Answer</p>         </td>
         <td><p>4</p>         </td>
         <td><p>Receiver</p>         </td>
         <td><p>Acknowledge file transfer</p>         </td>
      </tr>
      <tr>
         <td><p>EFNA</p>         </td>
         <td><p>End of File Negative Answer</p>         </td>
         <td><p>5</p>         </td>
         <td><p>Receiver</p>         </td>
         <td><p>Refuse end of file transfer</p>         </td>
      </tr>
      <tr>
         <td><p>CDT</p>         </td>
         <td><p>Set Credit</p>         </td>
         <td><p>C</p>         </td>
         <td><p>Receiver</p>         </td>
         <td><p>Release data flow</p>         </td>
      </tr>
      <tr>
         <td><p>EERP</p>         </td>
         <td><p>End-to-End Response</p>         </td>
         <td><p>E</p>         </td>
         <td><p>Receiver</p>         </td>
         <td><p>Acknowledge file transfer from end to end</p>         </td>
      </tr>
      <tr>
         <td><p>RTR</p>         </td>
         <td><p>Ready To Receive</p>         </td>
         <td><p>P</p>         </td>
         <td><p>Receiver</p>         </td>
         <td><p>Acknowledge previous EERP</p>         </td>
      </tr>
      <tr>
         <td><p>SECD</p>         </td>
         <td><p>Security Change Direction</p>         </td>
         <td><p>J</p>         </td>
         <td><p>Initiator &amp; Responder</p>         </td>
         <td><p>CD during authentication phase</p>         </td>
      </tr>
      <tr>
         <td><p>AUCH</p>         </td>
         <td><p>Authentication challenge</p>         </td>
         <td><p>A</p>         </td>
         <td><p>Initiator &amp; Responder</p>         </td>
         <td><p>Sending an authentication challenge</p>         </td>
      </tr>
      <tr>
         <td><p>AURP</p>         </td>
         <td><p>Authentication Response</p>         </td>
         <td><p>S</p>         </td>
         <td><p>Initiator &amp; Responder</p>         </td>
         <td><p>Sending an authentication response</p>         </td>
      </tr>
      <tr>
         <td><p>NERP</p>         </td>
         <td><p>Negative End-to-End Response</p>         </td>
         <td><p>N</p>         </td>
         <td><p>Receiver</p>         </td>
         <td><p>Negatively acknowledge file transfer from end to end</p>         </td>
      </tr>
   </tbody>
</table>

#### Typical OFTP protocol FPDU exchange

The following is a summary of a typical OFTP protocol FPDU exchange for sending a file with an end-to-end acknowledgment:

<table>
         
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Site A</p>         </th>
<th class="HeadE-Column1-Header1"><p>Network</p>         </th>
<th class="HeadE-Column1-Header1"><p>Site B</p>         </th>
<th class="HeadD-Column1-Header1"><p>Comments</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>NET_CON_REQ</p>
<p>NET_CON_CONF</p>         </td>
         <td><p>----&gt;</p>
<p>&lt;----</p>         </td>
         <td><p>NET_CON_IND</p>
<p>NET_CON_RESP</p>         </td>
         <td><p>Network connection.</p>         </td>
      </tr>
      <tr>
         <td><p> </p>
<p> </p>
<p>SSID (Initiator)</p>
<p> </p>         </td>
         <td><p> </p>
<p>&lt;----</p>
<p>----&gt;</p>
<p>&lt;----</p>         </td>
         <td><p> </p>
<p>SSRM</p>
<p> </p>
<p>SSID (Responder)</p>         </td>
         <td><p>A is sender, B is receiver.</p>
<p>Receiver is ready.</p>
<p>Sender sends ID.</p>
<p>Receiver replies with ID.</p>         </td>
      </tr>
      <tr>
         <td><p>SECD</p>
<p> </p>
<p>AURP</p>         </td>
         <td><p><span class="code">----&gt;</span></p>
<p>&lt;----</p>
<p>----&gt;</p>         </td>
         <td><p> </p>
<p>AUCH</p>
<p> </p>         </td>
         <td><p>Start Initiator authentication.</p>
<p>Send encrypted challenge.</p>
<p>Send back decrypted challenge.</p>         </td>
      </tr>
      <tr>
         <td><p> </p>
<p>AUCH</p>
<p> </p>         </td>
         <td><p><span><span class="code">&lt;----</span></span></p>
<p>----&gt;</p>
<p>&lt;----</p>         </td>
         <td><p>SECD</p>
<p> </p>
<p>AURP</p>         </td>
         <td><p>Start Responder authentication.</p>
<p>Send encrypted challenge.</p>
<p>Send back decrypted challenge.</p>         </td>
      </tr>
      <tr>
         <td><p>SFID</p>
<p> </p>         </td>
         <td><p>----&gt;</p>
<p>&lt;----</p>         </td>
         <td><p> </p>
<p>SFPA</p>         </td>
         <td><p>File transmission request.</p>
<p>Receiver accepts it.</p>         </td>
      </tr>
      <tr>
         <td><p>DATA</p>
<p>DATA</p>
<p> </p>
<p>DATA</p>
<p>DATA</p>
<p> </p>
<p>DATA</p>         </td>
         <td><p>----&gt;</p>
<p>----&gt;</p>
<p>&lt;----</p>
<p>----&gt;</p>
<p>----&gt;</p>
<p>&lt;----</p>
<p>----&gt;</p>         </td>
         <td><p> </p>
<p> </p>
<p>CDT</p>
<p> </p>
<p> </p>
<p>CDT</p>
<p> </p>         </td>
         <td><p>Sender sends file data and waits for credit responses from Receiver.</p>         </td>
      </tr>
      <tr>
         <td><p>EFID</p>
<p> </p>
<p> </p>
<p>CD</p>         </td>
         <td><p>----&gt;</p>
<p>&lt;----</p>
<p> </p>
<p>----&gt;</p>         </td>
         <td><p> </p>
<p>EFPA (<span style="font-weight: bold;">change_dir</span>=<span style="font-style: italic;">Yes</span>)</p>
<p> </p>
<p> </p>         </td>
         <td><p>Sender informs the partner of the end of data transmission.</p>
<p>Receiver accepts end of transfer and requests a Change Direction to send end-to-end acknowledgment.</p>
<p>Then sender can only change direction or close session.</p>
<p>A becomes receiver, B becomes sender.</p>         </td>
      </tr>
      <tr>
         <td><p> </p>
<p>RTR</p>
<p> </p>         </td>
         <td><p>&lt;----</p>
<p>----&gt;</p>
<p>&lt;----</p>         </td>
         <td><p>EERP</p>
<p> </p>
<p>CD</p>         </td>
         <td><p>B sends acknowledgment (EERP).</p>
<p>A sends RTR (Ready To Receive).</p>
<p>Then B has nothing further to do, so it changes direction.</p>
<p>A becomes sender, B becomes receiver.</p>         </td>
      </tr>
      <tr>
         <td><p>ESID</p>
<p>NET_DISCON_IND</p>         </td>
         <td><p>----&gt;</p>
<p>&lt;----</p>         </td>
         <td><p> </p>
<p>NET_DISCON_REQ</p>         </td>
         <td><p>A has nothing further to do either, so it closes session and B closes network connection.</p>         </td>
      </tr>
   </tbody>
</table>

 

#### OFTP transfer phases

There are six phases involved:

-   Start session
-   Authentication
-   Start file transfer
-   File transfer
-   End of file transfer
-   Change Direction (optional)

##### 1. Start session phase

The start session phase begins after the network connection. The Site that initiates the network connection is referred to as the <span style="font-style: italic;">Initiator</span> while its corresponding partner Site is the <span style="font-style: italic;">Responder</span>.

-   The Responder sends an SSRM command, notifying the Initiator that it is ready.
-   The Initiator sends a SSID command to identify itself.
-   The Responder checks the incoming SSID from the Initiator, negotiates the parameters for the protocol, then sends its SSID command to identify itself.

##### 2. Authentication phase

This phase only applies to OFTP R2.0.

-   The Initiator sends an SECD to the Responder.
-   The Responder sends an AUCH (encrypted challenge) to the Initiator.
-   The Initiator decrypts the AUCH and sends an AURP to authenticate itself.
-   The Responder sends an SECD to the Initiator.
-   The Initiator sends an AUCH (encrypted challenge) to the Responder.
-   The Responder decrypts the AUCH and sends an AURP to authenticate itself.

The session is now ready for the exchange: data transfer, end-to-end acknowledgment, or Change Direction.

##### 3. Start file transfer phase

To start the file transfer, the:

-   Initiator sends an SFID command.
-   Responder accepts the Transfer Request by sending an SFPA response.

After the start file transfer phase, data flows from the Initiator (sender) to the Responder (receiver).

##### 4. File transfer phase

During the file transfer phase, the Initiator can send a specific number of Data Exchange Buffers before it receives acknowledgment from the Responder. This number is negotiated in the start session phase, as the <span style="font-style: italic;">credit</span>. For example, if the credit value is set to 4, the Initiator can send four DATA commands.

-   The Initiator waits for the Responder to release the data flow by sending the CDT response, before it can send additional DATA commands.
-   On receiving the CDT response, the Initiator sends DATA commands until it reaches either the end of file, or the credit value.

##### 5. End of file transfer phase

When all data is transmitted, the Initiator must send a command to indicate the end of the file transfer.

-   The Initiator sends an end-of-file command: EFID.
-   The Responder acknowledges the end of transfer by sending one of the following responses:
    -   EFPA (positive): the file transfer is accepted
    -   EFNA (negative): the file transfer is rejected
    -   EFPA with CD (Change Direction) request.
-   If the Responder returns an EFPA with CD request:
    -   The Initiator must issue a CD command to allow the partner to send an end-to-end response command (EERP)
    -   It does not issue any more commands until it receives the Ready to Receive command (RTR).

##### 6. Change Direction phase

Both the Sender and Receiver can initiate a change in the file transfer direction. If accepted, the Sender becomes the Receiver and vice versa.

-   The sender issues a CD command to change the file transfer direction. The sender can issue a CD command after each file transfer.  
    You can activate a different connection hold timer by setting <span class="code">odt\_different\_conn\_hold\_timers</span> to 1. In this case, the connection will be closed by a timer set by the <span class="code">odt\_conn\_hold\_send\_delay</span> setting.
-   The receiver sends an EFPA response with the Change Direction field set to <span style="font-style: italic;">Yes</span> to request a change in the file transfer direction. On receiving this command, the sender must issue a CD command or close the session.

Related topics

[Configuring Gateway for OFTP](oftp_config)

[Submitting an OFTP Transfer Request](oftp_submitting_transfer)

[Monitoring an OFTP transfer](oftp_monitoring_transfer)

[OFTP trace example](oftp_trace_example)

[OFTP protocol log messages (ODT)](../../log_messages_about/odette_protocol_(odt))

[Internal user exits](../../customizing_gw_about/user_exits_about/user_exits_internal)

[Using PassPort PM with OFTP](oftp_and_passport_pm)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
