{
    "title": "Entities - PKIENTITY",
    "linkTitle": "Entities - PKIENTITY",
    "weight": "250"
}This topic describes how to create lists of certificate authority IDs in the PKI database.

The maximum number of CAs that you can enter for the ROOTCID parameter of the CFTSSL command is 10. To overcome this limitation, use the PKIENTITY object to create a list of up to 100 certificate authority IDs. You can then enter up to ten PKIENTITY objects in the CFTSSL ROOTCID parameter, to enable a maximum of 1000 certificate authorities IDs in the PKI database.

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">You can directly update PKIENTITY content in the PKI internal datafile without modifying Transfer CFT parameter settings.         </td>
      </tr>
   </tbody>
</table>

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">Some command line  parameters are not available in the user interface.         </td>
      </tr>
   </tbody>
</table>

## Define a certificate list

To define a certificate list, use the PKIENTITY parameters:

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>Parameter</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd" data-valign="top">
         <td>ID         </td>
         <td width="47.156%">An identifier is a case-insensitive string with a maximum of 32 characters. If the identifier contains spaces, enclose the identifier in single quotes. (<em>mandatoryparameter</em>)         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td>CERTIFICATES<br />
         </td>
         <td width="47.156%">A list of up to 100 certificate IDs. Each ID is a case-insensitive string with a maximum of 32 characters. There is no check other than syntax when you insert this parameter, so if you use an ID in the CERTIFICATES list that is the same as a PKIENTITY object ID <span>Transfer CFT</span> ignores this ID when loading CFTSSL properties.         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td>            <p>MODE</p>         </td>
         <td width="47.156%">            <p>An action on the certificate, CREATE, REPLACE, or DELETE. (default = REPLACE)</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td>PKIFNAME         </td>
         <td width="47.156%">The name of the PKI internal datafile to use. (default = $CFTPKU) <em>only in command line</em>         </td>
      </tr>
   </tbody>
</table>

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">See the <a href="../../../transport_security_start_here/certificates/pkiutil_cli_intro/using_the_pkicer_command">PKICER</a> command for more information on certificate parameters and settings.         </td>
      </tr>
   </tbody>
</table>

**Caution**  The PKIENTITY command neither checks nor manages the existing certificates in the internal PKI internal datafile when creating a new certificates list.
