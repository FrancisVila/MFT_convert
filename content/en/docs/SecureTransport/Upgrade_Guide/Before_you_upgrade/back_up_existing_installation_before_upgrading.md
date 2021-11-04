{
    "title": "Back up the existing installation before upgrading",
    "linkTitle": "Back up the existing installation before upgrading",
    "weight": "70"
}Use your corporate backup solution or follow the procedures bellow to perform a backup of <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>. Create the backup right before you upgrade. Do not install any software in the meantime between the backup and upgrade.

## Procedure for Unix-like systems

You can use the following procedure as a way to perform your backup on Unix-like systems.

1.  Stop all the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> services.  
    `<FILEDRIVEHOME>/bin/stop_all`
2.  Verify the all services are stopped by checking for running processes and `.pid` files in the `<FILEDRIVEHOME>/var/run` directory. In order to assure no processes are left running even in the rare case of missing files, check the process tree with the appropriate OS tools for running processes before proceeding.
3.  Back up the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> directory by tarring the files or using another backup method. Name the backup archive `SecureTransport.tar`.  
    Your backup must include the following files:
    -   All files in `<FILEDRIVEHOME>`
    -   For root installation on Linux: the `rc.stransportSecureTransport<XX>` init script in `/etc/rc.d/init.d `and `*stransportSecureTransport<XX>` files in all `rc<X>.d` subdirectories
    -   For non-root installation running as a Linux service: the `rc.stranport` script in `/etc/rc.d/init.d` and the `<xx>rc.stransport` files in all `rc<X>.d `subdirectories. Skip this step, if you use a non-root installation that is not a Linux service.
    -   For root installation on AIX: the `rc.stransportSecureTransport<XX>` in the `/etc` directory
    -   For non-root installation running as service of AIX: the `rc.stransport` script in the `/etc` directory
    -   The files in the `/etc` directory that end with the installation name. (You can use the `find /etc -name "*<installation name>*" -print` command to find those files.) The result of this command may be empty if you are using non-root deployment, please proceed if this is the case.
    -   The `/etc/synchronycomponents file` for root installation, or  
        `/home/<user name>/.synchronycomponents` for non-root installation.
    -   The SecureTransport `crontab` events that reside in the `/var/spool/cron` directory for Linux and in /`var/spool/cron/crontabs` for AIX. For example, for non-root installation, the events in the `/var/spool/cron/<user name>` file.
4.  Back up the <span class="mc-variable axway_variables.Company_Name variable">Axway</span> In staller directory by tarring the files or using another backup method. Name the backup archive `Axway Installer.tar`.
5.  If an external database is used, it must be backed up according to the database vendor's instructions.

## Procedure for Windows

You can use the following procedure as a way to perform your backup on Windows Server.

1.  Stop all the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> services.  
    `<FILEDRIVEHOME>\bin\stop_all`  
    You can also open CMD as an administrator and run `stop_all`.

2.  Verify the all services are stopped by checking for running processes and `.pid` files in the `<FILEDRIVEHOME>\var\run` directory. In order to assure no processes are left running even in the rare case of missing files, check the process tree with the appropriate OS tools for running processes before proceeding.

3.  Back up Windows registry entries. Run `regedit.exe`.
    1.  Select each of the following registry entries:
    2.  where `AxwaySecureTransport*` represents all the registry entries that start with `AxwaySecureTransport`.
    3.  Right click each entry, select **Export > Export Registry File**, and save the registry entry to a safe location.
    4.  When you are finished backing up the registry entries, exit `regedit`.

4.  Back up files of the existing <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> installation and installation information by copying the contents of the following directories, preserving the subdirectory structure, to a ZIP file or some other backup. Name the backup archive `SecureTransport.zip`.  


        C:\Axway\SecureTransport

5.  Back up the <span class="mc-variable axway_variables.Company_Name variable">Axway</span> home directory. Name the backup archive `Axway Installer.zip`.

6.  If an external database is used, it must be backed up according to the database vendor's instructions.
