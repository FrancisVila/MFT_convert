{
    "title": "Enterprise Cluster prerequisites",
    "linkTitle": "Cluster prerequisites",
    "weight": "130"
}Before you deploy an Enterprise Cluster, you must have:

-   A features license that permits the number of clustered <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Servers (nodes) in your cluster.
-   A license for all the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge servers in your cluster.
-   An external Oracle, PostgreSQL, or Microsoft SQL Server database server or cluster that satisfies the requirements described in the <span class="redirect_st_inst" cshid="install" data-version="5.3.5">*<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Installation Guide*</span>.
-   A file system that all servers in the cluster can access (for example, using network-attached storage).
-   The working network, including the firewall and load balancer systems required by your cluster deployment.
-   The time settings (clocks) on all computers in the network synchronized.
-   If a secure connection to the database is used, the cluster server installer will need to have the database certificate or access to the Java key store containing the database certificate.

**Related topics:**

-   <a href="../t_st_setup_cluster" class="MCXref xref">Set up a cluster</a>
-   <a href="../t_st_add_server_to_cluster" class="MCXref xref">Add a server to a cluster</a>
-   <a href="../t_st_remove_server_from_cluster" class="MCXref xref">Remove a server from a cluster</a>
-   <a href="../t_st_view_cluster_status" class="MCXref xref">View cluster status</a>
-   <a href="../t_st_notification_of_cluster_status" class="MCXref xref">Notification of cluster status</a>
-   <a href="../t_st_setup_disaster_recovery_cluster" class="MCXref xref">Set up a disaster recovery cluster</a>
-   <a href="../t_st_maintain_disaster_recovery_cluster" class="MCXref xref">Maintain a disaster recovery cluster</a>
-   <a href="../t_st_dr_failover_fallback" class="MCXref xref">Disaster recovery failover and fallback</a>
-   <a href="../t_st_direct_cluster_workload" class="MCXref xref">Direct cluster workload</a>
