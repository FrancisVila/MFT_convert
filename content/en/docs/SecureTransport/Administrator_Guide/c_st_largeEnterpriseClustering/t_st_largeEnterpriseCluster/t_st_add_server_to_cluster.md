{
    "title": "Add a server to a cluster",
    "linkTitle": "Add a server to a cluster",
    "weight": "160"
}If a {{< SecureTransport/componentshortname  >}} Server uses the cluster shared database schema and shared file system, you can add it to the cluster using the Administration Tool. To connect a {{< SecureTransport/componentshortname  >}} Server to an existing database schema, see [Migrate from embedded database to external Oracle database](../../../c_st_setup/c_st_database/t_st_database#top) or [Change the Oracle database configuration](../../../c_st_setup/c_st_database/t_st_oracle#top).

To use IPv6 addresses for communication between servers in an Enterprise Cluster (EC), you must edit the `<FILEDRIVEHOME>/conf/tangosol-coherence-override.xml` file on each server and set the value of the `<address>` element to the IPv6 address of the network interface used for cluster communications. The first lines of the `<cluster-config>` element must be:


    <cluster-config>
        <unicast-listener>
                  <address>IPv6-address</address>

1.  Make sure that the Administration Tool service and the Transaction Manager server are not running on the {{< SecureTransport/componentshortname >}} Server that you are adding to the cluster.

2.  Select **Operations > Cluster Management**.  
    The *Cluster Management* page is displayed.

3.  Type either the IP address or the FQDN of the {{< SecureTransport/componentshortname >}} Server to add to the cluster in the **Server Address** field in the **Servers** table.

4.  Click **Add Server**.  

    > **Note:**
    >
    > The Administration Tool does not prevent you from adding the same IP address to the cluster more than one, but this is not a valid operation and the additional entries do not add servers to the cluster.

5.  Start the Administration Tool service on the added {{< SecureTransport/componentshortname >}} Server. Log on to the Administration Tool and start the TM server and required protocol servers. The feature license defines the maximum number of nodes in an EC. If you attempt to start a TM that exceeds the maximum number of nodes defined in the feature license, the TM will not start or process tasks.

> **Note:**
>
> The Administration Tool service must run on all servers in the cluster whether or not you are accessing them using the Administration Tool.

**Related topics:**

-   [Enterprise Cluster prerequisites](../c_st_cluster_prerequisites)
-   [Set up a cluster](../t_st_setup_cluster)
-   [Remove a server from a cluster](../t_st_remove_server_from_cluster)
-   [View cluster status](../t_st_view_cluster_status)
-   [Notification of cluster status](../t_st_notification_of_cluster_status)
-   [Set up a disaster recovery cluster](../t_st_setup_disaster_recovery_cluster)
-   [Maintain a disaster recovery cluster](../t_st_maintain_disaster_recovery_cluster)
-   [Disaster recovery failover and fallback](../t_st_dr_failover_fallback)
-   [Direct cluster workload](../t_st_direct_cluster_workload)
