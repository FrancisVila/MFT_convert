{
    "title": "Upgrade SecureTransport on a UNIX-based platform",
    "linkTitle": "Upgrade SecureTransport on a UNIX-based platform",
    "weight": "80"
}<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top"> If you are using an external database, it must be upgraded to a <a href="https://docs.axway.com/bundle/SecureTransport_55_AdministratorGuide_allOS_en_HTML5/page/Content/AdministratorsGuide/introduction/r_st_Axway_and_third-party_software_support.htm#Database">supported version</a>  prior to upgrading <span>SecureTransport</span> to version <span>5.5</span> or a new instance of the respective database should be deployed and you should migrate the existing <span>SecureTransport</span> data to the new instance. Refer to the documentation for your database  for the upgrade or migration procedure. If additional information is needed, contact your database vendor’s support.
		         </td>
      </tr>
</table>

For **ROOT** installation, run the upgrade with ROOT user. After the upgrade finishes all binaries (both SecureTransport and Axway Installer) should be owned by the ROOT user.

For **NON-ROOT** installation, run the upgrade with NON-ROOT user. Attempts to run the upgrade with root user will be successful and no error message will be returned. However after the upgrade the permissions on installation files will be wrong and your installation will be corrupt. Also, make sure that the non-root user has a created home folder with the proper permissions: 

-   useradd stuser
-   mkdir /home/stuser (default)
-   chown -R stuser: /home/stuser

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">If you are upgrading an  <span>Axway</span> Appliance, refer to the <em><span>SecureTransport</span> Appliance Guide</em>.         </td>
      </tr>
</table>

1.  Log on with the user that owns SecureTransport services.

2.  Download the upgrade pack for your operating system.  
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>SecureTransport_5.5_UP1-from-5.4_&lt;OS&gt;-&lt;processor&gt;_&lt;BuildNumber&gt;.zip         </td>
      </tr>
   </tbody>
</table>

      
    where the variables represent the following:

    -   `<OS>` is the operating system: `aix` (for IBM AIX) or `linux` (for RHEL and SUSE).
    -   `<processor>` is the type of processor running the operating system: `power` or `x86-64`.
    -   `<BuildNumber>` is the actual build number listed in the installer executable file.

      
    

    <table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Do not place the binaries in the same folder where <span>Axway</span> Installer is installed         </td>
      </tr>
</table>

3.  Copy it into a temporary directory and unzip it.  
    It contains two folders:   
    
    -   *UpgradeStep1* contains an update file for AxwayInstaller
    -   *UpgradeStep2* contains an update file for SecureTransport

4.  Navigate to the Axway Installer directory in your existing SecureTransport installation and run the following command to update the installer:  
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p><code>./update.sh -i &lt;full path to the upgrade file in the UpgradeStep1 directory</code>&gt;</p>
         </td>
      </tr>
   </tbody>
</table>

      
    

    <table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Do not run more than one instance of the <span>SecureTransport</span> installer on a system at one time. The upgrade fails when more than one instance is running.         </td>
      </tr>
</table>

5.  Run the following command to update SecureTransport:   
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><code>./update.sh -i &lt;full path to the upgrade file in the UpgradeStep2 directory</code>&gt;         </td>
      </tr>
   </tbody>
</table>

      
    
    Oracle users, whose system privileges were granted through a role, should run the `update.sh` script with an additional argument:

    <table cellspacing="0">   <col/>   <tbody>      <tr>         <td><code>./update.sh -javaargument "-DskipDBProcedure=true" -i &lt;full path to the upgrade file in the UpgradeStep2 directory</code>&gt;         </td>      </tr>   </tbody></table>

      
    
    When -javaargument "-DskipDBProcedure=true" is used, the UPDATES\_DB\_LOG table is not populated. If the argument is skipped or used with a value different than `true`, the upgrade will fail.

After the installation completes, all services except for TM will be started automatically. You need to restart the TM and enable all custom TM rules manually.

The Axway Installer log file called *install.log* is located in `<AxwayHome>`.

After you upgrade SecureTransport, complete the required [post-upgrade tasks](../../post-upgrade-tasks).
