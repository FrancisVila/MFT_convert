{
    "title": "Passive disaster recovery",
    "linkTitle": "Passive disaster recovery",
    "weight": "140"
}If <span class="mc-variable axway_variables.Component_Long_Name variable">Axway SecureTransport</span> provides an essential function in your organization, it is likely to require a business continuity plan. To assure business continuity, you can deploy your <span class="mc-variable axway_variables.Component_Long_Name variable">Axway SecureTransport</span> <span class="mc-variable axway_variables.Component_Version variable">5.5</span> Enterprise Cluster with passive disaster recovery (DR). The following diagram illustrates a recommended deployment architecture for an Enterprise Cluster with passive disaster recovery. The arrows show the direction of
network connections for all the protocols. Data flows in both directions after the
connection made.

<img src="/Images/SecureTransport/STDeployment_LECPassiveDR.png" class="maxWidth" alt="Enterprise Cluster with passive disaster recovery" />

<span class="autonumber"></span>Enterprise Cluster with passive disaster recovery

The diagram does not illustrate the event synchronization among the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Servers in one site or any unproxied connections or connections through HTTP proxy servers from the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Servers to the partner servers. For simplicity, the diagram shows only one connection from a SOCKS5 proxy on a <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge to a partner server. The SOCKS5 proxies on all the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge servers can connect to the partner servers through the firewalls as needed. For an illustration of an unproxied connection and more detail about connections in a streaming deployment and configuration for internal clients and servers, see <a href="##Streamin" class="MCXref xref">Streaming deployment</a>.

This deployment architecture uses a redundant Enterprise Cluster and <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge servers at a separate site to provide passive DR. The DR cluster must provide the functionality of the production cluster with the same number or fewer servers than the production cluster. The SecureTransport Edge servers must also provide the functionality of the production site with the same number or fewer servers than the production site. All the servers must run on the same type of operating systems with the same installation directory, secret file, and configuration as the production servers. The SecureTransport Servers in the DR cluster must also have the same database type and configuration as the production SecureTransport Servers and the shared file system must be mounted under the same path on all SecureTransport Servers.

Each server in the DR site is associated with a server in the production site. So if there are fewer servers in the DR site, some servers in the production site are not associated with a server in the DR site. If there are fewer servers in the DR cluster, the configuration of the production site servers that are not associated with a server in the DR site must be maintained on the DR site so that the configuration can be replicated to the production site failback. The DR site *Cluster Management* page lists any production site servers that are not associated with a server in the DR site and shows them as offline.

The DR site is a passive standby. The servers in the DR site do not run when the production site is operational, but the configuration of the DR cluster and the DR SecureTransport Edge servers must be consistent with the configuration of the production cluster and SecureTransport Edge servers so that the DR site is ready to replace the production site. However, the IP addresses of the servers in the production site and the servers in the DR site can be different.

Each cluster has its own shared database and shared file system. So that the DR cluster can replace the production cluster when it is needed, you must implement database synchronization between the production cluster database and the DR cluster database so that the configuration and operational data is consistent. You must also implement data synchronization between the production cluster shared file system and the DR cluster shared file system so that the account home folders and other folders are consistent. Do not synchronize the file systems that host the operating systems and the SecureTransport application files. You keep these consistent by applying the same patches, services packs, and configuration file changes to all servers.

The system configuration and account information of the SecureTransport Edge servers in the production site and the SecureTransport Edge servers in the DR site must be consistent. If there is just one SecureTransport Edge server or if the SecureTransport Edge servers in the sites are synchronized, you can export the system configuration and administrator account information from one of the SecureTransport Edge servers in the active site, import it into one of the SecureTransport Edge servers in the inactive site, and synchronize the SecureTransport Edge servers in the inactive site. You need to do this whenever you change the system configuration or accounts on a SecureTransport Edge server in the active site. To import system configuration and account information into a SecureTransport Edge server or to manually synchronize SecureTransport Edge servers, you must start the database and the Administration Tool server. After the SecureTransport Edge servers are updated, you must stop all services on them.

> **Note:**
>
> If SecureTransport is deployed in a secure perimeter network (DMZ) configuration, the DMZ zones configuration cannot be modified. As a result, streaming is not operational in the DR site (as the nodes have different IP addresses) and all server-initiated transfers set to establish a connection through a DMZ zone will use the IP addresses configured for the production environment.

If you maintain consistency between the production and the DR sites, you can choose to use an external DR solution.

**Related topics:**

-   <a href="../c_st_large_enterprise_cluster_deployment" class="MCXref xref">Enterprise Cluster deployment</a>
-   <a href="../c_st_workload_distribution" class="MCXref xref">Workload distribution</a>
