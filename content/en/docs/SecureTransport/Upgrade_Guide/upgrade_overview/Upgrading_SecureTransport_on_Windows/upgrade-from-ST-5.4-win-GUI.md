{
    "title": "Upgrade from SecureTransport 5.4 using the GUI",
    "linkTitle": "Upgrade from SecureTransport 5.4 using the GUI",
    "weight": "120"
}For Microsoft Windows using GUI mode:

1.  Execute the following command to stop all services:  
    `stop_all`
2.  Verify that the Cygwin console and all Cygwin tools, including the Cygwin `cron` service, are closed.
3.  Download the following upgrade package and unzip it.  
    `SecureTransport_5.5_UP1-from-5.4_win-x86-64_<BuildNumber>.zip`  
    It contains two folders:  
    -   *UpgradeStep1* contains an update file for <span class="mc-variable axway_variables.Company_Name variable">Axway</span><span class="mc-variable suite_variables.InstallerName variable">Installer</span>
    -   *UpgradeStep2* contains an update file for <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>
4.  Select **Start > All Programs > Axway Software > Axway *&lt;installation\_name>* > Update**.  
    The <span class="mc-variable axway_variables.Company_Name variable">Axway</span> Installer starts in update mode and displays the *Welcome* page.
5.  Click **Next**.
6.  On the *Updates management* page, click **Select file**.
7.  Browse to select the update file in the *UpgradeStep1* folder and click **Open**.
8.  Click **Next**, then click **Update** to begin the update process.  
    The installer displays a confirmation window.
9.  If you have stopped all <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> processes, click **Yes**.
10. When the update is completed, click **Finish**.
11. Go to the <span class="mc-variable axway_variables.Company_Name variable">Axway</span> Installer directory, and delete the *update64.exe* file.
12. Rename "update64.exe.new" file to "update64.exe".
13. Run update64.exe.  
    The <span class="mc-variable axway_variables.Company_Name variable">Axway</span> Installer wizard opens again.
14. Click **Next**.
15. Browse to select the update file in the *UpgradeStep2* folder and click **Open**.
16. Click **Next**, then click **Update**, and again **Next**.  
    The <span class="mc-variable axway_variables.Company_Name variable">Axway</span> Installer starts updating <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> to version <span class="mc-variable axway_variables.Release_Number variable">5.5</span>.
17. When the update is completed, click **Finish** to exit the installer.

> **Note:**
>
> When the installer completes the installation, it will start all services except for TM. TM will need to be manually restarted. Also, all custom TM rules are disabled and need to be manually enabled.

The log file will be the `<AxwayHome>/install.log` of the <span class="mc-variable axway_variables.Company_Name variable">Axway</span> Installer.

After you upgrade <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>, complete the required [post-upgrade tasks](../../../post-upgrade-tasks).

**Related topics:**

-   <a href="../upgrading_from_st_5.4_win_console" class="MCXref xref">Upgrade from SecureTransport 5.4 using the console</a>
-   <a href="../../../recover-previous-installation-win" class="MCXref xref">Recover your previous SecureTransport installation on Windows</a>
