{
    "title": "Manage an active/passive cluster",
    "linkTitle": "Manage an active/passive cluster",
    "weight": "140"
}The following procedures describe how to perform management tasks for an active/passive cluster setup.

> **Note:**
>
> A cluster with cluster mode passive\_legacy does not monitor the state of each server in the cluster. However, if you attempt to synchronize all the servers in the cluster, and no errors occur, it indicates that both servers in the cluster are up.

> **Note:**
>
> Caution  
> In an active/passive cluster, the secondary server cannot be bounced remotely.

The following topics provide how-to instructions for managing an active/passive cluster:

-   [Restore a server to an active/passive cluster](#Restore)
-   [Remove a server from an active/passive cluster](#Remove)
-   [Manual failover](#Manual)

<span id="Restore"></span>

## Restore a server to an active/passive cluster

1.  Start the Administration Tool server and the TM server on the restored computer.
2.  On the primary server, perform a manual synchronization from the Administration Tool. For instructions, see [Synchronize the cluster from the primary server](../c_st_standard_cluster_synchronization#Synchron).

> **Note:**
>
> It is recommended that you synchronize the restored computer as soon as possible. If the restored computer becomes primary before it is synchronized, it might process messages based on outdated data it received before it failed.

<span id="Remove"></span>

## Remove a server from an active/passive cluster

When you remove a server from an active/passive cluster, the result is two stand-alone servers.

1.  Stop the TM server on both servers in the cluster.
2.  On each servers, open the `<FILEDRIVEHOME>/lib/admin/config/servers` file and remove the lines of information about the servers in the cluster.
3.  On each server, set `Cluster.mode` to `disabled`.
4.  If the cluster mode was `passive_legacy`, on the previous standby server, set `FolderMonitor.enable` and `Scheduler.enable` to `true`.
5.  Restart the TM server on both servers.

<span id="Manual"></span>

## Manual failover

When the primary server fails in an active/passive cluster with cluster mode set to `passive_legacy`, you must perform a manual failover on the passive standby server:

1.  Create a file named `<FILEDRIVEHOME>/var/tmp/sentinel_primary`.  
    To create the file, you can use the `touch` command in UNIX or create an empty file with no file extension in Windows. The file must have 0 bytes.
2.  On the *Server Configuration* page, set both `FolderMonitor.enable` and `Scheduler.enable` to `true`.
3.  On the *Server Control* page, start the TM Server.

 

**Related topics:**

-   [Manage an active/active cluster](../t_st_manage_active-active_cluster)
-   [Standard Cluster synchronization](../c_st_standard_cluster_synchronization)
