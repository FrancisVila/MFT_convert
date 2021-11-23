{
    "title": "XFBTransfer Tracked Object attributes",
    "linkTitle": "XFBTransfer Tracked Object attribute",
    "weight": "230"
}## Roles

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Sentinel</p>
<p>attribute</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Data type</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Length</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Description</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1"><p>Name in</p>
<p>{{< TransferCFT/componentshortname  >}}</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Direction</p>         </td>
         <td><p>Integer</p>         </td>
         <td><p>-</p>         </td>
         <td><ul>
<li>S: The file is sent (Sender).</li>
<li>R: The file is received (Receiver).</li>
</ul>         </td>
         <td><p>DIRECT</p>         </td>
      </tr>
      <tr>
         <td><p>IsServer</p>         </td>
         <td><p>Integer</p>         </td>
         <td><p>-</p>         </td>
         <td><ul>
<li>1: The Sender or the Receiver is a Server.</li>
<li>0: The Sender the Receiver is a Requester.</li>
</ul>         </td>
         <td><p>FLAG</p>         </td>
      </tr>
   </tbody>
</table>

## Senders and receivers

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Sentinel</p>
<p>attribute</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Data type</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Length</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Description</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1"><p>Name in</p>
<p>{{< TransferCFT/componentshortname  >}}</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Site</p>         </td>
         <td><p>String</p>         </td>
         <td><p>25</p>         </td>
         <td><p>Partner alias of the remote partner.</p>         </td>
         <td><p>PART</p>         </td>
      </tr>
      <tr>
         <td><p>ReceiverId</p>         </td>
         <td><p>String</p>         </td>
         <td><p>80</p>         </td>
         <td><p>Name of the Receiver.</p>         </td>
         <td><p>NRPART</p>         </td>
      </tr>
      <tr>
         <td><p>SenderId</p>         </td>
         <td><p>String</p>         </td>
         <td><p>80</p>         </td>
         <td><p>Name of the Sender.</p>         </td>
         <td><p>NSPART</p>         </td>
      </tr>
      <tr>
         <td><p>RAppl</p>         </td>
         <td><p>String</p>         </td>
         <td><p>80</p>         </td>
         <td><p>Optional identifier of the Receiving  application.</p>         </td>
         <td><p>RAPPL</p>         </td>
      </tr>
      <tr>
         <td><p>SAppl</p>         </td>
         <td><p>String</p>         </td>
         <td><p>80</p>         </td>
         <td><p>Optional identifier of the Sending  application.</p>         </td>
         <td><p>SAPPL</p>         </td>
      </tr>
      <tr>
         <td><p>SourceApplication</p>         </td>
         <td><p>String</p>         </td>
         <td><p>100</p>         </td>
         <td><p>The source application for a Central Governance flow, for monitoring purposes. The source system is the system that initiates a flow.</p>         </td>
         <td><p>SOURCEAPPL</p>         </td>
      </tr>
      <tr>
         <td><p>TargetApplication</p>         </td>
         <td><p>String</p>         </td>
         <td><p>100</p>         </td>
         <td><p>The target application in a Central Governance flow, for monitoring purposes. The target system is the system making a request to initiate the flow.</p>         </td>
         <td><p>TARGETAPPL</p>         </td>
      </tr>
      <tr>
         <td><p>FinalReceiverId</p>         </td>
         <td><p>String</p>         </td>
         <td><p>80</p>         </td>
         <td><p>Name of the final Receiver when using Store and Forward, otherwise the same as the ReceiverId.</p>         </td>
         <td><p>NDEST</p>         </td>
      </tr>
      <tr>
         <td><p>OriginalSenderId</p>         </td>
         <td><p>String</p>         </td>
         <td><p>80</p>         </td>
         <td><p>Name of the original Sender when using Store and Forward, otherwise the same as the SenderId.</p>         </td>
         <td><p>NORIG</p>         </td>
      </tr>
   </tbody>
</table>

## Product identification

