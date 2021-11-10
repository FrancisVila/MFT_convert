{
    "title": "Active/passive installation - Unix",
    "linkTitle": "Active/passive installation",
    "weight": "180"
}This section describes how to install an active/passive architecture, as described in [About Multi-node architecture.](../../../../about_multinode)

## Prerequisites

Transfer CFT in multi-host architecture requires:

-   A shared file system
-   You must configure the system prior to the multi-node installation, and the shared disk should be ready when you start the Transfer CFT Copilot server. See <a href="../../../windows_install_start_here/before_you_start_win/n_active_active/shared_file_prereq_win" class="MCXref xref">Shared file system prerequisites</a> for details.

### License keys

<span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> in multi-node architecture requires a shared file system for use of a multi-node architecture on several hosts (active/active). Additionally, the system must be configured prior to the multi-node installation and the shared disk ready when starting the Copilot server.

> **Note:**
>
> See Shared file system prerequisites for details.

You can use a single key for a multi-node installation, as either:

-   The hostname must not be defined for the key, or
-   The hostname defined for the key matches the hostname of one of the hosts that composes the multi-node instance

Additionally, the key must have the cluster option.

### Download and uncompress

Download and unzip the <span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span> install package, as described in <a href="../" class="MCXref xref">Install Transfer CFT</a>.

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
<blockquote>
<p><strong>Note:</strong></p>
<p>The load
balancer is used to connect to the Transfer CFT Copilot server.</p>
</blockquote>         </td>
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

When installing using a silent file for a multihost installation, in the silent file (initialize.properties) you can use the same other definitions as in the Transfer CFT <span class="mc-variable axway_variables.Release_Number variable">3.9</span> silent files.

 
