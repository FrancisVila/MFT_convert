{
    "title": "Certificates - PKICER",
    "linkTitle": "Certificates - PKICER",
    "weight": "230"
}This section describes how to:

-   Import,
    delete or update a root or intermediate certificate authority in the local
    database
-   Import,
    delete or update a user certificate (with or without the associated private
    key) in the local database
-   Import
    the private key associated with a user certificate

Users with several certificates signed by different authorities
can import all their certificates with the same identifier.

> **Note:**
>
> Some command line  parameters are not available in the user interface.

## Parameters

Some parameters are available only in command line, as indicated in the table.

<table>
   <tbody>
      <tr>
         <td><p>CID = string</p>         </td>
         <td><p>Unique local identifier of the certificate to be created,
replaced or deleted.</p>         </td>
      </tr>
      <tr>
         <td><p>[CHECK = YES
| NO]</p>         </td>
         <td><p>Certificate check during import: this option is only applicable
for a user or intermediate authority certificate.</p>
<p>A check is performed:</p>
<ul>
<li>To establish
whether the root or intermediate authority certificate exists in the local
database</li>
<li>On the
certificate signature</li>
<li>To determine
whether the public key matches the private key (if the private key is
to be imported)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>[COMMENT = string1..64]</p>         </td>
         <td><p>Comment associated with the certificate: for the CREATE
or REPLACE operations only.</p>         </td>
      </tr>
      <tr>
         <td>IDATA         </td>
         <td>Source as base64 or PEM data instead of a file. If you use PKIUTIL IDATA, you cannot also use INAME, and vice versa.         </td>
      </tr>
      <tr>
         <td>IKDATA         </td>
         <td><p>Source as base64 or PEM data instead of a file. If you use PKIUTIL IKDATA, you cannot also use IKNAME, and vice versa.</p>         </td>
      </tr>
      <tr>
         <td><p>[IFORM = PKCS12 | DER
| PEM | PKCS7]</p>         </td>
         <td><p>Format of the certificate to be imported. It must be specified
if the INAME parameter is set.</p>         </td>
      </tr>
      <tr>
         <td><p>[IKFORM = PKCS8 | DER | PEM ]</p>         </td>
         <td><p>Format of the private key to be imported. This parameter
must be specified if the IKNAME parameter is set. <em>only in command line</em></p>         </td>
      </tr>
      <tr>
         <td><p>[IKNAME = string1..64]</p>         </td>
         <td><p>File from which the private key, which is associated with
a user certificate, to be imported or updated must be read.</p>
<ul>
<li>This parameter is not significant if the certificate format
is PKCS#12 as the certificate and private key are declared in the same
source file.</li>
<li>If you call PKIUTIL with IKDATA, you cannot use IKNAME.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>[IKPASSW = string1..64]</p>         </td>
         <td><p>Source file protection password. This is the source file protection password, and must be
specified for encrypted PEM (PKCS#5), PKCS#8 encrypted private key formats, PKCS#7, or for PKCS#12 certificate
formats.</p>
<p>There are two ways to specify the password:</p>
<ul>
<li>By
value: the value assigned to the parameter is used directly as a password</li>
<li>By
reference to a file: the value assigned to the parameter is the name
of a file, the first record of which contains the password; in this case,
the file name must be preceded
by a # or @ sign depending on the OS. On Windows, for example, IKPASSW=#myfile
where the password is specified in the <span class="code">myfile </span>file; the first file
record must contain the password in plain format.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>[INAME = string1..128]</p>         </td>
         <td><p>Source file containing the certificate to be imported or
updated.</p>
<ul>
<li>This parameter is not allowed in DELETE
mode.</li>
<li>If you call PKIUTIL with IDATA, you cannot use INAME.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>[ITYPE = ALL
| USER | ROOT | INTER]</p>         </td>
         <td><p>Type of certificate to be imported.</p>
<p>This parameter is mandatory for the modes DELETE (deleting a certificate from the database) and REPLACE (updating a certificate).</p>
<p>This field must be specified for an X.509 certificate,
Version 1 or 2. The type of an X.509 version 3 certificate is determined
automatically. For version 3, the ITYPE parameter is matched against the
type detected:</p>
<ul>
<li>ALL:
certificate type not checked <em>only in command line</em></li>
<li>USER:
user certificate</li>
<li>ROOT:
root authority certificate</li>
<li>INTER:
intermediate authority certificate</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>[MODE = REPLACE
| CREATE | DELETE]</p>         </td>
         <td><p>Action on the certificate. The REPLACE
action imports or updates an existing certificate in the database.</p>
<p>If importing a certificate chain, user certificate and
all intermediate authority certificates, all certificates are recorded
in the local database. The user certificate is recorded with the identifier
generated from the ID parameter. Intermediate authority certificates are
recorded with internal identifiers in the local internal datafile and cannot be
viewed. <em>only in command line</em></p>         </td>
      </tr>
      <tr>
         <td>[PASSWORD]         </td>
         <td><p>If you use a password, the PKICER certificate is exported in PKCS#12 format (rather than KPRIV).</p>
<p><em>Only available in command line</em></p>         </td>
      </tr>
      <tr>
         <td><p>[ROOTCID = string1..8]</p>         </td>
         <td><p>This parameter is mandatory for the DELETE (deletion of
a certificate from the database) and REPLACE (update of a certificate)
modes. It indicates the identifier of the authority of the certificate
to be deleted or updated.</p>
<p>This parameter must even be indicated for an authority
certificate. In this case, the ID and ROOTCID parameters have the same
value. <em>Only mandatory for DELETE and REPLACE in command line</em></p>         </td>
      </tr>
      <tr>
         <td><p>[STATE = ACT
| INACT]</p>         </td>
         <td><p>Status of the imported certificate.</p>
<p>By default, the certificate is active and can
be used by Transfer CFT.</p>         </td>
      </tr>
   </tbody>
</table>
