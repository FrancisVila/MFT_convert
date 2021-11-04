{
    "title": "Working with Users (command line)",
    "linkTitle": "Command line operations",
    "weight": "180"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Security

<span class="code" style="font-weight: bold;">[peladm create\_user](#peladm_create_user)</span>

<span class="code" style="font-weight: bold;">[peladm delete\_user](#delete_user)</span>

<span class="code" style="font-weight: bold;">[peladm update\_user](#update_user)</span>

<span class="code" style="font-weight: bold;">[peldsp display\_user](#display_user)</span>

<span class="code" style="font-weight: bold;">[peldsp select\_user](#select_user)</span>

<span id="peladm_create_user"></span>

## Creating a User: peladm create\_user

<table>
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p>peladm create_user (<span style="font-weight: normal;">-username</span>) [<span style="font-style: italic;font-weight: normal;">-optional parameters</span><span style="font-style: italic;font-weight: normal;">, see below</span>]</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>This command is reserved for administrators only.</p>
<p>Use this command to create a new user.</p>
<p>All parameters apart from <span class="code">username</span> are optional.</p>
<p>The Profile that you specify must be defined in the Profile database.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>Mandatory</p>
<p><span class="code">-username (-un)</span>: Login name for this user</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-profile (-pr)</span>: Access profile name for this user</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-group (-gr)</span>: Group name for this user</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-password (-pswd)</span>: Password for this user</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-comments (-cts)</span>: Enter a free-text description of up to 80 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-expired (-exd)</span>: Enter an expiration date in the format <span style="font-style: italic;">YYYYDDMM HHMMSS</span></p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-maxretry (-mxr)</span>: Enter a number between 0 and 999 for the maximum number of connection retries allowed (default = 0)</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-administrator (-admin)</span>: Define the user as an administrator or not.</p>
<p>Enter one of the values:</p>
<ul>
<li><span style="font-weight: bold;">N</span>: non-administrator users</li>
<li><span style="font-weight: bold;">Y</span>: administrator users (default)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-allxfer (-ax)</span>: Defines the user with/without access to all transfers.</p>
<p>Enter one of the values:</p>
<ul>
<li><span style="font-weight: bold;">N</span>: non-administrator users (default)</li>
<li><span style="font-weight: bold;">Y</span>: administrator users</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-disabled (-dd)</span>: Enables/disables User.</p>
<p>Enter one of the values:</p>
<ul>
<li><span style="font-weight: bold;">N</span>: non-administrator users (default)</li>
<li><span style="font-weight: bold;">Y</span>: administrator users</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-allow_old_ver (-aov)</span> : Allow login from this user when connecting with an older API version. Useful especially for XIB users, where the API update is not in sync with Gateway release.
Enter one of the values:</p>
<ul>
<li><strong>N</strong>: don't allow</li>
<li><strong>Y</strong>: allow</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>Enter the command:</p>
<p>peladm create_user</p>
<p>-username USERONE</p>
<p>-password passone</p>
<p>-comments "Gateway administrator"</p>
<p>-group admin</p>
<p>-administrator Y</p>
<p>Gateway creates a new User with the name <span style="font-style: italic;">USERONE</span>, the password <span style="font-style: italic;">passone</span>, who belongs to the Group <span style="font-style: italic;">admin</span> and has administrator rights.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="note_re_env_var"></span>

#### Note:

Overall user access to Gateway is controlled by the **User access control** parameter in the **Configuration** menu. If you enable this option, you must edit the <span class="code">userprof.bat</span> script (Windows) or the <span class="code">osprofile </span>(UNIX) file, or modify <span class="code">exitlgin.c</span>, to set the following environment variables:

-   administration user: <span class="code">p\_cs\_username</span>
-   decryption key file pathname<span class="code">: p\_cs\_dk\_file</span>
-   encrypted password file pathname: <span class="code">p\_cs\_encpass\_file</span>

These environment variables must already be defined in an administration account.

(Storing the cleartext password in the environment variable <span class="code"></span>p\_cs\_password<span class="code"> </span>is no longer supported.)

For more information regarding password encryption, read <a href="../../../password_management" class="MCXref xref">Password management</a>.

<span id="update_user"></span>

## Modifying a User: peladm update\_user

<table>
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p>peladm update_user (<span style="font-weight: normal;">-username</span>) [<span style="font-style: italic;font-weight: normal;">-optional parameters</span><span style="font-style: italic;font-weight: normal;">, see below</span>]</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>This command is reserved for administrators only.</p>
<p>Use this command to modify a User definition.</p>
<p>For non-administrator users, the only modifiable parameter is <span class="code">password</span>, which enables users to set their own passwords as needed.</p>
<p>All parameters apart from <span class="code">username</span> are optional. If not specified, a parameter keeps its previous value.</p>
<p>The Profile that you specify must be defined in the Profile database.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>Mandatory</p>
<p><span class="code">-username (-un)</span>: Login name for this user.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-profile (-pr)</span>: Access profile name for this user.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-group (-gr)</span>: Group name for this user.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-password (-pswd)</span>: Password for this user.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-comments (-cts)</span>: Enter a free-text description of up to 80 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-expired (-exd)</span>: Enter an expiration date in the format <span style="font-style: italic;">YYYYDDMM HHMMSS</span>.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-maxretry (-mxr)</span>: Enter a number between 0 and 999 for the maximum number of connection retries allowed (default = 0).</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-administrator (-admin)</span>: Define the user as an administrator or not.</p>
<p>Enter one of the values:</p>
<ul>
<li><span style="font-weight: bold;">N</span>: non-administrator users</li>
<li><span style="font-weight: bold;">Y</span>: administrator users (default)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-allxfer (-ax)</span>: Defines the user with/without access to all transfers.</p>
<p>Enter one of the values:</p>
<ul>
<li><span style="font-weight: bold;">N</span>: non-administrator users (default)</li>
<li><span style="font-weight: bold;">Y</span>: administrator users</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-disabled (-dd)</span>: Enables/disables User.</p>
<p>Enter one of the values:</p>
<ul>
<li><span style="font-weight: bold;">N</span>: non-administrator users (default)</li>
<li><span style="font-weight: bold;">Y</span>: administrator users</li>
</ul>         </td>
      </tr>
      <tr>
         <td><span class="code">-allow_old_ver (-aov)</span> : Allow login from this user when connecting with an older API version. Useful especially for XIB users, where the API update is not in sync with Gateway release.
Enter one of the values:
<ul>
<li><strong>N</strong>: don't allow</li>
<li><strong>Y</strong>: allow</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>Enter the command:</p>
<p>peladm update_user<span style="font-weight: bold;">  -username USERONE  -password PASS</span></p>
<p>Gateway sets the password of the User <span style="font-style: italic;">USERONE</span> to the value <span style="font-style: italic;">PASS</span>.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="delete_user"></span>

## Deleting a User: peladm delete\_user

<table>
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p>peladm delete_user [<span style="font-weight: normal;">-username</span>]</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to delete a User definition.</p>
<p>Repeat the command for each User that you want to delete.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span class="code">-username (-un)</span>: Name of the user you want to delete</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>Enter the command:</p>
<p>peladm delete_user  -username USERONE</p>
<p>Gateway deletes the User <span style="font-style: italic;">USERONE.</span></p>         </td>
      </tr>
   </tbody>
</table>

<span id="select_user"></span>

## Selecting Users: peldsp select\_user

<table>
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p>peldsp select_user (-<span style="font-weight: normal;">username</span>) [<span style="font-style: italic;font-weight: normal;">-optional selection parameters</span><span style="font-style: italic;font-weight: normal;">, see below</span>]</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to display a subset of Users that matches a defined selection criteria.</p>
<p>To list all Users, enter the command without any selection parameters.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span class="code">-username (-un)</span>: Login name for this user.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-profile (-pr)</span>: Access profile name for this user.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-group (-gr)</span>: Group name for this user.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-comments (-cts)</span>: Enter a free-text description of up to 80 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-administrator (-admin)</span>: Define the user as an administrator or not.</p>
<p>Enter one of the values:</p>
<ul>
<li><span style="font-weight: bold;">N</span>: non-administrator users</li>
<li><span style="font-weight: bold;">Y</span>: administrator users</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-allxfer (-ax)</span>: Defines the user with/without access to all transfers.</p>
<p>Enter one of the values:</p>
<ul>
<li><span style="font-weight: bold;">N</span>: non-administrator users</li>
<li><span style="font-weight: bold;">Y</span>: administrator users</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-disabled (-dd)</span>: Enables/disables User.</p>
<p>Enter one of the values:</p>
<ul>
<li><span style="font-weight: bold;">N</span>: non-administrator users</li>
<li><span style="font-weight: bold;">Y</span>: administrator users</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>Enter the command:</p>
<p>peldsp select_user  -group MIS</p>
<p>Gateway selects all Users who belong to the group MIS for display.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="display_user"></span>

## Displaying a User: peldsp display\_user

<table>
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p>peldsp display_user (-<span style="font-weight: normal;">username</span>)</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to display the full definition of a User that you identify by name.</p>
<p>Each parameter is displayed on a separate line, in the format:</p>
<p>name_of_field="value"</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span class="code">-username (-un)</span>: Name of the user for whom you want to display the definition.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>Enter the command:</p>
<p>peldsp display_user  -username USERA</p>
<p>Gateway displays all attributes of user record USERA:</p>
<p>u_username='USERA'</p>
<p>u_group=admin</p>
<p>u_profile='admin'</p>
<p>u_password='pass1'</p>
<p>u_comments='Gateway administrator'</p>
<p>u_maxretry=0</p>
<p>u_expired=''</p>
<p>u_admin='Y'</p>
<p>u_allxfer='Y'</p>
<p>u_disabled='N'</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Managing profiles (command line)](managing_profiles_cli)

[About Access Control Management](../../)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
