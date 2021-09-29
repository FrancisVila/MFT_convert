{
    "title": "Import and export keys and certificates",
    "linkTitle": "Import and export keys and certificates",
    "weight": "260"
}## Import keys and certificates

You can use the import feature to convert your OpenPGP certificates
and private keys or a trading partner's certificates to the X.509/PKCS#12
format.

You can convert:

-   PGP Public
    Keyrings to X.509 Certificates
-   PGP Secret
    Keyrings to PKCS#12 packages

### Import procedure

You can convert a PGP public Keyring file to one or several X.509certificate(s) and a PGP secret Keyring file to one or several PKCS#12 package(s). If no options are provided, the .p12 file or the cert file is stored in the current directory. The private keys are assumed not password protected and a default subject DN is selected for you.

When you import a private keyring file containing ElGamal subkey(s), you must provide the PKCS#12 file for signing (as in public keyring import), because the ElGamal keys cannot be used for signing when you create a certificate.

1.  Use CFTUTIL to set the full path to Java executable:  
    <table data-cellspacing="0">
    <tbody>
    <tr class="odd">
    <td>UCONFSET id=cft.jre.java_binary_path ,value=/bin/java</td>
    </tr>
    </tbody>
    </table>
2.  Enter the import command:

-   UNIX: ImportPGPKey.sh
-   Windows: ImportPGPKey.bat

There are several options you can add to the command line:

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>Options</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>-h or -help</td>
<td>Displays the help with all available options.</td>
</tr>
<tr class="even">
<td>-dn</td>
<td>Subject DN of the generated certificate. If this option is not provided, the default subject DN is CN=PGP.</td>
</tr>
<tr class="odd">
<td>-out</td>
<td><p>Output path of the generated certificate or PKCS#12 file. If this option is not provided, the file is stored in the current directory. It must contain the tailing file separator („\‟ on Windows and „/‟ on UNIX).</p></td>
</tr>
<tr class="even">
<td>-passwd</td>
<td>Private key PassPhrase of the secret Keyring located in the input file.</td>
</tr>
<tr class="odd">
<td>-newpasswd</td>
<td>Private key PassPhrase of the generated PKCS#12 file. This option is mandatory for imported secret Keyrings.</td>
</tr>
<tr class="even">
<td>-pkcs12</td>
<td>PKCS#12 file used to sign the new generated certificate.</td>
</tr>
<tr class="odd">
<td>-passPkcs12</td>
<td>Passphrase of the PKCS#12 file used to sign the new generated certificate.</td>
</tr>
</tbody>
</table>

### Example commands

The following examples use the UNIX command extension (.sh). On Windows systems replace .sh with .bat in your command.

ImportPGPKey.sh -dn "cn=Axway,c=fr" -pkcs12 /home/user/pkcs12.p12 -passPkcs12 "passphrasePKCS12" -out /home/user/output/ /home/user/pubring.pkr

This example stores the certificate provided by the public Keyring home/user/pubring.pkr in the /home/user/output/ directory. The subject DN of the certificate generated will be "cn=Axway,c=fr".

The private key used to sign the certificate is stored in the PKCS#12 file located in the `/home/user/pkcs12.p12` directory.

The PassPhrase of this PKCS#12 file is "passphrasePKCS12".

ImportPGPKey.sh -passwd "pass" -newpasswd "newpasswd" -out /home/user/output/

`/home/user/secring.skr`

This example stores the private key provided by the secret Keyring home/user/secring.skr in the` /home/user/output/` directory.

The PassPhrase of the secret Keyring is "pass". The PassPhrase of the generated PKCS#12 file is "newpasswd".

## Export keys and certificates

This feature allows you to convert a PKCS#12 package to a PGP Public Keyring file and/or a PGP Secret Keyring file.

For the ElGamal keys stored in a PKCS#12 file, it is mandatory to provide a signing certificate and corresponding password. ElGamal keys cannot be used for signing or as a master key for a created keyring.

