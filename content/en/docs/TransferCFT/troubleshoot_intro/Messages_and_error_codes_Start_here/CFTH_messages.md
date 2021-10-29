{
    "title": "Transfer CFT messages: CFTH",
    "linkTitle": "CFTH messages",
    "weight": "330"
}This topic lists the CFTHxx (CFT xnnx) messages and provides the type, a description, consequence, and corrective actions when applicable.

**Message format**

Earlier versions of Transfer CFT used a different message format than version 3.1.3 and higher. This document displays both formats when applicable and available, otherwise only the v23 is used. Using the CFTLOG Format = V24 setting, the log displays as shown:

CFTXXX: fixed text message &lt;variables>

**Example**

CFTLOG FORMAT=\[V23,V24\]

For V23: CFTT57I PART=&part IDF=&idf IDT=&idt &str transfer started

For V24: `CFTT57I &str transfer started   <IDTU=&idtu PART=&part IDF=&idf IDT=&idt>`

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTH01E"></span>CFTH01E PART=&amp;part Context area allocation failure
CS=&amp;scs</p>
            <p>CFTH01E Context area allocation failure &lt;PART=&amp;part CS=&amp;cs&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>Cannot allocate the working area necessary for the transfer.</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>In REQUESTER mode, the transfer is refused with a <span>Transfer CFT</span>
122 diagnostic code and a MALLOC protocol diagnostic message.</p>
            <p>In SERVER
mode, the incoming call is rejected. In this case, as the partner's name
is not known, the value UNKNOWN
is displayed.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTH02E"></span>CFTH02E PART=&amp;part TFIL Exchange buffer allocation
failure CS=&amp;scs</p>
            <p>CFTH02E TFIL Exchange buffer allocation failure &lt;PART=&amp;part CS=&amp;cs&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>Cannot allocate the working area required to exchange information
between the PROTOCOL task and the FILE task.</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>In REQUESTER mode, the transfer is refused with a <span>Transfer CFT</span>
122 code and a MALLOC protocol diagnostic message.</p>
            <p>In SERVER mode, the incoming call is rejected. In this
case, as the partner's name is not known, the value UNKNOWN
is displayed.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTH03E"></span>CFTH03E PART=&amp;part
Error sending data on network NCR=&amp;ncr NCS=&amp;ncs NET=&amp;net</p>
            <p>CFTH03E Error sending data on network &lt;PART=&amp;part NCR=&amp;ncr NCS=&amp;cs NET=&amp;net&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>Cannot send a message on the network.</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>The transfer is interrupted with a <span>Transfer CFT</span> 302 code
and a protocol diagnostic message indicating the specific error code of
the error that occurred during the send request. This code is expressed
in hexadecimal.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTH04E"></span>CFTH04E PART=&amp;part
Mismatch between header and FPDU size</p>
            <p>CFTH04E Mismatch between header and FPDU size &lt;PART=&amp;part&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>The transfer is aborted. A 318 protocol code, transported
by an ABORT FPDU, is reported to the remote partner.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTH05E"></span>CFTH05E: PART=&amp;part ,&amp;message</p>
            <p>CFTH05E &lt;PART=&amp;part &amp;message&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>Inconsistent FPDU received.</p>
            <p>The end of the message is then set to one of the following
values:</p>
            <ul>
               <li>Unknown FPDU
type=n:               </li>
            </ul>
            <p>Reception of an FPDU, for which the type byte in the
header is unknown</p>
            <ul>
               <li>Missing PI number
n into FPDU fpdu:               </li>
            </ul>
            <p>Reception of an FPDU with missing mandatory PI</p>
            <ul>
               <li>PGI n in PGI
into FPDU fpdu:               </li>
            </ul>
            <p>Reception of an FPDU embedding a PGI in a PGI</p>
            <ul>
               <li>Invalid length
n for PI n into FPDU fpdu:               </li>
            </ul>
            <p>Reception of an FPDU with a PI of invalid length</p>
            <ul>
               <li>Unknown PI number
n into FPDU fpdu:               </li>
            </ul>
            <p>Reception of an FDPU with an unwanted PI</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>The transfer is aborted. A 318 protocol code, transported by
an ABORT FPDU, is reported to the remote partner.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTH06E"></span>CFTH06E PART=&amp;part Error &amp;cr while formatting
FPDU</p>
            <p>CFTH06E Error &amp;cr while formatting FPDU &lt;PART=&amp;part &gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>Problem encountered while formatting an FPDU.</p>
            <ul>
               <li>-1  PGI
embedded in a PGI               </li>
               <li>-2  Output
buffer overflow               </li>
               <li>-3  End
of PGI without PGI               </li>
               <li>-4  External/internal
type error               </li>
               <li>-5  End
of FPDU with PGI not closed               </li>
               <li>-8  Invalid
PI length               </li>
               <li>-11  FPDU
description pointer null               </li>
            </ul>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>The transfer is aborted. A 220 protocol code, transported by
an ABORT FPDU, is reported to the remote partner.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTH07E"></span>CFTH07E PART=&amp;part TFIL task Synchronization error
CR=&amp;cr CS=&amp;scs</p>
            <p>CFTH07E TFIL task Synchronization error &lt;PART=&amp;part CR= &amp;cr CS=&amp;cs&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>Problem encountered when sending a <span>Transfer CFT</span> internal
message to the FILE task.</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>The transfer
is aborted by the protocol task (network disconnection). However, as the
FILE task is not protected by a time-out, the request remains in the C status in the catalog.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTH08E"></span>CFTH08E PART=&amp;part Network release response error
NCR=&amp;ncr NCS=&amp;ncs</p>
            <p>CFTH08E Network release response error &lt;PART=&amp;part NCR=&amp;ncr NCS=&amp;cs&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>Cannot respond to a network connection failure indication.</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>This incident has no impact on the previous transfer (whether
terminated or interrupted).</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTH09E"></span>CFTH09E PART=&amp;part Network connect request local
error NCR=&amp;ncr NCS=&amp;ncs</p>
            <p>CFTH09E Network connect request local error &lt;PART=&amp;part NCR=&amp;ncr NCS=&amp;cs NET=&amp;net&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>Cannot make an outgoing connection request on the network.
For a general -6 code (maximum number of connections reached on the resource),
the transfer is refused with a <span>Transfer CFT</span> 416 diagnostic code and a
MAXCNX protocol diagnostic message.</p>
            <p>The transfer will be retried (minimum time-out equal to
the WSCAN parameter of the CFTCAT command), without incrementing the retry
counter.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTH10E"></span>CFTH10E PART=&amp;part Network connect reject RECOV=&amp;recov
L= &amp;local R=&amp;reason D=&amp;ncs</p>
            <p>CFTH10E Network connect reject &lt;PART=&amp;part RECOV=&amp;recov L=&amp;local R=&amp;reason D=&amp;ncs NET=&amp;net&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>The physical connection has been refused.</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>Depending
on the origin of the refusal and the RECOV code, the transfer is set to
the K state (diagnostics code
303) or remains set to the D state
(diagnostics code 302) and will be retried.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTH11E"></span>CFTH11E PART=&amp;part Error Opening session EV=&amp;pevent
ST=&amp;pstate</p>
            <p>CFTH11E Error Opening session &lt;PART=&amp;part EV=&amp;pevent ST=&amp;pstate&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>Problem opening a PeSIT session with a remote partner after
establishing the network session.</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>The transfer
is aborted with a <span>Transfer CFT</span> 451 diagnostic code.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTH12E"></span>CFTH12E PART=&amp;part Logon reject logon</p>
            <p>CFTH12E Logon reject &lt;PART=&amp;part &amp;str&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>The PESIT pre-connection phase, logon, is refused by the
SERVER partner (the correct response is ACK0 in EBCDIC). The string received
is included in the message.</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>The transfer
is aborted with one of the following possible diagnostic codes:</p>
            <ul>
               <li>903: invalid
password               </li>
               <li>970: password
expired, or               </li>
               <li>963: unknown acknowledgment of a pre-connection request               </li>
            </ul>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTH13E"></span>CFTH13E PART=&amp;part FPDU Remote reject DIAGI=&amp;diagi
DIAGP=&amp;diagp</p>
            <p>CFTH13E FPDU Remote reject &lt;PART=&amp;part DIAGI=&amp;diagi DIAGP=&amp;diagp&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>FPDU including a diagnostic code has been received. The
DIAGP field is of the XXX NNN type.</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>The transfer is aborted.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTH14E"></span>CFTH14E PART=&amp;part Invalid AckCONNECT FPDU &amp;str</p>
            <p>CFTH14E Invalid AckCONNECT FPDU &lt;PART=&amp;part &amp;str&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>The AckCONNECT FPDU sent by the SERVER partner is invalid.</p>
            <p>The field "&amp;str" is an explicit character
