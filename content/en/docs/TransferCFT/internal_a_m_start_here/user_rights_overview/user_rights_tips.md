{
    "title": "Recommendations and troubleshooting",
    "linkTitle": "Recommendations and troubleshooting",
    "weight": "260"
}This topic provides information on common mistakes when setting up user rights, fixes, and how to get more information when an error occurs.

## User rights recommendations

The following best practices may help you avoid or correct user rights issues. Deviating from these recommendation may lead to unexpected user rights, or errors in the log.

-   Respect the appropriate case (upper/lower) for user names and passwords.
-   The am.type is set by default to enable <span class="mc-variable Primary.CG or_UM variable">Central Governance</span>. Modifying this value effects user rights and access from <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span>.
-   Changing the domain may affect your ability to log in on the Transfer CFT client.
-   If you modify the createprocessasuser parameter setting, you must restart Copilot for the parameter change to be taken into account.
-   The am.passport.superuser can perform any superuser activity. From <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span> there is no check on the superuser; this user has all access regardless of the <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span> roles and privileges.
-   When USERCTRL is set to YES and if the [USERID](../../../c_intro_userinterfaces/command_summary/parameter_intro/userid) parameter is not set, then the file transfer owner (when receiving) or file reader (when sending) is the user that started <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span>.

## Troubleshooting user rights issues

### Access <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> logs in <span class="mc-variable Primary.CG or_UM variable">Central Governance</span>

In the <span class="mc-variable Primary.CG or_UM variable">Central Governance</span> interface, select **Products**. Select your <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> in the **Product List**, and in the right pane click **Logs**.

### Messages and logs in Transfer CFT

If there is no information available in the <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span> logs for the Transfer CFT, next check the following:

-   <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> logs
-   <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> trace files located in the <span class="code">&lt;installation directory>Transfer\_CFT\\runtime\\run</span>

### Check user definitions in <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span>

In <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span> roles and privileges grant or limit user permissions to perform actions, and define the user interface areas that they can access. See the <span class="mc-variable Primary.CG or_UM variable">Central Governance</span> <span class="mc-variable suite_variables.DocTypeUser variable">User Guide</span> for detailed descriptions of user roles and privileges.

## Issues

**From** **<span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span> I cannot perform <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> actions that I previously could perform**

Check that the local <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> superuser is correctly defined. This is a requirement for <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span> to correctly manage your <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span>. The value displayed in <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span> should match the value that displays for <span class="code">CFTUTIL listuconf value=am.passport.superuser</span>.

**I am a user with **<span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span>** rights to create flows, but** **I cannot create a flow**

Check the superuser file rights for the local <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span>s runtime environment (all runtime directory contents).

**I cannot connect to the Transfer CFT Copilot server even though I am the superuser defined in the UCONF file**

While the superuser has all privileges and is granted to all possible actions on a resource, when you log on the Transfer CFT Copilot server this triggers a credential check. Therefore, the superuser user must be defined in <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span>.

**Transfer CFT client hangs**

The Transfer CFT client has been launched at least one time from the root/system admin userid, making the root/system admin the owner of the persistent cache (in data directory). See [am.passport.persistency.fname](../../../admin_intro/uconf/uconf_directory).

Therefore, even when the Transfer CFT client is launched with the Transfer CFT user (a user with appropriate privileges) this user cannot update the persistent cache and causes <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> to query <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span> (PassPort AM) each time it needs to try to update the local cache.

To fix the issue, delete the persistent cache files (CFTAM and CFTAM.idx) and restart the Transfer CFT Copilot server.

<span id="More"></span>

## Operating system specific information

For more information, see the following platform specific guides for the appropriate OS:

-   UNIX - Running Transfer CFT for the first time UNIX
    -   [Defining user rights](#)
    -   [Declaring additional users](#)
    -   [UNIX system users](#)
    -   [License keys and authorizations](../../../cft_intro_install/unix_install_start_here/before_you_start_unix/prereqs_overview)
-   <span class="mc-variable Primary.for_Windows variable">Windows</span> - [Running Transfer CFT for the first time Windows](#)
    -   [Windows user rights](#)
    -   [Windows system users](#)
    -   [License keys and authorizations](../../../cft_intro_install/windows_install_start_here/before_you_start_win/prereqs_overview)
-   z/OS - [Installation and Operation Guide](https://docs.axway.com/bundle/TransferCFT_38_InstallationGuide_mvs_en_PDF/resource/TransferCFT_InstallationGuide_mvs_en.pdf)
-   IBM i - [Installation and Operation Guide](https://docs.axway.com/bundle/TransferCFT_38_InstallationGuide_os400_en_PDF/resource/TransferCFT_InstallationGuide_os400_en.pdf)

Related topics

-   [About system users](../)
-   [User rights use case scenarios](../user_rights_security_scenarios)
