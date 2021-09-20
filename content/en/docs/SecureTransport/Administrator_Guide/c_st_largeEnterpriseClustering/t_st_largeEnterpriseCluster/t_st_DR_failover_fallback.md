{
    "title": "Disaster recovery failover and fallback",
    "linkTitle": "Disaster recovery failover and fallback",
    "weight": "230"
}You can use cluster status notification to decide when you must fail over to the disaster recovery site. See [Notification of cluster status](../t_st_notification_of_cluster_status).

When the production site is unable to process file transfers, failover to the disaster recovery site:

1.  If possible, make sure that the disaster recovery site configuration and data is consistent with the production site.
2.  On every SecureTransport Server and SecureTransport Edge in the production site, use the
    `<FILEDRIVEHOME>/bin/stop_all` (or, on Windows, `<FILEDRIVEHOME>\bin\stop_all.com`)
    command to stop all SecureTransport processes.
3.  On every SecureTransport Server and SecureTransport Edge in the DR site, use the
    `<FILEDRIVEHOME>/bin/start_all` (or, on Windows, `<FILEDRIVEHOME>\bin\start_all.com`)
    command to start all SecureTransport processes.
4.  Make any changes to your load balancers or other network infrastructure to direct your SecureTransport
    traffic to the disaster recovery site.

When the production site is able to process file transfers, failback:

1.  If possible, make sure that any configuration changes made on the DR site are transferred to the
    production site and make sure that production data is consistent with the disaster recovery site.
2.  On every SecureTransport Server and SecureTransport Edge in the production site, use the
    `<FILEDRIVEHOME>/bin/start_all` (or, on Windows, `<FILEDRIVEHOME>\bin\start_all.com`)
    command to start all SecureTransport processes.
3.  On every SecureTransport Server and SecureTransport Edge in the DR site, use the
    `<FILEDRIVEHOME>/bin/stop_all` (or, on Windows, `<FILEDRIVEHOME>\bin\stop_all.com`)
    command to stop all SecureTransport processes.
4.  Make any changes to your load balancers or other network infrastructure to direct your SecureTransport
    traffic to the production site.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The time needed to perform a switch to the DR site can be estimated by assessing the time consumed for each of the following stages: stop and start ST services, perform the manual steps and maintain the data integrity. However, the time needed to keep the data integral is dependent on multiple factors, such as the chosen solution for database and filesystem synchronization, deployment specifics, connectivity, amount of data to transfer, distance between remote locations, etc.         </td>
      </tr>
</table>

**Related topics:**

-   [Enterprise Cluster prerequisites](../c_st_cluster_prerequisites)
-   [Set up a cluster](../t_st_setup_cluster)
-   [Add a server to a cluster](../t_st_add_server_to_cluster)
-   [Remove a server from a cluster](../t_st_remove_server_from_cluster)
-   [View cluster status](../t_st_view_cluster_status)
-   [Notification of cluster status](../t_st_notification_of_cluster_status)
-   [Set up a disaster recovery cluster](../t_st_setup_disaster_recovery_cluster)
-   [Maintain a disaster recovery cluster](../t_st_maintain_disaster_recovery_cluster)
-   [Direct cluster workload](../t_st_direct_cluster_workload)