string:</p>
            <ul>
               <li>Version
= n: The protocol version negotiated by the SERVER partner
is invalid Window without Pacing:
A synchronization window is specified even though the interval is null,               </li>
            </ul>
            <ul>
               <li>Window = n too large: The synchronization
window negotiated by the SERVER partner is too large The SIT profile does
not allow a value greater than 16               </li>
            </ul>
            <ul>
               <li>Pacing = n not authorized: The synchronization
interval negotiated by the SERVER partner does not comply with the specifications
of the SIT profile The values 1, 2 and 3 are not allowed               </li>
            </ul>
            <ul>
               <li>Pacing = n greater than initial value = n: The synchronization
interval negotiated by the SERVER partner is larger than that proposed               </li>
            </ul>
            <ul>
               <li>Window = n greater than initial value = n:
The synchronization
window negotiated by the SERVER partner is larger than that proposed               </li>
            </ul>
            <ul>
               <li>Resynchronization = n: The value
of the resynchronization option negotiated by the SERVER partner does
not comply with the specifications of the protocol               </li>
            </ul>
            <ul>
               <li>Mismatch between header and FPDU size: The FPDU
length indicated in the header is not equal to the length of the FPDU
received               </li>
            </ul>
            <ul>
               <li>Unknown FPDU: The number
identifying the received FPDU is not referenced               </li>
            </ul>
            <ul>
               <li>Missing PI number n into FPDU: The PI is
mandatory for this type of FPDU               </li>
            </ul>
            <ul>
               <li>Unknown PI number n into FPDU: The PI is
unknown for this type of FPDU               </li>
            </ul>
            <ul>
               <li>PGI n in PGI into FPDU: The presence
of a PGI embedded in another PGI is invalid               </li>
            </ul>
            <ul>
               <li>Invalid length n for PI n into FPDU: The length of the
PI is invalid (less than minimum length or greater than maximum length)               </li>
            </ul>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>The transfer is aborted with DIAGI=220, DIAGP=ACO + PeSIT code.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTH15E"></span>CFTH15E PART=&amp;part Invalid AckCREATE FPDU &amp;str</p>
            <p>CFTH15E Invalid AckCREATE FPDU &lt;PART=&amp;part &amp;str&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>The AckCREATE FPDU sent by the SERVER partner does not
conform.</p>
            <p>The "&amp;str" string is an explicit character
string:</p>
            <ul>
               <li>NSDU
size = n greater than initial value = n: The maximum NSDU size negotiated by the partner
is greater than that proposed               </li>
            </ul>
            <ul>
               <li>NSDU
size = n too lower for LRECL = n: In the SIT profile, as segmentation is not authorized,
a record must fit in an FPDU. The negotiated NSDU size (RUSIZE) must therefore
be greater than the record length of the file (plus 6 for the FPDU header)               </li>
            </ul>
            <ul>
               <li>Mismatch
between header and FPDU size: The FPDU length indicated in the header is not
equal to the length of the FPDU received               </li>
            </ul>
            <ul>
               <li>Unknown
FPDU: The number identifying the received FPDU is not
referenced               </li>
            </ul>
            <ul>
               <li>Missing
PI number n into FPDU: The PI is mandatory for this type of FPDU               </li>
            </ul>
            <ul>
               <li>Unknown
PI number n into FPDU: The PI is unknown for this type of FPDU               </li>
            </ul>
            <ul>
               <li>PGI n
in PGI into FPDU: The presence of a PGI embedded in another PGI is
invalid               </li>
            </ul>
            <ul>
               <li>Invalid
length n for PI n into FPDU: The length of the PI is invalid (less than minimum
length or greater than maximum length)               </li>
            </ul>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>Transfer aborted with DIAGI=220, DIAGP=ACR + PeSIT code.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTH16E"></span>CFTH16E PART=&amp;part Invalid AckWRITE FPDU &amp;str</p>
            <p>CFTH16E Invalid AckWRITE FPDU &lt;PART=&amp;part &amp;str&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>The AckWRITE FPDU sent by the SERVER partner does not conform.</p>
            <p>The field "&amp;str" is an explicit character
string:</p>
            <ul>
               <li>Restart
point without restart option: The remote partner proposes a restart point for
the transfer, even though it is a new transfer               </li>
            </ul>
            <ul>
               <li>Mismatch
between header and FPDU size: The FPDU length indicated in the header is not
equal to the length of the FPDU received               </li>
            </ul>
            <ul>
               <li>Unknown
FPDU: The number identifying the received FPDU is not
referenced               </li>
            </ul>
            <ul>
               <li>Missing
PI number n into FPDU: The PI is mandatory for this type of FPDU               </li>
            </ul>
            <ul>
               <li>Unknown
PI number n into FPDU: The PI is unknown for this type of FPDU               </li>
            </ul>
            <ul>
               <li>PGI n
in PGI into FPDU: The presence of a PGI embedded in another PGI is
invalid               </li>
            </ul>
            <ul>
               <li>Invalid
length n for PI n into FPDU: The length of the PI is invalid (less than minimum
length or greater than maximum length)               </li>
            </ul>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>Transfer aborted with DIAGI=220, DIAGP=AWR + PeSIT code.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTH17E"></span>CFTH17E PART=&amp;part Invalid Check Point acknowledge
&amp;n</p>
            <p>CFTH17E Invalid Check Point acknowledge &lt;PART=&amp;part &amp;n&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>The synchronization check point number is not correct.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTH18E"></span>CFTH18E Incoming call reject error NCR=&amp;ncr NCS=&amp;ncs
NET=&amp;net</p>
            <p>CFTH18E Incoming call reject error &lt;NCR=&amp;ncr NCS=&amp;cs NET=&amp;net&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>Cannot refuse an incoming call.</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>The transfer is aborted by the protocol task (it is not registered
in the catalog)</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTH19E"></span>CFTH19E Incoming call accept error NCR=&amp;ncr NCS=&amp;ncs
NET=&amp;net</p>
            <p>CFTH19E Incoming call accept error &lt;NCR=&amp;ncr NCS=&amp;cs NET=&amp;net&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>Cannot accept an incoming call.</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>The transfer is aborted by the protocol task (it is not
registered in the catalog).</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTH20E"></span>CFTH20E Invalid CONNECT FPDU &amp;str</p>
            <p>CFTH20E Invalid CONNECT FPDU &lt;&amp;str&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>The CONNECT FPDU sent by the REQUESTER partner does not
conform.</p>
            <p>The field "&amp;str" is an explicit character
string:</p>
            <ul>
               <li>CRC option
= n: The remote partner proposes a value for the CRC
option which does not comply with protocol specifications.               </li>
            </ul>
            <ul>
               <li>This
value is displayed: Only the values 0 (no CRC) and 1 (application of
a CRC) are correct               </li>
            </ul>
            <ul>
               <li>Version
= n: The protocol version proposed by the remote partner
does not comply with the specifications of the PeSIT protocol.Only the values 1 (version D) and 2 (version E)
are allowed. The incorrect value is displayed in the message               </li>
            </ul>
            <ul>
               <li>Window
without Pacing: A synchronization window is specified even though
the interval is null               </li>
            </ul>
            <ul>
               <li>Window
= n too large: The synchronization window negotiated by the REQUESTER
partner is too large. The SIT profile does not allow a value greater than
16               </li>
            </ul>
            <ul>
               <li>Access
= n: The correct access types are 0 for write mode,
1 for read mode and 2 for read/write mode. The other values represent
a violation of the protocol. The incorrect value received is displayed
in the message.               </li>
            </ul>
            <ul>
               <li>Resynchronization
= n: The functional resynchronization unit is negotiated
by the value 0 (no) or 1 (yes). Any other value is not allowed               </li>
            </ul>
            <ul>
               <li>Pacing
= n not authorized: The synchronization interval negotiated by the
SERVER partner does not comply with the specifications of the SIT profile.
The values 1, 2 and 3 are not allowed               </li>
            </ul>
            <ul>
               <li>Application
type relation R=sapp S=rapp: The SIT profile imposes a correlation between the
sender and receiver applications. This correlation is not respected. The
message displays the first byte of PI 3 and 4 of the CONNECT FPDU in numeric
form               </li>
            </ul>
            <ul>
               <li>Mismatch
between header and FPDU size: The FPDU length indicated in the header is not
equal to the length of the FPDU received               </li>
            </ul>
            <ul>
               <li>Unknown
