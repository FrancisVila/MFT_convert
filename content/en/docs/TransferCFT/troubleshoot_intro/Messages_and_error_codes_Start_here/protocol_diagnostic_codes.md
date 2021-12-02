{
    "title": "Protocol  diagnostic codes",
    "linkTitle": "Protocol diagnostic codes",
    "weight": "490"
}<span id="PeSIT_Protocol_Diagnostic_Codes"></span>

## PeSIT protocol diagnostic codes

The PeSIT protocol uses two PIs to carry diagnostic messages: PI 2 and
PI 29.

{{< TransferCFT/componentshortname  >}} is responsible for PI 29, which is valid only in
version E. {{< TransferCFT/componentshortname  >}} uses PI 29 to carry a clearform message describing
the error. This message is not seen by the user.

## Diagnostic protocol field format

This section presents the diagnostic protocol fields format for the PeSIT
protocol. In PeSIT protocol, the DIAGP or Diag Protocol
fields can be organized in several ways:

-   "HHHHHHHH"
    format

H represents a hexadecimal digit.

In general for {{< TransferCFT/componentshortname  >}}, this format represents
an error code specific to the operating system of the host computer and
only relates to NON network resources (file access, task management, system
services, etc.).

For PeSIT, this field can also represent an error
code specific to the method of access to the network of the system concerned.
In this case, the code is associated with the following internal diagnostics:

-   301: network
    addressing error in connection phase
-   302: network
    error (cut, timeout) during the data exchange phase
-   303: network
    parameter error in connection phase
-   "eNNsNN"
    format

N represents a decimal digit. An unexpected event
has arisen in the protocol controller.

This value should be given to the Technical support
in the event of unexplained transfer difficulties.

-   "PDU
    iNN" format

N represents a decimal digit. Reception of an FPDU
not conforming to the protocol specifications. The meanings associated
with this message are explained further on in this book. For example,
DIAGP = "PDU i16" means that the header of an FPDU received
does non conform, because its size is greater than the length of the network
message received.

-   "XXX
    NNN" format

X represents an alphabetical character.

N represents a decimal digit. Reception of an FPDU
featuring an error diagnostic (PI 2) conforming to the PeSIT protocol.
XXX represents the FPDU received. NNN represents the PeSIT
reason code (the two least significant bytes sent in the PI 2 code
of FPDUs). The possible values for the PeSIT reason code are given
further on in this appendix. The possible values for XXX are given
in the following table.

-   "XXX
    iNN" format

X represents an alphabetical character.  
N represents a decimal digit.  
Reception of an FPDU having a parameter not conforming to the protocol
specifications. As for the previous format, XXX represents the
FPDU received. NN indicates an error code which is used to refine
the problem detected. The possible values for XXX are given in
the following table.  
For example, DIAGP = "CRE i12" means that a CREATE FPDU
has been received with an unknown space reservation unit (PI 41).

 "XXX
iNN" format values

```

XXX
</th>

FPDU
</th>

Definition
</th>

ABO 
ABORT  
Sudden connection interruption 
ACF 
AckCRF  
File closing confirmation 
ACO 
ACONNECT 
Connection confirmation 
ACR 
AckCREATE  
File creation confirmation 
ADS 
AckDESELECT 
File deselect confirmation 
AMG 
AckMSG 
Message confirmation 
AOF 
AckORF 
File opening confirmation 
ARD 
AckREAD 
Read confirmation 
ASE 
AckSELECT 
File selection confirmation 
ATE 
AckTRANS.END 
End of transfer confirmation 
AWR 
AckWRITE 
Write confirmation 
CON 
CONNECT 
Connection request 
CRE 
CREATE 
File creation 
CRF 
CRF 
File closing 
DMG 
MSGDM 
Message start 
DSE 
DESELECT 
File deselect 
DTE 
TRANS.END 
End of transfer 
IDT 
IDT 
Transfer interruption 
MSG 
MSG 
Message transmission 
RCO 
RCONNECT 
Connection refusal 
SEL 
SELECT 
File selection 
```

-   "Vxxxxxxx"
    format

