{
    "title": "Add an administrator account",
    "linkTitle": "Add an administrator account",
    "weight": "190"
}If you have access to the *Administrators* page, you can define multiple administrators with varied access privileges for SecureTransport administration. Master administrators and delegated administrators with the **Manage Administrators** privilege have access to the *Administrators* page by default.

1.  Select **Accounts > Administrators**.  
    The *Administrators* page is displayed.

2.  Click **New Administrator**.  
    The *New Administrator* page is displayed.

3.  In the **Administrator Name** field, enter a name for the administrator. Administrator names are case-sensitive.

4.  Select the **Administrative Role** for the new administrator.

5.  Select **Password is stored locally (not in external directory)** to store the administrator password locally and not in an external directory. If this option is selected, completing the **Password** field is mandatory. If this option is not selected, the only mandatory parameters for creating an administrator are **Administrator Name** and **Administrative Role**.  
    

    <table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Uncheck this option in order for the current administrator to be able to log in, using an external authentication agent (SSO or authentication plug-in).         </td>
      </tr>
</table>

6.  In the **Password** field, enter a password for the administrator. Passwords are case-sensitive.

7.  In the **Confirm Password** field, type the password again to confirm it.

8.  If you have enabled administrators to login using a client certificate on the *Admin Settings* page, the **Certificate DN** field and **Dual authentication** check box are displayed. If client certificates are required or to specify one for this administrator, complete the fields.
    1.  In the **Certificate DN** field, type the Subject field value from the certificate.
    2.  To require the administrator to use both a certificate and password, select **Dual authentication**. If you select this option, you must type the Distinguished Name in the **Certificate DN** field.
    3.  In case the password stored locally is not checked, the Dual authentication will still be visible, allowing current administrator to be logged using dual-factor authentication by an external
    4.  In case the password stored locally is not checked, the Dual authentication will still be visible, allowing current administrator to be logged using dual-factor authentication by an external authentication agent (in this case the plug-in).  
        **Note:** This option will have no effort for SSO-authenticated administrators.  
          

9.  Click **Save** to add the administrator account.  
    The new administrator is displayed in the list of administrators on the *Administrators* page.

**Related topics:**

-   [Edit an administrator account](../t_st_edit_administrator_account)
-   [Delete an administrator account](../t_st_delete_administrator_account)
-   [Lock an administrator account](../t_st_lock_administrator_account)
-   [Unlock an administrator account](../t_st_unlock_administrator_account)
-   [Expire an administrator account password](../t_st_expire_administrator_account_password)
-   [Reset an expired administrator account password](../t_st_reset_expired_administrator_account_password)
-   [Change administrator password](../t_st_change_administrator_password)