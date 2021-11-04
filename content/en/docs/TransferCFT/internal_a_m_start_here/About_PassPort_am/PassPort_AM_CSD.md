{
    "title": "About the PassPort CSD",
    "linkTitle": "PassPort AM CSD",
    "weight": "190"
}This section describes how to configure access management when not using <span class="mc-variable Primary.CG or_UM variable">Central Governance</span>.

The PassPort CSD file provides resources and available actions for Transfer CFT. This CSD file must be accessible on your file system.

After installing Transfer CFT, access the CSD file at:

> &lt;Transfer CFT install directory>/home/distrib/am/csd\_Transfer\_CFT.xml

Available <span id="CSD description"></span>CSD actions and resources

<table>
   <th>
      <tr>
<th>Type of information         </th>
<th>Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Context</p>         </td>
         <td><p>Context range is limited to date and time.</p>         </td>
      </tr>
      <tr>
         <td><p>Resources</p>         </td>
         <td><p>Resources are limited to MESSAGES, BASE, and SERVER.</p>         </td>
      </tr>
      <tr>
         <td><p>Actions</p>         </td>
         <td><p>Customize the actions that can be made on each resource.</p>         </td>
      </tr>
      <tr>
         <td><p>Privileges</p>         </td>
         <td><p>Customize the rights to perform one or more actions on a resource.</p>         </td>
      </tr>
      <tr>
         <td><p>Roles</p>         </td>
         <td><p>Customize the sets of privileges assigned to each role.</p>         </td>
      </tr>
   </tbody>
</table>

For more information on customizing the CSD file, refer to the <span class="mc-variable axway_variables.Company_Name variable">Axway</span> PassPort
AM documentation available at [support.axway.com]().

Related topics

-   [About PassPort AM](../)
-   [Configuring PassPort AM](../configure_passport_am)
-   Configuring PassPort AM SSL
