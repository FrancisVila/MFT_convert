{
    "title": "Predefined administrative roles",
    "linkTitle": "Predefined administrative roles",
    "weight": "200"
}The following administrative roles are predefined:

-   **Master Administrator** – Access to all menus, tabs, and pages of the Administration Tool. Cannot be modified.
-   **Database Administrator** – Access to the *Database Settings* page only. Access to the *Setup Oracle* page is not included when {{< SecureTransport/componentshortname >}} is running on the embedded database. Only the `dbsetup` administrator can have this role. Information is maintained in the file system so that `dbsetup` can log in to the Administration Tool when the database is not running. Cannot be modified.
-   **Setup Administrator** – Access through the custom **Configure** menu to pages required to perform the post-installation tasks and setup operations described in the . Cannot be modified.
-   **Account Manager** – Access restricted to the *User Accounts*, **Unlicensed User Accounts*, Service Accounts*, *Templates*, and *Business Units* pages on the **Accounts** menu and all pages on the **Access** menu.
-   **Application Manager** – Access restricted to the pages on the **Service Accounts** and **Applications** menus.
-   **Delegated Administrator** – Configurable access to menus and data based on the function the administrator has within an organization. This administrator type is created by a master administrator or a parent delegated administrator.

The following table illustrates the access rights and restrictions of the default restriction levels for {{< SecureTransport/componentshortname  >}} administrators. You can modify the access rights for the Account Manager, Application Manager, and Delegated Administrator roles:

<table>
   <thead>
      <tr>
<th colspan="2" class="HeadE-Column1-Header1">Menus and Pages         </th>
<th style="text-align: center;" class="HeadE-Column1-Header1">Master<br />
Admini-<br />
strator         </th>
<th style="text-align: center;" class="HeadE-Column1-Header1">Setup<br />
Admini-<br />
strator         </th>
<th style="text-align: center;" class="HeadE-Column1-Header1">Account<br />
Manager         </th>
<th style="text-align: center;" class="HeadE-Column1-Header1">Applica-<br />
tion<br />
Manager         </th>
<th style="text-align: center;" class="HeadD-Column1-Header1">Delegated<br />
Admini-<br />
strator         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><strong>Operations</strong>         </td>
         <td>          </td>
         <td>          </td>
         <td>          </td>
         <td>          </td>
         <td>         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>Server Control         </td>
         <td><img src="/Images/SecureTransport/Checkmark_10x9.png" />         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
         <td>—         </td>
         <td>—         </td>
         <td>—         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>Cluster Management         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
         <td>—         </td>
         <td>—         </td>
         <td>—         </td>
         <td>—         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>Server Usage Monitor         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
         <td>—         </td>
         <td>—         </td>
         <td>—         </td>
         <td>—         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>File Tracking         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
         <td>—         </td>
         <td>—         </td>
         <td>—         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>Server Log         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
         <td>—         </td>
         <td>—         </td>
         <td>—         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>Audit Log         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
         <td>—         </td>
         <td>—         </td>
         <td><img src="/Images/SecureTransport/Checkmark_12x11.png" />         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>Server Configuration         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
         <td>—         </td>
         <td>—         </td>
         <td>—         </td>
         <td>—         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>Support Tool         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
         <td>—         </td>
         <td>—         </td>
         <td>—         </td>
         <td>—         </td>
      </tr>
      <tr>
         <td><strong>Setup</strong>         </td>
         <td>          </td>
         <td>          </td>
         <td>          </td>
         <td>          </td>
         <td>         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>Certificates         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
         <td>—         </td>
         <td>—         </td>
         <td>—         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>FTP Settings         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
         <td>—         </td>
         <td>—         </td>
         <td>—         </td>
         <td>—         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>AS2 Settings         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
         <td>—         </td>
         <td>—         </td>
         <td>—         </td>
         <td>—         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>SSH Settings         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
         <td>—         </td>
         <td>—         </td>
         <td>—         </td>
         <td>—         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>Admin Settings         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
         <td>—         </td>
         <td>—         </td>
         <td>—         </td>
         <td>—         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>PeSIT Settings         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
         <td>—         </td>
         <td>—         </td>
         <td>—         </td>
         <td>—         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>AdHoc Settings         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
         <td>—         </td>
         <td>—         </td>
         <td>—         </td>
         <td>—         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>Database Settings         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
         <td>—         </td>
         <td>—         </td>
         <td>—         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>{{< SecureTransport/companyname  >}} Sentinel         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
         <td>—         </td>
         <td>—         </td>
         <td>—         </td>
         <td>—         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>Server License         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
         <td>—         </td>
         <td>—         </td>
         <td>—         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>Command Logging         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
         <td>—         </td>
         <td>—         </td>
         <td>—         </td>
         <td>—         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>Transfer Logging         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
         <td>—         </td>
         <td>—         </td>
         <td>—         </td>
         <td>—         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>Holiday Schedule         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
         <td>—         </td>
         <td>—         </td>
         <td>—         </td>
         <td>—         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>Miscellaneous         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
         <td>—         </td>
         <td>—         </td>
         <td>—         </td>
         <td>—         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>File Archiving         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
         <td>—         </td>
         <td>—         </td>
         <td>—         </td>
         <td>—         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>TM Settings         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
         <td>—         </td>
         <td>—         </td>
         <td>—         </td>
         <td>—         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>Network Zones         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
         <td>—         </td>
         <td>—         </td>
         <td>—         </td>
         <td>—         </td>
      </tr>
      <tr>
         <td>Authentication - All submenus         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
         <td>—         </td>
         <td>—         </td>
         <td>—         </td>
         <td>—         </td>
      </tr>
      <tr>
         <td><strong>Account</strong>         </td>
         <td>          </td>
         <td>          </td>
         <td>          </td>
         <td>          </td>
         <td>         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>User Accounts         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
         <td>—         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
         <td>—         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>Unlicensed Users         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
         <td>—         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
         <td>—         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>Service Accounts         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
         <td>—         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>Import/Export         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
         <td>—         </td>
         <td>—         </td>
         <td>—         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>Administrators         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
         <td>—         </td>
         <td>—         </td>
         <td>—         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>Change Password         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
         <td>—         </td>
         <td>—         </td>
         <td>—         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>Manage Roles         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
         <td>—         </td>
         <td>—         </td>
         <td>—         </td>
         <td>—         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>Account Templates         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
         <td>—         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
         <td>—         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>Site Templates         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
         <td>—         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
         <td>—         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>System         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
         <td>—         </td>
         <td>—         </td>
         <td>—         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>Business Units         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
         <td>—         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
         <td>—         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>Active Users         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
         <td>—         </td>
         <td>—         </td>
         <td>—         </td>
         <td>—         </td>
      </tr>
      <tr>
         <td>Access—All submenus         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
         <td>—         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
         <td>—         </td>
         <td>—         </td>
      </tr>
      <tr>
         <td>Application—All submenus         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
         <td>—         </td>
         <td>—         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
      </tr>
      <tr>
         <td>Routes—All submenus         </td>
         <td><img src="/Images/SecureTransport/Checkmark_11x10.png" />         </td>
         <td>—         </td>
         <td>—         </td>
         <td>—         </td>
         <td>—         </td>
      </tr>
   </tbody>
</table>

**Related topics:**

-   <a href="../r_st_add_administrative_role" class="MCXref xref">Add an administrative role</a>
-   <a href="../r_st_edit_administrative_role" class="MCXref xref">Edit an administrative role</a>
