{
    "title": "Generate and manage keys",
    "linkTitle": "Generate and manage keys",
    "weight": "180"
}T<span style="font-weight: normal;">**he supported operating systems are listed in the** [Platform features](../../../datasheet) **table.**</span>

This section describes how to establish secure sessions and generate keys, import etc. in the context of SFTP.

<span id="Use"></span>

## Using PKIKEYGEN to generate and import a key pair

You can use the <span class="code">PKIKEYGEN </span>command to generate a key pair, where it then stores them in the local PKI database.



    PKIUTIL PKIKEYGEN 
     ID=KEY_2048, 
     PKIFNAME=$CFTPKU, 
     STATE=ACT, 
     KEYLEN=2048, 
     MODE=CREATE, 
     COMMENT="2048-bits RSA key"

## Using PKIKEY to manage keys

### About PKI formats

The SFTP keys are referenced in the PKI database as a <span class="code">Keys </span>identifier.

You can import the following formats in the PKI database:

-   Raw DER format
-   PEM format for RSA private and public key, beginning with “BEGIN RSA PRIVATE KEY” or “BEGIN RSA PUBLIC KEY”, or X.509 public key, beginning with “BEGIN PUBLIC KEY”
-   Encrypted PEM format for RSA private key (PKCS #5), beginning with "BEGIN RSA PRIVATE KEY " and "Proc-Type: 4,ENCRYPTED"
-   PKCS8 format, beginning with “BEGIN PRIVATE KEY” or “BEGIN ENCRYPTED PRIVATE KEY”
-   SSH2 format, beginning with “BEGIN SSH2 PUBLIC KEY”
-   ssh-rsa format, beginning with “ssh-rsa”

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>When using the ssh-keygen tool, keys are usually generated in encrypted PEM format, which you can import using the PKIKEY command.         </td>
      </tr>
   </tbody>
</table>

Restrictions

-   Transfer CFT does not support keys that contain comments, regardless of if you are directly referencing or importing them.
-   Transfer CFT does not support private keys with passphrases.
-   Transfer CFT supports the RSA digital signature algorithm; however, ECDSA and DSA are not supported.

### PKIKEY command parameters

A private key is comprised of both a private and public key component. You can use this private key, as it contains two keys, for both the server and the client. However, only the public key portion is used for the client.

The PKIKEY command is similar to the PKICER command. Parameters include:

<table>
   <th>
      <tr>
<th>Parameter         </th>
<th>Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/pkifname">PKIFNAME</a>:</p>         </td>
         <td><p>The PKI database file ($CFTPKU by default) <em>only in command line</em></p>         </td>
      </tr>
      <tr>
         <td><a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/id">ID</a>:         </td>
         <td>The PKIKEY identifier         </td>
      </tr>
      <tr>
         <td><a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/comment">COMMENT</a>:         </td>
         <td>Free comment         </td>
      </tr>
      <tr>
         <td><a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/state">STATE</a>:         </td>
         <td>The state of the imported key (ACT or INACT). You cannot use deactivated keys (state=INACT) for SFTP         </td>
      </tr>
      <tr>
         <td>IKDATA:          </td>
         <td>Use base-64 data instead of a file (where the format corresponds with ikform)         </td>
      </tr>
      <tr>
         <td><a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/iform">IKFORM</a>:         </td>
         <td>The key format (DER, PEM, PKCS8, SSH or KPRIV). The "SSH" value includes the SSH2 format and the ssh-rsa format         </td>
      </tr>
      <tr>
         <td><p><a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/ikname">IKNAME</a>:</p>         </td>
         <td>The key file to import <em>only in command line</em>         </td>
      </tr>
      <tr>
         <td><p>IKPUB:</p>         </td>
         <td>Text-only public key in ssh-rsa format <em>only in command line</em>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/ikpassw">IKPASSW</a>:</p>         </td>
         <td>The key file protection password in PKCS8 or encrypted PEM (PKCS #5)         </td>
      </tr>
      <tr>
         <td><a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/mode">MODE</a>:         </td>
         <td>The action to perform (CREATE, REPLACE, DELETE) <em>only in command line</em>         </td>
      </tr>
   </tbody>
</table>

### Import existing keys

If you already have keys that you want to use, you can import them as described in the following sections.

Import with PKCS8 format



    PKIUTIL PKIKEY ID=PRIVATE,COMMENT="My_note",IKFORM=PKCS8,IKPASSW="MyPassw", IKNAME=./conf/pki/private.pk8,MODE=CREATE

Import with encrypted PEM (PKCS#5) format



    PKIUTIL PKIKEY ID=PRIVATE,COMMENT="My_note",IKFORM=PEM,IKPASSW="MyPassw", IKNAME=./conf/pki/private.pem,MODE=CREATE

-----BEGIN RSA PRIVATE KEY-----

Proc-Type: 4,ENCRYPTED

DEK-Info: AES-128-CBC,9E18D04529594FB617BC471F9958C8A7

&lt;encrypted key data in base 64>

-----END RSA PRIVATE KEY---------

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>If a PEM encrypted key is generated using OpenSSL with FIPS, for example with "ssh-keygen", you cannot import it into <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span>. To use this key, convert it to PKCS#8 using the command:<br />
<code>openssl pkcs8 -topk8 -v2 aes128 -in &lt;key&gt; -out &lt;key.pk8&gt;</code>         </td>
      </tr>
   </tbody>
</table>

Import with private.rsa format


    PKIUTIL PKIKEY ID=PRIVRSA, IKFORM=PEM, IKNAME=./private.rsa, MODE=CREATE

-----BEGIN RSA PRIVATE KEY-----                                 

MIICXwIBAAKBgQDDUPaQmmgTL90EaFPvzt9u/1AAxdeXKhTuH6QMTevV7dllkNHe

...

-----END RSA PRIVATE KEY-----                                   

Import with public.ssh2 format


    PKIUTIL PKIKEY ID=PUBSSH2, IKFORM=SSH, IKNAME=./public.ssh2, MODE=CREATE

---- BEGIN SSH2 PUBLIC KEY ----                                                     

AAAAB3NzaC1yc2EAAAADAQABAAAAgQDDUPaQmmgTL90EaFPvzt9u/1AAxdeXKhTuH

....

---- END SSH2 PUBLIC KEY ----                                                                                        

Import with public.ssh-rsa format


    PKIUTIL PKIKEY ID=PUBSSHRSA, IKFORM=SSH, IKNAME=./public.ssh-rsa, MODE=CREATE

ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAAAgQDDUPaQmmgTL90EaFPvzt9u/1AAxdeXKhTuH6QMT...

BW4FzI2WRwuTK5vx4s2AF8+4wy7tKrR8kxHn2qnXB12ICh5/nnt2syjw== = KeyType=RSA Date=2017

0612 User=MyUser Comment=This is a free comment

Import with public.pem format


    PKIUTIL PKIKEY ID=PUBPEM, IKFORM=PEM, IKNAME=./public.pem, MODE=CREATE

> -----BEGIN PUBLIC KEY-----                                     
>
> MIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQDDUPaQmmgTL90EaFPvzt9u/1AA
>
> ...
>
> -----END PUBLIC KEY-----     

## Activate/deactivate a key

Use the <span class="code">ACT/INACT</span> commands to activate or deactivate, respectively.

Example

Use the LISTPKI command to list available keys:



    >LISTPKI

      Keys:
      Id.              S K Bits
      
    ---------------- - - ----
      
    CFT_SSH_PRIV     A x 2048
      
    CFT_SSH_PUB      A   2048


     
    PKIU00I LISTPKI  _ Correct ()

Example

This example demonstrates key deactivation where **I** indicates \[INACT\] and **A** indicates \[ACT\].



    >listpki
      Keys:

      Id.              S K Bits
      -----------
      CFT_SSH_PRIV     A x 2048
      
    CFT_SSH_PUB        A      2048


     

    >inact type=key
     
     
    >listpki
      Keys:

      Id.              S K Bits
      -----------
      CFT_SSH_PRIV     I x 2048
      
    CFT_SSH_PUB        I       2048