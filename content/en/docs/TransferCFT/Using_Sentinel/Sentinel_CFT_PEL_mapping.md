{
    "title": "Sentinel to Transfer CFT to InterPEL mapping",
    "linkTitle": "Sentinel to Transfer CFT to InterPEL mapping",
    "weight": "260"
}The following tables list parameter correspondence between Transfer CFT, Sentinel, and InterPEL. You find this mapping using in migrating from InterPEL to Transfer CFT.

> **Note**  
> The fields prefixed with "MLH" are fields that are specific to the PeSIT Hors SIT protocol, which are contained in the recording transfer from the Mailbox and are accessible by the Assembly Exits.

## XFBTransfer tracked object

### Roles


|  Sentinel<br/>attribute  | Data type  | Length  | Description  | Transfer CFT  | InterPEL Core  | InterPEL MVS  |
| --- | --- | --- | --- | --- | --- | --- |
| Direction  | Integer  | -  |  S: The file is sent (Sender).<br/>R: The file is received (Receiver).  | DIRECT  |  From direction:<br/>"R" "E" "B"  | TYPEREQ={S|M or C}  |
| IsServer  | Integer  | -  |  1: The Sender or the Receiver is a Server.<br/>0: The Sender the Receiver is a Requester.  | FLAG  |  From mode:<br/>Initiator "R" Responder "S"  | MLHMODR - Initiator “R” Responder “S” (depending on the STOSR parameter)  |


### Senders and receivers


| Sentinel  | Data type  | Length  | Description  | Transfer CFT  | InterPEL Core  | InterPEL MVS  |
| --- | --- | --- | --- | --- | --- | --- |
| Site  | String  | 25  | Partner alias of the remote partner.  | PART  | remote_agent  | DEST  |
| ReceiverId  | String  | 80  | Name of the Receiver.  | NRPART  |  from:<br/>local_agent_ident (direct IN)<br/>remote_agent_ident (direct OUT)  | MLHDEM (from LOCAL or SITLNAM parameters)  |
| SenderId  | String  | 80  | Name of the Sender.  | NSPART  |  from:<br/>remote_agent_ident (direct IN)<br/>local_agent_ident (direct OUT)  | MLHSERV (from DEST or ALTLOCN parameters)  |
| RAppl  | String  | 80  | Optional identifier of the Receiving application.  | RAPPL  | rcv_appli  | N/A  |
| SAppl  | String  | 80  | Optional identifier of the Sending application.  | SAPPL  | snd_appli  | N/A  |
| SourceApplication  | String  | 100  |  The source application for a Central Governance flow, for monitoring purposes.<br/>The source system is the system that initiates a flow.  | SOURCEAPPL  | N/A  | N/A  |
| TargetApplication  | String  | 100  |  The target application in a Central Governance flow, for monitoring purposes.<br/>The target system is the system making a request to initiate the flow.  | TARGETAPPL  | N/A  | N/A  |
| FinalReceiverId  | String  | 80  | Name of the final Receiver when using Store and Forward, otherwise the same as the ReceiverId.  | NDEST  | destination  | MLHBP  |
| OriginalSenderId  | String  | 80  | Name of the original Sender when using Store and Forward, otherwise the same as the SenderId.  | NORIG  | originator  | MLHORG1  |


### Product identification

The product that sends the events is identified with the following:


| Sentinel  | Data type  | Length  | Description  | Transfer CFT  | InterPEL Core  | InterPEL MVS  |
| --- | --- | --- | --- | --- | --- | --- |
| Location  | String  | 31  | Unique and logical identifier for the product.  | PART parameter of the CFTPARM object.  | local_site_alias  | LOCNAME of PELPARMS  |
| Monitor  | String  | 4  | Product name.  | “CFT”  | MSG_PROD_MONITOR_PEL &gt; "PEL"  | "PEL"  |
| MonitorVersion  | String  | 25  | Product version.  | Product version  |  Computation of:<br/>MSG_XFB_MONITOR_VERSION &gt; "6.6.3"  | "732"  |
| Machine  | String  | 25  | Name of the  application and platform that run on a Transfer CFT  |  PRODUCT_TYPE:<br/>"CFT-UNIX" "CFTL-NT" "CFT-MVS" "CFT-400" "CFT-NSK" "CFT-VMS"  |  PRODUCT_TYPE:<br/>"PEL-UNIX" "PEL-NT" "PEL-400" "PEL-NSK"  | PELIMVS  |
| ProductName  | String  | 50  | N/A  | uconf: sentinel.trkproductname  | local_site_alias  | N/A  |


