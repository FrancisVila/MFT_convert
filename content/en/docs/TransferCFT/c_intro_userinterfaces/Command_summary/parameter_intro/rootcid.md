{
    "title": "rootcid",
    "linkTitle": "rootcid",
    "weight": "2970"
}### <span id="rootcid"></span>rootcid

#### PKICER  

\[ ROOTCID = string 32 \]

This parameter must be indicated for a certificate authority.
In this case, the ID and ROOTCID parameters have the same value.

This parameter is mandatory for:

-   DELETE: deletion of a certificate
    from the database, and
-   REPLACE: update of a certificate, modes

It indicates
the identifier of the certificate authority to be deleted or updated.

#### PKIEXT, LISTPKI

\[ ROOTCID = string 32 \]

This parameter allows you to chose the ROOTCID of the certificates to extract or display, respectively.

Example

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>Id.       Root iNum T S C K E  Exp.Date   Delivered to  Delivered by</p>
<p>------------ ------------ ---- - - - - - ---------- ------------- -------------</p>
<p>2K_INTER  2K_ROOT I A x           22/07/2029  2k_l1_ca         2k_root</p>
<p>2K_ROOT   2K_ROOT R A x            22/07/2029  2k_root         2k_root</p>
<p>4K_ROOT   4K_ROOT R A x            28/07/2039  4k_root           4k_root</p>
<p>4K_USER   4K_ROOT U A x x        28/07/2039  4k_l1_user1   4k_root</p></td>
</tr>
</tbody>
</table>

PKIEXT example

The result is a file that contains only information about the 2K\_ROOT and 2K\_INTER certificates.

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>PKIUTIL PKIEXT FOUT=PKI.CMD, ROOTCID=2K_ROOT</p></td>
</tr>
</tbody>
</table>

LISTPKI example

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>PKIUTIL LISTPKI ROOTCID=4K_ROOT</p>
<p>Id. Root iNum T S C K E  Exp.Date   Delivered to  Delivered by</p>
<p>------------ ------------ ---- - - - - - ---------- ------------- -------------</p>
<p>4K_ROOT 4K_ROOT R A x     28/07/2039   4k_root      4k_root</p>
<p>4K_USER 4K_ROOT U A x x   28/07/2039   4k_l1_user1  4k_root</p></td>
</tr>
</tbody>
</table>

#### CFTSSL

\[ ROOTCID = string 32 \]

List of certificate authorities, where the total length of all identifiers cannot exceed 256 characters for CFTSSL. This list references a maximum of 10 identifiers in the local certificate database.

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">To use more than 10 identifiers, you can refer to the <a href="../../../../transport_security_start_here/certificates/pkiutil_cli_intro/pkientity">PKIENTITY</a> information.</td>
</tr>
</tbody>
</table>

In client mode, this list is used to check the server
certificate. Only certificates signed by one of the authorities in the
ROOTCID parameter are accepted.

 

[Return to Command index](../../)
