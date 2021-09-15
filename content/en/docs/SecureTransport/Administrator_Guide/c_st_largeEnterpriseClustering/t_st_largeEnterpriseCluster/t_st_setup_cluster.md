{
    "title": "Set up a cluster",
    "linkTitle": "Set up a cluster",
    "weight": "150"
}This is an overview of the steps required to create an Enterprise Cluster (EC). For the procedures to perform the server installation and initial configuration, refer to the <span cshid="install" data-version="5.3.5">*SecureTransport Installation Guide*</span>.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top"> If you use the <b>ClusterAuto-Register IP/FQDN</b> option during the installation of the SecureTransport Servers, the nodes of the cluster will be registered automatically. In this case, after completing step 4, you can directly proceed with step 9: you don't have to follow the steps 5 to 8.         </td>
      </tr>
</table>

1.  Implement and test the network and computers for the cluster, including the shared database and shared file system.
2.  Install the first SecureTransport Server.  
    When you install the first SecureTransport Server, the installer creates the schema for the cluster in the shared database.
3.  Install the SecureTransport licenses and perform the initial configuration for the first SecureTransport Server.
4.  Install the other SecureTransport Servers. Specify the same installation directory, specify usage of the existing database schema, and import the `taeh` file from the first Server.  
    **Note** The Admin service on the newly installed Server nodes starts after the installation; however it is not operational.  
5.  Stop the Admin service on each newly-installed SecureTransport node.
6.  Stop all the protocol servers and services on all nodes except on the first SecureTransport Server. Make sure that only the Administration Tool service is running on that SecureTransport Server.
7.  Log on to the Administration Tool on the running Server as the `admin` user, and add to the cluster each of the cluster nodes, including the one you are logged on to. For details, see [Add a server to a cluster](../t_st_add_server_to_cluster).  
    **Note** Do not restart any other SecureTransport Server until it is added to the cluster.  
8.  Start the Admin service on the newly-installed Secure Transport servers.
9.  Install the SecureTransport licenses for the newly-installed SecureTransport Servers.  
    Do not perform the other steps of the initial configuration because the configuration is copied to the other servers when they are added to the cluster.
10. Restart all SecureTransport Servers.

The Enterprise Cluster is now operational with its basic initial configuration.

## TLS encrypted communication across Server nodes

Communication across SecureTransport Server nodes in an Enterprise Cluster can be encrypted using TLS. The certificate with the `admind` alias is used for the encryption.  

-   On fresh installation of the November 2020 SecureTransport 5.5 build or later, TLS encrypted communication across SecureTransport Server nodes is applied by default.
-   If SecureTransport is upgraded to the November 2020 SecureTransport 5.5 build or later from any previous version (for example, 5.4 latest patch or 5.5 GA), the Server nodes communication is not encrypted by default.

You can modify this behavior using the `Cluster.enable.SSL` server configuration option.  

You can then proceed with the rest of the configuration setup, for example, perform the initial configuration for the SecureTransport Edge servers.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Tip  </b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Tip  &lt;/b&gt;" valign="top">You may perform most configuration tasks once on any SecureTransport Server. The configuration is saved in the database and shared across all other SecureTransport Server nodes in the cluster.         </td>
      </tr>
</table>

For more details on server configuration specifics, see [Server configuration](../../../operations_menu/c_st_serverconfiguration).

**Related topics:**

-   [Enterprise Cluster prerequisites](../c_st_cluster_prerequisites)
-   [Add a server to a cluster](../t_st_add_server_to_cluster)
-   [Remove a server from a cluster](../t_st_remove_server_from_cluster)
-   [View cluster status](../t_st_view_cluster_status)
-   [Notification of cluster status](../t_st_notification_of_cluster_status)
-   [Set up a disaster recovery cluster](../t_st_setup_disaster_recovery_cluster)
-   [Maintain a disaster recovery cluster](../t_st_maintain_disaster_recovery_cluster)
-   [Disaster recovery failover and fallback](../t_st_dr_failover_fallback)
-   [Direct cluster workload](../t_st_direct_cluster_workload)
