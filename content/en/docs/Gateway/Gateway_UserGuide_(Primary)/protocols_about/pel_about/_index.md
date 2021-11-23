{
    "title": "About PEL",
    "linkTitle": "PEL",
    "weight": "190"
}{{< Gateway/componentlongname  >}}: Protocols

## PEL

[PEL](#pel_intro)

[How PEL processing works](#how_pel_works)

<span id="pel_intro"></span>

### Introduction to PEL

PEL is an end-to-end protocol designed to transfer files between two platforms, irrespective of the network support, hardware, and software architecture of the host computers.

Gateway uses PEL with different communication types: SNA in LU 6.2 mode, TCP/IP, and some proprietary communication stacks such as DSA and SPX/IPX. You define these communication attributes in Remote Site objects.

<span id="PEL_services"></span>

### PEL services

The general PEL characteristics are:

-   File transmission
-   File reception
-   Restart of an interrupted transfer
-   Data compression
-   Two-way transfers over the same logical connection
-   Message transfer

#### File transmission

This service enables you to transfer data to a remote partner. A logical link must have been previously established between the two partner Sites.

#### File reception

This service enables you to transfer file data belonging to the Remote Site.

#### Restart of an interrupted transfer

PEL can automatically restart transfers interrupted by technical incidents or by a user.

The interruption closes the file and disables the protocol and network connections. It is always the Initiator who launches the restart, and the data receiver who decides from which synchronization point the transfer is to be restarted.

#### Data compression

Data can be compressed in order to reduce the size of data actually transferred.

Three types of compression are available:

-   Horizontal compression: deletes repeated characters in a logical record
-   Vertical compression: transmits only data which differs from the previous record
-   Horizontal and vertical compression: combines both of the above methods

#### Two-way transfers over the same logical connection

PEL allows only one file transfer in a given session at a time. Nevertheless, Gateway can perform several concurrent transfers either as:

-   *consecutive* transfers within the same session
-   several *simultaneous* file transfers on *different* sessions, and in both directions.

Gateway PEL file transfer (F.T.) enables you to use the same Site for simultaneous file transfers in both directions.

#### Message transfer

PEL protocol can carry user messages of up to 80 bytes. They are transmitted, unmodified, by the sender to the partner Site, and can be used in end-of-transfer exit functions to automate specific processing.

You supply these user messages using the **Message to send** (<span class="code">snd\_msg</span>) parameter in the Transfer Request.

<span id="Site_and_transfer_identification"></span>

### Site and transfer identification

PEL uses the following information to uniquely identify a transfer:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Parameter         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Site name</p>         </td>
         <td><p>Gateway assigns each Site in a network a unique:</p>
<ul>
<li>Protocol name</li>
<li>Local Site defined in the configuration file by the <span class="code">local_site_proto_ident</span> parameter</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Application</p>         </td>
         <td><p>PEL associates an Application with each transfer. This Application is defined in Gateway, and references parameters such as the compression mode and file formatting attributes.</p>         </td>
      </tr>
      <tr>
         <td><p>PEL-specific Application, PEL1</p>         </td>
         <td><p>Manages Transfer Requests submitted without an explicit Application. Gateway retrieves the file and transfer attributes from the Transfer Request.</p>         </td>
      </tr>
      <tr>
         <td><p>Rank number</p>         </td>
         <td><p>The Sender Site transmitting the file assigns this to each transfer.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Transfer_modes"></span>

### Transfer modes

The Initiator Site initiates the physical connection and the Responder Site responds to it. PEL allows data transfers in both directions: the Site sending data is the Sender, and the one receiving data is the Receiver. A given Site object can have one of the following roles:

-   Initiator/Sender
-   Initiator/Receiver
-   Responder/Sender
-   Responder/Receiver

Protocol commands and response messages are exchanged between the two partner Sites at some specific steps during file transfer processing, as described in [How PEL processing works](#how_pel_works).

<span id="File_and_transfer_attributes"></span>

### File and transfer attributes

The file content is transmitted over the network in data blocks whose size you define.

An acknowledgment mechanism is used by PEL to regulate data flow. It is configured via the<span class="code"> -check\_window</span> attribute of the Remote Site object.

Protocol data is coded in EBCDIC. Code conversion allows automatic conversion of file data transmitted to the partner Site. It is configured via<span class="code"> -data\_code</span> attributes defined in Application objects.

<span id="Routing"></span>

### Routing

PEL supplies a Store-and-Forward mechanism, allowing a transfer from one end Site to another via intermediate Sites. Gateway can use Logical Sites to submit file transfer towards a non-adjacent partner.

<span id="File_transfer_phases"></span>

### File transfer phases

The transfer actually begins with the physical connection of two Sites. PEL processes a file transfer in the following sequence:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Phase         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Protocol connection</p>         </td>
         <td><p>Initiated by server Site after the physical connection and a possible logon phase. User identification and password can be checked at this stage for security purposes.</p>         </td>
      </tr>
      <tr>
         <td><p>Selecting the set of information to be transferred</p>         </td>
         <td><p>Initiated by Initiator Site. If files are to be transferred from the Responder Site to the Initiator Site, this selection is made from the set of information previously received from the Responder.</p>         </td>
      </tr>
      <tr>
         <td><p>Data transfer</p>         </td>
         <td><p>After the selection, file data is sent without a header, and with flow control regulation, if requested.</p>         </td>
      </tr>
      <tr>
         <td><p>Deselecting the set</p>         </td>
         <td><p>When all file data is sent, a command containing checking information indicates the end of data transmission to the Receiver. The Receiver Site verifies the validity of the received information, and then accepts or rejects the set.</p>         </td>
      </tr>
      <tr>
         <td><p>Protocol connection release</p>         </td>
         <td><p>Initiated by Initiator Site (after de-selecting the set) and acknowledged by the Responder.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="how_pel_works"></span>

## How PEL processing works

<span id="Protocol_commands_and_processing"></span>

### Protocol commands and responses

Protocol messages comprise commands and responses. Each message is prefixed with its identification string followed by items defined in the PEL protocol.

Commands are prefixed with "?" and responses with "\*" as illustrated in the following table:

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Type         </th>
<th class="HeadE-Column1-Header1">Name         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Command</p>         </td>
         <td><p>?DEBUT</p>         </td>
         <td><p>Beginning of protocol connection</p>         </td>
      </tr>
      <tr>
         <td><p>?FIN</p>         </td>
         <td><p>End of protocol connection</p>         </td>
      </tr>
      <tr>
         <td><p>?LOTS</p>         </td>
         <td><p>Request for the list of selectable sets</p>         </td>
      </tr>
      <tr>
         <td><p>?TRANS</p>         </td>
         <td><p>Request for a file transfer</p>         </td>
      </tr>
      <tr>
         <td><p>Response</p>         </td>
         <td><p>*ACCEPTE</p>         </td>
         <td><p>Acceptance of the connection</p>         </td>
      </tr>
      <tr>
         <td><p>*ACQ</p>         </td>
         <td><p>Data acknowledgment</p>         </td>
      </tr>
      <tr>
         <td><p>*ADL</p>         </td>
         <td><p>Acceptance of the set</p>         </td>
      </tr>
      <tr>
         <td><p>*DDL</p>         </td>
         <td><p>Beginning of the set</p>         </td>
      </tr>
      <tr>
         <td><p>*FDL</p>         </td>
         <td><p>End of the set</p>         </td>
      </tr>
      <tr>
         <td><p>*FIN</p>         </td>
         <td><p>End of connection</p>         </td>
      </tr>
      <tr>
         <td><p>*LL</p>         </td>
         <td><p>List of sets</p>         </td>
      </tr>
      <tr>
         <td><p>*NDL</p>         </td>
         <td><p>Refusal of a set</p>         </td>
      </tr>
      <tr>
         <td><p>*NON</p>         </td>
         <td><p>Negative response</p>         </td>
      </tr>
      <tr>
         <td><p>*OK</p>         </td>
         <td><p>Positive response</p>         </td>
      </tr>
      <tr>
         <td><p>*RDL</p>         </td>
         <td><p>Restart of a set</p>         </td>
      </tr>
      <tr>
         <td><p>*REFUSE</p>         </td>
         <td><p>Rejection of a connection</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Interaction_diagrams"></span>

### Interaction diagrams

The following interaction diagrams illustrate the communication flows between Initiator and Responder.

#### File transmission

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Initiator         </th>
<th class="HeadE-Column1-Header1">          </th>
<th class="HeadE-Column1-Header1">          </th>
<th class="HeadD-Column1-Header1">Responder         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>&lt;-----</p>         </td>
         <td><p>?DEBUT</p>         </td>
      </tr>
      <tr>
         <td><p>*ACCEPTE Initiator</p>         </td>
         <td><p>-----&gt;</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>&lt;-----</p>         </td>
         <td><p>*OK</p>         </td>
      </tr>
      <tr>
         <td><p>?TRANS set</p>         </td>
         <td><p>-----&gt;</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>&lt;-----</p>         </td>
         <td><p>*OK</p>         </td>
      </tr>
      <tr>
         <td><p>*DDL</p>         </td>
         <td><p>-----&gt;</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>&lt;-----</p>         </td>
         <td><p>*OK or *RDL</p>         </td>
      </tr>
      <tr>
         <td><p>data</p>
<p>&amp;..</p>         </td>
         <td><p>-----&gt;</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>data</p>         </td>
         <td><p>-----&gt;</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>&lt;-----</p>         </td>
         <td><p>(*ACQ)</p>         </td>
      </tr>
      <tr>
         <td><p>data</p>
<p>&amp;..</p>         </td>
         <td><p>-----&gt;</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>data</p>         </td>
         <td><p>-----&gt;</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>&lt;-----</p>         </td>
         <td><p>(*ACQ)</p>         </td>
      </tr>
      <tr>
         <td><p>*FDL</p>         </td>
         <td><p>-----&gt;</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>&lt;-----</p>         </td>
         <td><p>*ADL</p>         </td>
      </tr>
      <tr>
         <td><p>?FIN</p>         </td>
         <td><p>-----&gt;</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>&lt;-----</p>         </td>
         <td><p>*END OF REQUEST</p>         </td>
      </tr>
   </tbody>
</table>

#### File reception

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Initiator         </th>
<th class="HeadE-Column1-Header1">          </th>
<th class="HeadE-Column1-Header1">          </th>
<th class="HeadD-Column1-Header1">Responder         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>&lt;-----</p>         </td>
         <td><p>?DEBUT</p>         </td>
      </tr>
      <tr>
         <td><p>*ACCEPTE Initiator</p>         </td>
         <td><p>-----&gt;</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>&lt;-----</p>         </td>
         <td><p>*OK</p>         </td>
      </tr>
      <tr>
         <td><p>?LOTS</p>         </td>
         <td><p>-----&gt;</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>&lt;-----</p>         </td>
         <td><p>*LL list</p>         </td>
      </tr>
      <tr>
         <td><p>?TRANS set</p>         </td>
         <td><p>-----&gt;</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>&lt;-----</p>         </td>
         <td><p>*DDL</p>         </td>
      </tr>
      <tr>
         <td><p>*OK or *RDL</p>         </td>
         <td><p>-----&gt;</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>&lt;-----</p>         </td>
         <td><p>data</p>
<p>&amp;..</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>&lt;-----</p>         </td>
         <td><p>data</p>         </td>
      </tr>
      <tr>
         <td><p>(*ACQ)</p>         </td>
         <td><p>-----&gt;</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>&lt;-----</p>         </td>
         <td><p>data</p>
<p>&amp;..</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>&lt;-----</p>         </td>
         <td><p>data</p>         </td>
      </tr>
      <tr>
         <td><p>(*ACQ)</p>         </td>
         <td><p>-----&gt;</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>&lt;-----</p>         </td>
         <td><p>data</p>
<p>&amp;</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>&lt;-----</p>         </td>
         <td><p>*FDL</p>         </td>
      </tr>
      <tr>
         <td><p>*ADL</p>         </td>
         <td><p>-----&gt;</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>&lt;-----</p>         </td>
         <td><p>*OK</p>         </td>
      </tr>
      <tr>
         <td><p>?FIN</p>         </td>
         <td><p>-----&gt;</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>&lt;-----</p>         </td>
         <td><p>*END OF REQUEST</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Configuring Gateway for PEL](pel_config)

[Submitting a PEL Transfer Request](pel_submitting_transfer)

 

Refer to [About user exits](../../customizing_gw_about/user_exits_about) for details of exit routines supplied for the PEL protocol.

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
