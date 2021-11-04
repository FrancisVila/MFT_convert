{
    "title": "Recover your previous SecureTransport installation on Windows ",
    "linkTitle": "Recover your previous SecureTransport installation",
    "weight": "90"
}> **Note:**
>
> After a successful upgrade to SecureTransport 5.5, there is no revert / downgrade path: the only way to roll back to a previous SecureTransport version deployment is to restore it from backup.

If the upgrade fails, you can recover your backed-up <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> 5.4 installation. Make sure you uninstall <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> <span class="mc-variable axway_variables.Component_Version variable">5.5</span> before you attempt to recover.

Complete the following steps to restore your <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> installation from a backup on Windows Server.

1.  For a <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server using an external Oracle database, restore the database using standard Oracle procedures. For a <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server using an external Microsoft SQL Server database, restore the database using standard Microsoft procedures.

2.  Expand the `SecureTransport.zip` file created during the backup procedure and extract the files into the original installation folder of your previous <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> installation.

3.  Expand the `Axway Installer.zip` file created during the backup procedure and extract the files into the original installer folder of your previous installation.

4.  Run `regedit.exe` to start the Windows registry, and delete the following registry entries:

        HKEY_LOCAL_MACHINE\SOFTWARE\Axway Software
        HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\
            Uninstall\Axway_Installer_4.10.7 SecureTransport1

5.  Restore the registry entries that you backed up. To import a registry entry into the Windows registry, double-click the name of the respective `.reg` files you saved when you backed up your installation.

6.  Make sure the file `cygwin1.dll` is included in your PATH environment variable. For example:

        C:\Axway\SecureTransport\cygwin\bin

7.  Make sure the folder `STServer\bin` is included in your PATH environment variable. For example:

        C:\Axway\SecureTransport\STServer\bin

8.  Install the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> services:
    -   To install the services on a <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server installation, navigate to the folder `STServer\bin`, located in the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> installation folder, and double-click the following files:

            install_ftpd_service.com
            install_httpd_service.com
            install_sshd_service.com
            install_tm_service.com
            install_admin_service.com
            install_as2d_service.com
            install_pesitd_service.com

    -   To install <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> services on a <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge installation, navigate to the folder `STServer\bin`, located in the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> installation folder, and double-click the following files:

            install_ftpd_service.com
            install_httpd_service.com
            install_sshd_service.com
            install_admin_service.com
            install_as2d_service.com

9.  Install Cygwin `cron`:
    1.  Navigate to the `cygwin\bin` folder in the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> installation folder and double-click the `cygwin.bat` file to start the Cygwin shell.

    2.  In the Cygwin shell, execute the following command:

            cygrunsrv -I cygwin_cron -d \"Cygwin cron\" -p /usr/sbin/cron \
                -a -D -f \"Cygwin Cron\"

10. Reboot your system and start all <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> services. For more information, refer to the <span class="redirect_st_ag" cshid="admin" data-version="5.3.5">*<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Administrator's Guide*</span>.