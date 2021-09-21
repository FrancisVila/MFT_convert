{
    "title": "Define internal access management",
    "linkTitle": "Define internal access management",
    "weight": "250"
}This section describes the OS specific settings required to enable internal access management. As a prerequisite, you should read and be familiar with the [Internal access management](https://docs.axway.com/bundle/TransferCFT_38_UsersGuide_allOS_en_HTML5/page/Content/internal_access_mgt/internal_a_m_start_here.htm) information in the *Transfer CFT User Guide*.

## Using system as the internal access management

With system access management, you define the mapping between predefined roles and groups in UCONF and the user groups assignment in the GRPPRF field.

For system access management, you must create different Groups to associate with your users, creating a Groups in the same way as you do a user.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CRTUSRPRF USRPRF(ADMIN)     TEXT('CFT admin group') SPCAUT(*JOBCTL *SPLCTL *ALLOBJ)</p>
            <p>CRTUSRPRF USRPRF(APPLI)     TEXT('CFT application group') SPCAUT(*NONE)</p>
            <p>CRTUSRPRF USRPRF(DESIGNER)  TEXT('CFT designer group') SPCAUT(*NONE)</p>
            <p>CRTUSRPRF USRPRF(HELPDESK)  TEXT('CFT helpdesk group') SPCAUT(*NONE)</p>
            <p>CRTUSRPRF USRPRF(PARTMANAG) TEXT('CFT partnermanager group') SPCAUT(*NONE)</p>
         </td>
      </tr>
   </tbody>
</table>

You can then associate your users with the various groups you created.

Example

To grant CFTUSER1 access to transfers and the configuration, associate this user with the previously created HELPDESK group using the command:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CHGUSRPRF USRPRF(CFTUSER1) GRPPRF(HELPDESK)</p>
         </td>
      </tr>
   </tbody>
</table>

You can now activate the access management in Transfer CFT according to your different groups:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>UCONFSET id=am.type                          ,value = internal</p>
            <p>UCONFSET id=am.internal.group_database       ,value = system</p>
            <p>UCONFSET id=am.internal.role.admin           ,value = ADMIN</p>
            <p>UCONFSET id=am.internal.role.application     ,value = APPLI</p>
            <p>UCONFSET id=am.internal.role.designer        ,value = DESIGNER</p>
            <p>UCONFSET id=am.internal.role.helpdesk        ,value = HELPDESK</p>
            <p>UCONFSET id=am.internal.role.partnermanager  ,value = PARTMANAG</p>
         </td>
      </tr>
   </tbody>
</table>