FPDU: The number identifying the received FPDU is not
referenced               </li>
            </ul>
            <ul>
               <li>Missing
PI number n into FPDU: The PI is mandatory for this type of FPDU               </li>
            </ul>
            <ul>
               <li>Unknown
PI number n into FPDU: The PI is unknown for this type of FPDU               </li>
            </ul>
            <ul>
               <li>PGI n
in PGI into FPDU: The presence of a PGI embedded in another PGI is
invalid               </li>
            </ul>
            <ul>
               <li>Invalid
length n for PI n into FPDU: The length of the PI is invalid (less than minimum
length or greater than maximum length)               </li>
            </ul>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>The transfer is aborted without trace in the catalog.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTH21E"></span>CFTH21E PART=&amp;part MAIN task Synchronization error
CR=&amp;cr CS=&amp;scs</p>
            <p>CFTH21E MAIN task Synchronization error &lt;PART=&amp;part CR= &amp;cr CS=&amp;cs&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p><span>Transfer CFT</span> internal synchronization error.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTH22E"></span>CFTH22E PART=&amp;part rejected DIAGI=&amp;diagi &lt;HOST=&amp;addr&gt;</p>
            <p>CFTH22E NPART=&amp;part rejected DIAGI=&amp;diagi &lt;HOST=&amp;pstate&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>Where:</p>
            <ul>
               <li>addr: The caller's IP address               </li>
            </ul>
            <p><span>Transfer CFT</span> refuses to open a protocol session following
a request to do so from a partner.</p>
            <p>The message displays the <span>Transfer CFT</span>
diagnostic code.</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>The transfer is aborted. No trace of this attempt appears in
the catalog.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTH23E"></span>CFTH23E NPART=&amp;part rejected EVENT=&amp;pevent</p>
            <p>CFTH23E PART=&amp;part rejected EVENT=&amp;pevent</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p><span>Transfer CFT</span> refuses to open a protocol session for internal
reasons, following a request to do so from a partner. The event which
caused this rejection is displayed in the message.</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>The transfer is aborted. No trace of this attempt appears in
the catalog.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTH24E"></span>CFTH24E PART=&amp;part Invalid CREATE FPDU &amp;str</p>
            <p>CFTH24E Invalid CREATE FPDU &lt;PART=&amp;part &amp;str&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>The CREATE FPDU sent by the REQUESTER partner does not
conform. The field "&amp;str" is an explicit character string:</p>
            <ul>
               <li>IDT is null:
Reception of a CREATE FPDU with a null Transfer
Identifier (PI 13)               </li>
            </ul>
            <ul>
               <li>Restart = n:
Invalid value for the restart option of a transfer               </li>
            </ul>
            <ul>
               <li>Data Code = n:
Unknown code for the data to be transported               </li>
            </ul>
            <ul>
               <li>Priority = n:
Invalid priority assigned to the transfer               </li>
            </ul>
            <ul>
               <li>Record Format
= n: Unknown record format               </li>
            </ul>
            <ul>
               <li>Record size =
n greater than Pacing: The record size is greater than the synchronization
interval               </li>
            </ul>
            <ul>
               <li>NSDU size = n
too lower for LRECL = n: In the SIT profile, as segmentation is not authorized,
a record must fit in the FPDU. The negotiated NSDU size (RUSIZE) must
therefore be greater than the record length of the file (plus 6 for the
FPDU header).               </li>
            </ul>
            <ul>
               <li>File Organization
= n: Unknown file organization               </li>
            </ul>
            <ul>
               <li>Key length without
indexed organization: A key length is specified for a file that is not
indexed               </li>
            </ul>
            <ul>
               <li>Key Position
without indexed organization: A key position is specified for a file that is
not indexed               </li>
            </ul>
            <ul>
               <li>Space Unit in
record without fixed format: A file must be in fixed format for its size to
be expressed as a number of records               </li>
            </ul>
            <ul>
               <li>Space Unit =
n: Space reservation unit unknown               </li>
            </ul>
            <ul>
               <li>Mismatch between
header and FPDU size: The FPDU length indicated in the header is not
equal to the length of the FPDU received               </li>
            </ul>
            <ul>
               <li>Unknown FPDU:
The number identifying the received FPDU is not
referenced               </li>
            </ul>
            <ul>
               <li>Missing PI number
n into FPDU: The PI is mandatory for this type of FPDU               </li>
            </ul>
            <ul>
               <li>Unknown PI number
n into FPDU: The PI is unknown for this type of FPDU               </li>
            </ul>
            <ul>
               <li>PGI n in PGI
into FPDU: The presence of a PGI embedded in another PGI is
invalid               </li>
            </ul>
            <ul>
               <li>Invalid length
n for PI n into FPDU: The length of the PI is invalid (less than minimum
length or greater than maximum length)               </li>
            </ul>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>Transfer aborted with DIAGI=220, DIAGP=CRE + PeSIT code.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Information</p>         </td>
         <td width="80%">            <p><span id="CFTH25I"></span>CFTH25I PART=&amp;part Concatenation area allocation
failure CS=&amp;scs</p>
            <p>CFTH25I Concatenation area allocation failure &lt;PART=&amp;part CS=&amp;cs&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>Cannot allocate a working area to execute the concatenation
option.</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>The transfer continues but the concatenation option remains
inhibited for the rest of the session.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td>            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTH26E"></span>CFTH26E PART=&amp;part
Too many data without synchronization</p>
            <p>CFTH26E Too many data without synchronization &lt;PART=&amp;part&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td>            <p>Explanation</p>         </td>
         <td width="80%">            <p>Detection of a synchronization error.</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td>            <p>Consequence</p>         </td>
         <td width="80%">            <p>The transfer is aborted.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTH27E"></span>CFTH27E PART=&amp;part SYNC FPDU without synchronization</p>
            <p>CFTH27E SYNC FPDU without synchronization &lt;PART=&amp;part&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>A synchronization FPDU was received unexpectedly as the
Functional Synchronization Unit was not negotiated at the beginning of
the session.</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>The transfer
is aborted with a <span>Transfer CFT</span> 730 diagnostic code, a protocol violation.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTH28E"></span>CFTH28E PART=&amp;part Invalid Checkpoint n</p>
            <p>CFTH28E Invalid Chekpoint &lt;PART=&amp;part &amp;n&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>Reception of an invalid synchronization point, which does
not follow the sequence.</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>The transfer is aborted.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTH29E"></span>CFTH29E PART=&amp;part Invalid FPDU RC=&amp;n</p>
            <p>CFTH29E Invalid FPDU RC=&amp;rc Incoming call address= &amp;str &lt;PART=&amp;part&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>An inconsistent FPDU has been received. The RC code enables
the error found to be defined more specifically: this code is identical
to the one included in the PDU_iNN protocol diagnostic message.</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>The transfer is aborted.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTH30E"></span>CFTH30E PART=&amp;part Invalid AckORF FPDU &amp;str</p>
            <p>CFTH30E Invalid AckORF FPDU &lt;PART=&amp;part &amp;str&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>The AckORF FPDU sent by the SERVER partner does not conform.</p>
            <p>The field "&amp;str" is an explicit character
string:</p>
            <ul>
               <li>Compression
Indicator = n: The compression indicator has a value which does
not comply with the specifications of the PeSIT protocol (0 no compression,
1 compression)               </li>
            </ul>
            <ul>
               <li>Compression
Value without Indicator: A compression value is negotiated even though the
indicator inhibits the compression option               </li>
            </ul>
            <ul>
               <li>Compression
Indicator without Value: The compression indicator is set even though the
negotiated value is null               </li>
            </ul>
            <ul>
               <li>Compression
Value = n: The negotiated compression value does not comply
with to the specifications of the PeSIT protocol               </li>
            </ul>
            <ul>
               <li>Compression
Negotiation: n for n: The negotiated compression is greater than the
proposed compression               </li>
            </ul>
            <ul>
               <li>Extended
LRECL greater than PACING: n for n:Compression may cause a record to be extended.
This risk, which is measurable (1 byte for 32 bytes), means that the record
size becomes greater than the synchronization interval               </li>
            </ul>
            <ul>
               <li>Mismatch
between header and FPDU size: The FPDU length indicated in the header is not
equal to the length of the FPDU received               </li>
            </ul>
            <ul>
               <li>Unknown
FPDU: The number identifying the received FPDU is not
referenced               </li>
            </ul>
            <ul>
               <li>Missing
PI number n into FPDU: The PI is mandatory for this type of FPDU               </li>
            </ul>
            <ul>
               <li>Unknown
PI number n into FPDU: The PI is unknown for this type of FPDU               </li>
            </ul>
            <ul>
               <li>PGI n
