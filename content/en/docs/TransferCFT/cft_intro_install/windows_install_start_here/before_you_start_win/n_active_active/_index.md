{
    "title": "Active/active installation - Windows",
    "linkTitle": "Active/active installation",
    "weight": "170"
}This section describes how to install active/active failover, as described in [About Multi-node architecture.](../../../../about_multinode)

## Prerequisites

When installing a Transfer CFT multi-node architecture in Windows, the user performing the installation must:

-   Be a domain user who is part of the Administrators group.
-   Be the same user for all machines.
-   Have all rights (create/modify/delete) to the shared disk on all machines when <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> is installed in a multi-host architecture.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>You must configure the system prior to the multi-node installation, and the shared disk should be ready when you start the Transfer CFT Copilot server. See <a href="shared_file_prereq_win" class="MCXref xref">Shared file system prerequisites</a> for details.         </td>
      </tr>
   </tbody>
</table>

## Overview

A cluster installation of Transfer CFT with multi-node (HA):

-   Install Transfer CFT and enable the multi-node architecture.
-   Installation procedure must be executed on each host:
    -   The first host installation sets the Shared directory, the &lt;Transfer\_CFT Shared> directory and all of the Transfer CFT configurations.
    -   During each hosts installation (meaning additional nodes), you are prompted to specify the shared directory.
-   Transfer CFT binaries are installed on several hosts and runtime files are installed on a shared file system.
-   Only runtime files are shared.
-   At any given time:
    -   One or several hosts are active.
    -   All Transfer CFT runtime environments (Transfer CFT nodes) are running.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>Transfer CFT binaries can be patched on each host one after the other without stopping the Transfer CFT instance (all of the Transfer CFT nodes).         </td>
      </tr>
   </tbody>
</table>

Shared directory

This is the path and name of the directory where you want to create a shared directory for the cluster installation. The shared directory is used to store product data files.

*Windows only* - When installing a Windows multi-host Transfer CFT architecture, we recommend that you use UNC notation, which defines the path to a shared folder using the format<span class="code"> \\\\server\\sharename.</span>

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>Transfer CFT supports all POSIX file systems.         </td>
      </tr>
   </tbody>
</table>

Installation directory

The path and name of the local directory where you want to install the first cluster.

## Before you start

### License keys

<span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> in multi-node architecture requires a shared file system for use of a multi-node architecture on several hosts (active/active). Additionally, the system must be configured prior to the multi-node installation and the shared disk ready when starting the Copilot server.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>See <a href="shared_file_prereq_win" class="MCXref xref">Shared file system prerequisites</a> for details.         </td>
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

Create as many copies of the initialize.properties file as you have hosts in the multi-node installation. Customize the *N* initialize.properties file with the following parameters to enable a multi-node installation.

<table>
   <tbody>
      <tr>
         <td>CFT_Full_Hostname         </td>
         <td><p>Host Address of the local server: FQDN (Fully Qualified Domain Name) or IP Address.</p>
<p>When you re installing a cluster, there are two ways to define this parameter:</p>
<ul>
<li><p>If you do not set this in the silent file, the install determines it (if the machine is correctly configured)</p></li>
<li>Set the FQDN for each machine in the cluster, that is, for each host installation</li>
</ul>         </td>
      </tr>
      <tr>
         <td>Runtimedir         </td>
         <td>The runtime directory must be in a shared directory.         </td>
      </tr>
      <tr>
         <td>Multinode_Enable         </td>
         <td><p>Enable the multi-node architecture.</p>
<p>To use a multi-node architecture, you must define the multi-node option in the initialize.properties file.</p>         </td>
      </tr>
      <tr>
         <td>Multinode_Number         </td>
         <td>Enter the number of nodes.         </td>
      </tr>
      <tr>
         <td>LoadBalancer_Host         </td>
         <td><p>Specify the host address of the load balancer.</p>
<p>When using an ACTIVE/ACTIVE or ACTIVE/PASSIVE deployment, you require a load
balancer to connect to the Transfer CFT Copilot server.</p>         </td>
      </tr>
      <tr>
         <td>LoadBalancer_Port         </td>
         <td>Specify the load balancer port, which is redirected to the
Central Governance dedicated port of the Transfer CFT UI Server.
<p>When using ACTIVE/ACTIVE or ACTIVE/PASSIVE deployment, you require a load
balancer to connect to the Transfer CFT Copilot server.</p>         </td>
      </tr>
   </tbody>
</table>

## Installation overview

1.  Start the installation.
2.  Transfer\_CFT\_<span class="mc-variable axway_variables.Release_Number variable">3.9</span>\_Install\_win-x86-64\_BNXXXXXXXX.exe/bat
3.  ./Transfer\_CFT\_<span class="mc-variable axway_variables.Release_Number variable">3.9</span>\_Install\_&lt;OS>\_&lt;BN>.run
4.  In the Installation Architecture screen, select **Cluster - first host**.
5.  Complete the installation.
6.  To add a host to create a multi-host, multi-node installation, run the install <span class="code">exe/bat</span> again. This time select **Cluster - Additional host**.

After installation, but before you can use the cluster installation, you must configure the high-availability operations. The procedure for cluster configuration varies depending on the platform on which the cluster is installed.

## Silent installation

This section describes the differences when installing using a silent file for a multi-node installation.

If the silent file architecture is either first\_host or additional\_host, there are two important parameters:

-   multinode\_hostname
-   multinode\_host\_address

By default, these 2 attributes are automatically completed if they are not specified in the silent file.

During the runtime creation and for each host, the multinode\_hostname is used as the basis for the cft.multi\_node.hostnames, where cft.multi\_node.hostnames=Cluster\_short\_hostname1, Cluster\_short\_hostname2, Cluster\_short\_hostname3, Cluster\_short\_hostname4. Using the same logic, the multinode\_host\_addresss is used to create each \_ cft.multi\_node.hostnames.\*\*\*\*.host uconf attribute.

In the silent file (initialize.properties), you can use the same other definitions as in the Transfer CFT 3.3.2 silent files.

## Commands

See the [Multi-node commands and management](../../../../about_multinode/multi_node_commands) section for details on using <span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span> commands and cluster management.

## Troubleshooting

Please see <a href="../../../../troubleshoot_intro/admin_troubleshooting_server/admin_troubleshooting_runtime/troubleshoot_multinode" class="MCXref xref">Troubleshoot multi-node</a>.

## Integrate Transfer CFT in a Microsoft Cluster Service (MSCS)

### Prerequisites

Transfer CFT must be installed in service mode.

### Define Transfer CFT as a Generic Service Resource

Transfer CFT is a cluster-unaware application. However, you can integrate Transfer CFT in a cluster environment as a Generic Service Resource. Use the Microsoft **High Availability Wizard** to create a **Generic Service**, and from the **Select Service** dialog box select the Transfer CFT service.

### License key

The Transfer CFT license key refers to a specific machine, and is based on the machine's hostname. To allow Transfer CFT to start on both cluster nodes, you need one license key per node. Enter the two license keys in the <span class="code">%CFTKEY%</span> file located on the shared disk, one key per line.