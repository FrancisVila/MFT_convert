{
    "title": "_HOME_",
    "linkTitle": "_HOME_",
    "weight": "1480"
}### &HOME

A keyword to use with the [WORKINGDIR](workingdir) parameter.

You can use the &HOME keyword in CFTSEND and CFTRECV command file names, script names, and directory parameters. This keyword functions differently depending on the system user setting:

-   When system users are enabled, &HOME represents the home folder ($HOME on UNIX or %USERPROFILE% on Windows) of the user that requested the transfer.
-   When system users are disabled, &HOME represents the home folder of the user that started Transfer CFT.

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">For more information on system users, refer to the platform specific guide, <a href="../../../cft_intro_install/unix_install_start_here/run_first_time_ux/run_first_time_ux/t_adding_system_user_unix"><u>UNIX</u>:Using system users</a> or <a href="../../../cft_intro_install/windows_install_start_here/windows_install_start_here/running_cft_for_the_first_time_windows/add_system_user_windows"><u>Windows</u>: Using system users</a>.         </td>
      </tr>
   </tbody>
</table>
