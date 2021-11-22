{
    "title": "Edge installation with Embedded Database",
    "linkTitle": "Edge installation with embedded database",
    "weight": "180"
}This topic provides instructions for migrating {{< SecureTransport/componentshortname  >}}{{< SecureTransport/componentversion  >}} Edge with embedded database on Windows Server 2012 R2 R2 deployment to Windows Server 2016 or Windows Server 2019.

The migration procedure requires you to form a synchronized cluster of Edges with your new SecureTransport Edge deployment (on Windows Server 2016 or Windows Server 2019) and the original one (on Windows Server 2019) and take advantage of the cluster capability to sync global configurations and accounts across nodes.

> **Note:**
>
> The migration procedure to Windows Server 2016 is the same as that to Windows Server 2019. To avoid repetition, instructions herein will discuss migration steps to Windows Server 2016. You can follow these same steps when migrating to Windows Server 2019.

## Prerequisites

-   Back up your existing {{< SecureTransport/componentshortname >}} installation. To back up your current {{< SecureTransport/componentshortname >}} deployment, follow a backup procedure applicable for your environment and make sure the backup is created at a time when all {{< SecureTransport/componentshortname >}} services are stopped.

> **Note:**
>
> Please keep in mind that migrating SecureTransport Edge to Windows Server 2016 will not migrate the Server and Audit log information. This information can be backed up prior to the migration.

## Migration procedure

Perform the below procedure for each of the {{< SecureTransport/componentshortname  >}} Edges when not in a synchronized cluster.

1.  Install a new {{< SecureTransport/componentshortname >}}{{< SecureTransport/componentversion >}} Edge (vanilla installation, no patches) on Windows Server 2016 using the `taeh` file from the one on Windows Server 2012 R2.
    -   Make sure that the host names and IP addresses of all servers are in the host files of all servers. Use the lookup command to verify that the host names of all servers resolve on all hosts.
    -   Select the computer that is to serve as the primary server. This must be the Windows Server 2012 R2 node from which the configuration is to be replicated.
2.  Make sure that the patch level of the new {{< SecureTransport/componentshortname >}} deployment (on Windows Server 2016) matches that of the original one (on Windows Server 2012 R2). For example, if the original deployment has Patch 22 installed, you must perform the necessary steps to upgrade the new vanilla {{< SecureTransport/componentshortname >}} installation to Patch 22 as well.
3.  Manually re-apply and reconfigure all previously applied customizations, for example:  
    -   plugins from the `…\STServer\plugins\` folder
    -   start/stop scripts
    -   configurations in `configuration.xml`
    -   configurations in `internaldb.conf`
    -   JVM heap size
    -   multi-protocol listeners
    -   all local server configurations (i.e. network zones, allowed {{< SecureTransport/componentshortname >}} Servers) and all Local Server configuration parameters in the {{< SecureTransport/componentshortname >}} Administration Tool: go to **Operation > Server Configuration** and select the **Local Parameters** checkbox on the new Windows Server 2016 node.
4.  Make sure you have a feature license that permits the necessary number of nodes for the migration procedure. In case your license does not allow you to add new machines to the existing environment, contact and request a temporary license. Do not forget to restart all services after the new license is applied.
5.  Follow the below steps of forming a Cluster between the {{< SecureTransport/componentshortname >}} Edge on Windows Server 2012 R2 and the one on Windows Server 2016.  
      
    **Prerequisites for Synchronization**
    -   The `<FILEDRIVEHOME>\lib\admin\config\servers` configuration file is correct and identical on all {{< SecureTransport/componentshortname >}} Edge servers.
    -   The `<FILEDRIVEHOME>\var\tmp\sentinel_primary` file exists on the primary {{< SecureTransport/componentshortname >}} Edge only.
    -   A shared common `taeh` file is used on all servers.
    -   Each server is hosted on a different computer or VM.
    -   All servers use the same installation path.
    -   All the servers are on the same LAN.
    -   The primary administrator user ID is the same on all servers and all have the same password.
    -   The clocks are set to the same time on all servers.
    -   The internal CAs on all servers is trusted by all other servers. You can import the same internal CA on all servers.
    -   All database settings must be identical on all edges.
    -   Only files used for server configuration are configured for synchronization.
    -   All the server certificates are issued by a common CA.

      
      
    **Cluster formation steps**
    1.  Exchange CA certificates between all servers.
    2.  On the primary and the secondary server, list all the servers in the `<FILEDRIVEHOME>\lib\admin\config\servers` configuration file. List the primary server first and continue with the secondary server.
    3.  On the primary server, create a file named `<FILEDRIVEHOME>\var\tmp\sentinel_primary`
    4.  Log out of the primary {{< SecureTransport/componentshortname >}} Edge server and log in again. Make sure that the server is identified as the primary server and that the **Synchronize All** and **Bounce All** buttons are displayed.
    5.  Synchronize the secondary server manually from the Administration Tool of the primary server.
6.  Manually verify that the data is successfully synced to the new node (parameters, administrators, certificates should be present on the new node).
7.  On both nodes comment the entries in the `servers` file located in `<FILEDRIVEHOME>\lib\admin\config\`
8.  On the primary node remove the previously created `sentinel_primary` file located in `<FILEDRIVEHOME>\var\tmp\`
9.  Power off the original node on Windows Server 2012 R2.
10. Change the IP address of the node on Windows Server 2016 to the IP address previously occupied by the node on Windows Server 2012 R2.
11. Re-add your existing (original) license if a temporary one was used and restart all services on the node on Windows Server 2016.

 

**Related Topics:**

-   <a href="../standalone-mysql" class="MCXref xref">Standalone installation with embedded database</a>
-   <a href="../standalone-ext-db" class="MCXref xref">Standalone with External Database</a>
-   <a href="../standard-cluster-mysql" class="MCXref xref">Standard Cluster environment with embedded database</a>
-   <a href="../lec-ext-db" class="MCXref xref">Enterprise Cluster environment with external database</a>
-   <a href="../edge-synced-mysql" class="MCXref xref">Edge installation with Embedded Database when part of a synchronized cluster</a>

 
