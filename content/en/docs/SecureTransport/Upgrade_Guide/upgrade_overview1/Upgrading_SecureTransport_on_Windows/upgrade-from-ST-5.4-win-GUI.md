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
    
    -   *UpgradeStep1* contains an update file for AxwayInstaller
    -   *UpgradeStep2* contains an update file for SecureTransport
4.  Select **Start > All Programs > Axway Software > Axway *&lt;installation\_name>* > Update**.  
    The Axway Installer starts in update mode and displays the *Welcome* page.
5.  Click **Next**.
6.  On the *Updates management* page, click **Select file**.
7.  Browse to select the update file in the *UpgradeStep1* folder and click **Open**.
8.  Click **Next**, then click **Update** to begin the update process.  
    The installer displays a confirmation window.
9.  If you have stopped all SecureTransport processes, click **Yes**.
10. When the update is completed, click **Finish**.
11. Go to the Axway Installer directory, and delete the *update64.exe* file.
12. Rename "update64.exe.new" file to "update64.exe".
13. Run update64.exe.   
    The Axway Installer wizard opens again.
14. Click **Next**.
15. Browse to select the update file in the *UpgradeStep2* folder and click **Open**.
16. Click **Next**, then click **Update**, and again **Next**.  
    The Axway Installer starts updating SecureTransport to version 5.5.
17. When the update is completed, click **Finish** to exit the installer.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">When the installer completes the installation, it will start all services except for TM. TM will need to be manually restarted. Also, all custom TM rules are disabled and need to be manually enabled.         </td>
      </tr>
</table>

The log file will be the `<AxwayHome>/install.log` of the Axway Installer.

After you upgrade SecureTransport, complete the required [post-upgrade tasks](../../../post-upgrade-tasks).

**Related topics:**

-   [Upgrade from SecureTransport 5.4 using the console](../upgrading_from_st_5.4_win_console)
-   [Recover your previous SecureTransport installation on Windows](../../../recover-previous-installation-win)
