{
    "title": "CFTSSL configuration",
    "linkTitle": "CFTSSL configuration",
    "weight": "190"
}# <span id="CFTSSL_Command"></span>Transport security in CFTSSL

## <span id="Defining_a_transport_security_profile"></span>Defining a transport security profile

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

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The Transfer CFT CFTSSL object in client mode is a dynamic object. However, when set to server mode this object is static (you must restart Transfer CFT for the value to be taken into account).         </td>
      </tr>
</table>

### Client mode SSL

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr valign="top">
         <td width="23.88%">
            <p>Syntax</p>
         </td>
         <td colspan="2" rowspan="1">
<div>CFTSSL</div>
<div> ID 
 identifier,</div>
<div>     DIRECT =     
 CLIENT,</div>
<div>     [USERCID =     
 identifier,]</div>
<div>     CIPHLIST =     
 (num, num, ..),</div>
<div>     [ROOTCID =     
 (identifier, identifier,..),]</div>
<div>     [DEPTH =     
 {10 |num},]</div>
<div>     [VERSION =     
 {TLSV1 | SSLV3},]</div>
<div>     [PARM =     
 string,]</div>
<div>     [DNUSER =     
 (string, string,..),]</div>
<div>     [DNISSUER =     
 (string, string,..),]</div>
<div>     [CERFNAME =     
 string,]</div>
<div>     [MODE =     
 {REPLACE | CREATE | DELETE},]</div>
            <p>     [ORIGIN        = string,]</p>
            <p>     [TRACE         = num,]</p>
            <p>[VERIFY = { ENFORCED |  NONE (NOTE: SAME AS OPTIONAL | REQUIRED) }, ]</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="23.88%">
            <p>Description</p>
         </td>
         <td colspan="2" rowspan="1">
            <p>Use this command to describes a security profile.</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="15" width="23.88%">
            <p>Parameters</p>
         </td>
         <td>
            <p>[CERFNAME = string1..64]</p>
         </td>
         <td width="45.371%">
            <p>File name root in which the remote user chain of certificates 
 is recorded.</p>
            <p>If this parameter is set and the remote partner is authenticated, 
 the chain of certificates proposed by the partner is recorded in DER format 
 in the file, the root of which is composed of the CERFNAME parameter value 
 and the unique name set by CFT. The full name of the file can be accessed 
 via the &amp;SSLCFNAM symbolic variable or catalog query APIs. The file 
 is systematically deleted when the corresponding catalog entry is purged.</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1">
            <p>CIPHLIST = {(num, num, 
 ..)}</p>
         </td>
         <td colspan="1" rowspan="1" width="45.371%">
            <p>List of algorithms supported.</p>
            <p>Each value defines three algorithms:</p>
            <ul>
               <li>Authentication 
 algorithm               </li>
               <li>Encryption 
 algorithm               </li>
               <li>Sealing 
 algorithm               </li>
            </ul>
            <p>This list is submitted to the server which then makes its 
 selection, depending on the client's preference.</p>
