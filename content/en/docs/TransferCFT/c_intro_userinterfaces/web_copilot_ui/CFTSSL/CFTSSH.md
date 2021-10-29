{
    "title": "CFTSSH - Security profile",
    "linkTitle": "SSH Security Profiles - CFTSSH",
    "weight": "210"
}Use the CFTSSH command to describe a security profile.

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">When using the SFTP protocol, the CFTSSH definition contains the SSH connection parameters for server or client mode.         </td>
      </tr>
   </tbody>
</table>

## Server

The CFTSSH object parameters for a server definition (DIRECT = SERVER).

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>Parameter</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="28.19%">            <p>ID = identifier</p>         </td>
         <td width="47.156%">            <p>Identifier of the security profile.</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="28.19%">            <p>CIPHLIST = {(num, num,
..)}</p>         </td>
         <td width="47.156%">            <p>List of allowed ciphers (encryption methods).</p>
            <p>Each value defines three algorithms:</p>
            <ul>
               <li>Authentication
algorithm               </li>
               <li>Encryption
algorithm               </li>
               <li>Sealing
algorithm               </li>
            </ul>
            <p>This list is compared with the list proposed by the client
in order of preference, for the purpose of determining the suite to be
negotiated.</p>
            <p><span>Transfer CFT</span> supports the following: aes256-ctr, aes192-ctr, aes128-ctr, aes256-cbc, aes192-cbc, aes128-cbc, 3des-cbc, blowfish-cbc.</p>
<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note  </strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note  &lt;/b&gt;" data-valign="top"><br />
If the field is empty, the default list is: aes256-ctr, aes192-ctr, aes128-ctr, aes256-cbc, aes192-cbc, aes128-cbc.         </td>
      </tr>
   </tbody>
</table>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="28.19%">CLIPUBKEY         </td>
         <td width="47.156%">            <p>When DIRECT=SERVER</p>
            <p>Key Id containing the client public key (RSA). When defined, the Transfer CFT server checks that the client public key referenced in CLIPUBKEY matches the public key provided by the client. If an error occurs, the connection is rejected with a DIAGI 433.</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="28.19%">Comment         </td>
         <td width="47.156%">Free comment.         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="28.19%">            <p>DIRECT</p>
            <p> </p>         </td>
         <td width="47.156%">            <p>The security profile is applicable in this mode (SERVER).</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="28.19%">HMAC         </td>
         <td width="47.156%">            <p>List of accepted HMAC (keyed-hash message authentication code).</p>
            <ul>
               <li>Choose from the following: hmac-sha2-512, hmac-sha2-256, hmac-sha1, none.<br />
               </li>
               <li>If the field is empty, the default list is hmac-sha2-512, hmac-sha2-256, hmac-sha1.               </li>
            </ul>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="28.19%">KEYEXCHG         </td>
         <td width="47.156%">            <p>List of key exchange methods to use.</p>
            <p>Choose from the following: curve25519-sha256@libssh.org, ecdh-sha2-nistp256, diffie-hellman-group14-sha1, diffie-hellman-group1-sha1.</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="28.19%">            <p>MODE = {REPLACE |
CREATE | DELETE}</p>         </td>
         <td width="47.156%">            <p>Action for the command. For DELETE mode, the command is
deleted from the PARAMETERS database; only the ID and DIRECT parameters
are required.</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="28.19%">ORIGIN = string         </td>
         <td width="47.156%">This parameter indicates the object's origin.         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="28.19%">SRVPRIVKEY         </td>
         <td width="47.156%">            <p>When DIRECT=SERVER:</p>
            <p>Key Id containing the server private key (RSA) to use with key authentication.</p>         </td>
      </tr>
   </tbody>
</table>

## Client

The CFTSSH object parameters for a client definition (DIRECT = CLIENT).

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>Parameter</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="28.19%">            <p>ID = identifier</p>         </td>
         <td width="47.156%">            <p>Identifier of the security profile.</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="28.19%">            <p>CIPHLIST = {(num, num,
..)}</p>         </td>
         <td width="47.156%">            <p>List of allowed ciphers (encryption methods).</p>
            <p>Each value defines three algorithms:</p>
            <ul>
               <li>Authentication
algorithm               </li>
               <li>Encryption
algorithm               </li>
               <li>Sealing
algorithm               </li>
            </ul>
            <p>This list is compared with the list proposed by the client
in order of preference, for the purpose of determining the suite to be
negotiated.</p>
            <p><span>Transfer CFT</span> supports the following: aes256-ctr, aes192-ctr, aes128-ctr, aes256-cbc, aes192-cbc, aes128-cbc, 3des-cbc, blowfish-cbc.</p>
<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note  </strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note  &lt;/b&gt;" data-valign="top"><br />
If the field is empty, the default list is: aes256-ctr, aes192-ctr, aes128-ctr, aes256-cbc, aes192-cbc, aes128-cbc.         </td>
      </tr>
   </tbody>
</table>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="28.19%">CLIPRIVKEY         </td>
         <td width="47.156%">When DIRECT=CLIENT
