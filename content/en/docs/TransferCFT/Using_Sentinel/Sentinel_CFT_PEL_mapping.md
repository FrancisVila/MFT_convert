{
    "title": "Sentinel to Transfer CFT to InterPEL mapping",
    "linkTitle": "Sentinel to Transfer CFT to InterPEL mapping",
    "weight": "260"
}The following tables list parameter correspondence between Transfer CFT, Sentinel, and InterPEL. You find this mapping using in migrating from InterPEL to Transfer CFT.

> **Note:**
>
> The fields prefixed with "MLH" are fields that are specific to the PeSIT Hors SIT protocol, which are contained in the recording transfer from the Mailbox and are accessible by the Assembly Exits.

## XFBTransfer tracked object

### Roles

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Sentinel</p>
<p>attribute</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Data type         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Length         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Description         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Transfer CFT         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">InterPEL Core         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">InterPEL MVS         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Direction         </td>
         <td>Integer         </td>
         <td>-         </td>
         <td><p>S: The file is sent (Sender).</p>
<p>R: The file is received (Receiver).</p>         </td>
         <td>DIRECT         </td>
         <td><p>From direction:</p>
<p>"R" "E" "B"</p>         </td>
         <td>TYPEREQ={S|M or C}         </td>
      </tr>
      <tr>
         <td>IsServer         </td>
         <td>Integer         </td>
         <td>-         </td>
         <td><p>1: The Sender or the Receiver is a Server.</p>
<p>0: The Sender the Receiver is a Requester.</p>         </td>
         <td>FLAG         </td>
         <td><p>From mode:</p>
<p>Initiator "R"
Responder "S"</p>         </td>
         <td>MLHMODR - Initiator “R” Responder “S” (depending on the STOSR parameter)         </td>
      </tr>
   </tbody>
</table>

### Senders and receivers

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Sentinel         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Data type         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Length         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Description         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Transfer CFT         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">InterPEL Core         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">InterPEL MVS         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Site         </td>
         <td>String         </td>
         <td>25         </td>
         <td>Partner alias of the remote partner.         </td>
         <td>PART         </td>
         <td>remote_agent         </td>
         <td>DEST         </td>
      </tr>
      <tr>
         <td>ReceiverId         </td>
         <td>String         </td>
         <td>80         </td>
         <td>Name of the Receiver.         </td>
         <td>NRPART         </td>
         <td><p>from:</p>
<p>local_agent_ident (direct IN)</p>
<p>remote_agent_ident (direct OUT)</p>         </td>
         <td>MLHDEM (from LOCAL or SITLNAM parameters)         </td>
      </tr>
      <tr>
         <td>SenderId         </td>
         <td>String         </td>
         <td>80         </td>
         <td>Name of the Sender.         </td>
         <td>NSPART         </td>
         <td><p>from:</p>
<p>remote_agent_ident (direct IN)</p>
<p>local_agent_ident (direct OUT)</p>         </td>
         <td>MLHSERV (from DEST or ALTLOCN parameters)         </td>
      </tr>
      <tr>
         <td>RAppl         </td>
         <td>String         </td>
         <td>80         </td>
         <td>Optional identifier of the Receiving  application.         </td>
         <td>RAPPL         </td>
         <td>rcv_appli         </td>
         <td>N/A         </td>
      </tr>
      <tr>
         <td>SAppl         </td>
         <td>String         </td>
         <td>80         </td>
         <td>Optional identifier of the Sending  application.         </td>
         <td>SAPPL         </td>
         <td>snd_appli         </td>
         <td>N/A         </td>
      </tr>
      <tr>
         <td>SourceApplication         </td>
         <td>String         </td>
         <td>100         </td>
         <td><p>The source application for a Central Governance flow, for monitoring purposes.</p>
<p>The source system is the system that initiates a flow.</p>         </td>
         <td>SOURCEAPPL         </td>
         <td>N/A         </td>
         <td>N/A         </td>
      </tr>
      <tr>
         <td>TargetApplication         </td>
         <td>String         </td>
         <td>100         </td>
         <td><p>The target application in a Central Governance flow, for monitoring purposes.</p>
<p>The target system is the system making a request to initiate the flow.</p>         </td>
         <td>TARGETAPPL         </td>
         <td>N/A         </td>
         <td>N/A         </td>
      </tr>
      <tr>
         <td>FinalReceiverId         </td>
         <td>String         </td>
         <td>80         </td>
         <td>Name of the final Receiver when using Store and Forward, otherwise the same as the ReceiverId.         </td>
         <td>NDEST         </td>
         <td>destination         </td>
         <td>MLHBP         </td>
      </tr>
      <tr>
         <td>OriginalSenderId         </td>
         <td>String         </td>
         <td>80         </td>
         <td>Name of the original Sender when using Store and Forward, otherwise the same as the SenderId.         </td>
         <td>NORIG         </td>
         <td>originator         </td>
         <td>MLHORG1         </td>
      </tr>
   </tbody>
</table>

### Product identification

The product that sends the events is identified with the following:

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Sentinel         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Data type         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Length         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Description         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Transfer CFT         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">InterPEL Core         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">InterPEL MVS         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Location         </td>
         <td>String         </td>
         <td>31         </td>
         <td>Unique and logical identifier for the product.         </td>
         <td>PART parameter of the CFTPARM object.         </td>
         <td>local_site_alias         </td>
         <td>LOCNAME of PELPARMS         </td>
      </tr>
      <tr>
         <td>Monitor         </td>
         <td>String         </td>
         <td>4         </td>
         <td>Product name.         </td>
         <td>“CFT”         </td>
         <td>MSG_PROD_MONITOR_PEL &gt; "PEL"         </td>
         <td>"PEL"         </td>
      </tr>
      <tr>
         <td>MonitorVersion         </td>
         <td>String         </td>
         <td>25         </td>
         <td>Product version.         </td>
         <td>Product version         </td>
         <td><p>Computation of:</p>
