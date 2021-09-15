{
    "title": "Install SecureTransport Server on Windows with an external database",
    "linkTitle": "Install SecureTransport Server on Windows with an external database",
    "weight": "120"
}Use this installation procedure to install SecureTransport on Windows Server where the installation will use an external database server:

-   SecureTransport Server in an Enterprise Cluster
-   Stand-alone SecureTransport Server when an external database server is otherwise required

To use an external database, you need a license for the Enterprise Clustering (EC) option.

Check the pre-installation information and prerequisites before you install.

All the nodes of a SecureTransport Enterprise Cluster share the same database schema and use the same installation directory and secret (`taeh`) file. The installer creates that schema when you install the first server in the cluster. You can have the installer create the `taeh` file or import an existing secret file for the first server in the cluster. You must copy the `taeh` file to the second and subsequent servers in the cluster before you install. For more information, see [Secret file](../../../prereqs_overview/secret_file).

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">In Enterprise Cluster deployments, all your SecureTransport Server nodes must have the same version as your first installed Server node. Do not attempt to add Server nodes to your cluster if the SecureTransport version does not match the one on already installed nodes.         </td>
      </tr>
</table>

This procedure assumes that SecureTransport is not installed on the system. Only one instance of SecureTransport Server or SecureTransport Edge is supported in a production environment. To upgrade an existing installation, refer to the *SecureTransport Upgrade Guide*.

During the installation, do not close any console windows that are opened.

