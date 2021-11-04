{
    "title": "Troubleshooting installations and upgrades",
    "linkTitle": "Troubleshoot installations and upgrades",
    "weight": "170"
}This page describes how to locate the various <span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span> installation logs when troubleshooting, and the files you made want to have ready if you need to contact Axway Support.

If an issue occurs while performing an installation or an upgrade, check for errors in the following places. Perform these steps before attempting to roll back in the case of an upgrade.

1.  If you performed an upgrade from a version prior to v3.6, look for errors in the <span class="code">install.log</span> located in the <span class="code">axway.installer</span> directory.
2.  Check for errors in the <span class="code">install.log</span> in the <span class="code">CFT</span> directory (if this is a new installation or you upgraded from a version that did not use the Axway installer).
3.  Navigate to the runtime directory and check the <span class="code">.up </span>folder contents.
4.  Again from the runtime directory, check the <span class="code">copupd </span>folder contents. This folder is only available after performing a <span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span> update or upgrade when using <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span> or <span class="mc-variable suite_variables.FlowManager variable">Flow Manager</span>. In the <span class="code">copupd </span>folder, navigate to the<span class="code"> log > install</span> file.
5.  Be ready to supply all of these files to Axway support if you cannot troubleshoot the issue with any errors found in the logs.

## Transfer CFT Copilot server issues

### Copilot doesn't start

-   Check that the port is not already used by another application.
-   Close all active sessions, use the syntax: <span class="code">copstop -f</span>
-   Check that there are no orphan "<span class="code">cop\*</span>" processes. If there are, manually kill these processes.

<span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> server

### Cannot start my <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>

-   Check your <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> log in Central Governance.
-   From the local <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> runtime, try to manually start the server. If you cannot manually start the server, refer to *[Support tools](https://docs.axway.com/bundle/TransferCFT_38_UsersGuide_allOS_en_HTML5/page/Content/Troubleshooting/support_tools.htm)* in the <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span><span class="mc-variable suite_variables.DocTypeUser variable">User Guide</span>.

### Runtime directory error

If for whatever reason an installation that uses symbolic links fails, once the silent files have been corrected, you must delete the <span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span> home installation directory to which the symbolic link points. Failing to do so causes the installer to go into upgrade mode.

Additionally, you cannot perform an installation in a directory if the runtime already exists.

### Problem with post-install step

If you get a **Warning***Problem running post-install step* message at the end of an installation, check the installation log file. The message `ERR: Unable to decrypt the password` indicates that there is an issue related to the PasswordsEncryptionKey.

1.  In the `initialize.properties` file, locate all encrypted passwords and enter the passwords in clear text, then ensure that the `PasswordsEncryptionKey` field is empty.
2.  Save the file.
3.  Remove the files created by the unsuccessful installation.
4.  Repeat the installation procedure.

## Multi-node multihost installation issues

### Second node or host fails to install

*UNIX*

While performing a multihost multi-node installation, where the user has a different UserId (UD) and GroupId (GID) for each host, you successfully install the first node on the first host, which creates the runtime on the shared disk. But the second node or host installation fails with the message:

Warning: The directory

/mnt/CFT36MNLIN\_BN12807000/runtime

is not writable by the current user

To resolve this issue, using a different user perform the following commands on all hosts that are involved in the multihost, multi-node installation:

1.  Open an SSH session on the machine and run the following command to change the UID, for example:  
    <span class="code">sudo usermod -u 1005 ithomas</span>  
    Where `1005 `is the desired common UID, and <span class="code">ithomas </span>is the user common to all of the UNIX hosts.
2.  Run the command to change the GID, for example:  
    `sudo groupmod -g 1006 ithomas`  
    Where <span class="code">1006 </span>is the desired common GID, and <span class="code">ithomas </span>is the group to which the user <span class="code">ithomas </span>belongs.

For more information, please refer to the [NFS](http://nfs.sourceforge.net/nfs-howto/ar01s07.html#pemission_issues) documentation.

## Installer does not run

When the /tmp directory and the user's homedir have the noexec option, InstallBuilder does not work:

EX:

Transfer\_CFT\_3.6\_Install\_linux-x86-64\_BN12807000.run --mode unattended --conf-file /opt/xip/cft36/initialize.properties

Unable to initialize installer.

The possible workarounds are therefore:

remove the noexec on one of the partitions

run the .run with a user who has the necessary rights (ex: sudo)

Create a temporary / home on an unprotected disk

sudo mkdir / instcft

sudo chown &lt;user>: &lt;user> / instcft

export HOME = / instcft => unprotected disk

./Transfer\_CFT\_3.7\_Install\_linux-x86-64\_BN13015241.run --mode unattended

Solution 3 should work for the client as long as the HOME points to a directory where it has execution rig