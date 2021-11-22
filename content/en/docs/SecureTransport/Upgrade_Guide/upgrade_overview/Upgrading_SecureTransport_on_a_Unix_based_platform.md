{
    "title": "Upgrade SecureTransport on a UNIX-based platform",
    "linkTitle": "Upgrade SecureTransport on a UNIX-based platform",
    "weight": "80"
}> **Note:**
>
> If you are using an external database, it must be upgraded to a supported version prior to upgrading SecureTransport to version 5.5 or a new instance of the respective database should be deployed and you should migrate the existing SecureTransport data to the new instance. Refer to the documentation for your database for the upgrade or migration procedure. If additional information is needed, contact your database vendor’s support.

For **ROOT** installation, run the upgrade with ROOT user. After the upgrade finishes all binaries (both {{< SecureTransport/componentshortname  >}} and {{< SecureTransport/companyname  >}} Installer) should be owned by the ROOT user.

For **NON-ROOT** installation, run the upgrade with NON-ROOT user. Attempts to run the upgrade with root user will be successful and no error message will be returned. However after the upgrade the permissions on installation files will be wrong and your installation will be corrupt. Also, make sure that the non-root user has a created home folder with the proper permissions: 

-   useradd stuser
-   mkdir /home/stuser (default)
-   chown -R stuser: /home/stuser

> **Note:**
>
> If you are upgrading an Axway Appliance, refer to the SecureTransport Appliance Guide.

1.  Log on with the user that owns {{< SecureTransport/componentshortname >}} services.

2.  Download the upgrade pack for your operating system.  


        SecureTransport_5.5_UP1-from-5.4_<OS>-<processor>_<BuildNumber>.zip

      
    where the variables represent the following:

    -   `<OS>` is the operating system: `aix` (for IBM AIX) or `linux` (for RHEL and SUSE).
    -   `<processor>` is the type of processor running the operating system: `power` or `x86-64`.
    -   `<BuildNumber>` is the actual build number listed in the installer executable file.

      

    > **Note:**
    >
    > Do not place the binaries in the same folder where Axway Installer is installed

3.  Copy it into a temporary directory and unzip it.  
    It contains two folders:  
    -   *UpgradeStep1* contains an update file for {{< SecureTransport/companyname >}}{{< SecureTransport/installername >}}
    -   *UpgradeStep2* contains an update file for {{< SecureTransport/componentshortname >}}

4.  Navigate to the {{< SecureTransport/companyname >}} Installer directory in your existing {{< SecureTransport/componentshortname >}} installation and run the following command to update the installer:  



        ./update.sh -i <full path to the upgrade file in the UpgradeStep1 directory>

      

    > **Note:**
    >
    > Do not run more than one instance of the SecureTransport installer on a system at one time. The upgrade fails when more than one instance is running.

5.  Run the following command to update {{< SecureTransport/componentshortname >}}:  


        ./update.sh -i <full path to the upgrade file in the UpgradeStep2 directory>

      
    Oracle users, whose system privileges were granted through a role, should run the `update.sh` script with an additional argument:

        ./update.sh -javaargument "-DskipDBProcedure=true" -i <full path to the upgrade file in the UpgradeStep2 directory>

      
    When `-javaargument "-DskipDBProcedure=true"` is used, the UPDATES\_DB\_LOG table is not populated. If the argument is skipped or used with a value different than `true`, the upgrade will fail.

After the installation completes, all services except for TM will be started automatically. You need to restart the TM and enable all custom TM rules manually.

The {{< SecureTransport/companyname  >}} Installer log file called *install.log* is located in `<AxwayHome>`.

After you upgrade {{< SecureTransport/componentshortname  >}}, complete the required [post-upgrade tasks](../../post-upgrade-tasks).
