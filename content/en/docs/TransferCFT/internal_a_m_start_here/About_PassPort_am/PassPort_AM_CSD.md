{
    "title": "PassPort AM CSD",
    "linkTitle": "PassPort AM CSD",
    "weight": "190"
}This section describes how to configure access management when not using Central Governance.

The PassPort CSD file provides resources and available actions for Transfer CFT. This CSD file must be accessible on your file system.

After installing Transfer CFT, access the CSD file at:

> &lt;Transfer CFT install directory>/home/distrib/am/csd\_Transfer\_CFT.xml

Available <span id="CSD description"></span>CSD actions and resources

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Type of information</th>
         <th>Description</th>
      </tr>
   </thead>
      <tr>
         <td>
            <p>Context</p>
         </td>
         <td>
            <p>Context range is limited to date and time.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Resources</p>
         </td>
         <td>
            <p>Resources are limited to MESSAGES, BASE, and SERVER.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>Actions </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Customize the actions that can be made on each resource.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>Privileges </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Customize the rights to perform one or more actions on a resource.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>Roles </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Customize the sets of privileges assigned to each role.</p>
         </td>
      </tr>
</table>

For more information on customizing the CSD file, refer to the Axway PassPort
AM documentation available at [support.axway.com]().

Related topics

-   [About PassPort AM](..//transfercft/internal_a_m_start_here/about_passport_am)
-   [Configuring PassPort AM](../configure_passport_am)
-   [Configuring PassPort AM SSL](configure_ssl_for_passport_am.htm)
