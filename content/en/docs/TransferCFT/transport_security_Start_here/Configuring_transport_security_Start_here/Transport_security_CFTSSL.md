{
    "title": "Transport  security in CFTSSL ",
    "linkTitle": "CFTSSL configuration",
    "weight": "180"
}<span id="Defining_a_transport_security_profile"></span>

## Defining a transport security profile

Transfer CFT opens an SSL session in client mode for any secure file
or message transfer in requester mode. Transfer CFT opens an SSL session
in server mode for any incoming call requiring a secure protocol.

The properties of each SSL session opened by Transfer CFT in both client
and server modes are determined by a security profile.

A security profile monitors the:

-   Required authentication
    mode: simple (server only) or mutual (server and client) authentication
-   Authentication,
    encryption and sealing algorithms to be used
-   Certificate to
    be sent for local authentication and the RSA authentication algorithm
-   Checks to be performed
    on the remote certificate for remote authentication and the RSA authentication
    algorithm

The CFTSSL command describes a security
profile. The DIRECT parameter indicates the mode to which the security
profile applies: DIRECT=CLIENT for client mode or DIRECT=SERVER for server
mode.

> **Note:**
>
> The Transfer CFT CFTSSL object in client mode is a dynamic object. However, when set to server mode this object is static (you must restart Transfer CFT for the value to be taken into account).

### Client mode SSL

<table>
   <tbody>
      <tr>
         <td><p>Syntax</p>         </td>
         <td><div class="code">
CFTSSL
</div>
<div class="code">
ID
identifier,
</div>
<div class="code">
     DIRECT =    
CLIENT,
</div>
<div class="code">
     [USERCID =    
identifier,]
</div>
<div class="code">
     CIPHLIST =    
(num, num, ..),
</div>
<div class="code">
     [ROOTCID =    
(identifier, identifier,..),]
</div>
<div class="code">
     [DEPTH =    
{10 |num},]
</div>
<div class="code">
     [VERSION =    
{TLSV1 | SSLV3},]
</div>
<div class="code">
     [PARM =    
string,]
</div>
<div class="code">
     [DNUSER =    
(string, string,..),]
</div>
<div class="code">
     [DNISSUER =    
(string, string,..),]
</div>
<div class="code">
     [CERFNAME =    
string,]
</div>
<div class="code">
     [MODE =    
{REPLACE | CREATE | DELETE},]
</div>
<p>     [ORIGIN        = string,]</p>
<p>     [TRACE         = num,]</p>
<p>[VERIFY = { ENFORCED | NONE (NOTE: SAME AS OPTIONAL | REQUIRED) }, ]</p>         </td>
      </tr>
      <tr>
         <td><p>Description</p>         </td>
         <td><p>Use this command to describes a security profile.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>[CERFNAME = string1..64]</p>         </td>
         <td><p>File name root in which the remote user chain of certificates
is recorded.</p>
<p>If this parameter is set and the remote partner is authenticated,
the chain of certificates proposed by the partner is recorded in DER format
in the file, the root of which is composed of the CERFNAME parameter value
and the unique name set by CFT. The full name of the file can be accessed
via the &amp;SSLCFNAM symbolic variable or catalog query APIs. The file
is systematically deleted when the corresponding catalog entry is purged.</p>         </td>
      </tr>
      <tr>
         <td><p>CIPHLIST = {(num, num,
..)}</p>         </td>
         <td><p>List of algorithms supported.</p>