<p>MSG_XFB_MONITOR_VERSION &gt; "6.6.3"</p>         </td>
         <td>"732"         </td>
      </tr>
      <tr>
         <td>Machine         </td>
         <td>String         </td>
         <td>25         </td>
         <td>Name of the application and platform that run on a Transfer CFT         </td>
         <td><p>PRODUCT_TYPE:</p>
<p>"CFT-UNIX"
"CFTL-NT"
"CFT-MVS"
"CFT-400"
"CFT-NSK"
"CFT-VMS"</p>         </td>
         <td><p>PRODUCT_TYPE:</p>
<p>"PEL-UNIX"
"PEL-NT"
"PEL-400"
"PEL-NSK"</p>         </td>
         <td>PELIMVS         </td>
      </tr>
      <tr>
         <td>ProductName         </td>
         <td>String         </td>
         <td>50         </td>
         <td>N/A         </td>
         <td>uconf: sentinel.trkproductname         </td>
         <td>local_site_alias         </td>
         <td>N/A         </td>
      </tr>
   </tbody>
</table>

### Transfer users

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Sentinel         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Data type         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Length         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Description         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Transfer CFT         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">InterPEL Core         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">InterPEL MVS         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>UserId         </td>
         <td>String         </td>
         <td>25         </td>
         <td>Local identifier of the user who owns the transferred file.         </td>
         <td>USERID         </td>
         <td>N/A         </td>
         <td>N/A         </td>
      </tr>
      <tr>
         <td>GroupId         </td>
         <td>String         </td>
         <td>25         </td>
         <td>Local identifier of the group to which the transfer owner belongs.         </td>
         <td>GROUPID         </td>
         <td>N/A         </td>
         <td>N/A         </td>
      </tr>
      <tr>
         <td>RequestUserId         </td>
         <td>String         </td>
         <td>25         </td>
         <td>Local identifier of the user who requested the transfer.         </td>
         <td>REQUSER         </td>
         <td>username         </td>
         <td>MLHUSERN         </td>
      </tr>
      <tr>
         <td>RequestGroupId         </td>
         <td>String         </td>
         <td>25         </td>
         <td>Local identifier of the group to which the requesting user belongs.         </td>
         <td>REQGROUP         </td>
         <td>N/A         </td>
         <td>N/A         </td>
      </tr>
      <tr>
         <td>Trustee         </td>
         <td>String         </td>
         <td>25         </td>
         <td><p>If User Access Control is:</p>
<ul>
<li>Activated for the transfer, the value of this attribute is the local identifier of the transfer owner (UserId).</li>
<li>Not activated for the transfer, the value of this attribute is the network identifier of the user who requested the transfer (RequestUserId).</li>
</ul>         </td>
         <td>IDAPPL         </td>
         <td>N/A         </td>
         <td>  N/A         </td>
      </tr>
      <tr>
         <td>RUser         </td>
         <td>String         </td>
         <td>30         </td>
         <td>Optional local identifier of the user who received the transfer.         </td>
         <td>RUSER         </td>
         <td>rcv_user         </td>
         <td>MLHUSERN         </td>
      </tr>
      <tr>
         <td>SUser         </td>
         <td>String         </td>
         <td>30         </td>
         <td>Optional local identifier of the user who sent the transfer.         </td>
         <td>SUSER         </td>
         <td>snd_user         </td>
         <td>N/A         </td>
      </tr>
   </tbody>
</table>

### Transfer identification

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Sentinel         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Data type         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Length         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Description         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Transfer CFT         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">InterPEL Core         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">InterPEL MVS         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>IdAppl         </td>
         <td>String         </td>
         <td>25         </td>
         <td><p>If the value of the IsServer attribute is:</p>
<ul>
<li>0: The value of this attribute is the local identifier of the Requester.</li>
<li>1: The value of this attribute is empty.</li>
</ul>         </td>
         <td>IDA         </td>
         <td>N/A         </td>
         <td>  auto PEL1         </td>
      </tr>
      <tr>
         <td>Application         </td>
         <td>String         </td>
         <td>80         </td>
         <td>Local application/Transfer profile (ST).         </td>
         <td>IDF         </td>
         <td>application         </td>
         <td>APPL         </td>
      </tr>
      <tr>
         <td>FileName         </td>
         <td>String         </td>
         <td>512         </td>
         <td><p>If the value of the CommandType attribute is File and the value of the Direction attribute is:</p>
<ul>
<li>E (Sender): This attribute identifies the file from which the Sender retrieved the transfer data (full path).</li>
</ul>
<ul>
<li>R (Receiver): This attribute identifies the file in which the Receiver recorded the transfer data (full path).</li>
</ul>         </td>
         <td>FNAME         </td>
         <td>dir_path/file_component         </td>
         <td>  DSNORIG         </td>
      </tr>
      <tr>
         <td>LocalId         </td>
         <td>String         </td>
         <td>25         </td>
         <td><p>If the value of the Direction attribute is:</p>
<ul>
<li>E (Sender): The value of this attribute is the local transfer identifier for the Sender.</li>
<li>R (Receiver): The value of this attribute is the local transfer identifier for the Receiver.</li>
</ul>         </td>
         <td>IDTU         </td>
         <td>  local_ident         </td>
         <td>  auto MLY_TRID         </td>
      </tr>
      <tr>
         <td>ProtocolFileName         </td>
         <td>String         </td>
         <td>512         </td>
         <td><p>Network transfer identifier.</p>
