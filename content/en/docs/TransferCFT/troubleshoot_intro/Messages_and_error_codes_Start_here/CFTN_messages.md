{
    "title": "CFTN messages",
    "linkTitle": "CFTN messages",
    "weight": "350"
}This topic lists the CFTNxx (CFT xnnx) messages and provides the type, a description, consequence, and corrective actions when applicable.

**Message format**

Earlier versions of Transfer CFT used a different message format than version 3.1.3 and higher. This document displays both formats when applicable and available, otherwise only the v23 is used. Using the CFTLOG Format = V24 setting, the log displays as shown:

CFTXXX: fixed text message &lt;variables>

**Example**

CFTLOG FORMAT=\[V23,V24\]

For V23: CFTT57I PART=&part IDF=&idf IDT=&idt &str transfer started

For V24: `CFTT57I &str transfer started   <IDTU=&idtu PART=&part IDF=&idf IDT=&idt>`

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr valign="top">
         <td>
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Information</p>
         </td>
         <td width="80%">
            <p><a name="CFTN01I"></a>CFTN01I NET=&amp;net started</p>
            <p>CFTN01I NET=&amp;net started</p>
         </td>
      </tr>
      <tr valign="top">
         <td>
            <p>Explanation</p>
         </td>
         <td width="80%">
            <p>Start of the network resource &amp;net.</p>
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr valign="top">
         <td width="20%">
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Information</p>
         </td>
         <td width="80%">
            <p><a name="CFTN02I"></a>CFTN02I NET=&amp;net PROTOCOL=&amp;prot started</p>
            <p>CFTN02I NET=&amp;net PROTOCOL=&amp;prot started</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="20%">
            <p>Explanation</p>
         </td>
         <td width="80%">
            <p>Start of the protocol &amp;prot associated with the &amp;net 
 network.</p>
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr valign="top">
         <td width="20%">
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>
         </td>
         <td width="80%">
            <p><a name="CFTN03E"></a>CFTN03E Error creating SSL task &amp;str</p>
            <p>CFTN03E Error creating SSL task &amp;str</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="20%">
            <p>Explanation</p>
         </td>
         <td width="80%">
            <p>Problem with activating the CFTTSSL task. The error is 
 specified by &amp;str.</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="20%">
            <p>Consequence</p>
         </td>
         <td width="80%">
            <p>The transfer is aborted.</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="20%">
            <p>Action</p>
         </td>
         <td width="80%">
            <p>Contact the support team if necessary.</p>
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr valign="top">
         <td>
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>
         </td>
         <td width="80%">
            <p><a name="CFTN04E"></a>CFTN04E Synchronization error (&amp;str) SSLTID=&amp;pid  
 CR=&amp;cr CS=&amp;scs</p>
            <p>CFTN04E Synchronization error (&amp;str) SSLTID=&amp;pid _ CR= &amp;cr CS=&amp;cs</p>
         </td>
      </tr>
      <tr valign="top">
         <td>
            <p>Explanation</p>
         </td>
         <td width="80%">
            <p>Problem with sending an internal <span>Transfer CFT</span> message to 
 a CFTTSSL task.</p>
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr valign="top">
         <td>
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Information</p>
         </td>
         <td width="80%">
            <p><a name="CFTN05I"></a>CFTN05I &amp;message</p>
            <p>CFTN05I Network resource depletion prevention enabled for class &amp;n</p>
         </td>
      </tr>
      <tr valign="top">
         <td>
            <p>Explanation</p>
         </td>
         <td width="80%">TCP/IP and connection dispatcher related information. The message contains the explanation of the information.         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr valign="top">
         <td width="20%">
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>
         </td>
         <td width="80%">
            <p><a name="CFTN05E"></a>CFTN05E &amp;message </p>
            <p>CFTN05E &amp;message</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="20%">
            <p>Explanation</p>
         </td>
         <td width="80%">
            <p>A TCP/IP error related to file transfer operations or
 resource initialization was detected. The message contains the explanation of the error in plain text.</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="20%">Consequence         </td>
         <td width="80%">If the error occurs during the <span>Transfer CFT</span> initialization
                      phase, this phase is stopped.
                      Otherwise, if the error is related to a file transfer,
                      this transfer will not proceed.
         </td>
      </tr>
      <tr valign="top">
         <td width="20%">Action         </td>
         <td width="80%">For an error occurring during the initialization phase, check
                      the CFTNET definitions.
                      For an error involving a file transfer, check the
                      CFTPART definitions.
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr valign="top">
         <td width="20%">
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Warning</p>
         </td>
         <td width="80%">
