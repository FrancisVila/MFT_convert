{
    "title": "Standard Cluster environment with embedded database",
    "linkTitle": "Standard Cluster environment with embedded database",
    "weight": "160"
}This topic provides instructions for migrating SecureTransport 5.5 Server (part of a Standard cluster deployment) on Windows Server 2012 R2 to Windows Server 2016 or Windows Server 2019.

The migration procedure requires you to add your new SecureTransport Server deployment (on Windows Server 2016 or Windows Server 2019) as a secondary server to the Standard cluster (replacing the old one) and take advantage of its capability to sync global configurations and accounts across nodes.

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
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top"> Please keep in mind that migrating <span>SecureTransport</span> with embedded database to Windows Server 2016 will not migrate the Transfer, Server and Audit log information. This information can be backed up prior to the migration.         </td>
      </tr>
</table>

## Migration procedure

Follow the steps below to replace the original SecureTransport Server (as part of a Standard cluster) deployed on Windows Server 2012 R2, with one on Windows Server 2016.

1.  Install 2 new SecureTransport 5.5 (vanilla installation, no patches) instances on Windows Server 2016 using the `taeh` file from the original one on Windows Server 2012 R2.
    -   Make sure that the host names and IP addresses of all servers are in the host files of all servers. Use the lookup command to verify that the host names of all servers resolve on all hosts.
    -   Select the machine that is to serve as the primary server. This must be the Windows Server 2012 R2 node from which the configuration is to be replicated.
2.  Make sure that the patch level of the new SecureTransport deployment (on Windows Server 2016) matches that of the original one (on Windows Server 2012 R2). For example, if the original deployment has Patch 22 installed, you must perform the necessary steps to upgrade the new vanilla SecureTransport installation to Patch 22 as well.
3.  Manually re-apply and reconfigure all previously applied customizations, for example:  
    
    -   plugins from the `…\STServer\plugins\` folder
    -   start/stop scripts
    -   configurations in `configuration.xml`
    -   configurations in `internaldb.conf`
    -   JVM heap size
    -   Multi-protocol listeners
    -   all local server configurations (i.e. network zones) and all Local Server configuration parameters: in the SecureTransport Administration Tool, go to **Operation > Server Configuration** and select the **Local Parameters** checkbox on the new Windows Server 2016 node.
4.  Make sure you have a feature license that permits the necessary number of nodes for the migration procedure. In case your license does not allow you to add new machines to the existing environment, contact [Axway Global Support](https://support.axway.com/ "Axway Global Support") to request a temporary license. Do not forget to restart all services after the new license is applied.
5.  On the existing Standard Cluster nodes (Windows Server 2012 R2) – stop the TM servers.
6.  On the Primary node – edit the `<FILEDRIVEHOME>\STServer\lib\admin\config\servers` file – remove the Secondary server and add one of the new SecureTransport on Windows Server 2016. On the original secondary server (Windows Server 2012 R2), set the `Cluster.mode` parameter to **disabled**, then comment the entries in the `servers` file located in `<FILEDRIVEHOME>\lib\admin\config\` and restart all services. This will run as standalone and will take the load during the migration procedure.
7.  Follow the below steps of forming a Standard Cluster between the original SecureTransport (on Windows Server 2012 R2) and the one on Windows Server 2016:  
      
    **<span id="prerequisite"></span>Prerequisites for Synchronization**  
    -   The SecureTransport administrator account names and passwords must be the same across all servers.
    -   When certificate authentication is enabled for the administrator accounts, the `Cluster.DynamicSync.adminName` and `Cluster.DynamicSync.keyAlias` configuration options must be manually set on all SecureTransport Server nodes.
    -   The SecureTransport installation path must be the same on all servers.
    -   The `taeh` file must be the same on all servers.
    -   The certificate for encrypting cluster communications specified in the `Cluster.Crypto.Alias` server configuration parameter must be the same on all servers.
    -   The internal CAs on all nodes must be trusted by all other nodes. You can import the same internal CA on all nodes using a SecureTransport generated certificate or an external one.
    -   All the SecureTransport server certificates must be issued by a common CA.
    -   Each server must be hosted on a different computer or virtual machine.
    -   All the servers in an active/active cluster must be in the same LAN.
    -   All servers in a cluster must have their clocks set to the same time.
    -   The TM Server must be running on all servers.
    -   All database settings must be identical on all the servers.

      
      
    <span id="form_cluster"></span>**Cluster formation steps**
      
    
    1.  Make sure that Transaction Manager (TM) servers are stopped on all machines.
    2.  On the primary and the secondary server, list both servers in the `<FILEDRIVEHOME>\lib\admin\config\servers` configuration file. List the primary server first and continue with the secondary servers in the order you want them promoted to primary server in the event of failover.
    3.  On the primary server, generate a local certificate for encrypting cluster communications.
    4.  On the primary server, export the certificate in `.p12` format protected with a password.
    5.  Import the certificate on each secondary server.
    6.  On the primary and the secondary server, configure encryption for cluster communications. On the Server Configuration page, change the value of the `Cluster.Crypto.Alias` server configuration parameter to the alias of the certificate.
    7.  On the primary server and all secondary servers, activate the cluster. On the *Server Configuration* page, change the value of the `Cluster.mode` parameter to **active**.
    8.  Start the TM server on the primary server and wait until it promotes itself as a primary server.
    9.  Check for a `'becomePrimary is called.'` message in the Server Log of the primary node.
    10. Start the TM server on the other server in the cluster and wait for it to go online.
    11. Check for a `'The machine <machine>/<IP> goes online.'` message in Server Log of the secondary node.
8.  Synchronize the secondary server manually from the Administration Tool of the primary server.
9.  Manually verify that the data is successfully synced to the new node (parameters, accounts, certificates should be present on the new node).
10. On both nodes set the `Cluster.mode` parameter to **disabled** and comment the entries in the `servers` file located in `<FILEDRIVEHOME>\lib\admin\config\`.
11. Edit the `servers` file located in `<FILEDRIVEHOME>\lib\admin\config\` on Windows Server 2016 machine - set its IP address on first position and the IP of the other SecureTransport Windows Server 2016 - on the second position.
12. Repeat the previous point on the other SecureTransport Windows Server 2016 machine.
13. Start all services on both SecureTransport instances.
14. Follow the *Prerequisites for Synchronization* and the *Cluster formation steps* as described above in order to form Standard Cluster with both SecureTransport instances on Windows Server 2016.
15. At this point you have a fully functioning Standard cluster on Windows Server 2016.
16. Power off the nodes on Windows Server 2012 R2.
17. Change the IP addresses of the nodes on Windows Server 2016 to the corresponding ones, previously occupied by the nodes on Windows Server 2012 R2.
18. Re-add your existing (original) license if a temporary one was used and restart all services on the node on Windows Server 2016.

 

**Related Topics:**

-   [Standalone installation with embedded database](../standalone-mysql)
-   [Standalone with External Database](../standalone-ext-db)
-   [Enterprise Cluster environment with external database](../lec-ext-db)
-   [Edge installation with Embedded Database](../edge-mysql)
-   [Edge installation with Embedded Database when part of a synchronized cluster](../edge-synced-mysql)
