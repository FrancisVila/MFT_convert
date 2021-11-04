{
    "title": "Create a user account",
    "linkTitle": "Create a user account",
    "weight": "160"
}Go to **Accounts &gt; User Accounts** to open the *User Accounts* page and click **New Account**.

When you create a user account, all the tabs except **Settings** are disabled.

Some of the options are initially hidden. The following table provides detailed information about Account Creation options.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Name / Type         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><strong>Account Name</strong>*
<p><em>text box</em></p>         </td>
         <td><p>The name of the account must be unique for the system. If an account already exists with the name you specify, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> prompts you to enter another name. This field is mandatory. Account Names cannot contain more than 80 characters. You cannot enter spaces-only values in this field. For more information, see <a href="#Spaces" class="MCXref xref">Spaces in required fields</a>.</p>         </td>
      </tr>
      <tr>
         <td><strong>Email Contact</strong>
<p><em>text box</em></p>         </td>
         <td><p>When this email address is the recipient of an ad hoc file transfer email sent from ST Web Client or one of the <span class="mc-variable axway_variables.Company_Name variable">Axway</span> Email Plug-ins, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> determines that this user is the recipient. If the user is allowed to log in by email, this is the value used in the <strong>User Name</strong> field of the login page.</p>
<blockquote>
<p><strong>Note:</strong></p>
<p>In order for login by email to function properly, all user accounts must be assigned unique email addresses. Also, the client password reset feature will not work if emails assigned to users accounts are not unique.</p>
</blockquote>
<p>The <em>Address Book Settings</em> are only displayed if the Address Book feature is enabled (the value of the <code>AddressBook.Enabled</code> configuration option is set to <strong>true</strong>).</p>         </td>
      </tr>
      <tr>
         <td><strong>Phone contact</strong>
<p><em>text box</em></p>         </td>
         <td>Contact Phone number.         </td>
      </tr>
      <tr>
         <td><strong>Account Type</strong>
<p><em>drop-down list</em></p>         </td>
         <td>Use this parameter to differentiate between accounts that transfer files internally and those that transfer files between partners. Choose from the following:
<ul>
<li><strong>Unspecified</strong> – Default value. All accounts created using versions of <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> that do not have this option have this value.</li>
<li><strong>Internal</strong> – Transfers for this account occur within a single organization.</li>
<li><strong>Partner</strong> – Transfers for this account occur between organizations</li>
</ul>         </td>
      </tr>
      <tr>
         <td><strong>Business Unit</strong>
<p><em>drop-down list</em></p>         </td>
         <td><p>Select the business unit the current account will belong to. The default setting is No Business Unit.</p>
<blockquote>
<p><strong>Note:</strong></p>
<p>All Business Unit-level policies apply to the current user account.</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td><strong>HTML Template</strong>
<p><em>drop-down list</em></p>         </td>
         <td><p>Select the <strong>HTML Template</strong> that <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> displays when the user logs in to the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> web client.</p>
<blockquote>
<p><strong>Note:</strong></p>
<p>If you select the default HTML template, the SecureTransport Web Client uses the template that is specified on the Miscellaneous Options page.</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td><strong>Routing Mode</strong>
<p><em>drop-down list</em></p>         </td>
         <td>This field controls how <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> behaves when it is the intermediate partner in a PeSIT transfer directed to this account and the transfer cannot be completed because no transfer site matches the routing destination and the account has no PeSIT default site.
<ul>
<li><strong>Reject</strong> (default) – A PeSIT transfer that cannot be routed is rejected before it starts.</li>
<li><strong>Accept</strong> – A PeSIT transfer that cannot be routed is performed and the file is retained locally.</li>
<li><strong>Ignore</strong> – A PeSIT transfer that cannot be routed is ignored.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><strong>Encrypt Mode</strong>
<p><em>drop-down list</em></p>         </td>
         <td>This field allows you to enable repository encryption for this user.
