{
    "title": "Standard Cluster model",
    "linkTitle": "Standard Cluster model",
    "weight": "90"
}As described in <a href="../../overview/c_st_deploy_models#Clusteri" class="MCXref xref">Cluster models</a>, you can use a Standard Cluster (SC) to provide more capacity than a single <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server or to provide a passive standby server to take over processing if an active server fails.

Standard Clustering uses an embedded database in each node. This minimizes external dependencies and overhead and reduces the cost of clustering. <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> synchronizes most configuration changes on all nodes in the cluster.

You can configure a Standard Cluster as an active/active or active/passive (1:1) cluster. You can deploy a maximum of three servers (nodes) in an active/active Standard Cluster. An active/passive Standard Cluster has one active server and one passive standby server.

One node of a Standard Cluster is distinguished as the *primary server*. The passive node of an active/passive cluster and the one to two other nodes of an active/active cluster are *secondary* servers. The Administration Tool login screen and banner indicate **Primary Server** or **Secondary Server**.

The following topics describe the active/active and active/passive clustering and scheduled tasks, the consolidated log data representation, and the services used for cluster management:

-   <a href="c_st_active-active_active-passive_clustering" class="MCXref xref">Active/active and active/passive clustering</a> - Describes active/active and active/passive clustering.
-   <a href="c_st_scheduled_tasks" class="MCXref xref">Scheduled tasks</a> - Describes active/active and active/passive clustering scheduled tasks.
-   <a href="c_st_consolidated_log_data_representation" class="MCXref xref">Consolidated log data representation</a> - Describes the consolidated log data representation.
-   <a href="c_st_services_used_for_cluster_management" class="MCXref xref">Services used for cluster management</a> - Describes the services used for cluster management.
