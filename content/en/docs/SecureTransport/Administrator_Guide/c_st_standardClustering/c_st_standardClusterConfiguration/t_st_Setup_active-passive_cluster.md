{
    "title": "Set up an active/passive cluster",
    "linkTitle": "Set up an active/passive cluster",
    "weight": "150"
}When you change the cluster settings to be active/passive, the secondary standby server stops processing events. For details, see <a href="../../c_st_standardclustermodel/c_st_active-active_active-passive_clustering#Active/a" class="MCXref xref">Active/active clusters</a>.

1.  Set up a two-server cluster using the instructions in <a href="../t_st_setup_active-active_cluster#Standard_Clustering_3967700027_1029540" class="MCXref xref">Set up an active/active cluster</a>.
2.  Stop the TM server on both servers in the cluster.
3.  On the *Server Configuration* page of each server, change the value of the `Cluster.mode` parameter to `passive` or `passive_legacy`.
4.  On the primary server, create a file named `<FILEDRIVEHOME>/var/tmp/sentinel_primary`. This file is not used for integration with {{< SecureTransport/companyname >}} Sentinel. It is required whether or not Sentinel is used.  
    To create the file, you can use the `touch` command in UNIX or create an empty file with no file extension in Windows. The file must have 0 bytes.
5.  If you set `Cluster.mode` to `passive_legacy`, on the standby server, set `FolderMonitor.enable` and `Scheduler.enable` to `false`.
6.  Start the TM server on both servers in the cluster.

**Related topics:**

-   <a href="../t_st_setup_active-active_cluster" class="MCXref xref">Set up an active/active cluster</a>
-   <a href="../t_st_specify_cluster_connection_timeout" class="MCXref xref">Specify the cluster connection timeout</a>
-   <a href="../t_st_configure_servers_cluste_trust_certificate" class="MCXref xref">Configure servers in a cluster to trust a certificate</a>
