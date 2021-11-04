{
    "title": "Scheduled tasks",
    "linkTitle": "Scheduled tasks",
    "weight": "120"
}In an active/active cluster, the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> scheduler manages all scheduled tasks centrally from the primary server in the cluster. When schedules trigger events for scheduled tasks, one consolidated queue for all events is maintained across the cluster. This queue is shared and replicated across all the servers in the cluster so that they share the load by taking events one item at a time from the queue and performing the actual transfers or other tasks. If the primary server fails, the scheduler start on the server that becomes the new primary server.

In an active/passive cluster, the secondary standby server does not process events. If the server mode is `passive`, the standby server starts the scheduler and starts processing events when the primary server fails.

**Related topics:**

-   <a href="../c_st_active-active_active-passive_clustering" class="MCXref xref">Active/active and active/passive clustering</a>
-   <a href="../c_st_consolidated_log_data_representation" class="MCXref xref">Consolidated log data representation</a>
-   <a href="../c_st_services_used_for_cluster_management" class="MCXref xref">Services used for cluster management</a>
