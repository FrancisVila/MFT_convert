{
    "title": "Zero downtime in active-passive deployment",
    "linkTitle": "Zero downtime in active-passive deployment",
    "weight": "160"
}Zero downtime is a concept that allows to smoothly redirect traffic from an active LEC cluster to a passive LEC cluster without experiencing interruptions in file transfers and event logging. This feature allows you to keep your ongoing transfers running while you prepare your initially active cluster for upgrades or maintenance.

The following diagram shows a simplified model of a setup that includes active Cluster (1) and passive Cluster (2). Initially, Cluster 1 handles all traffic from the load balancer while Cluster 2 is idle: there are no client connections and scheduled transfers are disabled.

![](lec-zero-downtime.png)

The process of zero downtime requires you to follow several steps to ensure best results.

## Prerequisites

To ensure zero downtime, the following prerequisites must be met:

-   The active and passive cluster must have identical configuration and deployment.
    -   both must use the same `taeh` file (used by each of the servers in the cluster for authentication and encryption purposes across servers)
    -   both must have the same system configurations and account schemas configured
-   The Load balancer balances traffic between the edges (SecureTransport nodes on Cluster 1) by hostname, resolved by internal DNS server (or hosts file on the Load Balancer host)
-   File storages on both clusters must be in constant sync and file contents must be identical and present at both clusters
-   The database replication requires that databases on both clusters contain a special set of tables. The following list of database tables contains the one that **must not be** synced.
    -   `AUDITLOG`
    -   `CLUSTERNODE`
    -   `DMZ_EDGE`
    -   `DMZ_EDGE_IP_ADDRESS`
    -   `DMZ_EDGE_PROTOCOL`
    -   `DMZ_EDGE_PROXY`
    -   `DMZ_ZONE`
    -   `EVENT`
    -   `HT_BUSINESSUNIT`
    -   `LOGGING_EVENT`
    -   `LOGGING_EVENT_EXCEPTION`
    -   `LOGGING_EVENT_EXCEPTION_TEMP`
    -   `LOGGING_EVENT_PROPERTY`
    -   `LOGGING_EVENT_PROPERTY_TEMP`
    -   `LOGGING_EVENT_TEMP`
    -   `SUBTRANSMISSIONSTATUS`
    -   `SUBTRANSMISSIONSTATUS_TEMP`
    -   `TRANSFERDATA`
    -   `TRANSFERDATA_TEMP`
    -   `TRANSFERDETAILS`
    -   `TRANSFERDETAILS_TEMP`
    -   `TRANSFERPROTOCOLCOMMANDS`
    -   `TRANSFERPROTOCOLCOMMANDS_TEMP`
    -   `TRANSFERRESUBMITDATA`
    -   `TRANSFERRESUBMITDATA_TEMP`

## Zero downtime execution steps

Several steps must be executed on the Cluster 1 and Cluster 2 in order to redirect seamlessly traffic redirection from Cluster 1 to Cluster 2:

1.  Stop Monitor Server on all SecureTransport Servers and Edges in Cluster 1 (and Cluster 2, if applicable).
2.  Stop all database replications across Clusters 1 and 2. Do not stop file system replications.
3.  Redirect the load balancer traffic from Cluster 1 to Cluster 2.
4.  On Cluster 1, stop the Scheduler and Folder Monitor on SecureTransport Servers.
5.  On Cluster 2, start the Scheduler and Folder Monitor on SecureTransport Servers.
6.  On Cluster 1, stop the protocol servers gracefully on all SecureTransport Servers and Edges. For more information, see [Graceful shutdown of protocol servers](../../../operations_menu/extended_server_control/graceful-shutdown).
7.  On Cluster 1, make sure all protocol servers (on all SecureTransport Servers and Edges) are stopped in order to proceed with stopping the Transaction Manager gracefully. For more information, see [Graceful shutdown of Transaction Manager](../../../operations_menu/extended_server_control/graceful-shutdown).
8.  Stop any remaining services on SecureTransport Servers and Edges in Cluster 1 – admin services, proxy services, etc. Use the `stop_all` console command: `<FILEDRIVEHOME>/bin/stop_all `(or, on Windows, `<FILEDRIVEHOME>\bin\stop_all.com`).

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">You can execute Steps 4, 6 and 7 on Cluster 1 <span>SecureTransport</span> Server nodes at once by shutting down gracefully each. For more information, see <a href="../../../operations_menu/extended_server_control/graceful-shutdown" xrefformat="{paratext}">Graceful shutdown of SecureTransport Server node</a>.         </td>
      </tr>
</table>

This is the list of basic steps your need to go through in order to gracefully shut down Cluster 1 after redirecting the load balancer traffic to Cluster 2. Once in downtime, Cluster 1 is ready for maintenance or upgrade procedures while Cluster 2 will be handling all requests and transfers. At some point Cluster 1 will be in passive mode while Cluster 2 will be the active one.

Once you decide to perform the reverse process: make Cluster 1 active and Cluster 2 passive again, follow the same steps as described above but perform each step on Cluster 2 instead of Cluster 1 and vice versa. This means that, for example, in step 2 you will switch load balancer traffic from Cluster 1 to Cluster 2 and apply steps 3 to 6 on Cluster 2.

## Known limitations

-   During the zero downtime process, no configuration changes must be performed since replications across clusters are disabled in Step 1.
-   After Step 2, the File tracking and Audit log on Cluster 1 will record only data for already initiated connections, events and transfers (on Cluster 1), plus respective post-processing info. events. All "new" traffic will go in Cluster 2, respectively all events will be logged in the File tracking and Audit log on Cluster 2. There is no replication of these logs across Cluster 1 and Cluster 2.