in PGI into FPDU: The presence of a PGI embedded in another PGI is
invalid               </li>
            </ul>
            <ul>
               <li>Invalid
length n for PI n into FPDU: The length of the PI is invalid (less than minimum
length or greater than maximum length)               </li>
            </ul>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>Transfer aborted with DIAGI=220, DIAGP=AOF + PeSIT code.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTH31E"></span>CFTH31E PART=&amp;part Invalid AckTRANS.END FPDU &amp;str</p>
            <p>CFTH31E Invalid AckTRANS.END FPDU &lt;PART=&amp;part &amp;str&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>The AckTRANSFER.END FPDU sent by the SERVER partner does
not conform.</p>
            <p>The field "&amp;str" is an explicit character
string:</p>
            <ul>
               <li>Byte count mismatch
n for n: The number of bytes transferred does not correspond
to the <span>Transfer CFT</span>-maintained counter               </li>
            </ul>
            <ul>
               <li>Record count
mismatch n for n: The number of records transferred does not correspond
to the <span>Transfer CFT</span>-maintained counter               </li>
            </ul>
            <ul>
               <li>Mismatch between
header and FPDU size: The FPDU length indicated in the header is not equal
to the length of the FPDU received               </li>
            </ul>
            <ul>
               <li>Unknown FPDU:
The number identifying the received FPDU is not referenced               </li>
            </ul>
            <ul>
               <li>Missing PI number
n into FPDU: The PI is mandatory for this type of FPDU               </li>
            </ul>
            <ul>
               <li>Unknown PI number
n into FPDU: The PI is unknown for this type of FPDU               </li>
            </ul>
            <ul>
               <li>PGI n in PGI
into FPDU: The presence of a PGI embedded in another PGI is invalid               </li>
            </ul>
            <ul>
               <li>Invalid length
n for PI n into FPDU: The length of the PI is invalid (less than minimum
length or greater than maximum length)               </li>
            </ul>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>Transfer aborted with DIAGI=220, DIAGP=ATE + PeSIT code.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTH32E"></span>CFTH32E PART=&amp;part Invalid AckMESSAGE FPDU &amp;str</p>
            <p>CFTH32E Invalid AckMESSAGE FPDU &lt;PART=&amp;part &amp;str&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>This message is only displayed in security-enabled mode
and corresponds to a security problem.</p>
            <p>The field "&amp;str" is an explicit character
string:</p>
            <ul>
               <li>Mismatch between
header and FPDU size: The FPDU length indicated in the header is not
equal to the length of the FPDU received               </li>
            </ul>
            <ul>
               <li>Unknown FPDU:
The number identifying the received FPDU is not
referenced               </li>
            </ul>
            <ul>
               <li>Missing PI number
n into FPDU: The PI is mandatory for this type of FPDU               </li>
            </ul>
            <ul>
               <li>Unknown PI number
n into FPDU: The
PI is unknown for this type of FPDU               </li>
            </ul>
            <ul>
               <li>PGI n in PGI
into FPDU: The presence of a PGI embedded in another PGI is
invalid               </li>
            </ul>
            <ul>
               <li>Invalid length
n for PI n into FPDU: The length of the PI is invalid (less than minimum
length or greater than maximum length)               </li>
            </ul>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>Transfer aborted with DIAGI=220, DIAGP=AMG + PeSIT code.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTH33E"></span>CFTH33E PART=&amp;part Invalid AckSELECT FPDU &amp;str</p>
            <p>CFTH33E Invalid AckSELECT FPDU &lt;PART=&amp;part &amp;str&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>The AckSELECT FPDU sent by the SERVER partner does not
conform.</p>
            <p>The field "&amp;str" is an explicit character
string:</p>
            <ul>
               <li>File type value
not authorized: Reception of an AckSELECT FPDU with an invalid
file type (PI 11) The values between 0xFFFC and 0xFFFF are invalid               </li>
            </ul>
            <ul>
               <li>IDT is null:
Reception of an AckSELECT FPDU with a null Transfer
Identifier (PI 13)               </li>
            </ul>
            <ul>
               <li>Data Code = n:
Unknown code for the data to be transported               </li>
            </ul>
            <ul>
               <li>Priority = n:
Invalid priority assigned to the transfer               </li>
            </ul>
            <ul>
               <li>Record Format
= n: Unknown record format               </li>
            </ul>
            <ul>
               <li>Record size =
n greater than Pacing: The record size is greater then the synchronization
interval               </li>
            </ul>
            <ul>
               <li>NSDU size negotiation
n for n: The negotiated NSDU size is greater than that proposed               </li>
            </ul>
            <ul>
               <li>NSDU too small
n: The negotiated NSDU size is smaller than the minimum
authorized value (128)               </li>
            </ul>
            <ul>
               <li>File Organization
= n: Unknown file organization               </li>
            </ul>
            <ul>
               <li>Key length without
indexed organization: A key length is specified for a file that is not indexed               </li>
            </ul>
            <ul>
               <li>Key Position
without indexed organization: A key position is specified for a file that is not
indexed               </li>
            </ul>
            <ul>
               <li>Space Unit in
record without fixed format: A file must be in fixed format for its size to be
expressed as a number of records               </li>
            </ul>
            <ul>
               <li>Space Unit =
n: Space reservation unit unknown               </li>
            </ul>
            <ul>
               <li>Mismatch between
header and FPDU size: The FPDU length indicated in the header is not equal
to the length of the FPDU received               </li>
            </ul>
            <ul>
               <li>Unknown FPDU:
The number identifying the received FPDU is not referenced               </li>
            </ul>
            <ul>
               <li>Missing PI number
n into FPDU: The PI is mandatory for this type of FPDU               </li>
            </ul>
            <ul>
               <li>Unknown PI number
n into FPDU: The PI is unknown for this type of FPDU               </li>
            </ul>
            <ul>
               <li>PGI n in PGI
into FPDU: The presence of a PGI embedded in another PGI is invalid               </li>
            </ul>
            <ul>
               <li>Invalid length
n for PI n into FPDU: The length of the PI is invalid (less than minimum
length or greater than maximum length)               </li>
            </ul>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>Transfer aborted with DIAGI=220, DIAGP=ASE + PeSIT code.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTH34E"></span>CFTH34E PART=&amp;part Invalid ORF FPDU &amp;str</p>
            <p>CFTH34E Invalid ORF FPDU &lt;PART=&amp;part &amp;str&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>The ORF FPDU sent by the REQUESTER partner does not conform.</p>
            <p>The field "&amp;str" is an explicit character
string:</p>
            <ul>
               <li>Compression
Indicator = n: The compression indicator has a value that does not
comply with the specifications of the PeSIT protocol (0 no compression,
1 compression)               </li>
            </ul>
            <ul>
               <li>Compression
Value without Indicator: A compression value is negotiated even though the
indicator inhibits the compression option               </li>
            </ul>
            <ul>
               <li>Compression
Indicator without Value: The compression indicator is set even though the negotiated
value is null               </li>
            </ul>
            <ul>
               <li>Compression Value
= n: The negotiated compression value does not comply with
the specifications of the PeSIT protocol               </li>
            </ul>
            <ul>
               <li>Extended Record
size greater than pacing: n for n: Compression may cause a record to be extended. This
risk, which is measurable (1 byte for 32 bytes), means that the record
size becomes greater than the synchronization interval               </li>
            </ul>
            <ul>
               <li>Mismatch
between header and FPDU size: The FPDU length indicated in the header is not equal
to the length of the FPDU received               </li>
            </ul>
            <ul>
               <li>Unknown
FPDU: The number identifying the received FPDU is not referenced               </li>
            </ul>
            <ul>
               <li>Missing
PI number n into FPDU:The PI is mandatory for this type of FPDU               </li>
            </ul>
            <ul>
               <li>Unknown PI number
n into FPDU: The PI is unknown for this type of FPDU               </li>
            </ul>
            <ul>
               <li>PGI n
in PGI into FPDU: The presence of a PGI embedded in another PGI is invalid               </li>
            </ul>
            <ul>
               <li>Invalid
length n for PI n into FPDU: The length of the PI is invalid (less than minimum
length or greater than maximum length)               </li>
            </ul>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>Transfer aborted with DIAGI=220, DIAGP=ORF + PeSIT code.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTH35E"></span>CFTH35E PART=&amp;part Invalid TRANS.END FPDU &amp;str</p>
            <p>CFTH35E Invalid TRANS.END FPDU &lt;PART=&amp;part &amp;str&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>This message is only displayed in security-enabled mode
