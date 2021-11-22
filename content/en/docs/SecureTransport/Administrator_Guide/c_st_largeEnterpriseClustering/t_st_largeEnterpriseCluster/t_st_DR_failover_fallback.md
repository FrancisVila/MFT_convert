{
    "title": "Disaster recovery failover and fallback",
    "linkTitle": "Disaster recovery failover and fallback",
    "weight": "220"
}You can use cluster status notification to decide when you must fail over to the disaster recovery site. See <a href="../t_st_notification_of_cluster_status" class="MCXref xref">Notification of cluster status</a>.

When the production site is unable to process file transfers, failover to the disaster recovery site:

1.  If possible, make sure that the disaster recovery site configuration and data is consistent with the production site.
2.  On every {{< SecureTransport/componentshortname >}} Server and {{< SecureTransport/componentshortname >}} Edge in the production site, use the
    `<FILEDRIVEHOME>/bin/stop_all` (or, on Windows, `<FILEDRIVEHOME>\bin\stop_all.com`)
    command to stop all {{< SecureTransport/componentshortname >}} processes.
3.  On every {{< SecureTransport/componentshortname >}} Server and {{< SecureTransport/componentshortname >}} Edge in the DR site, use the
    `<FILEDRIVEHOME>/bin/start_all` (or, on Windows, `<FILEDRIVEHOME>\bin\start_all.com`)
    command to start all {{< SecureTransport/componentshortname >}} processes.
4.  Make any changes to your load balancers or other network infrastructure to direct your {{< SecureTransport/componentshortname >}}
    traffic to the disaster recovery site.

When the production site is able to process file transfers, failback:

1.  If possible, make sure that any configuration changes made on the DR site are transferred to the
    production site and make sure that production data is consistent with the disaster recovery site.
2.  On every {{< SecureTransport/componentshortname >}} Server and {{< SecureTransport/componentshortname >}} Edge in the production site, use the
    `<FILEDRIVEHOME>/bin/start_all` (or, on Windows, `<FILEDRIVEHOME>\bin\start_all.com`)
    command to start all {{< SecureTransport/componentshortname >}} processes.
3.  On every {{< SecureTransport/componentshortname >}} Server and {{< SecureTransport/componentshortname >}} Edge in the DR site, use the
    `<FILEDRIVEHOME>/bin/stop_all` (or, on Windows, `<FILEDRIVEHOME>\bin\stop_all.com`)
    command to stop all {{< SecureTransport/componentshortname >}} processes.
4.  Make any changes to your load balancers or other network infrastructure to direct your {{< SecureTransport/componentshortname >}}
    traffic to the production site.

> **Note:**
>
> The time needed to perform a switch to the DR site can be estimated by assessing the time consumed for each of the following stages: stop and start ST services, perform the manual steps and maintain the data integrity. However, the time needed to keep the data integral is dependent on multiple factors, such as the chosen solution for database and filesystem synchronization, deployment specifics, connectivity, amount of data to transfer, distance between remote locations, etc.

**Related topics:**

-   <a href="../c_st_cluster_prerequisites" class="MCXref xref">Enterprise Cluster prerequisites</a>
-   <a href="../t_st_setup_cluster" class="MCXref xref">Set up a cluster</a>
-   <a href="../t_st_add_server_to_cluster" class="MCXref xref">Add a server to a cluster</a>
-   <a href="../t_st_remove_server_from_cluster" class="MCXref xref">Remove a server from a cluster</a>
-   <a href="../t_st_view_cluster_status" class="MCXref xref">View cluster status</a>
-   <a href="../t_st_notification_of_cluster_status" class="MCXref xref">Notification of cluster status</a>
-   <a href="../t_st_setup_disaster_recovery_cluster" class="MCXref xref">Set up a disaster recovery cluster</a>
-   <a href="../t_st_maintain_disaster_recovery_cluster" class="MCXref xref">Maintain a disaster recovery cluster</a>
-   <a href="../t_st_direct_cluster_workload" class="MCXref xref">Direct cluster workload</a>
