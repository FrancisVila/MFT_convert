{
    "title": "Specify the cluster connection timeout",
    "linkTitle": "Specify the cluster connection timeout",
    "weight": "140"
}You can specify a timeout value that determines how long a secondary server waits before declaring itself the primary server. This is important in cases where the primary server is heavily loaded and takes an extended period of time to respond to a secondary computer.

-   On the *Server Configuration* page of the primary server, change the value of the `Cluster.connectionTimeout` parameter to the value required in milliseconds. The default value is 60000.

**Related topics:**

-   [Set up an active/active cluster](../t_st_setup_active-active_cluster)
-   [Configure servers in a cluster to trust a certificate](../t_st_configure_servers_cluste_trust_certificate)
-   [Set up an active/passive cluster](../t_st_setup_active-passive_cluster)
