{
    "title": "CFTSSH - Security profile",
    "linkTitle": "SSH Security Profiles - CFTSSH",
    "weight": "200"
}Use the CFTSSH command to describe a security profile.

> **Note:**
>
> When using the SFTP protocol, the CFTSSH definition contains the SSH connection parameters for server or client mode.

## Server

The CFTSSH object parameters for a server definition (DIRECT = SERVER).

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Parameter         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>ID = identifier</p>         </td>
         <td><p>Identifier of the security profile.</p>         </td>
      </tr>
      <tr>
         <td><p>CIPHLIST = {(num, num,
..)}</p>         </td>
         <td><p>List of allowed ciphers (encryption methods).</p>
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
negotiated.</p>
<p><span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> supports the following: aes256-ctr, aes192-ctr, aes128-ctr, aes256-cbc, aes192-cbc, aes128-cbc, 3des-cbc, blowfish-cbc.</p>
<blockquote>
<p><strong>Note:</strong></p>
<p>If the field is empty, the default list is: aes256-ctr, aes192-ctr, aes128-ctr, aes256-cbc, aes192-cbc, aes128-cbc.</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td>CLIPUBKEY         </td>
         <td><p>When DIRECT=SERVER</p>
<p>Key Id containing the client public key (RSA). When defined, the Transfer CFT server checks that the client public key referenced in CLIPUBKEY matches the public key provided by the client. If an error occurs, the connection is rejected with a DIAGI 433.</p>         </td>
      </tr>
      <tr>
         <td>Comment         </td>
         <td>Free comment.         </td>
      </tr>
      <tr>
         <td><p>DIRECT</p>
<p> </p>         </td>
         <td><p>The security profile is applicable in this mode (SERVER).</p>         </td>
      </tr>
      <tr>
         <td>HMAC         </td>
         <td><p>List of accepted HMAC (keyed-hash message authentication code).</p>
<ul>
<li>Choose from the following: hmac-sha2-512, hmac-sha2-256, hmac-sha1, none.<br />
</li>
<li>If the field is empty, the default list is hmac-sha2-512, hmac-sha2-256, hmac-sha1.</li>
</ul>         </td>
      </tr>
      <tr>
         <td>KEYEXCHG         </td>
         <td><p>List of key exchange methods to use.</p>
<p>Choose from the following: curve25519-sha256@libssh.org, ecdh-sha2-nistp256, diffie-hellman-group14-sha1, diffie-hellman-group1-sha1.</p>         </td>
      </tr>
      <tr>
         <td><p>MODE = {REPLACE |
CREATE | DELETE}</p>         </td>
         <td><p>Action for the command. For DELETE mode, the command is
deleted from the PARAMETERS database; only the ID and DIRECT parameters
are required.</p>         </td>
      </tr>
      <tr>
         <td>ORIGIN = string         </td>
         <td>This parameter indicates the object's origin.         </td>
      </tr>
      <tr>
         <td>SRVPRIVKEY         </td>
         <td><p>When DIRECT=SERVER:</p>
<p>Key Id containing the server private key (RSA) to use with key authentication.</p>         </td>
      </tr>
   </tbody>
</table>

## Client

The CFTSSH object parameters for a client definition (DIRECT = CLIENT).

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Parameter         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>ID = identifier</p>         </td>
         <td><p>Identifier of the security profile.</p>         </td>
      </tr>
      <tr>
         <td><p>CIPHLIST = {(num, num,
..)}</p>         </td>
         <td><p>List of allowed ciphers (encryption methods).</p>
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
negotiated.</p>
<p><span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> supports the following: aes256-ctr, aes192-ctr, aes128-ctr, aes256-cbc, aes192-cbc, aes128-cbc, 3des-cbc, blowfish-cbc.</p>
<blockquote>
<p><strong>Note:</strong></p>
<p>If the field is empty, the default list is: aes256-ctr, aes192-ctr, aes128-ctr, aes256-cbc, aes192-cbc, aes128-cbc.</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td>CLIPRIVKEY         </td>
         <td>When DIRECT=CLIENT
Key Id containing the client private key (RSA) to use with key authentication. When defined, Transfer CFT uses key authentication. If an error occurs, the connection is rejected with a DIAGI 433.         </td>
      </tr>
      <tr>
         <td>Comment         </td>
         <td>Free comment.         </td>
      </tr>
      <tr>
         <td><p>DIRECT</p>         </td>
         <td><p>The security profile is applicable in this mode (CLIENT).</p>         </td>
      </tr>
      <tr>
         <td>HMAC         </td>
         <td><p>List of accepted HMAC (keyed-hash message authentication code).</p>
