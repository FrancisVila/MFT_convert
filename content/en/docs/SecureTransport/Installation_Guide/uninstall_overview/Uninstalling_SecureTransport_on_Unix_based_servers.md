{
    "title": "Uninstall SecureTransport on UNIX-based systems",
    "linkTitle": "Uninstall SecureTransport on UNIX-based systems",
    "weight": "90"
}This section explains how to uninstall <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> from the <span class="mc-variable axway_variables.Company_Name variable">Axway</span> appliance or any of the supported UNIX-based platforms.

The following error messages may occur and be placed in the `uninstall.log` during the uninstall of <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>:

-   `<Axway installer folder>/synInstall/scripts/utils.sh: line 743: [: -gt: unary operator expected`
-   `<Axway installer folder>/synInstall/scripts/utils.sh: line 746: [: too many arguments`

They are expected and will not cause an uninstall failure.

If you are uninstalling from the <span class="mc-variable axway_variables.Company_Name variable">Axway</span> appliance, you can use the Appliance Console Menu to proceed. Refer to the *<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Appliance Guide*.

> **Note:**
>
> In a cluster environment, stop all of the protocol servers and services on the node you want to uninstall and remove this node from the cluster before you uninstall it. For details refer to the SecureTransport Administrator's Guide.

1.  Log in to the system as the user who installed and runs <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>.

2.  Use the `<FILEDRIVEHOME>/bin/stop_all` command to stop all <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> services.

3.  Navigate to the Axway Installer directory of your installation and run the uninstaller script by typing the following on the command line:

        ./uninstall.sh

      

    > **Note:**
    >
    > If you want to run the uninstallation procedure in non-interactive mode, you should run ./uninstall.sh -a.

      
    The <span class="mc-variable axway_variables.Company_Name variable">Axway</span> Installer initializes and displays a welcome message and a prompt.

        Initialization in progress
                                        .......

        ----------------------------------------
        Welcome
        ----------------------------------------
        Welcome to the Axway Installer wizard for SecureTransport Server and SecureTransport Edge.
        This wizard will install SecureTransport Server or SecureTransport Edge on
                                            your computer.
        Next (type Next or N or n): to go to next Dialog
        Previous (type Previous or P or p): to go to previous Dialog
        Quit (type Quit or Q or q): to abort
        If you want to delete a field value, use the Space bar or the Tab key.
                                        During installation, all values or choices must be validated by pressing Enter.
        Enter (Next, Quit).
        >Next

4.  Press Enter to continue.  
    The installer prepares the uninstallation execution and displays the following prompt:

        Please wait while execution process is being prepared!

        ----------------------------------------
        Uninstallation execution
        ----------------------------------------
        All selected products are ready to uninstall. Type Next to start uninstalling.
                                    If not, type Previous to make changes.
        Enter (Next, Previous, Quit).
        >Next

5.  Press Enter to continue.  
    The installer displays the following confirmation prompt:

        Uninstall in progress...
        Confirmation
        Warning:
                                        Before proceeding, ensure that the products you want to uninstall are stopped.
                                    
        Do you want to continue?
        Confirm this operation [y/n]

6.  Type `y` and press Enter to continue.  
    The installer displays progress messages as it completes the uninstallation tasks.  
    When the installer has uninstalled <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> and the <span class="mc-variable axway_variables.Company_Name variable">Axway</span> Installer, it displays:

        Uninstallation successful

        ----------------------------------------
        Summary
        ----------------------------------------
        The information below summarizes the uninstallation status. Refer to install.log
                                        for more details.
        -------------------------------------------------------------------
        Product: SecureTransport_V5.5
                                    Uninstalled from <FILEDRIVEHOME>
        -------------------------------------------------------------------

7.  If you were running <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> as a service, as described in <a href="../../install_overview/installing_on_unix_based_platforms/running_st_as_service_unix" class="MCXref xref">Run SecureTransport as a service on UNIX-based platforms after non-root installation</a>:
    -   On AIX:
        1.  Remove `/etc/rc.stransport.`
        2.  Edit `/etc/rc.tcpip` and delete the `[ -f /etc/rc.stransport ] && sh /etc/rc.stransport start` line.
    -   On Oracle Linux and RHEL – Remove `/etc/init.d/rc.stransport.`
    -   On SLES – Remove `/etc/rc.d/rc.stransport.`
