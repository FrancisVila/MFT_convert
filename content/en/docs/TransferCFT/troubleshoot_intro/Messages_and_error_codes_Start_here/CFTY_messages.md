{
    "title": "Transfer CFT messages: CFTY",
    "linkTitle": "CFTY messages",
    "weight": "400"
}This topic lists the CFTYxx  (CFT xnnx) messages and provides the type,  a description, consequence, and corrective actions when applicable.

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
<span id="CFTY03E"></span>CFTY03E PID=&pid System error [&string] CR=&cr
CS=&cs
CFTY03E PID=&pid System error [&string] CR=&cr
CS=&cs
Explanation
A new SSL task cannot initialize its working environment. According
to the error origin, various messages are given below.
Result
The SSL session in progress is aborted.
V23 format
V24 format
Information
CFTY03E
PID=&pid System error [MMALLOC] CR=&cr CS=&cs
CFTY03E
PID=&pid System error [MMALLOC] CR=&cr CS=&cs
Explanation
Dynamic memory allocation failure.
V23 format
V24 format
Information
CFTY03E PID=&pid System error [SYDEF] CR=&cr CS=&cs
CFTY03E PID=&pid System error [SYDEF] CR=&cr CS=&cs
Explanation
Task semaphore creation failure:

-   CR=-1 Maximum
    semaphore count reached
-   CR=-2 Internal
    error
-   CR=-9 System
    error

V23 format
V24 format
Information
CFTY03E PID=&pid System error [SYPOST] CR=&cr CS=&cs
CFTY03E PID=&pid System error [SYPOST] CR=&cr CS=&cs
Explanation
Semaphore write failure:

-   CR=-1 Undefined
    or already closed semaphore
-   CR=-2 Too
    many messages waiting in semaphore
-   CR=-3 Message
    length too long  
-   CR=-9 System
    error

V23 format
V24 format
Information
CFTY03E PID=&pid System error [SYWAIT] CR=&cr CS=&cs
CFTY03E PID=&pid System error [SYWAIT] CR=&cr CS=&cs
Explanation
Semaphore read failure:

-   CR=-1 Undefined
    semaphore
-   CR=-3 Already
    closed semaphore
-   CR=-9 System
    error

V23 format
V24 format
Information
CFTY03E PID=&pid System error [CTXDEF] CR=&cr CS=&cs
CFTY03E PID=&pid System error [CTXDEF] CR=&cr CS=&cs
Explanation
SSL session context manager creation failure:

-   CR=-2,-3 Dynamic
    memory allocation failure
-   CR=-9 Maximum
    context manager count reached

V23 format
V24 format
Information
CFTY03E PID=&pid System error [STARTPKI] CR=&cr CS=&cs
CFTY03E PID=&pid System error [STARTPKI] CR=&cr CS=&cs
Explanation
PKI internal
error. The CS code is in the form « PKII nnn » for a Transfer
CFT internal PKI error or « PKIE nnn » for an external PKI error.
nnn is a SSL alert code. See SSL alert errors.
```

 

```
V23 format
V24 format
Information
<span id="CFTY04E"></span>CFTY04E PID=&pid PKIFNAME=&string Internal PKI
error [&string] CR=&cr
CS=&cs CFTY04E PID=&pid PKIFNAME=&string Internal PKI
error [&string] CR=&cr CS=&cs
Explanation
A new SSL
task cannot read the index file of the local certificate data base.
This file name is set by default in the CFTPARM
object. Depending on the error's origin, the message could be one of the following:
Result
The SSL session in progress is aborted.
V23 format
V24 format
Information
CFTY04E PID=&pid PKIFNAME=&string Internal PKI error
[FMALLOC] CR=&cr CS=&cs
CFTY04E PID=&pid PKIFNAME=&string Internal PKI error
[FMALLOC] CR=&cr CS=&cs
Explanation
File allocation failure:

-   CR=-1: File not found

<!-- -->

-   CR=-3: File already allocated (exclusive mode) by
    another application

<!-- -->

-   CR=-9: System error

V23 format
V24 format
Information
CFTY04E PID=&pid PKIFNAME=&string Internal PKI error
[DMOPEN] CR=&cr CS=&cs
CFTY04E PID=&pid PKIFNAME=&string Internal PKI error
[DMOPEN] CR=&cr CS=&cs
Explanation
File open failure:

-   CR=-1: File not allocated

<!-- -->

-   CR=-2: Invalid open mode

<!-- -->

