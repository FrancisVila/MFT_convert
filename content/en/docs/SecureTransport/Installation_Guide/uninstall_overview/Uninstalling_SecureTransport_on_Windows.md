{
    "title": "Uninstall SecureTransport on Windows",
    "linkTitle": "Uninstall SecureTransport on Windows",
    "weight": "100"
}This section explains how to uninstall <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> from Windows.

> **Note:**
>
> When uninstalling SecureTransport in Microsoft Windows environments, Axway registry entries may be left behind. It is safe to manually remove the Axway registry entries left behind.

If registry entries are left behind, run `regedit.exe` to start the Microsoft Windows registry and delete the following registry entries:


    HKEY_LOCAL_MACHINE\SOFTWARE\Axway Software
    HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\
        Uninstall\Axway_Installer_4.10.6 SecureTransport01

> **Note:**
>
> In a cluster environment, stop all of the protocol servers and services on the node you want to uninstall and remove this node from the cluster before you uninstall it. For details refer to the SecureTransport Administrator's Guide.

1.  Prior to uninstallation, stop all <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> processes and make sure that no <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> files or directories are in use and that the Cygwin console and all Cygwin tools and services installed with your previous <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> installation are closed. If necessary, close the Cygwin console and tools manually.
2.  Select **Start > Programs > Axway Software > Uninstall**.  
    The installer loads and displays the *Welcome* page.
3.  Click **Next** to proceed. The installer displays the *Ready to uninstall* page.
4.  Click **Uninstall** to start the uninstallation. The installer displays a confirmation dialog.
5.  If you have stopped all <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> and related services as described in step 1, click **Yes**. The installer displays the *Uninstall in progress* page which shows the progress of the uninstallation.
6.  When uninstallation is complete, the installer displays the *Uninstall completed* page.
7.  Click **Next**. The installer displays the *Summary* page.
8.  Click **Finish** to close the installer.

> **Note:**
>
> You can also use the Add/Remove Programs option in the Control Panel to uninstall SecureTransport Server or Edge or navigate to the Axway Installer installation folder and start uninstall64.exe.