and corresponds to a security problem.</p>
            <p>The field "&amp;str" is an explicit character
string:</p>
            <ul>
               <li>Mismatch between
header and FPDU size: The FPDU length indicated in the header is not equal
to the length of the FPDU received               </li>
            </ul>
            <ul>
               <li>Unknown
FPDU: The number identifying the received FPDU is not referenced               </li>
            </ul>
            <ul>
               <li>Missing
PI number n into FPDU: The PI is mandatory for this type of FPDU               </li>
            </ul>
            <ul>
               <li>Unknown
PI number n into FPDU: The PI is unknown for this type of FPDU               </li>
            </ul>
            <ul>
               <li>PGI n
in PGI into FPDU: The presence of a PGI embedded in another PGI is invalid               </li>
            </ul>
            <ul>
               <li>Invalid
length n for PI n into FPDU: The length of the PI is invalid (less than minimum
length or greater than maximum length)               </li>
            </ul>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>Transfer aborted with DIAGI=220, DIAGP=TFE + PeSIT code.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTH36E"></span>CFTH36E PART=&amp;part Invalid MESSAGE FPDU &amp;str</p>
            <p>CFTH36E Invalid MESSAGE FPDU &lt;PART=&amp;part &amp;str&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>The MESSAGE FPDU sent by the REQUESTER partner does not
conform.</p>
            <p>The field "&amp;str" is an explicit character
string:</p>
            <ul>
               <li>IDT is
null: Reception of a MESSAGE FPDU with a null Transfer Identifier
(PI 13)               </li>
            </ul>
            <ul>
               <li>Attribute
= n: PI 14 in the MESSAGE FPDU is set to an invalid value
(attribute request)               </li>
            </ul>
            <ul>
               <li>Data
Code = n: Unknown code for the data to be transported               </li>
            </ul>
            <ul>
               <li>Mismatch
between header and FPDU size: The FPDU length indicated in the header is not equal
to the length of the FPDU received               </li>
            </ul>
            <ul>
               <li>Unknown
FPDU: The number identifying the received FPDU is not referenced               </li>
            </ul>
            <ul>
               <li>Missing
PI number n into FPDU: The PI is mandatory for this type of FPDU               </li>
            </ul>
            <ul>
               <li>Unknown
PI number n into FPDU: The PI is unknown for this type of FPDU               </li>
            </ul>
            <ul>
               <li>PGI n
in PGI into FPDU: The presence of a PGI embedded in another PGI is invalid               </li>
            </ul>
            <ul>
               <li>Invalid
length n for PI n into FPDU: The length of the PI is invalid (less than minimum
length or greater than maximum length)               </li>
            </ul>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>Transfer aborted with DIAGI=220, DIAGP=MSG + PeSIT code.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTH37E"></span>CFTH37E PART=&amp;part Invalid D.MESSAGE FPDU &amp;str</p>
            <p>CFTH37E Invalid D.MESSAGE FPDU &lt;PART=&amp;part &amp;str&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>The START of MESSAGE FPDU sent by the REQUESTER partner
does not conform.</p>
            <p>The field "&amp;str" is an explicit character
string:</p>
            <ul>
               <li>IDT is
null: Reception of a D.MESSAGE FPDU with a null Transfer
Identifier (PI 13)               </li>
            </ul>
            <ul>
               <li>Attribute
= n: PI 14 of the D.MESSAGE FPDU is set to an invalid value
(attribute request)               </li>
            </ul>
            <ul>
               <li>Data
Code = n: Unknown code for the data to be transported               </li>
            </ul>
            <ul>
               <li>Mismatch
between header and FPDU size: The FPDU length indicated in the header is not equal
to the length of the FPDU received               </li>
            </ul>
            <ul>
               <li>Unknown
FPDU: The number identifying the received FPDU is not referenced               </li>
            </ul>
            <ul>
               <li>Missing
PI number n into FPDU: The PI is mandatory for this type of FPDU               </li>
            </ul>
            <ul>
               <li>Unknown
PI number n into FPDU: The PI is unknown for this type of FPDU               </li>
            </ul>
            <ul>
               <li>PGI n
in PGI into FPDU: The presence of a PGI embedded in another PGI is invalid               </li>
            </ul>
            <ul>
               <li>Invalid
length n for PI n into FPDU: The length of the PI is invalid (less than minimum
length or greater than maximum length)               </li>
            </ul>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>Transfer aborted with DIAGI=220, DIAGP=DMG + PeSIT code.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTH38E"></span>CFTH38E PART=&amp;part Invalid READ FPDU &amp;str</p>
            <p>CFTH38E Invalid READ FPDU &lt;PART=&amp;part &amp;str&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>The READ FPDU sent by the REQUESTER partner does not conform.</p>
            <p>The field "&amp;str" is an explicit character
string:</p>
            <ul>
               <li>Restart
point must be null for new transfer: Reception of a READ FPDU with a restart point other
than 0 for a new transfer               </li>
            </ul>
            <ul>
               <li>Mismatch
between header and FPDU size: The FPDU length indicated in the header is not equal
to the length of the FPDU received               </li>
            </ul>
            <ul>
               <li>Unknown
FPDU:               </li>
            </ul>
            <ul>
               <li>Missing
PI number n into FPDU: The PI is mandatory for this type of FPDU               </li>
            </ul>
            <ul>
               <li>Unknown
PI number n into FPDU: The PI is unknown for this type of FPDU               </li>
            </ul>
            <ul>
               <li>PGI n
in PGI into FPDU: The presence of a PGI embedded in another PGI is invalid               </li>
            </ul>
            <ul>
               <li>Invalid
length n for PI n into FPDU: The length of the PI is invalid (less than minimum
length or greater than maximum length)               </li>
            </ul>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>Transfer aborted with DIAGI=220, DIAGP=RDF + PeSIT code.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTH39E"></span>CFTH39E PART=&amp;part Invalid SELECT FPDU &amp;str</p>
            <p>CFTH39E Invalid SELECT FPDU &lt;PART=&amp;part &amp;str&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>The SELECT FPDU sent by the REQUESTER partner does not
conform.</p>
            <p>The field "&amp;str" is an explicit character
string:</p>
            <ul>
               <li>IDT not
null: Reception of a SELECT FPDU with a non-null Transfer
Identifier (PI 13) for a new transfer               </li>
            </ul>
            <ul>
               <li>IDT null
with restart: Reception of a SELECT FPDU with a null Transfer Identifier
(PI 13) for a transfer to be restarted               </li>
            </ul>
            <ul>
               <li>Attribute
= n: PI 15 of the SELECT FPDU is set to an invalid value
(file attribute request)               </li>
            </ul>
            <ul>
               <li>Restart
= n: PI 15 of the SELECT FPDU is set to an invalid value
(restart or new transfer)               </li>
            </ul>
            <ul>
               <li>Priority
= n: PI 17 of the SELECT FPDU is set to an invalid value
(transfer priority)               </li>
            </ul>
            <ul>
               <li>NSDU
too small n: The negotiated NSDU size is smaller than the minimum
allowed value (128)               </li>
            </ul>
            <ul>
               <li>Mismatch
between header and FPDU size: The FPDU length indicated in the header is not equal
to the length of the FPDU received               </li>
            </ul>
            <ul>
               <li>Unknown
FPDU: The number identifying the received FPDU is not referenced               </li>
            </ul>
            <ul>
               <li>Missing
PI number n into FPDU: The PI is mandatory for this type of FPDU               </li>
            </ul>
            <ul>
               <li>Unknown
PI number n into FPDU: The PI is unknown for this type of FPDU               </li>
            </ul>
            <ul>
               <li>PGI n
in PGI into FPDU: The presence of a PGI embedded in another PGI is invalid               </li>
            </ul>
            <ul>
               <li>Invalid
length n for PI n into FPDU: The length of the PI is invalid (less than minimum
length or greater than maximum length)               </li>
            </ul>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>Transfer aborted with DIAGI=220, DIAGP=SEL + PeSIT code.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTH40E"></span>CFTH40E PART=&amp;part Invalid DTF FPDU (MULTART)</p>
            <p>CFTH40E Invalid DTF FPDU (MULTART) &lt;PART=&amp;part&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>The DTF FPDU received is multi-record but it is not valid
(the sum of the record lengths is not equal to the total length of the
received FPDU).</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>The transfer is aborted. The protocol code transported to the
remote partner is 220.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTH41E"></span>CFTH41E PART=&amp;part Invalid DTF.END FPDU &amp;str</p>
            <p>CFTH41E Invalid DTF.END FPDU &lt;PART=&amp;part &amp;str&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>The DTF END (end of data) FPDU sent by the sender partner
