{
    "title": "CFTROLE",
    "linkTitle": "Roles - CFTROLE",
    "weight": "270"
}Set the roles, which define a type of user and application permission. See also <a href="../../../../internal_a_m_start_here/fm_access_management" class="MCXref xref">Access Management using Flow Manager</a>

### Using CFTROLE

A role is a general profile that can be associated with a user. A role is based on one or more privileges, and a privilege is based on a resource. There are two types of roles: predefined and user-defined. Predefined roles are available by default to assign to users.

You can assign users to one or more roles. Typically, users with multiple roles have more privileges than users with fewer roles.

Examples of roles can be ADMINISTRATOR, PARTNER MANAGER, IT MANAGER, and so on.

<table>
   <th>
      <tr>
<th><p>Field</p>         </th>
<th><p>Type</p>         </th>
<th><p>Comment</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>id</p>         </td>
         <td><p>String32</p>         </td>
         <td><p>Role identifier</p>         </td>
      </tr>
      <tr>
         <td><p>comment</p>         </td>
         <td><p>String80</p>         </td>
         <td><p>Comment</p>         </td>
      </tr>
      <tr>
         <td><p>privs[]</p>         </td>
         <td><p>List of String32</p>         </td>
         <td><p>List of privileges associated to this role (1 to 128)</p>         </td>
      </tr>
   </tbody>
</table>

Example of CFTROLE in a configuration file:



    CFTROLE      ID          = 'Application',
                 COMMENT     = 'My comments',
                 PRIVS       = ( 'SERVICE:UI_CONNECT',
                                 'MYPRIV1',
                                 'CONFIGURATION:CFTCOM_VIEW',
                                 'CONFIGURATION:CFTPARM_VIEW',
                                 'CONFIGURATION:CFTPART_VIEW',
                                 'CONFIGURATION:CFTDEST_VIEW',
                                 'CONFIGURATION:CFTSEND_VIEW',
                                 'CONFIGURATION:CFTRECV_VIEW',
                                 'CONFIGURATION:CFTLOG_VIEW',
                                 'FILTER:CATALOG_ALL',
                                 'FILTER:LOG_ALL',
                                 'FILE_VIEW'),
                 ORIGIN      = 'CFTUTIL',
                 MODE        = 'REPLACE'
