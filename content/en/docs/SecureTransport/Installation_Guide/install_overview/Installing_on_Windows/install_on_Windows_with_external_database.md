{
    "title": "Install SecureTransport Server on Windows with an external database ",
    "linkTitle": "Install SecureTransport Server on Windows with an external database",
    "weight": "120"
}Use this installation procedure to install {{< SecureTransport/componentshortname  >}} on Windows Server where the installation will use an external database server:

-   {{< SecureTransport/componentshortname >}} Server in an Enterprise Cluster
-   Stand-alone {{< SecureTransport/componentshortname >}} Server when an external database server is otherwise required

To use an external database, you need a license for the Enterprise Clustering (EC) option.

Check the pre-installation information and prerequisites before you install.

All the nodes of a {{< SecureTransport/componentshortname  >}} Enterprise Cluster share the same database schema and use the same installation directory and (`taeh`) file. The installer creates that schema when you install the first server in the cluster. You can have the installer create the `taeh` file or import an existing secret file for the first server in the cluster. You must copy the `taeh` file to the second and subsequent servers in the cluster before you install. For more information, see <a href="../../../prereqs_overview/secret_file#beforeinstallst_3365039947_1107715" class="MCXref xref">Secret file</a>.

> **Note:**
>
> In Enterprise Cluster deployments, all your SecureTransport Server nodes must have the same version as your first installed Server node. Do not attempt to add Server nodes to your cluster if the SecureTransport version does not match the one on already installed nodes.

This procedure assumes that {{< SecureTransport/componentshortname  >}} is not installed on the system. Only one instance of {{< SecureTransport/componentshortname  >}} Server or {{< SecureTransport/componentshortname  >}} Edge is supported in a production environment. To upgrade an existing installation, refer to the *{{< SecureTransport/componentshortname  >}} Upgrade Guide*.

During the installation, do not close any console windows that are opened.

