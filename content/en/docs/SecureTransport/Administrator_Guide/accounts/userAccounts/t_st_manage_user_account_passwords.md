{
    "title": "Manage user account passwords",
    "linkTitle": "Manage user account passwords",
    "weight": "200"
}This subsection describes procedures for changing and expiring passwords of user accounts, as well as applying configuration

## Change a user account password

Use the following procedure to change a user account password.

1.  Select **Accounts > User Accounts**. The *User Accounts* page is displayed.
2.  Click the name of the account whose password you want to change.  
    The *User Account Settings* page is displayed with details for the selected account.
3.  Click **Change Password**.  
    The *Change Password* pane is displayed.
4.  Type the new password.
5.  Re-type the password to confirm it.
6.  (Optional) Select the **Require user to change password on next login** check box.
7.  Click **Save**.

> **Note:**
>
> Password policy restrictions apply.

## Expire a user account password

When you expire the password of an account, the user is prompted to change the password on next login. The new password must follow the password policy you configured for {{< SecureTransport/componentshortname  >}}. For more information, see <a href="../../../c_st_setup/c_st_miscellaneousconfiguration/t_st_passwordpolicy#SetupMenu_1217491348_1024545" class="MCXref xref">Password policy</a>.

> **Note:**
>
> If you change the password policy of a user while that user is logged in to SecureTransport through a web client, the old password policy is displayed until the user logs out and logs in again.

1.  Select **Accounts > User Accounts**. The *User Accounts* page is displayed.
2.  Click the name of the account whose password you want to expire.  
    The *User Account Settings* page is displayed with details for the selected account.
3.  Click **Expire Password**.  
    The *User Account* page is displayed with the red text in the *Account Status* pane stating that the password is expired.

## Web password compatibility

If a user created a password that contained the plus symbol (+) while running a web client in a previous version of {{< SecureTransport/componentshortname  >}}, you must change the value of the `Http.Password.Compatability.Mode` server configuration parameter to `on` to allow passwords with the + symbol.

When its value is set to `on`, this parameter allows users who previously changed their password to a string containing the plus character through a web client to log in and change their password. This option affects only the web clients. Once the password is changed, the user can log in using any client or protocol.

If you have upgraded or performed a system import, and you did not already manually change the parameter, {{< SecureTransport/componentshortname  >}} sets the value set to `on` to allow legacy users with a + symbol in the password to log on without an error.

**Related topics:**

-   <a href="../t_st_create_user_account" class="MCXref xref">Create a user account</a>
-   <a href="../t_st_change_how_long_user_account_information_is_cached" class="MCXref xref">Change how long user account information is cached in memory</a>
-   <a href="../t_st_disable_enable_user_account" class="MCXref xref">Disable or enable a user account</a>
-   <a href="../t_st_lock_unlock_user_account" class="MCXref xref">Lock or unlock a user account</a>
-   <a href="../t_st_edit_user_account_settings" class="MCXref xref">Edit user account settings</a>
-   <a href="../t_st_delete_user_accounts" class="MCXref xref">Delete user accounts</a>
-   <a href="../t_st_delete_purge_user_account" class="MCXref xref">Delete and purge a user account</a>
-   <a href="../t_st_export_single_user_account" class="MCXref xref">Export a single user account</a>
-   <a href="../t_st_unlicensed_users" class="MCXref xref">Unlicensed users</a>
-   <a href="../c_st_protected_folders_accounts" class="MCXref xref">Protected folders and accounts</a>
