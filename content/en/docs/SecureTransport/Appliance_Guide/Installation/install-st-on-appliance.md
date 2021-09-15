{
    "title": "Install SecureTransport",
    "linkTitle": "Install SecureTransport",
    "weight": "80"
}You use the Appliance Console menu to install SecureTransport on the appliance. Installation on the appliance offers you most of the same options as other UNIX-based installations. For example, you can install SecureTransport Server or Edge using an embedded database server in a Standard Cluster or stand-alone. Alternatively, you can use an external database in an Enterprise Clustering (EC) option. Regardless of the setup, you must have a license.

Check the pre-installation information and prerequisites before you install.

This procedure is an example of the interaction when SecureTransport Server is not already installed on the system. Multiple instances of SecureTransport Server or Edge are not supported.

1.  Open the Appliance Console Menu. Do the following:
    -   Connect to your virtual appliance.
2.  On the Appliance Console Menu, enter **C** (SecureTransport Configuration) to display the SecureTransport Configuration menu.
3.  Enter **I** (Install SecureTransport) to begin installation.
4.  Choose your setup preference from the available options:
    -   Single — Install SecureTransport on a single machine in standalone mode. Standalone SecureTransport uses the embedded database.
    -   Enterprise Cluster — Install SecureTransport as a node in an Enterprise cluster: either as Server or Edge. This option requires a PostgreSQL, Oracle or Microsoft SQL Server database and a license for the Enterprise Cluster option.
    -   Standard Cluster — Install SecureTransport as a node in a Standard cluster: either as Server or Edge. This option uses the embedded database.

      
    
    For *embedded database* installation, see [Install SecureTransport to use the embedded database](../../../installation_guide/install_overview/installing_on_unix_based_platforms/installing_securetransport_embedded_db_unix). For *external database* installation, see [Install SecureTransport Server in an Enterprise Cluster or to use an external database](../../../installation_guide/install_overview/installing_on_unix_based_platforms/installing_securetransport_server_external_db_unix).  
5.  Follow the prompts. Provide all the required information and confirm installation.

The installer displays a progress indicator. It can take several minutes to install SecureTransport. When the installation is complete, the SecureTransport Configuration menu is once again displayed.

Once installed, you can [Configure network settings](../../app_network_config).
