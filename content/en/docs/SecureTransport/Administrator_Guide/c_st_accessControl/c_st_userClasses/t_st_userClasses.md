{
    "title": "Manage user classes",
    "linkTitle": "Manage user classes",
    "weight": "210"
}Use the *User Classes* page to add, enable, disable, reorder, and delete user classes.

The following topics provide user class examples and how-to instructions for managing user classes:

-   <a href="#Add" class="MCXref xref">Add a user class</a>
-   <a href="#Enable" class="MCXref xref">Enable or disable a user class</a>
-   <a href="#Edit" class="MCXref xref">Edit a user class</a>
-   <a href="#Reorder" class="MCXref xref">Reorder user classes</a>
-   <a href="#Delete" class="MCXref xref">Delete a user class</a>
-   <a href="#User" class="MCXref xref">User class examples</a>

**Related topics:**

-   <a href="../c_st_default_user_classes" class="MCXref xref">Default user classes</a>
-   <a href="../c_st_custom_expressions" class="MCXref xref">Custom expressions</a>

<span id="Add"></span>

## Add a user class

Use the following procedure to add a user class.

1.  Select **Access > User Classes**.  
    The *User Classes* page is displayed.
2.  Click **New User Class**. A new line is displayed in the *User Classes List*.
3.  In the **Class Name** field, enter the name for the user class to create.  
    If the name is not unique, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> uses only the first user class with that name in the *User Class List*.
4.  In the **User Type** field, select the predefined user type for the user class.
5.  In the **User Name** field, enter one of the following:
    -   The user name, such as the UNIX-based system login name, the Windows user name, virtual user name, LDAP user name, SiteMinder, or Single Sign-On (SSO) user name.
    -   On Windows, type either a `username`, `COMPUTERNAME\username`, or `DOMAIN\username`.
    -   A pattern using `*` and `?` to include matching users. For example, `*` includes all users.
    -   Only one pattern is allowed.
6.  In the **User Group** field, enter one of the following:
    -   The name or numerical GID of the group assigned to the user. If all characters are numeric, the value is a GID. Otherwise, it is group name. On Windows, the value can be either the Windows security identifier (SID) of the group or the GID from the `group` file.
    -   An asterisk (`*`) to include users in all groups.
7.  In the **From Address** field, enter a host name, a host name pattern, an IP address, or subnet specification. For valid values, see <a href="../../../c_st_ipaddressesandhostnames" class="MCXref xref">IP addresses and host names</a>.  
    Only one host name, an IP address, or subnet specification is allowed.
8.  To define the user class using other user attributes or LDAP attributes, enter a **Custom expression**. See <a href="../c_st_custom_expressions#Custom" class="MCXref xref">Custom expressions</a>.
9.  Click the Save icon (![Save](/Images/SecureTransport/SaveIcon2_13x13.png)) in the **Edit** column.  
    The status of a new user class is set to Disabled.

> **Note:**
>
> To cancel an add operation, select Access &gt; User Classes again.

<span id="Enable"></span>

## Enable or disable a user class

Use the following procedure to enable or disable a user class.

1.  Select **Access > User Classes**.  
    The *User Classes* page is displayed.
2.  In the *User Classes List*, select the check box for each user class to modify.
3.  Click **Enable** or **Disable**.  
    The icons in the **Class Name** column change to indicate the status of the classes.

<span id="Edit"></span>

## Edit a user class

Use the following procedure to edit a user class.

1.  Select **Access > User Classes**.  
    The *User Classes* page is displayed.
2.  In the *User Classes List*, click the Edit icon (![Edit](/Images/SecureTransport/EditIcon2_12x12.png)) in the **Edit** column for the user class entry to edit.
3.  Make the required changes to the fields in the row.
4.  Click the Save icon (![Save](/Images/SecureTransport/SaveIcon2_13x13.png)) in the **Edit** column.

> **Note:**
>
> To cancel an edit operation, select Access &gt; User Classes again.

<span id="Reorder"></span>

## Reorder user classes

If a user belongs to multiple classes, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> categorizes the user as belonging to the first matching class in the *User Classes List*.

If two or more user classes have the same name, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> processes only the first of those classes in the *User Classes List*.

1.  Select **Access > User Classes**.  
    The *User Classes* page is displayed.
2.  In the *User Classes List*, click **Reorder**.  
    Up and down arrows are displayed in a column before the **Class Name** column in the *User Classes List*.
3.  Drag the rows of the *User Classes List* to the required order.
4.  Click **Save Order**.

> **Note:**
>
> To cancel a reorder operation, select Access &gt; User Classes again.

<span id="Delete"></span>

## Delete a user class

Use the following procedure to delete a user class.

1.  Select **Access > User Classes**.  
    The *User Classes* page is displayed.
2.  In the *User Classes List*, select the check box for each user class to delete.
3.  Click **Delete**.
4.  Click **OK** in the confirmation dialog box.

> **Note:**
>
> If you delete a user class, it is best to remove all references to that user class from all access rules. SecureTransport ignores access rules that reference an undefined user class.

<span id="User"></span>

## User class examples

The following example illustrates some sample user class entries.

The following table summarizes the user classes and describes their functions.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">User class         </th>
<th class="HeadD-Column1-Header1">Definition         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Internal         </td>
         <td>Includes users of any type, name, or group, who connect from IP address that start with <code>192.168</code>.         </td>
      </tr>
      <tr>
         <td>Partner         </td>
         <td>Includes users of real type with GID 3000 who do not connect from IP address that start with <code>192.168</code>.         </td>
      </tr>
      <tr>
         <td>Employees1         </td>
         <td>Includes users of virtual type whose user name begins with <code>A</code>, are in the <code>employees</code> user group, have user ID greater than or equal to 500, and do not fall into the Internal class.         </td>
      </tr>
      <tr>
         <td>VirtClass         </td>
         <td>Includes all virtual users who do not fall into the Internal or Employee1 classes.         </td>
      </tr>
      <tr>
         <td>RealClass         </td>
         <td>Includes all real users who do not fall into the Partner class.         </td>
      </tr>
   </tbody>
</table>

Because the default RealClass and VirtClass include all users, all <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> users are in one of the four classes.
