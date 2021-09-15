{
    "title": "Cluster prerequisites",
    "linkTitle": "Cluster prerequisites",
    "weight": "140"
}Before you deploy an Enterprise Cluster, you must have:

-   A features license that permits the number of clustered SecureTransport Servers (nodes) in your cluster.
-   A license for all the SecureTransport Edge servers in your cluster.
-   An external Oracle, PostgreSQL, or Microsoft SQL Server database server or cluster that satisfies the requirements described in the <span cshid="install" data-version="5.3.5">*SecureTransport Installation Guide*</span>.
-   A file system that all servers in the cluster can access (for example, using network-attached storage).
-   The working network, including the firewall and load balancer systems required by your cluster deployment.
-   The time settings (clocks) on all computers in the network synchronized.
-   If a secure connection to the database is used, the cluster server installer will need to have the database certificate or access to the Java key store containing the database certificate.

**Related topics:**

-   [Set up a cluster](../t_st_setup_cluster)
-   [Add a server to a cluster](../t_st_add_server_to_cluster)
-   [Remove a server from a cluster](../t_st_remove_server_from_cluster)
-   [View cluster status](../t_st_view_cluster_status)
-   [Notification of cluster status](../t_st_notification_of_cluster_status)
-   [Set up a disaster recovery cluster](../t_st_setup_disaster_recovery_cluster)
-   [Maintain a disaster recovery cluster](../t_st_maintain_disaster_recovery_cluster)
-   [Disaster recovery failover and fallback](../t_st_dr_failover_fallback)
-   [Direct cluster workload](../t_st_direct_cluster_workload)
