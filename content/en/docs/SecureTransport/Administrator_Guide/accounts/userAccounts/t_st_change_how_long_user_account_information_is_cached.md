{
    "title": "Change how long user account information is cached in memory",
    "linkTitle": "Change how long user account information is cached in memory",
    "weight": "170"
}You can set how long <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> keeps the user account information cached in memory by editing the `TransactionManager.AccountContextAgent.cacheTimeout` parameter on the *Server Configuration* page. The default value is `900` seconds. Change the value to keep the cached information for a longer or shorter period of time. You can also set it to null or a negative value to not cache the account information. Changes you make to an account do not show up until after the cache is refreshed.

**Related topics:**

-   <a href="../t_st_create_user_account" class="MCXref xref">Create a user account</a>
-   <a href="../t_st_disable_enable_user_account" class="MCXref xref">Disable or enable a user account</a>
-   <a href="../t_st_lock_unlock_user_account" class="MCXref xref">Lock or unlock a user account</a>
-   <a href="../t_st_manage_user_account_passwords" class="MCXref xref">Manage user account passwords</a>
-   <a href="../t_st_edit_user_account_settings" class="MCXref xref">Edit user account settings</a>
-   <a href="../t_st_delete_user_accounts" class="MCXref xref">Delete user accounts</a>
-   <a href="../t_st_delete_purge_user_account" class="MCXref xref">Delete and purge a user account</a>
-   <a href="../t_st_export_single_user_account" class="MCXref xref">Export a single user account</a>
-   <a href="../t_st_unlicensed_users" class="MCXref xref">Unlicensed users</a>
-   <a href="../c_st_protected_folders_accounts" class="MCXref xref">Protected folders and accounts</a>
