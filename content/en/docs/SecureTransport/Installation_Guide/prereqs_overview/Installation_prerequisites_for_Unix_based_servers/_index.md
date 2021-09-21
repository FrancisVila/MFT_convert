{
    "title": "UNIX-based platforms",
    "linkTitle": "UNIX-based platforms",
    "weight": "100"
}Review the following information before starting the installer:

-   All SecureTransport Servers in a cluster must run on the same operating system. All SecureTransport Edge servers that synchronize configuration must run on the same operating system. However, in a multitier security deployment, the operating system for SecureTransport Server systems can be different from the operating system for the SecureTransport Edge systems.
-   SecureTransport is a 64-bit application and requires a 64-bit version of the supported operating systems. The embedded MariaDB database runs as a 32-bit process when SecureTransport is installed in an IBM AIX environment. On all the other supported 64-bit operating systems, the embedded MariaDB database runs as a 64-bit process.
-   All SecureTransport Servers in a cluster must use the same installation path, such as `/opt/Axway/SecureTransport`.
-   Copy the `taeh` file from the systems running the primary server in a Standard Cluster or the first server in the Enterprise Cluster to the system where you will install the subsequent server.
-   Set a `TasksMax` value  
    In some cases, the SecureTransport services may not automatically start after reboot on certain Unix-based OS distributions because of a default limit of each task per service configured on the OS side. While this limit may differ across different OSs, this problem may occur with services that handle bigger workloads. The recommended approach is to manually set a `TasksMax` value to a bigger one, for the relevant protocol services and the db service as well. The following example procedure is for the HTTP daemon. Apply that same procedure to the database service, and to all protocol services that handle bigger workloads:  
     
    1.  For `securetransport_httpd` service, create a directory `/etc/systemd/system/securetransport_httpd`.service.d (unless it already exists).

    2.  Create a file named `override.conf` in that directory.

    3.  Add the following content to the `override.conf` file:

    4.  <table cellspacing="0">   <col/>   <tbody>      <tr>         <td>            <p>[Service]
</p>            <p>TasksMax=8192</p>         </td>      </tr>   </tbody></table>

    5.  Repeat these steps for the `securetransport_db` service, as well as every protocol service in use.

## Minimum UNIX hardware requirements

SecureTransport runs on any computer or virtual environment capable of running the supported version of the operating system. The computer or virtual environment requires a functional network connection.

The following table provides the minimum hardware requirements needed to install SecureTransport:

<table cellpadding="0" cellspacing="0">   <col/>   <col/>   <col/>      <tr>         <td valign="top">         </td>         <td valign="top"><span><b>Note</b></span>         </td>         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">In heavy loaded environments, you might have to increase the value of <code>TasksMax</code> to above <code>8192</code>, but no more than <code>24576</code>.         </td>      </tr></table>

During SecureTransport installation, approximately 20 GB of free disk space is temporarily required for the extracted installer and SecureTransport files. The files are removed when the installation completes. If the installation fails, you can reclaim the disk space by removing the `/tmp/AxwayTemptimestamp` directory.

During SecureTransport upgrade, the `/tmp` directory requires an additional 20 GB of free space for a total of approximately 40 GB of free space needed to upgrade. The additional `/tmp` directory space is not required for fresh installations or during normal operations.

Alternatively, prior the upgrade, the `TEMPORARY_DIR` environment variable, pointing to a directory with sufficient space, can be exported to be used during the installation or upgrade.

To install and run SecureTransport, the OS must be able to allocate at least 8 GB of memory to SecureTransport. On UNIX-based platforms, you can limit the system resources available using `ulimit` or similar commands.

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Platform</th>
         <th>Architecture</th>
         <th>RAM for 64-bit OS</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>CentOS         </td>
         <td>x86_64         </td>
         <td>8 GB         </td>
      </tr>
      <tr>
         <td>IBM AIX         </td>
         <td>IBM POWER         </td>
         <td>8 GB         </td>
      </tr>
      <tr>
         <td>Oracle Enterprise Linux         </td>
         <td>x86_64         </td>
         <td>8 GB         </td>
      </tr>
      <tr>
         <td>Red Hat Enterprise Linux         </td>
         <td>x86_64         </td>
         <td>8 GB         </td>
      </tr>
      <tr>
         <td>SUSE Linux Enterprise Server         </td>
         <td>x86_64         </td>
         <td>8 GB         </td>
      </tr>
   </tbody>
</table>

### <span id="Viewing"></span>Viewing memory limits

You can view the memory limitations using the command `ulimit -a`. These limitations need to be adjusted for the `root` user for the installation to run correctly and for the user running SecureTransport if a non-root install is done. After installation, only the user running SecureTransport should be able to allocate that much memory.

### <span id="Changing"></span>Changing memory limits

To change these limits, different commands are used for each UNIX-based platform.

To set system resource limits on AIX:

1.  At the command line, type `smitty users` and press Enter.
2.  From the menu, select `Change / Show Characteristics of a User`.  
    Ensure that `Soft DATA segment` and `Hard DATA segment` allows more than 1 GB of memory. For best results, set these options to unlimited (`-1`).

To set system resource limits on RHEL:

1.  Modify the file `/etc/security/limits.conf`. Use the following setting to allow more than 1 GB of memory:

    <table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Ensure the resources allowed include at least 8 GB of memory.         </td>
      </tr>
</table>

2.  Reboot the computer.

## Host name resolution

For SecureTransport to run, the host name of the server must resolve to its actual IP address, not the loopback address (127.0.0.1).

1.  Use `nslookup` to check the IP address for the server.
2.  If the IP address returned is not the actual IP address of the server, check `/etc/hosts `and remove any entry that maps the host name to the loopback address and check the IP address again.
3.  If the IP address returned is not correct, check your the operating system name resolution settings, correct any errors, and check the IP address again.
4.  If the IP address returned is not correct, add an entry to `/etc/hosts` that maps the host name to the correct IP address.

 

**Related topics:**

-   [Requirements for specific operating systems](requirements_for_specific_operating_systems)
-   [Prerequisites for non-root installations](prerequisites_for_non_root_installations)
