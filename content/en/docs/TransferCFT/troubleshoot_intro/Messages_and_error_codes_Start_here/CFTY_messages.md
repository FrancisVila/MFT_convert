{
    "title": "CFTY messages",
    "linkTitle": "CFTY messages",
    "weight": "420"
}This topic lists the CFTYxx (CFT xnnx) messages and provides the type, a description, consequence, and corrective actions when applicable.

**Message format**

Earlier versions of Transfer CFT used a different message format than version 3.1.3 and higher. This document displays both formats when applicable and available, otherwise only the v23 is used. Using the CFTLOG Format = V24 setting, the log displays as shown:

CFTXXX: fixed text message &lt;variables>

**Example**

CFTLOG FORMAT=\[V23,V24\]

For V23: CFTT57I PART=&part IDF=&idf IDT=&idt &str transfer started

For V24: `CFTT57I &str transfer started   <IDTU=&idtu PART=&part IDF=&idf IDT=&idt>`

<table data-border="1" data-cellspacing="0" width="90%">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Information</p></td>
<td width="80%"><p><span id="CFTY03E"></span>CFTY03E PID=&amp;pid System error [&amp;string] CR=&amp;cr
CS=&amp;cs</p>
<p>CFTY03E PID=&amp;pid System error [&amp;string] CR=&amp;cr
CS=&amp;cs</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>A new SSL task cannot initialize its working environment. According
to the error origin, various messages are given below.</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="20%"><p>Result</p></td>
<td width="80%"><p>The SSL session in progress is aborted.</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Information</p></td>
<td width="80%"><p>CFTY03E
PID=&amp;pid System error [MMALLOC] CR=&amp;cr CS=&amp;cs</p>
<p>CFTY03E
PID=&amp;pid System error [MMALLOC] CR=&amp;cr CS=&amp;cs</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>Dynamic memory allocation failure.</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Information</p></td>
<td width="80%"><p>CFTY03E PID=&amp;pid System error [SYDEF] CR=&amp;cr CS=&amp;cs</p>
<p>CFTY03E PID=&amp;pid System error [SYDEF] CR=&amp;cr CS=&amp;cs</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>Task semaphore creation failure:</p>
<ul>
<li>CR=-1 Maximum
semaphore count reached</li>
<li>CR=-2 Internal
error</li>
<li>CR=-9 System
error</li>
</ul></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Information</p></td>
<td width="80%"><p>CFTY03E PID=&amp;pid System error [SYPOST] CR=&amp;cr CS=&amp;cs</p>
<p>CFTY03E PID=&amp;pid System error [SYPOST] CR=&amp;cr CS=&amp;cs</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>Semaphore write failure:</p>
<ul>
<li>CR=-1 Undefined
or already closed semaphore</li>
<li>CR=-2 Too
many messages waiting in semaphore</li>
<li>CR=-3 Message
length too long  </li>
<li>CR=-9 System
error</li>
</ul></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Information</p></td>
<td width="80%"><p>CFTY03E PID=&amp;pid System error [SYWAIT] CR=&amp;cr CS=&amp;cs</p>
<p>CFTY03E PID=&amp;pid System error [SYWAIT] CR=&amp;cr CS=&amp;cs</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>Semaphore read failure:</p>
<ul>
<li>CR=-1 Undefined
semaphore</li>
<li>CR=-3 Already
closed semaphore</li>
<li>CR=-9 System
error</li>
</ul></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Information</p></td>
<td width="80%"><p>CFTY03E PID=&amp;pid System error [CTXDEF] CR=&amp;cr CS=&amp;cs</p>
<p>CFTY03E PID=&amp;pid System error [CTXDEF] CR=&amp;cr CS=&amp;cs</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>SSL session context manager creation failure:</p>
<ul>
<li>CR=-2,-3 Dynamic
memory allocation failure</li>
<li>CR=-9 Maximum
context manager count reached</li>
</ul></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Information</p></td>
<td width="80%"><p>CFTY03E PID=&amp;pid System error [STARTPKI] CR=&amp;cr CS=&amp;cs</p>
<p>CFTY03E PID=&amp;pid System error [STARTPKI] CR=&amp;cr CS=&amp;cs</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>PKI internal
error. The CS code is in the form « PKII nnn » for a Transfer
CFT internal PKI error or « PKIE nnn » for an external PKI error.
nnn is a SSL alert code. See SSL alert errors.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Information</p></td>
<td width="80%"><p><span id="CFTY04E"></span>CFTY04E PID=&amp;pid PKIFNAME=&amp;string Internal PKI
error [&amp;string] CR=&amp;cr</p>
<p>CS=&amp;cs CFTY04E PID=&amp;pid PKIFNAME=&amp;string Internal PKI
error [&amp;string] CR=&amp;cr CS=&amp;cs</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>A new SSL
task cannot read the index file of the local certificate data base.</p>
<p>This file name is set by default in the CFTPARM
object. Depending on the error's origin, the message could be one of the following:</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="20%"><p>Result</p></td>
<td width="80%"><p>The SSL session in progress is aborted.</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Information</p></td>
<td width="80%"><p>CFTY04E PID=&amp;pid PKIFNAME=&amp;string Internal PKI error
[FMALLOC] CR=&amp;cr CS=&amp;cs</p>
<p>CFTY04E PID=&amp;pid PKIFNAME=&amp;string Internal PKI error
[FMALLOC] CR=&amp;cr CS=&amp;cs</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>File allocation failure:</p>
<ul>
<li>CR=-1: File not found</li>
</ul>
<ul>
<li>CR=-3: File already allocated (exclusive mode) by
another application</li>
</ul>
<ul>
<li>CR=-9: System error</li>
</ul></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Information</p></td>
<td width="80%"><p>CFTY04E PID=&amp;pid PKIFNAME=&amp;string Internal PKI error
[DMOPEN] CR=&amp;cr CS=&amp;cs</p>
<p>CFTY04E PID=&amp;pid PKIFNAME=&amp;string Internal PKI error
[DMOPEN] CR=&amp;cr CS=&amp;cs</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>File open failure:</p>
<ul>
<li>CR=-1: File not allocated</li>
</ul>
<ul>
<li>CR=-2: Invalid open mode</li>
</ul>
<ul>
<li>CR=-3: Access conflict</li>
</ul>
<ul>
<li>CR=-9: System error</li>
</ul></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Information</p></td>
<td width="80%"><p>CFTY04E PID=&amp;pid PKIFNAME=&amp;string Internal PKI error
[DMGN] CR=&amp;cr CS=&amp;cs</p>
<p>CFTY04E PID=&amp;pid PKIFNAME=&amp;string Internal PKI error
[DMGN] CR=&amp;cr CS=&amp;cs</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>File read failure:</p>
<ul>
<li>CR=-9: System error</li>
</ul></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Information</p></td>
<td width="80%"><p>CFTY04E PID=&amp;pid PKIFNAME=&amp;string Internal PKI error
[HPUT] CR=&amp;cr CS=&amp;cs</p>
<p>CFTY04E PID=&amp;pid PKIFNAME=&amp;string Internal PKI error
[HPUT] CR=&amp;cr CS=&amp;cs</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>File loading error:</p>
<ul>
<li>CR=-3: Dynamic memory allocation error when loading
file</li>
</ul></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Information</p></td>
<td width="80%"><p><span id="CFTY05E"></span>CFTY05E PID=&amp;pid PKIFNAME=&amp;file Syntax error
_ &amp;string</p>
<p>CFTY05E PID=&amp;pid PKIFNAME=&amp;file Syntax error
_ &amp;string</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>The index file of the local certificate data base is not valid.
This file name is set by default in the CFTPARM object.</p>
<p>Depending on the error's origin, the message could be one of the following:</p>
<ul>
<li>MISSING
SECTION=TrustedCas: the file doesn’t contain a [TrustedCas] section. This
section is used to declare certificate authorities (CA)</li>
<li>SECTION=TrustedCas
IS EMPTY: [TrustedCas] section is empty</li>
<li>BAD
VALUE LINE=linenumber: Invalid syntax for a certificate or private key
statement. The line number in the file is displayed</li>
<li>INVALID
SECTION LINE=linenumber: Invalid syntax for a section statement. The line
number in the file is displayed</li>
</ul></td>
</tr>
<tr class="odd" data-valign="top">
<td width="20%"><p>Result</p></td>
<td width="80%"><p>The SSL session in progress
is aborted.</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>Action </p></td>
<td width="80%"><p>Rectify the index file.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Information</p></td>
<td width="80%"><p><span id="CFTY06E"></span>CFTY06E CTX=&amp;ctx Certificate Request Message error
_ &amp;string</p>
<p>CFTY06E CTX=&amp;ctx Certificate Request Message error
_ &amp;string</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>SSL handshake error: a request certificate message, sent by
the server, is invalid. According to the error origin, various reasons
are given below:</p>
<ul>
<li>UNSUPPORTED
TYPE FIELD: The server requires an authentication type which is not supported
by <span>Transfer CFT</span>.</li>
<li>INVALID
DN LENGTH: The DN (Distinguished Name) length is invalid</li>
</ul></td>
</tr>
<tr class="odd" data-valign="top">
<td width="20%"><p>Result</p></td>
<td width="80%"><p>The SSL session in progress
is aborted. An alert is sent to the server.</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Information</p></td>
<td width="80%"><p><span id="CFTY07E"></span>CFTY07E CTX=&amp;ctx System error [&amp;string] CR=&amp;cr
CS=&amp;cs</p>
<p>CFTY07E CTX=&amp;ctx System error [&amp;string] CR=&amp;cr
CS=&amp;cs</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>SSL handshake error. According to the error origin, various
messages are given below.</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>Result</p></td>
<td width="80%"><p>The SSL session in progress is aborted. An alert is sent
to the remote entity.</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Information</p></td>
<td width="80%"><p>CFTY07E CTX=&amp;ctx System error [MMALLOC] CR=&amp;cr CS=&amp;cs</p>
<p>CFTY07E CTX=&amp;ctx System error [MMALLOC] CR=&amp;cr CS=&amp;cs</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>Dynamic memory allocation failure.</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="20%"><p>Result</p></td>
<td width="80%"><p>If the SSL handshake is in progress, the session is aborted
and an alert is sent to the remote entity.</p>
<p>If the SSL session is established (handshake successful)
the network session is cleared.</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Information</p></td>
<td width="80%"><p>CFTY07E CTX=&amp;ctx System error [SYPOST] CR=&amp;cr CS=&amp;cs</p>
<p>CFTY07E CTX=&amp;ctx System error [SYPOST] CR=&amp;cr CS=&amp;cs</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>Semaphore write failure:</p>
<ul>
<li>CR=-1
:The semaphore is undefined or already closed</li>
</ul>
<ul>
<li>CR=-2:
Too many messages are waiting on the semaphore</li>
</ul>
<ul>
<li>CR=-3: The message length is too big</li>
</ul>
<ul>
<li>CR=-9:
System error</li>
</ul></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Information</p></td>
<td width="80%"><p>CFTY07E CTX=&amp;ctx System error [CTXALLOC] CR=&amp;cr CS=&amp;cs</p>
<p>CFTY07E CTX=&amp;ctx System error [CTXALLOC] CR=&amp;cr CS=&amp;cs</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>Memory allocation error for a new SSL session context:</p>
<ul>
<li>CR=-2,-3: Dynamic memory allocation failure</li>
</ul>
<ul>
<li>CR=-9: Maximum context count reached</li>
</ul></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Information</p></td>
<td width="80%"><p>CFTY07E CTX=&amp;ctx System error [CTXCHK] CR=&amp;cr CS=&amp;cs</p>
<p>CFTY07E CTX=&amp;ctx System error [CTXCHK] CR=&amp;cr CS=&amp;cs</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>Invalid
message received from another <span>Transfer CFT</span> task (context is invalid or
already free).</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Information</p></td>
<td width="80%"><p>CFTY07E PROT=&amp;prot SSLPID=&amp;pid HOST=&amp;host synchronization
error CR=&amp;cr CS=&amp;scs</p>
<p>CFTY07E PROT=&amp;prot SSLPID=&amp;pid HOST=&amp;host synchronization
error CR=&amp;cr CS=&amp;scs</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>Problem
with sending an internal <span>Transfer CFT</span> message to the protocol task during
the SSL initialization phase</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>Consequence</p></td>
<td width="80%"><p>The transfer is aborted</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="20%"><p>Action</p></td>
<td width="80%"><p>Analyze the &amp;scs code and contact the product support team
if necessary</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Information</p></td>
<td width="80%"><p><span id="CFTY08I"></span>CFTY08I PID=&amp;pid Task started successfully</p>
<p>CFTY08I PID=&amp;pid Task started successfully</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>Successful creation of a new SSL task.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Information</p></td>
<td width="80%"><p><span id="CFTY09I"></span>CFTY09I PID=&amp;pid Task ended</p>
<p>CFTY09I PID=&amp;pid Task ended</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>SSL task ended.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Information</p></td>
<td width="80%"><p><span id="CFTY10E"></span>CFTY10E PID=&amp;pid CTX=&amp;ctx Invalid reference on
&amp;string</p>
<p>CFTY10E PID=&amp;pid CTX=&amp;ctx Invalid reference on
&amp;string</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>Invalid network message received (context is invalid or already
free).</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="20%"><p>Result</p></td>
<td width="80%"><p>Message is not treated.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Information</p></td>
<td width="80%"><p><span id="CFTY11I"></span>CFTY11I CTX=&amp;ctx PART=&amp;id SSL=&amp;id Closing
client SSL session</p>
<p>CFTY11I CTX=&amp;ctx PART=&amp;id SSL=&amp;id Closing
client SSL session</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>A client SSL session is closed. The session reference and the
transfer partner are displayed.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Information</p></td>
<td width="80%"><p><span id="CFTY12I"></span>CFTY12I CTX=&amp;ctx PROT=&amp;id SSL=&amp;id Closing
server SSL session</p>
<p>CFTY12I CTX=&amp;ctx PROT=&amp;id SSL=&amp;id Closing
server SSL session</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>A server SSL session is closed. The session reference and the
protocol are displayed.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Information</p></td>
<td width="80%"><p><span id="CFTY13E"></span>CFTY13E CTX=&amp;ctx SSL Handshake local error [&amp;string]
CR=&amp;cr</p>
<p>CFTY13E CTX=&amp;ctx SSL Handshake local error [&amp;string]
CR=&amp;cr</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>SSL session handshake failure.</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="20%"><p>Result</p></td>
<td width="80%"><p>The SSL session in progress is aborted. An alert is sent
to the remote entity.</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>Action</p></td>
<td width="80%"><p>Call the <span>Transfer CFT</span> hot line.</p>
<p>Analyze the &amp;cr error code (refer to the SSL protocol
error codes). Contact the product support
team if necessary.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Information</p></td>
<td width="80%"><p><span id="CFTY14I"></span>CFTY14I CTX=&amp;ctx PART=&amp;id SSL=&amp;id client
session established VERSION=&amp;ver CIPHER=&amp;num AUTH=&amp;mode CFTY14I CTX=&amp;ctx PART=&amp;id SSL=&amp;id client
session established VERSION=&amp;ver CIPHER=&amp;num AUTH=&amp;mode</p>
<p> </p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>Successful handshake. A new client SSL session is established.
The negotiated version, cypher suite, and the authentication mode (SERVER or BOTH)
are displayed.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Information</p></td>
<td width="80%"><p><span id="CFTY15I"></span>CFTY15I CTX=&amp;ctx PROT=&amp;id SSL=&amp;id server
session established VERSION=&amp;ver CIPHER=&amp;num AUTH=&amp;mode CFTY15I CTX=&amp;ctx PROT=&amp;id SSL=&amp;id server
session established VERSION=&amp;ver CIPHER=&amp;num AUTH=&amp;mode</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>Successful handshake. A new server SSL session is established.
The negotiated version, cypher suite, and the authentication mode (SERVER or BOTH)
are displayed.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
<tbody>
<tr class="odd" data-valign="top">
<td><p>V23 format</p>
<p>V24 format</p>
<p>Information</p></td>
<td width="80%"><p><span id="CFTY16I"></span>CFTY16I CTX=&amp;ctx &amp;message</p>
<p>CFTY16I CTX=&amp;ctx &amp;message</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>Explanation</p></td>
<td width="80%"><p>Message sent by the external PKI exit.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Information</p></td>
<td width="80%"><p><span id="CFTY17I"></span>CFTY17I CTX=&amp;ctx &amp;msg</p>
<p>CFTY17I CTX=&amp;ctx &amp;msg</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>Specific exit security (PKI System) message.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Information</p></td>
<td width="80%"><p><span id="CFTY18E"></span>CFTY18E CTX=&amp;ctx &amp;str</p>
<p>CFTY18E CTX=&amp;ctx &amp;str</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>Internal error on calling up the internal PKI. The "&amp;str"
field can have the following values:</p>
<ul>
<li>PKI_NOT_TREATED
: PKI function not treated</li>
</ul>
<ul>
<li>PKI_ERR_CERT_BAD
: Incorrect certificate (format error)</li>
</ul>
<ul>
<li>PKI_ERR_CERT_UNSUPPORTED
: Certificate not supported</li>
</ul>
<ul>
<li>PKI_ERR_CERT_REVOKED
: Certificate revoked</li>
</ul>
<ul>
<li>PKI_ERR_CERT_EXPIRED
: Certificate expired</li>
</ul>
<ul>
<li>PKI_ERR_CERT_UNKNOWN
: Certificate unknown</li>
</ul>
<ul>
<li>PKI_ERR_CERT_NOT_VALID
: Certificate not valid</li>
</ul>
<ul>
<li>PKI_ERR_CERT_BAD_SIGN
: Integrity error (incorrect signature)</li>
</ul>
<ul>
<li>PKI_ERR_CERT_BAD_HASH
: Integrity error (hash code  incorrect)</li>
</ul>
<ul>
<li>PKI_ERR_CERT_BAD_CA
:Certification organism certificate invalid</li>
</ul>
<ul>
<li>PKI_ERR_CERT_ALGO_UNSUPPORTED
: Unsupported ciphering algorithm</li>
</ul>
<ul>
<li>PKI_ERR_CERT_NOT_FOUND
: User certificate not found</li>
</ul>
<ul>
<li>PKI_ERR_CA_NOT_FOUND
: Certification organism certificate not found</li>
</ul>
<ul>
<li>PKI_ERR_BAD_KEY
: Invalid ciphering key</li>
</ul>
<ul>
<li>PKI_ERR_BUF_TOO_SHORT
 : Memory buffer size too small</li>
