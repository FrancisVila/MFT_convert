{
    "title": "Active/active installation - Unix",
    "linkTitle": "Active/active installation",
    "weight": "170"
}This section describes how to install active/active failover, as described in [About Multi-node architecture.](../../../about_multinode)

## Multi-node license keys

Transfer CFT in multi-node architecture requires a shared file system for use of a multi-node architecture on several hosts (active/active). Additionally, the system must be configured prior to the multi-node installation and the shared disk ready when starting the Copilot server.

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">See <a href="../../windows_install_start_here/before_you_start_win/active_passive_win/shared_file_prereq_win">Shared file system prerequisites</a> for details.         </td>
      </tr>
   </tbody>
</table>

You can use a single key for a multi-node installation, as either:

-   The hostname must not be defined for the key, or
-   The hostname defined for the key matches the hostname of one of the hosts that composes the multi-node instance

Additionally, the key must have the cluster option.

### Download and uncompress

Download and unzip the Transfer CFT install package, as described in [Install Transfer CFT](transfercft/cft_intro_install/unix_install_start_here/before_you_start_unix).

### Customize

Create as many copies of the initialize.properties file as you have hosts in the multi-node installation. Customize the *N* initialize.properties file with the following parameters to enable a multi-node installation.

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>CFT_Full_Hostname         </td>
         <td>            <p>Host Address of the local server: FQDN (Fully Qualified Domain Name) or IP Address.</p>
            <p>When you're installing a cluster, there are two ways to define this parameter:</p>
            <ul>
               <li>            <p>If you do not set this in the silent file, the install determines it (if the machine is correctly configured)</p>               </li>
               <li>Set the FQDN for each machine in the cluster, that is, for each host installation               </li>
            </ul>         </td>
      </tr>
      <tr class="even">
         <td>Runtimedir         </td>
         <td>The runtime directory must be in a shared directory.         </td>
      </tr>
      <tr class="odd">
         <td>Multinode_Enable         </td>
         <td>            <p>Enable the multi-node architecture.</p>
            <p>To use a multi-node architecture, you must define the multi-node option in the initialize.properties file.</p>         </td>
      </tr>
      <tr class="even">
         <td>Multinode_Number         </td>
         <td>Enter the number of nodes.         </td>
      </tr>
      <tr class="odd">
         <td>LoadBalancer_Host         </td>
         <td>            <p>Specify the host address of the load balancer.</p>
            <p>When using an ACTIVE/ACTIVE or ACTIVE/PASSIVE deployment, you require a load
balancer to connect to the Transfer CFT Copilot server.</p>         </td>
      </tr>
      <tr class="even">
         <td>LoadBalancer_Port         </td>
         <td>Specify the load balancer port, which is redirected to the
Central Governance dedicated port of the Transfer CFT UI Server.
            <p>When using ACTIVE/ACTIVE or ACTIVE/PASSIVE deployment, you require a load
balancer to connect to the Transfer CFT Copilot server.</p>         </td>
      </tr>
   </tbody>
</table>

## Install

1.  Start the installation.
2.  Transfer\_CFT\_3.9\_Install\_linux-x86-64\_BNXXXXXXXX.exe
3.  ./Transfer\_CFT\_3.9\_Install\_&lt;OS>\_&lt;BN>.run
4.  In the Installation Architecture screen, select **Cluster - first host**.
5.  Complete the installation.
6.  To add a host to create a multi-host, multi-node installation, run the install again. This time select **Cluster - Additional host**.

## Silent installation

This section describes the differences when installing using a silent file for a multi-node installation.

If the silent file architecture is either first\_host or additional\_host, there are two important parameters:

-   multinode\_hostname
-   multinode\_host\_address

By default, these 2 attributes are automatically completed if they are not specified in the silent file.

During the runtime creation and for each host, the multinode\_hostname is used as the basis for the cft.multi\_node.hostnames, where cft.multi\_node.hostnames=Cluster\_short\_hostname1, Cluster\_short\_hostname2, Cluster\_short\_hostname3, Cluster\_short\_hostname4. Using the same logic, the multinode\_host\_addresss is used to create each \_ cft.multi\_node.hostnames.\*\*\*\*.host uconf attribute.

In the silent file (initialize.properties), you can use the same other definitions as in the Transfer CFT 3.9 silent files.

## Commands

See the [Multi-node commands and management](../../../about_multinode/multi_node_commands) section for details on using Transfer CFT commands and cluster management.

## Troubleshooting

Please see [Troubleshoot multi-node](../../../troubleshoot_intro/admin_troubleshooting_server/admin_troubleshooting_runtime/troubleshoot_multinode).