<ul>
<li><strong>Unspecified</strong> (default) – Repository encryption is enabled based on the <code>EncryptClass</code> user class evaluation.</li>
<li><strong>Enabled</strong> – Repository encryption is enabled for this user account.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><strong>Subscription Folder Discovery</strong>
<p><em>drop-down list</em></p>         </td>
         <td><p>This field determines the subscription folder discovery mode. For accounts with multiple subscriptions,
the number of subscriptions and the target folder depth may impact performance.</p>
<ul>
<li><strong>Iterable</strong> (default) – Subscription folder discovery is performed by iteration over all of
the account's subscriptions while trying to match the target folder.<br />
Tip: Choose this mode when the number of subscriptions is
small and the target folder depth is large.</li>
<li><strong>Recursive</strong> – Subscription folder discovery is performed by recursive traversal of the target folder hierarchy -
the target folder is checked first and if no match is found, then its parent folder is checked. The process continues
until a match is found or there are no more folders to check.<br />
Tip: choose this mode when the number of subscriptions is large
and the target folder depth is shallow.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><span id="File_Archiving_account"></span><strong>File archiving policy</strong>
<p><em>drop-down list</em></p>         </td>
         <td><p>Determines the File archiving policy for the current user account based on the following options:</p>
<ul>
<li>When <strong>Default</strong> is selected, then the following applies: If the account is assigned to a business unit, it will inherit its policy. Otherwise, the global archiving policy applies</li>
<li>When <strong>Enabled</strong> is selected, File archiving is enabled for this account.</li>
<li>When <strong>Disabled</strong> is selected, File archiving is disabled for this account.</li>
</ul>
<blockquote>
<p><strong>Note:</strong></p>
<p>This option cannot be modified when the global file archiving policy is disabled or if this account is assigned to a business unit with Allow File Archiving Policy modifying option deselected.</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td><span id="FileMaintenance"></span><strong>File Maintenance policy</strong>
<p><em>drop-down list</em></p>         </td>
         <td><p>Determines the File Maintenance policy for the current user account based on the following options:</p>
<ul>
<li>When <strong>Default</strong> is selected, then the following applies:
If the account is assigned to a business unit, it will inherit its policy. Otherwise, the global file maintenance policy applies.</li>
<li>When <strong>Disabled</strong> is selected, File Maintenance is disabled for this account.</li>
<li>When <strong>Custom</strong> is selected, the panel expands with a <strong>Custom settings</strong> pane that allows you to modify the existing <a href="../../../applications/applicationsfilemaintenance#Configur" class="MCXref xref">File Maintenance application</a>. The customized policy applies to this account only.</li>
</ul>
<blockquote>
<p><strong>Note:</strong></p>
<p>This option cannot be modified when the global file maintenance policy is disabled or the account is assigned to a business unit with the Allow File Maintenance Policy modifying checkbox deselected.</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td><span id="Account_Maint_User"></span><strong>Account Maintenance policy</strong>
<p><em>drop-down list</em></p>         </td>
         <td>Determines the Account Maintenance policy for the current user account based on the following options:
<ul>
<li>When <strong>Default</strong> is selected, then the following applies: If the account is assigned to a business unit, it inherits its policy. Otherwise, the global Account Maintenance policy applies.</li>
<li>When <strong>Disabled</strong> is selected, then Account Maintenance will be disabled for this account.</li>
<li>When <strong>Custom</strong> is selected, the panel expands with a <strong>Custom settings</strong> pane that allows you to modify the existing <a href="../../../applications/applicationsaccountmaintenance" class="MCXref xref">Account Maintenance application</a>. The customized policy applies to this account only.</li>
</ul>
<ul>
<li><p>If a global Account Maintenance policy is not defined, or if this account is assigned to a business unit with the <strong>Allow Account Management policy modifying</strong> check-box option deselected, then you cannot modify the Account Maintenance policy on a user level.</p></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><strong>UID</strong>*</p>
<p><em>text box</em></p>         </td>
         <td><p>Type the numeric user ID of the user in the <strong>UID</strong> field. This field is mandatory on UNIX and Linux platforms. You cannot enter spaces-only values in this field. For more information, see <a href="#Spaces" class="MCXref xref">Spaces in required fields</a>.</p>
