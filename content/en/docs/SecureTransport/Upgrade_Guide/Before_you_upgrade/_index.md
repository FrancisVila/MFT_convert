{
    "title": "Pre-upgrade tasks",
    "linkTitle": "Pre-upgrade tasks",
    "weight": "50"
}-   Review the *SecureTransport Installation Guide* to ensure your system meets all the pre-installation requirements and you have all the required information.

-   Back up your existing SecureTransport installation.  
    To back up your current SecureTransport deployment, follow a backup procedure applicable for your environment and make sure the backup is created at a time when all SecureTransport services are stopped. In the rare case of an upgrade procedure failure resulting in system instability of any kind, follow the upgrade recovery procedure.
    For more information, refer to [Back up the existing installation before upgrading](back_up_existing_installation_before_upgrading)  
    
    -   Security settings must also be backed up and reapplied after upgrade. The `jdk.certpath.disabledAlgorithms` and `jdk.tls.disabledAlgorithms` parameters in the `[jre]/conf/security/java.security` file must be backed up and reapplied.
    -   Transaction Manager rules and the `<FILEDRIVEHOME>/brules/conf/brules.xml` settings file must be backed and reapplied after upgrade.
    -   Backup the `<FILEDRIVEHOME>/bin/start_*` files. The modifications made to the scripts in `<FILEDRIVEHOME>/bin/start_*` are not preserved on upgrade. To avoid manually editing the start scripts after each update, do the following: before upgrading to 5.5, in the `FILEDRIVEHOME/conf` directory, create a file called `STStartScriptsConfig` and place in it the existing start scripts configuration. The format of the file should be as described in [Advanced protocol server configuration](https://docs.axway.com/bundle/SecureTransport_55_AdministratorGuide_allOS_en_HTML5/page/Content/AdministratorsGuide/operations/advanced-server-config.htm). The content of the `STStartScriptsConfig` file is not overwritten on upgrade; the values set there are applied after each successful upgrade.

-   If your SecureTransport installation uses an external database, you need to backup and upgrade the database before upgrading SecureTransport.   
    

    <table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">You <b>MUST</b> upgrade Oracle 12.1.x to version 12.2 or later before you upgrade <span>SecureTransport</span>.         </td>
      </tr>
</table>

-   Make sure the port number for Tomcat JK2 is greater than 1024. (The default value is 8009.)  
    Check the following locations for the port numbers:
    -   In `<FILEDRIVEHOME>/tomcat/admin/conf/server.xml` find `Connector port=` and `jmvRoute`.

      
    If the Tomcat JK2 port number shown is less than or equal to 1024, change all occurrences to a number greater than 1024.

-   To ensure your previous version of SecureTransport is not running, execute the following command to stop all services:  
    `<FILEDRIVEHOME>/bin/stop_all`

-   Check for leftover running processes and `.pid` files in the `<FILEDRIVEHOME>/var/run` folder.

-   If you have made modifications to the start scripts and changed any parameter, including `min/max memory`, you should add those modifications to the `<FILEDRIVEHOME>/conf/STStartScriptsConfig` file before upgrading to SecureTransport 5.5. The content of the `STStartScriptsConfig` file is not modified on uprade, and the services will use the values set there when they automatically start after a successful upgrade.

-   During a chained upgrade, remove the `<AxwayHome>/Installer/xercesImpl-2.6.2.jar` file before launching the SecureTransport 5.5 upgrade.

-   Move all folders and folders in the `<FILEDRIVEHOME>/var/db/hist/*` directory to outside the `<FILEDRIVEHOME>` path. The high volume of files in the history folders could significantly slow down the upgrade process.

-   For instructions on how to upgrade systems with Account Retention or File Retention Add-on, refer to the Axway Support [knowledge base](https://support.axway.com/kb/180969/language/en).

**For IBM AIX upgrade**, also perform the following:

-   Log onto the IBM AIX appliance as a superuser and execute the following commands:  
    `no -o udp_recvspace=65000`
      
    `no -o udp_sendspace=65000`
-   Install the `libz.a` library

**For Windows upgrade**, also perform the following:

-   Make sure the Cygwin console and all Cygwin tools installed with your previous SecureTransport installation, including the Cygwin `cron` service, are closed. Check the **Users** tab in the Windows Task Manager to make sure no one else is using Cygwin. If necessary, close the Cygwin console and tools manually.  
    

    <table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Caution  </b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Caution  &lt;/b&gt;" valign="top"><b>If any Cygwin or Cygwin-environment related processes are running after all SecureTransport services have been stopped, they must be killed before starting the upgrade procedure. Failure to do so will result in a corrupted environment</b>.         </td>
      </tr>
</table>

-   Make sure that no folder in `<FILEDRIVEHOME>` or `<FILEDRIVEHOME>\..\cygwin` is in use or open in Windows Explorer or in a command window and that no file in those folders is in use or open in any application. Close Windows Explorer and any other application accessing the folders in question. Make sure no SecureTransport services, including Cygwin, are running.

-   Make sure you have installed the Microsoft Visual C++ 2010 SP1 Redistributable Package (x64). Download the package [here](http://www.microsoft.com/en-us/download/details.aspx?id=13523).

-   While it is not recommended to have antivirus software running on the same deployment as SecureTransport, in case you are running as such, please make sure the antivirus software is stopped and disabled during the upgrade. Leaving the antivirus software running can cause the upgrade to fail.
