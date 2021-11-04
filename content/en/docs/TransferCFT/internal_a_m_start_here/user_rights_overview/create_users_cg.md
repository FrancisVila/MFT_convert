{
    "title": "1. Create new users",
    "linkTitle": "1. Create new users ",
    "weight": "210"
}Begin by creating a new user in <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span>. You can refer to the <span class="mc-variable Primary.CG or_UM variable" style="mc-tag-and-class: i;">Central Governance</span> <span class="mc-variable suite_variables.DocTypeUser variable" style="mc-tag-and-class: i;">User Guide</span> for detailed descriptions of user roles and privileges.

To create new systems users:

1.  In <span class="mc-variable Primary.CG or_UM variable">Central Governance</span>, create your users and assign the appropriate roles and privileges as described in the <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span> <span class="mc-variable suite_variables.DocTypeUser variable">User Guide</span>.  
    For example, create the system users Flow Manager, Partner Manager, and Monitoring Assistant.
2.  Define the user rights for actions on files (USERCTRL) for these same new users for the local system where Transfer CFT is installed.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>Superusers have all rights on <span class="mc-variable header_footer_variables.hf_long_product_name variable">Transfer CFT</span> (you can check the uconf <a href="../../../admin_intro/uconf/uconf_directory">am.passport.superuser</a> parameter, providing a list of superusers). It is important to remember that in UNIX/Windows, the user that installs <span class="mc-variable header_footer_variables.hf_long_product_name variable">Transfer CFT</span> is the superuser. This means that even if you restrict a user's roles in <span class="mc-variable Primary.CG or_UM variable">Central Governance</span>, if that user is the superuser it can still perform all actions on files. Additionally, if you define a system user during installation, that user is automatically added to the <code>am.superuser</code> list of users.         </td>
      </tr>
   </tbody>
</table>

For users that have not yet implemented <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span>, either create user permissions in Passport, or continue on to Step 2.

## Parameter mapping for <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span>

The following parameters are now managed in <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span>. This table maps the existing <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> defaults and values.

<table>
   <th>
      <tr>
<th>CG field         </th>
<th>CG values         </th>
<th>CFTUTIL parameter         </th>
<th>Description         </th>
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
