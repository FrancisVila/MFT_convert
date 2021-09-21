{
    "title": "Keys - PKIKEY",
    "linkTitle": "Keys - PKIKEY",
    "weight": "230"
}This page describes how to manage keys via the user interface.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Some command line  parameters are not available in the user interface.          </td>
      </tr>
</table>

## About keys in Transfer CFT

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
            <p><a href="../../../command_summary/parameter_intro/pkifname">PKIFNAME</a>: </p>
         </td>
         <td width="47.156%">
            <p>The PKI database file ($CFTPKU by default) <i> only in command line</i></p>
         </td>
      </tr>
      <tr valign="top">
         <td width="28.19%"><a href="../../../command_summary/parameter_intro/id">ID</a>:          </td>
         <td width="47.156%">The PKIKEY identifier         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="28.19%"><a href="../../../command_summary/parameter_intro/comment">COMMENT</a>:          </td>
         <td colspan="1" rowspan="1" width="47.156%">Free comment         </td>
      </tr>
      <tr valign="top">
         <td width="28.19%"><a href="../../../command_summary/parameter_intro/state">STATE</a>:          </td>
         <td width="47.156%">The state of the imported key (ACT or INACT). You cannot use deactivated keys (state=INACT)  for SFTP         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="28.19%"><a href="ikdata.htm">IKDATA</a>:          </td>
         <td colspan="1" rowspan="1" width="47.156%">Use base-64 data instead of a file (where the format corresponds with ikform)         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="28.19%"><a href="../../../command_summary/parameter_intro/iform">IKFORM</a>:          </td>
         <td colspan="1" rowspan="1" width="47.156%">The key format (DER, PEM, PKCS8, SSH or KPRIV). The "SSH" value includes the SSH2 format and the ssh-rsa format         </td>
      </tr>
      <tr valign="top">
         <td width="28.19%">
            <p><a href="../../../command_summary/parameter_intro/ikname">IKNAME</a>: </p>
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
            <p><a href="../../../command_summary/parameter_intro/ikpassw">IKPASSW</a>:</p>
         </td>
         <td width="47.156%"> The key file protection password in PKCS8 or encrypted PEM (PKCS #5)         </td>
      </tr>
      <tr valign="top">
         <td width="28.19%"><a href="../../../command_summary/parameter_intro/mode">MODE</a>:          </td>
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
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">See the <a href="../../../../transport_security_start_here/certificates2/pkiutil_cli_intro/pkikeygen">PKIKEYGEN</a> command for details on how to generate and use your own keys.          </td>
      </tr>
</table>

### Restrictions

-   Transfer CFT does not support keys that contain comments, regardless of if you are directly referencing or importing them.
-   Transfer CFT does not support private keys with passphrases.
-   Transfer CFT supports the RSA digital signature algorithm; however, ECDSA and DSA are not supported.
