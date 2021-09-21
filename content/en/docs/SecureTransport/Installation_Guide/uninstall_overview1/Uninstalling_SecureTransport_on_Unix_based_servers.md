{
    "title": "Uninstall SecureTransport on UNIX-based systems",
    "linkTitle": "Uninstall SecureTransport on UNIX-based systems",
    "weight": "90"
}This section explains how to uninstall SecureTransport from the Axway appliance or any of the supported UNIX-based platforms.

The following error messages may occur and be placed in the `uninstall.log` during the uninstall of SecureTransport:

-   `<Axway installer folder>/synInstall/scripts/utils.sh: line 743: [: -gt: unary operator expected`
-   `<Axway installer folder>/synInstall/scripts/utils.sh: line 746: [: too many arguments`

They are expected and will not cause an uninstall failure.

If you are uninstalling from the Axway appliance, you can use the Appliance Console Menu to proceed. Refer to the *SecureTransport Appliance Guide*.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">In a cluster environment, stop all of the protocol servers and services on the node you want to uninstall and remove this node from the cluster before you uninstall it. For details refer to the <span data-cshid="admin" data-version="5.3.5"><em><span>SecureTransport</span> Administrator's Guide</em></span>.         </td>
      </tr>
</table>

1.  Log in to the system as the user who installed and runs SecureTransport.

2.  Use the `<FILEDRIVEHOME>/bin/stop_all` command to stop all SecureTransport services.

3.  Navigate to the Axway Installer directory of your installation and run the uninstaller script by typing the following on the command line:

    <table cellspacing="0">   <col/>   <tbody>      <tr>         <td>./uninstall.sh         </td>      </tr>   </tbody></table>

      
    

    <table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">If you want to run the uninstallation procedure in non-interactive mode, you should run <code>./uninstall.sh -a</code>.         </td>
      </tr>
</table>

      
    The Axway Installer initializes and displays a welcome message and a prompt.

    <table cellspacing="0">   <col/>   <tbody>      <tr>         <td><code>Initialization in progress
								.......</code><br><br><code>----------------------------------------</code><br/><code>Welcome</code><br/><code>----------------------------------------</code><br/><code>Welcome to the Axway Installer wizard for SecureTransport Server and SecureTransport Edge.</code><br/><code>This wizard will install SecureTransport Server or SecureTransport Edge on
									your computer.<br/>Next (type Next or N or n): to go to next Dialog<br/>Previous (type Previous or P or p): to go to previous Dialog<br/>Quit (type Quit or Q or q): to abort<br/>If you want to delete a field value, use the Space bar or the Tab key.
								During installation, all values or choices must be validated by pressing Enter.<br/>Enter (Next, Quit).<br/>&gt;Next</code><br/></br></br>         </td>      </tr>   </tbody></table>

4.  Press Enter to continue.  
    The installer prepares the uninstallation execution and displays the following prompt:

    <table cellspacing="0">   <col/>   <tbody>      <tr>         <td>Please wait while execution process is being prepared!<br><br/>----------------------------------------<br/>Uninstallation execution<br/>----------------------------------------<br/>All selected products are ready to uninstall. Type Next to start uninstalling.
							If not, type Previous to make changes.<br/>Enter (Next, Previous, Quit).<br/>&gt;Next</br>         </td>      </tr>   </tbody></table>

5.  Press Enter to continue.  
    The installer displays the following confirmation prompt:

    <table cellspacing="0">   <col/>   <tbody>      <tr>         <td>Uninstall in progress...<br>Confirmation<br/>Warning:
								Before proceeding, ensure that the products you want to uninstall are stopped.
							<br/>Do you want to continue?<br/>Confirm this operation [y/n]</br>         </td>      </tr>   </tbody></table>

6.  Type `y` and press Enter to continue.  
    The installer displays progress messages as it completes the uninstallation tasks.  
    When the installer has uninstalled SecureTransport and the Axway Installer, it displays:

    <table cellspacing="0">   <col/>   <tbody>      <tr>         <td>Uninstallation successful<br><br>----------------------------------------<br/>Summary<br/>----------------------------------------<br/>The information below summarizes the uninstallation status. Refer to install.log
								for more details.<br/><br/>-------------------------------------------------------------------<br/>Product: SecureTransport_V5.5
							Uninstalled from &lt;FILEDRIVEHOME&gt;<br/>-------------------------------------------------------------------</br></br>         </td>      </tr>   </tbody></table>

7.  If you were running SecureTransport as a service, as described in [Run SecureTransport as a service on UNIX-based platforms after non-root installation](../../install_overview2/installing_on_unix_based_platforms/running_st_as_service_unix):
    -   On AIX:
        1.  Remove `/etc/rc.stransport.`
        2.  Edit `/etc/rc.tcpip` and delete the `[ -f /etc/rc.stransport ] && sh /etc/rc.stransport start` line.
    -   On Oracle Linux and RHEL – Remove `/etc/init.d/rc.stransport.`
    -   On SLES – Remove `/etc/rc.d/rc.stransport.`
