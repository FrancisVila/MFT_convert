{
    "title": "Active/passive installation",
    "linkTitle": "Active/passive installation",
    "weight": "180"
}This section describes how to install an active/passive architecture, as described in [About Multi-node architecture.](../../../../about_multinode)

## Prerequisites

Transfer CFT in multi-host architecture requires:

-   A shared file system
-   You must configure the system prior to the multi-node installation, and the shared disk should be ready when you start the Transfer CFT Copilot server. See [Shared file system prerequisites](../../../windows_install_start_here/before_you_start_win/n_active_active2/shared_file_prereq_win) for details.

### License keys

Transfer CFT in multi-node architecture requires a shared file system for use of a multi-node architecture on several hosts (active/active). Additionally, the system must be configured prior to the multi-node installation and the shared disk ready when starting the Copilot server.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">See <a href="../../../windows_install_start_here/before_you_start_win/n_active_active2/shared_file_prereq_win">Shared file system prerequisites</a> for details.         </td>
      </tr>
</table>

You can use a single key for a multi-node installation, as either:

-   The hostname must not be defined for the key, or
-   The hostname defined for the key matches the hostname of one of the hosts that composes the multi-node instance

Additionally, the key must have the cluster option.

### Download and uncompress

Download and unzip the Transfer CFT install package, as described in [Install Transfer CFT](../).

### Customize

Create as many copies of the initialize.properties file as you have hosts in the installation. Customize the *n* initialize.properties file with the following parameters.

<table cellspacing="0">
   <col/>
   <col/>
   <tbody>
      <tr>
         <td>CFT_Full_Hostname         </td>
         <td>
            <p>Host Address of the local server: FQDN (Fully Qualified Domain Name) or IP Address.</p>
            <p>When you re installing a cluster, there are two ways to define this parameter:</p>
            <ul>
               <li>
            <p>If you do not set this in the silent file, the installation determines it (if the machine is correctly configured)</p>
               </li>
               <li>Set the FQDN for each machine in the cluster, that is, for each host installation               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>Runtimedir         </td>
         <td>The runtime directory must be in a shared directory.         </td>
      </tr>
      <tr>
         <td>LoadBalancer_Host         </td>
         <td>
            <p>Specify the host address of the load balancer, which is the cluster's public IP address in an active/passive deployment.
</p>
            <p>&amp;&amp;&amp; ïïï ùùù</p>
         </td>
      </tr>
      <tr>
         <td>LoadBalancer_Port         </td>
         <td>Specify the load balancer port, which is redirected to the
Central Governance dedicated port of the Transfer CFT UI Server.
         </td>
      </tr>
   </tbody>
</table>

## Install

1.  Start the installation.
2.  Transfer\_CFT\_3.9\_Install\_win-x86-64\_BNXXXXXXXX.exe
3.  ./Transfer\_CFT\_3.9\_Install\_&lt;OS>\_&lt;BN>.run
4.  In the Installation Architecture screen, select **Cluster - first host**.
5.  Complete the installation.
6.  To add a host to create a multi-host installation, run the install exe/bat again. This time select **Cluster - Additional host**.

## Silent installation

When installing using a silent file for a multihost installation, in the silent file (initialize.properties) you can use the same other definitions as in the Transfer CFT 3.9 silent files.

 
