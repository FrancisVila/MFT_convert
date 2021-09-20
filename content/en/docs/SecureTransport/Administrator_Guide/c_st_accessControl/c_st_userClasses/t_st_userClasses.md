{
    "title": "Manage user classes",
    "linkTitle": "Manage user classes",
    "weight": "220"
}Use the *User Classes* page to add, enable, disable, reorder, and delete user classes.

The following topics provide user class examples and how-to instructions for managing user classes:

-   [Add a user class](#add)
-   [Enable or disable a user class](#enable)
-   [Edit a user class](#edit)
-   [Reorder user classes](#reorder)
-   [Delete a user class](#delete)
-   [User class examples](#user)

**Related topics:**

-   [Default user classes](../c_st_default_user_classes)
-   [Custom expressions](../c_st_custom_expressions)

## <span id="Add"></span>Add a user class

Use the following procedure to add a user class.

1.  Select **Access > User Classes**.  
    The *User Classes* page is displayed.
2.  Click **New User Class**. A new line is displayed in the *User Classes List*.
3.  In the **Class Name** field, enter the name for the user class to create.  
    If the name is not unique, SecureTransport uses only the first user class with that name in the *User Class List*.
4.  In the **User Type** field, select the predefined user type for the user class.
5.  In the **User Name** field, enter one of the following:
    -   The user name, such as the UNIX-based system login name, the Windows user name, virtual user name, LDAP user name, SiteMinder, or Single Sign-On (SSO) user name.
    -   On Windows, type either a `username`, `COMPUTERNAME\username`, or `DOMAIN\username`.
    -   A pattern using `*` and `?` to include matching users. For example, `*` includes all users.
    -   Only one pattern is allowed.
6.  In the **User Group** field, enter one of the following:
    -   The name or numerical GID of the group assigned to the user. If all characters are numeric, the value is a GID. Otherwise, it is group name. On Windows, the value can be either the Windows security identifier (SID) of the group or the GID from the `group` file.
    -   An asterisk (`*`) to include users in all groups.
7.  In the **From Address** field, enter a host name, a host name pattern, an IP address, or subnet specification. For valid values, see [IP addresses and host names](../../../c_st_ipaddressesandhostnames).  
    Only one host name, an IP address, or subnet specification is allowed.
8.  To define the user class using other user attributes or LDAP attributes, enter a **Custom expression**. See [Custom expressions](../c_st_custom_expressions).
9.  Click the Save icon (![Save](SaveIcon2_13x13.png)) in the **Edit** column.  
    The status of a new user class is set to Disabled.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Because of the different ways <span>SecureTransport</span> treats the path name specification of the download or upload directory for real and virtual users when download or upload restrictions are defined, you should avoid selecting <code>*</code> to match all users.         </td>
      </tr>
</table>

## <span id="Enable"></span>Enable or disable a user class

Use the following procedure to enable or disable a user class.

1.  Select **Access > User Classes**.  
    The *User Classes* page is displayed.
2.  In the *User Classes List*, select the check box for each user class to modify.
3.  Click **Enable** or **Disable**.  
    The icons in the **Class Name** column change to indicate the status of the classes.

## <span id="Edit"></span>Edit a user class

Use the following procedure to edit a user class.

1.  Select **Access > User Classes**.  
    The *User Classes* page is displayed.
2.  In the *User Classes List*, click the Edit icon (![Edit](SaveIcon2_13x13.png)) in the **Edit** column for the user class entry to edit.
3.  Make the required changes to the fields in the row.
4.  Click the Save icon (![Save](SaveIcon2_13x13.png)) in the **Edit** column.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">To cancel an add operation, select <strong>Access &gt; User Classes</strong> again.         </td>
      </tr>
</table>

## <span id="Reorder"></span>Reorder user classes

If a user belongs to multiple classes, SecureTransport categorizes the user as belonging to the first matching class in the *User Classes List*.

If two or more user classes have the same name, SecureTransport processes only the first of those classes in the *User Classes List*.

1.  Select **Access > User Classes**.  
    The *User Classes* page is displayed.
2.  In the *User Classes List*, click **Reorder**.  
    Up and down arrows are displayed in a column before the **Class Name** column in the *User Classes List*.
3.  Drag the rows of the *User Classes List* to the required order.
4.  Click **Save Order**.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">To cancel an edit operation, select <strong>Access &gt; User Classes</strong> again.         </td>
      </tr>
</table>

## <span id="Delete"></span>Delete a user class

Use the following procedure to delete a user class.

1.  Select **Access > User Classes**.  
    The *User Classes* page is displayed.
2.  In the *User Classes List*, select the check box for each user class to delete.
3.  Click **Delete**.
4.  Click **OK** in the confirmation dialog box.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">To cancel a reorder operation, select <strong>Access &gt; User Classes</strong> again.         </td>
      </tr>
</table>

## <span id="User"></span>User class examples

The following example illustrates some sample user class entries.

The following table summarizes the user classes and describes their functions.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">If you delete a user class, it is best to remove all references to that user class from all access rules. <span>SecureTransport</span> ignores access rules that reference an undefined user class.         </td>
      </tr>
</table>

Because the default RealClass and VirtClass include all users, all SecureTransport users are in one of the four classes.