</ul>
<ul>
<li>PKI_ERR_SYS
 : Internal error linked to the system (memory
allotment, system function, and so on)</li>
</ul>
<ul>
<li>PKI_ERR_PARM
: Ciphering parameter invalid</li>
</ul>
<ul>
<li>PKI_ERR_OTHERS
: Other error (authentication, ciphering, integrity,
and so on)</li>
</ul></td>
</tr>
<tr class="odd" data-valign="top">
<td width="20%"><p>Consequence</p></td>
<td width="80%"><p>The transfer is aborted.</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>Action</p></td>
<td width="80%"><p>Contact the product support team if necessary.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Information</p></td>
<td width="80%"><p><span id="CFTY19I"></span>CFTY19I PART=&amp;id SSL=&amp;id opening client session
CTX=&amp;ctx on task PID=&amp;pid</p>
<p>CFTY19I PART=&amp;id SSL=&amp;id opening client session
CTX=&amp;ctx on task PID=&amp;pid</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>Handshake
is started for a new client SSL session. <span>Transfer CFT</span> gives a unique reference
to it. Using this reference, the session could be tracked.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Information</p></td>
<td width="80%"><p><span id="CFTY20I"></span> CFTY20I PROT=&amp;id SSL=&amp;id opening server session
CTX=&amp;ctx on task PID=&amp;pid</p>
<p>CFTY20I PROT=&amp;id SSL=&amp;id opening server session
CTX=&amp;ctx on task PID=&amp;pid</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>Handshake
is started for a new server SSL session. <span>Transfer CFT</span> gives a unique reference
to it. Using this reference, the session could be tracked.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Information</p></td>
<td width="80%"><p><span id="CFTY21I"></span>CFTY21I CTX=&amp;ctx Remote server certificate accepted</p>
<p>CFTY21I CTX=&amp;ctx Remote server certificate accepted</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>A server certificate is accepted during a session handshake.
The authority identifier which has signed the certificate is displayed.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Information</p></td>
<td width="80%"><p><span id="CFTY22I"></span>CFTY22I CTX=&amp;ctx Remote client certificate accepted</p>
<p>CFTY22I CTX=&amp;ctx Remote client certificate accepted</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>A client certificate is accepted during a session handshake.
The authority identifier which has signed the certificate is displayed.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Information</p></td>
<td width="80%"><p><span id="CFTY23I"></span>CFTY23I CTX=&amp;ctx Client certificate ID=&amp;id ROOTID=&amp;id</p>
<p>CFTY23I CTX=&amp;ctx Client certificate ID=&amp;id ROOTID=&amp;id</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>Client certificate used locally for authentication.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Information</p></td>
<td width="80%"><p><span id="CFTY24I"></span>CFTY24I CTX=&amp;ctx Server certificate ID=&amp;id ROOTID=&amp;id</p>
<p>CFTY24I CTX=&amp;ctx Server certificate ID=&amp;id ROOTID=&amp;id</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>Server certificate used locally for authentication.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Information</p></td>
<td width="80%"><p><span id="CFTY25I"></span>CFTY25I CTX=&amp;ctx remote address HOST=&amp;string</p>
<p>CFTY25I CTX=&amp;ctx remote address HOST=&amp;string</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>This message is displayed after the message CFTY20I. It gives
the address (HOST name or IP address using TCP/IP network) of the remote
connected entity.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Information</p></td>
<td width="80%"><p><span id="CFTY26I"></span>CFTY26I CTX=&amp;ctx Anonymous &amp;str session</p>
<p>CFTY26I CTX=&amp;ctx Anonymous &amp;str session</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>Opening of a secure session without authentication in either
client or server mode. Refer to the <span>Transfer CFT</span> Online documentation.</p>
<ul>
<li>&amp;ctx= context SSL</li>
<li>str = client or server</li>
</ul></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Information</p></td>
<td width="80%"><p><span id="CFTY28W"></span>CFTY28W CTX=&amp;ctx &amp;str2 = &amp;filename</p>
<p>CFTY28W CTX=&amp;ctx &amp;str2 = &amp;filename</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>The file contains the remote certificate has not been recorded.</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="20%"><p>Consequence</p></td>
<td width="80%"><p>The transfer can be performed but the remote certificate is
not recorded.</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>Action</p></td>
<td width="80%"><p>Write
down the &amp;str2
value and contact the product support team if necessary.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Information</p></td>
<td width="80%"><p><span id="CFTY30E"></span>CFTY30E CTX=&amp;ctx SSL Handshake remote error [&amp;string] CR=&amp;cr</p>
<p>CFTY30E CTX=&amp;ctx SSL Handshake remote error [&amp;string] CR=&amp;cr</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%">SSL session handshake failure. An alert has been received from the remote peer.</td>
</tr>
<tr class="odd" data-valign="top">
<td width="20%"><p>Consequence</p></td>
<td width="80%">The SSL session in progress is aborted.</td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>Action</p></td>
<td width="80%">Analyze the &amp;cr error code (refer to the SSL protocol error codes). Also check the remote partner log for more details. Contact Axway support if necessary.</td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Information</p></td>
<td width="80%"><p><span id="CFTY41E"></span>CFTY41E CFTCTX=&lt;session_reference&gt;, xpp call &lt;PassportPS_API_function&gt;: error [&lt;PassportPS_API_function_returncode&gt;]</p>
<p>CFTY41E CFTCTX=&lt;session_reference&gt;, xpp call &lt;PassportPS_API_function&gt;: error [&lt;PassportPS_API_function_returncode&gt;]</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>An error occurred during an exchange or connection with the PassPort PS server.</p>
<p>&lt;PassportPS_API_function&gt; and &lt;PassportPS_API_function_returncode&gt; identify the function in error and provide the return code for the function.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Information</p></td>
<td width="80%"><span id="CFTY44E"></span>CFTY44E CFTCTX=&lt;session_reference&gt;, long err msg : [&lt;PassportPS_API_error_code&gt;]</td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>An error occurred during an exchange or connection with the PassPort PS server. The &lt;PassportPS_API_error_code&gt; describes the error.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0" width="90%">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Information</p></td>
<td width="80%"><span id="CFTY45E"></span>CFTY45E CFTCTX=&lt;session_reference&gt;, &lt;PassportPS_API_error_message&gt;</td>
</tr>
<tr class="even" data-valign="top">
<td width="20%"><p>Explanation</p></td>
<td width="80%"><p>An error occurred during an exchange or connection with the PassPort PS server. The &lt;PassportPS_API_error_message&gt; describes the error.</p></td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Information</p></td>
<td width="80%"><p><span id="CFTY50I"></span>CFTY50I SSH client session established CTX=&amp;ctx PART=&amp;part Version=&amp;version Cipher in=&amp;cipher Cipher out=&amp;cipher Key exchange=&amp;key hmac in=&amp;hmac hmac out=&amp;hmac &amp;IPVersion</p>
<p>CFTY50I SSH client session established CTX=&amp;ctx PART=&amp;part Version=&amp;version Cipher in=&amp;cipher Cipher out=&amp;cipher Key exchange=&amp;key hmac in=&amp;hmac hmac out=&amp;hmac</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%">Explanation</td>
<td width="80%">Established a new SSH client session.
&amp;version is SSH1 or SSH2.</td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Information</p></td>
<td width="80%"><p><span id="CFTY51I"></span>CFTY51I SSH server session established CTX=&amp;ctx PART=&amp;part Version=&amp;version Cipher in=&amp;cipher Cipher out=&amp;cipher Key exchange=&amp;key hmac in=&amp;hmac hmac out=&amp;hmac &amp;IPVersion</p>
<p>CFTY51I SSH server session established CTX=&amp;ctx PROT=&amp;prot Version=&amp;version Cipher in=&amp;cipher Cipher out=&amp;cipher Key exchange=&amp;key hmac in=&amp;hmac hmac out=&amp;hmac</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%">Explanation</td>
<td width="80%">Established a new SSH client session.
&amp;version is SSH1 or SSH2.</td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Information</p></td>
<td width="80%"><p><span id="CFTY52I"></span>CFTY52I SFTP client session established CTX=&amp;ctx PART=&amp;part Version=&amp;version Authentication=&amp;authentication CFT Server=&amp;server</p>
<p>CFTY52I SFTP client session established CTX=&amp;ctx PART=&amp;part Version=&amp;version Authentication=&amp;authentication CFT Server=&amp;server</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%">Explanation</td>
<td width="80%">Established a new SFTP client session.
&amp;version is the SFTP version negotiated with the partner (&gt;= 3).
&amp;Authentication is Key or Password.
&amp;server indicates if we are connected to a Transfer CFT server (Yes or No).</td>
</tr>
</tbody>
</table>

 

<table data-border="1" data-cellspacing="0">
<tbody>
<tr class="odd" data-valign="top">
<td width="20%"><p>V23 format</p>
<p>V24 format</p>
<p>Information</p></td>
<td width="80%"><p><span id="CFTY53I"></span>CFTY53I SFTP server session established CTX=&amp;ctx PROT=&amp;prot Version=&amp;version Authentication=&amp;authentication CFT Client=&amp;client</p>
<p>CFTY53I SFTP server session established CTX=&amp;ctx PROT=&amp;prot Version=&amp;version Authentication=&amp;authentication CFT Client=&amp;client</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="20%">Explanation</td>
<td width="80%"><p>Established a new SFTP server session.
&amp;version is the SFTP version negotiated with the partner (&gt;= 3).</p>
<ul>
<li>&amp;Authentication is Password, System, PassPortAM, Key or XFBADM.</li>
<li>&amp;client indicates if you are connected to a Transfer CFT client.</li>
</ul></td>
</tr>
</tbody>
</table>

 
