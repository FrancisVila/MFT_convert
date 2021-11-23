{
    "title": "Edit an administrator account",
    "linkTitle": "Edit an administrator account",
    "weight": "190"
}> **Note:**
>
> If you are using a Firefox browser, disable the auto complete function prior to editing an administrator account settings.

If you have access to the *Administrators* page, you can edit an Administrator account. Master administrators and delegated administrators with the **Manage Administrators** privilege are granted access to the *Administrators* page by default.

## Account password stored locally

If the administrator account was created with **Password is stored locally (not in external directory)** selected and the account password is stored locally, use the following instructions to edit administrator account settings.

1.  Select **Accounts > Administrators**.  
    The *Administrators* page is displayed.
2.  Click the administrator entry you want to edit.  
    The *Edit Administrator* page is displayed.
3.  Make any desired changes in the *Administrator Account Status* pane. You can lock the account, expire the administrator account password, or reset an expired password.
4.  Make any desired changes to the fields in the *Edit Administrator Settings* pane.  
    You can change the **Administrative Role** and the administrator password. If you have enabled administrators to login using a client certificate on the *Login Settings* page, you can change the **Certificate DN** field and **Dual authentication** check box. If the **Administrative Role** is set to Delegated Administrator, you can also modify the **Delegated Administrator Settings**.
5.  Click **Save** to apply the changes.

## Account password stored externally

If the administrator account was created with **Password is stored locally (not in external directory)** not selected and the account password is stored externally, use the following instructions to edit administrator account settings. This option will allow the administrator to be authenticated by an external authentication agent (Identity provider).

1.  Select **Accounts > Administrators**  
    The *Administrators* page is displayed.
2.  Click the administrator entry you want to edit.  
    The *Edit Administrator* page is displayed.
3.  Make any desired changes in the *Administrator Account Status* pane. You can only lock and unlock the account.
4.  Make any desired changes to the fields in the *Edit Administrator Settings* pane. You can only change the **Administrative Role**  
    **Note:** If you have enabled administrators to log in using a client certificate on the **Login Settings** page, you can change the **Dual authentication** check box.  
5.  Click **Save** to apply the changes.

**Related topics:**

-   [Add an administrator account](../t_st_add_administrator_account)
-   [Delete an administrator account](../t_st_delete_administrator_account)
-   [Lock an administrator account](../t_st_lock_administrator_account)
-   [Unlock an administrator account](../t_st_unlock_administrator_account)
-   [Expire an administrator account password](../t_st_expire_administrator_account_password)
-   [Reset an expired administrator account password](../t_st_reset_expired_administrator_account_password)
-   [Change administrator password](../t_st_change_administrator_password)
