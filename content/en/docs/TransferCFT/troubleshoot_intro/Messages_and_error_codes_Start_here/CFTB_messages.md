{
    "title": "Transfer CFT messages: CFTB",
    "linkTitle": "CFTAB messages",
    "weight": "270"
}This topic lists the CFTBxx messages and provides a type, a description, and when applicable a consequence and corrective action.

**Message format**

Earlier versions of Transfer CFT used a different message format than version 3.1.3 and higher. This document displays both formats when applicable and available, otherwise only the v23 is used. Using the CFTLOG Format = V24 setting, the log displays as shown:

CFTXXX: fixed text message &lt;variables>

**Example**

CFTLOG FORMAT=\[V23,V24\]

For V23: `CFTT57I PART=&part IDF=&idf IDT=&idt &str transfer started`

For V24: `CFTT57I &str transfer started   <IDTU=&idtu PART=&part IDF=&idf IDT=&idt>`

### Auto documented messages

Certain auto-documented messages, for example CFTA01I, CFTA02W, CFTA03E, CFTA04F, are not fully detailed as they are considered self-explanatory. The CFTAnnx messages refer to the acceleration feature on all platforms that support acceleration.

-   CFTA01, CFTLOG\_SYS\_INFOR "CFTA01I &str"
-   CFTA02, CFTLOG\_SYS\_WARNI "CFTA02W &str"
-   CFTA03, CFTLOG\_SYS\_ERROR "CFTA03E &str"
-   CFTA04, CFTLOG\_SYS\_FATAL "CFTA04F &str"

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p>         </td>
         <td><p><span id="CFTB01E"></span>CFTB01E PART=&amp;part Context area allocation failure
CS=&amp;scs</p>
<p>CFTB01E PART=&amp;part Context area allocation failure CS=&amp;cs</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>Cannot allocate the working area necessary for the transfer.</p>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p>In REQUESTER mode, the transfer is refused with a {{< TransferCFT/componentshortname  >}}
122 diagnostic code and a MALLOC protocol diagnostic message.<br />
In SERVER mode, the incoming call is rejected.</p>
<p>In this case, as the partner's name is not known, the value
UNKNOWN is displayed.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p>         </td>
         <td><p><span id="CFTB02E"></span>CFTB02E PART=&amp;part
TFIL Exchange buffer allocation failure CS=&amp;scs</p>
<p>CFTB02E PART=&amp;part TFIL Exchange buffer allocation failure CS=&amp;cs</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>Cannot allocate the working area required to exchange information
between the PROTOCOL task and the FILE task.</p>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p>In REQUESTER mode, the transfer is refused with a Transfer
CFT 122 code and a MALLOC protocol diagnostic message.</p>
<p>In SERVER mode, the incoming call is rejected. In this
case, as the partner's name is not known, the value UNKNOWN is displayed.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p>         </td>
         <td><p><span id="CFTB03E"></span>CFTB03E PART=&amp;part Error sending data on network
NCR=&amp;ncr NCS=&amp;ncs NET=&amp;net</p>
<p>CFTB03E PART=&amp;part Error sending data on network NCR=&amp;ncr NCS=&amp;cs NET=&amp;net</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>Cannot send a message on the network.</p>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p>The transfer
is interrupted with a {{< TransferCFT/componentshortname  >}} 302 code and a protocol diagnostic
message indicating the specific error code of the error occurring during
the send request. This code is expressed in hexadecimal form.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p>         </td>
         <td><p><span id="CFTB06E"></span>CFTB06E Flow control error NCR=&amp;ncr NCS=&amp;ncs
NET=&amp;net</p>
<p>CFTB06E PART=&amp;part Flow control error NCR=&amp;ncr NCS=&amp;cs NET=&amp;net</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>Network flow control error.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p>         </td>
         <td><p><span id="CFTB07E"></span>CFTB07E PART=&amp;part TFIL task Synchronization error
CR=&amp;cr CS=&amp;cs</p>
<p>CFTB07E PART=&amp;part TFIL task Synchronization error CR= &amp;cr CS=&amp;cs</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>Problem encountered when sending an internal {{< TransferCFT/componentshortname  >}}
message to the FILE task.</p>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p>The transfer is aborted by the protocol task (network disconnection).
However, as the FILE task is not protected by a time-out, the request
remains in the C status in the catalog</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p>         </td>
         <td><p><span id="CFTB08E"></span>CFTB08E PART=&amp;part Network release resp err NCR=&amp;ncr
NCS=&amp;ncs NET=&amp;net</p>
<p>CFTB08E PART=&amp;part Network release resp err NCR=&amp;ncr NCS=&amp;cs NET=&amp;net</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>Cannot respond to a network disconnection indication.</p>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p>This incident has no effect on the previous transfer (whether
completed or interrupted).</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p>         </td>
         <td><p><span id="CFTB09E"></span>CFTB09E PART=&amp;part Network connect req local err
NCR=&amp;ncr NCS=&amp;ncs NET=&amp;net</p>
<p>CFTB09E PART=&amp;part Network connect req local err NCR=&amp;ncr NCS=&amp;cs NET=&amp;net</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>Cannot make an outgoing connection request on the network.</p>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p>For a general
-6 code (maximum number of connections reached on the resource), the transfer
is refused with a {{< TransferCFT/componentshortname  >}} 416 diagnostic code and a MAXCNX protocol
diagnostic message. The transfer will be retried (minimum time-out equal
to the WSCAN parameter of the CFTCAT command), without incrementing the
retry counter.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p>         </td>
         <td><p><span id="CFTB10E"></span>CFTB10E PART=&amp;part RECOV=&amp;recov L=&amp;local
R=&amp;reason D=&amp;diag NET=&amp;net</p>
<p>CFTB10E PART=&amp;part RECOV=&amp;recov L=&amp;local R=&amp;reason ld D=&amp;diag ld NET=&amp;net</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>Physical connection refused.</p>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p>Depending on the source of the refusal and the RECOV code, the
transfer is set to the K status (diagnostic code 303) or remains
in the D status (diagnostic code 302) and will be retried.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p>         </td>
         <td><p><span id="CFTB18E"></span>CFTB18E Incoming call reject error NCR=&amp;ncr NCS=&amp;ncs
NET=&amp;net</p>
<p>CFTB18E Incoming call reject error NCR=&amp;ncr NCS=&amp;cs NET=&amp;net</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>Cannot refuse an incoming call.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p>         </td>
         <td><p><span id="CFTB19E"></span>CFTB19E Incoming call accept error NCR=&amp;ncr NCS=&amp;ncs
NET=&amp;net</p>
<p>CFTB19E Incoming call accept error NCR=&amp;ncr NCS=&amp;cs NET=&amp;net</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>Cannot accept an incoming call.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p>         </td>
         <td><p><span id="CFTB19E"></span>CFTB20E Invalid ETEBAC3 Card &amp;id NET=&amp;net</p>
<p>CFTB20E Invalid ETEBAC3 Card &amp;id NET=&amp;net</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p> </p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p>         </td>
         <td><p><span id="CFTB21E"></span>CFTB21E PART=&amp;part MAIN task Synchronization error
CR=&amp;cr CS=&amp;scs</p>
<p>CFTB21E PART=&amp;part MAIN task Synchronization error CR= &amp;cr CS=&amp;cs</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>Transfer
CFT internal synchronization error.</p>         </td>
      </tr>
   </tbody>
</table>
