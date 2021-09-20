{
    "title": "Enterprise Cluster deployment",
    "linkTitle": "Enterprise Cluster deployment",
    "weight": "130"
}An Enterprise Cluster (EC) distributes the workload among a collection of networked SecureTransport Servers, all of which are active. All servers in an Enterprise Cluster must be on the same low latency network.

The following diagram illustrates a possible deployment architecture for an Enterprise Cluster that serves partners who access it using the Internet. The arrows show the direction of
network connections for all the protocols. Data flows in both directions after the
connection made.

![Enterprise Cluster](STDeployment_LEC.png)

Enterprise Cluster

The diagram does not illustrate the event synchronization among the SecureTransport Servers or any unproxied connections or connections through HTTP proxy servers from the SecureTransport Servers to the partner servers. For an illustration of an unproxied connection and more detail about connections in a streaming deployment and configuration for internal clients and servers, see [Streaming deployment](../../../c_st_setup/c_st_networkzones/c_st_streaming_deployment).

Deploy the number of SecureTransport Servers and SecureTransport Edge servers required for your file transfer workload. The connections from the TM Servers on the SecureTransport Servers to the protocol and SOCKS5 proxy servers on the SecureTransport Edge servers is many-to-many, so you can design your deployment with consistent or specialized configuration. For more information, see [Communication across Transaction Manager, protocol, and proxy servers](../../../c_st_setup/c_st_networkzones). Because SecureTransport Edge servers do not create and handle events, they are not clustered, but they can be configured to synchronize configuration changes. For more information, see [SecureTransport Edge synchronization](../../../c_st_edge_sync).

**Related topics:**

-   [Workload distribution](../c_st_workload_distribution)
-   [Passive disaster recovery](../c_st_passive_disaster_recovery)

## Components

This example deployment architecture includes the following components:

-   **SecureTransport Servers** – An Enterprise Cluster has two or more SecureTransport Servers. Each SecureTransport Server has an installation directory on its local file system. All the installation directories must have the same path. You can also deploy SecureTransport with the EC option as a single Server when you require an external database.
-   **Shared external database** – The SecureTransport Servers share an external database that they use to implement the cluster. The shared database stores all the shared (cluster-wide) configuration data and much of the local (individual) configuration data for the servers.
-   **Shared file system** – The SecureTransport Servers share a file system on external storage for working directories and files, for example, using a shared disk file system on a storage area network (SAN) or using network-attached storage (NAS). Because all servers in a cluster share many configuration definitions that include references to directories, such as accounts, the shared file system hosts those directories. SecureTransport installation on a private SAN logical unit number (LUN) is also a supported configuration.
-   **SecureTransport Edge servers** – If an Enterprise Cluster provides service to systems in a public or external unsecured network, it usually includes SecureTransport Edge servers. A cluster deployment usually includes one SecureTransport Edge for each SecureTransport Server, but this can vary depending on the characteristics of the workload. The SecureTransport Edge servers are not clustered, but their configuration can be synchronized.
-   **Firewalls** – The firewalls implement the perimeter network required to serve client systems in a public or external network.
-   **Load balancer** – In the Enterprise Cluster deployment diagram, the load balancer implements workload distribution by distributing the incoming requests from the external clients and servers among the SecureTransport Edge gateways. The specific load balancing method depends on the characteristics of your workload and cluster deployment.