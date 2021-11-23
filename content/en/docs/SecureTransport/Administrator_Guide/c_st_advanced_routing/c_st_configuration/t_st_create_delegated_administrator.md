{
    "title": "Advanced Routing delegated administrator",
    "linkTitle": "Advanced Routing delegated administrator",
    "weight": "210"
}The configuration of a delegated administrator for {{< SecureTransport/advancedrouting  >}} requires creating an {{< SecureTransport/advancedrouting  >}} administrator role and creating an {{< SecureTransport/advancedrouting  >}} administrator with the specified administrator settings. The following topics provide the configuration details for creating the role of {{< SecureTransport/advancedrouting  >}} administrator and assigning the role to the {{< SecureTransport/advancedrouting  >}} administrator.

The following topics provide how-to instructions for creating an {{< SecureTransport/advancedrouting  >}} administrator role and creating an {{< SecureTransport/advancedrouting  >}} administrator:

-   [Create Advanced Routing administrator role](#Create_role)
-   [Create Advanced Routing administrator](#Create_admin)

**Related topics:**

-   [Create user accounts](../t_st_create_user_accounts)
-   [Create Advanced Routing application](../t_st_create_advanced_routing_application)
-   [Manage Route Package Templates](../t_st_manage_route_package_templates)
-   [Manage Routes](../t_st_manage_routes)
-   [Subscribe to Advanced Routing application](../t_st_subscribe_advanced_routing_application)
-   [Assign Route Package Template](../t_st_assign_route_package_template)

<span id="Create_role"></span>

## Create {{< SecureTransport/advancedrouting  >}} administrator role

For details on creating administrative roles, refer to [Administrative roles](../../../c_st_advancedaccountadministration/c_st_administrativeroles). The {{< SecureTransport/advancedrouting  >}} administrator role should be created with the same settings as a delegated administrator plus the selection of *Route Packages* as shown in the following table and figure.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Function         </th>
<th class="HeadD-Column1-Header1">Selections         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Role Name:         </td>
         <td>{{< SecureTransport/advancedrouting  >}} Administrator         </td>
      </tr>
      <tr>
         <td>Role Type:         </td>
         <td>Limited         </td>
      </tr>
      <tr>
         <td>Bounce:         </td>
         <td>Prohibited         </td>
      </tr>
      <tr>
         <td>Accessible Menus         </td>
      </tr>
      <tr>
         <td>Operations         </td>
         <td>No selections         </td>
      </tr>
      <tr>
         <td>Setup         </td>
         <td>Mail Templates         </td>
      </tr>
      <tr>
         <td>LDAP         </td>
         <td>No selections         </td>
      </tr>
      <tr>
         <td>Accounts         </td>
         <td>User Accounts, Unlicensed Users, Service Accounts, Import/Export, Administrators, Change Password, Account Templates, Site Templates, System. Business Units         </td>
      </tr>
      <tr>
         <td>Access         </td>
         <td>No selections         </td>
      </tr>
      <tr>
         <td>Application         </td>
         <td>Application         </td>
      </tr>
      <tr>
         <td>Routes         </td>
         <td>Route Packages         </td>
      </tr>
   </tbody>
</table>

<span id="Create_admin"></span>

## Create {{< SecureTransport/advancedrouting  >}} administrator

For details on creating administrators, refer to [Manage administrator accounts](../../../c_st_advancedaccountadministration/c_st_manageadministratoraccounts). An {{< SecureTransport/advancedrouting  >}} administrator should be created with settings as shown in the following table and figure.

> **Note:**
>
> At least one business unit must be assigned to the Advanced Routing administrator.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Function         </th>
<th class="HeadD-Column1-Header1">Selections         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Administrator Name:         </td>
         <td>User determined         </td>
      </tr>
      <tr>
         <td>Password:         </td>
         <td>User determined         </td>
      </tr>
      <tr>
         <td>Confirm Password:         </td>
         <td>Must match password entry         </td>
      </tr>
      <tr>
         <td>Administrative Role:         </td>
         <td>{{< SecureTransport/advancedrouting  >}} Administrator         </td>
      </tr>
      <tr>
         <td>Parent Administrator:         </td>
         <td>/admin         </td>
      </tr>
      <tr>
         <td>Assigned Business Units         </td>
         <td>User determined - At least one Business Unit should be assigned         </td>
      </tr>
      <tr>
         <td>{{< SecureTransport/advancedrouting  >}}<br />
Administrator Selections         </td>
         <td>Update Users, Business Units, Applications, Route Package Templates, 'External Script' Step         </td>
      </tr>
   </tbody>
</table>

> **Note:**
>
> Manage Route Package Templates and Manage 'External Script' Step must be selected.