-   CR=-3: Access conflict

<!-- -->

-   CR=-9: System error

V23 format
V24 format
Information
CFTY04E PID=&pid PKIFNAME=&string Internal PKI error
[DMGN] CR=&cr CS=&cs
CFTY04E PID=&pid PKIFNAME=&string Internal PKI error
[DMGN] CR=&cr CS=&cs
Explanation
File read failure:

-   CR=-9: System error

V23 format
V24 format
Information
CFTY04E PID=&pid PKIFNAME=&string Internal PKI error
[HPUT] CR=&cr CS=&cs
CFTY04E PID=&pid PKIFNAME=&string Internal PKI error
[HPUT] CR=&cr CS=&cs
Explanation
File loading error:

-   CR=-3: Dynamic memory allocation error when loading
    file

```

 

```
V23 format
V24 format
Information
<span id="CFTY05E"></span>CFTY05E PID=&pid PKIFNAME=&file Syntax error
_ &string
CFTY05E PID=&pid PKIFNAME=&file Syntax error
_ &string
Explanation
The index file of the local certificate data base is not valid.
This file name is set by default in the CFTPARM object.
Depending on the error's origin, the message could be one of the following:

-   MISSING
    SECTION=TrustedCas: the file doesn’t contain a [TrustedCas] section. This
    section is used to declare certificate authorities (CA)
-   SECTION=TrustedCas
    IS EMPTY: [TrustedCas] section is empty
-   BAD
    VALUE LINE=linenumber: Invalid syntax for a certificate or private key
    statement. The line number in the file is displayed
-   INVALID
    SECTION LINE=linenumber: Invalid syntax for a section statement. The line
    number in the file is displayed

Result
The SSL session in progress
is aborted.
Action 
Rectify the index file.
```

 

```
V23 format
V24 format
Information
<span id="CFTY06E"></span>CFTY06E CTX=&ctx Certificate Request Message error
_ &string
CFTY06E CTX=&ctx Certificate Request Message error
_ &string
Explanation
SSL handshake error: a request certificate message, sent by
the server, is invalid. According to the error origin, various reasons
are given below:

-   UNSUPPORTED
    TYPE FIELD: The server requires an authentication type which is not supported
    by {{< TransferCFT/componentshortname >}}.
-   INVALID
    DN LENGTH: The DN (Distinguished Name) length is invalid

Result
The SSL session in progress
is aborted. An alert is sent to the server.
V23 format
V24 format
Information
<span id="CFTY07E"></span>CFTY07E CTX=&ctx System error [&string] CR=&cr
CS=&cs
CFTY07E CTX=&ctx System error [&string] CR=&cr
CS=&cs
Explanation
SSL handshake error. According to the error origin, various
messages are given below.
Result
The SSL session in progress is aborted. An alert is sent
to the remote entity.
V23 format
V24 format
Information
CFTY07E CTX=&ctx System error [MMALLOC] CR=&cr CS=&cs
CFTY07E CTX=&ctx System error [MMALLOC] CR=&cr CS=&cs
Explanation
Dynamic memory allocation failure.
Result
If the SSL handshake is in progress, the session is aborted
and an alert is sent to the remote entity.
If the SSL session is established (handshake successful)
the network session is cleared.
V23 format
V24 format
Information
CFTY07E CTX=&ctx System error [SYPOST] CR=&cr CS=&cs
CFTY07E CTX=&ctx System error [SYPOST] CR=&cr CS=&cs
Explanation
Semaphore write failure:

-   CR=-1
    :The semaphore is undefined or already closed

<!-- -->

-   CR=-2:
    Too many messages are waiting on the semaphore

<!-- -->

-   CR=-3: The message length is too big

<!-- -->

-   CR=-9:
    System error

V23 format
V24 format
Information
CFTY07E CTX=&ctx System error [CTXALLOC] CR=&cr CS=&cs
CFTY07E CTX=&ctx System error [CTXALLOC] CR=&cr CS=&cs
Explanation
Memory allocation error for a new SSL session context:

-   CR=-2,-3: Dynamic memory allocation failure

<!-- -->

-   CR=-9: Maximum context count reached

