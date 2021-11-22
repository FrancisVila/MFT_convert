{
    "title": "Manage administrator accounts",
    "linkTitle": "Manage administrator accounts",
    "weight": "160"
}Use the *Administrators* page to manage administrative accounts. You can create, edit, delete, and lock administrator accounts. You can also expire and reset administrator account passwords. If a custom hierarchical administration exists in an organization, you can specify different privileges for each administrator. Use the *Change Password* page to change your password even if you cannot edit accounts.

To display the *Administrators* page, select **Accounts &gt; Administrators** in the Administration Tool. To show only administrators whose names match a character string, type the string in the field in the *Search* pane and click **Search**.

For each administrator, you can view the information described in the following table.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Status         </td>
         <td><p>Reports the current status of the administrator account:</p>
<ul>
<li><strong>Active</strong> – The account is neither locked nor expired.</li>
<li><strong>Expired</strong> – Manual action or the expiration interval set the account as Expired.</li>
<li><strong>Locked</strong> – Manual action or login failures set this account as Locked. The account might also be Expired.</li>
</ul>         </td>
      </tr>
      <tr>
         <td>Administrator Name         </td>
         <td>The name given to the Administrator account         </td>
      </tr>
      <tr>
         <td>Full Creation Path         </td>
         <td>Applies only to delegated administrators. Shows the path for the parent administrator. For example, the path might look like: <code>admin/deladmin1/subdeladmin1</code>.         </td>
      </tr>
      <tr>
         <td>Administrative Role         </td>
         <td><p>Role assigned to the administrator account. The predefined administrative roles are:</p>
<ul>
<li><strong>Master Administrator</strong> – Access to all menus, tabs and pages of the Administration Tool. Cannot be modified.</li>
<li><strong>Database Administrator</strong> – Access to the <em>Database Settings</em> page only. Only the <code>dbsetup</code> administrator can have this role. Cannot be modified.</li>
<li><strong>Setup Administrator</strong> – Access through the custom <strong>Configure</strong> menu to pages required to perform the post-installation tasks and setup operations described in the . Cannot be modified.</li>
<li><strong>Account Manager</strong> – Access restricted to the <em>User Accounts</em>, <em><em>Unlicensed Users Accounts</em>, Service Accounts</em>, <em>Templates</em>, and <em>Business Units</em> pages on the <strong>Accounts</strong> menu and all pages on the <strong>Access</strong> menu.</li>
<li><strong>Application Manager</strong> – Access restricted to the pages on the <strong>Service Accounts</strong> and <strong>Applications</strong> menus.</li>
<li><strong>Delegated Administrator</strong> – Configurable access to menus and data based on the function the administrator has within an organization.</li>
</ul>         </td>
      </tr>
      <tr>
         <td>Password Status         </td>
         <td><p>The password status is reported differently depending on whether or not password expiration is enabled on the <em>Admin Settings</em> page.</p>
<p>If password expiration if enabled, this field shows one of the following:</p>
<ul>
<li>the expiration date</li>
<li>the date the password expires</li>
<li>a reminder to change the password at the next login</li>
<li>non-expiring</li>
</ul>
<p>If password expiration if not enabled, this field shows one of the following:</p>
<ul>
<li>the date the password was changed</li>
<li>a reminder to change the password at the next login</li>
<li>no change recorded</li>
</ul>
<p>Depending on your policy for these accounts, you can use the Reset function to mark the last password change time as the current time, or use the Expire function to force a password change at next login.</p>         </td>
      </tr>
      <tr>
         <td>Last Login         </td>
         <td>Reports the last login attempt recorded. This is either the date and time of the last successful login, or if the last recorded activity was a failed login, the number of failures and the date and time.         </td>
      </tr>
   </tbody>
</table>

The following topics provide how-to instructions for managing administrator accounts:

-   <a href="t_st_add_administrator_account" class="MCXref xref">Add an administrator account</a> - Provides how-to instructions for adding an administrator account.
-   <a href="t_st_edit_administrator_account" class="MCXref xref">Edit an administrator account</a> - Provides how-to instructions for editing an administrator account.
-   <a href="t_st_delete_administrator_account" class="MCXref xref">Delete an administrator account</a> - Provides how-to instructions for deleting an administrator account.
-   <a href="t_st_lock_administrator_account" class="MCXref xref">Lock an administrator account</a> - Provides how-to instructions for locking an administrator account.
-   <a href="t_st_unlock_administrator_account" class="MCXref xref">Unlock an administrator account</a> - Provides how-to instructions for unlocking an administrator account.
-   <a href="t_st_expire_administrator_account_password" class="MCXref xref">Expire an administrator account password</a> - Provides how-to instructions for expiring an administrator account password.
-   <a href="t_st_reset_expired_administrator_account_password" class="MCXref xref">Reset an expired administrator account password</a> - Provides how-to instructions for resetting an expired administrator account password.
-   <a href="t_st_change_administrator_password" class="MCXref xref">Change administrator password</a> - Provides how-to instructions for changing administrator password.