<p>Each value defines three algorithms:</p>
<ul>
<li>Authentication
algorithm</li>
<li>Encryption
algorithm</li>
<li>Sealing
algorithm</li>
</ul>
<p>This list is submitted to the server which then makes its
selection, depending on the client's preference.</p>
<p><span class="autonumber"><span></span></span><span id="Supported_suites"></span>Supported suites</p>
<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Suite </p>         </th>
<th style="text-align: center;" class="HeadE-Column1-Header1"><p>Order used</p>         </th>
<th class="HeadE-Column1-Header1"><p>Authentication </p>         </th>
<th class="HeadE-Column1-Header1"><p>Confidentiality </p>         </th>
<th class="HeadD-Column1-Header1"><p>Integrity </p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>49199 **         </td>
         <td>1         </td>
         <td>ECDHE + RSA authentication         </td>
         <td>AES-128 GCM         </td>
         <td>SHA-256         </td>
      </tr>
      <tr>
         <td>49200 **         </td>
         <td>2         </td>
         <td>ECDHE + RSA authentication         </td>
         <td>AES-256 GCM         </td>
         <td>SHA-384         </td>
      </tr>
      <tr>
         <td>49191 **         </td>
         <td>3         </td>
         <td><p>ECDHE + RSA authentication</p>         </td>
         <td>AES-128         </td>
         <td>SHA-256         </td>
      </tr>
      <tr>
         <td>49192**         </td>
         <td>4         </td>
         <td>ECDHE + RSA authentication         </td>
         <td>AES-256         </td>
         <td>SHA-384         </td>
      </tr>
      <tr>
         <td>156 **         </td>
         <td>5         </td>
         <td>RSA authentication         </td>
         <td>AES 128 GCM         </td>
         <td>SHA-256         </td>
      </tr>
      <tr>
         <td>157 **         </td>
         <td>6         </td>
         <td>RSA authentication         </td>
         <td>AES 256 GCM         </td>
         <td>SHA-384         </td>
      </tr>
      <tr>
         <td>60*         </td>
         <td>7         </td>
         <td>RSA authentication (512, 1024, 2048, or 4096)         </td>
         <td>AES-128         </td>
         <td>SHA-256         </td>
      </tr>
      <tr>
         <td>61*         </td>
         <td>8         </td>
         <td>RSA authentication (512, 1024, 2048, or 4096)         </td>
         <td>AES-256         </td>
         <td>SHA-256         </td>
      </tr>
      <tr>
         <td>47         </td>
         <td>9         </td>
         <td>RSA authentication (512, 1024, 2048, or 4096)         </td>
         <td>AES-128         </td>
         <td>SHA-1         </td>
      </tr>
      <tr>
         <td>53         </td>
         <td>10         </td>
         <td>RSA authentication (512, 1024, 2048, or 4096)         </td>
         <td>AES-256         </td>
         <td>SHA-1         </td>
      </tr>
      <tr>
         <td>10         </td>
         <td>11         </td>
         <td>RSA authentication (512, 1024, 2048, or 4096)         </td>
         <td>Triple DES         </td>
         <td>SHA-1         </td>
      </tr>
      <tr>
         <td>5         </td>
         <td>12         </td>
         <td>RSA authentication (512, 1024, 2048, or 4096)         </td>
         <td>RC4         </td>
         <td>SHA-1         </td>
      </tr>
      <tr>
         <td>4         </td>
         <td>13         </td>
         <td>RSA authentication (512, 1024, 2048, or 4096)         </td>
         <td>RC4         </td>
         <td>MD5         </td>
      </tr>
      <tr>
         <td>59*         </td>
         <td>14         </td>
         <td>RSA authentication (512, 1024, 2048, or 4096)         </td>
         <td>None         </td>
         <td>SHA-256         </td>
      </tr>
      <tr>
         <td>2         </td>
         <td>15         </td>
         <td>RSA authentication (512, 1024, 2048, or 4096)         </td>
         <td>None         </td>
         <td>SHA-1         </td>
      </tr>
      <tr>
         <td>1         </td>
         <td>16         </td>
         <td>RSA authentication (512, 1024, 2048, or 4096)          </td>
         <td>None         </td>
         <td>MD5         </td>
      </tr>
   </tbody>
</table>
<blockquote>
<p><strong>Note:</strong></p>
<p>* To comply with security standards, as of Transfer CFT version 3.2.0 the use of the cipher suites 59, 60, and 61 is restricted to TLS 1.2 exclusively. This means that you cannot negotiate a session with another partner (monitor) that is using a TLS version lower than 1.2 with these cipher suites.</p>
</blockquote>
<blockquote>
<p><strong>Note:</strong></p>
<p>** These cipher suites are only available for Transfer CFT 3.2.2 and higher and are restricted to use with TLS 1.2.</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td><p>[DEPTH = {10 | num}]</p>         </td>
         <td><p>Maximum number of intermediate authorities authorized for
the remote certificate.</p>
<p>This optional parameter has a numeric value between 0 and
10 (default value). 0 means that only self-signed certificates are accepted.
1 means that only certificates that are self-signed or signed by a recognized
root authority are accepted.</p>         </td>
      </tr>
      <tr>
         <td><p>DIRECT = CLIENT</p>         </td>
         <td><p>Security profile for the client mode.</p>         </td>
      </tr>
      <tr>
         <td><p>[DNISSUER = string1..512]</p>         </td>
         <td><p>List of values to be checked in the DN of the entity that directly issued the remote certificate.</p>