### Transfer users


| Sentinel  | Data type  | Length  | Description  | Transfer CFT  | InterPEL Core  | InterPEL MVS  |
| --- | --- | --- | --- | --- | --- | --- |
| UserId  | String  | 25  | Local identifier of the user who owns the transferred file.  | USERID  | N/A  | N/A  |
| GroupId  | String  | 25  | Local identifier of the group to which the transfer owner belongs.  | GROUPID  | N/A  | N/A  |
| RequestUserId  | String  | 25  | Local identifier of the user who requested the transfer.  | REQUSER  | username  | MLHUSERN  |
| RequestGroupId  | String  | 25  | Local identifier of the group to which the requesting user belongs.  | REQGROUP  | N/A  | N/A  |
| Trustee  | String  | 25  |  If User Access Control is:<br/> • Activated for the transfer, the value of this attribute is the local identifier of the transfer owner (UserId).<br/> • Not activated for the transfer, the value of this attribute is the network identifier of the user who requested the transfer (RequestUserId).</li>  | IDAPPL  | N/A  |  N/A  |
| RUser  | String  | 30  | Optional local identifier of the user who received the transfer.  | RUSER  | rcv_user  | MLHUSERN  |
| SUser  | String  | 30  | Optional local identifier of the user who sent the transfer.  | SUSER  | snd_user  | N/A  |


### Transfer identification


| Sentinel  | Data type  | Length  | Description  | Transfer CFT  | InterPEL Core  | InterPEL MVS  |
| --- | --- | --- | --- | --- | --- | --- |
| IdAppl  | String  | 25  |  If the value of the IsServer attribute is:<br/> • 0: The value of this attribute is the local identifier of the Requester.<br/> • 1: The value of this attribute is empty.</li>  | IDA  | N/A  |  auto PEL1  |
| Application  | String  | 80  | Local application/Transfer profile (ST).  | IDF  | application  | APPL  |
| FileName  | String  | 512  |  If the value of the CommandType attribute is File and the value of the Direction attribute is:<br/> • E (Sender): This attribute identifies the file from which the Sender retrieved the transfer data (full path).<br/> • R (Receiver): This attribute identifies the file in which the Receiver recorded the transfer data (full path).</li>  | FNAME  | dir_path/file_component  |  DSNORIG  |
| LocalId  | String  | 25  |  If the value of the Direction attribute is:<br/> • E (Sender): The value of this attribute is the local transfer identifier for the Sender.<br/> • R (Receiver): The value of this attribute is the local transfer identifier for the Receiver.</li>  | IDTU  |  local_ident  |  auto MLY_TRID  |
| ProtocolFileName  | String  | 512  |  Network transfer identifier.<br/>The Sender sent this identifier to the Receiver.  | NIDF  | file_name  | N  |
| ProtocolFileLabel  | String  | 80  |  The Sender sent this name to the Receiver.<br/>The Receiver can use this name to locally name the transfer.  | NFNAME  | file_label  | LABEL  |
| ProtocolId  | String  | 80  |  Network transfer identifier.<br/>The Sender generated this identifier.<br/>The Receiver acknowledged this identifier.  | NIDT  | xfer_ident  | MLHRANG  |
| ProtocolMessage  | String  | 4000  |  If the value of the CommandType attribute is:<br/> • Message: The value of this attribute is the content of the transferred message.<br/> • File: This attribute is empty.</li>  | SMSG  |  From:<br/> • snd_msg (message OUT)<br/> • rcv_msg (message IN)</li>  |  MSG1/ MSG2<br/>(Interpel MVS MSG1/MSG2/<br/>MSG3/MSG4/<br/>MSG5)  |
| PositionNumber  | String  | 80  |  Local transfer identifier. If the value of the Direction attribute is:<br/> • E (Sender): The value of this attribute identifies the transfer in the Sender's transfer catalog or DB.<br/> • R (Receiver): The value of this attribute identifies the transfer in the Receiver's transfer catalog or DB.</li>  | IDT  | sequence  |  auto MLBCLE  |
| ProtocolParameter  | String  | 512  |  Network transfer description.<br/>The Sender sent this description to the Receiver.  | PARM  |  from:<br/> • snd_msg (transfer OUT)<br/> • rcv_msg (transfer IN)</li>  |  MSG1<br/>(Interpel MVS MSG1/MSG2/<br/>MSG3/MSG4/<br/>MSG5)  |
| UserParameter1  | String  | 255  |  Local transfer description.<br/>This description is recorded at the transfer request time in the local DB and remains local.  | COMMENT  | param1  | USERAREA  |
| Flowname  | String  | 100  | Parameter to define a flow name in Central Governance for monitoring purposes.  | Flowname (v3.1.x)  | N/A  | N/A  |
| UserParameter2  | String  | 255  |  Local transfer description.<br/>This description is recorded at the transfer request time in the local DB and remains local.  | N/A  | param2  | N/A  |
| VirtualDirName  | String  | 255  | Virtual directory name  | N/A  | dir_name (not stored, always empty)  | N/A  |


