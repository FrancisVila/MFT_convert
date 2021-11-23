{
    "title": "Active/active and active/passive clustering",
    "linkTitle": "Active/active and active/passive clustering",
    "weight": "110"
}{{< SecureTransport/componentshortname  >}} supports two types of clustering: active/active and active/passive.

The following topics describe the active/active and active/passive clusters and processes:

-   [Active/active clusters](#Active/a)
-   [Active/passive clusters](#Active_passive)
-   [Active/passive deployment](#Active_deploy)
-   [Primary server processes](#Primary)
-   [Failover](#Failover)
-   [Synchronization](#Synchron)

<span id="Active/a"></span>

## Active/active clusters

In an active/active cluster, {{< SecureTransport/componentshortname  >}} balances the server-originating load between the primary and the secondary servers. All servers in the cluster are active and provide processing capacity. {{< SecureTransport/componentshortname  >}} automatically replicates all event information collected by the primary server to the secondary servers. If the primary server fails, the cluster automatically switches control to the secondary server. An active/active cluster requires a third-party load-balancer. To prevent performance degradation if the primary server fails in an active/active cluster, the servers should have identical hardware.

The main advantages of an active/active cluster are:

-   {{< SecureTransport/componentshortname >}} automatically balances the load between the different servers in the cluster.
-   The secondary servers are active. This means that they can assume the load from a failed secondary server or take over from a failed primary server almost immediately.

However, to prevent performance problems, you must carefully monitor the load on an active/active cluster. An active/active cluster can suffer performance degradation when one server fails unless the remaining servers can handle the total workload for the cluster.

For more information, see [Set up an active/active cluster](../../c_st_standardclusterconfiguration/t_st_setup_active-active_cluster#Standard_Clustering_3967700027_1029540).

<span id="Active_passive"></span>

## Active/passive clusters

An active/passive cluster consists of one active server and one passive standby server with a third-party load-balancer to determine when failover is required for passive legacy and to send the users to the correct node. For passive, the {{< SecureTransport/componentshortname  >}} will failover on its own. To prevent performance degradation if the primary server fails in an active/passive cluster, the servers should have identical hardware.

In an active/passive cluster, the primary server handles the event queue and processes events. While the primary server is active, the standby server remains in a passive state and does not process events. Depending on the server mode (set in the `Cluster.mode` server configuration parameter), an active/passive cluster has different features and advantages.

When the cluster mode is `passive`, the Transaction Manager runs on the secondary standby server and the event data is synchronized from the primary server. The primary server does not dispatch events to the Transaction Manager on the standby server and the standby server does not process events. The Sentinel link data is also synchronized.

The advantages of an active/passive cluster with `passive` cluster mode are:

-   The cluster includes a fully redundant secondary standby server to handle the cluster workload if the primary server fails.
-   Failover from the primary server to the secondary standby server is automatic.
-   On failover, the cluster reports the states of file transfers to Sentinel consistently so that Sentinel can link them, so this mode is required for an active/passive cluster that works with Sentinel.

With `passive_legacy` cluster mode, the Transaction Manager listeners start on the
standby server. The
event data is not synchronized from the primary server, but the
Transaction Manager on the standby server might accept connections and
process events. You must stop the Transaction Manager on the standby
server or configure your load balancer so that it does not direct
traffic to it when the primary server is up and running. The Sentinel link data is not synchronized. You must disable the Folder Monitor and scheduler on the standby server. If the primary server fails, you must perform a manual failover to make the standby server active.

The advantages an active/passive cluster with `passive_legacy` cluster mode are:

-   The cluster includes a fully redundant secondary standby server to handle the cluster workload if the primary server fails.
-   Because events and Sentinel link data are not sent to a standby server with `passive_legacy` cluster mode, it can be in a different location for a disaster recovery (DR) if the network between the sites has required bandwidth and latency. For information on a more general DR solution using Enterprise Clustering, see [Passive disaster recovery](../../../c_st_largeenterpriseclustering/c_st_largeenterpriseclustermodel/c_st_passive_disaster_recovery).

For more information, see [Set up an active/passive cluster](../../c_st_standardclusterconfiguration/t_st_setup_active-passive_cluster).

<span id="Active_deploy"></span>

## Active/passive deployment

The following diagram shows a simple active/passive deployment with `passive` cluster mode and one {{< SecureTransport/componentshortname  >}} Edge server. On failover, the load balancer in the secure network redirects the connections from the internal clients and servers to {{< SecureTransport/componentshortname  >}} Server 2 and the {{< SecureTransport/componentshortname  >}} Edge directs the connection from the partner clients and servers to {{< SecureTransport/componentshortname  >}} Server 2. For a description of the connections, see [Streaming deployment]().

<img src="/Images/SecureTransport/STDeployment_ActivePassive.png" class="maxWidth" alt="Active/passive deployment" />

Active/passive deployment

The diagram does not show the shared file system where the user home directories are located.

The diagram does not show any unproxied connections or connections through HTTP proxy servers from the primary active {{< SecureTransport/componentshortname  >}} Server or the secondary passive {{< SecureTransport/componentshortname  >}} Server to the partner servers. For an illustrations of such a connection and more detail about connections in a streaming deployment, see [Streaming deployment](#Streamin).

To handle your file transfer load or to provide redundancy in case of failure, you can deploy more than one {{< SecureTransport/componentshortname  >}} Edge servers in the DMZ. Because {{< SecureTransport/componentshortname  >}} Edge servers do not create and handle events, they are not clustered, but they can be configured to synchronize configuration changes. For more information, see [SecureTransport Edge synchronization](../../../c_st_edge_sync#Edge). For a deployment diagram showing multiple {{< SecureTransport/componentshortname  >}} Edge server, see [Enterprise Cluster deployment](../../../c_st_largeenterpriseclustering/c_st_largeenterpriseclustermodel/c_st_large_enterprise_cluster_deployment).

<span id="Primary"></span>

## Primary server processes

The primary server hosts the following:

-   The Folder Monitor service
-   A consolidated transfer log for the cluster, displayed on the Administration Tool *File Tracking* page
-   The scheduler that initiates scheduled transfers and maintenance applications  
    The scheduler submits items to the internal event queue. The event queue distributes them among servers in the cluster.

<span id="Failover"></span>

## Failover

When a server in an active/active cluster fails, two events occur. First, any internal load balancer for the cluster detects the server outage and fails over incoming requests to another server and all protocols servers on {{< SecureTransport/componentshortname  >}} Edge servers detect the server outage and begin sending incoming requests to the TM Servers on the other {{< SecureTransport/componentshortname  >}} Servers. In this case, the original client sessions are terminated and the clients must reestablish the sessions. Second, items in the event queue are reassigned from the failed server to other servers in the cluster.

When the primary server fails, one of the secondary servers is promoted to primary and the cluster continues processing messages. The secondary server promoted to primary status is determined by the order in which the server names are listed in the `<FILEDRIVEHOME>/lib/admin/config/servers` configuration file. The server listed just below the primary server in the file is considered the new primary server. When the cluster is synchronized, the state of the servers listed in the file are examined. If the first server in the servers list is online, it is reassigned as the new primary.

You can specify a timeout value that controls how long a secondary server waits before becoming the primary. For details, see [Specify the cluster connection timeout](../../c_st_standardclusterconfiguration/t_st_specify_cluster_connection_timeout).

When a secondary server is promoted to primary, it must run the scheduler and the Folder Monitor service. To enable this, the scheduler configuration on the primary server is replicated on all the other computers in the cluster.

When the active (primary) server fails in an active/passive cluster with cluster mode `passive`, the scheduler and the Folder Monitor service are already running on the passive standby server and failover is automatic. As with an active/active cluster, when the original active node recovers and the cluster is synchronized, the servers return to their original roles.

When the active (primary) server fails in an active/passive cluster with cluster mode `passive_legacy`, you must fail over the cluster to the standby server manually. All queued events and Sentinel link data are lost. For details, see [Manual failover](../../c_st_managestandardcluster/t_st_manage_active-passive_cluster#Manual).

<span id="Synchron"></span>

## Synchronization

You can configure the cluster on any server. Most configuration changes are dynamically synchronized with the other servers immediately.

You must use the Administration Tool on the primary server to perform manual synchronization after you perform certain actions. Manual synchronization replaces the cluster configuration on the secondary servers with the configuration from the primary server. Data replicated during synchronization includes database tables, cluster configuration data, and cluster management data. The Administration Tool server also performs manual synchronization each time it starts on the primary server. For more details, see [Standard Cluster synchronization](../../c_st_managestandardcluster/c_st_standard_cluster_synchronization).

**Related topics:**

-   [Scheduled tasks](../c_st_scheduled_tasks)
-   [Consolidated log data representation](../c_st_consolidated_log_data_representation)
-   [Services used for cluster management](../c_st_services_used_for_cluster_management)