<p width="80%"><a name="CFTN05W"></a>CFTN05W &amp;message </p>
<p width="80%">CFTN05W &amp;message</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="20%">
            <p>Explanation</p>
         </td>
         <td width="80%">
            <p>The same as CFTN08E, a TCP/IP related error, but the condition is considered less severe.</p>
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr valign="top">
         <td width="20%">
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Information</p>
         </td>
         <td width="80%">
<p width="80%"><a name="CFTN05W"></a><a name="CFTN06I"></a>CFTN06I No network class suitable for resource depletion prevention activation </p>
<p width="80%">CFTN06I No network class suitable for resource depletion prevention activation</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="20%">
            <p>Explanation</p>
         </td>
         <td width="80%">
            <p>Network resource depletion prevention (NRDP) is enabled but not activated.</p>
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr valign="top">
         <td width="20%">
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>
         </td>
         <td width="80%">
            <p><a name="CFTN08E"></a>CFTN08E SFTP bind() failed on address &amp;address and port &amp;port: Only one usage of each socket address (protocol/network address/port) is normally permitted</p>
            <p>CFTN08E SFTP bind() failed on address &amp;address and port &amp;port: Only one usage of each socket address (protocol/network address/port) is normally permitted</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="20%">
            <p>Explanation</p>
         </td>
         <td width="80%">There is another server connection on that port.         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr valign="top">
         <td>
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Error</p>
         </td>
         <td width="80%">
<p width="80%"><a name="CFTN09E"></a>CFTN09E SFTP bind() failed on address &amp;address and port &amp;port: &amp;reason</p>
<p width="80%">CFTN09E SFTP bind() failed on address &amp;address and port &amp;port: &amp;reason</p>
         </td>
      </tr>
      <tr valign="top">
         <td>
            <p>Explanation</p>
         </td>
         <td width="80%">Failed to establish the server connection for a reason other than CFTN08E.         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr valign="top">
         <td width="20%">
            <p>V23 format</p>
            <p>V24 format</p>Error         </td>
         <td width="80%">
<p width="80%"><a name="CFTN10E"></a>CFTN10E Server connection refused, we have reached the connection limit, MAXCNX=&amp;maxcnx</p>
            <p>CFTN10E Server connection refused, we have reached the connection limit, MAXCNX=&amp;n</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="20%">Explanation         </td>
         <td width="80%">Reached the maximum number of supported connections. The incoming connection is rejected.         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr valign="top">
         <td width="20%">
            <p>V23 format</p>
            <p>V24 format</p>Error         </td>
         <td width="80%">
            <p>CFTN11E Server connection refused, we have reached the limit of file descriptors in CFTSFTP process </p>
            <p>CFTN11E Server connection refused, we have reached the limit of file descriptors in CFTSFTP process</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="20%">Explanation         </td>
         <td width="80%">The server connection was refused because you reached the file descriptors limit in the CFTSFTP process.         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr valign="top">
         <td width="20%">
            <p>V23 format</p>
            <p>V24 format</p>Error          </td>
         <td width="80%">
<p width="80%">CFTN12E Connection failed, we have reached the limit of file descriptors in CFTSFTP process
</p>
<p width="80%">CFTN12E Connection failed, we have reached the limit of file descriptors in CFTSFTP process                    </p>
         </td>
      </tr>
      <tr valign="top">
         <td width="20%">Explanation         </td>
         <td width="80%">The client connection failed because you reached the file descriptors limit in the CFTSFTP process.         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr valign="top">
         <td width="20%">
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Warning </p>
         </td>
         <td width="80%">
            <p><a name="CFTN36W"></a>CFTN36W 
 TCPMAXUSER=&amp;maxcnx reached. Network connect reject host=&amp;host 
 port=&amp;port &amp;str </p>
            <p>CFTN36W 
 TCPMAXUSER=&amp;maxcnx reached. Network connect reject host=&amp;host 
 port=&amp;port &amp;str</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="20%">
            <p>Explanation</p>
         </td>
         <td width="80%">
            <p>The maximum number of connections supported has been reached. 
 An incoming connection from host &amp;host port &amp;port is rejected. 
 </p>
         </td>
      </tr>
</table>
