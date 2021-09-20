{
    "title": "Predefined administrative roles",
    "linkTitle": "Predefined administrative roles",
    "weight": "210"
}The following administrative roles are predefined:

-   **Master Administrator** – Access to all menus, tabs, and pages of the Administration Tool. Cannot be modified.
-   **Database Administrator** – Access to the *Database Settings* page only. Access to the *Setup Oracle* page is not included when SecureTransport is running on the embedded database. Only the `dbsetup` administrator can have this role. Information is maintained in the file system so that `dbsetup` can log in to the Administration Tool when the database is not running. Cannot be modified.
-   **Setup Administrator** – Access through the custom **Configure** menu to pages required to perform the post-installation tasks and setup operations described in the <span cshid="gs" data-version="5.3.5">*SecureTransport Getting Started Guide*</span>. Cannot be modified.
-   **Account Manager** – Access restricted to the *User Accounts*, **Unlicensed User Accounts*, Service Accounts*, *Templates*, and *Business Units* pages on the **Accounts** menu and all pages on the **Access** menu.
-   **Application Manager** – Access restricted to the pages on the **Service Accounts** and **Applications** menus.
-   **Delegated Administrator** – Configurable access to menus and data based on the function the administrator has within an organization. This administrator type is created by a master administrator or a parent delegated administrator.

The following table illustrates the access rights and restrictions of the default restriction levels for SecureTransport administrators. You can modify the access rights for the Account Manager, Application Manager, and Delegated Administrator roles:

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">If, as the <code>dbsetup</code> administrator, you change your password, have your password expired, or have your account disabled or enabled while there is no connection to the database, that change is not recorded in the database. The next time you log in as the <code>dbsetup</code> administrator with the database connected, the change is overwritten by the information from the database.         </td>
      </tr>
</table>

**Related topics:**

-   [Add an administrative role](../r_st_add_administrative_role)
-   [Edit an administrative role](../r_st_edit_administrative_role)