The product that sends the events is identified with the following:

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Sentinel</p>
<p>attribute</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Data type</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Length</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Description</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1"><p>Name in</p>
<p>{{< TransferCFT/componentshortname  >}}</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Location</p>         </td>
         <td><p>String</p>         </td>
         <td><p>31</p>         </td>
         <td><p>Unique and logical identifier for the product.</p>         </td>
         <td><p>PART parameter of the CFTPARM object.</p>         </td>
      </tr>
      <tr>
         <td><p>Monitor</p>         </td>
         <td><p>String</p>         </td>
         <td><p>4</p>         </td>
         <td><p>Product name.</p>         </td>
         <td><p>“CFT”</p>         </td>
      </tr>
      <tr>
         <td><p>MonitorVersion</p>         </td>
         <td><p>String</p>         </td>
         <td><p>25</p>         </td>
         <td><p>Product version.</p>         </td>
         <td><p>Product version (see CFTUTIL about).</p>         </td>
      </tr>
   </tbody>
</table>

## Transfer users

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Sentinel</p>
<p>attribute</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Data type</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Length</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Description</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1"><p>Name in</p>
<p>{{< TransferCFT/componentshortname  >}}</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>UserId</p>         </td>
         <td><p>String</p>         </td>
         <td><p>25</p>         </td>
         <td><p>Local identifier of the user who owns the transferred file.</p>         </td>
         <td><p>USERID</p>         </td>
      </tr>
      <tr>
         <td><p>GroupId</p>         </td>
         <td><p>String</p>         </td>
         <td><p>25</p>         </td>
         <td><p>Local identifier of the group to which the transfer owner belongs.</p>         </td>
         <td><p>GROUPID</p>         </td>
      </tr>
      <tr>
         <td><p>RequestUserId</p>         </td>
         <td><p>String</p>         </td>
         <td><p>25</p>         </td>
         <td><p>Local identifier of the user who requested the transfer.</p>         </td>
         <td><p>REQUSER</p>         </td>
      </tr>
      <tr>
         <td><p>RequestGroupId</p>         </td>
         <td><p>String</p>         </td>
         <td><p>25</p>         </td>
         <td><p>Local identifier of the group to which the requesting user belongs.</p>         </td>
         <td><p>REQGROUP</p>         </td>
      </tr>
      <tr>
         <td><p>Trustee</p>         </td>
         <td><p>String</p>         </td>
         <td><p>25</p>         </td>
         <td><p>If User Access Control is:</p>
<ul>
<li>Activated for the transfer, the value of this attribute is the local identifier of the transfer owner (UserId).</li>
<li>Not activated for the transfer, the value of this attribute is the network identifier of the user who requested the transfer (RequestUserId).</li>
</ul>         </td>
         <td><p>IDAPPL</p>         </td>
      </tr>
      <tr>
         <td><p>RUser</p>         </td>
         <td><p>String</p>         </td>
         <td><p>30</p>         </td>
         <td><p>Optional local identifier of the user who received the transfer.</p>         </td>
         <td><p>RUSER</p>         </td>
      </tr>
      <tr>
         <td><p>SUser</p>         </td>
         <td><p>String</p>         </td>
         <td><p>30</p>         </td>
         <td><p>Optional local identifier of the user who sent the transfer.</p>         </td>
         <td><p>SUSER</p>         </td>
      </tr>
   </tbody>
</table>

## Transfer identification

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Sentinel</p>
<p>attribute</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Data type</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Length</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Description</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1"><p>Name in</p>
<p>{{< TransferCFT/componentshortname  >}}</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>IdAppl</p>         </td>
         <td><p>String</p>         </td>
         <td><p>25</p>         </td>
         <td><p>If the value of the IsServer attribute is:</p>
<ul>
<li>0: The value of this attribute is the local identifier of the Requester.</li>
<li>1: The value of this attribute is empty.</li>
</ul>         </td>
         <td><p>IDA</p>         </td>
      </tr>
      <tr>
         <td><p>Application</p>         </td>
         <td><p>String</p>         </td>
         <td><p>80</p>         </td>
         <td><p>Local application/Transfer profile (ST).</p>         </td>
         <td><p>IDF</p>         </td>
      </tr>
      <tr>
         <td><p>FileName</p>         </td>
         <td><p>String</p>         </td>
         <td><p>512</p>         </td>
         <td><p>If the value of the CommandType attribute is:</p>