1.  Download the SecureTransport install package for Windows from [Axway Support.](https://support.axway.com/)  
     The name of the package is `SecureTransport_5.5_Install_win-x86-64_<BuildNumber>.zip`

2.  Extract the ZIP file to a location on the same drive where you are going to install SecureTransport. The name of the extracted folder is `SecureTransport_5.5_Install_win-x86-64`.

3.  In the extracted folder, run the `setup64.exe` executable to begin the installation process.

4.  The installer loads and displays the *Welcome* page. Click **Next** to proceed.

5.  Read and accept the terms of the license agreement to continue.
      
    (Optional) Click **Print** to print out a copy of the license agreement.

6.  Specify the **Installation Directory** to which the installer files to be deployed. It must reside on the same drive as the installation files. You can enter a custom location by using its absolute path.  
      
    

    <table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The directory path must not contain the tilde (~) character. Also, we recommend using a directory path without special characters and spaces.          </td>
      </tr>
</table>

      
     In the directory that you specify in this step, the installer installs its files, including the files required to update and uninstall SecureTransport 5.5. The directory is used as the parent directory of the SecureTransport default installation location.   
    Click **Next** to continue.

7.  On the *Modules* page, click **Next** to install the default Server module.

8.  Specify a location to install SecureTransport. By default, SecureTransport is installed in a sub-directory of the Axway Installer installation directory (specified at step 6). You can either accept the default or specify a new location following the requirements:
    -   The SecureTransport installation directory must be specified using an absolute path. It must not contain the tilde (~) character; letters and digits are acceptable.
    -   It must reside on the same drive as the SecureTransport installation files.
    -   The SecureTransport installation directory and the Axway Installer components must never be in the same directory.

      
    
    The installer installs SecureTransport into the `STServer` directory in this installation directory. The SecureTransport installation directory is referred to as `<FILEDRIVEHOME>` throughout this document and other SecureTransport documents.  
    Click **Next** to continue.

9.  Select an external database: **External Oracle Database**, **External Microsoft SQL Server Database**, or **External PostgreSQL Database**. Click **Next**.

10. Supply the required database connection parameters. The database settings must be the same for all SecureTransport Servers in a cluster.  
    
    Depending on the type of database you are connecting to, the required information might vary.
      
    
    -   **Host** – The FQDN or IP address of the system or cluster

    -   **Port** – The number of the port used to access the server or cluster. Defaults: 1521 for Oracle, 1433 for Microsoft SQL Server, 5432 for PostgreSQL.

    -   **Login Name** – The name of the user authorized to create the SecureTransport Specify the storage location of the and populate it. Do not enter a username if SecureTransport

    -   **Password** – The password for the user, not displayed.

    -   **Service Name** – Used to connect to the Oracle server or cluster

    -   **Database Name** – Used to connect to the Microsoft SQL Server or the PostgreSQL

    -   **Use secure connection** - When selected, the database connection will be established over a secure connection. The default value is: **true**

    -   **Server Certificate DN** (Optional) - This is the Server certificate DN value. If provided, the installer will explicitly match the provided value against the certificate provided by the database server.

    -   **TrustStore File Path** - PEM or DER file, or JKS (Java Key Store) keystore containing the trusted certificates needed by the installer to establish a chain of trust.
          
        

        <table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The  PostgreSQL database password cannot contain any of the following symbols: <code>%</code>, <code>&amp;</code> or <code>+</code>. The MSSQL password can contain any special symbols except curly braces <code>}{</code>.                      </td>
      </tr>
</table>

    -   **Certificate File** - the public key certificate file.

    -   **Use Proxy Authentication** - Set this option to `true` to use the native Oracle proxy authentication feature. You also need to provide the user name of the proxied account.

    -   **Use Kerberos mode** - This option is supported only for Oracle databases. When set to `true`, SecureTransport will connect to the database password-less using Kerberos authentication. Note that the Oracle database server must already be configured for Kerberos. Check the [prerequisites](https://docs.axway.com/bundle/SecureTransport_55_AdministratorGuide_allOS_en_HTML5/page/Content/AdministratorsGuide/setup/Configure-Oracle-Kerberos.htm#Prerequi). When configuring Kerberos mode:  
        
        -   Do not enter **Password** and **Login name**.
        -   Specify the storage location of the **Kerberos configuration file** (`krb5.conf`).
        -   If you want SecureTransport to refer to the Kerberos configuration file `(krb5.conf`) directly from the specified location, check the **Use Kerberos configuration file** checkbox. If this option is unchecked, SecureTransport will copy the file locally during installation and synchronize it between nodes using the System Configuration Files functionality.
        -   Specify the storage location of the **Kerberos credentials cache file**

    -   **Use Kerberos configuration file**: the specified Kerberos configuration file (ktb5.conf) will be used to establish the connection.  
        For more information, see [Connect to Oracle database using Kerberos Authentication](../../../../administrator_guide/c_st_setup/c_st_database/configure-oracle-kerberos) in the SecureTransport 5.5 Administrator's Guide.

11. Select **Use existing database schema** depending on whether you are installing the SecureTransport on a stand-alone server or the first server of an Enterprise Cluster, or on another clustered server:
    -   If you are installing the first server in a cluster or a stand-alone server, do not select **Use existing database schema**. The installer creates the database schema and the `taeh` file.
    -   If you are installing the second or a subsequent server in the cluster, select **Use existing database schema** to use the database schema created when you installed the first server.

      
    Click **Next**.  
    The installer tests the connection to the database. If the installer cannot connect, it displays an error message and you must correct the database settings.

12. When the installer verifies the database connection, it displays the *Configurations* page.  
    If you selected **Use existing database schema** for the second or subsequent server in an Enterprise Cluster, you cannot changes the values of the following three fields.
    -   **SSL Administration Tool Port** – default 444
    -   **Tomcat Shutdown Port** – default 8005

      
    The following field is always available:
    -   **Enable Nightly Log Rotation** – Select if you want the system to perform automatic backup and purging of log files on a nightly basis. When this feature is enabled, Server backups log files, generated on the respective day, and creates a new one for the subsequent day. The server takes a back up and creates a new log file at 23:59 or 00:00 hours, depending on the log file type. This option is enabled by default. You can enable or disable the nightly log rotation after installation - see the <span cshid="admin" data-version="5.3.5">*SecureTransport Administrator's Guide*</span> for more information.
    -   **Secret File Path**– The path to the `taeh` secret file you copied to this system. If blank, the installer creates a new secret file.
    -   If you are installing the first server in an Enterprise Cluster, you can specify a secret file or have the installer create one. Before you install SecureTransport on the other cluster nodes, you must copy the secret file to those systems.
    -   If you are installing the second or a subsequent server in the cluster, you must use the secret file you copied from the first server. For more information, see [Secret file](../../../prereqs_overview/secret_file).
    -   **ClusterAuto-Register IP/FQDN** – To automatically register a node in an Enterprise Cluster, specify it by its IP address or FQDN. Otherwise, leave the field empty. You can add a SecureTransport Server to the cluster at a later stage using the Administration Tool. For more information, see [Add a server to a cluster](../../../../administrator_guide/c_st_largeenterpriseclustering/t_st_largeenterprisecluster/t_st_add_server_to_cluster).

      
    Click **Next** to continue.

13. On the *Ready to install* page, click **Install** to start the installation. The installer displays the *Installation in progress* page which shows the progress of the installation.  
    The installation process can take several minutes to complete.

14. Once the SecureTransport installation has completed, the installer displays the *Installation completed* page. Click **Next** to see summary information about your SecureTransport installation.

15. Click **Finish** to exit the installer.  
    You can click **Update** to install patches and service packs without leaving the installer. Refer to the Readme files for the patches or service packs.

The installer also creates a log file, `<AxwayHome>/install.log`.

After successfully installing SecureTransport, you must perform several post-installation steps, such as updating your SecureTransport license, enabling, configuring, and starting the SecureTransport services. For more information, see the <span cshid="gs" data-version="5.3.5">*SecureTransport Getting Started Guide*</span>.

**Related topics:**

-   [Install SecureTransport Server on Windows with the embedded database](../install_to_use_embedded_database)
-   [Cancel the Windows installation](../cancel_windows_installation)
