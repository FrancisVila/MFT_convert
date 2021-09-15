{
    "title": "Set up a disaster recovery cluster",
    "linkTitle": "Set up a disaster recovery cluster",
    "weight": "210"
}Use the following procedure to set up a disaster recovery cluster.

1.  For each SecureTransport Server in your production cluster, edit the `<FILEDRIVEHOME>/conf/options-overwrite.conf` file and replace   
    `#Cluster.DeploymentSite=Prod`
      
    with  
    `Cluster.DeploymentSite=Prod`
2.  On one SecureTransport Server in the production site:
    1.  On the *Server Configuration* page:
        -   Set `Cluster.EnableDRConfiguration` to `true`.
        -   Make sure that `Cluster.DeploymentSite` is set to `Prod`.
    2.  For each network zone node, make sure the **Deployment Site** field is set to `Prod` so that this node will be used when `Cluster.DeploymentSite` is set to `Prod` and define another node for the DR site with the **Deployment Site** field set to `DR`.
3.  Deploy a separate cluster that duplicates your production cluster. For information you need when you plan your DR cluster and install the servers, see [Passive disaster recovery](../../c_st_largeenterpriseclustermodel/c_st_passive_disaster_recovery). To initialize the DR site:
    1.  Synchronize the database for the DR cluster with database for the production cluster so that configuration is consistent with the production cluster.
    2.  Synchronize the data for the DR cluster with data for the production cluster so that the account home folders and other folders are consistent.
4.  For each SecureTransport Server in the DR site:
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
        -   where `IP_adderess` is the IP address of the system that the SecureTransport Server is running on.

    4.  When SecureTransport Server starts, it updates the database with this IP address.

    5.  <table cellpadding="0" cellspacing="0">   <col/>   <col/>   <col/>      <tr>         <td valign="top">         </td>         <td valign="top"><span><b>Note</b></span>         </td>         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">You can use <code>options-overwrite.conf</code> to overwrite any local or shared editable server configuration parameter that you can set on the <em>Server Configuration</em> page.         </td>      </tr></table>
5.  For each SecureTransport Edge in the DR site:
    1.  Update the network zone node of the `Private` network zone so that it references the SecureTransport Servers in the DR cluster.
    2.  Export system configuration from the associated production SecureTransport Edge and import it.
6.  If you are using a separate shared databases for each site, log in to the Administration Tool on each SecureTransport Server in the DR cluster and change the database to the DR shared database.
7.  Set up email notification on the production cluster and define the procedure by which you decide to switch to the DR site and the method you use to switch.
8.  Set up and test the data replication from the production cluster to the DR cluster.

**Related topics:**

-   [Enterprise Cluster prerequisites](../c_st_cluster_prerequisites)
-   [Set up a cluster](../t_st_setup_cluster)
-   [Add a server to a cluster](../t_st_add_server_to_cluster)
-   [Remove a server from a cluster](../t_st_remove_server_from_cluster)
-   [View cluster status](../t_st_view_cluster_status)
-   [Notification of cluster status](../t_st_notification_of_cluster_status)
-   [Maintain a disaster recovery cluster](../t_st_maintain_disaster_recovery_cluster)
-   [Disaster recovery failover and fallback](../t_st_dr_failover_fallback)
-   [Direct cluster workload](../t_st_direct_cluster_workload)
