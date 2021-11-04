{
    "title": "Predefined privileges",
    "linkTitle": "Predefined privileges",
    "weight": "120"
}<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> provides the following predefined privileges. For additional information on the predefined privileges, refer to the *Administrative roles* section in the *Advanced account administration* chapter of the <span class="redirect_st_ag" cshid="admin" data-version="5.3.5">*<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Administrator's Guide*</span>.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Privilege         </th>
<th class="HeadE-Column1-Header1">Description         </th>
<th class="HeadD-Column1-Header1">Actions         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>account         </td>
         <td>Account Manager         </td>
         <td>View, Modify         </td>
      </tr>
      <tr>
         <td>admin         </td>
         <td>Master Administrator         </td>
         <td>Unlimited permissions         </td>
      </tr>
      <tr>
         <td>application         </td>
         <td>Application Manager         </td>
         <td>View, Modify         </td>
      </tr>
      <tr>
         <td>dbsetup         </td>
         <td>Database Administrator         </td>
         <td>View, Modify         </td>
      </tr>
      <tr>
         <td>setup         </td>
         <td>Setup Administrator         </td>
         <td>View, Modify         </td>
      </tr>
      <tr>
         <td>routes         </td>
         <td>Routes Manager         </td>
         <td>View, Modify         </td>
      </tr>
   </tbody>
</table>

## Account manager

This role enables the Account and Access menus. Users with this role can perform all tasks on the menus. This role groups the following privileges:

-   Manage user accounts, service accounts, site and account templates, and business units
-   Manage user classes and filesystem restrictions

## Application manager

The role enables the Account and Application menus. Users with this role can perform all tasks on the Application menu and one task on the Account menu. This role groups the following privileges:

-   Manage service accounts
-   Manage applications

## Database administrator

This role enables the Setup menu. Users with this role can manage database connection settings. This role groups the following privileges:

-   Manage DB connection settings such as host, port, and password

## Setup administrator

This role enables the Configuration menu. Users with this role can perform post-installation tasks. This role groups the following privileges:

-   Install licenses
-   Change default keystore password
-   Regenerate CA and certificates
-   Configure database settings

## Master administrator

This role enables all the menus. Users with this role have unlimited authority to perform all tasks.

## Delegated administrator

This role is customizable and enables different menus depending on its configuration. Users with this role can perform various tasks on specific user groups know as business units.