TrustedFile exports keys and certificates with the
following file names.

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>Key/certificate standard</th>
<th>Exported file name</th>
</tr>
</thead>
<tbody>
<tr class="odd" data-valign="middle">
<td><p>PGP Public Keyring</p></td>
<td><p><span>useridpacket</span>_pub.asc</p></td>
</tr>
<tr class="even" data-valign="middle">
<td><p>PGP Secret Keyring and Public Keyring</p></td>
<td><p><span>useridpacket</span>_sec.asc
and <span>useridpacket</span>_pub.asc</p></td>
</tr>
<tr class="odd" data-valign="middle">
<td><p>X.509 Certificate</p></td>
<td><p><span>certificate alias.</span><span>der</span></p></td>
</tr>
</tbody>
</table>

### Export procedure

1.  Use CFTUTIL to set the full path to Java executable:  
    <table data-cellspacing="0">
    <tbody>
    <tr class="odd">
    <td>UCONFSET id=cft.jre.java_binary_path ,value=/bin/java</td>
    </tr>
    </tbody>
    </table>
2.  Enter the import command:

-   UNIX: ExportPGPKey.sh
-   Windows: ExportPGPKey.bat

There are several options you can add to the command line:

<table data-cellspacing="0">
<thead>
<tr class="header">
<th><p>Option</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>-help | -h</p></td>
<td><p>Displays the help.</p></td>
</tr>
<tr class="even">
<td><p>-out</p></td>
<td><p>Output path (with the trailing path separator). If this option is not provided, the file is stored in the current directory.</p></td>
</tr>
<tr class="odd">
<td><p>-passSecRing</p></td>
<td><p>PassPhrase of the generated secret Keyring.</p></td>
</tr>
<tr class="even">
<td><p>-userIdPacket</p></td>
<td><p>User ID packet of the generated secret Keyring and public Keyring.</p></td>
</tr>
<tr class="odd">
<td><p>-passPkcs12</p></td>
<td><p>PassPhrase of the PKCS#12 file to be converted.</p></td>
</tr>
<tr class="even">
<td><p>-secRing</p></td>
<td><p>With the argument "no", the secret Keyring will not generate.</p>
<p>Do</p>
<p>not use this option or use an alternative argument.</p></td>
</tr>
<tr class="odd">
<td><p>-pubRing</p></td>
<td><p>With the argument "no", the public Keyring will not generate. Do not use this option or use an alternative argument.</p></td>
</tr>
<tr class="even">
<td><p>-masterPkcs12</p></td>
<td><p>(only for ElGamal) PKCS#12 file used to sign the new generated certificate.</p></td>
</tr>
<tr class="odd">
<td><p>-masterPassPkcs12</p></td>
<td><p>(only for ElGamal) Passphrase of the PKCS#12 file used to sign the new generated certificate.</p></td>
</tr>
</tbody>
</table>

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">The following options are required:<code> -userIdPacket</code> and <code>-passSecRing</code><span>.</span> By default (without <code>-secRing </code>or <code>-pubRing</code> options), the feature exports Public Keyring <span>and </span>Secret Keyring.<br />
If you do not need to export the Secret Keyring, add<span> - secRing no</span> to the command line.<br />
If you do not need to export the Public Keyring, add <span>- pubRing no</span> to the command line.</td>
</tr>
</tbody>
</table>

### Example commands

The following examples use the UNIX command extension (.sh). On Windows systems replace .sh with .bat in your command.

ExportPGPKey.sh -userIdPacket "userIdPacket" -passPkcs12 "passPkcs12"

-passSecRing "passSecRing" -out /home/user/output/

/home/user/Pkcs12ToConvert.p12

This example stores the secret Keyring and the public Keyring provided by the file `Pkcs12ToConvert.p12` in the `/home/user/output/` directory.

The PassPhrase of Pkcs12ToConvert.p12 is "passPkcs12". The user ID packet in the generated files is "userIdPacket". The generated secret Keyring is protected by the PassPhrase "passSecRing".

ExportPGPKey.sh -userIdPacket "userIdPacket" -passPkcs12 "passPkcs12"

-passSecRing "passSecRing" -out /home/user/output/ -secRing no

/home/user/Pkcs12ToConvert.p12

The example is the same as above, with the -secRing no option. Only the public Keyring is generated.
