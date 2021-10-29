{
    "title": "Using system users - UNIX",
    "linkTitle": "Using system users",
    "weight": "250"
}This section describes two optional UNIX-specific tasks that you can perform to enable system user authentication and file system rights, and which are not mutually exclusive.

-   [Enable the file user rights (USERCTRL)](#Manually)
    -   [Transfer CFT starts the CFTSU process](#Automati2)
    -   [User starts the CFTSUD process](#Manually2)
-   [Using system users - UNIX](#Enable)

## <span id="Manually"></span>Enable the file user rights (USERCTRL)

To enable file system rights in Unix, configure one of the following two scenarios to execute using the either the CFTSU or the CFTSUD process. See also, [USERCTRL](../CFTUTIL/Parameter_index/userctrl.htm). Reminder, on UNIX due to case sensitivity CFTSU is not the same as the cftsu file, which is dedicated to the Transfer CFT Copilot server.

### <span id="Automati2"></span>Transfer CFT starts the CFTSU process 

Perform the following steps so that when Transfer CFT starts the CFTSU process is automatically started.

1.  Set the CFTPARM USERCTRL option to YES to enable.
2.  Check that the UCONF cft.unix.cftsu.isservice parameter is set to NO (default).
3.  Log on as root.
4.  Go to the Transfer CFT runtime and execute the profile.
5.  Copy the CFTSU executable to a directory that is outside of the $CFTDIRINSTALL directory, for example /opt/cft/:  
    cp $CFTDIRINSTALL/bin/CFTSU /opt/cft/CFTSU  
    Ensure that the destination directory is outside of the $`CFTDIRINSTALL `directory to allow automatic updating when you apply a Transfer CFT service pack or update.
6.  Set the UCONF cft.unix.cftsu.fname parameter to the directory used above, for example /opt/cft/CFTSU.  
    <table data-cellspacing="0">
       <tbody>
          <tr class="odd">
             <td>CFTUTIL uconfset id=cft.unix.cftsu.fname,value=/opt/cft/CFTSU         </td>
          </tr>
       </tbody>
    </table>
7.  Execute the commands:  
    chown root:root /opt/cft/CFTSU  
    chmod u+s /opt/cft/CFTSU
8.  Copy the cftsu\_setup executable to the $CFTDIRRUNTIME/bin directory:  
    cp $CFTDIRINSTALL/bin/cftsu\_setup $CFTDIRRUNTIME/bin/cftsu\_setup
9.  Execute the commands:  
    chown root:root $CFTDIRRUNTIME/bin/cftsu\_setup  
    chmod u+s $CFTDIRRUNTIME/bin/cftsu\_setup  
    The` cftsu_setup` is a necessary step as it is required if at a later date you want to update or upgrade.

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">After starting Transfer CFT, with a user other than root, the message <span>CFTI34I PID=13653 /opt/cft/CFTSU Task started successfully (MQID=None) </span>confirms that the CFTSU steps above were successful.         </td>
      </tr>
   </tbody>
</table>

### CFTSU procedures for updates and upgrades

You do not need to repeat the Automatically start CFTSU process steps above when applying a Transfer CFT update after having performed this step at least once previously.

However, if you execute a version upgrade:

-   If you were using the CFTSU in the $CFTDIRINSTALL/bin directory, change to use the owner who installed Transfer CFT.
-   Move the CFTSU to a directory outside of the $CFTDIRINSTALL/bin directory.
-   Apply the upgrade.
-   Execute the Start CFTSU process steps above.

### <span id="Manually2"></span>User starts the CFTSUD process

In this scenario, the root user must manually start the CFTSUD process as a service before starting Transfer CFT.

1.  Set the CFTPARM USERCTRL option to YES (enabled).
2.  Before starting Transfer CFT, set the uconf parameter cft.unix.cftsu.isservice to yes.
3.  Set the uconf parameter to cft.unix.cftsu.afunix=$(cft.runtime\_dir)/run/SCFTSU.

#### CFTSUD rights

Give special rights to the CFTSUD executable as follows:

1.  Log on as root.

2.  Execute following command:

    chown root:root $CFTDIRINSTALL/bin/CFTSUD

#### Start CFTSUD

The root user now starts the CFTSUD process and sets the AF\_UNIX file owner, which you defined in `cft.unix.cftsu.afunix`. This results in Transfer CFT connecting via the CFTSUD process when started.

1.  Log on as root.

2.  Go to $CFTDIRRUNTIME directory.

3.  Execute the Transfer CFT profile:

    . ./profile

4.  Start CFTSUD:

    CFTSUD

5.  Set the AF\_UNIX file owner as the user that starts Transfer CFT:

    chown &lt;cftuser>:&lt;cftuser> &lt;afunix\_file>

## <span id="Enable2"></span>How to use system user authentication for the user interfaces

There are two ways to enable the system user authentication:

-   For the current web-based Transfer CFT UI: set `copilot.restapi.authentication_method=system`
-   For the deprecated Transfer CFT UI (Copilot): set `copilot.misc.createprocessasuser=yes`

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">Note that the <code>copilot.misc.createprocessasuser</code> parameter is set to <code>NO </code>for Unix systems by default.         </td>
      </tr>
   </tbody>
</table>

Proceed as follows:

1.  Log on as root.
2.  Execute the profile.
3.  Copy the `cftsu` executable to the following directory, where you must first create the `cft `sub-folder:  
    cp $CFTDIRINSTALL/bin/cftsu /opt/cft/cftsu  
    The destination directory, for example /opt/cft/, must be outside of the $CFTDIRINSTALL directory to allow automatic updating when apply a SP or product update.
4.  Execute the commands:  
    chown root:root /opt/cft/cftsu  
    chmod u+s /opt/cft/cftsu
5.  Set the copilot.unix.cftsu.fname parameter to /opt/cft/cftsu, for example:  
    CFTUTIL uconfset id=copilot.unix.cftsu.fname, value=/opt/cft/cftsu
6.  Copy the cftsu\_setup executable to the runtime\_dir/bin directory:  
    cp $CFTDIRINSTALL/bin/cftsu\_setup $CFTDIRRUNTIME/bin/cftsu\_setup
7.  Execute the commands:  
    chown root:root $CFTDIRRUNTIME/bin/cftsu\_setup  
    chmod u+s $CFTDIRRUNTIME/bin/cftsu\_setup  
    The cftsu\_setup is a necessary step to perform once, as it is required if at a later date you want to update or upgrade.

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">Once you perform the following procedure once, there is no need to repeat these steps when applying a Transfer CFT update (they are done automatically).         </td>
      </tr>
   </tbody>
</table>
