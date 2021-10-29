{
    "title": "Using PKIENTITY ",
    "linkTitle": "Using PKIENTITY",
    "weight": "280"
}## Create a list of certificate authority IDs

This topic describes how to create lists of certificate authority IDs in the PKI database.

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

## Define a certificate list

To define a certificate list, use the PKIENTITY command with the following parameters:

-   ID: An identifier is a case-insensitive string with a maximum of 32 characters. If the identifier contains spaces, enclose the identifier in single quotes. (*mandatory* *parameter*)
-   CERTIFICATES: A list of up to 100 certificate IDs. Each ID is a case-insensitive string with a maximum of 32 characters. There is no check other than syntax when you insert this parameter, so if you use an ID in the CERTIFICATES list that is the same as a PKIENTITY object ID Transfer CFT ignores this ID when loading CFTSSL properties.  
-   MODE: An action on the certificate, CREATE, REPLACE, or DELETE. (default = REPLACE)
-   PKIFNAME: The name of the PKI internal datafile to use. (default = $CFTPKU)

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">See the <a href="using_the_pkicer_command">PKICER</a> command for more information on certificate parameters and settings.         </td>
      </tr>
   </tbody>
</table>

**Caution**  The PKIENTITY command neither checks nor manages the existing certificates in the internal PKI internal datafile when creating a new certificates list.

Example

This example creates a PKIENTITY called new\_entity that has 3 certificates, CA1, CA2, and CA3.

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>PKIUTIL PKIENTITY id = new_entity, certificates = "(‘CA1’, ‘CA2’, ‘CA3’)"</p>         </td>
      </tr>
   </tbody>
</table>

In the CFTSSL definition that follows, the rootcid parameter has two identifiers. However, you cannot distinguish in this definition if the identifiers correspond to a PKIENTITY or a PKICER object.

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">The <span>rootcid </span>parameter in the CFTSSL object can contain certificate IDs (Root and Intermediate CAs), entities, or both.<br />
         </td>
      </tr>
   </tbody>
</table>

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>(CFTUTIL) CFTSSL id          = server_name,<br />
                 direct      = SERVER,</p>
            <p>                 usercid     = USER,<br />
                 rootcid      = (‘new_entity’, 'CA4'),</p>
            <p>                 ciphlist     = (61,60,59,53,47),</p>
            <p>                 verify      = required,<br />
                 mode        = replace      </p>         </td>
      </tr>
   </tbody>
</table>

The next example shows the PKIENTITY command equivalent in the rootcid (that is, the certificates defined earlier in this example).

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>(CFTUTIL) CFTSSL id          = server_name,<br />
                 direct      = SERVER,</p>
            <p>                 usercid     = USER,<br />
                 rootcid      =(‘CA1’, ‘CA2’, ‘CA3’, ‘CA4’),</p>
            <p>                 ciphlist     =(61,60,59,53,47),</p>
            <p>                 verify      = required,<br />
                 mode        = replace      </p>         </td>
      </tr>
   </tbody>
</table>

## Troubleshoot

The actions described in this section lead to a PKIU26E error. For more information, see [PKIUTIL error codes](../../../troubleshoot_intro/messages_and_error_codes_start_here/pkiutil_error_codes).

-   Inserting a PKIENTITY with MODE = CREATE using an ID that is already in the database. For example, here the ID entity5 already exists in the PKI database.

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>PKIU26E PKIENTITY _ Error ( PKI Record writing error {15008/0} () )</p>
            <p>PKIU00I PKIENTITY _ Failed (id entity5,certificates=‘CA5',mode=create)</p>         </td>
      </tr>
   </tbody>
</table>

-   Deleting a PKIENTITY that is not in the database. In this example, entity6 does not exist in the PKI database.

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>PKIU26E PKIENTITY _ Error ( No record found {15011/0} () )</p>
            <p>PKIU00I PKIENTITY _ Failed (id=entity6, mode=delete)</p>         </td>
      </tr>
   </tbody>
</table>

-   Inserting a PKIENTITY when there is already a PKICER certificate in the internal datafile with the same ID.

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>PKIU26E PKIENTITY _ Error ( PKI record conflict: existing certificate {15039/0} () )</p>
            <p>PKIU00I PKIENTITY _ Failed  (id=existing_PKICER,certificates=(an_id))</p>         </td>
      </tr>
   </tbody>
</table>

-   Inserting a PKICER when a PKIENTITY certificate exists with the same ID.

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>PKIU26E PKICER   _ Error ( PKI record conflict: existing entity {15038/0} () )</p>
            <p>PKIU00I PKICER   _ Failed  (id='existing_PKIENTITY',comment='Axway MFT </p>
            <p>PKIU00I     Demonstration Root Certificate"',iform='DER',iname</p>
            <p>PKIU00I   ='$CFTPKIDIR/Axway_MFT_Demonstration_Root_Certific</p>
            <p>PKIU00I     ate.der',itype='ROOT',pkifname='$CFTPKU'</p>
            <p>PKIU00I    'CFT',state='ACT',mode='CREATE')</p>         </td>
      </tr>
   </tbody>
</table>
