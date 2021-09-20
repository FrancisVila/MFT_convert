{
    "title": "Recover your previous SecureTransport installation",
    "linkTitle": "Recover your previous SecureTransport installation",
    "weight": "90"
}<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">After a successful upgrade to <span>SecureTransport</span> <span>5.5</span>, there is no revert / downgrade path: the only way to roll back to a previous <span>SecureTransport</span> version deployment is to restore it from backup.          </td>
      </tr>
</table>

If the upgrade fails, you can recover your backed-up SecureTransport 5.4 installation. Make sure you uninstall SecureTransport 5.5 before you attempt to recover.

Complete the following steps to restore your SecureTransport installation from a backup on Windows Server.

1.  For a SecureTransport Server using an external Oracle database, restore the database using standard Oracle procedures. For a SecureTransport Server using an external Microsoft SQL Server database, restore the database using standard Microsoft procedures.

2.  Expand the `SecureTransport.zip` file created during the backup procedure and extract the files into the original installation folder of your previous SecureTransport installation.

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

8.  Install the SecureTransport services:
    -   To install the services on a SecureTransport Server installation, navigate to the folder `STServer\bin`, located in the SecureTransport installation folder, and double-click the following files:

            install_ftpd_service.com
            install_httpd_service.com
            install_sshd_service.com
            install_tm_service.com
            install_admin_service.com
            install_as2d_service.com
            install_pesitd_service.com

    -   To install SecureTransport services on a SecureTransport Edge installation, navigate to the folder `STServer\bin`, located in the SecureTransport installation folder, and double-click the following files:

            install_ftpd_service.com
            install_httpd_service.com
            install_sshd_service.com
            install_admin_service.com
            install_as2d_service.com

9.  Install Cygwin `cron`:
    1.  Navigate to the `cygwin\bin` folder in the SecureTransport installation folder and double-click the `cygwin.bat` file to start the Cygwin shell.

    2.  In the Cygwin shell, execute the following command:

            cygrunsrv -I cygwin_cron -d \"Cygwin cron\" -p /usr/sbin/cron \
                -a -D -f \"Cygwin Cron\"

10. Reboot your system and start all SecureTransport services. For more information, refer to the <span cshid="admin" data-version="5.3.5">*SecureTransport Administrator's Guide*</span>.
