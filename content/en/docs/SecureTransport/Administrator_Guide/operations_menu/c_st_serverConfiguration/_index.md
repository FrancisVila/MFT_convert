{
    "title": "Server configuration",
    "linkTitle": "Server configuration",
    "weight": "130"
}{{< SecureTransport/componentshortname  >}} server configuration consists of all the information the server and its components require to operate. You establish most of the server configuration by setting fields on the various pages of the Administration Tool. In a {{< SecureTransport/componentshortname  >}} cluster, the servers store server configuration parameters in a shared database for an Enterprise Cluster (EC) and in synchronized embedded databases for a Standard Cluster (SC). The server configuration parameters include both shared, cluster-wide parameters and parameters for individual servers. When you change a shared parameter, all the servers in the cluster get the new value.

To support operation of the components that use configuration files, the server copies the configuration from the database into those files when it starts and when you change a parameter on any node of the cluster. It is not necessary to bounce the servers manually to propagate the change.

Use the *Server Configuration* page to view configuration parameters that are stored in the database and change those that are not set elsewhere in the Administration Tool. This page also includes access to pages you can use to view or update server configuration files on your local computer, synchronize configuration files, and export and import server configuration.

The following topics provide additional server configuration information:

-   <a href="c_st_editable_server_configuration_parameters" class="MCXref xref">Editable server configuration parameters</a> - Provides how-to instructions on setting editable server configuration parameters.
-   <a href="c_st_local_server_configuration_parameters" class="MCXref xref">Local server configuration parameters</a> - Describes the local server configuration parameters.
-   <a href="t_st_serverconfigurationparameters" class="MCXref xref">View and change server configuration parameters</a> - Provides how-to instructions for viewing and changing server configuration parameters.
-   <a href="t_st_serverconfigurationfiles" class="MCXref xref">Update configuration files</a> - Provides how-to instructions on updating server configuration files.
-   <a href="t_st_serverconfigurationexportimport" class="MCXref xref">Export and import server configuration</a> - Provides how-to instructions on exporting and importing server configurations.
