{
    "title": "Transfer CFT messages: CFTN",
    "linkTitle": "CFTN messages",
    "weight": "330"
}This topic lists the CFTNxx (CFT xnnx) messages and provides the type, a description, consequence, and corrective actions when applicable.

**Message format**

Earlier versions of Transfer CFT used a different message format than version 3.1.3 and higher. This document displays both formats when applicable and available, otherwise only the v23 is used. Using the CFTLOG Format = V24 setting, the log displays as shown:

CFTXXX: fixed text message &lt;variables>

**Example**

CFTLOG FORMAT=\[V23,V24\]

For V23: `CFTT57I PART=&part IDF=&idf IDT=&idt &str transfer started`

For V24: `CFTT57I &str transfer started   <IDTU=&idtu PART=&part IDF=&idf IDT=&idt>`

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Information</p>         </td>
         <td><p><span id="CFTN01I"></span>CFTN01I NET=&amp;net started</p>
<p>CFTN01I NET=&amp;net started</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>Start of the network resource &amp;net.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Information</p>         </td>
         <td><p><span id="CFTN02I"></span>CFTN02I NET=&amp;net PROTOCOL=&amp;prot started</p>
<p>CFTN02I NET=&amp;net PROTOCOL=&amp;prot started</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>Start of the protocol &amp;prot associated with the &amp;net
network.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p>         </td>
         <td><p><span id="CFTN03E"></span>CFTN03E Error creating SSL task &amp;str</p>
<p>CFTN03E Error creating SSL task &amp;str</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>Problem with activating the CFTTSSL task. The error is
specified by &amp;str.</p>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p>The transfer is aborted.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Contact the support team if necessary.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p>         </td>
         <td><p><span id="CFTN04E"></span>CFTN04E Synchronization error (&amp;str) SSLTID=&amp;pid 
CR=&amp;cr CS=&amp;scs</p>
<p>CFTN04E Synchronization error (&amp;str) SSLTID=&amp;pid _ CR= &amp;cr CS=&amp;cs</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>Problem with sending an internal {{< TransferCFT/componentshortname  >}} message to
a CFTTSSL task.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Information</p>         </td>
         <td><p><span id="CFTN05I"></span>CFTN05I &amp;message</p>
<p>CFTN05I Network resource depletion prevention enabled for class &amp;n</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td>TCP/IP and connection dispatcher related information. The message contains the explanation of the information.         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p>         </td>
         <td><p><span id="CFTN05E"></span>CFTN05E &amp;message</p>
<p>CFTN05E &amp;message</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>A TCP/IP error related to file transfer operations or
resource initialization was detected. The message contains the explanation of the error in plain text.</p>         </td>
      </tr>
      <tr>
         <td>Consequence         </td>
         <td>If the error occurs during the {{< TransferCFT/componentshortname  >}} initialization
phase, this phase is stopped.
Otherwise, if the error is related to a file transfer,
this transfer will not proceed.         </td>
      </tr>
      <tr>
         <td>Action         </td>
         <td>For an error occurring during the initialization phase, check
the CFTNET definitions.
For an error involving a file transfer, check the
CFTPART definitions.         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Warning</p>         </td>
         <td><p><span id="CFTN05W"></span>CFTN05W &amp;message</p>
<p>CFTN05W &amp;message</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>The same as CFTN08E, a TCP/IP related error, but the condition is considered less severe.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Information</p>         </td>
         <td><p><span id="CFTN05W"></span><span id="CFTN06I"></span>CFTN06I No network class suitable for resource depletion prevention activation</p>
<p>CFTN06I No network class suitable for resource depletion prevention activation</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>Network resource depletion prevention (NRDP) is enabled but not activated.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p>         </td>
         <td><p><span id="CFTN08E"></span>CFTN08E SFTP bind() failed on address &amp;address and port &amp;port: Only one usage of each socket address (protocol/network address/port) is normally permitted</p>
<p>CFTN08E SFTP bind() failed on address &amp;address and port &amp;port: Only one usage of each socket address (protocol/network address/port) is normally permitted</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td>There is another server connection on that port.         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Error</p>         </td>
         <td><p><span id="CFTN09E"></span>CFTN09E SFTP bind() failed on address &amp;address and port &amp;port: &amp;reason</p>
<p>CFTN09E SFTP bind() failed on address &amp;address and port &amp;port: &amp;reason</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td>Failed to establish the server connection for a reason other than CFTN08E.         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
Error         </td>
         <td><p><span id="CFTN10E"></span>CFTN10E Server connection refused, we have reached the connection limit, MAXCNX=&amp;maxcnx</p>
<p>CFTN10E Server connection refused, we have reached the connection limit, MAXCNX=&amp;n</p>         </td>
      </tr>
      <tr>
         <td>Explanation         </td>
         <td>Reached the maximum number of supported connections. The incoming connection is rejected.         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
Error         </td>
         <td><p>CFTN11E Server connection refused, we have reached the limit of file descriptors in CFTSFTP process</p>
<p>CFTN11E Server connection refused, we have reached the limit of file descriptors in CFTSFTP process</p>         </td>
      </tr>
      <tr>
         <td>Explanation         </td>
         <td>The server connection was refused because you reached the file descriptors limit in the CFTSFTP process.         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
Error         </td>
         <td><p>CFTN12E Connection failed, we have reached the limit of file descriptors in CFTSFTP process</p>
<p>CFTN12E Connection failed, we have reached the limit of file descriptors in CFTSFTP process</p>         </td>
      </tr>
      <tr>
         <td>Explanation         </td>
         <td>The client connection failed because you reached the file descriptors limit in the CFTSFTP process.         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Warning</p>         </td>
         <td><p><span id="CFTN36W"></span>CFTN36W
TCPMAXUSER=&amp;maxcnx reached. Network connect reject host=&amp;host
port=&amp;port &amp;str</p>
<p>CFTN36W
TCPMAXUSER=&amp;maxcnx reached. Network connect reject host=&amp;host
port=&amp;port &amp;str</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>The maximum number of connections supported has been reached.
An incoming connection from host &amp;host port &amp;port is rejected.</p>         </td>
      </tr>
   </tbody>
</table>