<p>The Sender sent this identifier to the Receiver.</p>         </td>
         <td>NIDF         </td>
         <td>file_name         </td>
         <td>N         </td>
      </tr>
      <tr>
         <td>ProtocolFileLabel         </td>
         <td>String         </td>
         <td>80         </td>
         <td><p>The Sender sent this name to the Receiver.</p>
<p>The Receiver can use this name to locally name the transfer.</p>         </td>
         <td>NFNAME         </td>
         <td>file_label         </td>
         <td>LABEL         </td>
      </tr>
      <tr>
         <td>ProtocolId         </td>
         <td>String         </td>
         <td>80         </td>
         <td><p>Network transfer identifier.</p>
<p>The Sender generated this identifier.</p>
<p>The Receiver acknowledged this identifier.</p>         </td>
         <td>NIDT         </td>
         <td>xfer_ident         </td>
         <td>MLHRANG         </td>
      </tr>
      <tr>
         <td>ProtocolMessage         </td>
         <td>String         </td>
         <td>4000         </td>
         <td><p>If the value of the CommandType attribute is:</p>
<ul>
<li>Message: The value of this attribute is the content of the transferred message.</li>
<li>File: This attribute is empty.</li>
</ul>         </td>
         <td>SMSG         </td>
         <td><p>From:</p>
<ul>
<li>snd_msg (message OUT)</li>
<li>rcv_msg (message IN)</li>
</ul>         </td>
         <td><p>  MSG1/ MSG2</p>
<p>(Interpel MVS MSG1/MSG2/</p>
<p>MSG3/MSG4/</p>
<p>MSG5)</p>         </td>
      </tr>
      <tr>
         <td>PositionNumber         </td>
         <td>String         </td>
         <td>80         </td>
         <td><p>Local transfer identifier. If the value of the Direction attribute is:</p>
<ul>
<li>E (Sender): The value of this attribute identifies the transfer in the Sender's transfer catalog or DB.</li>
<li>R (Receiver): The value of this attribute identifies the transfer in the Receiver's transfer catalog or DB.</li>
</ul>         </td>
         <td>IDT         </td>
         <td>sequence         </td>
         <td>  auto MLBCLE         </td>
      </tr>
      <tr>
         <td>ProtocolParameter         </td>
         <td>String         </td>
         <td>512         </td>
         <td><p>Network transfer description.</p>
<p>The Sender sent this description to the Receiver.</p>         </td>
         <td>PARM         </td>
         <td><p>from:</p>
<ul>
<li>snd_msg (transfer OUT)</li>
<li>rcv_msg (transfer IN)</li>
</ul>         </td>
         <td><p>MSG1</p>
<p>(Interpel MVS MSG1/MSG2/</p>
<p>MSG3/MSG4/</p>
<p>MSG5)</p>         </td>
      </tr>
      <tr>
         <td>UserParameter1         </td>
         <td>String         </td>
         <td>255         </td>
         <td><p>Local transfer description.</p>
<p>This description is recorded at the transfer request time in the local DB and remains local.</p>         </td>
         <td>COMMENT         </td>
         <td>param1         </td>
         <td>USERAREA         </td>
      </tr>
      <tr>
         <td>Flowname         </td>
         <td>String         </td>
         <td>100         </td>
         <td>Parameter to define a flow name in Central Governance for monitoring purposes.         </td>
         <td>Flowname (v3.1.x)         </td>
         <td>N/A         </td>
         <td>N/A         </td>
      </tr>
      <tr>
         <td>UserParameter2         </td>
         <td>String         </td>
         <td>255         </td>
         <td><p>Local transfer description.</p>
<p>This description is recorded at the transfer request time in the local DB and remains local.</p>         </td>
         <td>N/A         </td>
         <td>param2         </td>
         <td>N/A         </td>
      </tr>
      <tr>
         <td>VirtualDirName         </td>
         <td>String         </td>
         <td>255         </td>
         <td>Virtual directory name         </td>
         <td>N/A         </td>
         <td>dir_name (not stored, always empty)         </td>
         <td>N/A         </td>
      </tr>
   </tbody>
</table>

### Transfer validity periods

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Sentinel         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Data type         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Length         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Description         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Transfer CFT         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">InterPEL Core         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">InterPEL MVS         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>EarliestDate         </td>
         <td>Date         </td>
         <td>N/A         </td>
         <td>Date on which the validity period begins.         </td>
         <td>DATEM (Catalog)         </td>
         <td>From date_to_begin: date         </td>
         <td>SDATE {aaqqq | +n}         </td>
      </tr>
      <tr>
         <td>EarliestTime         </td>
         <td>Time         </td>
         <td>N/A         </td>
         <td>Time at which the validity period begins.         </td>
         <td>TIMEM (Catalog)         </td>
         <td>From date_to_begin: time         </td>
         <td>HSDEB         </td>
      </tr>
      <tr>
         <td>LatestDate         </td>
         <td>Date         </td>
         <td>N/A         </td>
         <td>Date on which the validity period ends.         </td>
         <td>DATEMAX (Catalog)         </td>
         <td>From date_to_end: date         </td>
         <td>N/A         </td>
      </tr>
      <tr>
         <td>LatestTime         </td>
         <td>Time         </td>
         <td>N/A         </td>
         <td>Time at which the validity period ends.         </td>
         <td>TIMEMAX (Catalog)         </td>
         <td>From date_to_end: time         </td>
         <td>HSFIN         </td>
      </tr>
   </tbody>
</table>

### Transfer dates and times

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Sentinel         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Data type         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Length         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Description         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Name in         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">InterPEL Core         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">InterPEL MVS         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>CreationDate         </td>
         <td>Date         </td>
         <td>N/A         </td>
         <td><p>By default, the system date on which the Sender sent the transfer.</p>
