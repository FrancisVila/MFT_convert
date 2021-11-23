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

-   [Create a user account](../t_st_create_user_account)
-   [Change how long user account information is cached in memory](../t_st_change_how_long_user_account_information_is_cached)
-   [Disable or enable a user account](../t_st_disable_enable_user_account)
-   [Manage user account passwords](../t_st_manage_user_account_passwords)
-   [Edit user account settings](../t_st_edit_user_account_settings)
-   [Delete user accounts](../t_st_delete_user_accounts)
-   [Delete and purge a user account](../t_st_delete_purge_user_account)
-   [Export a single user account](../t_st_export_single_user_account)
-   [Unlicensed users](../t_st_unlicensed_users)
-   [Protected folders and accounts](../c_st_protected_folders_accounts)