The mnemonic Vxxxxxxx represents a protocol
event.

This value should be given to the Technical
support in the event of unexplained transfer difficulties.

Vxxxxxxx format: possible
protocol events

```

Vxxxxxxx

Definition

"VFxxxxx" 
File transfer event  (eg: VFCAND)  
"VLOGxxxx" 
Event relative to the pre-connection message  (eg:
VLOGRP) 
"VNxxxxxx" 
Network event  (eg: VNRELI) 
"VRxxxxxx" 
FPDU reception event  (eg: VRABORT) 
"VVxxxxxx" 
Internal event (eg: VVTIMO) 
"VIxxxxxx" 
Induced internal event (eg: VIABORT) 
```

Error code descriptions


| Error Code &lt;/th&gt;  | FPDU &lt;/th&gt;  | Meaning &lt;/th&gt;  |
| --- | --- | --- |
|  100  |  RESYNC  |  Transmission error (invalid CRC)  |
|  139  |   |  Invalid file attributes  |
|  200  |  AckCREATE AckSELECT  |  Insufficient file characteristics (insufficient file parameters)  |
|  201  |  AckCREATE AckSELECT  |  System resources currently insufficient  |
|  202  |  AckCREATE AckSELECT  |  User resources currently insufficient  |
|  203  |  AckCREATE AckSELECT  |  Non-priority transfer  |
|  204  |  AckCREATE  |  File already exists  |
|  205  |  AckSELECT  |  File does not exist  |
|  206  |  AckCREATE  |  Available disk space smaller than file size  |
|  207  |  AckSELECT  |  File in use  |
|  209  |  AckMSG  |  Message type not supported  |
|  210  |  AckORF  |  Negotiation failure  |
|  211  |  AckORF  |  Cannot open file  |
|  212  |  AckCRF  |  Cannot close file  |
|  213  |  IDT AckWRITE  |  Fatal file input/output error  |
|  214  |  AckREAD  |  Restart point negotiation failure  |
|  215  |  IDT  |  Error specific to the system  |
|  216  |  IDT  |  Operator-requested premature abort  |
|  217  |  IDT  |  Too many synchronization points without acknowledgment  |
|  218  |  IDT  |  Cannot re-synchronize  |
|  219  |  IDT  |  File space exceeded  |
|  220  |  IDT  |  Record length greater than that declared  |
|  221  |  IDT  |  Time-out  |
|  222  |  IDT  |  Too much data without synchronization point  |
|  223  |  AckTRANSFER.<br/>END AckDESELECT  |  Abnormal end of transfer  |
|  224  |  AckTRANSFER.END  |  Declared file size smaller than actual size  |
|  226  |  AckCREATE AckSELECT  |  Transfer denied  |
|  228  |   |  File type not supported  |
|  229  |   |  File type incompatible with transfer direction  |
|  230  |   |  File type incompatible with application  |
|  231  |   |  Transfer number not unique  |
|  232  |   |  Coding incompatible with file type  |
|  233  |   |  Restart context not available  |
|  234  |   |  Data entity size inconsistent with record  |
|  235  |   |  Record format incompatible with file type  |
|  236  |   |  Record length incompatible with file type  |
|  237  |   |  Incorrect client identifier  |
|  238  |   |  Non-authorized client  |
|  239  |   |  Non-authorized client / requester / file type combination  |
|  240  |   |  Client not authorized on this server  |
|  241  |   |  Bank not authorized on this server  |
|  242  |   |  Old password invalid  |
|  243  |   |  New password invalid  |
|  245  |   |  Incorrect file length  |
|  246  |   |  No file of this type for this client  |
|  247  |   |  No file of this type on this server  |
|  248  |   |  Identification type not supported  |
|  249  |   |  Nominative reference not supported  |
|  250  |   |  File already transferred  |
|  251  |   |  Reference type not supported  |
|  252  |   |  Start date too old  |
|  253  |   |  Incorrect date(s)  |
|  254  |   |  File service closed  |
|  299  |  All acknowledgment FPDUs  |  Other fatal errors  |
|  300  |  RelCONNECT  |  Congestion of local communication system  |
|  301  |  RelCONNECT  |  Identification of called party unknown  |
|  302  |  RelCONNECT  |  Called party not attached to a Service Access Point (SAP)  |
|  303  |  RelCONNECT  |  Maximum number of connections reached  |
|  304  |  RelCONNECT AckCREATE AckSELECT ABORT  |  Non-authorized requester identification  |
|  305  |  RelCONNECT  |  SELECT negotiation failure  |
|  306  |  RelCONNECT  |  RESYN negotiation failure  |
|  307  |  RelCONNECT  |  SYNC negotiation failure  |
|  308  |  RelCONNECT  |  Version number not supported  |
|  309  |  RelCONNECT ABORT  |  Too many connections already in progress  |
|  310  |  ABORT  |  Network incident  |
|  311  |  ABORT  |  Remote PeSIT protocol error  |
|  312  |  RelCONNECT (if partner inactive) ABORT/RELEASE  |  Shutdown of service requested by the user  |
|  313  |  ABORT/RELEASE  |  Connection closed due to inactivity  |
|  314  |  ABORT/RELEASE  |  Unused connection closed to open a new connection  |
|  315  |  ABORT  |  Negotiation failure  |
|  316  |  ABORT/RELEASE  |  Connection closed by the administrator  |
|  317  |  ABORT  |  Connection time-out  |
|  318  |  ABORT  |  Mandatory PI missing or invalid  |
|  319  |  ABORT  |  Incorrect number of records or bytes  |
|  320  |  ABORT  |  Excessive number of re-synchronizations  |
|  321  |  RelCONNECT AckCREATE AckSELECT  |  Call backup number  |
|  322  |  RelCONNECT AckCREATE AckSELECT  |  Call back later  |
|  323  |   |  Incompatible CRC / connection mode  |
|  324  |   |  Incorrect requester identifier  |
|  325  |   |  Old password invalid  |
|  326  |   |  New password invalid  |
|  327  |   |  Receive access temporarily closed  |
|  328  |   |  Receive access not supported  |
|  329  |   |  Send access temporarily closed  |
|  330  |   |  Send access not supported  |
|  331  |   |  Excessive time-out value  |
|  332  |   |  Write not negotiated  |
|  333  |   |  Read not negotiated  |
|  334  |   |  Reverse charging refused  |
|  335  |   |  Invalid calling party number  |
|  336  |   |  Server date and time refused  |
|  399  |  All ABORT acknowledgment FPDUs  |  Other fatal errors  |


