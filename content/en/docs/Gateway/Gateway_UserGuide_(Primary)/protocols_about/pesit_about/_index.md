{
    "title": "PeSIT Hors SIT",
    "linkTitle": "PeSIT Hors SIT",
    "weight": "190"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Protocols

## About PeSIT Hors SIT

[PeSIT Hors SIT](#pesit_intro)

[How PeSIT Hors SIT processing works](#how_pesit_works)

<span id="pesit_intro"></span>

### PeSIT Hors SIT Introduction

PeSIT Hors SIT (or PeSIT) is an end-to-end public protocol designed to provide a reliable and normalized interface for user applications to exchange files and messages between heterogeneous systems, irrespective of the network communication type.

The PeSIT Hors SIT protocol is used on SNA in LU 6.2, TCP/IP and some proprietary communication networks such as DSA, and SPX/IPX.

There are four standard user profiles in the PeSIT protocol: SIT, Hors SIT, secured Hors SIT.

This section describes the implementation and use of the two standardized versions of the PeSIT Hors SIT protocol:

-   Version D (November 1987) referred to as <span style="font-weight: bold;">PeSIT HS D</span>
-   Version E (July 1989) - referred to as <span style="font-weight: bold;">PeSIT HS E</span>

<span id="PeSIT_common_services"></span>

### PeSIT common services

Both PeSIT HS D and PeSIT HS E provide the following services:

-   File transmission
-   File reception
-   Setting of synchronization points during transfer
-   Restart of interrupted transfers from a synchronization point
-   Dynamic synchronization (during transfer)
-   Temporary suspension of transfer
-   Data compression
-   Generic file selection

#### File transmission

File transmission, also known as file-writing, enables you to transfer data to a remote partner, provided that you have established a logical link between the two users.

#### File reception

File reception, also known as file-reading, enables you to transfer file data from a partner represented by a Remote Site.

#### Setting of synchronization points

The data sender can initiate sequentially numbered synchronization points during the transfer. The data receiver can acknowledge the synchronization points to confirm that the data transferred up to that point has been correctly received and saved. This mechanism is used to restart a transfer after an incident.

When you establish the logical connection between partner Sites, the two Sites can negotiate the following:

-   Synchronization acknowledgment window
-   Interval between synchronization points
-   Whether resynchronization is allowed

#### Restarting interrupted transfers

Transfer restart enables you to restart a transfer interrupted before its completion. The interruption closes the file and disables the protocol and network connections. It is always the Initiator who initiates the restart and the Receiver who decides from which synchronization point the transfer is to be restarted.

#### Dynamic synchronization

Dynamic synchronization allows you to ask the partner to restart the transfer from a previous synchronization point, if an incident was encountered during data transfer. The file remains open during this operation, which can be initiated by either Initiator or Responder.

#### Temporary suspension of transfer

Transfer suspension allows you to suspend the current transfer (closing and de-selecting the file) but retain the active connection with the Remote Site. The suspended transfer will be restarted later.

#### Data compression

Data can be compressed in order to reduce the size of data actually transferred.

Three types of compression are available:

-   Horizontal compression: deletes repeated characters in a logical record
-   Vertical compression: transmits only that data which differs from the previous record
-   Horizontal and vertical compression: combines both of these methods

#### Generic file selection

When an existing file is remotely selected for read access, the file name sent by the Initiator is no longer just a nominative reference. With PeSIT HS E, it may also be a set of criteria that the server uses to select files. File selection can also be generic. The partner Sites are responsible for handling the fact that several files may meet the given selection criteria.

### PeSIT HS E enhancement

In addition to the common PeSIT HS features described above, Gateway supports the following functions for PeSIT HS E only:

-   Two-way transfers over the same logical connection
-   Transmission error control using CRC (Cyclic Redundancy Checking) on each data block
-   Message transfer which enables the transmission of application messages of arbitrary length, or end-to-end response acknowledgment messages
-   Store-and-forward mode with automatic routing from one Site to another via intermediate Sites

#### Two-way transfers over the same logical connection

The PeSIT HS E protocol allows only one file transfer in a given session at a time. Nevertheless, Gateway can perform several concurrent transfers either as:

-   *consecutive* transfers within the same session
-   several *simultaneous* file transfers on *different* sessions, and in both directions

#### Transmission error control

Gateway provides a straightforward, efficient transmission error detection mechanism, CRC, for use over unreliable communication networks. The process involves adding two bytes resulting from a polynomial calculation on this data unit to each protocol unit of data sent.

#### Message transfer

This operation enables items of relatively small information to be exchanged between the Sites. A message is accompanied by a minimum of service information and may, for example, be used to acknowledge the correct processing of a received file.

Gateway enables you to transmit 254-character user messages, unchanged, to the partner Site.

### Transfer and file identification

Gateway associates with each transfer a numeric transfer identifier, which is transmitted by the protocol.

The following parameters identify the file to be transferred (each parameter has a PI, Parameter Identifier)

<span style="font-weight: bold;">Note:</span> All PeSIT Hors SIT transfers are identified solely by these parameters.

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Parameter         </th>
<th class="HeadE-Column1-Header1">PI         </th>
<th class="HeadD-Column1-Header1">Comment         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Client Site name</p>         </td>
         <td><p>PI 3</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>Server Site name</p>         </td>
         <td><p>PI 4</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>Logical originator protocol identifier</p>         </td>
         <td><p>PI 61</p>         </td>
         <td><p>For routed transfers</p>         </td>
      </tr>
      <tr>
         <td><p>Logical destination protocol identifier</p>         </td>
         <td><p>PI 62</p>         </td>
         <td><p>For routed transfers</p>         </td>
      </tr>
      <tr>
         <td><p>File type</p>         </td>
         <td><p>PI 11</p>         </td>
         <td><p>Integer between 0 and 65635</p>         </td>
      </tr>
      <tr>
         <td><p>File name</p>         </td>
         <td><p>PI 12</p>         </td>
         <td><p>Application logical file name</p>         </td>
      </tr>
      <tr>
         <td><p>Transfer identifier</p>         </td>
         <td><p>PI 13</p>         </td>
         <td><p>Transfer ID number generated by the initial file originator</p>         </td>
      </tr>
   </tbody>
</table>

### Transfer modes

During a session between two Sites using the PeSIT protocol, the dialog is always asymmetrical: the two Sites play different complementary roles. The requester of the session, the Initiator, also takes the initiative regarding transfers, while the Responder (server Site) executes the requests received from the Initiator.

The Initiator sends files to the Responder (write), or the Responder sends files to the Initiator (read).

A given partner can have the following roles:

-   Initiator/Sender
-   Initiator/Receiver
-   Responder/Sender
-   Responder/Receiver

### Password management

During the pre-connection and connection phases, passwords can be exchanged and validated by the two conversing partners.

There are three types of password that you define in the Remote Site object:

-   Pre-connection password
-   Connection password sent by the Initiator (client: FPDU CONNECT PI 5)
-   Connection acknowledgment password sent by the Responder (server: FPDU ACONNECT PI 5)

For more information on how to define passwords, refer to [CGates: Protocol Connection](../../managing_partners_start_here/cgates_start_here/cgates_protocol_connection_phase).

The Initiator can send ID and password details in the PeSIT pre-connection message. The Responder then validates them.

If the pre-connection message exchange is successful, the Initiator can send the connection FPDU with the connection password, which is subsequently validated by the Responder. The Responder can then send its own password back in the connection acknowledgment FPDU to identify itself to the Initiator.

<span style="font-weight: bold;">Note:</span> In the PeSIT Hors SIT protocol specification, password management is an optional feature. If your partner Site does not support the same features, leave the <span class="code">check\_password</span> and <span class="code">check\_password2</span> fields blank.

### File and transfer attributes

The protocol negotiates the size of data blocks exchanged, as well as the compression type.

During the connection phase, the two Sites negotiate the synchronization point frequency and the acknowledgment data window.

<span id="how_pesit_works"></span>

## How PeSIT Hors SIT processing works

### Interaction diagrams

PeSIT provides a set of user services and a protocol dialogue used by two Sites to exchange files and messages. A service defines the interaction between two PeSIT end users.

Four types of service primitives implement this interaction:

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Primitive         </th>
<th class="HeadE-Column1-Header1">Notation         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Request</p>         </td>
         <td><p>REQ</p>         </td>
         <td><p>Request a given service</p>         </td>
      </tr>
      <tr>
         <td><p>Indication</p>         </td>
         <td><p>IND</p>         </td>
         <td><p>Notify the arrival of a service request</p>         </td>
      </tr>
      <tr>
         <td><p>Response</p>         </td>
         <td><p>RSP</p>         </td>
         <td><p>Answer a request</p>         </td>
      </tr>
      <tr>
         <td><p>Confirmation</p>         </td>
         <td><p>CNF</p>         </td>
         <td><p>Confirm the arrival of a response to a previous request</p>         </td>
      </tr>
   </tbody>
</table>

At the very minimum, a service involves a request submitted by a user and its corresponding indication to the partner. Some services also require a response and a confirmation to be complete.

The primitives provide functions for the following:

-   File-writing
-   File-reading
-   Synchronization
-   Transfer restart
-   Resynchronization during the transfer
-   Transfer suspension
-   Data compression
-   Error checking
-   Message transfer

#### File transmission

The following interaction diagram illustrates the communication flows between Initiator and Responder during file transmission.

<table>
         
         
         
         
   
   <thead>
      <tr>
<th colspan="3" class="HeadD-Column1-Header1">Sending a file         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>PeSIT</p>         </td>
         <td><p> </p>         </td>
         <td><p>PeSIT</p>         </td>
      </tr>
      <tr>
         <td><p>INITIATOR</p>         </td>
         <td><p> </p>         </td>
         <td><p>RESPONDER</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p>idle</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>F.CONNECT, REQ <strong>------&gt;</strong></p>         </td>
         <td><p> </p>         </td>
         <td><p><strong>------&gt;</strong>IND, F.CONNECT</p>         </td>
      </tr>
      <tr>
         <td><p>F.CONNECT, CNF <strong>&lt;------</strong></p>         </td>
         <td><p> </p>         </td>
         <td><p><strong>&lt;------</strong>RSP, F.CONNECT</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p>connected</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>F.CREATE, REQ <strong>------&gt;</strong></p>         </td>
         <td><p> </p>         </td>
         <td><p><strong>------&gt;</strong>IND, F.CREATE</p>         </td>
      </tr>
      <tr>
         <td><p>F.CREATE, CNF <strong>&lt;------</strong></p>         </td>
         <td><p> </p>         </td>
         <td><p><strong>&lt;------</strong>RSP, F.CREATE</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p>file selected</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>F.OPEN, REQ <strong>------&gt;</strong></p>         </td>
         <td><p> </p>         </td>
         <td><p><strong>------&gt;</strong>IND, F.OPEN</p>         </td>
      </tr>
      <tr>
         <td><p>F.OPEN, CNF <strong>&lt;------</strong></p>         </td>
         <td><p> </p>         </td>
         <td><p><strong>&lt;------</strong>RSP, F.OPEN</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p>file opened</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>F.WRITE, REQ <strong>------&gt;</strong></p>         </td>
         <td><p> </p>         </td>
         <td><p><strong>------&gt;</strong>IND, F.WRITE</p>         </td>
      </tr>
      <tr>
         <td><p>F.WRITE, CNF <strong>&lt;------</strong></p>         </td>
         <td><p> </p>         </td>
         <td><p><strong>&lt;------</strong>RSP, F.WRITE</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p>transfer started</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>F.DATA, REQ <strong>-------&gt;</strong></p>         </td>
         <td><p>data transfer</p>         </td>
         <td><p>------&gt;IND, F.DATA</p>         </td>
      </tr>
      <tr>
         <td><p>F.DATA, REQ <strong>-------&gt;</strong></p>         </td>
         <td><p> </p>         </td>
         <td><p><strong>------&gt;</strong>IND, F.DATA</p>         </td>
      </tr>
      <tr>
         <td><p>F.CHECK, REQ <strong>-------&gt;</strong></p>         </td>
         <td><p>synchronization point</p>         </td>
         <td><p><strong>------&gt;</strong>IND, F.CHECK</p>         </td>
      </tr>
      <tr>
         <td><p>F.DATA, REQ <strong>-------&gt;</strong></p>         </td>
         <td><p> </p>         </td>
         <td><p><strong>------&gt;</strong>IND, F.DATA</p>         </td>
      </tr>
      <tr>
         <td><p>F.DATA, REQ <strong>-------&gt;</strong></p>         </td>
         <td><p> </p>         </td>
         <td><p><strong>------&gt;</strong>IND, F.DATA</p>         </td>
      </tr>
      <tr>
         <td><p>F.CHECK, REQ <strong>-------&gt;</strong></p>         </td>
         <td><p> </p>         </td>
         <td><p><strong>------&gt;</strong>IND, F.CHECK</p>         </td>
      </tr>
      <tr>
         <td><p>F.DATA, REQ <strong>-------&gt;</strong></p>         </td>
         <td><p> </p>         </td>
         <td><p><strong>------&gt;</strong>IND, F.DATA</p>         </td>
      </tr>
      <tr>
         <td><p>F.DATA-END, REQ <strong>-----&gt;</strong></p>         </td>
         <td><p> </p>         </td>
         <td><p><strong>------&gt;</strong>IND, F.DATA-END</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>F.TRANSFER-END, REQ <strong>-----&gt;</strong></p>         </td>
         <td><p> </p>         </td>
         <td><p><strong>------&gt;</strong>IND,F.TRANSFER-END</p>         </td>
      </tr>
      <tr>
         <td><p>F.TRANSFER-END, CNF <strong>&lt;-----</strong></p>         </td>
         <td><p> </p>         </td>
         <td><p><strong>&lt;------</strong>RSP,F.TRANSFER-END</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p>transfer ended</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>F.CLOSE, REQ <strong>------&gt;</strong></p>         </td>
         <td><p> </p>         </td>
         <td><p><strong>------&gt;</strong>IND, F.CLOSE</p>         </td>
      </tr>
      <tr>
         <td><p>F.CLOSE, CNF <strong>&lt;------</strong></p>         </td>
         <td><p> </p>         </td>
         <td><p><strong>&lt;------</strong>RSP, F.CLOSE</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p>file closed</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>F.DESELECT, REQ <strong>------&gt;</strong></p>         </td>
         <td><p> </p>         </td>
         <td><p><strong>------&gt;</strong>IND, F.DESELECT</p>         </td>
      </tr>
      <tr>
         <td><p>F.DESELECT, CNF <strong>&lt;------</strong></p>         </td>
         <td><p> </p>         </td>
         <td><p><strong>&lt;------</strong>RSP, F.DESELECT</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p>file deselected</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>F.RELEASED, REQ <strong>------&gt;</strong></p>         </td>
         <td><p> </p>         </td>
         <td><p><strong>------&gt;</strong>IND, F.RELEASED</p>         </td>
      </tr>
      <tr>
         <td><p>F.RELEASED, CNF <strong>&lt;------</strong></p>         </td>
         <td><p> </p>         </td>
         <td><p><strong>&lt;------</strong>RSP, F.RELEASED</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p>disconnected</p>         </td>
         <td><p> </p>         </td>
      </tr>
   </tbody>
</table>

#### File reception

The following interaction diagram illustrates the communication flows between Initiator and Responder during file reception.

<table>
         
         
         
         
   
   <thead>
      <tr>
<th colspan="3" class="HeadD-Column1-Header1">Receiving a file         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>PeSIT</p>         </td>
         <td><p> </p>         </td>
         <td><p>PeSIT</p>         </td>
      </tr>
      <tr>
         <td><p>INITIATOR</p>         </td>
         <td><p> </p>         </td>
         <td><p>RESPONDER</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p>connected</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>F.SELECT, REQ <strong>------&gt;</strong></p>         </td>
         <td><p> </p>         </td>
         <td><p><strong>------&gt;</strong>IND, F.SELECT</p>         </td>
      </tr>
      <tr>
         <td><p>F.SELECT, CNF <strong>&lt;------</strong></p>         </td>
         <td><p> </p>         </td>
         <td><p><strong>&lt;------</strong>RSP, F.SELECT</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p>file selected</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>F.OPEN, REQ <strong>------&gt;</strong></p>         </td>
         <td><p> </p>         </td>
         <td><p><strong>------&gt;</strong>IND, F.OPEN</p>         </td>
      </tr>
      <tr>
         <td><p>F.OPEN, CNF <strong>&lt;------</strong></p>         </td>
         <td><p> </p>         </td>
         <td><p><strong>&lt;------</strong>RSP, F.OPEN</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p>file opened</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>F.READ, REQ <strong>------&gt;</strong></p>         </td>
         <td><p> </p>         </td>
         <td><p><strong>------&gt;</strong>IND, F.READ</p>         </td>
      </tr>
      <tr>
         <td><p>F.READ, CNF <strong>&lt;------</strong></p>         </td>
         <td><p> </p>         </td>
         <td><p><strong>&lt;------</strong>RSP, F.READ</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p>transfer started</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>F.DATA, IND <strong>&lt;------</strong></p>         </td>
         <td><p> </p>         </td>
         <td><p><strong>&lt;------</strong>REQ, F.DATA</p>         </td>
      </tr>
      <tr>
         <td><p>F.DATA, IND <strong>&lt;------</strong></p>         </td>
         <td><p> </p>         </td>
         <td><p><strong>&lt;------</strong>REQ, F.DATA</p>         </td>
      </tr>
      <tr>
         <td><p>F.CHECK, IND <strong>&lt;------</strong></p>         </td>
         <td><p> </p>         </td>
         <td><p><strong>&lt;------</strong>REQ, F.CHECK</p>         </td>
      </tr>
      <tr>
         <td><p>F.DATA, IND <strong>&lt;------</strong></p>         </td>
         <td><p> </p>         </td>
         <td><p><strong>&lt;------</strong>REQ, F.DATA</p>         </td>
      </tr>
      <tr>
         <td><p>F.DATA, IND <strong>&lt;------</strong></p>         </td>
         <td><p> </p>         </td>
         <td><p><strong>&lt;------</strong>REQ, F.DATA</p>         </td>
      </tr>
      <tr>
         <td><p>F.CHECK, IND <strong>&lt;------</strong></p>         </td>
         <td><p> </p>         </td>
         <td><p><strong>&lt;------</strong>REQ, F.CHECK</p>         </td>
      </tr>
      <tr>
         <td><p>F.DATA, IND <strong>&lt;------</strong></p>         </td>
         <td><p> </p>         </td>
         <td><p><strong>&lt;------</strong>REQ, F.DATA</p>         </td>
      </tr>
      <tr>
         <td><p>F.DATA-END, IND</p>         </td>
         <td><p> </p>         </td>
         <td><p><strong>&lt;------</strong>REQ, F.DATA-END</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>F.TRANSFER-END, REQ <strong>-----&gt;</strong></p>         </td>
         <td><p> </p>         </td>
         <td><p><strong>------&gt;</strong>IND,F.TRANSFER-END</p>         </td>
      </tr>
      <tr>
         <td><p>F.TRANSFER-END, CNF <strong>&lt;-----</strong></p>         </td>
         <td><p> </p>         </td>
         <td><p><strong>&lt;------</strong>RSP,F.TRANSFER-END</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p>transfer ended</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>F.CLOSE, REQ <strong>------&gt;</strong></p>         </td>
         <td><p> </p>         </td>
         <td><p><strong>------&gt;</strong>IND, F.CLOSE</p>         </td>
      </tr>
      <tr>
         <td><p>F.CLOSE, CNF <strong>&lt;------</strong></p>         </td>
         <td><p> </p>         </td>
         <td><p><strong>&lt;------</strong>RSP, F.CLOSE</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p><em>file closed</em></p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>F.DESELECT, REQ <strong>------&gt;</strong></p>         </td>
         <td><p> </p>         </td>
         <td><p><strong>------&gt;</strong>IND, F.DESELECT</p>         </td>
      </tr>
      <tr>
         <td><p>F.DESELECT, CNF <strong>&lt;------</strong></p>         </td>
         <td><p> </p>         </td>
         <td><p><strong>&lt;------</strong>RSP, F.DESELECT</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p>file deselected</p>         </td>
         <td><p> </p>         </td>
      </tr>
   </tbody>
</table>

#### Message transmission

The following interaction diagram illustrates the communication flows between Initiator and Responder during message transmission.

<table>
         
         
         
         
   
   <thead>
      <tr>
<th colspan="3" class="HeadD-Column1-Header1">Sending a message         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>PeSIT</p>         </td>
         <td><p> </p>         </td>
         <td><p>PeSIT</p>         </td>
      </tr>
      <tr>
         <td><p>INITIATOR</p>         </td>
         <td><p> </p>         </td>
         <td><p>RESPONDER</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p>idle</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>F.CONNECT, REQ <strong>------&gt;</strong></p>         </td>
         <td><p> </p>         </td>
         <td><p><strong>------&gt;</strong>IND, F.CONNECT</p>         </td>
      </tr>
      <tr>
         <td><p>F.CONNECT, CNF <strong>&lt;------</strong></p>         </td>
         <td><p> </p>         </td>
         <td><p><strong>&lt;------</strong>RSP, F.CONNECT</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p><em>connected</em></p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>F.MESSAGE, REQ <strong>------&gt;</strong></p>         </td>
         <td><p> </p>         </td>
         <td><p><strong>------&gt;</strong>IND, F.MESSAGE</p>         </td>
      </tr>
      <tr>
         <td><p>F.MESSAGE, CNF <strong>&lt;------</strong></p>         </td>
         <td><p> </p>         </td>
         <td><p><strong>&lt;------</strong>RSP, F.MESSAGE</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>F.RELEASED, REQ <strong>------&gt;</strong></p>         </td>
         <td><p> </p>         </td>
         <td><p><strong>------&gt;</strong>IND, F.RELEASED</p>         </td>
      </tr>
      <tr>
         <td><p>F.RELEASED, CNF <strong>&lt;------</strong></p>         </td>
         <td><p> </p>         </td>
         <td><p><strong>&lt;------</strong>RSP, F.RELEASED</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p>disconnected</p>         </td>
         <td><p> </p>         </td>
      </tr>
   </tbody>
</table>

### Protocol messages

#### Message structure

The messages that carry out the dialogue between the Initiator and the Responder are referred to as FPDUs (<span style="font-weight: bold;">F</span>ile transfer <span style="font-weight: bold;">P</span>rotocol <span style="font-weight: bold;">D</span>ata <span style="font-weight: bold;">U</span>nits). Each FPDU comprises a header (six bytes) that specifies the type of data transferred.

The body of the FPDUs is formed of a series of parameters used to specify and negotiate all the transfer elements. Each parameter, named PI (Parameter Identifier), is assigned a number and value as defined in the PeSIT protocol specifications.

Each parameter group unit is identified by a numeric code named **PGI** (<span style="font-weight: bold;">P</span>arameters <span style="font-weight: bold;">G</span>roup <span style="font-weight: bold;">I</span>dentifier).

For more information on PeSIT HS protocol, refer to documentation published by the GSIT (Groupement pour un Système Interbancaire de Télécompensation): *PeSIT protocol, Technical Specifications - version E*.

#### Examples of message structures (LI is the length indicator)

Message with two parameters (PI)

<table>
         
         
         
         
         
         
         
         
         
   
   <thead>
      <tr>
<th colspan="8" class="HeadD-Column1-Header1">FPDU Header         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p> </p>         </td>
         <td><p>TML</p>         </td>
         <td><p>PI</p>         </td>
         <td><p>LI</p>         </td>
         <td><p>VALUE</p>         </td>
         <td><p>PI</p>         </td>
         <td><p>LI</p>         </td>
         <td><p>VALUE</p>         </td>
      </tr>
   </tbody>
</table>

 

Message with one PGI containing two parameters (PI)

<table>
         
         
         
         
         
         
         
         
         
         
         
   
   <thead>
      <tr>
<th colspan="10" class="HeadD-Column1-Header1">FPDU Header         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p> </p>         </td>
         <td><p>TML</p>         </td>
         <td><p>PGI</p>         </td>
         <td><p>LI</p>         </td>
         <td><p>PI</p>         </td>
         <td><p>LI</p>         </td>
         <td><p>VALUE</p>         </td>
         <td><p>PI</p>         </td>
         <td><p>LI</p>         </td>
         <td><p>VALUE</p>         </td>
      </tr>
   </tbody>
</table>

#### List of PI codes

When labeled <span style="font-style: italic;">not used</span> the PIs are not sent, or are ignored on reception.

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">PI         </th>
<th class="HeadE-Column1-Header1">Values         </th>
<th class="HeadD-Column1-Header1">Meaning         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>1</p>         </td>
         <td><p>0 = not used</p>
<p>1 = used</p>         </td>
         <td><p>Use of a CRC (1 byte)</p>
<p>Not used</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>byte 1: error type</p>
<p>bytes 2-3: reason code</p>         </td>
         <td><p>Diagnostic giving the type of error encountered (3 bytes)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p> </p>         </td>
         <td><p>24-character parameter identifying the Initiator and defined by Site object protocol identifier:</p>
<ul>
<li>Initiator/Sender or Responder/ Receiver in the origin Site</li>
<li>Initiator/Receiver or Responder/ Sender in the destination Site</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p> </p>         </td>
         <td><p>24-character parameter identifying the Responder and defined by the Site object protocol identifier:</p>
<ul>
<li>Initiator/Sender or Responder/ Receiver: Destination Site</li>
<li>Initiator/Receiver or Responder/ Sender: Originator Site</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p> </p>         </td>
         <td><p>Access control</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>1: version D</p>
<p>2: version E</p>         </td>
         <td><p>Protocol version number. Defined in conffile by the parameter <span class="code">ver_num</span></p>         </td>
      </tr>
      <tr>
         <td><p>7</p>         </td>
         <td><p>b1b2=0: no synchronization point</p>
<p>b3=0: no acknowledgment</p>         </td>
         <td><p>Synchronization option (3 bytes)</p>
<p>Bytes 1-2: synchronization interval (in KB)</p>
<p>Byte 3: synchronization window</p>
<p>Negotiated in connection phase</p>         </td>
      </tr>
      <tr>
         <td><p>11</p>         </td>
         <td><p>= 0: no specific action</p>         </td>
         <td><p>Numeric parameter providing the file type as specified in the protocol documents</p>
<p>Transfer Request <span class="code">file_type</span> parameter</p>         </td>
      </tr>
      <tr>
         <td><p>12</p>         </td>
         <td><p>ASCII string</p>         </td>
         <td><p>File name</p>
<p>Transfer Request <span class="code">file_name</span> parameter</p>         </td>
      </tr>
      <tr>
         <td><p>13</p>         </td>
         <td><p> </p>         </td>
         <td><p>Transfer identifier: numeric value generated by the Sender</p>         </td>
      </tr>
      <tr>
         <td><p>14</p>         </td>
         <td><p>bitmap (1 byte)</p>         </td>
         <td><p>Requested attributes</p>         </td>
      </tr>
      <tr>
         <td><p>15</p>         </td>
         <td><p>0 = new transfer</p>
<p>1 = transfer restarted</p>         </td>
         <td><p>Transfer restarted</p>         </td>
      </tr>
      <tr>
         <td><p>16</p>         </td>
         <td><p>0 = ASCII</p>
<p>1 = EBCDIC</p>
<p>2 = BINARY</p>         </td>
         <td><p>Data code</p>         </td>
      </tr>
      <tr>
         <td><p>17</p>         </td>
         <td><p>0 = urgent</p>
<p>1 = normal</p>
<p>2 = lowest priority</p>         </td>
         <td><p>Transfer priority</p>
<p>Supplied by Transfer Request parameters</p>         </td>
      </tr>
      <tr>
         <td><p>18</p>         </td>
         <td><p>0 = beginning of file</p>         </td>
         <td><p>Restart point</p>
<p>Supplied by Gateway</p>         </td>
      </tr>
      <tr>
         <td><p>19</p>         </td>
         <td><p>4 = error (restart to follow)</p>
<p>8 = suspension</p>
<p>12 = canceled by Responder</p>
<p>16 = canceled by Initiator</p>         </td>
         <td><p>End-of-transfer code</p>         </td>
      </tr>
      <tr>
         <td><p>20</p>         </td>
         <td><p>0 = beginning of file</p>         </td>
         <td><p>Synchronization point number</p>
<p>Supplied by Gateway</p>         </td>
      </tr>
      <tr>
         <td><p>21</p>         </td>
         <td><p>byte 1:</p>
<ul>
<li>0 = No compression</li>
<li>1 = compression</li>
</ul>
<p>byte 2:</p>
<ul>
<li>1 = horizontal comp</li>
<li>2 = vertical comp</li>
<li>3 = both</li>
</ul>         </td>
         <td><p>Compression type: numeric value (2 bytes)</p>         </td>
      </tr>
      <tr>
         <td><p>22</p>         </td>
         <td><p>0 = Read</p>
<p>1 = Write</p>
<p>2 = RW</p>         </td>
         <td><p>File access type</p>         </td>
      </tr>
      <tr>
         <td><p>23</p>         </td>
         <td><p>0 = F.RESTART authorized</p>
<p>1 = not authorized</p>         </td>
         <td><p>Resynchronization specifying whether F.RESTART is authorized or not</p>
<p>Defined in Site object <span class="code">restart_allowed</span> parameter</p>         </td>
      </tr>
      <tr>
         <td><p>25</p>         </td>
         <td><p>must be &gt; 800 bytes</p>         </td>
         <td><p>Maximum length of data block</p>
<p>Supplied by configuration parameter <span class="code">sdu_max_len</span></p>         </td>
      </tr>
      <tr>
         <td><p>27</p>         </td>
         <td><p> </p>         </td>
         <td><p>Data byte count</p>         </td>
      </tr>
      <tr>
         <td><p>28</p>         </td>
         <td><p> </p>         </td>
         <td><p>Record count</p>
<p>Mandatory if PAD is used</p>         </td>
      </tr>
      <tr>
         <td><p>31</p>         </td>
         <td><p>=0: fix</p>
<p>=80h: variable</p>         </td>
         <td><p>Record format (1 byte)</p>         </td>
      </tr>
      <tr>
         <td><p>32</p>         </td>
         <td><p> </p>         </td>
         <td><p>Record length (2 bytes)</p>         </td>
      </tr>
      <tr>
         <td><p>33</p>         </td>
         <td><p>=0: sequential</p>
<p>=1: relative</p>
<p>=2: indexed</p>         </td>
         <td><p>File organization</p>         </td>
      </tr>
      <tr>
         <td><p>37</p>         </td>
         <td><p> </p>         </td>
         <td><p>File label: not used (256 bytes)</p>         </td>
      </tr>
      <tr>
         <td><p>38</p>         </td>
         <td><p> </p>         </td>
         <td><p>Key length in the record (2 bytes)</p>
<p>Parameter present if PI 33 = 2</p>         </td>
      </tr>
      <tr>
         <td><p>39</p>         </td>
         <td><p> </p>         </td>
         <td><p>Key offset in the record</p>
<p>Parameter present if PI 33 = 2</p>         </td>
      </tr>
      <tr>
         <td><p>41</p>         </td>
         <td><p>=0: KB</p>
<p>=1: record</p>         </td>
         <td><p>Space allocation unit</p>
<p>Supplied by Transfer Request <span class="code">alloc_unit</span> parameter</p>         </td>
      </tr>
      <tr>
         <td><p>42</p>         </td>
         <td><p> </p>         </td>
         <td><p>Maximum value of space reservation</p>
<p>Supplied by Transfer Request <span class="code">max_alloc_size</span> parameter</p>         </td>
      </tr>
      <tr>
         <td><p>51</p>         </td>
         <td><p> </p>         </td>
         <td><p>Date and time of transfer creation</p>
<p>Supplied by Gateway</p>         </td>
      </tr>
      <tr>
         <td><p>52</p>         </td>
         <td><p> </p>         </td>
         <td><p>Date and time of last extraction</p>
<p>Supplied by Gateway</p>         </td>
      </tr>
      <tr>
         <td><p>61</p>         </td>
         <td><p>24-byte char string</p>         </td>
         <td><p>Initial sender of the file</p>
<p>In routing mode, it is the Transfer Request Originator Site</p>         </td>
      </tr>
      <tr>
         <td><p>62</p>         </td>
         <td><p>24-byte char string</p>         </td>
         <td><p>Final receiver of the file</p>
<p>In routing mode, it is the Transfer Request Destination Site</p>         </td>
      </tr>
      <tr>
         <td><p>91</p>         </td>
         <td><p> </p>         </td>
         <td><p>Message</p>         </td>
      </tr>
      <tr>
         <td><p>99</p>         </td>
         <td><p>Free format message</p>         </td>
         <td><p>Usually supplied by Transfer Request <span class="code">snd_msg</span> parameter. </p>
<p>The supported message length is:</p>
<ul>
<li>512 bytes on PeSIT E</li>
<li>64 bytes on PeSIT D</li>
</ul>
<p>It is possible to send PI 99 messages both :</p>
<ul>
<li>on transfer-related phases: file creation/selection and deselection, and</li>
<li>on connection related phases: connect and release/disconnect.</li>
</ul>
<p>Only the values exchanged in transfer-related phases are recorded on the mailbox entry associated with the transfer. Values exchanged in the latest phase overwrite those exchanged in previous phases.</p>         </td>
      </tr>
   </tbody>
</table>

#### File transfer phases

The PeSIT protocol processes file transfers in following phases:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Phase         </th>
<th class="HeadD-Column1-Header1">Processing         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Connection/ Disconnection</p>         </td>
         <td><p>Connection establishment and connection release initiated either by the user or the protocol</p>         </td>
      </tr>
      <tr>
         <td><p>File selection/ deselection</p>         </td>
         <td><p>File creation, selection/ de-selection, and message transfer</p>         </td>
      </tr>
      <tr>
         <td><p>Opening/ Closure</p>         </td>
         <td><p>Opening and closing of file services</p>         </td>
      </tr>
      <tr>
         <td><p>Transfer</p>         </td>
         <td><p>Reading / writing files, sending data, setting of the synchronization points, transferring, resynchronization</p>         </td>
      </tr>
      <tr>
         <td><p>Interruption</p>         </td>
         <td><p>Restart of a transfer, end-of- data transmission, end of transfer</p>         </td>
      </tr>
   </tbody>
</table>

 

The processing passes through these phases in the sequence illustrated below.

1- CONNECTION phase

2- FILE SELECTION phase

3- FILE OPENING phase

4- DATA TRANSFER phase

4- END OF DATA TRANSFER

3- FILE CLOSING

2- FILE DESELECTION

 

2- FILE SELECTION

3- FILE OPENING

4- DATA TRANSFER

4- END OF DATA TRANSFER

3- FILE CLOSING

2- FILE DESELECTION

1- DISCONNECTION

 

Each phase is a step in the file transfer process. It is not possible to leave a phase without closing all the phases it contains.

Related topics

[Configuring PeSIT Hors SIT](pesit_config)

[Submitting a PeSIT Transfer Request](pesit_submitting_transfer)

[Monitoring a PeSIT transfer](pesit_monitoring_transfer) (return codes and trace messages)

[PeSIT specific user exits](pesit_exits)

[Executing a basic PeSIT transfer](../../transfer_examples/transfer_example_pesit)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