Key Id containing the client private key (RSA) to use with key authentication. When defined, Transfer CFT uses key authentication. If an error occurs, the connection is rejected with a DIAGI 433.         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="28.19%">Comment         </td>
         <td width="47.156%">Free comment.         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="28.19%">            <p>DIRECT</p>         </td>
         <td width="47.156%">            <p>The security profile is applicable in this mode (CLIENT).</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="28.19%">HMAC         </td>
         <td width="47.156%">            <p>List of accepted HMAC (keyed-hash message authentication code).</p>
            <ul>
               <li>Choose from the following: hmac-sha2-512, hmac-sha2-256, hmac-sha1, none.<br />
               </li>
               <li>If the field is empty, the default list is hmac-sha2-512, hmac-sha2-256, hmac-sha1.               </li>
            </ul>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="28.19%">KEYEXCHG         </td>
         <td width="47.156%">List of key exchange methods to use. Choose from the following: curve25519-sha256@libssh.org, ecdh-sha2-nistp256, diffie-hellman-group14-sha1, diffie-hellman-group1-sha1.         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="28.19%">            <p>MODE = {REPLACE |
CREATE | DELETE}</p>         </td>
         <td width="47.156%">            <p>Action for the command. For DELETE mode, the command is
deleted from the PARAMETERS database; only the ID and DIRECT parameters
are required.</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="28.19%">ORIGIN = string         </td>
         <td width="47.156%">This parameter indicates the object's origin.         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="28.19%">SRVPUBKEY         </td>
         <td width="47.156%">            <p>When DIRECT=CLIENT:</p>
            <p>Key Id containing the server public key (RSA) for the server. When defined, the Transfer CFT client checks that the public key referenced by SRVPUBKEY matches the key provided by the server.</p>
            <p>If an error occurs, the connection is rejected with a DIAGI 264.</p>         </td>
      </tr>
   </tbody>
</table>

Example 1

This example demonstrates an SSH default profile that has no client key authentication (CLIPUBKEY is not defined). The server private key is referenced by the SRVPRIVKEY parameter (SSH\_PRIV\_KEY in the example). The SRVPRIVKEY value is a key identifier that corresponds to a key stored in the local PKI database.

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTSSH ID = 'SSH_DEFAULT',</p>
            <p> DIRECT = 'SERVER',</p>
            <p> SRVPRIVKEY = 'SSH_PRIV_KEY',</p>
            <p>...</p>
            <p> MODE = 'REPLACE'</p>         </td>
      </tr>
   </tbody>
</table>

Example 2

The next example demonstrates an SSH default profile that uses client key authentication (CLIPUBKEY is defined). The client public key is referenced by the CLIPUBKEY parameter (SSH\_PUB\_KEY). The CLIPUBKEY value is a key identifier that corresponds to a key stored in the local PKI database.

Example 3

The server private key is referenced by the SRVPRIVKEY parameter (SSH\_PRIV\_KEY in the example). The value is also a key identifier that corresponds to a key stored in the local PKI database.

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTSSH ID = 'SSH_DEFAULT',</p>
            <p> DIRECT = 'SERVER',</p>
            <p> SRVPRIVKEY = 'SSH_PRIV_KEY',</p>
            <p>  CLIPUBKEY = 'SSH_PUB_KEY',</p>
            <p> MODE = 'REPLACE'</p>         </td>
      </tr>
   </tbody>
</table>

Example 4

This example demonstrates an SSH default profile with no server key authentication (SRVPUBKEY is not defined), but where there is no client key authentication (CLIPRIVKEY is not defined).

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTSSH ID = 'SSH_DEFAULT',</p>
            <p> DIRECT = 'CLIENT',</p>
            <p>  MODE = 'REPLACE'</p>         </td>
      </tr>
   </tbody>
</table>

Example 5

This example demonstrates an SSH default profile with server key authentication (SRVPUBKEY is defined), but where there is no client key authentication (CLIPRIVKEY is not defined). The server public key is referenced by the SRVPUBKEY parameter (SSH\_PUB\_KEY in the example). The SRVPUBKEY value is a key identifier that corresponds to a key stored in the local PKI database.

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTSSH ID = 'SSH_DEFAULT',</p>
            <p>  DIRECT = 'CLIENT',</p>
            <p> SRVPUBKEY = 'SSH_PUB_KEY',</p>
            <p>  MODE = 'REPLACE'</p>         </td>
      </tr>
   </tbody>
</table>

Example 6

This example demonstrates an SSH default profile with server key authentication (SRVPUBKEY is defined) and client key authentication (CLIPRIVKEY is defined).

-   The server public key is referenced by the SRVPUBKEY parameter (SSH\_PUB\_KEY). The SRVPUBKEY value is a key identifier that corresponds to a key stored in the local PKI database.
-   The client private key is referenced by the CLIPRIVKEY parameter (SSH\_PRIV\_KEY in this example). The CLIPRIVKEY value is a key identifier that corresponds to a key stored in the local PKI database.

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTSSH ID = 'SSH_DEFAULT',</p>
            <p>DIRECT = 'CLIENT',</p>
            <p>SRVPUBKEY = 'SSH_PUB_KEY',</p>
            <p>CLIPRIVKEY = 'SSH_PRIV_KEY',</p>
            <p>MODE = 'REPLACE'</p>         </td>
      </tr>
   </tbody>
</table>
