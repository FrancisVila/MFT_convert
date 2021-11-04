{
    "title": "Services used for cluster management",
    "linkTitle": "Services used for cluster management",
    "weight": "140"
}<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> implements the following services to manage and synchronize the cluster and the computers deployed in it.

The following topics describe the services used for cluster management:

-   <a href="#Persistent" class="MCXref xref">Persistent Event Queue service</a>
-   <a href="#Account" class="MCXref xref">Account Manager service</a>
-   <a href="#Transfer" class="MCXref xref">Transfer Status Manager service</a>

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

-   <a href="../c_st_active-active_active-passive_clustering" class="MCXref xref">Active/active and active/passive clustering</a>
-   <a href="../c_st_scheduled_tasks" class="MCXref xref">Scheduled tasks</a>
-   <a href="../c_st_consolidated_log_data_representation" class="MCXref xref">Consolidated log data representation</a>
