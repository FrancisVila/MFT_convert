{
    "title": "Change how long user account information is cached in memory",
    "linkTitle": "Change how long user account information is cached in memory",
    "weight": "180"
}You can set how long SecureTransport keeps the user account information cached in memory by editing the `TransactionManager.AccountContextAgent.cacheTimeout` parameter on the *Server Configuration* page. The default value is `900` seconds. Change the value to keep the cached information for a longer or shorter period of time. You can also set it to null or a negative value to not cache the account information. Changes you make to an account do not show up until after the cache is refreshed.

**Related topics:**

-   [Create a user account](../t_st_create_user_account)
-   [Disable or enable a user account](../t_st_disable_enable_user_account)
-   [Lock or unlock a user account](../t_st_lock_unlock_user_account)
-   [Manage user account passwords](../t_st_manage_user_account_passwords)
-   [Edit user account settings](../t_st_edit_user_account_settings)
-   [Delete user accounts](../t_st_delete_user_accounts)
-   [Delete and purge a user account](../t_st_delete_purge_user_account)
-   [Export a single user account](../t_st_export_single_user_account)
-   [Unlicensed users](../t_st_unlicensed_users)
-   [Protected folders and accounts](../c_st_protected_folders_accounts)