does not conform.</p>
            <p>The field "&amp;str" is an explicit character
string:</p>
            <ul>
               <li>Mismatch
between header and FPDU size:               </li>
            </ul>
            <p>The FPDU length indicated in the header is not equal
to the length of the FPDU received</p>
            <ul>
               <li>Unknown
FPDU:               </li>
            </ul>
            <p>The number identifying the received FPDU is not referenced</p>
            <ul>
               <li>Missing
PI number n into FPDU:               </li>
            </ul>
            <p>The PI is mandatory for this type of FPDU</p>
            <ul>
               <li>Unknown
PI number n into FPDU:               </li>
            </ul>
            <p>The PI is unknown for this type of FPDU</p>
            <ul>
               <li>PGI n
in PGI into FPDU:               </li>
            </ul>
            <p>The presence of a PGI embedded in another PGI is invalid</p>
            <ul>
               <li>Invalid
length n for PI n into FPDU:               </li>
            </ul>
            <p>The length of the PI is invalid (less than minimum
length or greater than maximum length)</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>Transfer aborted with DIAGI=220, DIAGP=DTE + PeSIT code.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTH42E"></span>CFTH42E PART=&amp;part Invalid SYNC FPDU &amp;str</p>
            <p>CFTH42E Invalid SYNC FPDU &lt;PART=&amp;part &amp;str&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>The SYNC (set synchronization point) FPDU sent by the sender
partner does not conform.</p>
            <p>The field "&amp;str" is an explicit character
string:</p>
            <ul>
               <li>Mismatch
between header and FPDU size:               </li>
            </ul>
            <p>The FPDU length indicated in the header is not equal
to the length of the FPDU received</p>
            <ul>
               <li>Unknown
FPDU:               </li>
            </ul>
            <p>The number identifying the received FPDU is not referenced</p>
            <ul>
               <li>Missing
PI number n into FPDU:               </li>
            </ul>
            <p>The PI is mandatory for this type of FPDU</p>
            <ul>
               <li>Unknown
PI number n into FPDU:               </li>
            </ul>
            <p>The PI is unknown for this type of FPDU</p>
            <ul>
               <li>PGI n
in PGI into FPDU:               </li>
            </ul>
            <p>The presence of a PGI embedded in another PGI is invalid</p>
            <ul>
               <li>Invalid
length n for PI n into FPDU:               </li>
            </ul>
            <p>The length of the PI is invalid (less than minimum
length or greater than maximum length)</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>Transfer aborted with DIAGI=220, DIAGP=SYN + PeSIT code.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTH43E"></span>CFTH43E PART=&amp;part Invalid AckSYNC 
FPDU &amp;str</p>
            <p>CFTH43E Invalid AckSYNC FPDU &lt;PART=&amp;part &amp;str&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>The AckSYNC (acknowledge synchronization point) FPDU sent
by the receiver partner does not conform.</p>
            <p>The field "&amp;str" is an explicit character
string:</p>
            <ul>
               <li>Mismatch
between header and FPDU size:               </li>
            </ul>
            <p>The FPDU length indicated in the header is not equal
to the length of the FPDU received</p>
            <ul>
               <li>Unknown
FPDU:               </li>
            </ul>
            <p>The number identifying the received FPDU is not referenced</p>
            <ul>
               <li>Missing
PI number n into FPDU:               </li>
            </ul>
            <p>The PI is mandatory for this type of FPDU</p>
            <ul>
               <li>Unknown
PI number n into FPDU:               </li>
            </ul>
            <p>The PI is unknown for this type of FPDU</p>
            <ul>
               <li>PGI n
in PGI into FPDU:               </li>
            </ul>
            <p>The presence of a PGI embedded in another PGI is invalid</p>
            <ul>
               <li>Invalid
length n for PI n into FPDU:               </li>
            </ul>
            <p>The length of the PI is invalid (less than minimum
length or greater than maximum length)</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>Transfer aborted with DIAGI=220, DIAGP=ASY + PeSIT code.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTH44E"></span>CFTH44E PART=&amp;part Invalid IDT FPDU &amp;str</p>
            <p>CFTH44E Invalid IDT FPDU &lt;PART=&amp;part &amp;str&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>The IDT (transfer interrupt) FPDU sent by the partner does
not conform.</p>
            <p>The field "&amp;str" is an explicit character
string:</p>
            <ul>
               <li>Mismatch
between header and FPDU size:               </li>
            </ul>
            <p>The FPDU length indicated in the header is not equal
to the length of the FPDU received,</p>
            <ul>
               <li>Unknown
FPDU:               </li>
            </ul>
            <p>The number identifying the received FPDU is not referenced</p>
            <ul>
               <li>Missing
PI number n into FPDU:               </li>
            </ul>
            <p>The PI is mandatory for this type of FPDU</p>
            <ul>
               <li>Unknown
PI number n into FPDU:               </li>
            </ul>
            <p>The PI is unknown for this type of FPDU</p>
            <ul>
               <li>PGI n
in PGI into FPDU:               </li>
            </ul>
            <p>The presence of a PGI embedded in another PGI is invalid</p>
            <ul>
               <li>Invalid
length n for PI n into FPDU:               </li>
            </ul>
            <p>The length of the PI is invalid (less than minimum
length or greater than maximum length)</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>Transfer aborted with DIAGI=220, DIAGP=IDT + PeSIT code.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTH45E"></span>CFTH45E PART=&amp;part Invalid AckIDT FPDU &amp;str</p>
            <p>CFTH45E Invalid AckIDT FPDU &lt;PART=&amp;part &amp;str&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>The AckIDT (acknowledge transfer interrupt) FPDU sent by
the partner does not conform.</p>
            <p>The field "&amp;str" is an explicit character
string:</p>
            <ul>
               <li>Mismatch
between header and FPDU size:               </li>
            </ul>
            <p>The FPDU length indicated in the header is not equal
to the length of the FPDU received</p>
            <ul>
               <li>Unknown
FPDU:               </li>
            </ul>
            <p>The number identifying the received FPDU is not referenced</p>
            <ul>
               <li>Missing
PI number n into FPDU:               </li>
            </ul>
            <p>The PI is mandatory for this type of FPDU</p>
            <ul>
               <li>Unknown
PI number n into FPDU:               </li>
            </ul>
            <p> The
PI is unknown for this type of FPDU</p>
            <ul>
               <li>PGI n
in PGI into FPDU:               </li>
            </ul>
            <p>The presence of a PGI embedded in another PGI is invalid</p>
            <ul>
               <li>Invalid
length n for PI n into FPDU:               </li>
            </ul>
            <p>The length of the PI is invalid (less than minimum
length or greater than maximum length)</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>Transfer aborted with DIAGI=220, DIAGP=AID + PeSIT code.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTH46E"></span>CFTH46E PART=&amp;part Invalid RESYNC FPDU &amp;str</p>
            <p>CFTH46E Invalid RESYNC FPDU &lt;PART=&amp;part &amp;str&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>The RESYNC (dynamic transfer resynchronization) FPDU sent
by the sender partner does not conform.</p>
            <p>The field "&amp;str" is an explicit character
string:</p>
            <ul>
               <li>Resynchronization
is not authorized:               </li>
            </ul>
            <p>Dynamic resynchronization is not authorized (CFTPROT
RESYNC parameter) or the maximum number of resynchronizations is exceeded
(CFTPROT RESTART parameter),</p>
            <ul>
               <li>Mismatch
between header and FPDU size:               </li>
            </ul>
            <p>The FPDU length indicated in the header is not equal
to the length of the FPDU received</p>
            <ul>
               <li>Unknown
FPDU:               </li>
            </ul>
            <p>The number identifying the received FPDU is not referenced</p>
            <ul>
               <li>Missing
PI number n into FPDU:               </li>
            </ul>
            <p>The PI is mandatory for this type of FPDU</p>
            <ul>
               <li>Unknown
PI number n into FPDU:               </li>
            </ul>
            <p>The PI is unknown for this type of FPDU</p>
            <ul>
               <li>PGI n
in PGI into FPDU:               </li>
            </ul>
            <p>The presence of a PGI embedded in another PGI is invalid</p>
            <ul>
               <li>Invalid
length n for PI n into FPDU:               </li>
            </ul>
            <p>The length of the PI is invalid (less than minimum
length or greater than maximum length)</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>Transfer aborted with DIAGI=220, DIAGP=RST + PeSIT code.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTH47E"></span>CFTH47E PART=&amp;part Invalid DESELECT FPDU &amp;str</p>
            <p>CFTH47E Invalid DESELECT FPDU &lt;PART=&amp;part &amp;str&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>The DESELECT FPDU sent by the requester partner does not
