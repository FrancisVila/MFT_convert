{
    "title": "Delegated administration",
    "linkTitle": "Delegated administration",
    "weight": "170"
}{{< SecureTransport/componentshortname  >}} provides a customizable administrator type called a *delegated administrator*. The delegated administrator works with specific user groups referred to as business units. User accounts, service accounts, account templates, unlicensed user accounts, and applications are divided into business unit groups and each user or service account, unlicensed user, and account template is assigned to only one business unit.

Each delegated administrator is assigned one or more business units that determine the user accounts, service accounts, unlicensed user accounts, account templates, and applications managed by that administrator. Tracking information is also displayed based on the business unit assigned.

When you log in to the {{< SecureTransport/componentshortname  >}} Administration Tool as a delegated administrator, you see a subset of the menus and pages normally available. You are allowed to view the file transfer tracking information, accounts, and applications that are assigned to your business unit.

As a delegated administrators with the **Manage Administrators** privilege, you can create other delegated administrators and perform the following actions:

-   Delegate to the new administrator any privileges that you have
-   Assign your business unit or any child business unit to the new administrator

## Maker and Checker

With SecureTrasnport version 5.3.8 and later, there are two additional available "roles" of the delegated administrator, defined by specific permissions: *Maker* and *Checker*.

-   The Maker is a delegated administrator who can create and update user accounts. Accounts created by the Maker will remain in "Pending" verification status until further processing by a Checker.
-   The Checker is a delegated administrator who can view in read-only mode all settings associated with an account. The Checker has the responsibility to review and accept or reject the newly created account by the Maker. In fact, these are the only actions the Checker privileges grant: the rest of the Checker permissions are read-only.

The concept of the Maker and Checker is to separate the responsibilities and duties of account creation and account approval. These two roles complement each other and the Checker acts as a second level of user account approval.

When you create a delegated administrator, you can either assign **Read Only** or **Checker Rights** or **Maker Rights**; or you could use any combination of the other available privileges.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Privilege         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Read Only         </td>
         <td>Allows the administrator to view the pages only. This administrator cannot make any changes. Use Read Only for auditing.         </td>
      </tr>
      <tr>
         <td>Checker Rights         </td>
         <td>Allows the administrator to inspect all settings of user, service and template accounts in an assigned business unit. The Checker administrator can also approve or reject accounts created by a Maker administrator in the assigned business unit.         </td>
      </tr>
      <tr>
         <td>Maker Rights         </td>
         <td>Allows the administrator to create user, service and template accounts in an assigned business unit. The Maker administrator can update all account settings before submitting the accounts for approval by Checker administrator.         </td>
      </tr>
      <tr>
         <td>Create Users         </td>
         <td><p>Allows the administrator to create new accounts for an assigned business unit outside of the Maker-Checker user creation flow.</p>         </td>
      </tr>
      <tr>
         <td>Update Users         </td>
         <td>Allows the administrator to modify existing accounts for an assigned business unit outside of the Maker-Checker user creation flow.         </td>
      </tr>
      <tr>
         <td>HelpDesk Rights         </td>
         <td>Allows the administrator to change the password of users in an assigned business unit. The administrator can also enable or disable a user in the assigned business unit.         </td>
      </tr>
      <tr>
         <td>Audit Log Rights         </td>
         <td>Allows the delegated administrator to access Audit Log entries of actions performed by all administrators. When deselected, the administrator can access only the audit log entries of actions performed by their account and no one else's.         </td>
      </tr>
      <tr>
         <td>Manage Administrators         </td>
         <td>Allows the administrator to create, modify, and delete delegated administrators for an assigned business unit.         </td>
      </tr>
      <tr>
         <td>Manage Business Units         </td>
         <td>Allows the administrator to create, modify, and delete business units.         </td>
      </tr>
      <tr>
         <td>Manage Applications         </td>
         <td>Allows the administrator to create, modify, and delete applications other than Shared Folder type applications for an assigned business unit.         </td>
      </tr>
      <tr>
         <td>Manage Shared Folders Applications         </td>
         <td>Allows the administrator to create, modify, and delete Shared Folder type applications for an assigned business unit.         </td>
      </tr>
      <tr>
         <td>Manage Route Package Templates         </td>
         <td><p>Allows the administrator to create, modify, and delete route package templates.</p>
<blockquote>
<p><strong>Note:</strong></p>
<p>In order these privileges to take effect, the appropriate administrative role should be updated to allow access to the Routes Menu.</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td>Manage 'External Script' Step         </td>
         <td><p>Allows the administrator to create, modify, and delete any <strong>External Script</strong> steps in a route belonging to route package or route package template.</p>
<blockquote>
<p><strong>Note:</strong></p>
<p>In order for these privileges to take effect, the appropriate administrative role should be updated to allow access to the Routes Menu.</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td>Manage 'Run as root external scripts'         </td>
         <td>Allows the administrator to modify the <strong>Run as root administrator</strong> External Script property.
<blockquote>
<p><strong>Note:</strong></p>
<p>In order for these privileges to take effect, the administrator should have privilege to manage External Script step.</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td>Manage Login Restriction Policies         </td>
         <td>Allows the administrator to create and maintain login restriction policies. They can also create and manage login restriction policy entries.         </td>
      </tr>
   </tbody>
</table>

When each delegated administrator delegates privileges and assigns business unit to delegated administrators he creates, the result is a hierarchy of delegated administrators where those higher in the hierarchy can have greater responsibility and more privileges than those below them.

For example, a finance delegated administrator with permission for the finance business unit can create an audit delegated administrator who can view the Administration Tool pages and two other delegated administrators to administer business units within finance. The following diagram shows the hierarchy:

<img src="/Images/SecureTransport/DelegatedAdmin_Example.png" class="maxWidth" alt="Delegated administration hierarchy" />

Example delegated administration hierarchy

The following topic describes how to create a delegated administrator:

-   [Create a delegated administrator](t_st_create_delegated_administrator) - Provides how-to instructions for creating a delegated administrator.
