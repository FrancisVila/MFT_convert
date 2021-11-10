{
    "title": "Keys - PKIKEY",
    "linkTitle": "Keys - PKIKEY",
    "weight": "220"
}This page describes how to manage keys via the user interface.

> **Note:**
>
> Some command line  parameters are not available in the user interface.

## About keys in <span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span>

A private key is comprised of both a private and public key component. You can use this private key, as it contains two keys, for both the server and the client. However, only the public key portion is used for the client.

The PKIKEY command is similar to the PKICER command. Parameters include:

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Parameter         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/pkifname">PKIFNAME</a>:</p>         </td>
         <td><p>The PKI database file ($CFTPKU by default) <em>only in command line</em></p>         </td>
      </tr>
      <tr>
         <td><a href="../../../command_summary/parameter_intro/id">ID</a>:         </td>
         <td>The PKIKEY identifier         </td>
      </tr>
      <tr>
         <td><a href="../../../command_summary/parameter_intro/comment">COMMENT</a>:         </td>
         <td>Free comment         </td>
      </tr>
      <tr>
         <td><a href="../../../command_summary/parameter_intro/state">STATE</a>:         </td>
         <td>The state of the imported key (ACT or INACT). You cannot use deactivated keys (state=INACT) for SFTP         </td>
      </tr>
      <tr>
         <td>IKDATA:          </td>
         <td>Use base-64 data instead of a file (where the format corresponds with ikform)         </td>
      </tr>
      <tr>
         <td><a href="../../../command_summary/parameter_intro/iform">IKFORM</a>:         </td>
         <td>The key format (DER, PEM, PKCS8, SSH or KPRIV). The "SSH" value includes the SSH2 format and the ssh-rsa format         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/ikname">IKNAME</a>:</p>         </td>
         <td>The key file to import <em>only in command line</em>         </td>
      </tr>
      <tr>
         <td><p>IKPUB:</p>         </td>
         <td>Text-only public key in ssh-rsa format <em>only in command line</em>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/ikpassw">IKPASSW</a>:</p>         </td>
         <td>The key file protection password in PKCS8 or encrypted PEM (PKCS #5)         </td>
      </tr>
      <tr>
         <td><a href="../../../command_summary/parameter_intro/mode">MODE</a>:         </td>
         <td>The action to perform (CREATE, REPLACE, DELETE) <em>only in command line</em>         </td>
      </tr>
   </tbody>
</table>

> **Note:**
>
> See the PKIKEYGEN command for details on how to generate and use your own keys.

### Restrictions

-   Transfer CFT does not support keys that contain comments, regardless of if you are directly referencing or importing them.
-   Transfer CFT does not support private keys with passphrases.
-   Transfer CFT supports the RSA digital signature algorithm; however, ECDSA and DSA are not supported.
