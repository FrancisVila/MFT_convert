{
    "title": "User accounts",
    "linkTitle": "User accounts",
    "weight": "150"
}Use the *User Accounts* page to display, create, modify, and delete user accounts.

## See available user accounts

The *User Accounts* page displays a list of accounts. You can display a list of all user accounts, or search the list based on account name or login name.

-   Select **Accounts > User Accounts**. The *User Accounts* page is displayed.

The *User Accounts* page lists 100 account entries per page by default.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">You can change the default number of records per page by editing the <code>LinesPerPage</code> parameter in the file <code>&lt;FILEDRIVEHOME&gt;/tomcat/admin/webapps/coreadmin/WEB-INF/web.xml</code>.         </td>
      </tr>
</table>

## Search for a user account

You can search the user accounts database and display the results on the *User Accounts* page.

1.  Select **Accounts > User Accounts**. The *User Accounts* page is displayed.
2.  In the *Search* pane, type all or part of a user account name and click **Search**. Wildcards are not accepted.  
    The search results are displayed on the *User Accounts* page.
3.  (Optional) Click **More Options** to expand the Search panel with Account status checkboxes as additional search filters.  
    Note that the **Pending** and **Rejected** account statuses are introduced as part of the Maker-Checker flow.  
4.  (Optional) Narrow your list of search results. In the *Search* pane, append or prepend your search string.  
    After you perform a search, the **Show All** button is displayed.
5.  To display all accounts, click **Show All**.

## Page through the list of user accounts

Use the browse buttons at the top and bottom of the page.

## View account settings

Use the *Settings* pane to view and modify account status and settings. When an account is defined for an external authenticated user, such as an LDAP or SiteMinder user, the external UID, GID, and home folder attributes are replaced with the values taken from the account information while the external user is logged into SecureTransport.

1.  Select **Accounts > User Accounts**. The *User Accounts* page is displayed.
2.  Click the name of the account whose settings you want to view.  
    The *Settings* pane is displayed with details for the selected account.

The following topics describe managing user accounts:

-   [Create a user account](t_st_create_user_account)
-   [Change how long user account information is cached in memory](t_st_change_how_long_user_account_information_is_cached)
-   [Disable or enable a user account](t_st_disable_enable_user_account)
-   [Lock or unlock a user account](t_st_lock_unlock_user_account)
-   [Manage user account passwords](t_st_manage_user_account_passwords)
-   [Edit user account settings](t_st_edit_user_account_settings)
-   [Delete user accounts](t_st_delete_user_accounts)
-   [Delete and purge a user account](t_st_delete_purge_user_account)
-   [Export a single user account](t_st_export_single_user_account)
-   [Unlicensed users](t_st_unlicensed_users)
-   [Protected folders and accounts](c_st_protected_folders_accounts)