conform.</p>
            <p>The field "&amp;str" is an explicit character
string:</p>
            <ul>
               <li>Mismatch
between header and FPDU size: The FPDU length indicated in the header
is not equal to the length of the FPDU received               </li>
               <li>Unknown FPDU:
The number identifying the received FPDU is not referenced               </li>
               <li>Missing PI number
n into FPDU: The PI is mandatory for this type of FPDU               </li>
               <li>Unknown PI number
n into FPDU: The PI is unknown for this type of FPDU               </li>
               <li>PGI n in PGI
into FPDU: The presence of a PGI embedded in another PGI is invalid               </li>
               <li>Invalid length
n for PI n into FPDU: The length of the PI is invalid (less than minimum
length or greater than maximum length)               </li>
            </ul>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>Transfer aborted with DIAGI=220, DIAGP=DSE + PeSIT code.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTH48E"></span>CFTH48E PART=&amp;part Invalid DESELECT FPDU &amp;str</p>
            <p>CFTH48E Invalid AckREAD FPDU &lt;PART=&amp;part &amp;str&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>The AckRead FPDU sent by the receiver/sender partner does
not conform.</p>
            <p>The field "&amp;str" is an explicit character
string:</p>
            <ul>
               <li>Mismatch between
header and FPDU size: The FPDU length indicated in the header is not equal
to the length of the FPDU received               </li>
               <li>Unknown FPDU:
The number identifying the received FPDU is not referenced               </li>
               <li>Missing PI number
n into FPDU: The PI is mandatory for this type of FPDU               </li>
               <li>Unknown PI number
n into FPDU: The PI is unknown for this type of FPDU               </li>
               <li>PGI n in PGI
into FPDU: The presence of a PGI embedded in another PGI is invalid               </li>
               <li>Invalid length
n for PI n into FPDU: The length of the PI is invalid (less than minimum
length or greater than maximum length)               </li>
            </ul>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>Transfer aborted with DIAGI=220, DIAGP=ARD + PeSIT code.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTH49E"></span>CFTH49E PART=&amp;part Invalid WRITE FPDU &amp;str</p>
            <p>CFTH49E Invalid WRITE FPDU &lt;PART=&amp;part &amp;str&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>The WRITE FPDU sent by the requester/sender partner does
not conform.</p>
            <p>The field "&amp;str" is an explicit character
string:</p>
            <ul>
               <li>Mismatch
between header and FPDU size: The FPDU length indicated in the header
is not equal to the length of the FPDU received               </li>
               <li>Unknown
FPDU: The number identifying the received FPDU is not referenced               </li>
               <li>Missing
PI number n into FPDU: The PI is mandatory for this type of FPDU               </li>
               <li>Unknown
PI number n into FPDU: The PI is unknown for this type of FPDU               </li>
               <li>PGI n
in PGI into FPDU: The presence of a PGI embedded in another PGI is invalid               </li>
               <li>Invalid
length n for PI n into FPDU: The length of the PI is invalid (less than
minimum length or greater than maximum length)               </li>
            </ul>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>Transfer aborted with DIAGI=220, DIAGP=WRI + PeSIT code.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTH50E"></span>CFTH50E PART=&amp;part Invalid M.MESSAGE FPDU &amp;str</p>
            <p>CFTH50E Invalid M.MESSAGE FPDU &lt;PART=&amp;part &amp;str&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>The Middle of Message FPDU sent by the requester partner
does not conform.</p>
            <p>The field "&amp;str" is an explicit character
string:</p>
            <ul>
               <li>Mismatch
between header and FPDU size: The FPDU length indicated in the header
is not equal to the length of the FPDU received               </li>
               <li>Unknown
FPDU: The number identifying the received FPDU is not referenced               </li>
               <li>Missing
PI number n into FPDU: The PI is mandatory for this type of FPDU               </li>
               <li>Unknown
PI number n into FPDU: The PI is unknown for this type of FPDU               </li>
               <li>PGI n
in PGI into FPDU: The presence of a PGI embedded in another PGI is invalid               </li>
               <li>Invalid
length n for PI n into FPDU: The length of the PI is invalid (less than
minimum length or greater than maximum length)               </li>
            </ul>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>Transfer aborted with DIAGI=220, DIAGP=MMG + PeSIT code.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTH51E"></span>CFTH51E PART=&amp;part Invalid F.MESSAGE FPDU &amp;str</p>
            <p>CFTH51E Invalid F.MESSAGE FPDU &lt;PART=&amp;part &amp;str&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>The End of Message FPDU sent by the requester partner does
not conform.</p>
            <p>The field "&amp;str" is an explicit character
string:</p>
            <ul>
               <li>Mismatch between
header and FPDU size: The FPDU length indicated in the header is not equal
to the length of the FPDU received               </li>
               <li>Unknown FPDU:The
number identifying the received FPDU is not referenced               </li>
               <li>Missing PI number
n into FPDU:The PI is mandatory for this type of FPDU               </li>
               <li>Unknown PI number
n into FPDU:The PI is unknown for this type of FPDU               </li>
               <li>PGI n in PGI
into FPDU: The presence of a PGI embedded in another PGI is invalid               </li>
               <li>Invalid length
n for PI n into FPDU:The length of the PI is invalid (less than minimum
length or greater than maximum length)               </li>
            </ul>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>Transfer aborted with DIAGI=220, DIAGP=FMG + PeSIT code.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTH52E"></span>CFTH52E PART=&amp;part Invalid AckCLOSE FPDU &amp;str</p>
            <p>CFTH52E Invalid AckCLOSE FPDU &lt;PART=&amp;part &amp;str&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>The AckCLOSE FPDU sent by the server partner does not conform.</p>
            <p>The field "&amp;str" is an explicit character
string:</p>
            <ul>
               <li>Mismatch
between header and FPDU size: The FPDU length indicated in the header
is not equal to the length of the FPDU received               </li>
               <li>Unknown
FPDU: The number identifying the received FPDU is not referenced               </li>
               <li>Missing
PI number n into FPDU: The PI is mandatory for this type of FPDU               </li>
               <li>Unknown
PI number n into FPDU: The PI is unknown for this type of FPDU               </li>
               <li>PGI n
in PGI into FPDU: The presence of a PGI embedded in another PGI is invalid               </li>
               <li>Invalid
length n for PI n into FPDU: The length of the PI is invalid (less than
minimum length or greater than maximum length)               </li>
            </ul>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>Transfer aborted with DIAGI=220, DIAGP=ACF + PeSIT code.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTH53E"></span>CFTH53E PART=&amp;part Invalid AckDESELECT  FPDU
&amp;str</p>
            <p>CFTH53E Invalid AckDESELECT FPDU &lt;PART=&amp;part &amp;str&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>The AckDESELECT FPDU sent by the server partner does not
conform.</p>
            <p>The field "&amp;str" is an explicit character
string:</p>
            <ul>
               <li>Mismatch between
header and FPDU size: The FPDU length indicated in the header is not equal
to the length of the FPDU received               </li>
               <li>Unknown FPDU: The
number identifying the received FPDU is not referenced               </li>
               <li>Missing PI number
n into FPDU: The PI is mandatory for this type of FPDU               </li>
               <li>Unknown PI number
n into FPDU: The PI is unknown for this type of FPDU               </li>
               <li>PGI n in PGI into
FPDU: The presence of a PGI embedded in another PGI is invalid               </li>
               <li>Invalid length
