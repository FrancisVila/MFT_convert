{
    "title": "Add an administrative role",
    "linkTitle": "Add an administrative role",
    "weight": "210"
}> **Note:**
>
> If you have been using a previous version of SecureTransport and you have upgraded to SecureTransport 5.3.1, only administrative roles which used to have full rights for the Transaction Manager tab (Packages, Install Agents, and Install Functions) will have permissions for TM Settings in the Setup tab.

Use the following procedure to add administrative role.

1.  Select **Accounts > Manage Roles**.  
    The *Administrative Roles* page is displayed.  
    If you do not see roles with Master in the Type column, you are logged on as a user with a limited role.
2.  Click **New Administrative Role**.  
    The *New Administrative Role* window is displayed.
3.  Type the **Role Name**.
4.  Select the **Role Type**.
    -   Select **Master** to give this role complete privileges over the Administration Tool menus selected under **Accessible Menus** and access to all accounts and business units. Only an administrator whose role has Master type can select this.
    -   Select **Limited** to enable limiting the business unit access and privileges for administrators with this role. The Delegated Administrator role has **Role Type** set to **Limited**. A user with a limited role and **Manage Roles** access cannot access Master roles or his own role. **Limited** is the default setting.
5.  Select values from the **Bounce** drop-down list.
    -   Select **Permitted** to enable administrators at this level to bounce (manually signal running server processes to reload their configurations) servers.
    -   Select **Prohibited** to deny these same privileges. **Prohibited** is the default setting.
6.  Under **Accessible Menus**, do the following:
    -   Select the menus that the administrative role can access. Select the check box for the column heading to select all the menus in the column.
    -   Clear the menus that the administrative role cannot access. Clear the check box for the column heading to clear all the menus in the column.
7.  Click **Apply**.  
    The new administrative role is added to the *Administrative Roles* page.

**Related topics:**

-   [Predefined administrative roles](../r_st_predefined_administrative_roles)
-   [Edit an administrative role](../r_st_edit_administrative_role)
