{
    "title": "Enterprise Cluster model",
    "linkTitle": "Enterprise Cluster model",
    "weight": "100"
}As described in <a href="../../overview/c_st_deploy_models#Clusteri" class="MCXref xref">Cluster models</a>, the managed file transfer workload of an enterprise can exceed the capacity of Standard Clustering. Also, an enterprise might prefer to use an external database to allow their DBAs additional tuning of the underlying database. In either of these cases, you can use {{< SecureTransport/componentlongname  >}} {{< SecureTransport/componentversion  >}} with the Enterprise Cluster (EC) option to implement at a single site a cluster that provides the capacity to handle the file transfer workload required by your organization. With an Enterprise Cluster, an external database and a high-performance cache-management layer significantly improve efficiency and increase potential scale. This allows up to 20 nodes in an active/active cluster. The Enterprise Cluster option requires your organization to provide and maintain an [external database](../../overview/r_st_axway_and_third-party_software_support#Database).

An Enterprise Cluster is efficient and flexible. All tasks, including scheduled work, are distributed across the cluster. You can add and remove servers as needed up to the maximum allowed by your {{< SecureTransport/componentshortname  >}} features license. You can also control how the workload is directed to the servers in the cluster, for example, based on task type.

In an Enterprise Cluster, all servers are active, so there are no standby servers to replace an active server that fails. However, because the components that direct and schedule tasks are distributed across the clustered servers, the cluster implements failover by continuing to process its workload with reduced capacity when a server fails. For increased availability, you can remove another potential single point of failure by implementing a database cluster for the shared database.

Also, with the Enterprise Cluster option, you can implement an active/active cluster with a passive Disaster Recovery (DR) site. For this, you must provide a properly distributed and replicated database and file storage. To enable your implementation of passive DR, the primary production active/active cluster can notify an external mechanism to trigger failover automatically when the number of active nodes in the cluster falls below a threshold.

The following topics provide additional Enterprise Cluster information:

-   <a href="c_st_large_enterprise_cluster_deployment" class="MCXref xref">Enterprise Cluster deployment</a> - Describes the Enterprise Cluster deployment.
-   <a href="c_st_workload_distribution" class="MCXref xref">Workload distribution</a> - Describes the Enterprise Cluster workload distribution.
-   <a href="c_st_passive_disaster_recovery" class="MCXref xref">Passive disaster recovery</a> - Describes the Enterprise Cluster passive disaster recovery.
