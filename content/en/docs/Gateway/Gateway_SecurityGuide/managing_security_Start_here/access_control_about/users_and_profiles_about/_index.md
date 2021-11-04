{
    "title": " ",
    "linkTitle": "Users and Profiles",
    "weight": "140"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Security

# Users and Profiles

## About Users and Profiles

[Users and Profiles](#users)

[Controlled elements](#elements)

[Access rights](#rights)

[Access to Transfer Requests](#trans_req)

This topic describes the <span style="font-style: italic;">User</span> and <span style="font-style: italic;">Profile</span> objects that Gateway uses to manage Access Control.

Alternatively you can use:

-   [PassPort AM](../passport_am_about) to manage User Access Control for all products of the <span class="mc-variable axway_variables.Platform_or_Suite_Short_Name variable">Axway Platform</span>.
-   [Customizable user exits](../access_control_using_exits) to manage Access Control on Gateway

<span id="users"></span>

### Users and Profiles

You define each Gateway <span style="font-weight: bold;">User</span> by specifying a unique name, an access password and the name of the Profile object with which the User is associated. All Users, apart from the Administrator, must be associated with a specific Profile. All Users associated with the same Profile have identical rights.

Users only have access to their own User records (records bearing their names), unless they are administrators.

For security reasons, you should restrict access to User and Profile objects to administrators only.

The <span style="font-weight: bold;">Profile</span> object defines the type of access rights that a user, or a set of users, has to specific objects or files. For example, a user may have <span style="font-style: italic;">read access</span> for Site objects and <span style="font-style: italic;">write access</span> for Application and Model objects.

<span id="elements"></span>

### Controlled elements

The objects and files that are subject to access control are:

<table>
   <thead>
      <tr>
<th class="HeadD-Column1-Header1"><p>Element</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Sites</p>         </td>
      </tr>
      <tr>
         <td><p>Applications</p>         </td>
      </tr>
      <tr>
         <td><p>Transfer Requests</p>         </td>
      </tr>
      <tr>
         <td><p>Models</p>         </td>
      </tr>
      <tr>
         <td><p>Diffusion Lists</p>         </td>
      </tr>
      <tr>
         <td><p>Users</p>         </td>
      </tr>
      <tr>
         <td><p>Profiles</p>         </td>
      </tr>
      <tr>
         <td><p>Log file</p>         </td>
      </tr>
      <tr>
         <td><p>CGates and CGateGroups</p>         </td>
      </tr>
      <tr>
         <td>Configuration         </td>
      </tr>
      <tr>
         <td>Audit         </td>
      </tr>
      <tr>
         <td><p>Virtual File Directory (VFD)</p>
<p>Used by administrators only for modifications</p>         </td>
      </tr>
      <tr>
         <td><p>Rule Tables</p>         </td>
      </tr>
      <tr>
         <td><p>Decision Rules</p>         </td>
      </tr>
      <tr>
         <td><p>Proxies</p>         </td>
      </tr>
      <tr>
         <td><p>Trading Partners</p>         </td>
      </tr>
      <tr>
         <td><p>Transfer security</p>         </td>
      </tr>
   </tbody>
</table>

<span id="rights"></span>

### Access rights

The types of access that you can assign are:

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Access</p>         </th>
<th class="HeadD-Column1-Header1"><p>Enables the user to...</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Read</p>         </td>
         <td><p>Retrieve or list the object</p>         </td>
      </tr>
      <tr>
         <td><p>Write</p>         </td>
         <td><p>Create a new instance of the object</p>         </td>
      </tr>
      <tr>
         <td><p>Update</p>         </td>
         <td><p>Modify object attributes</p>         </td>
      </tr>
      <tr>
         <td><p>Delete</p>         </td>
         <td><p>Remove the object</p>         </td>
      </tr>
      <tr>
         <td><p>Admin</p>         </td>
         <td><p>Perform all operations:</p>
<ul>
<li>Suspend, resume or cancel a Transfer</li>
<li>Enable or disable a Site</li>
<li>Suspend, restart or archive the log file</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

Since, logically, any update or delete action is always preceded by a read access, users with update or delete access rights must also have read access to an object or file.

<span id="trans_req"></span>

### Access to Transfer Requests

When users create Transfer Requests, they also need access to information on Site and Application objects. Therefore, a user with write (create) access to Transfer Request objects, must, as a minimum, have <span style="font-style: italic;">read</span> access to both Site and Application objects.

Typically, users only have access to Transfer Requests that they created. To grant user access to all Transfer Requests, you must assign the <span style="font-style: italic;">access all transfers</span> privilege.

Related topics

[About Access Control Management](../)

[Working with Users](managing_users)

[Working with User Profiles](managing_profiles)

[Working with Users (command line)](managing_users_cli)

[Working with Profiles (command line)](managing_users_cli/managing_profiles_cli)

[Access Control using exits](../access_control_using_exits)

[About PassPort AM](../passport_am_about)

[Working with PassPort AM](../passport_am_about/passport_am_working_with)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
