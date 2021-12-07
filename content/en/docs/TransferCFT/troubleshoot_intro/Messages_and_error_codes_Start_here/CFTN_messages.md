{
    "title": "Transfer CFT messages: CFTN",
    "linkTitle": "CFTN messages",
    "weight": "330"
}This topic lists the CFTNxx  (CFT xnnx) messages and provides the type,  a description, consequence, and corrective actions when applicable.

**Message format**

Earlier versions of Transfer CFT used a different message format than version 3.1.3 and higher. This document displays both formats when applicable and available, otherwise only the v23 is used. Using the CFTLOG Format = V24 setting, the log displays as shown:

CFTXXX: fixed text message &lt;variables>

**Example**

CFTLOG FORMAT=\[V23,V24\]

For V23: `CFTT57I PART=&part IDF=&idf IDT=&idt &str transfer started`

For V24: `CFTT57I &str transfer started   <IDTU=&idtu PART=&part IDF=&idf IDT=&idt>`

```
V23 format
V24 format
Information
<span id="CFTN01I"></span>CFTN01I NET=&net started
CFTN01I NET=&net started
Explanation
Start of the network resource &net.
```

 

```
V23 format
V24 format
Information
<span id="CFTN02I"></span>CFTN02I NET=&net PROTOCOL=&prot started
CFTN02I NET=&net PROTOCOL=&prot started
Explanation
Start of the protocol &prot associated with the &net
network.
```

 

```
V23 format
V24 format
Error
<span id="CFTN03E"></span>CFTN03E Error creating SSL task &str
CFTN03E Error creating SSL task &str
Explanation
Problem with activating the CFTTSSL task. The error is
specified by &str.
Consequence
The transfer is aborted.
Action
Contact the support team if necessary.
```

 

```
V23 format
V24 format
Error
<span id="CFTN04E"></span>CFTN04E Synchronization error (&str) SSLTID=&pid 
CR=&cr CS=&scs
CFTN04E Synchronization error (&str) SSLTID=&pid _ CR= &cr CS=&cs
Explanation
Problem with sending an internal {{< TransferCFT/componentshortname >}} message to
a CFTTSSL task.
```

 

```
V23 format
V24 format
Information
<span id="CFTN05I"></span>CFTN05I &message
CFTN05I Network resource depletion prevention enabled for class &n
Explanation
TCP/IP and connection dispatcher related information. The message contains the explanation of the information.
```

 

```
V23 format
V24 format
Error
<span id="CFTN05E"></span>CFTN05E &message
CFTN05E &message
Explanation
A TCP/IP error related to file transfer operations or
resource initialization was detected. The message contains the explanation of the error in plain text.
Consequence
If the error occurs during the {{< TransferCFT/componentshortname >}} initialization
                      phase, this phase is stopped.
                      Otherwise, if the error is related to a file transfer,
                      this transfer will not proceed.
Action
For an error occurring during the initialization phase, check
                      the CFTNET definitions.
                      For an error involving a file transfer, check the
                      CFTPART definitions.
```

 

```
V23 format
V24 format
Warning
<span id="CFTN05W"></span>CFTN05W &message
CFTN05W &message
Explanation
The same as CFTN08E, a TCP/IP related error, but the condition is considered less severe.
```

 

```
V23 format
V24 format
Information
<span id="CFTN05W"></span><span id="CFTN06I"></span>CFTN06I No network class suitable for resource depletion prevention activation
CFTN06I No network class suitable for resource depletion prevention activation
Explanation
Network resource depletion prevention (NRDP) is enabled but not activated.
```

 

```
V23 format
V24 format
Error
<span id="CFTN08E"></span>CFTN08E SFTP bind() failed on address &address and port &port: Only one usage of each socket address (protocol/network address/port) is normally permitted
CFTN08E SFTP bind() failed on address &address and port &port: Only one usage of each socket address (protocol/network address/port) is normally permitted
Explanation
There is another server connection on that port.
```

 

```
V23 format
V24 format
Error
<span id="CFTN09E"></span>CFTN09E SFTP bind() failed on address &address and port &port: &reason
CFTN09E SFTP bind() failed on address &address and port &port: &reason
Explanation
Failed to establish the server connection for a reason other than CFTN08E.
```

 

```
V23 format
V24 format
Error
<span id="CFTN10E"></span>CFTN10E Server connection refused, we have reached the connection limit, MAXCNX=&maxcnx
CFTN10E Server connection refused, we have reached the connection limit, MAXCNX=&n
Explanation
Reached the maximum number of supported connections. The incoming connection is rejected.
```

 

```
V23 format
V24 format
Error
CFTN11E Server connection refused, we have reached the limit of file descriptors in CFTSFTP process
CFTN11E Server connection refused, we have reached the limit of file descriptors in CFTSFTP process
Explanation
The server connection was refused because you reached the file descriptors limit in the CFTSFTP process.
```

 

```
V23 format
V24 format
Error
CFTN12E Connection failed, we have reached the limit of file descriptors in CFTSFTP process
CFTN12E Connection failed, we have reached the limit of file descriptors in CFTSFTP process                    
Explanation
The client connection failed because you reached the file descriptors limit in the CFTSFTP process.
```

 

```
V23 format
V24 format
Warning
<span id="CFTN36W"></span>CFTN36W
TCPMAXUSER=&maxcnx reached. Network connect reject host=&host
port=&port &str
CFTN36W
TCPMAXUSER=&maxcnx reached. Network connect reject host=&host
port=&port &str
Explanation
The maximum number of connections supported has been reached.
An incoming connection from host &host port &port is rejected.
```
