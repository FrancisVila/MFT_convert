{
    "title": "View cluster status",
    "linkTitle": "View cluster status",
    "weight": "180"
}Use the following procedure to view the cluster status.

1.  Select **Operations > Cluster Management.**  
    The *Cluster Management* page is displayed.
2.  In the **Servers** table, check the **Status** column.
    -   **Online** – The {{< SecureTransport/componentshortname >}} Server is reachable and both the TM and Administration Tool server are running.
    -   **Offline** – Either the {{< SecureTransport/componentshortname >}} Server is not reachable, the Transaction Manager is not running, or the Administration Tool server is not running.

{{< SecureTransport/componentshortname  >}} makes an entry in the server log when a server in the cluster goes offline.

To refresh the **Status** column, select **Operations &gt; Cluster Management**.

If the status of a {{< SecureTransport/componentshortname  >}} Server is Offline, you can check its status in more detail.

-   Log in to the server using the Administration Tool, select **Operations > Server Control**, and make sure that the TM Server is running.
-   If you cannot connect to the server using the Administration Tool, log in to the computer that hosts the server and make sure that the {{< SecureTransport/componentshortname >}} Administration Tool and TM server are running.

> **Note:**
>
> If a SecureTransport Server fails, the distributed event manager assigns pending events to other servers, but user sessions connected to the failed server are closed. However, Axway Secure Client automatically reestablishes the closed session and resumes any transfers.

**Related topics:**

-   <a href="../c_st_cluster_prerequisites" class="MCXref xref">Enterprise Cluster prerequisites</a>
-   <a href="../t_st_setup_cluster" class="MCXref xref">Set up a cluster</a>
-   <a href="../t_st_add_server_to_cluster" class="MCXref xref">Add a server to a cluster</a>
-   <a href="../t_st_remove_server_from_cluster" class="MCXref xref">Remove a server from a cluster</a>
-   <a href="../t_st_notification_of_cluster_status" class="MCXref xref">Notification of cluster status</a>
-   <a href="../t_st_setup_disaster_recovery_cluster" class="MCXref xref">Set up a disaster recovery cluster</a>
-   <a href="../t_st_maintain_disaster_recovery_cluster" class="MCXref xref">Maintain a disaster recovery cluster</a>
-   <a href="../t_st_dr_failover_fallback" class="MCXref xref">Disaster recovery failover and fallback</a>
-   <a href="../t_st_direct_cluster_workload" class="MCXref xref">Direct cluster workload</a>