### PeSIT reason code

<table>
   <thead>
      <tr>
<th >PeSIT reason code&lt;/th&gt;         </th>
<th >Description&lt;/th&gt;         </th>
<th >{{< TransferCFT/componentshortname  >}} internal
diagnostic         </th>
<th >Service item concerned&lt;/th&gt;         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Diagnostics imposing a re-synchronization </p>         </td>
      </tr>
      <tr>
         <td><p>100 </p>         </td>
         <td><p>Transmission error </p>         </td>
         <td><p>720 </p>         </td>
         <td><p>F.RESTART </p>         </td>
      </tr>
      <tr>
         <td><p>Diagnostics imposing a restart </p>         </td>
      </tr>
      <tr>
         <td><p>200 </p>         </td>
         <td><p>File characteristics insufficient </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.CREATE<br />
F.SELECT </p>         </td>
      </tr>
      <tr>
         <td><p>201 </p>         </td>
         <td><p>System resources temporarily insufficient </p>         </td>
         <td><p>916 </p>         </td>
         <td><p>F.CREATE<br />
F.SELECT </p>         </td>
      </tr>
      <tr>
         <td><p>202 </p>         </td>
         <td><p>User resources temporarily insufficient </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.CREATE<br />
F.SELECT </p>         </td>
      </tr>
      <tr>
         <td><p>203 </p>         </td>
         <td><p>Transfer not overriding </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.CREATE<br />
F.SELECT </p>         </td>
      </tr>
      <tr>
         <td><p>204 </p>         </td>
         <td><p>File already exists </p>         </td>
         <td><p>613 </p>         </td>
         <td><p>F.CREATE<br />
