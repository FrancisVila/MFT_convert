{
    "title": "Server configuration",
    "linkTitle": "Server configuration",
    "weight": "140"
}SecureTransport server configuration consists of all the information the server and its components require to operate. You establish most of the server configuration by setting fields on the various pages of the Administration Tool. In a SecureTransport cluster, the servers store server configuration parameters in a shared database for an Enterprise Cluster (EC) and in synchronized embedded databases for a Standard Cluster (SC). The server configuration parameters include both shared, cluster-wide parameters and parameters for individual servers. When you change a shared parameter, all the servers in the cluster get the new value.

To support operation of the components that use configuration files, the server copies the configuration from the database into those files when it starts and when you change a parameter on any node of the cluster. It is not necessary to bounce the servers manually to propagate the change.

Use the *Server Configuration* page to view configuration parameters that are stored in the database and change those that are not set elsewhere in the Administration Tool. This page also includes access to pages you can use to view or update server configuration files on your local computer, synchronize configuration files, and export and import server configuration.

The following topics provide additional server configuration information:

-   [Editable server configuration parameters](c_st_editable_server_configuration_parameters) - Provides how-to instructions on setting editable server configuration parameters.
-   [Local server configuration parameters](c_st_local_server_configuration_parameters) - Describes the local server configuration parameters.
-   [View and change server configuration parameters](t_st_serverconfigurationparameters) - Provides how-to instructions for viewing and changing server configuration parameters.
-   [Update configuration files](t_st_serverconfigurationfiles) - Provides how-to instructions on updating server configuration files.
-   [Export and import server configuration](t_st_serverconfigurationexportimport) - Provides how-to instructions on exporting and importing server configurations.
