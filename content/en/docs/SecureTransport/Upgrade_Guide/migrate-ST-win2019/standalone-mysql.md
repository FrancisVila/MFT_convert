{
    "title": "Standalone installation with embedded database",
    "linkTitle": "Standalone installation with Embedded Database",
    "weight": "140"
}This topic provides steps to a successful migration of a standalone <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span><span class="mc-variable axway_variables.Component_Version variable">5.5</span> on Windows Server 2012 R2 to Windows Server 2016 or Windows Server 2019.

The migration procedure requires you to form a Standard cluster and take advantage of its capability of synchronizing global configurations and accounts across nodes.

> **Note:**
>
> The migration procedure to Windows Server 2016 is the same as that to Windows Server 2019. To avoid repetition, instructions herein will discuss migration steps to Windows Server 2016. You can follow these same steps when migrating to Windows Server 2019.

## Prerequisites

-   Back up your existing <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> installation. To back up your current <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> deployment, follow a backup procedure applicable for your environment and make sure the backup is created at a time when all <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> services are stopped.

> **Note:**
>
> Please keep in mind that migrating SecureTransport with embedded database to Windows Server 2016 will not migrate the Transfer, Server and Audit log information. This information can be backed up prior to the migration.

 

## Migration procedure

Follow the steps below to replace the original <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server (standalone installation) deployed on Windows Server 2012 R2, with one on Windows Server 2016.

1.  Install a new node of <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span><span class="mc-variable axway_variables.Component_Version variable">5.5</span> (vanilla installation, no patches) on Windows Server 2016 using the `taeh` file from the one on Windows Server 2012 R2.
    -   Make sure that the host names and IP addresses of all servers are in the host files of all servers. Use the lookup command to verify that the host names of all servers resolve on all hosts.
    -   Select the computer that is to serve as the primary server. This must be the Windows Server 2012 R2 node from which the configuration is to be replicated.

2.  Make sure that the patch level of the new <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> deployment (on Windows Server 2016) matches that of the original one (on Windows Server 2012 R2). For example, if the original deployment has Patch 22 installed, you must perform the necessary steps to upgrade the new vanilla <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> installation to Patch 22 as well.

3.  Manually re-apply and reconfigure all previously applied customizations, for example:

4.  -   plugins from the `…\STServer\plugins\` folder
    -   start/stop scripts
    -   configurations in `configuration.xml`
    -   configurations in `internaldb.conf`
    -   JVM heap size
    -   multi-protocol listeners
    -   all local server configurations (i.e. network zones) and all Local Server configuration parameters: in the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Administration Tool, go to **Operation > Server Configuration** and select the **Local Parameters** checkbox on the new Windows Server 2016 <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> deployment.

5.  Make sure you have a feature license that permits the necessary number of nodes for the migration procedure. In case your license does not allow you to add new machines to the existing environment, contact <span style="background-color: #ffff00;">[Axway Global Support](https://support.axway.com/ "Axway Global Support")</span> and request a temporary license. Do not forget to restart all services after the new license is applied.

6.  Follow the below steps of forming a Standard Cluster between the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> on Windows Server 2012 R2 and the one on Windows Server 2016.

7.    
    **Prerequisites for Synchronization**

8.  -   The <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> administrator account names and passwords on the new <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> deployment must be the same as those on the original <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> deployment.
    -   When certificate authentication is enabled for the administrator accounts, `Cluster.DynamicSync.adminName` and `Cluster.DynamicSync.keyAlias` configuration options must be set on all nodes manually.
    -   The <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> installation path of the new <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> deployment must be the same as that on the original one.
    -   The `taeh` file on the new <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> deployment must be the same as that on the original one.
    -   The certificate for encrypting cluster communications specified in the `Cluster.Crypto.Alias` server configuration parameter on the new <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> deployment must be the same as that on the original one.
    -   The internal CAs on all nodes must be trusted by all other nodes. You can import the same internal CA on all nodes using a <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> generated certificate or an external one.
    -   All the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> server certificates must be issued by a common CA.
    -   Each server must be hosted on a different computer or virtual machine.
    -   All the servers in an active/active cluster must be in the same LAN.
    -   All servers in a cluster must have their clocks set to the same time.
    -   The TM Server must be running on all servers.
    -   All database settings on the new <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> deployment must be identical to that on the original one.

9.    
    Cluster formation steps

10. 1.  Make sure that Transaction Manager (TM) servers are stopped on all <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> servers.
    2.  On the primary and the secondary server, list both servers in the `<FILEDRIVEHOME>\lib\admin\config\servers` configuration file. List the primary server first and continue with the secondary server.
    3.  On the primary server, generate a local certificate for encrypting cluster communications.
    4.  On the primary server, export the certificate in `.p12` format protected with a password.
    5.  Import the certificate on the secondary server.
    6.  On the primary and the secondary server, configure encryption for cluster communications. On the *Server Configuration* page of each node, change the value of the `Cluster.Crypto.Alias` server configuration parameter to the alias of the certificate.
    7.  On the primary server and the secondary server, activate the cluster. On the *Server Configuration* page of each node, change the value of the `Cluster.mode` parameter to **active**.
    8.  Start the TM server on the primary server and wait until it promotes itself as a primary server.
    9.  Check for a `'becomePrimary is called.'` message in the Server Log of the primary node.
    10. Start the TM server on the other server in the cluster and wait for it to go online.
    11. Check for a `'The machine <machine>/<IP> goes online.'` message in Server Log of the secondary node.

<!-- -->

1.  Synchronize the secondary server manually using the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Administration Tool of the primary server.  
2.  Manually verify that the data is successfully synced to the new node (parameters, accounts, certificates should be present on the new node).
3.  On both nodes set the `Cluster.mode` parameter to **disabled** and comment the entries in the `servers` file located in `<FILEDRIVEHOME>\lib\admin\config\`.
4.  Power off the original node on Windows Server 2012 R2.
5.  Change the IP address of the new <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> on Windows Server 2016 deployment to the IP address previously occupied by the original deployment on Windows Server 2012 R2.
6.  Re-add your existing (original) license if a temporary one was used and restart all services on the new <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> installation on Windows Server 2016.

 

**Related Topis:**

-   <a href="../standalone-ext-db" class="MCXref xref">Standalone with External Database</a>
-   <a href="../standard-cluster-mysql" class="MCXref xref">Standard Cluster environment with embedded database</a>
-   <a href="../lec-ext-db" class="MCXref xref">Enterprise Cluster environment with external database</a>
-   <a href="../edge-mysql" class="MCXref xref">Edge installation with Embedded Database</a>
-   <a href="../edge-synced-mysql" class="MCXref xref">Edge installation with Embedded Database when part of a synchronized cluster</a>

 