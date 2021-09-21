{
    "title": "Recommendations and troubleshooting",
    "linkTitle": "Recommendations and troubleshooting",
    "weight": "270"
}This topic provides information on common mistakes when setting up user rights, fixes, and how to get more information when an error occurs.

## User rights recommendations

The following best practices may help you avoid or correct user rights issues. Deviating from these recommendation may lead to unexpected user rights, or errors in the log.

-   Respect the appropriate case (upper/lower) for user names and passwords.
-   The am.type is set by default to enable Central Governance. Modifying this value effects user rights and access from Central Governance.
-   Changing the domain may affect your ability to log in on the Transfer CFT client.
-   If you modify the createprocessasuser parameter setting, you must restart Copilot for the parameter change to be taken into account.
-   The am.passport.superuser can perform any superuser activity. From Central Governance there is no check on the superuser; this user has all access regardless of the Central Governance roles and privileges.
-   When USERCTRL is set to YES and if the [USERID](../../../c_intro_userinterfaces/command_summary/parameter_intro/userid) parameter is not set, then the file transfer owner (when receiving) or file reader (when sending) is the user that started Transfer CFT.

## Troubleshooting user rights issues

### Access Transfer CFT logs in Central Governance

In the Central Governance interface, select **Products**. Select your Transfer CFT in the **Product List**, and in the right pane click **Logs**.

### Messages and logs in Transfer CFT

If there is no information available in the Central Governance logs for the Transfer CFT, next check the following:

-   Transfer CFT logs
-   Transfer CFT trace files located in the &lt;installation directory>Transfer\_CFT\\runtime\\run

### Check user definitions in Central Governance

In Central Governance roles and privileges grant or limit user permissions to perform actions, and define the user interface areas that they can access. See the Central Governance User Guide for detailed descriptions of user roles and privileges.

## Issues

**From** **Central Governance I cannot perform Transfer CFT actions that I previously could perform**

Check that the local Transfer CFT superuser is correctly defined. This is a requirement for Central Governance to correctly manage your Transfer CFT. The value displayed in Central Governance should match the value that displays for CFTUTIL listuconf value=am.passport.superuser.

**I am a user with **Central Governance** rights to create flows, but** **I cannot create a flow**

Check the superuser file rights for the local Transfer CFTs runtime environment (all runtime directory contents).

**I cannot connect to the Transfer CFT Copilot server even though I am the superuser defined in the UCONF file**

While the superuser has all privileges and is granted to all possible actions on a resource, when you log on the Transfer CFT Copilot server this triggers a credential check. Therefore, the superuser user must be defined in Central Governance.

**Transfer CFT client hangs**

The Transfer CFT client has been launched at least one time from the root/system admin userid, making the root/system admin the owner of the persistent cache (in data directory). See [am.passport.persistency.fname](../../../admin_intro/uconf/uconf_directory).

Therefore, even when the Transfer CFT client is launched with the Transfer CFT user (a user with appropriate privileges) this user cannot update the persistent cache and causes Transfer CFT to query Central Governance (PassPort AM) each time it needs to try to update the local cache.

To fix the issue, delete the persistent cache files (CFTAM and CFTAM.idx) and restart the Transfer CFT Copilot server.

## <span id="More"></span>Operating system specific information

For more information, see the following platform specific guides for the appropriate OS:

-   UNIX - [Running Transfer CFT for the first time UNIX](running_cft_for_the_first_time_unix.htm)
    -   [Defining user rights](../../../cft_intro_install/unix_install_start_here/run_first_time_ux/run_first_time_ux/user_rights_and_interface_unix)
    -   [Declaring additional users](../../../cft_intro_install/unix_install_start_here/run_first_time_ux/run_first_time_ux/declaring_additional_users)
    -   [UNIX system users](../../../cft_intro_install/unix_install_start_here/run_first_time_ux/run_first_time_ux/t_adding_system_user_unix)
    -   [License keys and authorizations](../../../cft_intro_install/unix_install_start_here/before_you_start_unix/prereqs_overview)
-   Windows - [Running Transfer CFT for the first time Windows](../../../cft_intro_install/windows_install_start_here/windows_install_start_here/running_cft_for_the_first_time_windows)
    -   [Windows user rights](../../../cft_intro_install/windows_install_start_here/windows_install_start_here/running_cft_for_the_first_time_windows/user_rights_and_interface_win)
    -   [Windows system users](../../../cft_intro_install/windows_install_start_here/windows_install_start_here/running_cft_for_the_first_time_windows/add_system_user_windows)
    -   [License keys and authorizations](../../../cft_intro_install/windows_install_start_here/before_you_start_win/prereqs_overview2)
-   z/OS - [Installation and Operation Guide](https://docs.axway.com/bundle/TransferCFT_38_InstallationGuide_mvs_en_PDF/resource/TransferCFT_InstallationGuide_mvs_en.pdf)
-   IBM i - [Installation and Operation Guide](https://docs.axway.com/bundle/TransferCFT_38_InstallationGuide_os400_en_PDF/resource/TransferCFT_InstallationGuide_os400_en.pdf)

Related topics

-   [About system users](..//transfercft/internal_a_m_start_here/user_rights_overview)
-   [User rights use case scenarios](../user_rights_security_scenarios)