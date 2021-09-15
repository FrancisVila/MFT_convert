{
    "title": "Managing password files",
    "linkTitle": "Managing password files",
    "weight": "250"
}Use the *Password Files* page to add, enable, disable, and delete password entries for real users.

By default the *Password File List* contains a disabled entry for real users. On a UNIX-based system, you cannot delete this entry or add an entry. On Windows, you can delete the entry for real uses and add password vault entries. SecureTransport stores password vaults in the SecureTransport database.

The following topics provide how-to instructions for managing password files and password vaults:

-   [Add password file entry](#add_pass)
-   [Enable or disable password file entries](#enable)
-   [Edit a password file entry](#edit)
-   [Delete password file entries](#delete)
-   [Add a user to a password vault](#add)
-   [Edit a user in a password vault](#edit_user)
-   [Delete users from a password vault](#delete_users)
-   [Purge a password vault](#purge)

**Related topic:**

-   [Real users](../c_st_real_users)

## <span id="Add_pass"></span>Add password file entry

Use the following procedure to a password file entry.

1.  Select **Accounts > System**.  
    The *Password Files* page is displayed.
2.  Click **Add Password File**.  
    A new row is displayed in the table.
3.  In the **Type** list, select `Real Users` or `Password Vault`.
4.  If you selected `Password Vault`, in the **Location** column, enter a Windows file path for the password vault.  
    SecureTransport stores the password vault entries in the database and uses the value of the **Location** field to identify the password vault. SecureTransport does not create a file for the password vault.
5.  Click the Save icon (![Save](SaveIcon_13x13.png)) in the last column of the list.

## <span id="Enable"></span>Enable or disable password file entries

Once you have created the password file entry, you can enable it. You can disable entries you want to keep but not use.

1.  Select **Accounts > System**.  
    The *Password Files* page is displayed.
2.  Select the entries to enable or disable.
3.  Click **Enable** or **Disable**.

## <span id="Edit"></span>Edit a password file entry

Use the following procedure to edit a password file entry.

1.  Click the Edit icon (![Edit](SaveIcon_13x13.png)) in the last column of the entry to edit.
2.  Make changes in the **Type** or **Location** columns.
3.  Click the Save icon (![Save](SaveIcon_13x13.png)) in the last column.

## <span id="Delete"></span>Delete password file entries

If you no longer want to keep the password file entry, you can delete it.

1.  Select **Accounts > System**.  
    The *Password Files* page is displayed.
2.  Select the entries to delete.
3.  Click **Delete**.  
    SecureTransport displays a confirmation dialog.
4.  Click **OK** to delete the entries.

## <span id="Add"></span>Add a user to a password vault

Use the following procedure to add a user to password vault.

1.  Select **Accounts > System**.  
    The *Password Files* page is displayed.
2.  Click **Edit File** in the **File Action** column for the password vault entry.  
    The *Edit Password File* page is displayed.
3.  Click **Add Vault Entry**.  
    A new row is displayed in the table.
4.  In the **Domain\\Username** column, type the domain or computer name and user name using one of the following formats:  
    `Domain\Username` or `Computer\Username`  
    where `Username` is the valid domain or computer user.
5.  In the **Password** column, type the password of the user.
6.  Click the Save icon (![Save](SaveIcon_13x13.png)) in the last column of the list.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">On UNIX-based platforms, <code>Real Users</code> is the only option in the <strong>Type</strong> list. On Windows platforms, there are two options: <code>Real Users</code> and <code>Password Vault</code>.         </td>
      </tr>
</table>

## <span id="Edit_user"></span>Edit a user in a password vault

Use the following procedure to edit a user in a password vault.

1.  Select **Accounts > System**.  
    The *Password Files* page is displayed.
2.  Click **Edit File** in the **File Action** column for the password vault entry.  
    The *Edit Password File* page is displayed.
3.  Click the Edit icon (![Edit](SaveIcon_13x13.png)) in the last column of the user to edit.
4.  Make changes in the **Domain\\Username** or **Password** columns.
5.  Click the Save icon (![Save](SaveIcon_13x13.png)) in the last column of the list.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">If the password is incorrect, or the specified user does not have the relevant Windows local or domain permissions, the addition of the user fails with an appropriate error message. If the reason is wrong permissions, contact the domain administrator.         </td>
      </tr>
</table>

## <span id="Delete_users"></span>Delete users from a password vault

Use the following procedure to delete users from a password vault.

1.  Select **Accounts > System**.  
    The *Password Files* page is displayed.
2.  Click **Edit File** in the **File Action** column for the password vault entry.  
    The *Edit Password File* page is displayed.
3.  Select the entries to delete.
4.  Click **Delete**.  
    SecureTransport displays a confirmation dialog.
5.  Click **OK** to delete the users.

## <span id="Purge"></span>Purge a password vault

Use the following procedure to purge a password vault.

1.  Select **Accounts > System**.  
    The *Password Files* page is displayed.
2.  Click **Purge File** in the **File Action** column for the password vault entry.  
    SecureTransport immediately deletes the password vault from the database and deletes the entry from the *Password Files* page.
