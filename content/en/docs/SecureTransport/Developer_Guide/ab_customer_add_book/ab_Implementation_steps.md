{
    "title": "Custom Address Book implementation steps",
    "linkTitle": "Custom Address Book implementation steps",
    "weight": "110"
}To implement a custom Address Book (AB), execute the following steps:

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Step         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><a href="../ab_provider_class" class="MCXref xref">Create a provider class</a>         </td>
         <td>Used to hold the main logic for an address book. It is responsible for returning Address Book entries specified by search criteria.         </td>
      </tr>
      <tr>
         <td><a href="../ab_criterion_class" class="MCXref xref">Create a criteria class</a>         </td>
         <td>Used to define the Address Book search criteria for entries.         </td>
      </tr>
      <tr>
         <td><a href="../ab_confi_class" class="MCXref xref">Create a configuration class</a>         </td>
         <td>Used as the configuration settings for an Address Book.         </td>
      </tr>
      <tr>
         <td><a href="../ab_register_provider" class="MCXref xref">Register Address Book provider</a>         </td>
         <td>Every Address Book provider must be packaged in a specific way in order to be registered correctly into {{< SecureTransport/securetransportname  >}} system.         </td>
      </tr>
   </tbody>
</table>
