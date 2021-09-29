{
    "title": "Using ACT and INACT",
    "linkTitle": "Using ACT and INACT",
    "weight": "240"
}# <span id="Using_the_ACT_and_INACT_commands"></span>Using the ACT and INACT commands

## Activating or deactivating a certificate

Syntax

ACT or INACT

ROOTCID     =    
string,

ID = string,

\[INUM = number,\]

TYPE = string

<table data-cellspacing="0">
<tbody>
<tr class="odd" data-valign="top">
<td width="22.124%"><p>Description</p></td>
<td colspan="2" width="77.876%"><p>Use the ACT and INACT commands to activate or deactivate
one or more certificates in the local database. If a root
or intermediate authority certificate is deactivated, all dependent certificates
(user or intermediate authorities) are automatically deactivated.</p>
<p>The syntax is the same for both commands.</p></td>
</tr>
<tr class="even" data-valign="top">
<td rowspan="4" width="22.124%"><p>Parameters</p></td>
<td width="30.803%"><p>ID = string1..8</p></td>
<td width="47.073%"><p>Unique local identifier of the certificate(s) to be activated
or deactivated, depending on the command.</p>
<p>The * and ? wildcard characters are accepted for the ID
parameter value.</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="30.803%">[ INUM= number1..99]</td>
<td width="47.073%"><p>Internal number for the intermediate certificates in an imported chain of certificates (in the PKI database).</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="30.803%">[PKIFNAME = string1..64]</td>
<td width="47.073%">[PKIFNAME = string1..64] <em>Obsolete for Windows/Unix.</em></td>
</tr>
<tr class="odd" data-valign="top">
<td width="30.803%"><p>ROOTCID = string1..8</p></td>
<td width="47.073%"><p>Local identifier of the authority of the certificates to
be enabled/disabled.</p>
<p>This parameter must even be indicated for an authority certificate.
In this case, the ID and ROOTCID parameters have the same value.</p></td>
</tr>
<tr class="even" data-valign="top">
<td> </td>
<td width="30.803%">TYPE = KEY</td>
<td width="47.073%">To activate/deactivate the PKIKEY.</td>
</tr>
</tbody>
</table>
