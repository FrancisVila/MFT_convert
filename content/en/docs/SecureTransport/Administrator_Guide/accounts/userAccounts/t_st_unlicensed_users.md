{
    "title": "Unlicensed users",
    "linkTitle": "Unlicensed users",
    "weight": "250"
}The recipient of an ad hoc human-to-human file transfer email or a system-to-human file transfer email does not need all {{< SecureTransport/componentshortname  >}} user account functionality to retrieve the files. If the recipient does not need other {{< SecureTransport/componentshortname  >}} functionality, the recipient can be an unlicensed user. As the name implies, unlicensed users do not require an account license to connect to {{< SecureTransport/componentshortname  >}} to retrieve or reply to messages.

Unlicensed users can log in to {{< SecureTransport/componentshortname  >}} using ST Web Client or one of the {{< SecureTransport/companyname  >}} Email Plug-ins to retrieve files. Using ST Web Client, they can reply once to the sender of a file transfer email. Using Microsoft Outlook or Lotus Notes, they can reply to a file transfer email as they would to any email. They cannot create or forward messages with ad hoc file transfers. For an unlicensed user, ST Web Client does not include the file transfer functions.

If the ad hoc human-to-human file transfer specifies enrollment as an unlicensed user or the System to Human transfer site specifies a security level of `Enroll User - Unlicensed`, the recipient becomes an unlicensed user on enrollment.

Create account templates for unlicensed users. Configure the account template that applies to unlicensed users in the business unit or in the **Default enrollment account template** field on the *AdHoc Setting* page. See <a href="../../../c_st_advancedaccountadministration/c_st_accounttemplates/t_st_accounttemplates#top" class="MCXref xref">Manage account templates</a>, <a href="#Create" class="MCXref xref">Create or edit a business unit</a>, and <a href="../../../c_st_setup/t_st_adhocconfiguration#SetupMenu_1217491348_1052091" class="MCXref xref">Configure adhoc file transfers</a>.

You can also create an unlicensed user account from the *Unlicensed User Accounts* page.

1.  Select **Accounts > Unlicensed Users**. The *Unlicensed User Accounts* page is displayed.

2.  Click **New Account**.  
    The *Settings* pane of the *New Unlicensed User Account* page is displayed.  

    > **Note:**
    >
    > The Address Book Settings are only displayed if the Address Book feature is enabled (the value of the AddressBook.Enabled configuration option is set to true). For Address Book account level configuration instructions, refer to Address Book account level configuration.

3.  For the common fields, see <a href="../t_st_create_user_account#Unlicens" class="MCXref xref">Create a user account</a>.

4.  Select **Allow reply to packages** to permit the unlicensed user to reply once to a received package.

5.  If **Allow this account to login to SecureTransport Server** is not selected, the following fields are not displayed.

6.  Click **Save**.  
    The user account information is saved and displayed in the *Settings* pane of the user account. The other user account tabs are not available for unlicensed users.

You can convert an unlicensed user account to a licensed user account.

1.  Select **Accounts > Unlicensed Users**. The *Unlicensed User Accounts* page is displayed.
2.  Click the name of the account to convert to a licensed user account.  
    The *User Account Settings* page is displayed with details for the selected account.
3.  Click **Convert to Licensed**.  
    The Administration Tool displays the *Settings* pane for the new user account.

The other procedures are the same for licensed and unlicensed user accounts.

**Related topics:**

-   <a href="../t_st_create_user_account" class="MCXref xref">Create a user account</a>
-   <a href="../t_st_change_how_long_user_account_information_is_cached" class="MCXref xref">Change how long user account information is cached in memory</a>
-   <a href="../t_st_disable_enable_user_account" class="MCXref xref">Disable or enable a user account</a>
-   <a href="../t_st_lock_unlock_user_account" class="MCXref xref">Lock or unlock a user account</a>
-   <a href="../t_st_manage_user_account_passwords" class="MCXref xref">Manage user account passwords</a>
-   <a href="../t_st_edit_user_account_settings" class="MCXref xref">Edit user account settings</a>
-   <a href="../t_st_delete_user_accounts" class="MCXref xref">Delete user accounts</a>
-   <a href="../t_st_delete_purge_user_account" class="MCXref xref">Delete and purge a user account</a>
-   <a href="../t_st_export_single_user_account" class="MCXref xref">Export a single user account</a>
-   <a href="../c_st_protected_folders_accounts" class="MCXref xref">Protected folders and accounts</a>
