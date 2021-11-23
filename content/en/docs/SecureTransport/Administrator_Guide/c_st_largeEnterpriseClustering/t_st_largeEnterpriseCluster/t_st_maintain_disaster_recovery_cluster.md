{
    "title": "Maintain a disaster recovery cluster",
    "linkTitle": "Maintain a disaster recovery cluster",
    "weight": "210"
}Once your DR site is set up, you must maintain consistency with the production site as described in [Passive disaster recovery](../../c_st_largeenterpriseclustermodel/c_st_passive_disaster_recovery#Large_Enterprise_Clustering_2746683174_1047112) so that the data in the DR shared database and the DR shared file system are current.

When you edit a configuration file or a script on an active {{< SecureTransport/componentshortname  >}} Server or {{< SecureTransport/componentshortname  >}} Edge, consider if you need to make the same changes on the corresponding server in the other site.

After you fail over to the DR cluster, you need to restore your production cluster’s functionality. Before you switch back to your production cluster and return your DR cluster to standby status, you must replicate the data in the DR shared database and the DR shared file system to the production site.

**Related topics:**

-   [Enterprise Cluster prerequisites](../c_st_cluster_prerequisites)
-   [Set up a cluster](../t_st_setup_cluster)
-   [Add a server to a cluster](../t_st_add_server_to_cluster)
-   [Remove a server from a cluster](../t_st_remove_server_from_cluster)
-   [View cluster status](../t_st_view_cluster_status)
-   [Notification of cluster status](../t_st_notification_of_cluster_status)
-   [Set up a disaster recovery cluster](../t_st_setup_disaster_recovery_cluster)
-   [Disaster recovery failover and fallback](../t_st_dr_failover_fallback)
-   [Direct cluster workload](../t_st_direct_cluster_workload)