<ul>
<li>The Sender can set this date.</li>
<li>The Receiver can filter transfers based on this date.</li>
</ul>         </td>
         <td>From FDATE (Catalog)         </td>
         <td>From hist_create_date: date         </td>
         <td>CDATE=aaqqq         </td>
      </tr>
      <tr>
         <td>CreationTime         </td>
         <td>Time         </td>
         <td>N/A         </td>
         <td><p>By default, the system time at which the Sender sent the transfer.</p>
<ul>
<li>The Sender can set this time.</li>
<li>The Receiver can filter transfers based on this time.</li>
</ul>         </td>
         <td>From FTIME (Catalog)         </td>
         <td>From hist_create_date: time         </td>
         <td>CTIME=hhmmss         </td>
      </tr>
      <tr>
         <td>SendDate         </td>
         <td>Date         </td>
         <td>N/A         </td>
         <td><p>If the value of the Direction attribute is:</p>
<ul>
<li>E (Sender): The value of this attribute is the date on which the Sender recorded the transfer in the transfer catalog.</li>
<li>R (Receiver): The value of this attribute is the date on which the Receiver recorded the transfer in the transfer catalog. The Sender and the Receiver record each transfer only once.</li>
</ul>         </td>
         <td>From DATEK (Catalog)         </td>
         <td>N/A         </td>
         <td>N/A         </td>
      </tr>
      <tr>
         <td>SendTime         </td>
         <td>Time         </td>
         <td>N/A         </td>
         <td><p>If the value of the Direction attribute is:</p>
<ul>
<li>E (Sender): The value of this attribute is the local time at which the Sender recorded the transfer in the transfer catalog.</li>
<li>R (Receiver): The value of this attribute is the local time at which the Receiver recorded the transfer in the transfer catalog.</li>
</ul>
The Sender and the Receiver record each transfer only once.         </td>
         <td>From TIMEK (Catalog)         </td>
         <td>N/A         </td>
         <td>N/A         </td>
      </tr>
      <tr>
         <td>AckDate         </td>
         <td>Date         </td>
         <td>N/A         </td>
         <td>Date on which the Receiver acknowledged the transfer (if any).         </td>
         <td>From Current Date when ack         </td>
         <td>N/A         </td>
         <td>N/A         </td>
      </tr>
      <tr>
         <td>AckTime         </td>
         <td>Time         </td>
         <td>N/A         </td>
         <td>Time at which the Receiver acknowledged the transfer (if any).         </td>
      </tr>
      <tr>
         <td>StartDate         </td>
         <td>Date         </td>
         <td>N/A         </td>
         <td><p>If the value of the State attribute is:</p>
<ul>
<li>SENT: The value of this attribute is the date on which the Sender began sending the transfer.</li>
<li>RECEIVED: The value of this attribute is the date on which the Receiver began receiving the transfer.</li>
</ul>
<p>These dates are expressed in dd.mm.yyyy format.</p>         </td>
         <td>From DATEB (Catalog)         </td>
         <td>From date_begin: date         </td>
         <td> (MVS) SDATE, MLHDATDT         </td>
      </tr>
      <tr>
         <td>StartTime         </td>
         <td>Time         </td>
         <td>N/A         </td>
         <td><p>If the value of the State attribute is:</p>
<ul>
<li>SENT: The value of this attribute is the local time at which the Sender began sending the transfer.</li>
<li>RECEIVED: The value of this attribute is the local time at which the Receiver began receiving the transfer.</li>
</ul>
<p>These times are expressed in hh:mn:ss format.</p>         </td>
         <td>From TIMEB (Catalog)         </td>
         <td>From date_begin: time         </td>
         <td><p>  MLHHEUDT</p>
<p>(MVS does not exist in Pelica2 requests)</p>         </td>
      </tr>
      <tr>
         <td>EndDate         </td>
         <td>Date         </td>
         <td>N/A         </td>
         <td><p>If the value of the State attribute is:</p>
<ul>
<li>SENT: The value of this attribute is the date on which the Sender stopped sending the transfer.</li>
<li>RECEIVED: The value of this attribute is the date on which the Receiver stopped receiving the transfer.</li>
</ul>
<p>These dates are expressed in dd.mm.yyyy format.</p>         </td>
         <td>From DATEE (Catalog)         </td>
         <td>From date_end: date         </td>
         <td>  MLHDATFT         </td>
      </tr>
      <tr>
         <td>EndTime         </td>
         <td>Time         </td>
         <td>N/A         </td>
         <td><p>If the value of the State attribute is:</p>
<ul>
<li>SENT: The value of this attribute is the local time at which the Sender stopped sending the transfer.</li>
<li>RECEIVED: The value of this attribute is the local time at which the Receiver stopped receiving the transfer.</li>
</ul>
<p>These times are expressed in hh:mn:ss format.</p>         </td>
         <td>From TIMEE (Catalog)         </td>
         <td>From date_end: time         </td>
         <td>  MLHHEUFT         </td>
      </tr>
      <tr>
         <td>RequestCreationDate         </td>
         <td>Date         </td>
         <td>N/A         </td>
         <td><p>If the value of the State attribute is:</p>
<ul>
<li>SENT: The value of this attribute is local date of the creation of the file on the Sender side.</li>
<li><span style="font-size: 11; font-family: Calibri; color: #000000">RECEIVED: The value of this attribute is the date of the creation of the file on the Sender side.
</span></li>
</ul>
<p><span style="font-size: 11; font-family: Calibri; color: #000000">ITP: transfer request creation date</span></p>         </td>
         <td>From FDATE (Catalog)         </td>
         <td>From date_create: date         </td>
         <td>  MLHDATR         </td>
      </tr>
      <tr>
         <td>RequestCreationTime         </td>
         <td>Time         </td>
         <td>N/A         </td>
         <td><p>If the value of the State attribute is:</p>