n for PI n into FPDU: The length of the PI is invalid (less than minimum
length or greater than maximum le               </li>
            </ul>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>Transfer aborted with DIAGI=220, DIAGP=ADS + PeSIT code.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTH54E"></span>CFTH54E PART=&amp;part Invalid CLOSE FPDU &amp;str</p>
            <p>CFTH54E Invalid CLOSE FPDU &lt;PART=&amp;part &amp;str&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>The CLOSE (file close) FPDU sent by the requester partner
does not conform.</p>
            <p>The field "&amp;str" is an explicit character
string:</p>
            <ul>
               <li>Mismatch
between header and FPDU size: The FPDU length indicated in the header
is not equal to the length of the FPDU received               </li>
               <li>Unknown
FPDU: The number identifying the received FPDU is not referenced               </li>
               <li>Missing
PI number n in FPDU: The PI is mandatory for this type of FPDU               </li>
               <li>Unknown
PI number n in FPDU: The PI is unknown for this type of FPDU               </li>
               <li>PGI n
in PGI into FPDU: The presence of a PGI embedded in another PGI is invalid               </li>
               <li>Invalid
length n for PI n into FPDU: The length of the PI is invalid (less than
minimum length or greater than maximum length)               </li>
            </ul>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>Transfer aborted with DIAGI=220, DIAGP=CRF + PeSIT code.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTH55E"></span>CFTH55E PART=&amp;part Invalid DTF FPDU &amp;str</p>
            <p>CFTH55E Invalid DTF FPDU &lt;PART=&amp;part &amp;str&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>The DTF (data send) FPDU sent by the sender partner does
not conform.</p>
            <p>The field "&amp;str" is an explicit character
string:</p>
            <ul>
               <li>Too much
data without synchro               </li>
            </ul>
            <p>A synchronization interval, CFTPROT SPACING or RPACING
parameter, has been negotiated and the amount of data received since the
start of the transfer (or since the last synchronization FPDU) is greater
than this interval.</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>Consequence</p>         </td>
         <td width="80%">            <p>Transfer aborted with DIAGI=220, DIAGP=DTF + PeSIT code.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Information</p>         </td>
         <td width="80%">            <p><span id="CFTH56I"></span>CFTH56I PART=&amp;part IDS=&amp;ids &amp;prot &amp;str session opened pi7=&amp;n:&amp;n HOST=&amp;pstate &amp;prot</p>
            <p>CFTH56I &amp;prot &amp;str session opened &lt;PART=&amp;part IDS=&amp;ids pi7=&amp;n:&amp;n HOST=&amp;pstate&gt; &amp;prot</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">An &amp; prot session in either Requester or Server mode was opened, where &amp;prot = PeSIT, ODETTE, or SFTP.
            <p>And where:</p>
            <ul>
               <li>PART: partner               </li>
               <li>PROT:
local protocol definition (CFTPROT)               </li>
               <li>IDS:
reference for this session               </li>
               <li>pi7:
the window and the interval of the negotiated synchronization               </li>
               <li>pi2 and pi24:
the window and the interval of the negotiated synchronization               </li>
               <li>HOST:
            <ul>
               <li>            <p>Requester: The host address configured through CFTTCP for the related partner (either an IP or a logical hostname).</p>               </li>
               <li>            <p>Server: The IP address of the incoming connection.</p>               </li>
            </ul>               </li>
            </ul>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Information</p>         </td>
         <td width="80%">            <p><span id="CFTH57I"></span>CFTH57I PART=&amp;part IDS=&amp;ids IDF=&amp;idf IDT=&amp;idt transfer selected pi25=&amp;n</p>
            <p>CFTH57I transfer selected PART=&amp;part IDS=&amp;ids IDF=&amp;idf IDT=&amp;idt
pi25=&amp;n</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>A
transfer passed the selection phase in the PeSIT session that was referenced
by the IDS field.</p>
            <p>The field
pi25 indicate the maximum size of the negotiated message. The displayed
reference in the second message is the public transfer reference.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Information</p>         </td>
         <td width="80%">            <p><span id="CFTH58I"></span>CFTH58I PART=&amp;part IDS=&amp;ids IDF=&amp;idf NIDT=&amp;idt transfer deselected T=&amp;n</p>
            <p>CFTH58I transfer deselected &lt;PART=&amp;part IDS=&amp;ids IDF=&amp;idf NIDT=&amp;idt T=&amp;n&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>A transfer passed the deselection phase in the PeSIT
session referred to by the IDS. The IDS is the reference for this particular session context.</p>
            <p>The T field indicates the armed time-out for the CFTPROT parameter:</p>
            <ul>
               <li>disctd – requester mode, <span>or</span>               </li>
               <li>discts – server mode               </li>
            </ul>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Information</p>         </td>
         <td width="80%">            <p><span id="CFTH59I"></span>CFTH59I PART=&amp;part IDS=&amp;ids IDM=&amp;idm NIDT=&amp;idt message transferred</p>
            <p>CFTH59I message transferred PART=&amp;part IDS=&amp;ids IDM=&amp;idm NIDT=&amp;idt</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>A message
transfer was carried out in the PeSIT as referenced by the IDS field, where the IDS refers to this specific session context.</p>
            <p>The displayed
reference in the second message is the public transfer reference.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Information</p>         </td>
         <td width="80%">            <p><span id="CFTH60I"></span>CFTH60I PART=&amp;part IDS=&amp;ids IDM=&amp;idm NIDT=&amp;idt [Reply | Nack] transferred</p>
            <p>CFTH60I [Reply | Nack] transferred PART=&amp;part IDS=&amp;ids IDM=&amp;idm NIDT=&amp;idt</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>An acknowledgement
type transfer message was carried out in the PeSIT session, where
the IDS references the session context.</p>
            <p>The
reference in the second message is the public transfer reference.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Information</p>         </td>
         <td width="80%">            <p><span id="CFTH61I"></span>CFTH61I PART=&amp;part IDS=&amp;ids ["Requester"|"Server"] &amp;ref session closed &amp;prot</p>
            <p>CFTH61I &amp;prot ["Requester"|"Server"] session closed &lt;PART=&amp;part IDS=&amp;ids&gt; &amp;prot</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>An &amp; prot session in either Requester or Server mode was closed, where &amp;prot = PeSIT, ODETTE, or SFTP.</p>
            <p>And:</p>
            <ul>
               <li>&amp;part: the partner identifier involved in the session               </li>
               <li>&amp;ids: the reference for this session context               </li>
            </ul>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Information</p>         </td>
         <td width="80%">            <p><span id="CFTH62I"></span>CFTH62I REF=&amp;ref</p>
            <p>CFTH62I REF=&amp;ref</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>
            <p> </p>         </td>
         <td width="80%">            <ul>
               <li>The transfer has passed the selection phase in the PeSIT
session referenced by the IDS field.                 </li>
               <li>An acknowledgement-type message was performed in the
PeSIT session referenced by the IDS, the session reference.               </li>
               <li>The pi25 field indicates the maximum size of the negotiated
message.               </li>
               <li>The reference displayed in the second message is the public
reference of the transfer (pi13.pi3.pi4.pi11.pi12.pi61.pi62).               </li>
            </ul>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Information</p>         </td>
         <td width="80%">            <p><span id="CFTH63I"></span>CFTH63I PART=&amp;part IDS=&amp;ids PESIT DMZ session for messages only</p>
            <p>CFTH63I PESIT DMZ session for messages only &lt;PART=&amp;part IDS=&amp;ids&gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>A PeSIT DMZ session was open but only for mailing messages.
This message follows message CFTH56I, where the IDS is the session call id.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Information</p>         </td>
         <td width="80%">            <p><span id="CFTH64I"></span>CFTH64I PESIT session rejected L=&amp;reason R=&amp;diag</p>
            <p>CFTH64I PESIT session rejected L=&amp;local R=&amp;reason</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>Protocol connection refused at network level.</p>
            <ul>
               <li>&amp;reason: Network reason               </li>
               <li>&amp;diag: Network diagnostic               </li>
            </ul>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Information</p>         </td>
         <td width="80%">            <p><span id="CFTH65I"></span>CFTH65I PART=&amp;part IDS=&amp;ids PESIT DMZ permanent session control call=&amp;n</p>
            <p>CFTH65I PESIT DMZ permanent session control call=&amp;n &lt;PART=&amp;part IDS=&amp;ids &gt;</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>Support for permanent links in DMZ.</p>
            <p><span>Transfer CFT</span> in DMZ does not give the TURN when there are
no more files to send, but sends
an FPDU Control Call to the initiator
<span>Transfer CFT</span> at regular negotiated intervals to prevent the temporization from expiring.</p>
            <ul>
               <li>&amp;ids = Session call id               </li>
               <li>&amp;call = interval for the DMZ control call               </li>
            </ul>         </td>
      </tr>
   </tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="100%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="20%">            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>         </td>
         <td width="80%">            <p><span id="CFTH66E"></span>CFTH66E Incoming calls (&amp;count) rejected, ERROR=&amp;error (&amp;info1|&amp;info2), PROTOCOL=&amp;protocol</p>
            <p>CFTH66E Incoming calls (&amp;count) rejected, ERROR=&amp;error (&amp;info1|&amp;info2), PROTOCOL=&amp;protocol</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="20%">            <p>Explanation</p>         </td>
         <td width="80%">            <p>Incoming calls are rejected:</p>
            <ul>
               <li>&amp;count = Number of rejected calls               </li>
               <li>&amp;error = Error message               </li>
               <li>&amp;info1 = Additional information               </li>
               <li>&amp;info2 = Additional information               </li>
               <li>&amp;protocol = Protocol type when available               </li>
            </ul>         </td>
      </tr>
   </tbody>
</table>
