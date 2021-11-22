{
    "title": "Set up a disaster recovery cluster",
    "linkTitle": "Set up a disaster recovery cluster",
    "weight": "200"
}Use the following procedure to set up a disaster recovery cluster.

1.  For each {{< SecureTransport/componentshortname >}} Server in your production cluster, edit the `<FILEDRIVEHOME>/conf/options-overwrite.conf` file and replace  
    `#Cluster.DeploymentSite=Prod`  
    with  
    `Cluster.DeploymentSite=Prod`
2.  On one {{< SecureTransport/componentshortname >}} Server in the production site:
    1.  On the *Server Configuration* page:
        -   Set `Cluster.EnableDRConfiguration` to `true`.
        -   Make sure that `Cluster.DeploymentSite` is set to `Prod`.
    2.  For each network zone node, make sure the **Deployment Site** field is set to `Prod` so that this node will be used when `Cluster.DeploymentSite` is set to `Prod` and define another node for the DR site with the **Deployment Site** field set to `DR`.
3.  Deploy a separate cluster that duplicates your production cluster. For information you need when you plan your DR cluster and install the servers, see <a href="../../c_st_largeenterpriseclustermodel/c_st_passive_disaster_recovery" class="MCXref xref">Passive disaster recovery</a>. To initialize the DR site:
    1.  Synchronize the database for the DR cluster with database for the production cluster so that configuration is consistent with the production cluster.
    2.  Synchronize the data for the DR cluster with data for the production cluster so that the account home folders and other folders are consistent.
4.  For each {{< SecureTransport/componentshortname >}} Server in the DR site:
    1.  Copy the `<LocalConfigurationsId>` element in `<FILEDRIVEHOME>/conf/configuration.xml` from the corresponding server in the production site.

    2.  The content of the `<LocalConfigurationsId>` element establishes the correspondence between a production server and its corresponding DR server.

    3.  Edit the `<FILEDRIVEHOME>/conf/options-overwrite.conf` file.
        -   Replace
        -   `#Cluster.DeploymentSite=Prod`
        -   with
        -   `Cluster.DeploymentSite=DR`
        -   Replace
        -   `#node.ip=`
        -   with
        -   `node.ip=IP_adderess`
        -   where `IP_adderess` is the IP address of the system that the {{< SecureTransport/componentshortname >}} Server is running on.

    4.  When {{< SecureTransport/componentshortname >}} Server starts, it updates the database with this IP address.

    5.  **Note:**
        >
        > You can use options-overwrite.conf to overwrite any local or shared editable server configuration parameter that you can set on the Server Configuration page.
5.  For each {{< SecureTransport/componentshortname >}} Edge in the DR site:
    1.  Update the network zone node of the `Private` network zone so that it references the {{< SecureTransport/componentshortname >}} Servers in the DR cluster.
    2.  Export system configuration from the associated production {{< SecureTransport/componentshortname >}} Edge and import it.
6.  If you are using a separate shared databases for each site, log in to the Administration Tool on each {{< SecureTransport/componentshortname >}} Server in the DR cluster and change the database to the DR shared database.
7.  Set up email notification on the production cluster and define the procedure by which you decide to switch to the DR site and the method you use to switch.
8.  Set up and test the data replication from the production cluster to the DR cluster.

**Related topics:**

-   <a href="../c_st_cluster_prerequisites" class="MCXref xref">Enterprise Cluster prerequisites</a>
-   <a href="../t_st_setup_cluster" class="MCXref xref">Set up a cluster</a>
-   <a href="../t_st_add_server_to_cluster" class="MCXref xref">Add a server to a cluster</a>
-   <a href="../t_st_remove_server_from_cluster" class="MCXref xref">Remove a server from a cluster</a>
-   <a href="../t_st_view_cluster_status" class="MCXref xref">View cluster status</a>
-   <a href="../t_st_notification_of_cluster_status" class="MCXref xref">Notification of cluster status</a>
-   <a href="../t_st_maintain_disaster_recovery_cluster" class="MCXref xref">Maintain a disaster recovery cluster</a>
-   <a href="../t_st_dr_failover_fallback" class="MCXref xref">Disaster recovery failover and fallback</a>
-   <a href="../t_st_direct_cluster_workload" class="MCXref xref">Direct cluster workload</a>
