{
    "title": "Set up an active/active cluster",
    "linkTitle": "Set up an active/active cluster",
    "weight": "120"
}You can set up a cluster of {{< SecureTransport/componentshortname  >}} Server computers. When you set up a cluster, a shared secret file, (called `taeh` file) is used by each of the servers in the cluster for authentication purposes across servers and for encryption. The `taeh` file contains randomly-generated data that secures the {{< SecureTransport/componentshortname  >}} cookies exchanged during server administration. {{< SecureTransport/componentshortname  >}} generates the shared `taeh` file as part of the installation process. Refer to the for more information.

> **Note:**
>
> When you install SecureTransport on your secondary computers, you have an opportunity to import the taeh file from the primary server. You can only import the taeh file on a secondary computer during the installation process.

To set up an active/passive cluster, see [Manage an active/passive cluster](../../c_st_managestandardcluster/t_st_manage_active-passive_cluster#Standard_Clustering_3967700027_1035527).

1.  Make sure that the hosts file on each {{< SecureTransport/componentshortname >}} Server or {{< SecureTransport/componentshortname >}} Edge host operating system contains the hostnames and IP addresses of all servers with which it communicates: {{< SecureTransport/componentshortname >}} Server, {{< SecureTransport/componentshortname >}} Edge, and internal servers integrated with {{< SecureTransport/componentshortname >}} like LDAP, external database, Sentinel server, SSO server, ICAP server, etc.
2.  Select the computer that is to serve as the primary server.
3.  Make sure that the `taeh` file of the primary server is installed on all secondary computers.
4.  Set up the secondary servers as independent installations. Add licenses for all servers. For instructions, refer to the or see [Server licenses](../../../c_st_setup/c_st_serverlicenses#SetupMenu_1217491348_1081231).
5.  Generate an internal CA on each server. For instructions, refer to the or see [Manage the internal CA](../../../c_st_setup/c_st_certificates/t_st_internalca#SetupMenu_1217491348_1118526).
6.  Exchange CA certificates between all servers in the cluster. For details, refer to the procedures for exporting and importing {{< SecureTransport/componentshortname >}} Server CA certificates in the or in [Manage local certificates and certificate signing requests](../../../c_st_setup/c_st_certificates/t_st_localcertificatesandcsrs#top).
7.  Make sure that Transaction Manager (TM) servers are stopped on all computers.
8.  On the primary and all secondary servers, list the servers in the `<FILEDRIVEHOME>/lib/admin/config/servers` configuration file. List the primary server first and continue with the secondary servers in the order you want them promoted to primary server in the event of failover.  
    Edit the file and add a line of following form for each server in the cluster:  
    `host.example.com  https://host.example.com:444`  
    where:  
    -   `host.example.com` is the FQDN or IP address of the computer
    -   `https://host.example.com:444` is the URL of the Administration Tool on that computer

      
    and the two fields are separated by a tab character.
9.  On the primary server, generate a local certificate for encrypting cluster communications. For instructions, see [Generate a self-issued server certificate](../../../c_st_setup/c_st_certificates/t_st_localcertificatesandcsrs#Generate).
10. On the primary server, export the certificate in `.p12` format protected with a password. For instructions, see [Export a local certificate](../../../c_st_setup/c_st_certificates/t_st_localcertificatesandcsrs#Export).
11. Import the certificate on each secondary server. For instructions, see [Import a local certificate](../../../c_st_setup/c_st_certificates/t_st_localcertificatesandcsrs#Import).
12. On the primary and all secondary servers, configure encryption for cluster communications. On the *Server Configuration* page, change the value of the `Cluster.Crypto.Alias` server configuration parameter to the alias of the certificate.
13. On the primary server and all secondary servers, activate the cluster. On the *Server Configuration* page, change the value of the `Cluster.mode` parameter to `active`.
14. Start the TM server on the primary server and wait until it promotes itself as a primary server. Start the TM server on all other servers in the cluster. For instructions, see [Manage server operations]().
15. Synchronize the secondary servers manually from the Administration Tool of the primary server. For instructions, see [Requirements for synchronization](../../c_st_managestandardcluster/c_st_standard_cluster_synchronization#Requirem).

During cluster operation, most configuration changes are synchronized dynamically. For more information, see [Synchronization](../../c_st_standardclustermodel/c_st_active-active_active-passive_clustering#Synchron).

<span id="Config_increased_transfers"></span>

## Configuration optimizations in case of increased transfers load

In case of increased transfer payload, you can configure the maximum number of threads for `GeneralMessageProcessing` in the {{< SecureTransport/securetransportname  >}} Server Configuration by increasing the value of the following parameter:

`Cluster.ThreadPools.ThreadPool.GeneralMessageProcessing.maxThreads`

By default this value is set to `4`. For optimal performance, you can increase this value up to `100` or even more.

You have to apply this configuration across all nodes.

**Related topics:**

-   [Specify the cluster connection timeout](../t_st_specify_cluster_connection_timeout)
-   [Configure servers in a cluster to trust a certificate](../t_st_configure_servers_cluste_trust_certificate)
-   [Set up an active/passive cluster](../t_st_setup_active-passive_cluster)