### Transfer validity periods


| Sentinel  | Data type  | Length  | Description  | Transfer CFT  | InterPEL Core  | InterPEL MVS  |
| --- | --- | --- | --- | --- | --- | --- |
| EarliestDate  | Date  | N/A  | Date on which the validity period begins.  | DATEM (Catalog)  | From date_to_begin: date  | SDATE {aaqqq | +n}  |
| EarliestTime  | Time  | N/A  | Time at which the validity period begins.  | TIMEM (Catalog)  | From date_to_begin: time  | HSDEB  |
| LatestDate  | Date  | N/A  | Date on which the validity period ends.  | DATEMAX (Catalog)  | From date_to_end: date  | N/A  |
| LatestTime  | Time  | N/A  | Time at which the validity period ends.  | TIMEMAX (Catalog)  | From date_to_end: time  | HSFIN  |


### Transfer dates and times

<table>
   <thead>
      <tr>
<th >Sentinel         </th>
<th >Data type         </th>
<th >Length         </th>
<th >Description         </th>
<th >Name in         </th>
<th >InterPEL Core         </th>
<th >InterPEL MVS         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td >CreationDate         </td>
         <td >Date         </td>
         <td >N/A         </td>
         <td ><p>By default, the system date on which the Sender sent the transfer.</p>
<ul>
<li>The Sender can set this date.</li>
<li>The Receiver can filter transfers based on this date.</li>
</ul>         </td>
         <td >From FDATE (Catalog)         </td>
         <td >From hist_create_date: date         </td>
         <td >CDATE=aaqqq         </td>
      </tr>
      <tr>
         <td >CreationTime         </td>
         <td >Time         </td>
         <td >N/A         </td>
         <td ><p>By default, the system time at which the Sender sent the transfer.</p>
<ul>
<li>The Sender can set this time.</li>
<li>The Receiver can filter transfers based on this time.</li>
</ul>         </td>
         <td >From FTIME (Catalog)         </td>
         <td >From hist_create_date: time         </td>
         <td >CTIME=hhmmss         </td>
      </tr>
      <tr>
         <td >SendDate         </td>
         <td >Date         </td>
         <td >N/A         </td>
         <td ><p>If the value of the Direction attribute is:</p>
<ul>
<li>E (Sender): The value of this attribute is the date on which the Sender recorded the transfer in the transfer catalog.</li>
<li>R (Receiver): The value of this attribute is the date on which the Receiver recorded the transfer in the transfer catalog. The Sender and the Receiver record each transfer only once.</li>
</ul>         </td>
         <td >From DATEK (Catalog)         </td>
         <td >N/A         </td>
         <td >N/A         </td>
      </tr>
      <tr>
         <td >SendTime         </td>
         <td >Time         </td>
         <td >N/A         </td>
         <td ><p>If the value of the Direction attribute is:</p>