<ul>
<li>File and the value of the Direction attribute is E (Sender): This attribute identifies the file from which the Sender retrieved the transfer data (full path).</li>
<li>File and the value of the Direction attribute is R (Receiver): This attribute identifies the file in which the Receiver recorded the transfer data (full path).</li>
</ul>         </td>
         <td><p>FNAME</p>         </td>
      </tr>
      <tr>
         <td><p>LocalId</p>         </td>
         <td><p>String</p>         </td>
         <td><p>25</p>         </td>
         <td><p>If the value of the Direction attribute is:</p>
<ul>
<li>E (Sender): The value of this attribute is the local transfer identifier for the Sender.</li>
<li>R (Receiver): The value of this attribute is the local transfer identifier for the Receiver.</li>
</ul>         </td>
         <td><p>IDTU</p>         </td>
      </tr>
      <tr>
         <td><p>ProtocolFileName</p>         </td>
         <td><p>String</p>         </td>
         <td><p>512</p>         </td>
         <td><p>Network transfer identifier. The Sender sent this identifier to the Receiver.</p>         </td>
         <td><p>NIDF</p>         </td>
      </tr>
      <tr>
         <td><p>ProtocolFileLabel</p>         </td>
         <td><p>String</p>         </td>
         <td><p>80</p>         </td>
         <td><p>The Sender sent this name to the Receiver. The Receiver can use this name to locally name the transfer.</p>         </td>
         <td><p>NFNAME</p>         </td>
      </tr>
      <tr>
         <td><p>ProtocolId</p>         </td>
         <td><p>String</p>         </td>
         <td><p>80</p>         </td>
         <td><p>Network transfer identifier. The Sender generated this identifier. The Receiver acknowledged this identifier.</p>         </td>
         <td><p>NIDT</p>         </td>
      </tr>
      <tr>
         <td><p>ProtocolMessage</p>         </td>
         <td><p>String</p>         </td>
         <td><p>4000</p>         </td>
         <td><p>If the value of the CommandType attribute is:</p>
<ul>
<li>Message: the value of this attribute is the content of the transferred message.</li>
<li>File: this attribute is empty.</li>
</ul>         </td>
         <td><p>SMSG</p>         </td>
      </tr>
      <tr>
         <td><p>PositionNumber</p>         </td>
         <td><p>String</p>         </td>
         <td><p>80</p>         </td>
         <td><p>Local transfer identifier. If the value of the Direction attribute is:</p>
<ul>
<li>E (Sender): The value of this attribute identifies the transfer in the Sender's transfer catalog or DB</li>
<li>R (Receiver): The value of this attribute identifies the transfer in the Receiver's transfer catalog or DB</li>
</ul>         </td>
         <td><p>IDT</p>         </td>
      </tr>
      <tr>
         <td><p>ProtocolParameter</p>         </td>
         <td><p>String</p>         </td>
         <td><p>512</p>         </td>
         <td><p>Network transfer description. The Sender sent this description to the Receiver.</p>         </td>
         <td><p>PARM</p>         </td>
      </tr>
      <tr>
         <td><p>UserParameter1</p>         </td>
         <td><p>String</p>         </td>
         <td><p>255</p>         </td>
         <td><p>Local transfer description. This description is recorded at the transfer request time in the local DB and remains local.</p>         </td>
         <td><p>COMMENT</p>         </td>
      </tr>
      <tr>
         <td><p>Flowname</p>         </td>
         <td><p>String</p>         </td>
         <td><p>100</p>         </td>
         <td><p>Parameter to define a flow name in Central Governance for monitoring purposes.</p>         </td>
         <td><p>Flowname (v3.1.x)</p>         </td>
      </tr>
   </tbody>
</table>

## Transfer validity periods

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Sentinel</p>
<p>attribute</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Data type</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Length</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Description</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1"><p>Name in</p>
<p>product</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>EarliestDate</p>         </td>
         <td><p>Date</p>         </td>
         <td><p>-</p>         </td>
         <td><p>Date on which the validity period begins.</p>         </td>
         <td><p>DATEM</p>         </td>
      </tr>
      <tr>
         <td><p>EarliestTime</p>         </td>
         <td><p>Time</p>         </td>
         <td><p>-</p>         </td>
         <td><p>Time at which the validity period begins.</p>         </td>
         <td><p>TIMEM</p>         </td>
      </tr>
      <tr>
         <td><p>LatestDate</p>         </td>
         <td><p>Date</p>         </td>
         <td><p>-</p>         </td>
         <td><p>Date on which the validity period ends.</p>         </td>
         <td><p>DATEMAX</p>         </td>
      </tr>
      <tr>
         <td><p>LatestTime</p>         </td>
         <td><p>Time</p>         </td>
         <td><p>-</p>         </td>
         <td><p>Time at which the validity period ends.</p>         </td>
         <td><p>TIMEMAX</p>         </td>
      </tr>
   </tbody>
