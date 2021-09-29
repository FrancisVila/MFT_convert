{
    "title": "Delivered files and samples ",
    "linkTitle": "Delivered files and samples ",
    "weight": "240"
}The samples that are delivered with Transfer CFT use the Transfer CFT preprocessing utility to encode/decode a plaintext file before sending it. This topic describes the various delivered files, samples, and certificates that you can use to complete your TrustedFile implementation.

Content described in this topic:

-   [Scripts](#scripts)
-   [Trusted File configuration file](#trusted)
-   [Encoding/decoding samples](#sample)
-   [Sample certificates](#sample)
-   [Trusted File messages](#messages)
-   [Transcoding conversion tables](#transcod)

Conventions for Transfer CFT with Trusted File content includes:

-   $CFTDIRRUNTIME variable
    -   Unix: &lt;CFTDIRRUNTIME>
    -   Windows: %CFTDIRRUNTIME%
-   $CFTDIRINSTAL variable
    -   Unix: &lt;CFTDIRINSTALL>
    -   Windows: %CFTDIRINSTALL%

## <span id="Scripts"></span>Scripts

Unix scripts

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>Script</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>&lt;CFTDIRRUNTIME&gt;/exec/tf_decipher.cmd</td>
<td>Trusted File deciphering script</td>
</tr>
<tr class="even">
<td>&lt;CFTDIRRUNTIME&gt;/exec/tf_cipher.cmd</td>
<td>Trusted File ciphering script</td>
</tr>
<tr class="odd">
<td>&lt;CFTDIRRUNTIME&gt;/exec/tf_delfile.cmd</td>
<td>End of transfer procedure to delete the sent ciphered file</td>
</tr>
</tbody>
</table>

Windows scripts

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>Script</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>&lt;CFTDIRRUNTIME&gt;/exec/tf_decipher.bat</td>
<td>Trusted File deciphering script</td>
</tr>
<tr class="even">
<td>&lt;CFTDIRRUNTIME&gt;/exec/tf_cipher.bat</td>
<td>Trusted File ciphering script</td>
</tr>
<tr class="odd">
<td>&lt;CFTDIRRUNTIME&gt;/exec/tf_delfile.bat</td>
<td>End of transfer procedure to delete the sent ciphered file</td>
</tr>
</tbody>
</table>

## <span id="Trusted"></span>TrustedFile configuration file

The entities.xml file is the Trusted File configuration file containing the certificates for Trusted File. This configuration file is customized during Transfer CFT installation with the supplied default private and public certificates, “user1” and “user2”. If you intent to use your own certificates, update the entities.xml file, located at &lt;CFTDIRRUNTIME>/conf/tf/entities.xml.

If you want to use your own certificates and if the option tf.enablepasswordcipher=yes you have to generate a phassphrase using cfttf function:

passPhrase: For PKCS#12 files, the password required to access the file.

 

General Usage: CFTTF -pcfg conffile \[-plain plainFilename\] \[-entitiesLocation entitiesLocation\]

\[-envelope envelopeName\] \[-plainFileCharset plainCharset\] \[-plainEncCharset encCharset\]

\[-messagesPath messagesPath\] \[-template xmlFilename\]

To generate a passphrase, use the command: CFTTF -pw \[password\]

Example

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>CFTTF –pw user1
<p>OUTPUT: OGrplhngkBLeiazMyPkAdcLnd5jlNOnMoGYKaI2WfAw=</p></td>
</tr>
</tbody>
</table>

See also [How to generate a certificate for Trusted File](../tf_generate_cert).

## <span id="Sample"></span>Sample encoding files

The following files refer to “user1” and “user2”, which are used in the supplied private certificate. You must update these users if you intend to use your own certificates. These files are located in: &lt;CFTDIRRUNTIME>/conf/tf/.

Sample file descriptions

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>File</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>encfile_cms.xml</td>
<td>Sample file used for encoding CMS format</td>
</tr>
<tr class="even">
<td>encfile_pgp.xml</td>
<td>Sample file used for encoding PGP format</td>
</tr>
<tr class="odd">
<td>encfile_smime.xml</td>
<td>Sample file used for encoding S/MIME format</td>
</tr>
<tr class="even">
<td>decfile_cms.xml</td>
<td>Sample file used decoding CMS format</td>
</tr>
<tr class="odd">
<td>decfile_pgp.xml</td>
<td>Sample file used for decoding PGP format</td>
</tr>
<tr class="even">
<td>decfile_smime.xml</td>
<td>Sample file used for decoding S/MIME format</td>
</tr>
</tbody>
</table>

## Sample certificates

The following certificates are located in: &lt;CFTDIRRUNTIME>/conf/tf/.

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>Certificate</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>&lt;CFTDIRRUNTIME&gt;/conf/tf/certs/priv/xppuser1.p12</td>
<td>Private delivered “user1” certificate</td>
</tr>
<tr class="even">
<td>&lt;CFTDIRRUNTIME&gt;/conf/tf/certs/priv/xppuser2.p12</td>
<td>Private delivered “user2” certificate</td>
</tr>
<tr class="odd">
<td>&lt;CFTDIRRUNTIME&gt;/conf/tf/certs/pub/xppuser1.pem</td>
<td>Public delivered “user1” certificate</td>
</tr>
<tr class="even">
<td>&lt;CFTDIRRUNTIME&gt;/conf/tf/certs/pub/xppuser2.pem</td>
<td>Public delivered “user2” certificate</td>
</tr>
</tbody>
</table>

## <span id="Messages"></span>Trusted File messages

The following messages are used by Trusted File, and are located in: $CFTDIRINSTALL/distrib/tf/english/. Each file contains a set of error message associated with the type of encoding used.

-   xasn.msg
-   xp3.msg
-   xpppki.msg
-   pgp.msg
-   smime.msg
-   xppadm.msg
-   xppconf.msg
-   xppgen.msg
-   xpp.msg
-   xppsrv.msg
-   xppwrap.msg

Refer to the Trusted File 3.6 Reference Guide for details, available on [support.axway.com](https://support.axway.com/).

## <span id="Transcod"></span>Transcoding table

The `<CFTDIRRUNTIME>/conf/tf/transcoding.tbl` file contains all available transcoding tables.

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>Table</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>&lt;CFTDIRINSTALL&gt;/distrib/tf/tables/iso_atoe.tbl</td>
<td>Converts Latin ASCII to French EBCDIC</td>
</tr>
<tr class="even">
<td>&lt;CFTDIRINSTALL&gt;/distrib/tf/tables/iso_etoa.tbl</td>
<td>Converts French EBCDIC to Latin ASCII</td>
</tr>
<tr class="odd">
<td>&lt;CFTDIRINSTALL&gt;/distrib/tf/tables/std_atoe.tbl</td>
<td>Converts  IBM-PC850 to French EBCDIC</td>
</tr>
<tr class="even">
<td>&lt;CFTDIRINSTALL&gt;/distrib/tf/tables/std_etoa.tbl</td>
<td>Converts French EBCDIC to IBM-PC850</td>
</tr>
</tbody>
</table>