<ul>
<li>E (Sender): The value of this attribute is the local time at which the Sender recorded the transfer in the transfer catalog.</li>
<li>R (Receiver): The value of this attribute is the local time at which the Receiver recorded the transfer in the transfer catalog.</li>
</ul>
The Sender and the Receiver record each transfer only once.         </td>
         <td >From TIMEK (Catalog)         </td>
         <td >N/A         </td>
         <td >N/A         </td>
      </tr>
      <tr>
         <td >AckDate         </td>
         <td >Date         </td>
         <td >N/A         </td>
         <td >Date on which the Receiver acknowledged the transfer (if any).         </td>
         <td rowspan="2" >From Current Date when ack         </td>
         <td rowspan="2" >N/A         </td>
         <td rowspan="2" >N/A         </td>
      </tr>
      <tr>
         <td >AckTime         </td>
         <td >Time         </td>
         <td >N/A         </td>
         <td >Time at which the Receiver acknowledged the transfer (if any).         </td>
      </tr>
      <tr>
         <td >StartDate         </td>
         <td >Date         </td>
         <td >N/A         </td>
         <td ><p>If the value of the State attribute is:</p>
<ul>
<li>SENT: The value of this attribute is the date on which the Sender began sending the transfer.</li>
<li>RECEIVED: The value of this attribute is the date on which the Receiver began receiving the transfer.</li>
</ul>
<p>These dates are expressed in dd.mm.yyyy format.</p>         </td>
         <td >From DATEB (Catalog)         </td>
         <td >From date_begin: date         </td>
         <td > (MVS) SDATE, MLHDATDT         </td>
      </tr>
      <tr>
         <td >StartTime         </td>
         <td >Time         </td>
         <td >N/A         </td>
         <td ><p>If the value of the State attribute is:</p>
<ul>
<li>SENT: The value of this attribute is the local time at which the Sender began sending the transfer.</li>
<li>RECEIVED: The value of this attribute is the local time at which the Receiver began receiving the transfer.</li>
</ul>
<p>These times are expressed in hh:mn:ss format.</p>         </td>
         <td >From TIMEB (Catalog)         </td>
         <td >From date_begin: time         </td>
         <td ><p>  MLHHEUDT</p>
<p>(MVS does not exist in Pelica2 requests)</p>         </td>
      </tr>
      <tr>
         <td >EndDate         </td>
         <td >Date         </td>
         <td >N/A         </td>
         <td ><p>If the value of the State attribute is:</p>
<ul>
<li>SENT: The value of this attribute is the date on which the Sender stopped sending the transfer.</li>
<li>RECEIVED: The value of this attribute is the date on which the Receiver stopped receiving the transfer.</li>
</ul>
<p>These dates are expressed in dd.mm.yyyy format.</p>         </td>
         <td >From DATEE (Catalog)         </td>
         <td >From date_end: date         </td>
         <td >  MLHDATFT         </td>
      </tr>
      <tr>
         <td >EndTime         </td>
         <td >Time         </td>
         <td >N/A         </td>
         <td ><p>If the value of the State attribute is:</p>
<ul>
<li>SENT: The value of this attribute is the local time at which the Sender stopped sending the transfer.</li>
<li>RECEIVED: The value of this attribute is the local time at which the Receiver stopped receiving the transfer.</li>
</ul>
<p>These times are expressed in hh:mn:ss format.</p>         </td>
         <td >From TIMEE (Catalog)         </td>
         <td >From date_end: time         </td>
         <td >  MLHHEUFT         </td>
      </tr>
      <tr>
         <td >RequestCreationDate         </td>
         <td >Date         </td>
         <td >N/A         </td>
         <td ><p>If the value of the State attribute is:</p>
<ul>
<li>SENT: The value of this attribute is local date of the creation of the file on the Sender side.</li>
<li></li>
</ul>         </td>
         <td >From FDATE (Catalog)         </td>
         <td >From date_create: date         </td>
         <td >  MLHDATR         </td>
      </tr>
      <tr>
         <td >RequestCreationTime         </td>
         <td >Time         </td>
         <td >N/A         </td>
         <td ><p>If the value of the State attribute is:</p>