<p>Strings are limited to 512 bytes each. A check is
performed as follows:</p>
<ul>
<li>dnuser='C=FR/O=
Axway/ OU=MFT Demonstration', means the remote certificate DN must contain this
string.</li>
<li>dnuser='C=UK,O=Axway'
means that the remote certificate must contain 'C=UK' string OR 'O=Axway'
string.</li>
</ul>
<p>Note that the different attributes of the dnuser or dnissuer
string are separated by the '/' character.</p>         </td>
      </tr>
      <tr>
         <td><p>[DNUSER = string1..512]</p>         </td>
         <td><p>List of values to be checked in the remote certificate DN.</p>
<p>Strings are limited to 512 bytes each. A check is
performed as follows:</p>
<ul>
<li>dnuser='C=FR/O=
Axway/ OU=MFT Demonstration', means the remote certificate DN must contain this
string.</li>
<li>dnuser='C=UK,O=Axway'
means that the remote certificate must contain 'C=UK' string OR 'O=Axway'
string.</li>
</ul>
<p>Note that the different attributes of the dnuser or dnissuer
string are separated by the '/' character.</p>         </td>
      </tr>
      <tr>
         <td><p>ID = identifier</p>         </td>
         <td><p>Security profile identifier.</p>         </td>
      </tr>
      <tr>
         <td><p>[MODE = {REPLACE
| CREATE | DELETE}]</p>         </td>
         <td><p>Action for the command. For DELETE mode, the command is
deleted from the PARAMETERS database; only the ID and DIRECT parameters
are required.</p>         </td>
      </tr>
      <tr>
         <td>[ORIGIN = string ]         </td>
         <td>This parameter indicates the origin of an object.         </td>
      </tr>
      <tr>
         <td><p>PASSW</p>
<p>string</p>         </td>
         <td><p>The parameter is the PassPort entity password for a user's certificate (the password that corresponds with the USERCID). This parameter enables PassPort connectivity.</p>         </td>
      </tr>
      <tr>
         <td>[PARM = string1..64]         </td>
         <td><p>Freeform parameter associated with the security profile.</p>
<p>This local data item is not used by the SSL protocol. It
can be reused as a symbolic variable in an end of transfer procedure (&amp;SSLPARM).
It is also passed to the end of transfer, directory or file exits.</p>         </td>
      </tr>
      <tr>
         <td><p>[ROOTCID = (identifier,
identifier, ...)]</p>         </td>
         <td><p>List of certificate authorities. This list can reference a maximum of 10 identifiers in the local certificate database.</p>
<p>In client mode, this list is used to check the server
certificate. Only certificates signed by one of the authorities in the
ROOTCID parameter are accepted.</p>
<blockquote>
<p><strong>Note:</strong></p>
<p>To use more than 10 identifiers, you can refer to the PKIENTITY information.</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td>[TRACE = number ]         </td>
         <td>SSL trace level.         </td>
      </tr>
      <tr>
         <td><p>[USERCID = identifier]</p>         </td>
         <td><p>Local user certificate. Within the context of the Transfer
CFT integrated PKI, this identifier
refers to the identifier of a user certificate in the database.</p>
<p>This parameter is used to select a user certificate for
authentication by the server (if requested by the server). The first user
certificate found (signed by one of the authorities proposed by the server)
is used.</p>
<p>The &amp;USERID and &amp;PART symbolic variables are accepted.<br />
These variables are then substituted with the name of the transfer owner
(refer to the CFTAPPL, CFTSEND and CFTRECV commands) and the local identifier
of the transfer partner respectively.</p>         </td>
      </tr>
      <tr>
         <td><p>[VERSION = {TLSV1 | SSLV3 | TLSV1COMP | SSLV3COMP}]</p>         </td>
         <td><p>Session version.</p>
<p>Transfer CFT supports:</p>
<ul>
<li>TLS version 1.2, 1.1, 1.0 (TLSV1 | TLSV1COMP keyword)</li>
<li>SSL version 3.0 (SSLV3 | SSLV3COMP keyword)</li>
</ul>
<p><strong>About sessions</strong></p>
<p>In Transfer CFT, the SSL/TLS session version is proposed by the client and negotiated with the server.</p>
<p><strong>Client mode</strong></p>
<p>DIRECT=CLIENT</p>
<p>In client mode, TLSV1COMP or SSLV3COMP sets the header length in the NSDU to enable compatibility with other products.</p>
<p><strong>Server mode</strong></p>
<p>DIRECT=SERVER</p>
<p>In server mode, the header length is automatically detected for all SSL versions (SSLV3, TLSV1, SSLV3COMP, TLSV1COMP).</p>
<p>Limitation: The header length policy in the protocol header is only available for the PeSIT (ANY) protocol.</p>         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>VERIFY         </td>
         <td><p>Sets the authentication mode requirement.</p>