</table>

## Transfer dates and times

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Sentinel</p>
<p>attribute</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Data type</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Length</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Description</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1"><p>Name in</p>
<p>{{< TransferCFT/componentshortname  >}}</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>CreationDate</p>         </td>
         <td><p>Date</p>         </td>
         <td><p>-</p>         </td>
         <td><p>By default, the system date on which the Sender sent the transfer. The Sender can set this date. The Receiver can filter transfers based on this date.</p>         </td>
         <td><p>FDATE</p>         </td>
      </tr>
      <tr>
         <td><p>CreationTime</p>         </td>
         <td><p>Time</p>         </td>
         <td><p>-</p>         </td>
         <td><p>By default, the system time at which the Sender sent the transfer. The Sender can set this time. The Receiver can filter transfers based on this time.</p>         </td>
         <td><p>FTIME</p>         </td>
      </tr>
      <tr>
         <td><p>SendDate</p>         </td>
         <td><p>Date</p>         </td>
         <td><p>-</p>         </td>
         <td><p>If the value of the Direction attribute is:</p>
<ul>
<li>E (Sender): The value of this attribute is the date on which the Sender recorded the transfer in the transfer catalog.</li>
<li>R (Receiver): The value of this attribute is the date on which the Receiver recorded the transfer in the transfer catalog.</li>
</ul>
<p>The Sender and the Receiver record each transfer only once.</p>         </td>
         <td><p>DATEK</p>         </td>
      </tr>
      <tr>
         <td><p>SendTime</p>         </td>
         <td><p>Time</p>         </td>
         <td><p>-</p>         </td>
         <td><p>If the value of the Direction attribute is:</p>
<ul>
<li>E (Sender): The value of this attribute is the local time at which the Sender recorded the transfer in the transfer catalog.</li>
<li>R (Receiver): The value of this attribute is the local time at which the Receiver recorded the transfer in the transfer catalog.</li>
</ul>
<p>The Sender and the Receiver record each transfer only once.</p>         </td>
         <td><p>TIMEK</p>         </td>
      </tr>
      <tr>
         <td><p>AckDate</p>         </td>
         <td><p>Date</p>         </td>
         <td><p>-</p>         </td>
         <td><p>Date on which the Receiver acknowledged the transfer (if any).</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>AckTime</p>         </td>
         <td><p>Time</p>         </td>
         <td><p>-</p>         </td>
         <td><p>Time at which the Receiver acknowledged the transfer (if any).</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>StartDate</p>         </td>
         <td><p>Date</p>         </td>
         <td><p>-</p>         </td>
         <td><p>If the value of the State attribute is:</p>
<ul>
<li>SENT: The value of this attribute is the date on which the Sender began sending the transfer.</li>
<li>RECEIVED: The value of this attribute is the date on which the Receiver began receiving the transfer.</li>
</ul>
<p>These dates are expressed in dd.mm.yyyy format.</p>         </td>
         <td><p>DATEB</p>         </td>
      </tr>
      <tr>
         <td><p>StartTime</p>         </td>
         <td><p>Time</p>         </td>
         <td><p>-</p>         </td>
         <td><p>If the value of the State attribute is:</p>
<ul>
<li>SENT: The value of this attribute is the local time at which the Sender began sending the transfer.</li>
<li>RECEIVED: The value of this attribute is the local time at which the Receiver began receiving the transfer.</li>
</ul>
<p>These times are expressed in hh:mn:ss format.</p>         </td>
         <td><p>TIMEB</p>         </td>
      </tr>
      <tr>
         <td><p>EndDate</p>         </td>
         <td><p>Date</p>         </td>
         <td><p>-</p>         </td>
         <td><p>If the value of the State attribute is:</p>