<ul>
<li>SENT: The value of this attribute is local time of the creation of the file on the Sender side.</li>
<li></li>
</ul>         </td>
         <td >From FTIME (Catalog)         </td>
         <td >From date_create: time         </td>
         <td >  MLHTIMR         </td>
      </tr>
      <tr>
         <td >TransmissionDuration         </td>
         <td >Integer         </td>
         <td >N/A         </td>
         <td >Transfer duration, expressed in seconds.         </td>
         <td >From TIMES (Catalog)         </td>
         <td >date_end-date_begin         </td>
         <td >MLHDATDT - MLHDATFT         </td>
      </tr>
   </tbody>
</table>

### Transfer protocols


| Sentinel  | Data type  | Length  | Description  | Transfer CFT  | InterPEL Core  | InterPEL MVS  |
| --- | --- | --- | --- | --- | --- | --- |
| Protocol  | String  | 25  |  Name of the protocol that operates at the Protocol Layer of the transfer. Possible values:<br/> • CFT (PeSIT, version CFT)<br/> • PSIT_HS_E (PeSIT, version E)<br/> • PSIT_HS_D (PeSIT, version D)<br/> • ODT (ODETTE File Transfer Protocol)</li>  | Protocol Type: "CFT "PSIT_HS_E" "ODT" "SFTP"  |  From protocol: "PSIT_HS_E"<br/>"PSIT_HS_D"<br/>"PEL"<br/>"ETB3"<br/>"ODT"<br/>"ETB5V1"<br/>"ETB5V2"<br/>"FTP"  |  MLHPROT  |
| IsSSL  | String  | 1  |  1: SSL/TLS used for the transfer.<br/>0: SSL/TLS not used for the transfer.  |  from SSLMODE (Catalog) cMode = C or S &gt; "1"<br/>cMode = "" &gt; "0"  |  from sprof:<br/>"0": empty<br/>"1": not empty  | MLHSSLPR  |
| SSLAuth  | String  | 1  |  <li>S: The Server sent X.509 certificates to the Requester.<br/> • B: Both the Server and the Requester sent X.509 certificates to each other.<br/> • N: Neither the Server nor the Requester sent X.509 certificates.</li>  | From SSLAUTH (Catalog)  | From client_auth , server_auth: same values  |  MLHSSLCA  |
| SSLCypher  | String  | 2  | The cipher suite that the Server and the Requester used during the SSL/TLS session.  | From SSLCIPH (Catalog)  | cipher_suite  | MLHSSLCS  |


### Transfer options


| Sentinel  | Data type  | Length  | Description  | Transfer CFT  | InterPEL Core  | InterPEL MVS  |
| --- | --- | --- | --- | --- | --- | --- |
| Compression  | String  | 1  |  One of the following:<br/> • 0: Undefined<br/> • 1: Horizontal<br/> • 2: Vertical<br/> • 3: Both horizontal and vertical<br/> • 4: Not compressed<br/> • 5: Zlib</li>  |  From NCOMP (Catalog)<br/>ncomp = 0: 4<br/>0 &lt; ncomp = &lt; 8: 1<br/>ncomp = 8: 2<br/>8  &lt; ncomp = &lt; 16: 3<br/>ncomp = 16: 5  | From compression: same values  |  MLHCOMP  |
| EOTProcedure  | String  | 255  | Name of the end-of-transfer procedure executed upon the completion of the transfer.  | EXEC  | end_xfer_scriptpath  | N/A  |
| Priority  | Integer  | N/A  |  Transfer priority. Receivers process transfers in the order of their priority.<br/>The range of possible values for this attribute is 0 to 255.<br/>The lowest priority is zero. The highest priority is 255.  | PRI  | priority  | MLHPRIO  |
| RetryMaxNumber  | Integer  | N/A  | Maximum number of times that the Sender can attempt to send transfers.  | RETRYM  | retry_count_max  | MLHRETMX  |
| RetryNumber  | Integer  | N/A  |  Number of times that the Sender attempted to send the transfer.<br/>Each time the Sender established a connection with the Receiver, the Sender counted one attempt.  | RETRY  | retry_count  | MLHRETRY  |
| RequestType  | String  | 1  |  One of the following:<br/> • S: The Sender sent a single transfer to a single Receiver.<br/> • F: The Sender sent a group of transfers to a single Receiver. For each transfer in the group, the product generated one Processing Cycle.<br/> • D: The Sender sent a single transfer to a group of Receivers (diffusion). For each Receiver in the group, the product generated one Processing Cycle.<br/> • P: Cyclic transfer.</li>  |  From DIFTYP and FILTYP  (Catalog)  | from type : "S", "D".  |  N/A  |
| TransferType  | String  | 1  |  One of the following:<br/> • S: The Sender sent a single transfer to a single Receiver.<br/> • F: The transfer belongs to a group of transfers that the Sender sent to a single Receiver. For each transfer in the group, the product generated one Processing Cycle.<br/> • D: The Receiver belongs to a group of Receivers to whom the Sender sent the transfer (diffusion). For each Receiver in the group, the product generated one Processing Cycle.</li>  | Same as box above  | N/A (Gateway value)  |  MLHLDFKL  |
| IsPermanent  | Char  | N/A  | Permanent transfer  | N/A  | perm  | N/A  |