F.SELECT </p>         </td>
      </tr>
      <tr>
         <td><p>205 </p>         </td>
         <td><p>File does not exist </p>         </td>
         <td><p>610 </p>         </td>
         <td><p>F.CREATE<br />
F.SELECT </p>         </td>
      </tr>
      <tr>
         <td><p>206 </p>         </td>
         <td><p>Reception of the file will cause an overflow of the disk
quota </p>         </td>
         <td><p>611 </p>         </td>
         <td><p>F.CREATE<br />
F.SELECT </p>         </td>
      </tr>
      <tr>
         <td><p>207 </p>         </td>
         <td><p>File occupied </p>         </td>
         <td><p>635 </p>         </td>
         <td><p>F.CREATE<br />
F.SELECT </p>         </td>
      </tr>
      <tr>
         <td><p>208 </p>         </td>
         <td><p>File too old </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.CREATE<br />
F.SELECT </p>         </td>
      </tr>
      <tr>
         <td><p>209 </p>         </td>
         <td><p>Message of this type not accepted on the reference installation </p>         </td>
         <td><p>920 </p>         </td>
         <td><p>F.CREATE<br />
F.SELECT </p>         </td>
      </tr>
      <tr>
         <td><p>210 </p>         </td>
         <td><p>Presentation context negotiation failure </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.OPEN </p>         </td>
      </tr>
      <tr>
         <td><p>211 </p>         </td>
         <td><p>Not possible to open file </p>         </td>
         <td><p>604 </p>         </td>
         <td><p>F.OPEN </p>         </td>
      </tr>
      <tr>
         <td><p>212 </p>         </td>
         <td><p>Not possible to close file normally  </p>         </td>
         <td><p>605 </p>         </td>
         <td><p>F.CLOSE </p>         </td>
      </tr>
      <tr>
         <td><p>213 </p>         </td>
         <td><p>Inhibiting input/output error </p>         </td>
         <td><p>600 </p>         </td>
         <td><p>F.READ<br />
F.WRITE<br />
F.DATA.END<br />
F.CANCEL </p>         </td>
      </tr>
      <tr>
         <td><p>214 </p>         </td>
         <td><p>Restart point negotiation failure  </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.READ<br />
F.DATA.END<br />
F.CANCEL </p>         </td>
      </tr>
      <tr>
         <td><p>215 </p>         </td>
         <td><p>Specific system error </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.DATA.END<br />
F.CANCEL </p>         </td>
      </tr>
      <tr>
         <td><p>216 </p>         </td>
         <td><p>Intentional premature halt </p>         </td>
         <td><p>621 </p>         </td>
         <td><p>F.DATA.END<br />
F.CANCEL </p>         </td>
      </tr>
      <tr>
         <td><p>217 </p>         </td>
         <td><p>Too many synchronization points not acknowledged </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.DATA.END<br />
F.CANCEL </p>         </td>
      </tr>
      <tr>
         <td><p>218 </p>         </td>
         <td><p>Re-synchronization not possible </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.DATA.END<br />
F.CANCEL </p>         </td>
      </tr>
      <tr>
         <td><p>219 </p>         </td>
         <td><p>File space full </p>         </td>
         <td><p>614 </p>         </td>
         <td><p>F.DATA.END<br />
F.CANCEL </p>         </td>
      </tr>
      <tr>
         <td><p>220 </p>         </td>
         <td><p>Article longer than expected </p>         </td>
         <td><p>626 </p>         </td>
         <td><p>F.DATA.END<br />
F.CANCEL </p>         </td>
      </tr>
      <tr>
         <td><p>221 </p>         </td>
         <td><p>Expected end of transmission time </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.DATA.END<br />
F.CANCEL </p>         </td>
      </tr>
      <tr>
         <td><p>222 </p>         </td>
         <td><p>Too much data without synchronization points </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.DATA.END<br />
F.CANCEL </p>         </td>
      </tr>
      <tr>
         <td><p>223 </p>         </td>
         <td><p>Abnormal end of transfer </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.TRANSFER.END<br />