<ul>
<li>SENT: The value of this attribute is the date on which the Sender stopped sending the transfer.</li>
<li>RECEIVED: The value of this attribute is the date on which the Receiver stopped receiving the transfer.</li>
</ul>
<p>These dates are expressed in dd.mm.yyyy format.</p>         </td>
         <td><p>DATEE</p>         </td>
      </tr>
      <tr>
         <td><p>EndTime</p>         </td>
         <td><p>Time</p>         </td>
         <td><p>-</p>         </td>
         <td><p>If the value of the State attribute is:</p>
<ul>
<li>SENT: The value of this attribute is the local time at which the Sender stopped sending the transfer.</li>
<li>RECEIVED: The value of this attribute is the local time at which the Receiver stopped receiving the transfer.</li>
</ul>
<p>These times are expressed in hh:mn:ss format.</p>         </td>
         <td><p>TIMEE</p>         </td>
      </tr>
      <tr>
         <td><p>RequestCreationDate</p>         </td>
         <td><p>Date</p>         </td>
         <td><p>-</p>         </td>
         <td><p>If the value of the State attribute is:</p>
<ul>
<li>SENT: The value of this attribute is local date of the creation of the file on the Sender side.</li>
<li>RECEIVED: The value of this attribute is the date of the creation of the file on the Sender side.</li>
</ul>         </td>
         <td><p>DATEK</p>         </td>
      </tr>
      <tr>
         <td><p>RequestCreationTime</p>         </td>
         <td><p>Time</p>         </td>
         <td><p>-</p>         </td>
         <td><p>If the value of the State attribute is:</p>
<ul>
<li>SENT: The value of this attribute is local time of the creation of the file on the Sender side.</li>
<li>RECEIVED: The value of this attribute is the time of the creation of the file on the Sender side.</li>
</ul>         </td>
         <td><p>TIMEK</p>         </td>
      </tr>
      <tr>
         <td><p>TransmissionDuration</p>         </td>
         <td><p>Integer</p>         </td>
         <td><p>-</p>         </td>
         <td><p>Transfer duration, expressed in seconds.</p>         </td>
         <td><p>TIMES</p>         </td>
      </tr>
   </tbody>
</table>

## Transfer protocols

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Sentinel</p>
<p>attribute</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Data type</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Length</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Description</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1"><p>Name in</p>
<p>{{< TransferCFT/componentshortname  >}}</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Protocol</p>         </td>
         <td><p>String</p>         </td>
         <td><p>25</p>         </td>
         <td><p>Name of the protocol that operates at the Protocol Layer of the transfer. Possible values:</p>
<ul>
<li>CFT (PeSIT, version CFT)</li>
<li>PSIT_HS_E (PeSIT, version E)</li>
<li>PSIT_HS_D (PeSIT, version D)</li>
<li>ODT (ODETTE File Transfer Protocol)</li>
</ul>         </td>
         <td><p>Protocol</p>         </td>
      </tr>
      <tr>
         <td><p>IsSSL</p>         </td>
         <td><p>String</p>         </td>
         <td><p>1</p>         </td>
         <td><ul>
<li>1: SSL/TLS used for the transfer.</li>
<li>0: SSL/TLS not used for the transfer.</li>
</ul>         </td>
         <td><p>SSLMODE</p>         </td>
      </tr>
      <tr>
         <td><p>SSLAuth</p>         </td>
         <td><p>String</p>         </td>
         <td><p>1</p>         </td>
         <td><ul>
<li>S: The Server sent X.509 certificates to the Requester.</li>
<li>B: Both the Server and the Requester sent X.509 certificates to each other.</li>
<li>N: Neither the Server nor the Requester sent X.509 certificates.</li>
</ul>         </td>
         <td><p>SSLAUTH</p>         </td>
      </tr>
      <tr>
         <td><p>SSLCypher</p>         </td>
         <td><p>String</p>         </td>
         <td><p>2</p>         </td>
         <td><p>The cipher suite that the Server and the Requester used during the SSL/TLS session.</p>         </td>
         <td><p>SSLCIPH</p>         </td>
      </tr>
   </tbody>
</table>

## Transfer options

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Sentinel</p>
<p>attribute</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Data type</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Length</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Description</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1"><p>Name in</p>
<p>{{< TransferCFT/componentshortname  >}}</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Compression</p>         </td>
         <td><p>String</p>         </td>
         <td><p>1</p>         </td>
         <td><p>One of the following:</p>