<ul>
<li>ENFORCED: Ensures client authentication with the server. The transfer fails if the server does not ask for the client certificate during the handshake.</li>
<li>OPTIONAL and REQUIRED: The same as NONE (enabling backward compatibility), but should not be used.</li>
<li>NONE: No authentication required.</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

### Server mode

<table>
   <tbody>
      <tr>
         <td><p>Syntax</p>         </td>
         <td><p><code>CFTSSL</code><br />
<code>     ID                 =     identifier,</code><br />
<code>     DIRECT          =       SERVER,</code><br />
<code>     [USERCID          =       identifier,]</code><br />
<code>     CIPHLIST          =       (num, num, ..),</code><br />
<code>     [VERIFY          =       { REQUIRED | OPTIONAL | NONE},]</code></p>
<p><code>     [ROOTCID          =       (identifier, identifier,..),]</code><br />
<code>     [DEPTH          =       {10,num},]</code><br />
<code>     [VERSION          =       {TLSV1 | SSLV3},]</code><br />
<code>     [PARM          =       string,]</code></p>
<p>      [ORIGIN        =     string,]</p>
<p>      [TRACE         =     num,]<br />
<code>     [DNUSER          =       (string, string,..),]</code><br />
<code>     [DNISSUER     =       (string, string,..),]</code><br />
<code>     [CERFNAME     =       string,]</code><br />
<code>     [MODE          =       {REPLACE | CREATE | DELETE},]</code></p>         </td>
      </tr>
      <tr>
         <td><p>Description</p>         </td>
         <td><p>Use this command to describes a security profile.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>ID = identifier</p>         </td>
         <td><p>Identifier of the security profile.</p>         </td>
      </tr>
      <tr>
         <td><p>[CERFNAME = string1..64]</p>         </td>
         <td><p>File name root used to record the remote user chain of
certificates.</p>
<p>If this parameter is set and the remote partner is authenticated,
the chain of certificates proposed by the partner is recorded in DER format
in a file, the root of which comprises the CERFNAME parameter value and
the unique name set by Transfer CFT. The full name of the file can be
accessed via the &amp;SSLCFNAM symbolic variable or catalog query APIs.
The file is systematically deleted when the corresponding catalog entry
is purged.</p>         </td>
      </tr>
      <tr>
         <td><p>CIPHLIST = {(num, num,
..)}</p>         </td>
         <td><p>List of the algorithms supported.</p>
<p>Each value defines three algorithms:</p>
<ul>
<li>Authentication
algorithm</li>
<li>Encryption
algorithm</li>
<li>Sealing
algorithm</li>
</ul>
<p>This list is compared with the list proposed by the client
in order of preference, for the purpose of determining the suite to be
negotiated.</p>         </td>
      </tr>
      <tr>
         <td><p>[DEPTH = {10
| num}]</p>         </td>
         <td><p>Maximum number of intermediate authorities authorized for
the remote certificate.</p>
<p>This optional parameter has a numerical value between 0
and 10, the default value. 0 signifies that only self-signed certificates
are accepted. 1 signifies that only certificates that are self-signed
or signed by a recognized root authority are accepted.</p>         </td>
      </tr>
      <tr>
         <td><p>DIRECT = SERVER</p>         </td>
         <td><p>The security profile is applicable in the server mode.</p>         </td>
      </tr>
      <tr>
         <td><p>[DNISSUER = string1...512]</p>         </td>
         <td><p>Strings that are limited to 512 bytes each. A check is
performed as follows:</p>
<ul>
<li>dnuser='C=FR/O=
Axway/ OU=MFT Demonstration', means the remote certificate DN must contain this
string.</li>
<li>dnuser='C=UK,O=Axway'
means that the remote certificate must contain 'C=UK' string OR 'O=Axway'
string.</li>
</ul>
<p>Note that the different attributes of the dnuser or dnissuer
string are separated by the '/' character.</p>         </td>
      </tr>
      <tr>
         <td><p>[DNUSER = string1..512]</p>         </td>
         <td><p>Strings that are limited to 512 bytes each. A check is
