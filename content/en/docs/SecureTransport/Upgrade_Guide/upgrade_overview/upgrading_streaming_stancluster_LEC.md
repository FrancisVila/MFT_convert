{
    "title": "Upgrade in Streaming, Standard Cluster, and Enterprise Cluster environments",
    "linkTitle": "Upgrade in Streaming, Standard Cluster, and Enterprise Cluster environments",
    "weight": "100"
}This section describes the options for upgrading in Streaming, Standard Cluster, and Enterprise Cluster (EC) environments.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top"> If you are using an external database, it must be upgraded to a <a href="https://docs.axway.com/bundle/SecureTransport_55_AdministratorGuide_allOS_en_HTML5/page/Content/AdministratorsGuide/introduction/r_st_Axway_and_third-party_software_support.htm#Database">supported version</a>  before upgrading <span>SecureTransport</span> to version <span>5.5</span> or a new instance of the respective database should be deployed and you should migrate the existing <span>SecureTransport</span> data to the new instance.          </td>
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
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">On upgrade from an older SecureTransport version with SQL Server edition different than Enterprise to 5.5, the database partitioning feature will not be used by <span>SecureTransport</span>.         </td>
      </tr>
</table>

## Streaming

In a streaming environment, stop all of the protocol servers and services on all of the SecureTransport Edges before you start upgrading. Update the SecureTransport Server (backend) first and then update the SecureTransport Edges. Once the upgrades are completed, restart all servers and edges.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Verify that an edge and server on different versions are never started together.         </td>
      </tr>
</table>

## Standard Cluster

In a Standard Cluster environment, stop all of the protocol servers and services on all of the nodes before you start updating.

For Standard Clusters the following two options for upgrade are supported:

-   Option 1 (recommended)
    -   Stop the nodes and upgrade the nodes one at a time. After a node is upgraded, stop all SecureTransport services on the node and proceed with the upgrade of the next node in the cluster. Start all SecureTransport services only after the upgrade is applied on all the nodes in the cluster.
    -   After all node upgrades are finished, do a manual sync. Only after you have completed a manual sync will you have functional and operating cluster.
-   Option 2:
    -   Dis-join the cluster before the upgrade by changing the cluster mode and deleting the node entries in the servers file. For details, refer to the *Remove a server from an active/active cluster* section in the <span cshid="admin" data-version="5.3.5">*SecureTransport Administrator's Guide*</span>.
    -   Then upgrade all the nodes as standalone installations.
    -   Once the upgrades are completed, join the cluster back together and do a manual sync. The cluster is considered upgraded and running only after the successful manual sync. For details, refer to the *Remove a server from an active/active cluster* section in the <span cshid="admin" data-version="5.3.5">*SecureTransport Administrator's Guide*</span>.

## Enterprise Cluster

The upgrade of an Enterprise Cluster (EC) consists of upgrading the nodes.

The following Enterprise Cluster upgrade option is supported:

-   Stop the nodes and upgrade the nodes one at a time. After a node is upgraded, stop all SecureTransport services on the node and proceed with the upgrade of the next node in the cluster. Start all SecureTransport services only after the upgrade is applied on all the nodes in the cluster.
