{
    "title": "Maintain a disaster recovery cluster",
    "linkTitle": "Maintain a disaster recovery cluster",
    "weight": "210"
}Once your DR site is set up, you must maintain consistency with the production site as described in <a href="../../c_st_largeenterpriseclustermodel/c_st_passive_disaster_recovery#Large_Enterprise_Clustering_2746683174_1047112" class="MCXref xref">Passive disaster recovery</a> so that the data in the DR shared database and the DR shared file system are current.

When you edit a configuration file or a script on an active {{< SecureTransport/componentshortname  >}} Server or {{< SecureTransport/componentshortname  >}} Edge, consider if you need to make the same changes on the corresponding server in the other site.

After you fail over to the DR cluster, you need to restore your production cluster’s functionality. Before you switch back to your production cluster and return your DR cluster to standby status, you must replicate the data in the DR shared database and the DR shared file system to the production site.

**Related topics:**

-   <a href="../c_st_cluster_prerequisites" class="MCXref xref">Enterprise Cluster prerequisites</a>
-   <a href="../t_st_setup_cluster" class="MCXref xref">Set up a cluster</a>
-   <a href="../t_st_add_server_to_cluster" class="MCXref xref">Add a server to a cluster</a>
-   <a href="../t_st_remove_server_from_cluster" class="MCXref xref">Remove a server from a cluster</a>
-   <a href="../t_st_view_cluster_status" class="MCXref xref">View cluster status</a>
-   <a href="../t_st_notification_of_cluster_status" class="MCXref xref">Notification of cluster status</a>
-   <a href="../t_st_setup_disaster_recovery_cluster" class="MCXref xref">Set up a disaster recovery cluster</a>
-   <a href="../t_st_dr_failover_fallback" class="MCXref xref">Disaster recovery failover and fallback</a>
-   <a href="../t_st_direct_cluster_workload" class="MCXref xref">Direct cluster workload</a>
