{
    "title": "Enterprise Cluster environment with external database",
    "linkTitle": "Enterprise Cluster environment with external database",
    "weight": "170"
}This topic provides instructions for migrating {{< SecureTransport/componentshortname  >}}{{< SecureTransport/componentversion  >}} Server on Windows Server 2012 R2 deployment (as part of an Enterprise cluster with Oracle or MSSQL database) to Windows Server 2016 or Windows Server 2019.

The migration procedure requires you to add your new SecureTransport Server deployment (on Windows Server 2016 or Windows Server 2019) to the Enterprise cluster and take advantage of its capability to sync global configurations and accounts across nodes.

> **Note:**
>
> The migration procedure to Windows Server 2016 is the same as that to Windows Server 2019. To avoid repetition, instructions herein will discuss migration steps to Windows Server 2016. You can follow these same steps when migrating to Windows Server 2019.

## Prerequisites

-   Back up your existing {{< SecureTransport/componentshortname >}} installation. To back up your current {{< SecureTransport/componentshortname >}} deployment, follow a backup procedure applicable for your environment and make sure the backup is created at a time when all {{< SecureTransport/componentshortname >}} services are stopped. It is recommended that you perform a full database backup.
-   All Windows Server 2016 machines must be added to the same Domain.
-   The time of the Windows Server 2016 machine must be the same as the time on Windows Server 2012 R2 machine where your current {{< SecureTransport/componentshortname >}} is installed. The time settings (clocks) on all machines in the network must be synchronized.
-   All new Windows Server 2016 machines must have access to the network storage that the Windows Server 2012 R2 machines are using.

## Migration procedure

Follow the steps below for adding a new node on Windows Server 2016 to the existing {{< SecureTransport/componentshortname  >}} Cluster on Windows Server 2012 R2.

1.  Install {{< SecureTransport/componentshortname >}} Server {{< SecureTransport/componentversion >}} (vanilla installation, no patches) on Windows Server 2016 using the `taeh` file from the one on Windows Server 2012 R2 and use the existing database schema
2.  The {{< SecureTransport/componentshortname >}} installation path must be the same on all servers
3.  Make sure that the patch level of the new {{< SecureTransport/componentshortname >}} deployment (on Windows Server 2016) matches that of the original one (on Windows Server 2012 R2). For example, if the original deployment has Patch 22 installed, you must perform the necessary steps to upgrade the new vanilla {{< SecureTransport/componentshortname >}} installation to Patch 22 as well.
4.  Manually re-apply and reconfigure all previously applied customizations, for example:  
    -   plugins from the `…\STServer\plugins\` folder
    -   start/stop scripts
    -   configurations in `configuration.xml`
    -   JVM heap size
    -   multi-protocol listeners
    -   all local server configurations (i.e. network zones) and all Local Server configuration parameters: in the {{< SecureTransport/componentshortname >}} Administration Tool, go to **Operation > Server Configuration** and select the **Local Parameters** checkbox on the new Windows Server 2016 node.
5.  Make sure you have a feature license that permits the necessary number of nodes for the migration procedure. In case your license does not allow you to add new machines to the existing EC, contact and request a temporary license. Do not forget to restart all services after the new license is applied.
6.  Log in to the SecureTransport Administration Tool on the running {{< SecureTransport/componentshortname >}} server on Windows Server 2012 R2 as the admin user. Go to the *Cluster management* page and add the Windows Server 2016 machine to the cluster by entering its IP address.
7.  Start the Administration Tool server on Windows Server 2016 machine.
8.  Log in to the {{< SecureTransport/componentshortname >}} Administration Tool (on Windows Server 2016) as the admin user and install the license.
9.  In case the current {{< SecureTransport/componentshortname >}} environment uses separate Oracle databases, they have to be added manually in the *Database Settings* page.
10. Restart all {{< SecureTransport/componentshortname >}} services on the Windows Server 2016 machine.
11. Make sure all nodes in the Enterprise cluster are online and synchronized.
12. Make sure that all global server configuration options are present in the newly added node after the synchronization.
13. Manually add all local server configuration options (i.e. network zones) and all Local Server configuration parameters in the {{< SecureTransport/componentshortname >}} Administration Tool: go to **Operation > Server Configuration** and select the **Local Parameters** checkbox on the new Windows Server 2016 node.
14. Stop the original Windows Server 2012 R2 machine.
15. Log in to the SecureTransport Administration Tool of the second {{< SecureTransport/componentshortname >}} node (on Windows Server 2012 R2), go to *Cluster Management* page and remove the IP address of the machine that was powered off from the Servers table.
16. Stop all services on {{< SecureTransport/componentshortname >}} on Windows Server 2016.
17. Change the IP address of Windows Server 2016 to the one of the powered off Windows Server 2012 R2.
18. Add the IP address from step 17 again to the cluster.
19. Start all services on {{< SecureTransport/componentshortname >}} on Windows Server 2016.
20. Wait until the node goes online.
21. Log in the {{< SecureTransport/componentshortname >}} Administration Tool and go to the *Cluster management* page
22. Remove the original IP address of the Windows Server 2016 machine from the cluster.
23. Re-add your existing (original) license in case a temporary one was used and restart all services on the new node (on Windows Server 2016).

Repeat the same steps for all other {{< SecureTransport/componentshortname  >}} Server nodes from the Enterprise cluster.

 

**Related Topics:**

-   <a href="../standalone-mysql" class="MCXref xref">Standalone installation with embedded database</a>
-   <a href="../standalone-ext-db" class="MCXref xref">Standalone with External Database</a>
-   <a href="../standard-cluster-mysql" class="MCXref xref">Standard Cluster environment with embedded database</a>
-   <a href="../edge-mysql" class="MCXref xref">Edge installation with Embedded Database</a>
-   <a href="../edge-synced-mysql" class="MCXref xref">Edge installation with Embedded Database when part of a synchronized cluster</a>
