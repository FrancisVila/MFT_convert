{
    "title": "Using PKIEXT",
    "linkTitle": "Using PKIEXT",
    "weight": "300"
}You can use the PKIEXT command to extract the certificates and keys from the Transfer CFT PKI database. PKIEXT generates as an output the configuration commands used to reconstitute the PKI database, certificates, and keys in the KPRIV format (an internal Transfer CFT format).

Additionally, this page describes how to export an SSH public key for [SFTP](../../../../protocols_start_here/sftp_intro).

## Parameters

You can use a mix of the ID and TYPE parameters to create extraction filters. See the [examples](#Examples) below for details.

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td rowspan="7"   width="19.982%"><p>Parameters</p>         </td>
         <td >ID         </td>
         <td   width="49.916%"><p>Identifier of either the certificate or key to be extracted.</p>
<p>When this parameter is not defined, all of the certificates and keys are extracted pending if TYPE is defined.</p>         </td>
      </tr>
      <tr>
         <td >BASE64         </td>
         <td   width="49.916%"><p>Export base64 data:</p>
<ul>
<li>Yes</li>
<li>No (default)</li>
</ul>
<p>When exporting data from the PKI database, you can request Base64 data instead of files.
This way, additional files are not created.</p>         </td>
      </tr>
      <tr>
         <td ><p>FOUT</p>         </td>
         <td   width="49.916%"><p>Name of the file where the command’s standard output
is  redirected.</p>
<p>This generated file can then be interpreted directly by
PKIUTIL.</p>
<p>If this parameter is not defined, the standard output is displayed.</p>         </td>
      </tr>
      <tr>
         <td   width="28.162%">[ INUM  = {number0...99} ]         </td>
         <td   width="49.916%">Internal number for the intermediate certificates in an imported chain of certificates (in the PKI database). You can use this option to select a specific intermediate certificate.         </td>
      </tr>
      <tr>
         <td   width="28.162%">PASSWORD         </td>
         <td   width="49.916%"><p>The password length must be between 4 and 64 characters.</p>
<ul>
<li>                        When using a password, PKIEXT exports a certificate/key pair in PKCS#12 format instead of DER (certificate) and KPRIV (key). &lt;/li&gt;</li>
<li>When using a password, PKIEXT exports a key  in PKCS#8 format instead of KPRIV.
                    &lt;/li&gt;</li>
</ul>         </td>
      </tr>
      <tr>
         <td   width="28.162%">ROOTCID         </td>
         <td   width="49.916%">The  certificate authority ID. See an example usage in <a href="../../../../c_intro_userinterfaces/command_summary/parameter_intro/rootcid">ROOTCID</a>.         </td>
      </tr>
      <tr>
         <td   width="28.162%">TYPE         </td>
         <td   width="49.916%"><p>This parameter defines the certificate or key type to be extracted.</p>
<p>Possible values:</p>
<ul>
<li>ALL: extracts ROOT, INTER, and USER in PKICER, PKIKEY, and PKIENTITY</li>
<li>USER</li>
<li>ROOT</li>
<li>INTER</li>
<li>ENTITY</li>
<li>KEY</li>
<li>CERT: extracts ROOT, INTER, and USER in PKICER</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

<span id="Examples"></span>

## Examples

This example extracts only the ROOT certificates of the PKI database.

```
PKIUTIL PKIEXT FOUT=PKI.EXT,TYPE=ROOT
```

This example extracts only the element of ID "MYKEY", regardless its type (PKIKEY, PKIENTITY...).

```
PKIUTIL PKIEXT FOUT=PKI.EXT,ID=MYKEY
```

This example extracts only the ROOT certificates with the ID "MYCERT" (this could be useful if multiple certificates have the same ID but are of a different TYPE).

```
PKIUTIL PKIEXT FOUT=PKI.EXT,TYPE=ROOT,ID=MYCERT
```

The following command exports `MY_CERT`, which is an existing user certificate, in PKCS12 format by adding a password `Mypassword`.

```
PKIUTIL PKIEXT ID=MY_CERT, FOUT=PKI.CONF, PASSWORD=Mypassword
```

After exporting the certificate, open the` PKI.CONF` file, where the INAME is the name of the exported PKCS12 certificate (and the password equal to `Mypassword`).

To use the Base64 option:

```
PKIUTIL PKIEXT FOUT=BAR.cmd, BASE64=YES
```

Which results in a single `BAR.cmd` command file.

## Exporting an SSH public key for SFTP

When using SFTP, you can export the public key  in an SSH\_RSA format to share with software other than Transfer CFT. To  perform an extract, you must have originally imported the key with the same PKIPASSW as used in the CFTPARM object. If not, the  export returns a key in KPRIV format instead of SSH\_RSA format (which is usable only by Transfer CFT).

## Importing and exporting keys

You can use PKIEXT to export keys from the local database.  To  perform an extract, you must use the  same PKIPASSW  (CFTPARM object) as was originally used to import the key. Using the same logic, to re-import a key that you extracted using PKIEXT, you require the same CFTPARM [PKIPASSW](../../../../c_intro_userinterfaces/command_summary/parameter_intro/pkipassw).

Due to native OS encoding (for example, ASCII on Linux and EBCDIC on z/OS), when you export a key to a different operating system the decode operation may fail even when both systems are using the same password.

Use the correct encoding and put the PKIPASSW  in a file, for example, the ASCII string "`password`" on an EBCDIC system. Then point the CFTPARM PKIPASSW  to this file, for example` PKIPASSW=#|@/path/to/pkipass_file`. The PKIPASSW is consequently read with the correct encoding, and the file is correctly deciphered.

> **Note**
>
> In earlier versions of Transfer CFT, the PKIPASSW parameter was used for encryption in multiple PKI commands. This functionality is now replaced by the UCONF crypto.key\_fname parameter.