F.DESELECT </p>         </td>
      </tr>
      <tr>
         <td><p>224 </p>         </td>
         <td><p>The size of the file sent is greater than the one announced
in F.CREATE </p>         </td>
         <td><p>600 </p>         </td>
         <td><p>F.TRANSFER.END<br />
F.DESELECT </p>         </td>
      </tr>
      <tr>
         <td><p>225 </p>         </td>
         <td><p>Workstation application congested: the file has effectively
been received but SCRS has not been able to give it to the workstation
application  </p>         </td>
         <td><p>600 </p>         </td>
         <td><p>F.TRANSFER.END<br />
F.DESELECT </p>         </td>
      </tr>
      <tr>
         <td><p>226 </p>         </td>
         <td><p>Transfer refusal </p>         </td>
         <td><p>904 </p>         </td>
         <td><p>F.CREATE<br />
F.SELECT </p>         </td>
      </tr>
      <tr>
         <td><p>299 </p>         </td>
         <td><p>Other </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.CREATE<br />
F.SELECT<br />
F.OPEN<br />
F.CLOSE<br />
F.READ<br />
F.WRITE<br />
F.DATA.END<br />
F.CANCEL<br />
F.TRANSFER.END<br />
F.DESELECT<br />
F.RESTART </p>         </td>
      </tr>
      <tr>
         <td><p>Diagnostics imposing a reconnection </p>         </td>
      </tr>
      <tr>
         <td><p>300 </p>         </td>
         <td><p>Local communication system congested  </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.CONNECT  </p>         </td>
      </tr>
      <tr>
         <td><p>301 </p>         </td>
         <td><p>Identification requested not known </p>         </td>
         <td><p>909 </p>         </td>
         <td><p>F.CONNECT  </p>         </td>
      </tr>
      <tr>
         <td><p>302 </p>         </td>
         <td><p>Requested system not attached to a SSAP </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.CONNECT </p>         </td>
      </tr>
      <tr>
         <td><p>303 </p>         </td>
         <td><p>Remote communication system congested<br />
(too many connections) </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.CONNECT  </p>         </td>
      </tr>
      <tr>
         <td><p>304 </p>         </td>
         <td><p>Requested identification not authorized (security) </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.CONNECT<br />
F.ABORT<br />
F.CREATE<br />
F.ABORT </p>         </td>
      </tr>
      <tr>
         <td><p>305 </p>         </td>
         <td><p>Negotiation failure (SELECT) </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.CONNECT </p>         </td>
      </tr>
      <tr>
         <td><p>306 </p>         </td>
         <td><p>Negotiation failure (RESYN) </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.CONNECT </p>         </td>
      </tr>
      <tr>
         <td><p>307 </p>         </td>
         <td><p>Negotiation failure (SYNC) </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.CONNECT </p>         </td>
      </tr>
      <tr>
         <td><p>308 </p>         </td>
         <td><p>Version number not supported  </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.CONNECT </p>         </td>
      </tr>
      <tr>
         <td><p>309 </p>         </td>
         <td><p>Too many connections already in process for this processing
centre </p>         </td>
         <td><p>916 </p>         </td>
         <td><p>F.CONNECT<br />
F.ABORT </p>         </td>
      </tr>
      <tr>
         <td><p>310 </p>         </td>
         <td><p>Network incident </p>         </td>
         <td><p>802 </p>         </td>
         <td><p>F.ABORT </p>         </td>
      </tr>
      <tr>
         <td><p>311 </p>         </td>
         <td><p>Remote PeSIT protocol error </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.ABORT </p>         </td>
      </tr>
      <tr>
         <td><p>312 </p>         </td>
         <td><p>Service closure requested by the user </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.RELEASE<br />
F.ABORT </p>         </td>
      </tr>
      <tr>
         <td><p>313 </p>         </td>
         <td><p>Connection broken at the end of the TD inactivity interval </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.RELEASE<br />
F.ABORT </p>         </td>
      </tr>
      <tr>
         <td><p>314 </p>         </td>
         <td><p>Connection used to host a new connection </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.RELEASE<br />