## Transfer size

<table>
   <thead>
      <tr>
<th >Sentinel attribute         </th>
<th >Data type         </th>
<th >Length         </th>
<th colspan="3" >Description         </th>
<th ><p>Transfer CFT</p>         </th>
<th >InterPEL Core         </th>
<th >InterPEL MVS         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td >FileSize         </td>
         <td >Integer         </td>
         <td >N/A         </td>
         <td colspan="3" ><p>Size of the transferred file. This size is expressed in bytes.  </p>
<blockquote>
<p><strong>Note</strong></p>
<p>For PeSIT, an estimation of size is given at the beginning of the transfer. This value is updated upon completion of the transfer with the real value.</p>
</blockquote>         </td>
         <td >FCARS         </td>
         <td >  file_size         </td>
         <td >  MLHNBYTE         </td>
      </tr>
      <tr>
         <td >TransmittedBytes         </td>
         <td >Integer         </td>
         <td >N/A         </td>
         <td colspan="3" ><p>Number of bytes transferred, after decompression, to transfer the file. This size is expressed in bytes.  </p>
<blockquote>
<p><strong>Note</strong></p>
<p>For PeSIT, this value sent is crosschecked by both the sender and receiver.</p>
</blockquote>         </td>
         <td >NCARS         </td>
         <td >x_bytes         </td>
         <td >MLHABYTE         </td>
      </tr>
   </tbody>
</table>

### Transfer structure and content

<table>
   <thead>
      <tr>
<th >Sentinel attribute         </th>
<th >Data type         </th>
<th >Length         </th>
<th colspan="3" >Description         </th>
<th ><p>Transfer CFT</p>         </th>
<th >InterPEL Core         </th>
<th >InterPEL MVS         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td >CommandType         </td>
         <td >String         </td>
         <td >1         </td>
         <td colspan="3" ><ul>
<li>F: File transfer</li>
<li>M: Message transfer</li>
<li>A: Message reply</li>
<li>N: Message nack</li>
</ul>         </td>
         <td >TYPE         </td>
         <td >type F or M (ack/nack is in "State")         </td>
         <td ><p>TYPEREQ={S|C or M}</p>         </td>
      </tr>
      <tr>
         <td >         </td>
         <td >String         </td>
         <td >25         </td>
         <td colspan="3" ><ul>
<li>org_sequential: The transferred data is not indexed.</li>
<li>indexed: The transferred data is indexed.</li>
<li>direct: The transferred data is assigned relative access.</li>
</ul>         </td>
         <td >FORG         </td>
         <td >file_org         </td>
         <td >GENFILE FORG={AUTO|SEQ|…}         </td>
      </tr>
      <tr>
         <td rowspan="2" >FileType         </td>
         <td rowspan="2" >String         </td>
         <td rowspan="2" >60         </td>
         <td colspan="3" >B: The transferred file is a binary file.         </td>
         <td rowspan="2" >FTYPE         </td>
         <td rowspan="2" >file_type         </td>
         <td rowspan="2" >GENFILE RECFM= {FB | … }         </td>
      </tr>
      <tr>
         <td colspan="3" >J, T, O, X: The transferred file is a text file.         </td>
      </tr>
      <tr>
         <td >RecordNumber         </td>
         <td >Integer         </td>
         <td >N/A         </td>
         <td colspan="3" ><p>Number of record in the file. This size is expressed in bytes.  </p>
