{
    "title": "Manage an active/active cluster",
    "linkTitle": "Manage an active/active cluster",
    "weight": "130"
}The following procedures describe how to perform management tasks for an active/active cluster setup.

The following topic provide the how-to instructions for managing an active/active cluster:

-   [Monitor an active/active cluster](#Monitor)
-   [Add a server to an active/active cluster](#Add)
-   [Restore a server to an active/active cluster](#Restore)
-   [Remove a server from an active/active cluster](#Remove)

**Related topics:**

-   [Manage an active/passive cluster](../t_st_manage_active-passive_cluster)
-   [Standard Cluster synchronization](../c_st_standard_cluster_synchronization)

<span id="Monitor"></span>

## Monitor an active/active cluster

Cluster status is displayed in the Administration Tool.

-   Select **Operations > Cluster Management**.  
    The *Cluster Management* page is displayed.

For each Server in the cluster, the page lists its status (online or offline), its type (primary or secondary), and its host name or IP address. Online status means the server is running and communicating with the cluster. Offline status means the server has been stopped, has failed, or cannot communicate with the cluster.

The **Bounce**, **Bounce All**, and **Synchronize All** buttons do not appear on secondary servers. To bounce a secondary server locally, see [Reload server configuration](#Reload).

On a secondary server, the time of the last manual synchronization is reported. The timestamp is also reported in the `cluster_last_sync_timestamp` file located in the `<FILEDRIVEHOME>/var/tmp/cluster_last_sync_timestamp` directory.

Cluster status is also stored in the `cluster_state` file. It contains information about which cluster node is the primary server, which are secondary servers, which servers are online, and which are offline. For example:


    <ClusterGroup name="STCluster">
       <Member hostname="test01.your.cluster" state="online" 
          status="primary"/>
       <Member hostname="test02.your.cluster" state="online" 
          status="secondary"/>
       <Member hostname="test03.your.cluster" state="offline" 
          status="secondary"/>
    </ClusterGroup>

By default, the `cluster_state` file is located in `<FILEDRIVEHOME>/var/tmp/cluster_state`. You can change the location and file name by editing the following server configuration parameters:

-   `Cluster.File.clusterStateFile.relative` – the base location (`fdhome` for `<FILEDRIVEHOME>)`
-   `Cluster.File.clusterStateFile.path` – the path and file name relative to `Cluster.File.clusterStateFile.relative`

<span id="Add"></span>

## Add a server to an active/active cluster

1.  Stop the TM server on all servers in the cluster.
2.  Add the information about the new server into the `<FILEDRIVEHOME>/lib/admin/config/servers` file on the primary server.
3.  Copy the `servers` file to the new computer.
4.  Follow steps 11 through 15 from [Set up an active/active cluster](../../c_st_standardclusterconfiguration/t_st_setup_active-active_cluster#Standard_Clustering_3967700027_1029540).

> **Note:**
>
> The new server must use the same secret file as the rest of the nodes in the cluster.

<span id="Restore"></span>

## Restore a server to an active/active cluster

1.  Start the Administration Tool and TM server on the restored server.
2.  Perform a manual synchronization from the Administration Tool of the primary server. For instructions, see [Synchronize the cluster from the primary server](../c_st_standard_cluster_synchronization#Synchron).

> **Note:**
>
> Synchronize the restored server as soon as possible. If the restored server becomes primary before it is synchronized, it might process messages based on outdated data it received before it failed.

<span id="Remove"></span>

## Remove a server from an active/active cluster

When you remove a server from an active/active cluster, you can configure it as a stand-alone server.

1.  On each of the nodes in t he cluster, stop the TM server.
2.  On the node you are removing from the cluster:
    1.  Open the `<FILEDRIVEHOME>/lib/admin/config/servers` file and remove the lines of information about the servers in the cluster.
    2.  On the *Server Configuration* page, set the `Cluster.mode` parameter to `disabled`.
3.  On each of the remaining nodes in the cluster, open the `<FILEDRIVEHOME>/lib/admin/config/servers` file and remove the line of information about the server you are removing from the cluster.
4.  On each of the remaining nodes in the cluster, start the TM server.
5.  On the primary server, perform a manual synchronization from the Administration Tool. For instructions, see [Synchronize the cluster from the primary server](../c_st_standard_cluster_synchronization#Synchron).
