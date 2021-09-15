{
    "title": "Consolidated log data representation",
    "linkTitle": "Consolidated log data representation",
    "weight": "140"
}The transfer log allows file tracking information to be monitored across the entire cluster. To this end, the Administration Tool on the primary server in the cluster provides a consolidated view of the transfer data stored in the server logs.

If the primary server goes down, a secondary server is promoted to primary and starts maintaining the transfer log information. If the old primary server comes back up again and resumes its role as primary server for the cluster, the transfer log information from the temporary primary server is not migrated to the original primary server.

**Related topics:**

-   [Active/active and active/passive clustering](../c_st_active-active_active-passive_clustering)
-   [Scheduled tasks](../c_st_scheduled_tasks)
-   [Services used for cluster management](../c_st_services_used_for_cluster_management)
