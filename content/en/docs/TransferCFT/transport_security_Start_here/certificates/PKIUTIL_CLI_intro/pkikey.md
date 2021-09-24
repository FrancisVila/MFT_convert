{
    "title": "Using PKIKEY",
    "linkTitle": "Using PKIKEY",
    "weight": "300"
}This page describes how to use the PKIUTIL PKIKEY command.

## About PKIKEY

A private key is comprised of both a private and public key component. You can use this private key, as it contains two keys, for both the server and the client. However, only the public key portion is used for the client.

The PKIKEY command is similar to the PKICER command. Parameters include:

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Parameter</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr valign="top">
         <td width="28.19%">
            <p><a href="../../../../c_intro_userinterfaces/command_summary/parameter_intro/pkifname">PKIFNAME</a>: </p>
         </td>
         <td width="47.156%">
            <p>The PKI database file ($CFTPKU by default) <i> only in command line</i></p>
         </td>
      </tr>
      <tr valign="top">
         <td width="28.19%"><a href="../../../../c_intro_userinterfaces/command_summary/parameter_intro/id">ID</a>:          </td>
         <td width="47.156%">The PKIKEY identifier         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="28.19%"><a href="../../../../c_intro_userinterfaces/command_summary/parameter_intro/comment">COMMENT</a>:          </td>
         <td colspan="1" rowspan="1" width="47.156%">Free comment         </td>
      </tr>
      <tr valign="top">
         <td width="28.19%"><a href="../../../../c_intro_userinterfaces/command_summary/parameter_intro/state">STATE</a>:          </td>
         <td width="47.156%">The state of the imported key (ACT or INACT). You cannot use deactivated keys (state=INACT)  for SFTP         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="28.19%"><a href="ikdata.htm">IKDATA</a>:          </td>
         <td colspan="1" rowspan="1" width="47.156%">Use base-64 data instead of a file (where the format corresponds with ikform)         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="28.19%"><a href="../../../../c_intro_userinterfaces/command_summary/parameter_intro/iform">IKFORM</a>:          </td>
         <td colspan="1" rowspan="1" width="47.156%">The key format (DER, PEM, PKCS8, SSH or KPRIV). The "SSH" value includes the SSH2 format and the ssh-rsa format         </td>
      </tr>
      <tr valign="top">
         <td width="28.19%">
            <p><a href="../../../../c_intro_userinterfaces/command_summary/parameter_intro/ikname">IKNAME</a>: </p>
         </td>
         <td width="47.156%">The key file to import<i> only in command line</i>         </td>
      </tr>
      <tr valign="top">
         <td width="28.19%">
            <p><a href="ikpub.htm">IKPUB</a>: </p>
         </td>
         <td width="47.156%">Text-only public key in ssh-rsa format<i> only in command line</i>         </td>
      </tr>
      <tr valign="top">
         <td width="28.19%">
            <p><a href="../../../../c_intro_userinterfaces/command_summary/parameter_intro/ikpassw">IKPASSW</a>:</p>
         </td>
         <td width="47.156%"> The key file protection password in PKCS8 or encrypted PEM (PKCS #5)         </td>
      </tr>
      <tr valign="top">
         <td width="28.19%"><a href="../../../../c_intro_userinterfaces/command_summary/parameter_intro/mode">MODE</a>:          </td>
         <td width="47.156%">The action to perform (CREATE, REPLACE, DELETE)<i> only in command line</i>         </td>
      </tr>
   </tbody>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">See the <a href="../pkikeygen">PKIKEYGEN</a> command for details on how to generate and use your own keys.          </td>
      </tr>
</table>

### Restrictions

-   Transfer CFT does not support keys that contain comments, regardless of if you are directly referencing or importing them.
-   Transfer CFT does not support private keys with passphrases.
-   Transfer CFT supports the RSA digital signature algorithm; however, ECDSA and DSA are not supported.

## Example uses

If you already have keys that you want to use, you can import them as described in the following sections.

Import with PKCS8 format

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>PKIUTIL PKIKEY ID=PRIVATE,COMMENT="My_note",IKFORM=PKCS8,IKPASSW="MyPassw", IKNAME=./conf/pki/private.pk8,MODE=CREATE</p>
         </td>
      </tr>
   </tbody>
</table>

Import with encrypted PEM (PKCS#5) format

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>PKIUTIL PKIKEY ID=PRIVATE,COMMENT="My_note",IKFORM=PEM,IKPASSW="MyPassw", IKNAME=./conf/pki/private.pem,MODE=CREATE</p>
         </td>
      </tr>
   </tbody>
</table>

-----BEGIN RSA PRIVATE KEY-----

Proc-Type: 4,ENCRYPTED

DEK-Info: AES-128-CBC,9E18D04529594FB617BC471F9958C8A7

&lt;encrypted key data in base 64>

-----END RSA PRIVATE KEY---------

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">If a PEM encrypted key is generated using OpenSSL with FIPS, for example with "ssh-keygen", you cannot import it into <span>Transfer CFT</span>. To use this key,  convert it to PKCS#8 using the command: <br/><code>openssl pkcs8 -topk8 -v2 aes128 -in &lt;key&gt; -out &lt;key.pk8&gt;</code>         </td>
      </tr>
</table>

Import with private.rsa format

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>PKIUTIL PKIKEY ID=PRIVRSA, IKFORM=PEM, IKNAME=./private.rsa, MODE=CREATE         </td>
      </tr>
   </tbody>
</table>

-----BEGIN RSA PRIVATE KEY-----                                 

MIICXwIBAAKBgQDDUPaQmmgTL90EaFPvzt9u/1AAxdeXKhTuH6QMTevV7dllkNHe

...

-----END RSA PRIVATE KEY-----                                   

Import with public.ssh2 format

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>PKIUTIL PKIKEY ID=PUBSSH2, IKFORM=SSH, IKNAME=./public.ssh2, MODE=CREATE         </td>
      </tr>
   </tbody>
</table>

---- BEGIN SSH2 PUBLIC KEY ----                                                     

AAAAB3NzaC1yc2EAAAADAQABAAAAgQDDUPaQmmgTL90EaFPvzt9u/1AAxdeXKhTuH

....

---- END SSH2 PUBLIC KEY ----                                                                                        

Import with public.ssh-rsa format

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>PKIUTIL PKIKEY ID=PUBSSHRSA, IKFORM=SSH, IKNAME=./public.ssh-rsa, MODE=CREATE         </td>
      </tr>
   </tbody>
</table>

ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAAAgQDDUPaQmmgTL90EaFPvzt9u/1AAxdeXKhTuH6QMT...

BW4FzI2WRwuTK5vx4s2AF8+4wy7tKrR8kxHn2qnXB12ICh5/nnt2syjw== = KeyType=RSA Date=2017

0612 User=MyUser Comment=This is a free comment

Import with public.pem format

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>PKIUTIL PKIKEY ID=PUBPEM, IKFORM=PEM, IKNAME=./public.pem, MODE=CREATE         </td>
      </tr>
   </tbody>
</table>

> -----BEGIN PUBLIC KEY-----                                     
>
> MIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQDDUPaQmmgTL90EaFPvzt9u/1AA
>
> ...
>
> -----END PUBLIC KEY-----     
