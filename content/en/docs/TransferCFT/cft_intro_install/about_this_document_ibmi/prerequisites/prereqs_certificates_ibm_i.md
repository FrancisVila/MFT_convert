{
    "title": "Certificates",
    "linkTitle": "Certificates",
    "weight": "180"
}## Delivered certificates

The use of the default certificate supplied with Transfer CFT is strongly discouraged in a production environment. You should use your own certificates to enhance security.

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Caution  </strong></span></td>
<td data-mc-autonum="&lt;b&gt;Caution  &lt;/b&gt;" data-valign="top">You must store certificates on the native side of the machine. Certificates located on the IFS partition are not supported.</td>
</tr>
</tbody>
</table>

## Create a PEM certificate for IBM i

For a PEM certificate, you must create a file with a record length equal to the size of the certificate in bytes. You can then upload the certificate to the newly created file.

Example

In this example, assume that your certificate 2k\_l1\_user1\_key.pem size is 1,191 bytes. Before uploading this certificate to the IBM i server, you would need to create a file with a record length of 1,191 bytes, as follows:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-mc-conditions="Primary.For_IBM_i_os400">CRTPF FILE(YOURLIB/PEM_CERT) RCDLEN(1191)</td>
</tr>
</tbody>
</table>

You can use FTP, for example, to then upload 2k\_l1\_user1\_key.pem to YOURLIB/PEM\_CERT.

-   You must transfer PEM certificates in ASCII mode
-   All other certificates can be transferred in binary mode

## Upload certificates to iSeries

You can use 3 type of certificates with Transfer CFT IBM i - PEM, DER, and P12, which must be stored on the native partition. Before you upload a certificate though, you need to know if it is binary or text, as the process differs depending on the format. For example, PEM certificates are in text, while the p12 certificates are in binary format.

### Using PEM (ASCII) certificates and keys

To use an ASCII certificate with Transfer CFT, perform the steps in this section.

On the Unix/Windows machine:

1.  Use a text editor, such as Notepad, to open the certificate and modify it so that is has only one line, and save.
2.  Use a text editor, such as Notepad, to open the private key and modify it so that is has only one line, and save.
3.  Use FTP to upload the certificate and key files (in ASCII mode) to the iSeries machine.

For example:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>FTP open &lt;HOST&gt;</p>
<p>cd CFTPROD</p>
<p>ascii</p>
<p>put USER.pem USERPEM</p>
<p>put USERK.pem USERKPEM</p></td>
</tr>
</tbody>
</table>

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">If you have multiple certificates, repeat the process for each.</td>
</tr>
</tbody>
</table>

### Using binary certificates and keys

#### P12

Use FTP to upload the certificate file (in binary mode) to the iSeries machine. For example:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>FTP OPEN &lt;HOST&gt;</p>
<p>cd CFTPROD</p>
<p>binary</p>
<p>put USER.P12 USERP12</p></td>
</tr>
</tbody>
</table>

#### DER

Use FTP to upload the certificate and key files (in binary mode) to the iSeries machine. For example:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>FTP open &lt;HOST&gt;</p>
<p>cd CFTPROD</p>
<p>binary</p>
<p>put USER.der USERDER</p>
<p>put USERK.der USERKDER</p></td>
</tr>
</tbody>
</table>