<ul>
<li>0: Undefined</li>
<li>1: Horizontal</li>
<li>2: Vertical</li>
<li>3: Both horizontal and vertical</li>
<li>4: Not compressed</li>
</ul>         </td>
         <td><p>NCOMP</p>         </td>
      </tr>
      <tr>
         <td><p>EOTProcedure</p>         </td>
         <td><p>String</p>         </td>
         <td><p>255</p>         </td>
         <td><p>Name of the end-of-transfer procedure executed upon the completion of the transfer.</p>         </td>
         <td><p>EXEC</p>         </td>
      </tr>
      <tr>
         <td><p>Priority</p>         </td>
         <td><p>Integer</p>         </td>
         <td><p>-</p>         </td>
         <td>Transfer priority. Receivers process transfers in the order of their priority. The range of possible values for this attribute is 0 to 255. The lowest priority is zero. The highest priority is 255.         </td>
         <td><p>PRI</p>         </td>
      </tr>
      <tr>
         <td><p>RetryMaxNumber</p>         </td>
         <td><p>Integer</p>         </td>
         <td><p>-</p>         </td>
         <td><p>Maximum number of times that the Sender can attempt to send transfers.</p>         </td>
         <td><p>RETRYM</p>         </td>
      </tr>
      <tr>
         <td><p>RetryNumber</p>         </td>
         <td><p>Integer</p>         </td>
         <td><p>-</p>         </td>
         <td><p>Number of times that the Sender attempted to send the transfer. Each time the Sender established a connection with the Receiver, the Sender counted one attempt.</p>         </td>
         <td><p>RETRY</p>         </td>
      </tr>
      <tr>
         <td><p>RequestType</p>         </td>
         <td><p>String</p>         </td>
         <td><p>1</p>         </td>
         <td><p>One of the following:</p>
<ul>
<li>S: The Sender sent a single transfer to a single Receiver.</li>
<li>F: The Sender sent a group of transfers to a single Receiver. For each transfer in the group, the product generated one Processing Cycle.</li>
<li>D: The Sender sent a single transfer to a group of Receivers (diffusion). For each Receiver in the group, the product generated one Processing Cycle.</li>
<li>P:  Cyclic transfer.</li>
</ul>         </td>
         <td><p>DIFTYP</p>         </td>
      </tr>
      <tr>
         <td><p>TransferType</p>         </td>
         <td><p>String</p>         </td>
         <td><p>1</p>         </td>
         <td><p>One of the following:</p>
<ul>
<li>S: The Sender sent a single transfer to a single Receiver.</li>
<li>F: The transfer belongs to a group of transfers that the Sender sent to a single Receiver. For each transfer in the group, the product generated one Processing Cycle.</li>
<li>D: The Receiver belongs to a group of Receivers to whom the Sender sent the transfer (diffusion). For each Receiver in the group, the product generated one Processing Cycle.</li>
</ul>         </td>
         <td><p>FILTYP</p>         </td>
      </tr>
   </tbody>
</table>

## Transfer size

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Sentinel</p>
<p>attribute</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Data type</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Length</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Description</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1"><p>Name in</p>
<p>{{< TransferCFT/componentshortname  >}}</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>FileSize</p>         </td>
         <td><p>Integer</p>         </td>
         <td><p>-</p>         </td>
         <td><p>Size of the transferred file. This size is expressed in bytes.</p>
<blockquote>
<p><strong>Note:</strong></p>
<p>For PeSIT, an estimation of size is given at the beginning of the transfer. This value is updated upon completion of the transfer with the real value.</p>
</blockquote>         </td>
         <td><p>FSPACE</p>         </td>
      </tr>
      <tr>
         <td><p>TransmittedBytes</p>         </td>
         <td><p>Integer</p>         </td>
         <td><p>-</p>         </td>
         <td><p>Number of bytes transferred, after decompression, to transfer the file. This size is expressed in bytes.</p>
<blockquote>
<p><strong>Note:</strong></p>
<p>For PeSIT, this value sent is crosschecked by both the sender and receiver.</p>
</blockquote>         </td>
         <td><p>NCAR</p>         </td>
      </tr>
   </tbody>
</table>