<p>On Windows platforms, this field is named <strong>Real User</strong> and is optional.</p>         </td>
      </tr>
      <tr>
         <td><strong>GID</strong>*
<p><em>text box</em></p>         </td>
         <td><p>Type the numeric group ID for the user account in the <strong>GID</strong> field. The account uses the system access rights and privileges valid for this user group on the system. You cannot enter spaces-only values in this field.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Change home to</strong></p>
<em>text boxes</em>         </td>
         <td><p>You must assign a <strong>Current Home</strong> folder for your user.</p>
<p>Enter a valid home folder in the <strong>Change Home To</strong> field for the account as an absolute path. <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> validates the directory path you specify and prompts you for a new path if necessary. This field is mandatory. You cannot enter spaces-only values in this field.</p>
<p>Add a base folder path in the field to the left of the forward slash (<code>/</code>) and add the home folder in the field to the right of it. You can add multiple levels, such as <code>/home/dev3/test</code>, but the parent directories must be typed in the field to the left of the slash. Only the final child directory should be in the field to the right of the slash. When you select a business unit, a base folder for the business unit is automatically added. The base folder must be the business unit base folder. You cannot change the base folder for a user account if a business unit is selected unless the business unit has the option <strong>Allow Base Folder modifying</strong> selected.</p>
<p>Although you can use the <code>/</code> when adding parent directories to a home folder, you cannot use the following characters in the home folder name: <code>* &lt; &gt; ? " / \ | :</code></p>
<blockquote>
<p><strong>Note:</strong></p>
<p>If you change the home folder when editing a user account, any subscription folders the account has are reinitialized. In other words, the subscription folders are created again under the new home folder of the account. None of the other folders created by the user will be moved and the user will no longer have access to them. This also happens if the user is moved from one Business Unit to another.</p>
</blockquote>
<blockquote>
<p><strong>Note:</strong></p>
<p>For SecureTransport on Windows, you can create a home folder for an account in a UNC format, pointing to a local or a remotely shared folder over the network.</p>
</blockquote>
<blockquote>
<p><strong>Note:</strong></p>
<p>On Windows, when a network share is used as a home folder for an account, you must manually create a directory with proper access settings. SecureTransport cannot create the home folder because the SecureTransport services run on Windows as service accounts with a local system user as its owner. You must either use SecureTransport impersonation functionality or use permissions sufficient for the network share to be accessed by local system users. For more information, see Real users on Windows.</p>
</blockquote>
<blockquote>
<p><strong>Note:</strong></p>
<p>Transaction Manager agents must use the Windows impersonation functionality (mapping virtual users to real users) as needed to access directories on a network share (that is, directories in UNC format or on mapped drives. paths.</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td><strong>Home Folder Access Level</strong>
<p><em>drop-down list</em></p>         </td>
         <td><p>The home folder access level determines whether and which other accounts are able to publish to the home folder of the current account.</p>
<ul>
<li><strong>Private</strong> – The access level is private. Only the current account is able to publish files to its home folder.</li>
<li><strong>Business Unit</strong> – Account home folder access is limited to the account’s business unit. The current account and all accounts in the current account’s business unit can publish to this account’s home folder.</li>
<li><strong>Public</strong> – Access to the account is public. All accounts are able to publish to this account’s home folder.</li>
</ul>
<blockquote>
<p><strong>Note:</strong></p>
<p>Access level is applicable only when Advanced Routing feature is used. For more information see Advanced Routing</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td><p><strong>Notes</strong></p>
<p><em>text box</em></p>         </td>
         <td>Enter a text description of the user account in the <strong>Notes</strong> field.         </td>
      </tr>
      <tr>
         <td><strong>Delivery Method</strong>
<p><em>drop-down list</em></p>         </td>
         <td><em>AdHoc settings</em>
<p>This value controls the options that ST Web Client displays in the <em>User Access</em> window.</p>
<ul>
<li><strong>Disabled</strong> – The user cannot send files using ad hoc file transfers.</li>
<li><strong>Default</strong> – Use the delivery method specified in the account template, if any, or in the <strong>Default Package Delivery Method</strong> field of the <em>AdHoc Setting</em> page.</li>
<li><strong>Anonymous</strong> – The sender can choose <strong>Send attachment link only</strong> or <strong>Protect attachment link with security question</strong>.</li>
<li><strong>Account Without Enrollment</strong> – The sender can choose <strong>Send attachment link only</strong>, <strong>Protect attachment link with security question</strong>, or <strong>Send to existing users only</strong>.</li>
<li><strong>Account With Enrollment</strong> – The sender can choose <strong>Send attachment link only</strong>, <strong>Protect attachment link with security question</strong>, <strong>Send to existing users only</strong>, <strong>Allow recipients to enroll as restricted users (receive and reply to messages only)</strong>, or <strong>Allow recipients to enroll as unrestricted users</strong>. (Elsewhere the Administration Tool refers to restricted users as unlicensed users and unrestricted users as licensed users.)</li>
<li><strong>Custom</strong> – Select the allowed enrollment types in the <strong>Enrollment Types</strong> field. The sender can chose any of the selected enrollment types.<br />
For a custom delivery method, select one or more of the allowed enrollment types in the <strong>Enrollment Types</strong> field:</li>
<li><ul>
<li><strong>Anonymous</strong> – The ad hoc file recipient receives a link to retrieve the files and is not enrolled as a user. The ST Web Client option is <strong>Send attachment link only</strong>.</li>
<li><strong>Challenge</strong> – The ad hoc file recipient receives a link and must answer correctly a challenge question specified by the sender to retrieve the files. The recipient is not enrolled as a user. The ST Web Client option is <strong>Protect attachment link with security question</strong>.</li>
<li><strong>Existing Account</strong> – Do not enroll ad hoc file recipients. Only existing users can receive files. The ST Web Client option is <strong>Send to existing users only</strong>.</li>
<li><strong>Enroll Unlicensed</strong> – If the ad hoc file recipient does not have a user account, the recipient must enroll and create an account before retrieving the files. The ad hoc file recipient becomes a restricted user who can only reply once to the email and retrieve the files. Other user attributes are defined by the enrollment template. The ST Web Client option is <strong>Allow recipients to enroll as restricted users (receive and reply to messages only)</strong>.</li>
<li><strong>Enroll Licensed</strong> – If the ad hoc file recipient does not have a user account, the recipient must enroll and create an account before retrieving the files. The ad hoc file recipient becomes a <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> user with all the attributes specified in the default enrollment template. The ST Web Client option is <strong>Allow recipients to enroll as unrestricted users</strong></li>
</ul>
<p>When the value of the <strong>Delivery Method</strong> field is not <strong>Default</strong>, the <strong>Implicit Enrollment Type</strong> value controls which option ST Web Client selects initially in the <em>User Access</em> window and which enrollment type is used by the <span class="mc-variable axway_variables.Company_Name variable">Axway</span> Email Plug-ins. The choices depend on the enrollment types enabled by the <strong>Delivery Methods</strong> and <strong>Enrollment Types</strong> fields. <strong>Challenge</strong> is not an option because the <span class="mc-variable axway_variables.Company_Name variable">Axway</span> Email Plug-in do not include the challenge question and answer function.</p></li>
</ul>         </td>
      </tr>
      <tr>
         <td><strong>Address Book Settings</strong>
<p><em>group of options</em></p>         </td>
         <td><em>Address Book Settings</em>
<p>(Optional) When the Address Book feature is enabled, the <em>Address Book Settings</em> are displayed. To configure the user account Address Book settings:</p>
<ol>
<li>Select the Address Book source.
<ul>
<li><strong>Default</strong> - The account inherits either its business unit Address Book policy or the global Address Book policy.</li>
<li><strong>Custom</strong> - A custom Address Book policy configuration will be set for this account only and the following will be configurable:
<ol type="a">
<li>Enable or disable Address Book sources for the account.</li>
<li>Specify the parent groups for Address Book sources.</li>
<li>Specify the domain for LDAP Address Book sources.</li>
<li>Specify <strong>All Business Units</strong> or <strong>User's own business unit</strong> for local and custom Address Book sources.</li>
</ol></li>
<li><strong>Disabled</strong> - The Address Book policy is set to disabled for this account.</li>
</ul></li>
<li>Specify whether or not to allow collaboration with non-Address Book recipients. If Address Book functionality is disabled, this setting does not affect user collaboration.
<ul>
<li>When <strong>checked</strong>, the account will be allowed to send email packages and share folders with users that do not exist in the defined Address Book.</li>
<li>When <strong>unchecked</strong>, the account will be allowed to send email packages and share folders only with users that exist in the defined Address Book.</li>
</ul></li>
<li>This account setting overrides the business unit or global Address Book Policy setting for collaboration.</li>
</ol>
<p>For additional Address Book account level configuration information, see <a href="##Address2" class="MCXref xref">Address Book account level configuration</a>.</p>         </td>
      </tr>
      <tr>
         <td><strong>Bandwidth Limits Policy</strong>
<p><em>drop-down list</em></p>         </td>
         <td><p><em>Bandwidth limits</em></p>
<p>Select a <strong>Bandwidth Limits Policy</strong> to apply:<br />
</p>
<ul>
<li>Default – the current user account inherits their bandwidth limits from the parent business unit or the global bandwidth</li>
<li>Custom – the panel expands with two additional options for you to configure: <strong>Inbound limit</strong> and <strong>Outbound limit</strong> (both values in kb/s per user)<br />
</li>
<li>Disabled – no bandwidth limits are applied to the users assigned to the current business unit</li>
</ul>         </td>
      </tr>
      <tr>
         <td><strong>Login Settings</strong>
<p><em>check-box-controlled group of options</em></p>         </td>
         <td>In the <em>Login Settings</em> area: select <strong>Allow this account to log in to <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server</strong> to allow the new account to log in to <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>. This setting is enabled by default. Disabling the option restricts access of this account to the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server. If you enable this option, the following options are enabled.
<ul>
<li>Enter a <strong>Login Name</strong> for the account. This is the unique name with which the account is identified by the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server. Login names cannot contain the following characters: +, :, or [. Login Names cannot start with the following character: *.</li>
<li>Select the <strong>Login Restriction Policy</strong>. The Login Restriction Policy defines rules for allow or deny login to users based on the client IP or host and other conditions. For additional information, see <a href="../../../c_st_accesscontrol/c_st_loginrestictions" class="MCXref xref">Login restrictions</a>.
<ul>
<li>If a Login Restriction Policy is selected as the global default policy, it will be the inherited default selection for the user account.</li>
<li>If a Login Restriction Policy is not selected as the global default policy and the Business Unit has a Login Restriction Policy selected, it will be the inherited default selection for the user account.</li>
<li>If neither a global default Login Restriction Policy or a Business Unit Login Restriction Policy is selected, then the policy selected for the users account will be in effect.</li>
<li><blockquote>
<p><strong>Note:</strong></p>
<p>The default inherited Login Restriction Policy can be overridden by selecting a Login Restriction Policy from On Account.</p>
</blockquote></li>
</ul></li>
<li>Select <strong>Allow this account to login by email</strong> to allow the user to log in using with the value of the <strong>Email Contact</strong> field as well as the <strong>Login Name</strong>.<br />
</li>
<li><blockquote>
<p><strong>Note:</strong></p>
<p>A user of one of the Axway Email Plug-ins must either have Allow this account to login by email selected or have the identical values in the Email Contact field and the Login Name field.</p>
</blockquote></li>
<li>Select <strong>Allow this account to submit transfers using the Transfers RESTful API</strong> to enable calls from the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> REST file transfer API authenticated with the credentials from this account. When this option is selected, the account will be allowed to trigger server initiated transfers using the Transfers RESTful API resource and retrieve the tracking information for these transfers.</li>
<li><p>Select <strong>Password is stored locally (not in external directory)</strong> to store the password locally in the system. <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> stores the passwords of real, LDAP, SiteMinder, and SSO users in an external directory, and the passwords of virtual users are stored in the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> database.<br />
</p>
<blockquote>
<p><strong>Note:</strong></p>
<p>The Password is stored locally (not in external directory) option can only be used for a user account that has a virtual user associated with it. If the user associated with the account is a real, LDAP, SiteMinder, or SSO user, then the password cannot be stored locally in the database and this option is unusable.</p>
</blockquote>
<ul>
<li>Enter a <strong>New Password</strong> for the account.</li>
<li><strong>Re-enter Password</strong> for the account.</li>
<li>Select <strong>Require user to change password on next login</strong> to require the user to change their password on the next login.</li>
<li>Select <strong>Require user to set new secret question on next login</strong> to require the user to select and answer a new secret question. When this option is selected, the user must select and answer a new secret question on their next login. For information on configuring the secret question feature, see <a href="../../t_st_password_reset/t_st_secretquestion" class="MCXref xref">Configure a secret question</a>.</li>
<li>Complete the <strong>Require user to change password every X days</strong> field to require the user to change their password every specified number of days. If the number of days is unspecified, the user will not be required to change their password every "X" number of days.</li>
<li>Complete the <strong>Lock account after X failed login attempts</strong> field to lock the account after the specified number of failed login attempts. If you don't supply a value, the value of the <code>Users.DefaultLockoutLimit</code> configuration option will be applied. If the value is set to 0 [zero], an infinite number of failed login attempts are allowed.</li>
<li><blockquote>
<p><strong>Note:</strong></p>
<p>Certificate authentication attempts over HTTP are not counted as failed login attempts.</p>
</blockquote></li>
<li>Complete the <strong>Lock account after X failed ssh key authentication login attempts</strong> field to lock the account after the specified number of failed ssh key authentication login attempts. If you don't supply a value, the value of the <code>Users.DefaultSshKeyLockoutLimit</code> configuration option will be applied. If you set the value to 0 [zero], infinite number of failed login attempts via SSH keys will be allowed.</li>
<li>Complete the <strong>Lock account after X successful logins</strong> field to lock the account after the specified number of successful logins. If you don't supply a value, infinite number of successful login attempts will be allowed.</li>
</ul>
<blockquote>
<p><strong>Note:</strong></p>
<p>The GlobalLoginThreshold configuration option is a percentage value that will allow additional successful logins after reaching the threshold specified in the Account page (Lock user after X successful logins).</p>
</blockquote></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span id="addattrib"></span><strong>Add Attribute</strong></p>
<p><em>group of options</em></p>         </td>
         <td><em>Additional Attributes</em>
<p>To add an attribute, click <strong>Add Attribute</strong>. For additional information on Additional Attributes, see <a href="../../../c_st_setup/t_st_mailtemplates/c_st_mail_template_commands_variables#Addition" class="MCXref xref">Additional attributes</a>.</p>
<h5 id="add-an-attribute">Add an attribute</h5>
<ul>
<li>Click <strong>Add Attribute</strong> to enable input in the <strong>Attribute</strong> and <strong>Value</strong> fields.</li>
<li>Enter the respective values and click the Save (<img src="/Images/SecureTransport/SaveIcon.png" />) icon.</li>
</ul>
<p>Repeat the process to add more Additional attributes, if necessary. You can also access these custom properties using any fields in Advanced Routing.</p>
<h5 id="delete-an-attribute">Delete an attribute</h5>
<ul>
<li>Simply select the corresponding check-box of the (one or more) attribute to remove and then click <strong>Delete</strong>.</li>
</ul>
<p>Some examples of Attributes are:</p>
<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Attribute         </th>
<th class="HeadD-Column1-Header1">Value         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>userVars.1         </td>
         <td>internalEmail@axway.com         </td>
      </tr>
      <tr>
         <td>userVars.2         </td>
         <td>ReportsMonitor         </td>
      </tr>
   </tbody>
</table>
<p>To access attributes, see the following examples:</p>
<p><code>${account.attributes['userVars.1']}</code></p>
<p><code>${account.attributes['userVars.2']}</code></p>
<p>For example, the <code>account.attributes</code> is the selector for attributes of the account used to execute the current route - it has to be written exactly as shown.</p>
<p>The <code>userVars.</code> prefix <u>must</u> be prepended to attribute name.</p>
<p>All this should be written as an EL expression: <code>${...}</code></p>
<p>Click the attribute Save (<img src="/Images/SecureTransport/SaveIcon.png" />) icon.</p>         </td>
      </tr>
   </tbody>
</table>

After you add all your changes, click **Save**.

The user account information is saved and displayed in the *Settings* tab of the user account.

Once you have saved the account settings, you can select the **Subscriptions**, **Routes**, **Transfer Sites**, or **Certificates** to further define the new account. For more information, see <a href="../../c_st_subscriptions/t_st_subscriptions#AccountsMenu_2253641766_1247370" class="MCXref xref">Manage subscriptions</a>, <a href="../../../c_st_advanced_routing/c_st_configuration/t_st_manage_routes" class="MCXref xref">Manage Routes</a>, <a href="../../transfersites#AccountsMenu_2253641766_1151145" class="MCXref xref">Transfer sites</a>, and <a href="../../c_st_usercertificates/t_st_usercertificates#AccountsMenu_2253641766_1090701" class="MCXref xref">Manage login certificates</a>.

**Related topics:**

-   <a href="../t_st_change_how_long_user_account_information_is_cached" class="MCXref xref">Change how long user account information is cached in memory</a>
-   <a href="../t_st_disable_enable_user_account" class="MCXref xref">Disable or enable a user account</a>
-   <a href="../t_st_lock_unlock_user_account" class="MCXref xref">Lock or unlock a user account</a>
-   <a href="../t_st_manage_user_account_passwords" class="MCXref xref">Manage user account passwords</a>
-   <a href="../t_st_edit_user_account_settings" class="MCXref xref">Edit user account settings</a>
-   <a href="../t_st_delete_user_accounts" class="MCXref xref">Delete user accounts</a>
-   <a href="../t_st_delete_purge_user_account" class="MCXref xref">Delete and purge a user account</a>
-   <a href="../t_st_export_single_user_account" class="MCXref xref">Export a single user account</a>
-   <a href="../t_st_unlicensed_users" class="MCXref xref">Unlicensed users</a>
-   <a href="../c_st_protected_folders_accounts" class="MCXref xref">Protected folders and accounts</a>

<span id="Spaces"></span>

## Spaces in required fields

Some fields in <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> require that you enter a value. When you enter a value in such a field, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> trims any leading or trailing spaces and then determines whether the field is empty. This means you cannot enter space-only values in required fields because those fields are treated as empty.

# Maker-Checker user creation

Delegated administrators with Maker and Checker rights have two separate complementing roles:

-   Maker creates the user account and submits it for approval
-   Checker approves or rejects the pending user account

## Create and submit user

As a Maker, you can create a user account that will remain in Pending verification status. Your user will not have access until a Checker administrator *approves* their particular account.

In order to submit the account for approval, go to **Accounts &gt; User Accounts** and on the *Settings* tab click **Submit for approval**.

## Approve user

As a Checker administrator, you can only view and approve or reject users in pending Account verification status.

If you reject a pending account, you can type in the reason for rejection.
