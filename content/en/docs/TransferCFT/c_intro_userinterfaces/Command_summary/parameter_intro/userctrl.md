{
    "title": "userctrl",
    "linkTitle": "userctrl",
    "weight": "3700"
}### <span id="userctrl"></span>userctrl

#### CFTPARM

\[USERCTRL = { NO
| YES }\]

Use this field to define the file access control. You can use the UserCtrl parameter to define access to files under another credential (UserId parameter) other than the user who started Transfer CFT.

-   YES:
    Transfer CFT checks the user access rights on the file to be transferred.
-   NO: No check is performed.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Caution  </b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Caution  &lt;/b&gt;" valign="top"><i>Windows only</i> - You cannot use a UNC or mapped drive (as opposed to files on a local disk) when USERCTRL=YES. Note though that even when USERCTRL=NO,  you cannot access files on a local or remote disk under another account.          </td>
      </tr>
</table>

-   For details in UNIX, please see [Enable the file user rights (USERCTRL)](../../../../cft_intro_install/unix_install_start_here/run_first_time_ux/run_first_time_ux/t_adding_system_user_unix)
-   For details in Windows, please see [Enable the file user rights (USERCTRL)](../../../../cft_intro_install/windows_install_start_here/windows_install_start_here/running_cft_for_the_first_time_windows/add_system_user_windows)

 

[Return to Command index](../../)
