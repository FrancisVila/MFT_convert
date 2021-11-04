{
    "title": "Install SecureTransport on the appliance",
    "linkTitle": "Install SecureTransport",
    "weight": "80"
}You use the Appliance Console menu to install <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> on the appliance. Installation on the appliance offers you most of the same options as other UNIX-based installations. For example, you can install <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server or Edge using an embedded database server in a Standard Cluster or stand-alone. Alternatively, you can use an external database in an Enterprise Clustering (EC) option. Regardless of the setup, you must have a license.

Check the pre-installation information and prerequisites before you install.

This procedure is an example of the interaction when <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server is not already installed on the system. Multiple instances of <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server or Edge are not supported.

1.  Open the Appliance Console Menu. Do the following:
    -   Connect to your virtual appliance.
2.  On the Appliance Console Menu, enter **C** (SecureTransport Configuration) to display the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Configuration menu.
3.  Enter **I** (Install <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>) to begin installation.
4.  Choose your setup preference from the available options:
    -   Single — Install <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> on a single machine in standalone mode. Standalone <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> uses the embedded database.
    -   Enterprise Cluster — Install <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> as a node in an Enterprise cluster: either as Server or Edge. This option requires a PostgreSQL, Oracle or Microsoft SQL Server database and a license for the Enterprise Cluster option.
    -   Standard Cluster — Install <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> as a node in a Standard cluster: either as Server or Edge. This option uses the embedded database.

      
    For *embedded database* installation, see [Install SecureTransport on Unix with the embedded database](https://docs.axway.com/bundle/SecureTransport_55_InstallationGuide_allOS_en_HTML5/page/Content/InstallationGuide/install/Installing_SecureTransport_embedded_db_Unix.htm). For *external database* installation, see [Install SecureTransport Server on Unix with an external database](https://docs.axway.com/bundle/SecureTransport_55_InstallationGuide_allOS_en_HTML5/page/Content/InstallationGuide/install/Installing_SecureTransport_Server_external_db_Unix.htm).  
5.  Follow the prompts. Provide all the required information and confirm installation.

The installer displays a progress indicator. It can take several minutes to install <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>. When the installation is complete, the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Configuration menu is once again displayed.

Once installed, you can <a href="../../app_network_config" class="MCXref xref">Configure network settings</a>.
