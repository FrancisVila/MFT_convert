{
    "title": "Using  the ACT and INACT commands",
    "linkTitle": "Using ACT and INACT",
    "weight": "230"
}## Activating or deactivating a certificate

Syntax

ACT or INACT

ROOTCID     =    
string,

ID = string,

\[INUM = number,\]

TYPE = string

<table>
   <tbody>
      <tr>
         <td><p>Description</p>         </td>
         <td><p>Use the ACT and INACT commands  to activate or deactivate
one or more certificates in the local database. If a root
or intermediate authority certificate is deactivated, all dependent certificates
(user or intermediate authorities) are automatically deactivated.</p>
<p>The syntax is the same for both commands.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>ID = string1..8</p>         </td>
         <td><p>Unique local identifier of the certificate(s) to be activated
or deactivated, depending on the command.</p>
<p>The * and ? wildcard characters are accepted for the ID
parameter value.</p>         </td>
      </tr>
      <tr>
         <td>[ INUM= number1..99]         </td>
         <td><p>Internal number for the intermediate certificates in an imported chain of certificates (in the PKI database).</p>         </td>
      </tr>
      <tr>
         <td>[PKIFNAME = string1..64]         </td>
         <td>[PKIFNAME = string1..64] <em>Obsolete for Windows/Unix.</em>         </td>
      </tr>
      <tr>
         <td><p>ROOTCID = string1..8</p>         </td>
         <td><p>Local identifier of the authority of the certificates to
be enabled/disabled.</p>
<p>This parameter must even be indicated for an authority certificate.
In this case, the ID and ROOTCID parameters have the same value.</p>         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>TYPE = KEY         </td>
         <td>To activate/deactivate the PKIKEY.         </td>
      </tr>
   </tbody>
</table>