V23 format
V24 format
Information
CFTY07E CTX=&ctx System error [CTXCHK] CR=&cr CS=&cs
CFTY07E CTX=&ctx System error [CTXCHK] CR=&cr CS=&cs
Explanation
Invalid
message received from another {{< TransferCFT/componentshortname >}} task (context is invalid or
already free).
V23 format
V24 format
Information
CFTY07E PROT=&prot SSLPID=&pid HOST=&host synchronization
error CR=&cr CS=&scs
CFTY07E PROT=&prot SSLPID=&pid HOST=&host synchronization
error CR=&cr CS=&scs
Explanation
Problem
with sending an internal {{< TransferCFT/componentshortname >}} message to the protocol task during
the SSL initialization phase
Consequence
The transfer is aborted
Action
Analyze the &scs code and contact the product support team
if necessary
```

 

```
V23 format
V24 format
Information
<span id="CFTY08I"></span>CFTY08I PID=&pid Task started successfully
CFTY08I PID=&pid Task started successfully
Explanation
Successful creation of a new SSL task.
```

 

```
V23 format
V24 format
Information
<span id="CFTY09I"></span>CFTY09I PID=&pid Task ended
CFTY09I PID=&pid Task ended
Explanation
SSL task ended.
```

 

```
V23 format
V24 format
Information
<span id="CFTY10E"></span>CFTY10E PID=&pid CTX=&ctx Invalid reference on
&string
CFTY10E PID=&pid CTX=&ctx Invalid reference on
&string
Explanation
Invalid network message received (context is invalid or already
free).
Result
Message is not treated.
```

 

```
V23 format
V24 format
Information
<span id="CFTY11I"></span>CFTY11I CTX=&ctx PART=&id SSL=&id Closing
client SSL session
CFTY11I CTX=&ctx PART=&id SSL=&id Closing
client SSL session
Explanation
A client SSL session is closed. The session reference and the
transfer partner are displayed.
```

 

```
V23 format
V24 format
Information
<span id="CFTY12I"></span>CFTY12I CTX=&ctx PROT=&id SSL=&id Closing
server SSL session
CFTY12I CTX=&ctx PROT=&id SSL=&id Closing
server SSL session
Explanation
A server SSL session is closed. The session reference and the
protocol are displayed.
```

 

```
V23 format
V24 format
Information
<span id="CFTY13E"></span>CFTY13E CTX=&ctx SSL Handshake local error [&string]
CR=&cr
CFTY13E CTX=&ctx SSL Handshake local error [&string]
CR=&cr
Explanation
SSL session handshake failure.
Result
The SSL session in progress is aborted. An alert is sent
to the remote entity.
Action
Call the {{< TransferCFT/componentshortname >}} hot line.
Analyze the &cr error code (refer to the SSL protocol
error codes). Contact the product support
team if necessary.
```

 

```
V23 format
V24 format
Information
<span id="CFTY14I"></span>CFTY14I CTX=&ctx PART=&id SSL=&id client
session established VERSION=&ver CIPHER=&num AUTH=&mode CFTY14I CTX=&ctx PART=&id SSL=&id client
session established VERSION=&ver CIPHER=&num AUTH=&mode
 
Explanation
Successful handshake. A new client SSL session is established.
The negotiated version, cypher suite, and the authentication mode (SERVER or BOTH)
are displayed.
```

 

```
V23 format
V24 format
Information
<span id="CFTY15I"></span>CFTY15I CTX=&ctx PROT=&id SSL=&id server
session established VERSION=&ver CIPHER=&num AUTH=&mode CFTY15I CTX=&ctx PROT=&id SSL=&id server
session established VERSION=&ver CIPHER=&num AUTH=&mode
Explanation
Successful handshake. A new server SSL session is established.
The negotiated version, cypher suite, and the authentication mode (SERVER or BOTH)
are displayed.
```

 

```
V23 format
V24 format
Information
<span id="CFTY16I"></span>CFTY16I CTX=&ctx &message
CFTY16I CTX=&ctx &message
Explanation
Message sent by the external PKI exit.
```

 

```
V23 format
V24 format
Information
<span id="CFTY17I"></span>CFTY17I CTX=&ctx &msg
CFTY17I CTX=&ctx &msg
Explanation
Specific exit security (PKI System) message.
```

 

```
V23 format
V24 format
Information
<span id="CFTY18E"></span>CFTY18E CTX=&ctx &str
CFTY18E CTX=&ctx &str
Explanation
Internal error on calling up the internal PKI. The "&str"
field can have the following values:

-   PKI_NOT_TREATED
    : PKI function not treated

<!-- -->

-   PKI_ERR_CERT_BAD
    : Incorrect certificate (format error)

<!-- -->

