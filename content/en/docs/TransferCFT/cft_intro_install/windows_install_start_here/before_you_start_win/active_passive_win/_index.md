{
    "title": "Active/passive installation - Windows",
    "linkTitle": "Active/passive installation",
    "weight": "180"
}This section describes how to install an active/passive architecture, as described in [About Multi-node architecture.](../../../../about_multinode)

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>Transfer CFT supports all POSIX file systems. Active/passive shared disks must be POSIX compliant!         </td>
      </tr>
   </tbody>
</table>

A cluster installation of Transfer CFT without multi-node is an active/passive installation as described below:

-   Install Transfer CFT using the Cluster installation architecture of the Installer and disable the multi-node architecture.
-   Installation procedure must be executed on each host:
    -   The first host installation
    -   Additional hosts installation
-   Transfer CFT binaries are installed on several hosts and runtime files are installed on a shared file system.
-   Only runtime files are shared.
-   You must configure the cluster after installation but before you can use the cluster. The procedure for cluster configuration varies depending on the platform on which the cluster is installed.
-   At any given time:
    -   Only one host is active
    -   Only one Transfer CFT runtime environment is running on the active host

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>After installing applications in active/passive mode, you must implement the <span class="bold_in_para" style="font-weight: bold;">cft start</span>, <span class="bold_in_para">cft stop</span>, and <span class="bold_in_para">cft status</span> scripts for the cluster.         </td>
      </tr>
   </tbody>
</table>

Shared Directory

This is the path and name of the directory where you want to create a shared directory for the cluster installation. The shared directory is used to store product data files.

*Windows only* - When installing a Windows multi-host Transfer CFT architecture, we recommend that you use UNC notation, which defines the path to a shared folder using the format<span class="code"> \\\\server\\sharename.</span>

Installation Directory

The path and name of the local directory where you want to install the first cluster.

## Prerequisites

### Multi-node license keys

<span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> in multi-node architecture requires a shared file system for use of a multi-node architecture on several hosts (active/active). Additionally, the system must be configured prior to the multi-node installation and the shared disk ready when starting the Copilot server.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>See <a href="../n_active_active/shared_file_prereq_win" class="MCXref xref">Shared file system prerequisites</a> for details.         </td>
      </tr>
   </tbody>
</table>

You can use a single key for a multi-node installation, as either:

-   The hostname must not be defined for the key, or
-   The hostname defined for the key matches the hostname of one of the hosts that composes the multi-node instance

Additionally, the key must have the cluster option.

### Download and uncompress

Download and unzip the <span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span> install package, as described in <a href="../../../unix_install_start_here/before_you_start_unix" class="MCXref xref">Install Transfer CFT</a>.

### Customize

Create as many copies of the initialize.properties file as you have hosts in the installation. Customize the *n* initialize.properties file with the following parameters.

<table>
   <tbody>
      <tr>
         <td>CFT_Full_Hostname         </td>
         <td><p>Host Address of the local server: FQDN (Fully Qualified Domain Name) or IP Address.</p>
<p>When you re installing a cluster, there are two ways to define this parameter:</p>
<ul>
<li><p>If you do not set this in the silent file, the installation determines it (if the machine is correctly configured)</p></li>
<li>Set the FQDN for each machine in the cluster, that is, for each host installation</li>
</ul>         </td>
      </tr>
      <tr>
         <td>Runtimedir         </td>
         <td>The runtime directory must be in a shared directory.         </td>
      </tr>
      <tr>
         <td>LoadBalancer_Host         </td>
         <td><p>Specify the host address of the load balancer, which is the cluster's public IP address in an active/passive deployment.</p>
<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>The load
balancer is used to connect to the Transfer CFT Copilot server.         </td>
      </tr>
   </tbody>
</table>         </td>
      </tr>
      <tr>
         <td>LoadBalancer_Port         </td>
         <td>Specify the load balancer port, which is redirected to the
Central Governance dedicated port of the Transfer CFT UI Server.         </td>
      </tr>
   </tbody>
</table>

## Install

1.  Start the installation.
2.  Transfer\_CFT\_<span class="mc-variable axway_variables.Release_Number variable">3.9</span>\_Install\_win-x86-64\_BNXXXXXXXX.exe
3.  ./Transfer\_CFT\_<span class="mc-variable axway_variables.Release_Number variable">3.9</span>\_Install\_&lt;OS>\_&lt;BN>.run
4.  In the Installation Architecture screen, select **Cluster - first host**.
5.  Complete the installation.
6.  To add a host to create a multi-host installation, run the install <span class="code">exe/bat</span> again. This time select **Cluster - Additional host**.

## Silent installation

This section describes the differences when installing using a silent file for a multi-host installation.

In the silent file (initialize.properties), you can use the same definitions as in the Transfer CFT 3.3.2 silent files.

## Integrate Transfer CFT in a Microsoft Cluster Service (MSCS)

### Prerequisites

Transfer CFT must be installed in service mode.

### Define Transfer CFT as a Generic Service Resource

Transfer CFT is a cluster-unaware application. However, you can integrate Transfer CFT in a cluster environment as a Generic Service Resource. Use the Microsoft **High Availability Wizard** to create a **Generic Service**, and from the **Select Service** dialog box select the Transfer CFT service.