<blockquote>
<p><strong>Note</strong></p>
<p>For PeSIT, this value sent is crosschecked by both the sender and receiver.</p>
</blockquote>         </td>
         <td >FREC         </td>
         <td >rec_count         </td>
         <td >MLHNBRER         </td>
      </tr>
      <tr>
         <td >RecordFormat         </td>
         <td >String         </td>
         <td >64         </td>
         <td colspan="3" ><ul>
<li>F: Fixed - The transferred data contains fixed-length records.</li>
<li>V: Variable - The transferred data contains variable-length records.</li>
<li>U: Undefined - The structure of the transferred data is unknown.</li>
</ul>         </td>
         <td >FRECFM         </td>
         <td ><p>xfer_rec_fmt:</p>
<p>"F", "V",</p>
<p>"S": Stream</p>
<p>"T" : Text</p>         </td>
         <td >  MLH1RECF         </td>
      </tr>
      <tr>
         <td >RecordSize         </td>
         <td >Integer         </td>
         <td >N/A         </td>
         <td colspan="3" ><p>If the value of RecordFormat attribute is fixed, the value of this attribute is the size of all records in the transferred file, expressed in bytes.</p>
<p>If the value of RecordFormat is variable or undefined, the value of this attribute is the size of the largest record in the transferred file, expressed in bytes.</p>         </td>
         <td >FLRECL         </td>
         <td >rec_len         </td>
         <td >GENFILE LRECL=nnn         </td>
      </tr>
      <tr>
         <td >Transcoding         </td>
         <td >         </td>
         <td >(ITP Core: 25)         </td>
         <td colspan="3" ><p>Character code of the transferred data:</p>
<ul>
<li>A: ASCII</li>
<li>B: Binary</li>
<li>E: EBCDIC</li>
</ul>         </td>
         <td >FCODE         </td>
         <td ><p>From: xfer_data_code,data_code:</p>
<p>A/AT: ASCII (with Transco)</p>
<p>E/ET: EBCDIC (with Transco)</p>
<p>B/BT: Binary (with Transco)</p>
<p>U/UT: Undefined (with Transco)</p>         </td>
         <td >  FILECODE {A|E|B}         </td>
      </tr>
      <tr>
         <td >TranslationTableId         </td>
         <td >String         </td>
         <td >25         </td>
         <td colspan="3" >Name of the local translation table use during the transfer (if any).         </td>
         <td >XLATE         </td>
         <td >N/A (data_code, not set)         </td>
         <td >N/A         </td>
      </tr>
      <tr>
         <td >BlockSize         </td>
         <td >Integer         </td>
         <td >N/A         </td>
         <td colspan="3" >File block size (used by some OS)         </td>
         <td >From FBLKSIZE (Catalog)         </td>
         <td >block_size         </td>
         <td >N/A         </td>
      </tr>
   </tbody>
</table>

### Other attributes