1.  Download the {{< SecureTransport/componentshortname >}} install package for Windows from [Axway Support.](https://support.axway.com/)  
    The name of the package is `SecureTransport_5.5_Install_win-x86-64_<BuildNumber>.zip`

2.  Extract the ZIP file to a location on the same drive where you are going to install {{< SecureTransport/componentshortname >}}. The name of the extracted folder is `SecureTransport_5.5_Install_win-x86-64`.

3.  In the extracted folder, run the `setup64.exe` executable to begin the installation process.

4.  The installer loads and displays the *Welcome* page. Click **Next** to proceed.

5.  Read and accept the terms of the license agreement to continue.  
    (Optional) Click **Print** to print out a copy of the license agreement.

6.  Specify the **Installation Directory** to which the installer files to be deployed. It must reside on the same drive as the installation files. You can enter a custom location by using its absolute path.  
      

    > **Note:**
    >
    > The directory path must not contain the tilde (~) character. Also, we recommend using a directory path without special characters and spaces.

      
    In the directory that you specify in this step, the installer installs its files, including the files required to update and uninstall {{< SecureTransport/componentshortname >}} {{< SecureTransport/componentversion >}}. The directory is used as the parent directory of the {{< SecureTransport/componentshortname >}} default installation location.  
    Click **Next** to continue.

7.  On the *Modules* page, click **Next** to install the default Server module.

8.  Specify a location to install {{< SecureTransport/componentshortname >}}. By default, {{< SecureTransport/componentshortname >}} is installed in a sub-directory of the Axway Installer installation directory (specified at step 6). You can either accept the default or specify a new location following the requirements:
    -   The SecureTransport installation directory must be specified using an absolute path. It must not contain the tilde (~) character; letters and digits are acceptable.
    -   It must reside on the same drive as the {{< SecureTransport/componentshortname >}} installation files.
    -   The SecureTransport installation directory and the Axway Installer components must never be in the same directory.

      
    The installer installs {{< SecureTransport/componentshortname >}} into the `STServer` directory in this installation directory. The {{< SecureTransport/componentshortname >}} installation directory is referred to as `<FILEDRIVEHOME>` throughout this document and other {{< SecureTransport/componentshortname >}} documents.  
    Click **Next** to continue.

9.  Select an external database: **External Oracle Database**, **External Microsoft SQL Server Database**, or **External PostgreSQL Database**. Click **Next**.

10. Supply the required database connection parameters. The database settings must be the same for all {{< SecureTransport/componentshortname >}} Servers in a cluster.  
    Depending on the type of database you are connecting to, the required information might vary.  
    -   **Host** – The FQDN or IP address of the system or cluster

    -   **Port** – The number of the port used to access the server or cluster. Defaults: 1521 for Oracle, 1433 for Microsoft SQL Server, 5432 for PostgreSQL.

    -   **Login Name** – The name of the user authorized to create the {{< SecureTransport/componentshortname >}} Specify the storage location of the and populate it. Do not enter a username if {{< SecureTransport/componentshortname >}}

    -   **Password** – The password for the user, not displayed.

    -   **Service Name** – Used to connect to the Oracle server or cluster

    -   **Database Name** – Used to connect to the Microsoft SQL Server or the PostgreSQL

    -   **Use secure connection** - When selected, the database connection will be established over a secure connection. The default value is: **true**

    -   **Server Certificate DN** (Optional) - This is the Server certificate DN value. If provided, the installer will explicitly match the provided value against the certificate provided by the database server.

    -   **TrustStore File Path** - PEM or DER file, or JKS (Java Key Store) keystore containing the trusted certificates needed by the installer to establish a chain of trust.  

        > **Note:**
        >
        > Make sure that all potential certificates for connections between SecureTransport and your database either have no key usage specified or include a Digital Signature key usage extension.

    -   **Certificate File** - the public key certificate file.

    -   **Use Proxy Authentication** - Set this option to `true` to use the native Oracle proxy authentication feature. You also need to provide the user name of the proxied account.

    -   **Use Kerberos mode** - This option is supported only for Oracle databases. When set to `true`, SecureTransport will connect to the database password-less using Kerberos authentication. Note that the Oracle database server must already be configured for Kerberos. Check the <a href="https://docs.axway.com/bundle/SecureTransport_55_AdministratorGuide_allOS_en_HTML5/page/Content/AdministratorsGuide/setup/Configure-Oracle-Kerberos.htm#Prerequi" class="MCXref xref">prerequisites</a>. When configuring Kerberos mode:  
        -   Do not enter **Password** and **Login name**.
        -   Specify the location of the **Kerberos credentials cache file**.
        -   **Use Kerberos configuration file** - When unchecked, SecureTransport copies the file to the `<FDH>/conf` directory and synchronizes it between the nodes. The file can be updated via the *Use the Server Configuration Files* page.  
            When checked, SecureTransport references the Kerberos configuration file directly by specified path. In this case, the file is not synchronized between nodes. You specify it per node. SecureTransport automatically reloads the Kerberos configuration when there’s a change in the file.

11. Select **Use existing database schema** depending on whether you are installing the {{< SecureTransport/componentshortname >}} on a stand-alone server or the first server of an Enterprise Cluster, or on another clustered server:
    -   If you are installing the first server in a cluster or a stand-alone server, do not select **Use existing database schema**. The installer creates the database schema and the `taeh` file.
    -   If you are installing the second or a subsequent server in the cluster, select **Use existing database schema** to use the database schema created when you installed the first server.

      
    Click **Next**.  
    The installer tests the connection to the database. If the installer cannot connect, it displays an error message and you must correct the database settings.

12. When the installer verifies the database connection, it displays the *Configurations* page.  
    If you selected **Use existing database schema** for the second or subsequent server in an Enterprise Cluster, you cannot changes the values of the following three fields.
    -   **SSL Administration Tool Port** – default 444
    -   **Tomcat Shutdown Port** – default 8005

      
    The following field is always available:
    -   **Enable Nightly Log Rotation** – Select if you want the system to perform automatic backup and purging of log files on a nightly basis. When this feature is enabled, Server backups log files, generated on the respective day, and creates a new one for the subsequent day. The server takes a back up and creates a new log file at 23:59 or 00:00 hours, depending on the log file type. This option is enabled by default. You can enable or disable the nightly log rotation after installation - see the for more information.
    -   **Secret File Path**– The path to the `taeh` secret file you copied to this system. If blank, the installer creates a new secret file.
    -   If you are installing the first server in an Enterprise Cluster, you can specify a secret file or have the installer create one. Before you install {{< SecureTransport/componentshortname >}} on the other cluster nodes, you must copy the secret file to those systems.
    -   If you are installing the second or a subsequent server in the cluster, you must use the secret file you copied from the first server. For more information, see <a href="../../../prereqs_overview/secret_file#beforeinstallst_3365039947_1107715" class="MCXref xref">Secret file</a>.
    -   **ClusterAuto-Register IP/FQDN** – To automatically register a node in an Enterprise Cluster, specify it by its IP address or FQDN. Otherwise, leave the field empty. You can add a SecureTransport Server to the cluster at a later stage using the Administration Tool. For more information, see <a href="/bundle/SecureTransport_55_AdministratorGuide_allOS_en_HTML5/page/Content/AdministratorsGuide/large_enterprise_clustering/t_st_add_server_to_cluster.htm" class="MCXref xref">Add a server to a cluster</a>.

      
    Click **Next** to continue.

13. On the *Ready to install* page, click **Install** to start the installation. The installer displays the *Installation in progress* page which shows the progress of the installation.  
    The installation process can take several minutes to complete.

14. Once the {{< SecureTransport/componentshortname >}} installation has completed, the installer displays the *Installation completed* page. Click **Next** to see summary information about your {{< SecureTransport/componentshortname >}} installation.

15. Click **Finish** to exit the installer.  
    You can click **Update** to install patches and service packs without leaving the installer. Refer to the Readme files for the patches or service packs.

The installer also creates a log file, `<AxwayHome>/install.log`.

After successfully installing {{< SecureTransport/componentshortname  >}}, you must perform several post-installation steps, such as updating your {{< SecureTransport/componentshortname  >}} license, enabling, configuring, and starting the {{< SecureTransport/componentshortname  >}} services. For more information, see the .

**Related topics:**

-   <a href="../install_to_use_embedded_database" class="MCXref xref">Install SecureTransport on Windows with the embedded database</a>
-   <a href="../cancel_windows_installation" class="MCXref xref">Cancel the Windows installation</a>
