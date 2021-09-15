{
    "title": "Upgrade to SecureTransport 5.5 Virtual Appliance",
    "linkTitle": "Upgrade to SecureTransport 5.5 Virtual Appliance",
    "weight": "120"
}You can only upgrade appliances running Appliance Platform 7.2.x with SecureTransport 5.4 latest patch. The upgrade is handled via a single package that upgrades both SecureTransport to version 5.5 and the operating system of the appliance to its latest version based on SLES 12 SP5.

## Upgrade prerequisites

-   Appliance Platform 7.2.x  
    If you are running an older Appliance version, refer to the SecureTransport 5.4 *Appliance guide* for instructions on how to migrate to 7.2.0.  
-   SecureTransport 5.4 latest patch  
     For detailed instructions, refer to the SecureTransport 5.4 *Upgrade guide* and the latest patch Readme file.
-   At least 12 GB of free disk space

## Pre-upgrade tasks

SecureTransport 5.5 Appliance is based on SLES 12 SP5, and SecureTransport 5.4 is based on SLES 12 SP4. Use your corporate solution to back up the entire filesystem along with the OS, or follow the <u>example</u> procedure bellow to perform a backup of SecureTransport.

1.  Stop all SecureTransport services.
2.  If you use an external database, back up the database according to your database vendor's instructions.
3.  Take a snapshot of the virtual machine where your SecureTransport instance is deployed.

## Upgrade procedure

1.  Go to the [Axway Technical support website](https://support.axway.com/ "Axway Software Technical Support website")
    and download the following upgrade package:  
    `SecureTransport_5.5_UP1-from-7.2_ap-x86-64_<BuildNumber>.zip`

2.  Copy the appliance upgrade package into a temporary directory, and unzip it.

3.  Enter the following command to install the update:  
    

         ./platform-upgrade.sh

When the upgrade completes, the installer will reboot the OS automatically unless you press **q** to exit the installer before rebooting the OS.

The platform upgrade log, called *platformupgrade.log*, is in the platform upgrade directory. The log file for SecureTransport upgrade is in `<AxwayHome>`.

### Upgrade the OS only

There is an option to skip the SecureTransport update, and upgrade only the operating system of the appliance. To do this, enter the following command:

-   ./platform-upgrade.sh --dontupgradeproduct

You will receive an out of compliance message. After the OS upgrade completes, the SecureTransport Edge upgrade will not start automatically. It must be performed manually. Note that when only the OS is upgraded, the `systemd` units in `/usr/lib/systemd/system` remains and should be removed in order to be able to upgrade SecureTransport to 5.5.

### Upgrade SecureTransport manually after OS update

To upgrade SecureTransport manually, follow the instructions provided in the SecureTransport 5.5 Upgrade Guide. The upgrade packages can be taken from the `st_updater` directory from the platform upgrade distributive.

## Roll back to a previous version of SecureTransport

SecureTransport 5.5 Appliance is based on SLES 12 SP5, and if you need to revert your SecureTransport instance to version 5.4, you have to go back to SLES 12 SP4. Use your recovery solution to restore your filesystem and go back to a previous version of SecureTransport, or follow the <u>example</u> procedure: 

1.  Stop all SecureTransport services.
2.  If you use an external database, follow your database vendor's instructions for restoring the database.
3.  Revert the appliance snapshot.
