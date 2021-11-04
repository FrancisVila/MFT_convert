{
    "title": "PassPort AM",
    "linkTitle": "PassPort AM",
    "weight": "150"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Security

## About PassPort AM

Axway PassPort AM centralizes the management of users for all products of the <span class="mc-variable axway_variables.Platform_or_Suite_Short_Name variable">Axway Platform</span> platform. If you have installed PassPort AM, you can use it to define all your users and profiles. Gateway can then connect to PassPort AM to check user permissions.

PassPort AM provides control of:

-   Authentication  
    The authentication functionality handles the identification of a user via login and password.
-   Access control management  
    The access control management functionality restricts access to Gateway resources.

In PassPort AM, users are given role-based access and are assigned roles that define the privileges they have.

The use of PassPort AM is not mandatory. Like many other Axway products, Gateway also has its own method of managing users, based on [users and profiles](../users_and_profiles_about). When PassPort AM is selected, you cannot use Gateway's own user management (via the User and Profile objects). The two methods are exclusive.

To use this feature, select PassPort AM Access Control Management when installing or configuring Gateway.

There are some differences between using Gateway and PassPort AM for managing user access. For example, in Gateway, the Admin access right on a Transfer object enables the user to perform all Pause, Resume and Cancel actions. In PassPort AM however, separate actions exist: Pause, Resume and Cancel.

<span id="csd_file"></span>

### Component Security Descriptor (CSD) file

For each <span class="mc-variable axway_variables.Platform_or_Suite_Short_Name variable">Axway Platform</span> component, PassPort AM uses an XML-format Component Security Descriptor (CSD) file. Each CSD file contains access definitions relating to a specific <span class="mc-variable axway_variables.Platform_or_Suite_Short_Name variable">Axway Platform</span> component.

The CSD file for Gateway contains information about:

-   Component identification
-   Resources (Gateway objects - for example SITE)
-   Possible actions related to each resource (for example, view or create)

The CSD file for Gateway is provided with PassPort AM. After installing Gateway and PassPort AM, the CSD file must be imported.

<span id="resources"></span>

### Resources defined in the Gateway CSD file

<table>
   <thead>
      <tr>
<th class="HeadD-Column1-Header1"><p>Resource</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>SITE</p>         </td>
      </tr>
      <tr>
         <td><p>TRANSFER</p>         </td>
      </tr>
      <tr>
         <td><p>APPLICATION</p>         </td>
      </tr>
      <tr>
         <td><p>TRADING PARTNER</p>         </td>
      </tr>
      <tr>
         <td><p>CGATE</p>         </td>
      </tr>
      <tr>
         <td><p>CGATEGROUP</p>         </td>
      </tr>
      <tr>
         <td><p>LOGICAL SITE</p>         </td>
      </tr>
      <tr>
         <td><p>DIFFUSION LIST</p>         </td>
      </tr>
      <tr>
         <td><p>PROXY</p>         </td>
      </tr>
      <tr>
         <td><p>MODEL</p>         </td>
      </tr>
      <tr>
         <td><p>VFD</p>         </td>
      </tr>
      <tr>
         <td><p>DECISION RULE</p>         </td>
      </tr>
      <tr>
         <td><p>RULE TABLE</p>         </td>
      </tr>
      <tr>
         <td><p>CONNECTION</p>         </td>
      </tr>
      <tr>
         <td><p>CONNECTED USER</p>         </td>
      </tr>
      <tr>
         <td><p>LOG</p>         </td>
      </tr>
      <tr>
         <td><p>CERTIFICATE</p>         </td>
      </tr>
      <tr>
         <td><p>SPROF</p>         </td>
      </tr>
      <tr>
         <td><p>SSHPROF</p>         </td>
      </tr>
      <tr>
         <td><p>KEY</p>         </td>
      </tr>
      <tr>
         <td><p>NETPROF</p>         </td>
      </tr>
      <tr>
         <td><p>CONFIGURATION</p>         </td>
      </tr>
      <tr>
         <td>AUDIT         </td>
      </tr>
      <tr>
         <td>LOGIN         </td>
      </tr>
   </tbody>
</table>

<span id="actions"></span>

### Actions defined in the Gateway CSD file

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Action</p>         </th>
<th class="HeadD-Column1-Header1"><p>Comment</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>VIEW</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>CREATE</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>EDIT</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>DELETE</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>ACTIVATE</p>         </td>
         <td><p>For Sites</p>         </td>
      </tr>
      <tr>
         <td><p>DEACTIVATE</p>         </td>
         <td><p>For Sites</p>         </td>
      </tr>
      <tr>
         <td><p>MOUNT</p>         </td>
         <td><p>For VFDs</p>         </td>
      </tr>
      <tr>
         <td><p>UNMOUNT</p>         </td>
         <td><p>For VFDs</p>         </td>
      </tr>
      <tr>
         <td><p>PAUSE</p>         </td>
         <td><p>For Transfers &amp; Logs</p>         </td>
      </tr>
      <tr>
         <td><p>RESUME</p>         </td>
         <td><p>For Transfers &amp; Logs</p>         </td>
      </tr>
      <tr>
         <td><p>CANCEL</p>         </td>
         <td><p>For Transfers</p>         </td>
      </tr>
      <tr>
         <td><p>DISCONNECT</p>         </td>
         <td><p>For Connections and Connected Users</p>         </td>
      </tr>
      <tr>
         <td><p>RESET</p>         </td>
         <td><p>For Connected Users</p>         </td>
      </tr>
      <tr>
         <td><p>ARCHIVE</p>         </td>
         <td><p>For Logs</p>         </td>
      </tr>
      <tr>
         <td>LOGIN_WITH_OLDER_API         </td>
         <td>For LOGIN resource - allow login to Gateway server using older client version. Used for the LOGIN_XIB predefined privilege.         </td>
      </tr>
   </tbody>
</table>

<span style="font-weight: bold;">Note:</span> The actions available depend on the resource.

Related topics

[About Access Control Management](../)

[Working with PassPort AM](passport_am_working_with)

 

For more information

For information about PassPort AM, refer to the Axway PassPort AM documentation.

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