<ul>
<li>SENT: The value of this attribute is local time of the creation of the file on the Sender side.</li>
<li><span style="font-size: 11; font-family: Calibri; color: #000000">RECEIVED: The value of this attribute is the time of the creation of the file on the Sender side.
</span></li>
</ul>
<p><span style="font-size: 11; font-family: Calibri; color: #000000">ITP: transfer request creation time.</span></p>         </td>
         <td>From FTIME (Catalog)         </td>
         <td>From date_create: time         </td>
         <td>  MLHTIMR         </td>
      </tr>
      <tr>
         <td>TransmissionDuration         </td>
         <td>Integer         </td>
         <td>N/A         </td>
         <td>Transfer duration, expressed in seconds.         </td>
         <td>From TIMES (Catalog)         </td>
         <td>date_end-date_begin         </td>
         <td>MLHDATDT - MLHDATFT         </td>
      </tr>
   </tbody>
</table>

### Transfer protocols

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Sentinel         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Data type         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Length         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Description         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Transfer CFT         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">InterPEL Core         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">InterPEL MVS         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Protocol         </td>
         <td>String         </td>
         <td>25         </td>
         <td><p>Name of the protocol that operates at the Protocol Layer of the transfer. Possible values:</p>
<ul>
<li>CFT (PeSIT, version CFT)</li>
<li>PSIT_HS_E (PeSIT, version E)</li>
<li>PSIT_HS_D (PeSIT, version D)</li>
<li>ODT (ODETTE File Transfer Protocol)</li>
</ul>         </td>
         <td>Protocol Type:
"CFT
"PSIT_HS_E"
"ODT"
"SFTP"         </td>
         <td><p>From protocol: "PSIT_HS_E"</p>
<p>"PSIT_HS_D"</p>
<p>"PEL"</p>
<p>"ETB3"</p>
<p>"ODT"</p>
<p>"ETB5V1"</p>
<p>"ETB5V2"</p>
<p>"FTP"</p>         </td>
         <td>  MLHPROT         </td>
      </tr>
      <tr>
         <td>IsSSL         </td>
         <td>String         </td>
         <td>1         </td>
         <td><p>1: SSL/TLS used for the transfer.</p>
<p>0: SSL/TLS not used for the transfer.</p>         </td>
         <td><p>from SSLMODE (Catalog)
cMode = C or S &gt; "1"</p>
<p>cMode = "" &gt; "0"</p>         </td>
         <td><p>from sprof:</p>
<p>"0": empty</p>
<p>"1": not empty</p>         </td>
         <td>MLHSSLPR         </td>
      </tr>
      <tr>
         <td>SSLAuth         </td>
         <td>String         </td>
         <td>1         </td>
         <td><ul>
<li>S: The Server sent X.509 certificates to the Requester.</li>
<li>B: Both the Server and the Requester sent X.509 certificates to each other.</li>
<li>N: Neither the Server nor the Requester sent X.509 certificates.</li>
</ul>         </td>
         <td>From SSLAUTH (Catalog)         </td>
         <td>From client_auth , server_auth:
same values         </td>
         <td>  MLHSSLCA         </td>
      </tr>
      <tr>
         <td>SSLCypher         </td>
         <td>String         </td>
         <td>2         </td>
         <td>The cipher suite that the Server and the Requester used during the SSL/TLS session.         </td>
         <td>From SSLCIPH (Catalog)         </td>
         <td>cipher_suite         </td>
         <td>MLHSSLCS         </td>
      </tr>
   </tbody>
</table>

### Transfer options

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Sentinel         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Data type         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Length         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Description         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Transfer CFT         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">InterPEL Core         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">InterPEL MVS         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Compression         </td>
         <td>String         </td>
         <td>1         </td>
         <td><p>One of the following:</p>
<ul>
<li>0: Undefined</li>
<li>1: Horizontal</li>
<li>2: Vertical</li>
<li>3: Both horizontal and vertical</li>
<li>4: Not compressed</li>
<li>5: Zlib</li>
</ul>         </td>
         <td><p>From NCOMP (Catalog)</p>
<p>ncomp = 0: 4</p>
<p>0 &lt; ncomp = &lt; 8: 1</p>
<p>ncomp = 8: 2</p>
<p>8 &lt; ncomp = &lt; 16: 3</p>
<p>ncomp = 16: 5</p>         </td>
         <td>From compression:
same values         </td>
         <td>  MLHCOMP         </td>
      </tr>
      <tr>
         <td>EOTProcedure         </td>
         <td>String         </td>
         <td>255         </td>
         <td>Name of the end-of-transfer procedure executed upon the completion of the transfer.         </td>
         <td>EXEC         </td>
         <td>end_xfer_scriptpath         </td>
         <td>N/A         </td>
      </tr>
      <tr>
         <td>Priority         </td>
         <td>Integer         </td>
         <td>N/A         </td>
         <td><p>Transfer priority. Receivers process transfers in the order of their priority.</p>
<p>The range of possible values for this attribute is 0 to 255.</p>
<p>The lowest priority is zero. The highest priority is 255.</p>         </td>
         <td>PRI         </td>
         <td>priority         </td>
         <td>MLHPRIO         </td>
      </tr>
      <tr>
         <td>RetryMaxNumber         </td>
         <td>Integer         </td>
         <td>N/A         </td>
         <td>Maximum number of times that the Sender can attempt to send transfers.         </td>
         <td>RETRYM         </td>
         <td>retry_count_max         </td>
         <td>MLHRETMX         </td>
      </tr>
      <tr>
         <td>RetryNumber         </td>
         <td>Integer         </td>
         <td>N/A         </td>
         <td><p>Number of times that the Sender attempted to send the transfer.</p>
