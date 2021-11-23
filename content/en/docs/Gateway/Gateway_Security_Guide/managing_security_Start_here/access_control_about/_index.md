{
    "title": "Access Control Management",
    "linkTitle": "Access Control Management",
    "weight": "120"
}{{< Gateway/componentlongname  >}}: Managing Security

## About Access Control Management

You can manage user Access Control in Gateway using any of the following methods:

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>Method</p>         </td>
         <td><p>Description</p>         </td>
      </tr>
      <tr>
         <td><p><a href="users_and_profiles_about">Gateway</a></p>         </td>
         <td><p>Users are managed by <em>User</em> and <em>Profile</em> objects in Gateway.</p>
<p>Users must supply their authentication (user ID and password) in their login request.</p>
<p>Access control is based on object type.</p>
<p>A user with authorized access to a type of object has the same access to all instances of that object type.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="access_control_using_exits">Customizable user exits</a></p>         </td>
      </tr>
      <tr>
         <td><p><a href="passport_am_about">PassPort AM</a></p>         </td>
         <td><p>Users are managed by Axway PassPort AM.</p>
<p>Access control is managed centrally for all products of the {{< Gateway/platformorsuiteshortname  >}}.</p>         </td>
      </tr>
   </tbody>
</table>

These User Access Control methods are mutually exclusive. When one method is selected, you cannot use another one at the same time.

### User Access Control of Gateway objects

User Access Control applies to Gateway objects, whatever the interface used: the Gateway GUI, command lines, APIs or the Axway MFT Navigator.

### Users and Profile objects

The *User* and *Profile* objects in Gateway enable you to define user identification and access rights. Typically only Administrators have access to these objects.

##### Users

The *User* object defines properties for each user:

-   Name and password
-   Group for the user
-   Profile for the user (all users must be associated with a user Profile)

##### Profiles

The *Profile* object defines the type of operations a set of users can perform on each Gateway object. All users associated with the same user Profile have identical access rights. You can define authorization for the following types of operation:

-   Read: retrieve or list objects
-   Write: create new instance of an object
-   Update: modify attributes of an object
-   Delete: remove objects
-   Admin: suspend, remove or cancel Transfer Requests, enable or disable Sites, suspend, restart or archive the log file

The Profile object specifies the authorized operations on the following objects:

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><ul>
<li>Applications</li>
<li>CGates</li>
<li>Decision Rules</li>
<li>Diffusion Lists</li>
</ul>         </td>
         <td><ul>
<li>Log</li>
<li>Models</li>
<li>Profiles</li>
<li>Proxies</li>
</ul>         </td>
         <td><ul>
<li>Sites</li>
<li>Transfers</li>
<li>Users</li>
<li>VFD</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

For example, you could specify that all Users associated with a given Profile are authorized to access Site objects in Read and Write mode only.

**Note**: A user only has access to the elements defined in his profile.

Related topics

[Working with Users](users_and_profiles_about/managing_users)

[Working with User Profiles](users_and_profiles_about/managing_profiles)

[About Users and Profiles](users_and_profiles_about)

[Access Control using exits](access_control_using_exits)

[About PassPort AM](passport_am_about)

 

Links to documentation set for Axway Gateway {{< Gateway/releasenumber  >}}:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