<ul>
<li>Choose from the following: hmac-sha2-512, hmac-sha2-256, hmac-sha1, none.<br />
</li>
<li>If the field is empty, the default list is hmac-sha2-512, hmac-sha2-256, hmac-sha1.</li>
</ul>         </td>
      </tr>
      <tr>
         <td>KEYEXCHG         </td>
         <td>List of key exchange methods to use. Choose from the following: curve25519-sha256@libssh.org, ecdh-sha2-nistp256, diffie-hellman-group14-sha1, diffie-hellman-group1-sha1.         </td>
      </tr>
      <tr>
         <td><p>MODE = {REPLACE |
CREATE | DELETE}</p>         </td>
         <td><p>Action for the command. For DELETE mode, the command is
deleted from the PARAMETERS database; only the ID and DIRECT parameters
are required.</p>         </td>
      </tr>
      <tr>
         <td>ORIGIN = string         </td>
         <td>This parameter indicates the object's origin.         </td>
      </tr>
      <tr>
         <td>SRVPUBKEY         </td>
         <td><p>When DIRECT=CLIENT:</p>
<p>Key Id containing the server public key (RSA) for the server. When defined, the Transfer CFT client checks that the public key referenced by SRVPUBKEY matches the key provided by the server.</p>
<p>If an error occurs, the connection is rejected with a DIAGI 264.</p>         </td>
      </tr>
   </tbody>
</table>

Example 1

This example demonstrates an SSH default profile that has no client key authentication (CLIPUBKEY is not defined). The server private key is referenced by the SRVPRIVKEY parameter (SSH\_PRIV\_KEY in the example). The SRVPRIVKEY value is a key identifier that corresponds to a key stored in the local PKI database.



    CFTSSH        ID          = 'SSH_DEFAULT',
     DIRECT      = 'SERVER',
     SRVPRIVKEY     = 'SSH_PRIV_KEY',
     ...
     MODE        = 'REPLACE'

Example 2

The next example demonstrates an SSH default profile that uses client key authentication (CLIPUBKEY is defined). The client public key is referenced by the CLIPUBKEY parameter (SSH\_PUB\_KEY). The CLIPUBKEY value is a key identifier that corresponds to a key stored in the local PKI database.

Example 3

The server private key is referenced by the SRVPRIVKEY parameter (SSH\_PRIV\_KEY in the example). The value is also a key identifier that corresponds to a key stored in the local PKI database.



    CFTSSH        ID          = 'SSH_DEFAULT',
      DIRECT      = 'SERVER',
      SRVPRIVKEY     = 'SSH_PRIV_KEY',
      CLIPUBKEY      = 'SSH_PUB_KEY',
      MODE        = 'REPLACE'

Example 4

This example demonstrates an SSH default profile with no server key authentication (SRVPUBKEY is not defined), but where there is no client key authentication (CLIPRIVKEY is not defined).



    CFTSSH        ID          = 'SSH_DEFAULT',
     DIRECT      = 'CLIENT',
      MODE        = 'REPLACE'

Example 5

This example demonstrates an SSH default profile with server key authentication (SRVPUBKEY is defined), but where there is no client key authentication (CLIPRIVKEY is not defined). The server public key is referenced by the SRVPUBKEY parameter (SSH\_PUB\_KEY in the example). The SRVPUBKEY value is a key identifier that corresponds to a key stored in the local PKI database.



    CFTSSH        ID          = 'SSH_DEFAULT',
      DIRECT      = 'CLIENT',
      SRVPUBKEY     = 'SSH_PUB_KEY',
      MODE        = 'REPLACE'

Example 6

This example demonstrates an SSH default profile with server key authentication (SRVPUBKEY is defined) and client key authentication (CLIPRIVKEY is defined).

-   The server public key is referenced by the SRVPUBKEY parameter (SSH\_PUB\_KEY). The SRVPUBKEY value is a key identifier that corresponds to a key stored in the local PKI database.
-   The client private key is referenced by the CLIPRIVKEY parameter (SSH\_PRIV\_KEY in this example). The CLIPRIVKEY value is a key identifier that corresponds to a key stored in the local PKI database.

<!-- -->



    CFTSSH        ID          = 'SSH_DEFAULT',
     DIRECT      = 'CLIENT',
     SRVPUBKEY     = 'SSH_PUB_KEY',
     CLIPRIVKEY    = 'SSH_PRIV_KEY',
     MODE        = 'REPLACE'