performed as follows:</p>
<ul>
<li>dnuser='C=FR/O=
Axway/ OU=MFT Demonstration', means the remote certificate DN must contain this
string.</li>
<li>dnuser='C=UK,O=Axway'
means that the remote certificate must contain 'C=UK' string OR 'O=Axway'
string.</li>
</ul>
<p>Note that the different attributes of the dnuser or dnissuer
string are separated by the '/' character.</p>         </td>
      </tr>
      <tr>
         <td><p>[MODE = {REPLACE |
CREATE | DELETE}]</p>         </td>
         <td><p>Action for the command. For DELETE mode, the command is
deleted from the PARAMETERS database; only the ID and DIRECT parameters
are required.</p>         </td>
      </tr>
      <tr>
         <td>[ORIGIN = string ]         </td>
         <td>This parameter indicates the origin of an object.         </td>
      </tr>
      <tr>
         <td><p>[PARM = string1..64]</p>         </td>
         <td><p>Freeform parameter associated with the security profile.</p>
<p>This local data item is not used by the SSL protocol. It
can be reused as a symbolic variable in an end of transfer procedure (&amp;SSLPARM).
It is also passed to the end of transfer, directory or file exits.</p>         </td>
      </tr>
      <tr>
         <td><p>[ROOTCID = (identifier,
identifier, ...)]</p>         </td>
         <td><p>List of the certificate authorities. This list references
identifiers in the local certificate database.</p>
<p>This list has two functions:</p>
<ul>
<li>A user
certificate can be chosen for authentication by the client</li>
<li>If the
client must be authenticated, the list of authority DNs supported by the
server is supplied</li>
</ul>
<blockquote>
<p><strong>Note:</strong></p>
<p>To use more than 10 identifiers, refer to the PKIENTITY information.</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td>[TRACE = number ]         </td>
         <td>SSL trace level.         </td>
      </tr>
      <tr>
         <td><p>[USERCID = identifier]</p>         </td>
         <td><p>Reference of a user certificate in the local certificate
database. The purpose of this identifier is to select a user certificate
for authentication by the client.</p>
<p>If the server
requires client authentication, it provides the client with the list of
authority DNs supported during the SSL protocol negotiation phase.</p>
<blockquote>
<p><strong>Note:</strong></p>
<p>This parameter
is ignored when the CFTSSL command is used for additional controls in
the server mode (CFTSSL command indicated by a CFTPART command).</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td><p>VERIFY = {REQUIRED
| OPTIONAL | NONE}</p>         </td>
         <td><p>Sets the authentication mode requirement.</p>
<p>The VERIFY and USERCID parameters set the security profile
authentication mode.</p>
<blockquote>
<p><strong>Note:</strong></p>
<p>With the SSL
protocol, the server determines whether the client must be authenticated.
If the server wants the client to be authenticated, then the server must
first be authenticated by the client. Due to the algorithms supported
by Transfer CFT (refer to the CIPHLIST parameter), the server must currently
be authenticated by an X.509 certificate.</p>
</blockquote>
<p>The following list describes the possible cases for a security
profile in server mode (the USERCID parameter is mandatory for
a server CFTSSL command).</p>
<ul>
<li>REQUIRED: The server and the client must be authenticated. (Default)</li>
<li>OPTIONAL: The server and the client must be authenticated. An invalid
certificate is tolerated by the server. </li>
<li>NONE : Only the server must be authenticated. </li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>[VERSION = {TLSV1 | SSLV3 | TLSV1COMP | SSLV3COMP}]</p>         </td>
         <td><p>SSL session version.</p>
<p>Client mode</p>
<p>In Client mode (DIRECT=CLIENT), TLSV1COMP or SSLV3COMP set the header length in NSDU to enable compatibility with other products.</p>
<p>Server mode</p>
<p>In server mode (DIRECT=SERVER) the header length is automatically detected for all SSL versions (SSLV3, TLSV1, SSLV3COMP, TLSV1COMP).</p>
<p>Limitation: The header length policy in the protocol header is only available for the PeSIT (ANY) protocol.</p>         </td>
      </tr>
   </tbody>
</table>

### Associate the security profile with the CFTPROT object

The SSL parameter is used to associate a security profile with a protocol
definition.

-   For a security profile related to incoming calls (server mode), the
    SSL parameter value must correspond to the identifier of a DIRECT=SERVER
    SSL command.
-   For a default security profile related to outgoing calls (client mode),
    the SSL parameter value must correspond to the identifier of a DIRECT=CLIENT
    SSL command.

If you do not define the CFTPROT SAP parameter when using the SSL protocol,
then the server mode for CFTSSL is not mandatory.

Related topics

-   [CFTPROT](../../../admin_intro/admin_config_commands/transfer_protocol_concepts)
