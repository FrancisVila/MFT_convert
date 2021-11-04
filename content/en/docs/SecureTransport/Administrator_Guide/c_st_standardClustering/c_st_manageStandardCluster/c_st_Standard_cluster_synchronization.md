{
    "title": "Standard Cluster synchronization",
    "linkTitle": "Standard cluster synchronization",
    "weight": "150"
}You can configure the cluster on any server. Most configuration changes are synchronized with the other servers immediately.

When needed, you must propagate configuration data from the primary server to secondary servers across a cluster through manual synchronization. Use the Administration Tool on the primary server to perform synchronization.

You must perform manual synchronization after you:

-   Upgrade <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>
-   Restart the whole cluster
-   Restore a failed primary server
-   Restart the Administration Tool server on a secondary server, if you made changes using the Administration Tool on the primary server while it was down

Manual synchronization replaces the information on the secondary servers with the configuration from the primary server. The Administration Tool server also performs dynamic synchronization each time it starts on the primary server.

You cannot use manual synchronization to data move information from the primary server to selected secondary servers.

A full synchronization may take a long time to complete and during the synchronization process, all dynamic updates are stopped, so make sure that you perform the synchronization when your system is not under heavy load.

When you create an application or account, or change the keystore password on the primary server, like most configuration information, the new application, account settings, or keystore password is copied to the secondary servers using dynamic synchronization when you save the settings. However, the audit log entry for the application, keystore password, or account creation is not copied from the primary to the secondary servers.

The directories for accounts that are synchronized manually use the UID and GID specified within the account settings on the secondary servers when the parent directory of the account exists only on the primary server in the cluster.

> **Note:**
>
> When synchronizing an application, an error message is returned indicating that the application was not copied if the secondary servers do not already have the application type the application is based on. Clicking the Synchronize button copies the application types from the primary server to the secondary servers, along with the application instances created.

Servers that are online, but not fully synchronized, are updated with new account and application information without having to perform a manual synchronization. You must still perform a full synchronization to start the TM server on a server that was previously down, even though the account and application information might be current.

The following topics describe the synchronization requirements and what information is synchronized and provide how-to instructions for synchronization:

-   <a href="#Requirem" class="MCXref xref">Requirements for synchronization</a>
-   <a href="#What" class="MCXref xref">What information is synchronized</a>
-   <a href="#Synchron" class="MCXref xref">Synchronize the cluster from the primary server</a>

**Related topics:**

-   <a href="../t_st_manage_active-active_cluster" class="MCXref xref">Manage an active/active cluster</a>
-   <a href="../t_st_manage_active-passive_cluster" class="MCXref xref">Manage an active/passive cluster</a>

<span id="Requirem"></span>

## Requirements for synchronization

Dynamic and manual cluster synchronization requires the following:

-   The <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> administrator account names must be the same on all servers.
-   When certificate authentication is enabled for the administrator accounts, Cluster.DynamicSync.adminName and Cluster.DynamicSync.keyAlias configuration options must be set on all nodes manually.
-   The <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> installation path must be the same on all servers.
-   The `taeh` file must be the same on all servers.
-   The certificate for encrypting cluster communications specified in the `Cluster.Crypto.Alias` server configuration parameter must be the same on all servers.
-   The internal CAs on all nodes must be trusted by all other nodes. Optionally, you can import the same internal CA on all nodes.
-   All the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> server certificates must be issued by a common CA.
-   Each server must be hosted on a different computer or virtual machine.
-   All the servers in an active/active cluster must be in the same LAN.
-   The two servers in an active/passive cluster with cluster mode `passive_legacy` can be in different locations, but they must be in the same low latency network.
-   All servers in a cluster must have their clocks set to the same time.
-   The TM Server must be running on all servers.
-   All database settings must be *identical* on all the servers.

<span id="What"></span>

## What information is synchronized

The following types of information are synchronized:

-   All configuration files listed in the `<FILEDRIVEHOME>/conf/sync.conf` file
-   All database tables listed in the `<FILEDRIVEHOME>/conf/sync_tables.conf` file
-   All server configuration parameters that are not local to the server

The files listed in `sync.excl` are not copied from the primary to the secondary server.

<span id="Synchron"></span>

## Synchronize the cluster from the primary server

Use the Administration Tool on the
primary server to synchronize the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> servers in a Standard Cluster.

> **Note:**
>
> The upper right corner of the Administration Tool shows whether the server on which it is running is a primary or secondary server.

1.  Select **Operations > Cluster Management**.  
    The *Cluster Management* page is displayed.
2.  Click **Synchronize All**.  
    When synchronization completes, the page displays the status of the operation and links to the secondary server Administration Tools.
