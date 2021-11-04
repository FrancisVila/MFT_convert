{
    "title": "Update product",
    "linkTitle": "Update product",
    "weight": "110"
}This section explains how to apply service packs or patches using the Axway Installer.

## Prerequisites

-   Download the product updates from Axway Sphere to the machine you want to update.
-   Stop the servers that you want to update.
-   If you install a service pack or patch for the Installer, make sure all Windows services created by the Installer are stopped.
-   If you install a service pack or patch to a product, make sure that the product is stopped.
-   Before starting the update procedure, it is strongly recommended you change the location of the temporary directory by setting the TEMPORARY\_DIR environment variable.
-   On Windows platforms, the same user that performed the initial installation (or at least the same type of user) must start the update.

## Install updates in an interactive mode

1.  Use the Update function of the installer:  
    -   UNIX: Go to the installation folder you want to update and run update.sh
    -   Windows: In the Windows Start menu, select
    -   Axway Software > Axway \[installation name\] > Update
    -   Using the console: Change to the installation directory you want to update and run update.exe
2.  Select your updates. In the Updates Management page you have the following possibilities:  
    -   **Select a directory**: Select the directory containing all the updates you want to install.
    -   **Select file**: Select the update file you want to install.
    -   The file can be a JAR file or a ZIP archive of JAR files.
    -   The Installer allows the ZIP file format containing the updates to apply to more than one product in the same installation package.
    -   **Information**: Click to open the readme file.
    -   Click **Next** to continue.
3.  Review the updates you want to install.  
    To apply the update: Click **Update**. A warning message appears. Click **Yes** to continue. After the updates are installed, click **Next** to view the summary.
4.  Review the summary and click OK to exit the Installer.
5.  View log files. The installation of updates are tracked in the install.log file, located in the installation root directory.
6.  An update log is kept for each product which contains the update history of operations performed. The location of this file is found in `<installation_root>/<Secure Relay RA>/synInstall/synPatch/update.log`.

## Install updates in a non-interactive mode

To install a single update file, run the following command:

-   UNIX: `update.sh –i <full_path_to_update_file>`
-   Windows:` update.exe -i <full_path_to_update_file>`

This command applies to JAR and ZIP files.

The update progresses without user interaction. When the update process is complete, the summary is displayed and you can check the log files.

The installation of updates is tracked in the updates` install.log` file, located in the installation root directory.

An update log is kept for each product which contains the update history of operations performed. The location of this file is found in `<installation_root>/<Secure Relay RA>/synInstall/synPatch/update.log`.
