{
    "title": "Upgrade in Streaming, Standard Cluster, and Enterprise Cluster environments",
    "linkTitle": "Upgrade in Streaming, Standard Cluster, and Enterprise Cluster environments",
    "weight": "100"
}This section describes the options for upgrading in Streaming, Standard Cluster, and Enterprise Cluster (EC) environments.

> **Note:**
>
> If you are using an external database, it must be upgraded to a supported version before upgrading SecureTransport to version 5.5 or a new instance of the respective database should be deployed and you should migrate the existing SecureTransport data to the new instance.

> **Note:**
>
> On upgrade from an older SecureTransport version with SQL Server edition different than Enterprise to 5.5, the database partitioning feature will not be used by SecureTransport.

## Streaming

In a streaming environment, stop all of the protocol servers and services on all of the SecureTransport Edges before you start upgrading. Update the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server (backend) first and then update the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edges. Once the upgrades are completed, restart all servers and edges.

> **Note:**
>
> Verify that an edge and server on different versions are never started together.

## Standard Cluster

In a Standard Cluster environment, stop all of the protocol servers and services on all of the nodes before you start updating.

For Standard Clusters the following two options for upgrade are supported:

-   Option 1 (recommended)
    -   Stop the nodes and upgrade the nodes one at a time. After a node is upgraded, stop all <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> services on the node and proceed with the upgrade of the next node in the cluster. Start all <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> services only after the upgrade is applied on all the nodes in the cluster.
    -   After all node upgrades are finished, do a manual sync. Only after you have completed a manual sync will you have functional and operating cluster.
-   Option 2:
    -   Dis-join the cluster before the upgrade by changing the cluster mode and deleting the node entries in the servers file. For details, refer to the *Remove a server from an active/active cluster* section in the <span class="redirect_st_ag" cshid="admin" data-version="5.3.5">*<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Administrator's Guide*</span>.
    -   Then upgrade all the nodes as standalone installations.
    -   Once the upgrades are completed, join the cluster back together and do a manual sync. The cluster is considered upgraded and running only after the successful manual sync. For details, refer to the *Remove a server from an active/active cluster* section in the <span class="redirect_st_ag" cshid="admin" data-version="5.3.5">*<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Administrator's Guide*</span>.

## Enterprise Cluster

The upgrade of an Enterprise Cluster (EC) consists of upgrading the nodes.

The following Enterprise Cluster upgrade option is supported:

-   Stop the nodes and upgrade the nodes one at a time. After a node is upgraded, stop all SecureTransport services on the node and proceed with the upgrade of the next node in the cluster. Start all SecureTransport services only after the upgrade is applied on all the nodes in the cluster.
