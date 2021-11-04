{
    "title": "Lock or unlock a user account",
    "linkTitle": "Lock or unlock a user account",
    "weight": "190"
}Use the following procedure to lock or unlock a user account.

1.  Select **Accounts > User Accounts**. The *User Accounts* page is displayed.

2.  Click the name of the account that you want to lock or unlock.  
    The *Settings* pane is displayed with details for the selected account.

3.  Click **Lock Account** or **Unlock Account**, depending on the current status of the account.  

    > **Note:**
    >
    > An account can be locked or unlocked only if it has a user associated with it. When an account is locked, the user associated with it cannot log in to the SecureTransport Server. However, if an account is locked, server-initiated transfers associated with that account are not affected.

Accounts are locked when:

-   When an administrator locks an account using the lock user account procedure.

-   When the number failed login attempts exceeds the configured number of allowed attempts.

-   When the number failed ssh key authentication login attempts exceeds the configured number of allowed attempts.

-   When the number successful login attempts exceeds the configured number of successful attempts.

-   When the day count exceeds the configured number of days between password changes.  

    > **Note:**
    >
    > Change password failures are counted as failed login attempts.

**Related topics:**

-   <a href="../t_st_create_user_account" class="MCXref xref">Create a user account</a>
-   <a href="../t_st_change_how_long_user_account_information_is_cached" class="MCXref xref">Change how long user account information is cached in memory</a>
-   <a href="../t_st_disable_enable_user_account" class="MCXref xref">Disable or enable a user account</a>
-   <a href="../t_st_manage_user_account_passwords" class="MCXref xref">Manage user account passwords</a>
-   <a href="../t_st_edit_user_account_settings" class="MCXref xref">Edit user account settings</a>
-   <a href="../t_st_delete_user_accounts" class="MCXref xref">Delete user accounts</a>
-   <a href="../t_st_delete_purge_user_account" class="MCXref xref">Delete and purge a user account</a>
-   <a href="../t_st_export_single_user_account" class="MCXref xref">Export a single user account</a>
-   <a href="../t_st_unlicensed_users" class="MCXref xref">Unlicensed users</a>
-   <a href="../c_st_protected_folders_accounts" class="MCXref xref">Protected folders and accounts</a>
