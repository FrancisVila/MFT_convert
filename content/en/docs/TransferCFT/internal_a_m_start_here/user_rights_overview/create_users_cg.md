{
    "title": "1. Create new users",
    "linkTitle": "1. Create new users ",
    "weight": "210"
}Begin by creating a new user in {{< TransferCFT/centralgovernancename  >}}. You can refer to the {{< TransferCFT/doctypeuser  >}} for detailed descriptions of user roles and privileges.

To create new systems users:

1.  In , create your users and assign the appropriate roles and privileges as described in the {{< TransferCFT/centralgovernancename >}} {{< TransferCFT/doctypeuser >}}.  
    For example, create the system users Flow Manager, Partner Manager, and Monitoring Assistant.
2.  Define the user rights for actions on files (USERCTRL) for these same new users for the local system where Transfer CFT is installed.

> **Note:**
>
> Superusers have all rights on Transfer CFT (you can check the uconf am.passport.superuser parameter, providing a list of superusers). It is important to remember that in UNIX/Windows, the user that installs Transfer CFT is the superuser. This means that even if you restrict a user's roles in Central Governance, if that user is the superuser it can still perform all actions on files. Additionally, if you define a system user during installation, that user is automatically added to the am.superuser list of users.

For users that have not yet implemented {{< TransferCFT/centralgovernancename  >}}, either create user permissions in Passport, or continue on to Step 2.

## Parameter mapping for {{< TransferCFT/centralgovernancename  >}}

The following parameters are now managed in {{< TransferCFT/centralgovernancename  >}}. This table maps the existing {{< TransferCFT/componentlongname  >}} defaults and values.

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">CG field         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">CG values         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">CFTUTIL parameter         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
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
      <tr>
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
      <tr>
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
      <tr>
         <td>Create process as user         </td>
         <td>YES | <u>NO</u>         </td>
         <td>copilot.misc.createprocessasuser         </td>
         <td>Specifies whether Transfer CFT Copilot user must have system rights.         </td>
      </tr>
   </tbody>
</table>

Related topics

-   [Recommendations and troubleshooting](../user_rights_tips)
