{
    "title": "Entities - PKIENTITY",
    "linkTitle": "Entities - PKIENTITY",
    "weight": "250"
}This topic describes how to create lists of certificate authority IDs in the PKI database.

The maximum number of CAs that you can enter for the ROOTCID parameter of the CFTSSL command is 10. To overcome this limitation, use the PKIENTITY object to create a list of up to 100 certificate authority IDs. You can then enter up to ten PKIENTITY objects in the CFTSSL ROOTCID parameter, to enable a maximum of 1000 certificate authorities IDs in the PKI database.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top"> You can directly update PKIENTITY content in the PKI internal datafile without  modifying Transfer CFT parameter settings.         </td>
      </tr>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Some command line  parameters are not available in the user interface.          </td>
      </tr>
</table>

## Define a certificate list

To define a certificate list, use the PKIENTITY parameters:

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Parameter</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr valign="top">
         <td>
               <li>ID               </li>
         </td>
         <td width="47.156%">
               <li>An identifier is a case-insensitive string with a maximum of 32 characters. If the identifier contains spaces, enclose the identifier in single quotes. (<i>mandatory</i><i>parameter</i>)               </li>
         </td>
      </tr>
      <tr valign="top">
         <td>
               <li>CERTIFICATES<br/>               </li>
         </td>
         <td width="47.156%">A list of up to 100 certificate IDs. Each ID is a case-insensitive string with a maximum of 32 characters.  There is no check other than syntax when you insert this parameter,  so if you use an ID in the CERTIFICATES list that is the same as a PKIENTITY object ID <span>Transfer CFT</span> ignores this ID when loading CFTSSL properties.         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1">
            <p>MODE</p>
         </td>
         <td colspan="1" rowspan="1" width="47.156%">
            <p>An action on the certificate, CREATE, REPLACE, or DELETE.  (default = REPLACE)</p>
         </td>
      </tr>
      <tr valign="top">
         <td>PKIFNAME         </td>
         <td width="47.156%"> The name of the PKI internal datafile to use. (default = $CFTPKU)<i> only in command line</i>         </td>
      </tr>
   </tbody>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">See the <a href="../../../../transport_security_start_here/certificates/pkiutil_cli_intro/using_the_pkicer_command">PKICER</a> command for more information on certificate parameters and settings.         </td>
      </tr>
</table>

**Caution**  The PKIENTITY command neither checks nor manages the existing certificates in the internal PKI internal datafile when creating a new certificates list.