-   PKI_ERR_CERT_UNSUPPORTED
    : Certificate not supported

<!-- -->

-   PKI_ERR_CERT_REVOKED
    : Certificate revoked

<!-- -->

-   PKI_ERR_CERT_EXPIRED
    : Certificate expired

<!-- -->

-   PKI_ERR_CERT_UNKNOWN
    : Certificate unknown

<!-- -->

-   PKI_ERR_CERT_NOT_VALID
    : Certificate not valid

<!-- -->

-   PKI_ERR_CERT_BAD_SIGN
    : Integrity error (incorrect signature)

<!-- -->

-   PKI_ERR_CERT_BAD_HASH
    : Integrity error (hash code  incorrect)

<!-- -->

-   PKI_ERR_CERT_BAD_CA
    :Certification organism certificate invalid

<!-- -->

-   PKI_ERR_CERT_ALGO_UNSUPPORTED
    : Unsupported ciphering algorithm

<!-- -->

-   PKI_ERR_CERT_NOT_FOUND
    : User certificate not found

<!-- -->

-   PKI_ERR_CA_NOT_FOUND
    : Certification organism certificate not found

<!-- -->

-   PKI_ERR_BAD_KEY
    : Invalid ciphering key

<!-- -->

-   PKI_ERR_BUF_TOO_SHORT
     : Memory buffer size too small

<!-- -->

-   PKI_ERR_SYS
     : Internal error linked to the system (memory
    allotment, system function, and so on)

<!-- -->

-   PKI_ERR_PARM
    : Ciphering parameter invalid

<!-- -->

-   PKI_ERR_OTHERS
    : Other error (authentication, ciphering, integrity,
    and so on)

Consequence
The transfer is aborted.
Action
Contact the product support team if necessary.
```

 

```
V23 format
V24 format
Information
<span id="CFTY19I"></span>CFTY19I PART=&id SSL=&id opening client session
CTX=&ctx on task PID=&pid
CFTY19I PART=&id SSL=&id opening client session
CTX=&ctx on task PID=&pid
Explanation
Handshake
is started for a new client SSL session. {{< TransferCFT/componentshortname >}} gives a unique reference
to it. Using this reference, the session could be tracked.
```

 

```
V23 format
V24 format
Information
<span id="CFTY20I"></span> CFTY20I PROT=&id SSL=&id opening server session
CTX=&ctx on task PID=&pid
CFTY20I PROT=&id SSL=&id opening server session
CTX=&ctx on task PID=&pid
Explanation
Handshake
is started for a new server SSL session. {{< TransferCFT/componentshortname >}} gives a unique reference
to it. Using this reference, the session could be tracked.
```

 

```
V23 format
V24 format
Information
<span id="CFTY21I"></span>CFTY21I CTX=&ctx Remote server certificate accepted
CFTY21I CTX=&ctx Remote server certificate accepted
Explanation
A server certificate is accepted during a session handshake.
The authority identifier which has signed the certificate is displayed.
```

 

```
V23 format
V24 format
Information
<span id="CFTY22I"></span>CFTY22I CTX=&ctx Remote client certificate accepted
CFTY22I CTX=&ctx Remote client certificate accepted
Explanation
A client certificate is accepted during a session handshake.
The authority identifier which has signed the certificate is displayed.
```

 

```
V23 format
V24 format
Information
<span id="CFTY23I"></span>CFTY23I CTX=&ctx Client certificate ID=&id ROOTID=&id
CFTY23I CTX=&ctx Client certificate ID=&id ROOTID=&id
Explanation
Client certificate used locally for authentication.
```

 

```
V23 format
V24 format
Information
<span id="CFTY24I"></span>CFTY24I CTX=&ctx Server certificate ID=&id ROOTID=&id
CFTY24I CTX=&ctx Server certificate ID=&id ROOTID=&id
Explanation
Server certificate used locally for authentication.
```

 

```
V23 format
V24 format
Information
<span id="CFTY25I"></span>CFTY25I CTX=&ctx remote address HOST=&string
CFTY25I CTX=&ctx remote address HOST=&string
Explanation
This message is displayed after the message CFTY20I. It gives
the address (HOST name or IP address using TCP/IP network) of the remote
connected entity.
```

 

```
V23 format
V24 format
Information
<span id="CFTY26I"></span>CFTY26I CTX=&ctx Anonymous &str session
CFTY26I CTX=&ctx Anonymous &str session
Explanation
Opening of a secure session without authentication in either
client or server mode. Refer to the {{< TransferCFT/componentshortname >}} Online documentation.

