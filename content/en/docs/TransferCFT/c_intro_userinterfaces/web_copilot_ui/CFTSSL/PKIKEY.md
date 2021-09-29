{
    "title": "Keys - PKIKEY",
    "linkTitle": "Keys - PKIKEY",
    "weight": "230"
}This page describes how to manage keys via the user interface.

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">Some command line  parameters are not available in the user interface.</td>
</tr>
</tbody>
</table>

## About keys in Transfer CFT

A private key is comprised of both a private and public key component. You can use this private key, as it contains two keys, for both the server and the client. However, only the public key portion is used for the client.

The PKIKEY command is similar to the PKICER command. Parameters include:

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>Parameter</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd" data-valign="top">
<td width="28.19%"><p><a href="../../../command_summary/parameter_intro/pkifname">PKIFNAME</a>:</p></td>
<td width="47.156%"><p>The PKI database file ($CFTPKU by default) <em>only in command line</em></p></td>
</tr>
<tr class="even" data-valign="top">
<td width="28.19%"><a href="../../../command_summary/parameter_intro/id">ID</a>:</td>
<td width="47.156%">The PKIKEY identifier</td>
</tr>
<tr class="odd" data-valign="top">
<td width="28.19%"><a href="../../../command_summary/parameter_intro/comment">COMMENT</a>:</td>
<td width="47.156%">Free comment</td>
</tr>
<tr class="even" data-valign="top">
<td width="28.19%"><a href="../../../command_summary/parameter_intro/state">STATE</a>:</td>
<td width="47.156%">The state of the imported key (ACT or INACT). You cannot use deactivated keys (state=INACT) for SFTP</td>
</tr>
<tr class="odd" data-valign="top">
<td width="28.19%"><a href="ikdata.htm">IKDATA</a>: </td>
<td width="47.156%">Use base-64 data instead of a file (where the format corresponds with ikform)</td>
</tr>
<tr class="even" data-valign="top">
<td width="28.19%"><a href="../../../command_summary/parameter_intro/iform">IKFORM</a>:</td>
<td width="47.156%">The key format (DER, PEM, PKCS8, SSH or KPRIV). The "SSH" value includes the SSH2 format and the ssh-rsa format</td>
</tr>
<tr class="odd" data-valign="top">
<td width="28.19%"><p><a href="../../../command_summary/parameter_intro/ikname">IKNAME</a>:</p></td>
<td width="47.156%">The key file to import <em>only in command line</em></td>
</tr>
<tr class="even" data-valign="top">
<td width="28.19%"><p><a href="ikpub.htm">IKPUB</a>:</p></td>
<td width="47.156%">Text-only public key in ssh-rsa format <em>only in command line</em></td>
</tr>
<tr class="odd" data-valign="top">
<td width="28.19%"><p><a href="../../../command_summary/parameter_intro/ikpassw">IKPASSW</a>:</p></td>
<td width="47.156%">The key file protection password in PKCS8 or encrypted PEM (PKCS #5)</td>
</tr>
<tr class="even" data-valign="top">
<td width="28.19%"><a href="../../../command_summary/parameter_intro/mode">MODE</a>:</td>
<td width="47.156%">The action to perform (CREATE, REPLACE, DELETE) <em>only in command line</em></td>
</tr>
</tbody>
</table>

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">See the <a href="../../../../transport_security_start_here/certificates/pkiutil_cli_intro/pkikeygen">PKIKEYGEN</a> command for details on how to generate and use your own keys.</td>
</tr>
</tbody>
</table>

### Restrictions

-   Transfer CFT does not support keys that contain comments, regardless of if you are directly referencing or importing them.
-   Transfer CFT does not support private keys with passphrases.
-   Transfer CFT supports the RSA digital signature algorithm; however, ECDSA and DSA are not supported.