## The structure and content of transfers

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Sentinel</p>
<p>attribute</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Data type</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Length</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Description</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1"><p>Name in</p>
<p>{{< TransferCFT/componentshortname  >}}</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>CommandType</p>         </td>
         <td><p>String</p>         </td>
         <td><p>1</p>         </td>
         <td><ul>
<li>F: File transfer</li>
<li>M: Message transfer</li>
<li>A: Message reply</li>
<li>N: Message nack</li>
</ul>         </td>
         <td><p>TYPE</p>         </td>
      </tr>
      <tr>
         <td><p>FileOrganization</p>         </td>
         <td><p>String</p>         </td>
         <td><p>25</p>         </td>
         <td><ul>
<li>org_sequential: The transferred data is not indexed.</li>
<li>indexed: The transferred data is indexed.</li>
<li>direct: The transferred data is assigned relative access.</li>
</ul>         </td>
         <td><p>FORG</p>         </td>
      </tr>
      <tr>
         <td><p>FileType</p>         </td>
         <td><p>String</p>         </td>
         <td><p>60</p>         </td>
         <td><ul>
<li>B: The transferred file is a binary file.</li>
<li>J, T, O, X: The transferred file is a text file.</li>
</ul>         </td>
         <td><p>FTYPE</p>         </td>
      </tr>
      <tr>
         <td><p>RecordNumber</p>         </td>
         <td><p>Integer</p>         </td>
         <td><p> </p>         </td>
         <td><p>Number of record in the file. This size is expressed in bytes.</p>
<blockquote>
<p><strong>Note:</strong></p>
<p>For PeSIT, this value sent is crosschecked by both the sender and receiver.</p>
</blockquote>         </td>
         <td><p>FREC</p>         </td>
      </tr>
      <tr>
         <td><p>RecordFormat</p>         </td>
         <td><p>String</p>         </td>
         <td><p>64</p>         </td>
         <td><ul>
<li>F: fixed - The transferred data contains fixed-length records.</li>
<li>V: variable - The transferred data contains variable-length records.</li>
<li>U: undefined - The structure of the transferred data is unknown.</li>
</ul>         </td>
         <td><p>FRECFM</p>         </td>
      </tr>
      <tr>
         <td><p>RecordSize</p>         </td>
         <td><p>Integer</p>         </td>
         <td><p> </p>         </td>
         <td><ul>
<li>If the value of RecordFormat attribute is fixed, the value of this attribute is the size of all records in the transferred file, expressed in bytes.</li>
<li>If the value of RecordFormat is variable or undefined, the value of this attribute is the size of the largest record in the transferred file, expressed in bytes.</li>
</ul>         </td>
         <td><p>FLRECL</p>         </td>
      </tr>
      <tr>
         <td><p>Transcoding</p>         </td>
         <td><p>Integer</p>         </td>
         <td><p> </p>         </td>
         <td><p>Character code of the transferred data:</p>
<ul>
<li>A: ASCII</li>
<li>B: Binary</li>
<li>E: EBCDIC</li>
</ul>         </td>
         <td><p>FCODE</p>         </td>
      </tr>
      <tr>
         <td><p>TranslationTableId</p>         </td>
         <td><p>String</p>         </td>
         <td><p>25</p>         </td>
         <td><p>Name of the local translation table use during the transfer (if any).</p>         </td>
         <td><p>XLATE</p>         </td>
      </tr>
   </tbody>
</table>

## Other attribute

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Sentinel</p>
<p>attribute</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Data type</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Length</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Description</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1"><p>Name in</p>
<p>{{< TransferCFT/componentshortname  >}}</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>IsRelay</p>         </td>
         <td><p>String</p>         </td>
         <td><p>1</p>         </td>
         <td><p>If transfer event comes from a relay site:</p>
<ul>
<li>1: Yes</li>
<li>0: No</li>
</ul>         </td>
         <td><p>IsRelay</p>         </td>
      </tr>
      <tr>
         <td>NodeId         </td>
         <td>Integer         </td>
         <td>          </td>
         <td>Identifier of the node that executes the transfer         </td>
         <td>NodeID         </td>
      </tr>
      <tr>
         <td>ParentCycleid         </td>
         <td>String         </td>
         <td>250         </td>
         <td>The identifier of the event which is the parent of the
current event         </td>
         <td>ParentCycleid         </td>
      </tr>
   </tbody>
</table>