<p data-mc-autonum=""><span><span></span></span><a name="Supported_suites"></a>Supported suites</p>
            <p>&amp;&amp;&amp; ïïï ùùù</p>
            <p>&amp;&amp;&amp; ïïï ùùù</p>
            <p>&amp;&amp;&amp; ïïï ùùù</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1">
            <p>[DEPTH = {10 | num}]</p>
         </td>
         <td colspan="1" rowspan="1" width="45.371%">
            <p>Maximum number of intermediate authorities authorized for 
 the remote certificate.</p>
            <p>This optional parameter has a numeric value between 0 and 
 10 (default value). 0 means that only self-signed certificates are accepted. 
 1 means that only certificates that are self-signed or signed by a recognized 
 root authority are accepted.</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1">
            <p>DIRECT = CLIENT</p>
         </td>
         <td colspan="1" rowspan="1" width="45.371%">
            <p>Security profile for the client mode.</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1">
            <p>[DNISSUER = string1..512]</p>
         </td>
         <td colspan="1" rowspan="1" width="45.371%">
            <p>List of values to be checked in the DN of the entity that directly issued the remote certificate.</p>
            <p>Strings are limited to 512 bytes each. A check is 
 performed as follows:</p>
            <ul>
               <li>dnuser='C=FR/O= 
 Axway/ OU=MFT Demonstration', means the remote certificate DN must contain this 
 string.               </li>
               <li>dnuser='C=UK,O=Axway' 
 means that the remote certificate must contain 'C=UK' string OR 'O=Axway' 
 string.                </li>
            </ul>
            <p>Note that the different attributes of the dnuser or dnissuer 
 string are separated by the '/' character.</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1">
            <p>[DNUSER = string1..512]</p>
         </td>
         <td colspan="1" rowspan="1" width="45.371%">
            <p>List of values to be checked in the remote certificate DN.</p>
            <p>Strings are limited to 512 bytes each. A check is 
 performed as follows:</p>
            <ul>
               <li>dnuser='C=FR/O= 
 Axway/ OU=MFT Demonstration', means the remote certificate DN must contain this 
 string.               </li>
               <li>dnuser='C=UK,O=Axway' 
 means that the remote certificate must contain 'C=UK' string OR 'O=Axway' 
 string.                </li>
            </ul>
            <p>Note that the different attributes of the dnuser or dnissuer 
 string are separated by the '/' character.</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1">
            <p>ID = identifier</p>
         </td>
         <td colspan="1" rowspan="1" width="45.371%">
            <p>Security profile identifier.</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1">
            <p>[MODE = {REPLACE 
 | CREATE | DELETE}]</p>
         </td>
         <td colspan="1" rowspan="1" width="45.371%">
            <p>Action for the command. For DELETE mode, the command is 
 deleted from the PARAMETERS database; only the ID and DIRECT parameters 
 are required.</p>
         </td>
      </tr>
      <tr valign="top">
         <td>[ORIGIN = string ]         </td>
         <td width="45.371%">This parameter indicates the origin of an object.          </td>
      </tr>
      <tr valign="top">
         <td>
            <p>PASSW</p>
            <p>string</p>
         </td>
         <td width="45.371%">
            <p>The parameter is the PassPort entity password for a user's certificate (the password that corresponds with the USERCID). This parameter enables PassPort connectivity.</p>
         </td>
      </tr>
      <tr valign="top">
         <td>[PARM = string1..64]         </td>
         <td width="45.371%">
            <p>Freeform parameter associated with the security profile.</p>
            <p>This local data item is not used by the SSL protocol. It 
 can be reused as a symbolic variable in an end of transfer procedure (&amp;SSLPARM). 
 It is also passed to the end of transfer, directory or file exits.</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1">
            <p>[ROOTCID = (identifier, 
 identifier, ...)]</p>
         </td>
         <td colspan="1" rowspan="1" width="45.371%">
            <p>List of certificate authorities. This list can reference a maximum of 10 identifiers  in the local certificate database.</p>
            <p>In client mode, this list is used to check the server 
 certificate. Only certificates signed by one of the authorities in the 
 ROOTCID parameter are accepted.</p>
            <p>&amp;&amp;&amp; ïïï ùùù</p>
         </td>
      </tr>
      <tr valign="top">
         <td>[TRACE = number ]         </td>
         <td width="45.371%">SSL trace level.         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1">
            <p>[USERCID = identifier]</p>
         </td>
         <td colspan="1" rowspan="1" width="45.371%">
            <p>Local user certificate. Within the context of the Transfer 
 CFT integrated PKI, this identifier 
 refers to the identifier of a user certificate in the database.</p>
            <p>This parameter is used to select a user certificate for 
 authentication by the server (if requested by the server). The first user 
 certificate found (signed by one of the authorities proposed by the server) 
 is used.</p>
            <p>The &amp;USERID and &amp;PART symbolic variables are accepted.<br/>These variables are then substituted with the name of the transfer owner 
 (refer to the CFTAPPL, CFTSEND and CFTRECV commands) and the local identifier 
 of the transfer partner respectively.</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1">
            <p>[VERSION = {TLSV1 | SSLV3 | TLSV1COMP | SSLV3COMP}]</p>
         </td>
         <td colspan="1" rowspan="1" width="45.371%">
            <p>Session version.</p>
            <p>Transfer CFT supports:</p>
            <ul>
               <li> TLS version 1.2, 1.1, 1.0 (TLSV1 | TLSV1COMP keyword)               </li>
               <li>SSL version 3.0 (SSLV3 | SSLV3COMP keyword)               </li>
            </ul>
            <p><strong>About sessions</strong>
</p>
            <p>In Transfer CFT, the SSL/TLS session version is proposed by the client and negotiated with the server. </p>
            <p><strong>Client mode</strong>
</p>
            <p>DIRECT=CLIENT</p>
            <p>In client mode, TLSV1COMP or SSLV3COMP sets the header length in the NSDU to enable compatibility with other products.</p>
            <p><strong>Server mode</strong>
</p>
            <p>DIRECT=SERVER</p>
            <p>In server mode, the header length is automatically detected for all SSL versions (SSLV3, TLSV1, SSLV3COMP, TLSV1COMP).</p>
            <p>Limitation: The header length policy in the protocol header is only available for the PeSIT (ANY) protocol.</p>
         </td>
      </tr>
      <tr valign="top">
         <td>          </td>
         <td>VERIFY         </td>
         <td width="45.371%">
            <p>Sets the authentication mode requirement.</p>
            <ul>
               <li>ENFORCED:  Ensures client  authentication with the server. The transfer fails if the server does not ask for the client certificate during the handshake.               </li>
               <li>OPTIONAL and REQUIRED: The same as NONE (enabling backward compatibility), but should not be used.               </li>
               <li>NONE: No authentication required.               </li>
            </ul>
         </td>
      </tr>
