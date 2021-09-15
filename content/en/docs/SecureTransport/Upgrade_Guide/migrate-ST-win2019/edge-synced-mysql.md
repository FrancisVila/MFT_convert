{
    "title": "Edge installation with embedded database when part of a synchronized cluster",
    "linkTitle": "Edge installation with embedded database when part of a synchronized cluster",
    "weight": "190"
}This topic provides instructions for migrating SecureTransport 5.5 Edge on Windows Server 2012 R2 deployment (as part of a synchronized cluster) to Windows Server 2016 or Windows Server 2019.

The migration procedure requires you to add your new SecureTransport Edge deployment (on Windows Server 2016 or Windows Server 2019) to a synchronized cluster of Edges and take advantage of the cluster capability to sync global configurations and accounts across nodes.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The migration procedure to Windows Server 2016 is the same as that to Windows Server 2019. To avoid repetition, instructions herein will discuss migration steps to Windows Server 2016. You can follow these same steps when migrating to Windows Server 2019.         </td>
      </tr>
</table>

## Prerequisites

-   Back up your existing SecureTransport installation. To back up your current SecureTransport deployment, follow a backup procedure applicable for your environment and make sure the backup is created at a time when all SecureTransport services are stopped.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Please keep in mind that migrating SecureTransport Edge to Windows Server 2016 will not migrate the Server and Audit log information. This information can be backed up prior to the migration.         </td>
      </tr>
</table>

-   If migrating SecureTransport Edges in a synchronized cluster, perform the below procedure for each set of two nodes (one old and one new, the new replaces the old one).

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Alternatively if all of the nodes have the same local settings you can add a new node on Windows Server 2016 to the existing synchronized cluster (to sync and replace the old Primary), after which add all other nodes on Windows Server 2016 to the synchronized cluster and resync.         </td>
      </tr>
</table>

##   Migration procedure

1.  Install a new SecureTransport 5.5 Edge (vanilla installation, no patches) on Windows Server 2016 using the `taeh` file from the one on Windows Server 2012 R2.
    -   Make sure that the host names and IP addresses of all servers are in the host files of all servers. Use the lookup command to verify that the host names of all servers resolve on all hosts.
    -   Select the computer that is to serve as the primary server. This must be the Windows Server 2012 R2 node from which the configuration is to be replicated.
2.  Make sure that the patch level of the new SecureTransport deployment (on Windows Server 2016) matches that of the original one (on Windows Server 2012 R2). For example, if the original deployment has Patch 22 installed, you must perform the necessary steps to upgrade the new vanilla SecureTransport installation to Patch 22 as well.
3.  Manually re-apply and reconfigure all previously applied customizations, for example:  
    
    -   plugins from the `…\STServer\plugins\` folder
    -   start/stop scripts
    -   configurations in `configuration.xml`
    -   configurations in `internaldb.conf`
    -   JVM heap size
    -   multi-protocol listeners
    -   all local server configurations (i.e. network zones, allowed SecureTransport Servers) and all Local Server configuration parameters in the SecureTransport Administration Tool: go to **Operation > Server Configuration** and select the **Local Parameters** checkbox on the new Windows Server 2016 node.
4.  Make sure you have a feature license that permits the necessary number of nodes for the migration procedure. In case your license does not allow you to add new machines to the existing environment, contact [Axway Global Support](https://support.axway.com/ "Axway Global Support") and request a temporary license. Do not forget to restart all services after the new license is applied.
5.  On all Windows Server 2012 R2 Edge nodes comment the entries in the `servers` file located in `<FILEDRIVEHOME>\lib\admin\config\` so that the edges will no longer remain synched.
6.  Follow the below steps of forming a Cluster between the SecureTransport Edge on Windows Server 2012 R2 and the one on Windows Server 2016.  
    Perform these steps for the corresponding set of nodes:  
      
    
    -   on one hand the node from which the configuration will be copied. This is the primary one on Windows Server 2012 R2.
    -   on the other the node which will receive the old configuration. This is the new primary one on Windows Server 2016, which will replace the old one on Windows Server 2012 R2.

      
      
    <span id="prereq"></span>**Prerequisites for Synchronization**  
      
    
    -   The `<FILEDRIVEHOME>\lib\admin\config\servers` configuration file is correct and identical on all SecureTransport Edge servers.
    -   The `<FILEDRIVEHOME>\var\tmp\sentinel_primary` file exists on the primary SecureTransport Edge only.
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
    2.  On the primary and the secondary server, list all the servers in the `<FILEDRIVEHOME>\lib\admin\config\servers` configuration file. List the primary server first and continue with the secondary servers.
    3.  On the primary server, create a file named `<FILEDRIVEHOME>\var\tmp\sentinel_primary`
    4.  Log out of the primary SecureTransport Edge server and log in again. Make sure that the server is identified as the primary server and that the **Synchronize All** and **Bounce All** buttons on the *Server Control* page are displayed.
    5.  Synchronize the secondary server manually from the Administration Tool of the primary server.
7.  Manually verify that the data is successfully synced to the new node (parameters, administrators, certificates should be present on the new node).
8.  On both nodes comment the entries in the `servers` file located in `<FILEDRIVEHOME>\lib\admin\config\`.
9.  On the primary node remove the previously created `sentinel_primary` file located in `<FILEDRIVEHOME>\var\tmp\`
10. Power off the original node on Windows Server 2012 R2.
11. Change the IP address of the node on Windows Server 2016 to the IP address previously occupied by the node on Windows Server 2012 R2.
12. Restart all services on the node on Windows Server 2016.
13. For all secondary nodes, follow steps 1 through 4, make sure the new node meets the [Prerequisites for Synchronization](#prereq), and then follow steps 10 through 12.
14. After each node has been successfully replaced by its corresponding Windows Server 2016 node, uncomment the entries in the `servers` file located in `<FILEDRIVEHOME>\lib\admin\config\` on all nodes.
15. Restart all services on all nodes.
16. Synchronize the secondary servers manually from the SecureTransport Administration Tool of the primary server.
17. Re-add your existing (original) license if a temporary one was used and restart all services.

 

**Related topics:**

-   [Standalone installation with embedded database](../standalone-mysql)
-   [Standalone with External Database](../standalone-ext-db)
-   [Standard Cluster environment with embedded database](../standard-cluster-mysql)
-   [Enterprise Cluster environment with external database](../lec-ext-db)
-   [Edge installation with Embedded Database](../edge-mysql)
