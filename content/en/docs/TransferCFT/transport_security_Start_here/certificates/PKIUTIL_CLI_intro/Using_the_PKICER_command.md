{
    "title": "Using PKICER",
    "linkTitle": "Using PKICER",
    "weight": "250"
}# <span id="Using_the_PKICER_command"></span>Using the PKICER command

Use the PKICER command to:

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

## Working with certificates

Syntax

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>PKICER</p>
<p>ID    
=     string,</p>
<div>
<p>[CHECK    
=     {YES | NO},]</p>
<p>[COMMENT  
=     string,]</p>
<p>[IDATA     
=     string,]</p>
<p>[IFORM    
=     {PKCS12 | DER | PEM | PKCS7,]</p>
<p>[IKDATA    
=     {base64/PEM},]</p>
<p>[IKFORM   
=     {DER | PEM | PKCS8},]</p>
<p>[IKNAME   
=     string,]</p>
<p>[IKPASSW  
=   string,]</p>
<p>[INAME    
=     string,]</p>
<p>[ITYPE    
=     {ALL | USER | ROOT | INTER},]</p>
<p>[MODE    
=     {REPLACE | CREATE | DELETE},]</p>
<p>[STATE    
=     {ACT | INACT},]</p>
<p>[ROOTCID  
=     string,]</p>
<p>[PKICER    = string,]</p>
</div></td>
</tr>
</tbody>
</table>

Some parameters are available only in command line, as indicated in the table.

<table data-cellspacing="0">
<tbody>
<tr class="odd" data-valign="top">
<td width="23.061%"><p>ID = string1..32</p></td>
<td width="54.815%"><p>Unique local identifier of the certificate to be created,
replaced or deleted.</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="23.061%"><p>[CHECK = YES
| NO]</p></td>
<td width="54.815%"><p>Certificate check during import: this option is only applicable
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
</ul>
<p>Command line only</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="23.061%"><p>[COMMENT = string1..64]</p></td>
<td width="54.815%"><p>Comment associated with the certificate: for the CREATE
or REPLACE operations only.</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="23.061%">IDATA</td>
<td width="54.815%">Source as base64 or PEM data instead of a file. If you use PKIUTIL IDATA, you cannot also use INAME, and vice versa.</td>
</tr>
<tr class="odd" data-valign="top">
<td width="23.061%">IKDATA</td>
<td width="54.815%"><p>Source as base64 or PEM data instead of a file. If you use PKIUTIL IKDATA, you cannot also use IKNAME, and vice versa.</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="23.061%"><p>[IFORM = PKCS12 | DER
| PEM | PKCS7]</p></td>
<td width="54.815%"><p>Format of the certificate to be imported. It must be specified
if the INAME parameter is set.</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="23.061%"><p>[IKFORM = PKCS8 | DER | PEM ]</p></td>
<td width="54.815%"><p>Format of the private key to be imported. This parameter
must be specified if the IKNAME parameter is set.</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="23.061%"><p>[IKNAME = string1..64]</p></td>
<td width="54.815%"><p>File from which the private key, that is associated with
a user certificate, to be imported or updated must be read.</p>
<ul>
<li>This parameter is not significant if the certificate format
is PKCS#12 as the certificate and private key are declared in the same
source file.</li>
<li>If you call PKIUTIL with IKDATA, you cannot use IKNAME.</li>
</ul></td>
</tr>
<tr class="odd" data-valign="top">
<td width="23.061%"><p>[IKPASSW = string1..64]</p></td>
<td width="54.815%"><p>Source file protection password. This is the source file protection password, and must be
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
where the password is specified in the <span>myfile </span>file; the first file
record must contain the password in plain format.</li>
</ul></td>
</tr>
<tr class="even" data-valign="top">
<td width="23.061%"><p>[INAME = string1..128]</p></td>
<td width="54.815%"><p>Source file containing the certificate to be imported or
updated.</p>
<ul>
<li>This parameter is not allowed in DELETE
mode.</li>
<li>If you call PKIUTIL with IDATA, you cannot use INAME.</li>
</ul></td>
</tr>
<tr class="odd" data-valign="top">
<td width="23.061%"><p>[ITYPE = ALL
| USER | ROOT | INTER]</p></td>
<td width="54.815%"><p>Type of certificate to be imported.</p>
<p>This parameter is mandatory for the modes DELETE (deleting a certificate from the database) and REPLACE (updating a certificate).</p>
<p>This field must be specified for an X.509 certificate,
Version 1 or 2. The type of an X.509 version 3 certificate is determined
automatically. For version 3, the ITYPE parameter is matched against the
type detected:</p>
<ul>
<li>ALL:
certificate type not checked</li>
<li>USER:
user certificate</li>
<li>ROOT:
root authority certificate</li>
<li>INTER:
intermediate authority certificate</li>
</ul></td>
</tr>
<tr class="even" data-valign="top">
<td width="23.061%"><p>[MODE = REPLACE
| CREATE | DELETE]</p></td>
<td width="54.815%"><p>Action on the certificate. The REPLACE
action imports or updates an existing certificate in the database.</p>
<p>If importing a certificate chain, user certificate and
all intermediate authority certificates, all certificates are recorded
in the local database. The user certificate is recorded with the identifier
generated from the ID parameter. Intermediate authority certificates are
recorded with internal identifiers in the local internal datafile and cannot be
viewed.</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="23.061%">[PASSWORD]</td>
<td width="54.815%">If you use a password, the PKICER certificate is exported in PKCS#12 format (rather than KPRIV).</td>
</tr>
<tr class="even" data-valign="top">
<td width="23.061%"><p>[ROOTCID = string]</p></td>
<td width="54.815%"><p>This parameter is mandatory for the DELETE (deletion of
a certificate from the database) and REPLACE (update of a certificate)
modes. It indicates the identifier of the authority of the certificate
to be deleted or updated.</p>
<p>This parameter must even be indicated for an authority
certificate. In this case, the ID and ROOTCID parameters have the same
value.</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="23.061%"><p>[STATE = ACT
| INACT]</p></td>
<td width="54.815%"><p>Status of the imported certificate.</p>
<p>By default, the certificate is active and can
be used by Transfer CFT.</p></td>
</tr>
</tbody>
</table>
