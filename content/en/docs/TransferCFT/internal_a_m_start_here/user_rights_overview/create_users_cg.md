{
    "title": "1. Create new users",
    "linkTitle": "1. Create new users ",
    "weight": "220"
}Begin by creating a new user in Central Governance. You can refer to the Central Governance User Guide for detailed descriptions of user roles and privileges.

To create new systems users:

1.  In Central Governance, create your users and assign the appropriate roles and privileges as described in the Central Governance User Guide.  
    For example, create the system users Flow Manager, Partner Manager, and Monitoring Assistant.
2.  Define the user rights for actions on files (USERCTRL) for these same new users for the local system where Transfer CFT is installed.

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">Superusers have all rights on <span>Transfer CFT</span> (you can check the uconf <a href="../../admin_intro/uconf/uconf_directory">am.passport.superuser</a> parameter, providing a list of superusers). It is important to remember that in UNIX/Windows, the user that installs <span>Transfer CFT</span> is the superuser. This means that even if you restrict a user's roles in <span>Central Governance</span>, if that user is the superuser it can still perform all actions on files. Additionally, if you define a system user during installation, that user is automatically added to the <code>am.superuser</code> list of users.         </td>
      </tr>
   </tbody>
</table>

For users that have not yet implemented Central Governance, either create user permissions in Passport, or continue on to Step 2.

## Parameter mapping for Central Governance

The following parameters are now managed in Central Governance. This table maps the existing Transfer CFT defaults and values.

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>CG field</th>
         <th>CG values</th>
         <th>CFTUTIL parameter</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td>User for file
access         </td>
         <td><u>Transfer CFT system
account</u> | USERID
variable         </td>
         <td>CFTPARM - USERCTRL = <u>NO</u> |
YES         </td>
         <td>Specifies the account that is used to
read/write transferred files.         </td>
      </tr>
      <tr class="even">
         <td>User for
script
execution         </td>
         <td><u>Transfer CFT system
account</u> | USERID
variable         </td>
         <td>UCONF - cft.server.exec_as_
user =  <u>NO</u> | YES         </td>
         <td>Specifies the account that is used to
execute scripts.
This parameter is not supported on
Transfer CFTs running on z/OS and IBM i
systems.         </td>
      </tr>
      <tr class="odd">
         <td>Check permission
for transfer
execution         </td>
         <td>YES | <u>NO</u>         </td>
         <td>am.passport.userctrl.check_
permissions_on_transfer_
execution         </td>
         <td>Checks whether the user has
permissions to execute transfers.         </td>
      </tr>
      <tr class="even">
         <td>Create process as user         </td>
         <td>YES | <u>NO</u>         </td>
         <td>copilot.misc.createprocessasuser         </td>
         <td>Specifies whether Transfer CFT Copilot user must have system rights.         </td>
      </tr>
   </tbody>
</table>

Related topics

-   [Recommendations and troubleshooting](user_rights_tips)