-   &ctx= context SSL
-   str = client or server

```

 

```
V23 format
V24 format
Information
<span id="CFTY28W"></span>CFTY28W CTX=&ctx &str2 = &filename
CFTY28W CTX=&ctx &str2 = &filename
Explanation
The file contains the remote certificate has not been recorded.
Consequence
The transfer can be performed but the remote certificate is
not recorded.
Action
Write
down the &str2
value and contact the product support team if necessary.
```

 

```
V23 format
V24 format
Information
<span id="CFTY30E"></span>CFTY30E CTX=&ctx SSL Handshake remote error [&string] CR=&cr
CFTY30E CTX=&ctx SSL Handshake remote error [&string] CR=&cr
Explanation
SSL session handshake failure. An alert has been received from the remote peer.
Consequence
The SSL session in progress is aborted.
Action
Analyze the &cr error code (refer to the SSL protocol error codes). Also check the remote partner log for more details. Contact Axway support if necessary.
```

 

```
V23 format
V24 format
Information
<span id="CFTY41E"></span>CFTY41E CFTCTX=<session_reference>, xpp call <PassportPS_API_function>: error [<PassportPS_API_function_returncode>]
CFTY41E CFTCTX=<session_reference>, xpp call <PassportPS_API_function>: error [<PassportPS_API_function_returncode>]
Explanation
An error occurred during an exchange or connection with the PassPort PS server.
<PassportPS_API_function> and <PassportPS_API_function_returncode> identify the function in error and provide the return code for the function.
```

 

```
V23 format
V24 format
Information
<span id="CFTY44E"></span>CFTY44E CFTCTX=<session_reference>, long err msg : [<PassportPS_API_error_code>]
Explanation
An error occurred during an exchange or connection with the PassPort PS server. The <PassportPS_API_error_code>  describes the error.
```

 

```
V23 format
V24 format
Information
<span id="CFTY45E"></span>CFTY45E CFTCTX=<session_reference>, <PassportPS_API_error_message>
Explanation
An error occurred during an exchange or connection with the PassPort PS server. The <PassportPS_API_error_message> describes the error.
```

 

```
V23 format
V24 format
Information
<span id="CFTY50I"></span>CFTY50I SSH client session established CTX=&ctx PART=&part Version=&version Cipher in=&cipher Cipher out=&cipher Key exchange=&key hmac in=&hmac hmac out=&hmac &IPVersion
CFTY50I SSH client session established CTX=&ctx PART=&part Version=&version Cipher in=&cipher Cipher out=&cipher Key exchange=&key hmac in=&hmac hmac out=&hmac
Explanation
Established a new SSH client session.
&version is SSH1 or SSH2.
```

 

```
V23 format
V24 format
Information
<span id="CFTY51I"></span>CFTY51I SSH server session established CTX=&ctx PART=&part Version=&version Cipher in=&cipher Cipher out=&cipher Key exchange=&key hmac in=&hmac hmac out=&hmac &IPVersion
CFTY51I SSH server session established CTX=&ctx PROT=&prot Version=&version Cipher in=&cipher Cipher out=&cipher Key exchange=&key hmac in=&hmac hmac out=&hmac
Explanation
Established a new SSH client session.
&version is SSH1 or SSH2.
```

 

```
V23 format
V24 format
Information
<span id="CFTY52I"></span>CFTY52I SFTP client session established CTX=&ctx PART=&part Version=&version Authentication=&authentication CFT Server=&server
CFTY52I SFTP client session established CTX=&ctx PART=&part Version=&version Authentication=&authentication CFT Server=&server
Explanation
Established a new SFTP client session.
&version is the SFTP version negotiated with the partner (>= 3).
&Authentication is Key or Password.
&server indicates if we are connected to a Transfer CFT server (Yes or No).
```

 

```
V23 format
V24 format
Information
<span id="CFTY53I"></span>CFTY53I SFTP server session established CTX=&ctx PROT=&prot Version=&version Authentication=&authentication CFT Client=&client
CFTY53I SFTP server session established CTX=&ctx PROT=&prot Version=&version Authentication=&authentication CFT Client=&client
Explanation
Established a new SFTP server session.
&version is the SFTP version negotiated with the partner (>= 3).

-   &Authentication is Password, System, PassPortAM, Key or XFBADM.
-   &client indicates if you are connected to a Transfer CFT client.

```

 
