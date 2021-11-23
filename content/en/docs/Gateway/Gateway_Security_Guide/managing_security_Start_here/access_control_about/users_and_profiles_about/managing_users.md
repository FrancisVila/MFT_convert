{
    "title": "Working with Users",
    "linkTitle": "Working with Users",
    "weight": "160"
}{{< Gateway/componentlongname  >}}: Managing Security

[Creating a new User object](#creating_user)

[Displaying all User objects](#Displaying_a_list_of_User_objects)

[Displaying a list of selected User objects](#Displaying_a_selected_list_of_User_objects)

[Viewing User object attributes](#Viewing_the_attributes_of_a_User_object)

[Modifying a User object](#Modifying_a_User_object)

[Deleting a User object](#Deleting_a_User_object)

<span id="creating_user"></span>

## Creating a new User object

To create a new User object:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:

Security Management &gt; Access Control Management

1.  Right-click the **User** sub-node, and then select <span style="font-weight: bold;">New</span> from the context menu.

Gateway displays the <span style="font-style: italic;">New User</span> window.

1.  In the <span style="font-style: italic;">New User</span> window, complete the fields described in the following table:

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Field</p>         </th>
<th class="HeadD-Column1-Header1"><p>Meaning</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Name<span style="font-weight: normal;"> (</span><span style="font-weight: normal;font-style: italic;">mandatory</span><span style="font-weight: normal;">)</span></p>         </td>
         <td><p>Enter a unique name that identifies the user to Gateway. For platforms that support multi-users, the user name should be the same as that used in the operating system.<br />
Maximum: 31 characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Group</p>         </td>
         <td><p>Optional</p>
<p>Enter the Group name for this User. If you do not specify a Group, the default Group GDEFAULT is used.</p>         </td>
      </tr>
      <tr>
         <td><p>Comments</p>         </td>
         <td><p>Free-text field.<br />
Maximum: 80 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Access control:</p>         </td>
      </tr>
      <tr>
         <td><p>Set password<span style="font-weight: normal;"> </span> </p>         </td>
         <td><p>Opens a dialog box to enter a user password. If you do not set a user password, a new password will be required at login time.<br />
Maximum: 15 characters.</p>         </td>
      </tr>
      <tr>
         <td><p>User profile</p>         </td>
         <td><p>Enter the name of the Profile object that defines the access rights (authorized actions) for a user or a set of users. This record is stored in the Profile database. You must specify an access Profile for all users other than administrators.</p>
<p>Alternatively, click the down arrow to display a list of available Profiles, and then select a Profile from the list.</p>         </td>
      </tr>
      <tr>
         <td><p>Expiration date</p>         </td>
         <td><p>Optional</p>
<p>Select an expiration date for user access.</p>         </td>
      </tr>
      <tr>
         <td><p>Maximum retries</p>         </td>
         <td><p>Optional</p>
<p>Enter an integer that represents the upper limit for consecutive unsuccessful login attempts. Beyond this limit, the user account is disabled, and administrator intervention is required to re-enable it. A value of zero stands for no limit checking.</p>         </td>
      </tr>
      <tr>
         <td><p>Disabled</p>         </td>
         <td><p>Check this option to disable the user account.</p>         </td>
      </tr>
      <tr>
         <td><p>Additional rights:</p>         </td>
      </tr>
      <tr>
         <td><p>Administrator</p>         </td>
         <td><p>Check this option to assign administrator access to the User. Administrators have access to all operations. If you assign Administrator access, the associated Profile definition is ignored.</p>         </td>
      </tr>
      <tr>
         <td><p>Access all transfers</p>         </td>
         <td><p>Each Transfer Request is associated with its creator, also known as owner.</p>
<p>Access to Transfer Requests is limited to:</p>
<ul>
<li>Transfer Request creator</li>
<li>Administrators</li>
<li>Users with <span style="font-style: italic;">Access all transfers</span> privilege</li>
</ul>
<p>Check this option to assign access to all Transfers. The actions the User can perform on Transfer Requests are still limited to those defined in the associated Profile object.</p>         </td>
      </tr>
      <tr>
         <td><strong>Allow old versions</strong>         </td>
         <td>Allow login from this user when connecting with an older API version. Useful especially for XIB users, where the API update is not in sync with the <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> release.         </td>
      </tr>
   </tbody>
</table>

1.  Click <span style="font-weight: bold;">OK</span> to save the new user definition and close the window.

#### Note:

Define overall User Access Control in the Gateway configuration menu ([Gateway &gt; Connection control](../../../../../gateway_userguide_(primary)/configuration_start_here/config_gateway_paras#olh_gateway_connection_control)).

If you want to use script or batch functions, you must define environment variables for the following:

-   an administration account login (<span class="code">p\_cs\_username</span>)
-   an administration decryption key file (<span class="code">p\_cs\_dk\_file</span>)
-   an administration encrypted password key file (<span class="code">p\_cs\_encpass\_file</span>)

(Storing the cleartext password in the environment variable <span class="code"></span>p\_cs\_password<span class="code"> </span>is no longer supported.)

For more information regarding password encryption, read <a href="../../../password_management" class="MCXref xref">Password management</a>.

<span id="Displaying_a_list_of_User_objects"></span>

## Displaying all User objects

To display a list of all User objects stored in the database:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:

Security Management &gt; Access Control Management

1.  Click the <span style="font-weight: bold;">User</span> sub-node.

Gateway displays a list of all existing User objects in the right (display) pane.

<span id="Displaying_a_selected_list_of_User_objects"></span>

## Displaying a list of selected User objects

You can reduce the number of User objects listed in the display pane by applying selection criteria to the display.

To display a selected list of User objects:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:

Security Management &gt; Access Control Management

1.  Click the <span style="font-weight: bold;">User</span> sub-node.

Gateway displays a list of all existing User objects in the right pane.

1.  Right-click the <span style="font-weight: bold;">User</span> sub-node, then select <span style="font-weight: bold;">Select...</span> from the context menu.

Gateway displays the <span style="font-style: italic;">Select User</span> window.

1.  In the <span style="font-style: italic;">Select User</span> window, use the data fields to enter criteria for User display selection. You can use one or more of the following User attributes as selection criteria:
    -   Maximum number of lists (default = 50)
    -   User Name
    -   Group
    -   Comments
    -   User profile
    -   Disable
    -   Administrator
    -   Access all transfers

<!-- -->

1.  Click <span style="font-weight: bold;">OK</span> to accept the display selection criteria.

Gateway regenerates the right window User list display, taking into account your selection criteria.

<span id="Viewing_the_attributes_of_a_User_object"></span>

## Viewing User object attributes

To view the attributes of a specific User object:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:

Security Management &gt; Access Control Management

1.  Click the <span style="font-weight: bold;">User</span> sub-node.

Gateway displays a list of all existing User objects in the right (display) pane.

1.  In the right pane, right-click the name of the User object you want to view. Select <span style="font-weight: bold;">View...</span> from the context menu.

Gateway displays the <span style="font-style: italic;">User (read only)</span> window. This window provides you with a view of all attributes for the selected User object.

1.  When you have finished viewing the information, click <span style="font-weight: bold;">Close</span> to quit the window.

<span id="Modifying_a_User_object"></span>

## Modifying a User object

To modify the attributes of an existing User object:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:

Security Management &gt; Access Control Management

1.  Click the <span style="font-weight: bold;">User</span> sub-node.

Gateway displays a list of all existing User objects in the right (display) pane.

1.  In the display frame (right frame), right-click the User object that you want to modify. Then in the context menu click <span style="font-weight: bold;">Modify...</span>

Gateway opens the <span style="font-style: italic;">User</span> editing window. This window comprises two tabs.

1.  Modify the value fields of the tabs according to your requirements.
2.  Click <span style="font-weight: bold;">OK</span> to confirm changes and complete the modification procedure.

<span id="Deleting_a_User_object"></span>

## Deleting a User object

To delete an existing User object:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Partner Management</span> node.
2.  Click the <span style="font-weight: bold;">User</span> sub-node.

Gateway displays a list of all existing User objects in the right (display) pane.

1.  In the right pane, right-click the name of the User object you want to delete. Select <span style="font-weight: bold;">Delete...</span> from the context menu.

Gateway displays a confirmation dialog box.

1.  In the confirmation dialog box, click <span style="font-weight: bold;">Yes</span> to confirm the delete operation.  
    Alternatively, click <span style="font-weight: bold;">No</span> or <span style="font-weight: bold;">Cancel</span> to abandon the operation.

Gateway deletes the User object from the database and removes the entry from the display window.

Related topics

[About Access Control Management](../../)

[Configuration: Gateway parameters](../../../../../gateway_userguide_(primary)/configuration_start_here/config_gateway_paras)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