<p>Each time the Sender established a connection with the Receiver, the Sender counted one attempt.</p>         </td>
         <td>RETRY         </td>
         <td>retry_count         </td>
         <td>MLHRETRY         </td>
      </tr>
      <tr>
         <td>RequestType         </td>
         <td>String         </td>
         <td>1         </td>
         <td><p>One of the following:</p>
<ul>
<li>S: The Sender sent a single transfer to a single Receiver.</li>
<li>F: The Sender sent a group of transfers to a single Receiver. For each transfer in the group, the product generated one Processing Cycle.</li>
<li>D: The Sender sent a single transfer to a group of Receivers (diffusion). For each Receiver in the group, the product generated one Processing Cycle.</li>
<li>P:  Cyclic transfer.</li>
</ul>         </td>
         <td><p>From DIFTYP and FILTYP (Catalog)</p>         </td>
         <td>from type : "S", "D".         </td>
         <td>  N/A         </td>
      </tr>
      <tr>
         <td>TransferType         </td>
         <td>String         </td>
         <td>1         </td>
         <td><p>One of the following:</p>
<ul>
<li>S: The Sender sent a single transfer to a single Receiver.</li>
<li>F: The transfer belongs to a group of transfers that the Sender sent to a single Receiver. For each transfer in the group, the product generated one Processing Cycle.</li>
<li>D: The Receiver belongs to a group of Receivers to whom the Sender sent the transfer (diffusion). For each Receiver in the group, the product generated one Processing Cycle.</li>
</ul>         </td>
         <td>Same as box above         </td>
         <td>N/A (Gateway value)         </td>
         <td>  MLHLDFKL         </td>
      </tr>
      <tr>
         <td>IsPermanent         </td>
         <td>Char         </td>
         <td>N/A         </td>
         <td>Permanent transfer         </td>
         <td>N/A         </td>
         <td>perm         </td>
         <td>N/A         </td>
      </tr>
   </tbody>
</table>

## Transfer size

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Sentinel attribute         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Data type         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Length         </th>
<th colspan="3" class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Description         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Transfer CFT</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">InterPEL Core         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">InterPEL MVS         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>FileSize         </td>
         <td>Integer         </td>
         <td>N/A         </td>
         <td><p>Size of the transferred file. This size is expressed in bytes.  </p>
<blockquote>
<p><strong>Note:</strong></p>
<p>For PeSIT, an estimation of size is given at the beginning of the transfer. This value is updated upon completion of the transfer with the real value.</p>
</blockquote>         </td>
         <td>FCARS         </td>
         <td>  file_size         </td>
         <td>  MLHNBYTE         </td>
      </tr>
      <tr>
         <td>TransmittedBytes         </td>
         <td>Integer         </td>
         <td>N/A         </td>
         <td><p>Number of bytes transferred, after decompression, to transfer the file. This size is expressed in bytes.  </p>
<blockquote>
<p><strong>Note:</strong></p>
<p>For PeSIT, this value sent is crosschecked by both the sender and receiver.</p>
</blockquote>         </td>
         <td>NCARS         </td>
         <td>x_bytes         </td>
         <td>MLHABYTE         </td>
      </tr>
   </tbody>
</table>

### Transfer structure and content

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Sentinel attribute         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Data type         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Length         </th>
<th colspan="3" class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Description         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Transfer CFT</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">InterPEL Core         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">InterPEL MVS         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>CommandType         </td>
         <td>String         </td>
         <td>1         </td>
         <td><ul>
<li>F: File transfer</li>
<li>M: Message transfer</li>
<li>A: Message reply</li>
<li>N: Message nack</li>
</ul>         </td>
         <td>TYPE         </td>
         <td>type F or M (ack/nack is in "State")         </td>
         <td><p>TYPEREQ={S|C or M}</p>         </td>
      </tr>
      <tr>
         <td><span style="font-size: 11; font-family: Calibri; color: #000000">FileOrganization (ITP Core :</span><span style="font-size: 11; font-family: Calibri; color: #000000">FileOrganisation)</span>         </td>
         <td>String         </td>
         <td>25         </td>
         <td><ul>
<li>org_sequential: The transferred data is not indexed.</li>
<li>indexed: The transferred data is indexed.</li>
<li>direct: The transferred data is assigned relative access.</li>
</ul>         </td>
         <td>FORG         </td>
         <td>file_org         </td>
         <td>GENFILE FORG={AUTO|SEQ|…}         </td>
      </tr>
      <tr>
         <td>FileType         </td>
         <td>String         </td>
         <td>60         </td>
         <td>B: The transferred file is a binary file.         </td>
         <td>FTYPE         </td>
         <td>file_type         </td>
         <td>GENFILE RECFM= {FB | … }         </td>
      </tr>
      <tr>
         <td>J, T, O, X: The transferred file is a text file.         </td>
      </tr>
      <tr>
         <td>RecordNumber         </td>
         <td>Integer         </td>
         <td>N/A         </td>
         <td><p>Number of record in the file. This size is expressed in bytes.  </p>
<blockquote>
<p><strong>Note:</strong></p>
<p>For PeSIT, this value sent is crosschecked by both the sender and receiver.</p>
</blockquote>         </td>
         <td>FREC         </td>
         <td>rec_count         </td>
         <td>MLHNBRER         </td>
      </tr>
      <tr>
         <td>RecordFormat         </td>
         <td>String         </td>
         <td>64         </td>
         <td><ul>