F.ABORT </p>         </td>
      </tr>
      <tr>
         <td><p>315 </p>         </td>
         <td><p>Negotiation failure </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.ABORT </p>         </td>
      </tr>
      <tr>
         <td><p>316 </p>         </td>
         <td><p>Connection broken as a result of an administration command
 </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.RELEASE<br />
F.ABORT </p>         </td>
      </tr>
      <tr>
         <td><p>317 </p>         </td>
         <td><p>Time-out </p>         </td>
         <td><p>740 </p>         </td>
         <td><p>F.ABORT </p>         </td>
      </tr>
      <tr>
         <td><p>318 </p>         </td>
         <td><p>Mandatory PI absent or illegal PI contents </p>         </td>
         <td><p>722 </p>         </td>
         <td><p>F.ABORT </p>         </td>
      </tr>
      <tr>
         <td><p>319 </p>         </td>
         <td><p>Number of bytes or articles incorrect </p>         </td>
         <td><p>620 </p>         </td>
         <td><p>F.ABORT </p>         </td>
      </tr>
      <tr>
         <td><p>320 </p>         </td>
         <td><p>Excessive number of resynchronizations for a transfer </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.ABORT </p>         </td>
      </tr>
      <tr>
         <td><p>321 </p>         </td>
         <td><p>Call the backup number </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.CONNECT<br />
F.CREATE<br />
F.ABORT </p>         </td>
      </tr>
      <tr>
         <td><p>322 </p>         </td>
         <td><p>Call back later </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.CONNECT<br />
F.CREATE<br />
F.ABORT </p>         </td>
      </tr>
      <tr>
         <td><p>399 </p>         </td>
         <td><p>Other </p>         </td>
         <td><p>730 </p>         </td>
         <td><p>F.CONNECT<br />
F.RELEASE<br />
F.CREATE<br />
F.ABORT </p>         </td>
      </tr>
   </tbody>
</table>

<span id="ODETTE_Protocol__Diagnostic_Codes"></span>

## ODETTE Protocol Diagnostic Codes

These codes are specific to the ODETTE protocol and correspond to the
"ODETTE diagnostic code" transmitted by the protocol.

The values of these codes consist of the diagnostic code (two digits)
to which the {{< TransferCFT/componentshortname  >}} adds 100 or 200 depending on the protocol phase concerned.

-   Values between 100 and 199 correspond to the "SFNA" (Start
    File Negative Answer) and "EFNA" (End File Negative Answer)
    protocol messages.
-   Values between 200 and 299 correspond to the "ESID" (End Session
    IDentification) protocol message.
-   This code forms the "NNN NNNN"-type DIAGP protocol diagnostic
    code. Values are expressed in decimal.


| Error code  | Description  |
| --- | --- |
|  101  |  File does not exist  |
|  102  |  Target site does not exist for the file  |
|  103  |  Source site does not exist for the file  |
|  104  |  File format not supported  |
|  105  |  Record length error (length not supported)  |
|  106  |  File too big  |
|  110  |  Invalid number of records  |
|  111  |  Invalid number of characters  |
|  112  |  Fatal file input/output error (file access method problem)  |
|  113  |  File already exists  |
|  199  |  Non-referenced errors  |
|  201  |  NSDU (Network System Data Unit) not recognized (faulty header)  |
|  202  |  Protocol error (reception of a invalid NSDU)  |
|  203  |  Requestee identification not known  |
|  204  |  Requester identifier not authorized or password incorrect  |
|  205  |  Congestion of local communication system (sudden shutdown of communication system)  |
|  206  |  FPDU received with missing parameter or unexpected value  |
|  207  |  Invalid NSDU size received  |
|  208  |  User resources currently insufficient  |
|  209  |  End of time-out  |
|  210  |  Incorrect number of records. The number transported by the EFID FPDU does not correspond to the number of received records counted by the {{< TransferCFT/componentshortname  >}} (F- or V-format files)  |
|  211  |  Number of characters incorrect. The number transported by the EFID FPDU does not correspond to the number of received characters counted by the {{< TransferCFT/componentshortname  >}} (T- or U-format files)  |

