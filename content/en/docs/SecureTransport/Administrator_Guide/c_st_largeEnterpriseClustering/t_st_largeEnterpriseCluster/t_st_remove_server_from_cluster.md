{
    "title": "Remove a server from a cluster",
    "linkTitle": "Remove a server from a cluster",
    "weight": "180"
}You can remove a SecureTransport Server from the cluster.

1.  Select **Operations > Cluster Management**.  
    The *Cluster Management* page is displayed.
2.  In the **Servers** table, select the servers to remove from the cluster.
3.  Click **Remove Server**.  
    The lines for the servers are removed to the **Servers** table and the servers are no longer part of the cluster.
4.  Stop all SecureTransport servers and services on the removed systems.

The local server configuration setting for the removed server remains in the shared database.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">To avoid problems with the shared database, do not start any <span>SecureTransport</span> servers or services on the removed systems unless and until you add them back to the same cluster.         </td>
      </tr>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">If a node is removed from the cluster and added back to the cluster after any demon configuration change was made, the private zone of the secondary node will not be updated to reflect the change. You will need to manually apply the changes by updating the <em>Server Control</em> page of the added node and restarting the changed daemons and Transaction Manager.         </td>
      </tr>
</table>

**Related topics:**

-   [Enterprise Cluster prerequisites](../c_st_cluster_prerequisites)
-   [Set up a cluster](../t_st_setup_cluster)
-   [Add a server to a cluster](../t_st_add_server_to_cluster)
-   [View cluster status](../t_st_view_cluster_status)
-   [Notification of cluster status](../t_st_notification_of_cluster_status)
-   [Set up a disaster recovery cluster](../t_st_setup_disaster_recovery_cluster)
-   [Maintain a disaster recovery cluster](../t_st_maintain_disaster_recovery_cluster)
-   [Disaster recovery failover and fallback](../t_st_dr_failover_fallback)
-   [Direct cluster workload](../t_st_direct_cluster_workload)