<li>F: Fixed - The transferred data contains fixed-length records.</li>
<li>V: Variable - The transferred data contains variable-length records.</li>
<li>U: Undefined - The structure of the transferred data is unknown.</li>
</ul>         </td>
         <td>FRECFM         </td>
         <td><p>xfer_rec_fmt:</p>
<p>"F", "V",</p>
<p>"S": Stream</p>
<p>"T" : Text</p>         </td>
         <td>  MLH1RECF         </td>
      </tr>
      <tr>
         <td>RecordSize         </td>
         <td>Integer         </td>
         <td>N/A         </td>
         <td><p>If the value of RecordFormat attribute is fixed, the value of this attribute is the size of all records in the transferred file, expressed in bytes.</p>
<p>If the value of RecordFormat is variable or undefined, the value of this attribute is the size of the largest record in the transferred file, expressed in bytes.</p>         </td>
         <td>FLRECL         </td>
         <td>rec_len         </td>
         <td>GENFILE LRECL=nnn         </td>
      </tr>
      <tr>
         <td>Transcoding         </td>
         <td><span style="font-size: 11; font-family: Calibri; color: #000000">Integer
</span><span style="font-size: 11; font-family: Calibri; color: #000000">(ITP Core : String)</span>         </td>
         <td>(ITP Core: 25)         </td>
         <td><p>Character code of the transferred data:</p>
<ul>
<li>A: ASCII</li>
<li>B: Binary</li>
<li>E: EBCDIC</li>
</ul>         </td>
         <td>FCODE         </td>
         <td><p>From: xfer_data_code,data_code:</p>
<p>A/AT: ASCII (with Transco)</p>
<p>E/ET: EBCDIC (with Transco)</p>
<p>B/BT: Binary (with Transco)</p>
<p>U/UT: Undefined (with Transco)</p>         </td>
         <td>  FILECODE {A|E|B}         </td>
      </tr>
      <tr>
         <td>TranslationTableId         </td>
         <td>String         </td>
         <td>25         </td>
         <td>Name of the local translation table use during the transfer (if any).         </td>
         <td>XLATE         </td>
         <td>N/A (data_code, not set)         </td>
         <td>N/A         </td>
      </tr>
      <tr>
         <td>BlockSize         </td>
         <td>Integer         </td>
         <td>N/A         </td>
         <td>File block size (used by some OS)         </td>
         <td>From FBLKSIZE (Catalog)         </td>
         <td>block_size         </td>
         <td>N/A         </td>
      </tr>
   </tbody>
</table>

### Other attributes

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Sentinel attribute         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Data type         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Length         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Description         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Transfer CFT         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">InterPEL Core         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">InterPEL MVS         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>IsRelay         </td>
         <td>String         </td>
         <td>1         </td>
         <td><p>If transfer event comes from a relay site:</p>
<ul>
<li>1: Yes</li>
<li>0: No</li>
</ul>         </td>
         <td>IsRelay         </td>
         <td>N/A         </td>
         <td>N/A         </td>
      </tr>
      <tr>
         <td>NodeId         </td>
         <td>Integer         </td>
         <td>          </td>
         <td>Identifier of the node that executes the transfer.         </td>
         <td>NodeID         </td>
         <td>N/A         </td>
         <td>N/A         </td>
      </tr>
      <tr>
         <td>ParentCycleid         </td>
         <td>String         </td>
         <td>250         </td>
         <td>The identifier of the event which is the parent of the current event.         </td>
         <td>ParentCycleid         </td>
         <td>N/A         </td>
         <td>N/A         </td>
      </tr>
      <tr>
         <td>CycleId         </td>
         <td>String         </td>
         <td>250         </td>
         <td>CycleId         </td>
         <td>From TRKR (Catalog) symbolic variable &amp;XFRCYCID         </td>
         <td>this_cycle_id (not stored)         </td>
         <td>MLHTKCID         </td>
      </tr>
      <tr>
         <td>InternalCycleId         </td>
         <td>String         </td>
         <td>155         </td>
         <td>CycleID before hash.         </td>
         <td>Not stored         </td>
         <td>this_extended_cycle_id (not stored)         </td>
         <td>Not stored         </td>
      </tr>
      <tr>
         <td>State         </td>
         <td>String         </td>
         <td>20         </td>
         <td>Transfer state.         </td>
         <td><p>From: STATE,PHASE,</p>
<p>PHASESTEP,STATED,</p>
<p>DIRECT,DIAGI,FLAF</p>
<p>(Catalog):</p>
<p>"CONSUMED", "SENDING",</p>
<p>"SENT"
"RECEIVING",</p>
<p>"RECEIVED",
"TO_EXECUTE",</p>
<p>"CANCELED",
"DELETED",</p>
<p>"SUSPENDED"</p>
<p>"INTERRUPTED", "CREATED",</p>
<p>"TO_ROUTE","ACKED", "ENDED_TO_ACK",</p>
<p>"AVAILABLE", "ROUTED","NACKED",</p>
<p>"ENDED_TO-NACK",</p>
<p>"PRE_PROC",</p>
<p>"PRE_PROC_ABORT",</p>
<p>"POST_PROC",</p>
<p>"POST_PROC_ABORT",</p>
<p>"POST_PROC-ACK",</p>
<p>"POST_PROC_ACK_ABORT",</p>
<p>"ACK_EXPECTED",</p>
<p>"COMPLETED",</p>
<p>"DELETED"</p>         </td>
         <td><p>From state,