</table>

### Server mode

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p>Suite </p>
</th>
         <th>
            <p>Order used</p>
</th>
         <th>
            <p>Authentication </p>
</th>
         <th>
            <p>Confidentiality </p>
</th>
         <th>
            <p>Integrity </p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr valign="middle">
         <td valign="top" width="9%">49199 **         </td>
         <td>1         </td>
         <td valign="top">ECDHE + RSA authentication         </td>
         <td valign="top" width="20%">AES-128 GCM         </td>
         <td valign="top" width="27%">SHA-256         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="9%">49200 **         </td>
         <td>2         </td>
         <td valign="top">ECDHE + RSA authentication         </td>
         <td valign="top" width="20%">AES-256 GCM         </td>
         <td valign="top" width="27%">SHA-384         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="9%">49191 **         </td>
         <td>3         </td>
         <td valign="top">
<p valign="top">
            <p>ECDHE + RSA authentication</p>
</p>
         </td>
         <td valign="top" width="20%">AES-128         </td>
         <td valign="top" width="27%">SHA-256         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="9%">49192**         </td>
         <td>4         </td>
         <td valign="top">ECDHE + RSA authentication         </td>
         <td valign="top" width="20%">AES-256         </td>
         <td valign="top" width="27%">SHA-384         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="9%">156 **         </td>
         <td>5         </td>
         <td valign="top">RSA authentication          </td>
         <td valign="top" width="20%">AES 128 GCM         </td>
         <td valign="top" width="27%">SHA-256         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="9%">157 **         </td>
         <td>6         </td>
         <td valign="top">RSA authentication          </td>
         <td valign="top" width="20%">AES 256 GCM         </td>
         <td valign="top" width="27%">SHA-384         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="9%">60* 
         </td>
         <td>7         </td>
         <td valign="top">RSA authentication (512, 1024, 2048, or 4096)         </td>
         <td valign="top" width="20%">AES-128         </td>
         <td valign="top" width="27%">SHA-256         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="9%">61*         </td>
         <td>8         </td>
         <td valign="top">RSA authentication (512, 1024, 2048, or 4096)         </td>
         <td valign="top" width="20%">AES-256 
         </td>
         <td valign="top" width="27%">SHA-256         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="9%">47
                                 </td>
         <td>9         </td>
         <td valign="top">RSA authentication (512, 1024, 2048, or 4096) 
                                 </td>
         <td valign="top" width="20%">AES-128
                                 </td>
         <td valign="top" width="27%">SHA-1
                                 </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="9%">53 
         </td>
         <td>10         </td>
         <td valign="top">RSA authentication (512, 1024, 2048, or 4096)         </td>
         <td valign="top" width="20%">AES-256         </td>
         <td valign="top" width="27%">SHA-1 
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="9%">10
                                 </td>
         <td>11         </td>
         <td valign="top">RSA authentication (512, 1024, 2048, or 4096) 
                                 </td>
         <td valign="top" width="20%">Triple DES
                                 </td>
         <td valign="top" width="27%">SHA-1
                                 </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="9%">5
                                 </td>
         <td>12         </td>
         <td valign="top">RSA authentication (512, 1024, 2048, or 4096) 
                                 </td>
         <td valign="top" width="20%">RC4
                                 </td>
         <td valign="top" width="27%">SHA-1
                                 </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="9%">4
                                 </td>
         <td>13         </td>
         <td valign="top">RSA authentication (512, 1024, 2048, or 4096) 
                                 </td>
         <td valign="top" width="20%">RC4
                                 </td>
         <td valign="top" width="27%">MD5
                                 </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="9%">59* 
         </td>
         <td>14         </td>
         <td valign="top">RSA authentication (512, 1024, 2048, or 4096)         </td>
         <td valign="top" width="20%">None         </td>
         <td valign="top" width="27%">SHA-256         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="9%">2
                                 </td>
         <td>15         </td>
         <td valign="top">RSA authentication (512, 1024, 2048, or 4096) 
                                 </td>
         <td valign="top" width="20%">None
                                 </td>
         <td valign="top" width="27%">SHA-1
                                 </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="9%">1
                                 </td>
         <td>16         </td>
         <td valign="top">RSA authentication (512, 1024, 2048, or 4096) 
                                 </td>
         <td valign="top" width="20%">None
                                 </td>
         <td valign="top" width="27%">MD5
                                 </td>
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