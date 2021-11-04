{
    "title": "SecureTransport on Azure Virtual Network",
    "linkTitle": "SecureTransport on Azure Virtual Network",
    "weight": "40"
}## <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> in Azure Virtual Network

As of date of issue of the current guide, deployment of SecureTransport on Azure VNet is verified for Red Hat Enterprise Linux in an Enterprise Cluster deployment with streaming setup to a cluster of Edges.

<img src="/Images/SecureTransport/st-in-azure.png" title="SecureTransport Enterprise Cluster in Azure" class="maxWidth" />

The primary deployment architecture includes the SecureTransport Edges in cluster setup, logically separated in the Public Subnet – DMZ. Streaming is established to all <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edges from the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Servers. On the Backend part, the MS SQL cluster server and the GlusterFS Shared storage servers reside in another dedicated Private Subnet.

**Note** The SQL servers are installed on Azure VMs and not as Azure SQL Database services.

##### **Availability zones**

To ensure high availability (HA), it is recommended to distribute Enterprise Cluster nodes evenly across the two availability zones.

An Availability Zone is a unique physical location within a given Azure region which hosts the VMs of all SecureTransport components. The <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> deployment model described here suggests two availability zones: each of which contains an equal number of SecureTransport Edges and Enterprise Cluster nodes.

Availability zones provide a way to make applications highly available and protected from disaster recovery with reliable replication of data with other zones.

A zone in an Azure region provides a combination of a fault domain and an update domain. This means that your VMs are effectively distributed across the update domains and fault domains and maintain instant availability of replicated apps and data in another zone.

##### **SQL Clustering**

The primary and secondary MS SQL servers are deployed in an Always On availability group. This availability group requires a cluster manager component. In Windows, failover clustering provides the cluster manager (Windows Server Failover Cluster (WSFC)).

The availability replica of a given availability group must reside on the secondary node of the same failover cluster. The shared storage GlusterFS servers are deployed in a similar fashion.

Depending on your requirements, you can deploy a load balancers for workload distribution across your Edges*.*

This architecture concept allows high availability with controlled replication and logging across all components in Azure.

As an optional component, there is a host placed in the public subnet called "Administration host" (also known as "Bastion host" or “Jump host”). Bastion hosts are instances that typically reside within your public subnet and are usually accessed using SSH or RDP. Once remote connectivity is established with the bastion host, it then acts as a *jump* server, allowing you to use SSH or RDP to log in to publicly inaccessible instances. The Administration host is used to perform maintenance and administration tasks on the servers in the SecureTransport setup. If you consider resiliency and high availability of your services in cloud deployments, the recommended practice is to have each of the Administration hosts placed in a different Availability Zone in case one of the hosts goes down. For minimal security risks, you should stop your Administration host instances for the duration of no maintenance work and start them when you need access to your servers in Azure again.

You can connect directly to your VNet using a Point-to-Site connection in case you don't want to have an Administration host in your setup (see *[Configure a Point-to-Site connection to your VNet](../p2s-connection)* section in this guide).

The installation of SecureTransport on Red Hat instances in Microsoft Azure cloud follows a flow which is the same as that of an installation on a regular Red Hat machine, including the required installation prerequisites. This process is already described in the [<span class="mc-variable axway_variables.Component_Short_Name variable" style="font-style: italic;">SecureTransport</span> *<span class="mc-variable axway_variables.Release_Number variable">5.5</span> Installation Guide*](https://axway.zoominsoftware.io/bundle/SecureTransport_55_InstallationGuide_allOS_en_HTML5/page/Content/InstallationGuide/STInstallationGuideStartPage.htm).

You will pass through several Azure cloud specific setup and configuration stages until you are able to proceed with your <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> installation.

To set up <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> in Azure Virtual Network, you must pass through the following steps:

1.  Create a Virtual Network.
2.  Create Network Security Groups.
3.  Create one public and two private subnets.
4.  Launch the following instances:
    1.  *(optionally)* Launch an instance for an Administration Host.
    2.  Launch instances in the public subnets for <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge installations.
    3.  Launch instances in the private subnets for <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server installations.
    4.  Launch instances in the private subnets for external GlusterFS file system.

      
    Note <span style="font-weight: normal;">Make sure to separate all components of each Enterprise Cluster node in a respective Availability Zone.</span>
5.  Set up two Microsoft SQL Server Always On Availability groups, deployed in a Windows Server Failover Cluster(WSFC).
6.  Establish VPN connection to your Azure VNet.
7.  Set up <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Enterprise Cluster.
8.  Set up Load Balancer.