direction,
mode,
user_processed,
route_state:</p>
<p>"CONSUMED",</p>
<p>"SENDING",</p>
<p>"SENT"</p>
<p>"RECEIVING",</p>
<p>"RECEIVED",</p>
<p>"TO_EXECUTE",</p>
<p>"CANCELED",</p>
<p>"DELETED",</p>
<p>"SUSPENDED"</p>
<p>"INTERRUPTED",</p>
<p>"CREATED",</p>
<p>"TO_ROUTE",</p>
<p>"TO_SIGN",</p>
<p>"ACKED",</p>
<p>"ENDED_TO_ACK",</p>
<p>"AVAILABLE",</p>
<p>"ROUTED",</p>
<p>"ROUTE_FAILED"</p>         </td>
         <td>MLHSTATU         </td>
      </tr>
      <tr>
         <td>ReturnCode         </td>
         <td>String         </td>
         <td>20         </td>
         <td>Last transfer diagnostic.         </td>
         <td>From DIAGI and DIAGP (Catalog)         </td>
         <td>last_end_diag         </td>
         <td>MLHPDTSE + MLHPDCSE         </td>
      </tr>
      <tr>
         <td>UserState         </td>
         <td>String         </td>
         <td>20         </td>
         <td>Transfer user state.         </td>
         <td>From APPSTATE (Catalog)         </td>
         <td>user_state         </td>
         <td>N/A         </td>
      </tr>
   </tbody>
</table>

## XFBLog tracked object

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Sentinel attribute         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Data type         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Length         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Description         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Transfer CFT         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">InterPEL Core         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">InterPEL MVS         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Monitor         </td>
         <td>N/A         </td>
         <td>N/A         </td>
         <td>Monitor         </td>
         <td>"XFB"         </td>
         <td>See "Monitor" in Transfer object         </td>
         <td>PEL         </td>
      </tr>
      <tr>
         <td>Product         </td>
         <td>String         </td>
         <td>10         </td>
         <td>Product         </td>
         <td>"CFT"         </td>
         <td>See "Machine" in Transfer object         </td>
         <td>PELIMVS         </td>
      </tr>
      <tr>
         <td>ProductName         </td>
         <td>String         </td>
         <td>50         </td>
         <td>Product identifier         </td>
         <td>N/A         </td>
         <td>"XFBLog"         </td>
         <td>INTERPELMVS         </td>
      </tr>
      <tr>
         <td>ApplicationName         </td>
         <td>String         </td>
         <td>40         </td>
         <td>Application name         </td>
         <td>PART from CFTPARM         </td>
         <td>local_site_alias         </td>
         <td>PELPARMS ID= or LOCNAME=         </td>
      </tr>
      <tr>
         <td>ReturnMessage         </td>
         <td>String         </td>
         <td>512         </td>
         <td>N/A         </td>
         <td>From Log text         </td>
         <td>From Log text         </td>
         <td>From Log text         </td>
      </tr>
      <tr>
         <td>EventDate         </td>
         <td>Date         </td>
         <td>N/A         </td>
         <td>Creation date         </td>
         <td>From log timestamp: date         </td>
         <td>From log timestamp: date         </td>
         <td>From log timestamp dd:mm:yyyy         </td>
      </tr>
      <tr>
         <td>EventTime         </td>
         <td>Time         </td>
         <td>N/A         </td>
         <td>Creation time         </td>
         <td>From log timestamp: time         </td>
         <td>From log timestamp: time         </td>
         <td>From log timestamp hh:mm:ss         </td>
      </tr>
      <tr>
         <td>RecDate         </td>
         <td>Date         </td>
         <td>N/A         </td>
         <td>Record date         </td>
         <td>From log timestamp: date         </td>
         <td>From log timestamp: date         </td>
         <td>From log timestamp dd:mm:yyyy         </td>
      </tr>
      <tr>
         <td>RecTime         </td>
         <td>Time         </td>
         <td>N/A         </td>
         <td>Record time         </td>
         <td>From log timestamp: time         </td>
         <td>From log timestamp: time         </td>
         <td>From log timestamp hh:mm:ss         </td>
      </tr>
      <tr>
         <td>IdentMsg         </td>
         <td>String         </td>
         <td>10         </td>
         <td>Log message identifier         </td>
         <td>From Log text (header)         </td>
         <td>From Log Ident         </td>
         <td>From Log Ident         </td>
      </tr>
      <tr>
         <td>IsEnd         </td>
         <td>Integer         </td>
         <td>N/A         </td>
         <td>End of message. (multi-messages)         </td>
         <td>N/A         </td>
         <td>1         </td>
         <td>N/A         </td>
      </tr>
      <tr>
         <td>SeverityClass         </td>
         <td>String         </td>
         <td>10         </td>
         <td>N/A         </td>
         <td>N/A         </td>
         <td><p>From log message severity:</p>
<p>"I" &gt; "IG"</p>
<p>"W" &gt; "AV"</p>
<p>"E" &gt; "EC"</p>         </td>
         <td><p>From log message severity:</p>
<p>"I" &gt; "IG"</p>
<p>"W" &gt; "AV"</p>
<p>"E" &gt; "EC"</p>         </td>
      </tr>
      <tr>
         <td>Severity         </td>
         <td>Integer         </td>
         <td>N/A         </td>
         <td>N/A         </td>
         <td>N/A         </td>
         <td><p>From log message severity:</p>
<p>"I" &gt; 1</p>
<p>"W" &gt; 2</p>
<p>"E" &gt; 3</p>         </td>
         <td>N/A         </td>
      </tr>
      <tr>
         <td>IsAlert         </td>
         <td>Integer         </td>
         <td>N/A         </td>
         <td>Log message is an alert         </td>
         <td>From log message severity: E,F &gt; "1"         </td>
         <td><p>From log message severity:</p>
<p>"W",</p>
<p>"E" &gt; "1"</p>         </td>
         <td>From Alert indication         </td>
      </tr>
   </tbody>
</table>
