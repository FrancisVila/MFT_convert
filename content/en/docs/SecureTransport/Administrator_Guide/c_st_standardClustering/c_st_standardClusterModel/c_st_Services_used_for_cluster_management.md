{
    "title": "Services used for cluster management",
    "linkTitle": "Services used for cluster management",
    "weight": "140"
}{{< SecureTransport/componentshortname  >}} implements the following services to manage and synchronize the cluster and the computers deployed in it.

The following topics describe the services used for cluster management:

-   [Persistent Event Queue service](#Persistent)
-   [Account Manager service](#Account)
-   [Transfer Status Manager service](#Transfer)

<span id="Persistent"></span>

## Persistent Event Queue service

The Persistent Event Queue service is used to:

-   Store certain events and replicates them to all cluster servers
-   Synchronize the persistent events state to all cluster servers
-   Perform recovery operations when a computer from the cluster fails during the processing of an event
-   Spread the execution of following operations to all cluster servers:
    -   Add a new event to the persistent queue
    -   Delete an event from the persistent queue
    -   Mark an event as active
    -   Repair an event of a failed computer

> **Note:**
>
> The Event Queue service dispatches all events related to one remote PeSIT server to the same SecureTransport server in the cluster.

<span id="Account"></span>

## Account Manager service

The Account Manager distributes to all cluster servers dynamic information for the following events:

-   Change of a user password.
-   User login.

<span id="Transfer"></span>

## Transfer Status Manager service

The Transfer Status Manager service consolidates the transfer log on the primary server. All transfer log entries are stored in the database on the primary server.

**Related topics:**

-   [Active/active and active/passive clustering](../c_st_active-active_active-passive_clustering)
-   [Scheduled tasks](../c_st_scheduled_tasks)
-   [Consolidated log data representation](../c_st_consolidated_log_data_representation)
