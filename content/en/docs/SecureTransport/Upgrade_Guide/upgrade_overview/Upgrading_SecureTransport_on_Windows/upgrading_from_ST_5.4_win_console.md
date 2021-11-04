{
    "title": "Upgrade from SecureTransport 5.4 using the console",
    "linkTitle": "Upgrade from SecureTransport 5.4 using the console",
    "weight": "110"
}On Microsoft Windows using the console mode:

1.  Execute the following command to stop all services:  
    `stop_all`

2.  Verify that the Cygwin console and all Cygwin tools, including the Cygwin `cron` service, are closed.

3.  Download the file `SecureTransport_5.5_UP1-from-5.4_win-x86-64_<BuildNumber>.zip` and unzip it.  
    It contains two folders:  
    -   *UpgradeStep1* contains an update file for <span class="mc-variable axway_variables.Company_Name variable">Axway</span><span class="mc-variable suite_variables.InstallerName variable">Installer</span>
    -   *UpgradeStep2* contains an update file for <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>

4.  Navigate to the <span class="mc-variable axway_variables.Company_Name variable">Axway</span> Installer directory from your existing <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> installation and run the following command to update the installer:  


         update64.exe -i <full path to the update file in the UpgradeStep1 directory>

5.  In the `<AxwayHome>` directory, delete the *update64.exe* file and rename "update64.exe.new" to "update64.exe".

6.  Run the following command to install the <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> update:  


         update64.exe -i <full path to the update file in the UpgradeStep2 directory>

      
    Oracle users whose system privileges were granted through a role, should run the `update` command with an additional argument:

        update64.exe -javaargument "-DskipDBProcedure=true" -i <full path to the upgrade file in the UpgradeStep2 directory>

      
    When <span class="code">-javaargument "-DskipDBProcedure=true"</span> is used, the UPDATES\_DB\_LOG table is not populated. If the argument is skipped or used with a value different than `true`, the upgrade will fail.

After the installation completes, all services except for TM will be started automatically. You need to restart the TM and enable all custom TM rules manually.

The <span class="mc-variable axway_variables.Company_Name variable">Axway</span> Installer log file called install.log is located in `<AxwayHome>`.

After you upgrade <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>, complete the required [post-upgrade tasks](../../../post-upgrade-tasks).

**Related topics:**

-   <a href="../../../recover-previous-installation-win" class="MCXref xref">Recover your previous SecureTransport installation on Windows</a>