| Sentinel attribute  | Data type  | Length  | Description  | Transfer CFT  | InterPEL Core  | InterPEL MVS  |
| --- | --- | --- | --- | --- | --- | --- |
| IsRelay  | String  | 1  |  If transfer event comes from a relay site:<br/> • 1: Yes<br/> • 0: No</li>  | IsRelay  | N/A  | N/A  |
| NodeId  | Integer  |   | Identifier of the node that executes the transfer.  | NodeID  | N/A  | N/A  |
| ParentCycleid  | String  | 250  | The identifier of the event which is the parent of the current event.  | ParentCycleid  | N/A  | N/A  |
| CycleId  | String  | 250  | CycleId  | From TRKR (Catalog) symbolic variable &amp;XFRCYCID  | this_cycle_id (not stored)  | MLHTKCID  |
| InternalCycleId  | String  | 155  | CycleID before hash.  | Not stored  | this_extended_cycle_id (not stored)  | Not stored  |
| State  | String  | 20  | Transfer state.  |  From: STATE,PHASE,<br/>PHASESTEP,STATED,<br/>DIRECT,DIAGI,FLAF<br/>(Catalog):<br/>"CONSUMED", "SENDING",<br/>"SENT" "RECEIVING",<br/>"RECEIVED", "TO_EXECUTE",<br/>"CANCELED", "DELETED",<br/>"SUSPENDED"<br/>"INTERRUPTED", "CREATED",<br/>"TO_ROUTE","ACKED", "ENDED_TO_ACK",<br/>"AVAILABLE", "ROUTED","NACKED",<br/>"ENDED_TO-NACK",<br/>"PRE_PROC",<br/>"PRE_PROC_ABORT",<br/>"POST_PROC",<br/>"POST_PROC_ABORT", "POST_PROC-ACK", "POST_PROC_ACK_ABORT", "ACK_EXPECTED", "COMPLETED", "DELETED"  |  From          state,             direction,                   mode, user_processed,       route_state:&lt;/p&gt; "CONSUMED", "SENDING", "SENT" "RECEIVING", "RECEIVED", "TO_EXECUTE", "CANCELED", "DELETED", "SUSPENDED" "INTERRUPTED", "CREATED", "TO_ROUTE", "TO_SIGN", "ACKED", "ENDED_TO_ACK", "AVAILABLE", "ROUTED", "ROUTE_FAILED"  | MLHSTATU  |
| ReturnCode  | String  | 20  | Last transfer diagnostic.  | From DIAGI and DIAGP (Catalog)  | last_end_diag  | MLHPDTSE + MLHPDCSE  |
| UserState  | String  | 20  | Transfer user state.  | From APPSTATE (Catalog)  | user_state  | N/A  |


## XFBLog tracked object


| Sentinel attribute  | Data type  | Length  | Description  | Transfer CFT  | InterPEL Core  | InterPEL MVS  |
| --- | --- | --- | --- | --- | --- | --- |
| Monitor  | N/A  | N/A  | Monitor  | "XFB"  | See "Monitor" in Transfer object  | PEL  |
| Product  | String  | 10  | Product  | "CFT"  | See "Machine" in Transfer object  | PELIMVS  |
| ProductName  | String  | 50  | Product identifier  | N/A  | "XFBLog"  | INTERPELMVS  |
| ApplicationName  | String  | 40  | Application name  | PART from CFTPARM  | local_site_alias  | PELPARMS ID= or LOCNAME=  |
| ReturnMessage  | String  | 512  | N/A  | From Log text  | From Log text  | From Log text  |
| EventDate  | Date  | N/A  | Creation date  | From log timestamp: date  | From log timestamp: date  | From log timestamp dd:mm:yyyy  |
| EventTime  | Time  | N/A  | Creation time  | From log timestamp: time  | From log timestamp: time  | From log timestamp hh:mm:ss  |
| RecDate  | Date  | N/A  | Record date  | From log timestamp: date  | From log timestamp: date  | From log timestamp dd:mm:yyyy  |
| RecTime  | Time  | N/A  | Record time  | From log timestamp: time  | From log timestamp: time  | From log timestamp hh:mm:ss  |
| IdentMsg  | String  | 10  | Log message identifier  | From Log text (header)  | From Log Ident  | From Log Ident  |
| IsEnd  | Integer  | N/A  | End of message. (multi-messages)  | N/A  | 1  | N/A  |
| SeverityClass  | String  | 10  | N/A  | N/A  |  From log message severity:<br/>"I" &gt; "IG"<br/>"W" &gt; "AV"<br/>"E" &gt; "EC"  |  From log message severity:<br/>"I" &gt; "IG"<br/>"W" &gt; "AV"<br/>"E" &gt; "EC"  |
| Severity  | Integer  | N/A  | N/A  | N/A  |  From log message severity:<br/>"I" &gt; 1<br/>"W" &gt; 2<br/>"E" &gt; 3  | N/A  |
| IsAlert  | Integer  | N/A  | Log message is an alert  | From log message severity: E,F &gt; "1"  |  From log message severity:<br/>"W",<br/>"E" &gt; "1"  | From  Alert indication  |

