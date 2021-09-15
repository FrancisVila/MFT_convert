{
    "title": "View cluster status",
    "linkTitle": "View cluster status",
    "weight": "190"
}Use the following procedure to view the cluster status.

1.  Select **Operations > Cluster Management.**  
    The *Cluster Management* page is displayed.
2.  In the **Servers** table, check the **Status** column.
    -   **Online** – The SecureTransport Server is reachable and both the TM and Administration Tool server are running.
    -   **Offline** – Either the SecureTransport Server is not reachable, the Transaction Manager is not running, or the Administration Tool server is not running.

SecureTransport makes an entry in the server log when a server in the cluster goes offline.

To refresh the **Status** column, select **Operations &gt; Cluster Management**.

If the status of a SecureTransport Server is Offline, you can check its status in more detail.

-   Log in to the server using the Administration Tool, select **Operations > Server Control**, and make sure that the TM Server is running.
-   If you cannot connect to the server using the Administration Tool, log in to the computer that hosts the server and make sure that the SecureTransport Administration Tool and TM server are running.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">If a <span>SecureTransport</span> Server fails, the distributed event manager assigns pending events to other servers, but user sessions connected to the failed server are closed. However, <span>Axway</span> Secure Client automatically reestablishes the closed session and resumes any transfers.         </td>
      </tr>
</table>

**Related topics:**

-   [Enterprise Cluster prerequisites](../c_st_cluster_prerequisites)
-   [Set up a cluster](../t_st_setup_cluster)
-   [Add a server to a cluster](../t_st_add_server_to_cluster)
-   [Remove a server from a cluster](../t_st_remove_server_from_cluster)
-   [Notification of cluster status](../t_st_notification_of_cluster_status)
-   [Set up a disaster recovery cluster](../t_st_setup_disaster_recovery_cluster)
-   [Maintain a disaster recovery cluster](../t_st_maintain_disaster_recovery_cluster)
-   [Disaster recovery failover and fallback](../t_st_dr_failover_fallback)
-   [Direct cluster workload](../t_st_direct_cluster_workload)
