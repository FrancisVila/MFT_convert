{
    "title": "Standalone with External Database",
    "linkTitle": "Standalone installation with External Database",
    "weight": "150"
}This topic provides instructions for migrating a standalone {{< SecureTransport/componentshortname  >}} {{< SecureTransport/componentversion  >}} deployment on Windows Server 2012 R2 to Windows Server 2016 or Windows Server 2019.

The migration procedure requires you to use the external database of your existing (original) deployment (on Windows Server 2012 R2) to acquire all original global configurations and account information.

> **Note:**
>
> The migration procedure to Windows Server 2016 is the same as that to Windows Server 2019. To avoid repetition, instructions herein will discuss migration steps to Windows Server 2016. You can follow these same steps when migrating to Windows Server 2019.

## Prerequisites

-   Back up your existing {{< SecureTransport/componentshortname >}} installation. To back up your current {{< SecureTransport/componentshortname >}} deployment, follow a backup procedure applicable for your environment and make sure the backup is created at a time when all {{< SecureTransport/componentshortname >}} services are stopped. It is recommended that you perform a full database backup.
-   All Windows Server 2016 machines must be added to the same Domain.
-   The time set on the Windows Server 2016 machine must be the same as the time on Windows Server 2012 R2 machine where your current {{< SecureTransport/componentshortname >}} is installed. The time settings (clocks) on all machines in the network must be synchronized.
-   The new Windows Server 2016 machine must have access to the network storage that the Windows Server 2012 R2 machine is using.

## Migration procedure

Follow the steps below to replace a {{< SecureTransport/componentshortname  >}} installation on Windows Server 2012 R2 (standalone installation, with external database) with one on Windows Server 2016.

1.  Install {{< SecureTransport/componentshortname >}} Server {{< SecureTransport/componentversion >}} (vanilla installation, no patches) on Windows Server 2016 using the `taeh` file from the one on Windows Server 2012 R2 and use the existing database schema.
2.  The {{< SecureTransport/componentshortname >}} installation path must be the same on all servers.
3.  Make sure that the patch level of the new {{< SecureTransport/componentshortname >}} deployment (on Windows Server 2016) matches that of the original one (on Windows Server 2012 R2). For example, if the original deployment has Patch 22 installed, you must perform the necessary steps to upgrade the new vanilla {{< SecureTransport/componentshortname >}} installation to Patch 22 as well.
4.  Manually re-apply and reconfigure all previously applied customizations, for example:  
    -   plugins from the `…\STServer\plugins\` folder
    -   start/stop scripts
    -   configurations in `configuration.xml`
    -   JVM heap size
    -   multi-protocol listeners
    -   all local server configurations (i.e. network zones) and all Local Server configuration parameters: in the {{< SecureTransport/componentshortname >}} Administration Tool, go to **Operation > Server Configuration** and select the **Local Parameters** checkbox on the new Windows Server 2016 node.
5.  Make sure you have a feature license that permits the necessary number of nodes for the migration procedure. In case your license does not allow you to use more machines, contact and request a temporary license. Do not forget to restart all services after a new license is applied.
6.  Start the {{< SecureTransport/componentshortname >}} Administration Tool server on Windows Server 2016 machine
7.  Log in to the {{< SecureTransport/componentshortname >}} Administration Tool (on Windows Server 2016) as the admin user and install the license.
8.  Restart all {{< SecureTransport/componentshortname >}} services on Windows Server 2016 machine.
9.  Make sure that all global server configuration options are present on the new installation on Windows Server 2016.
10. Manually add all local server configuration options from the original {{< SecureTransport/componentshortname >}} (on Windows Server 2012 R2) to the new {{< SecureTransport/componentshortname >}} installed on Windows Server 2016.
11. Stop the original Windows Server 2012 R2 machine.
12. Stop all services on {{< SecureTransport/componentshortname >}} on Windows Server 2016.
13. Change the IP address of Windows Server 2016 to the one of the powered off Windows Server 2012 R2.
14. Start all services on {{< SecureTransport/componentshortname >}} on Windows Server 2016.
15. Wait until the new {{< SecureTransport/componentshortname >}} deployment goes online.
16. Re-add your existing (original) license if a temporary one was used and restart all services on your new {{< SecureTransport/componentshortname >}} deployment (on Windows Server 2016).

 

**Related Topics:**

-   [Standalone installation with embedded database](../standalone-mysql)
-   [Standard Cluster environment with embedded database](../standard-cluster-mysql)
-   [Enterprise Cluster environment with external database](../lec-ext-db)
-   [Edge installation with Embedded Database](../edge-mysql)
-   [Edge installation with Embedded Database when part of a synchronized cluster](../edge-synced-mysql)
