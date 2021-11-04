{
    "title": "Entities - PKIENTITY",
    "linkTitle": "Entities - PKIENTITY",
    "weight": "240"
}This topic describes how to create lists of certificate authority IDs in the PKI database.

The maximum number of CAs that you can enter for the ROOTCID parameter of the CFTSSL command is 10. To overcome this limitation, use the PKIENTITY object to create a list of up to 100 certificate authority IDs. You can then enter up to ten PKIENTITY objects in the CFTSSL ROOTCID parameter, to enable a maximum of 1000 certificate authorities IDs in the PKI database.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>You can directly update PKIENTITY content in the PKI internal datafile without modifying Transfer CFT parameter settings.         </td>
      </tr>
   </tbody>
</table>

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>Some command line  parameters are not available in the user interface.         </td>
      </tr>
   </tbody>
</table>

## Define a certificate list

To define a certificate list, use the PKIENTITY parameters:

<table>
   <th>
      <tr>
<th>Parameter         </th>
<th>Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>ID         </td>
         <td>An identifier is a case-insensitive string with a maximum of 32 characters. If the identifier contains spaces, enclose the identifier in single quotes. (<em>mandatoryparameter</em>)         </td>
      </tr>
      <tr>
         <td>CERTIFICATES<br />
         </td>
         <td>A list of up to 100 certificate IDs. Each ID is a case-insensitive string with a maximum of 32 characters. There is no check other than syntax when you insert this parameter, so if you use an ID in the CERTIFICATES list that is the same as a PKIENTITY object ID <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> ignores this ID when loading CFTSSL properties.         </td>
      </tr>
      <tr>
         <td><p>MODE</p>         </td>
         <td><p>An action on the certificate, CREATE, REPLACE, or DELETE. (default = REPLACE)</p>         </td>
      </tr>
      <tr>
         <td>PKIFNAME         </td>
         <td>The name of the PKI internal datafile to use. (default = $CFTPKU) <em>only in command line</em>         </td>
      </tr>
   </tbody>
</table>

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>See the <a href="../../../../transport_security_start_here/certificates/pkiutil_cli_intro/using_the_pkicer_command">PKICER</a> command for more information on certificate parameters and settings.         </td>
      </tr>
   </tbody>
</table>

**Caution**  The PKIENTITY command neither checks nor manages the existing certificates in the internal PKI internal datafile when creating a new certificates list.
