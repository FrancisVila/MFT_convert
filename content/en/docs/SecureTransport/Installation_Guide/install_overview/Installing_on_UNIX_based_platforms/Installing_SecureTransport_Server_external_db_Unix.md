{
    "title": "Install SecureTransport Server on Unix with an external database",
    "linkTitle": "Install SecureTransport Server on Unix with an external database",
    "weight": "110"
}Use this installation procedure to install SecureTransport on UNIX-based platforms where the installations will use an external database server:

-   SecureTransport Server in an Enterprise Cluster
-   Stand-alone SecureTransport Server when an external Oracle, PostgreSQL, or Microsoft SQL Server database server is otherwise required

To use an external database, either in single or in multi-node environment, you need a license for the Enterprise Clustering (EC) option.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The <span>SecureTransport</span> Enterprise Cluster installation will fail if the database password contains the dollar sign (<code>$</code>) and other special characters. The password for the PostgreSQL database cannot contain any of the following symbols: <code>%</code>, <code>&amp;</code> or <code>+</code>. The password for SQL Server cannot contain curly brackets (<code>{</code>,<code>}</code>)         </td>
      </tr>
</table>

Check the pre-installation information and prerequisites before you install.

All the nodes of a SecureTransport Enterprise Cluster share the same database schema and use the same installation directory and secret (`taeh`) file. The installer creates that schema when you install the first server in the cluster. You can have the installer create the `taeh` file or import an existing file for the first server in the cluster. You must copy and import the `taeh` file to the second and subsequent servers in the cluster before you install. For more information, see [Secret file](../../../prereqs_overview/secret_file).

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

1.  Log in to the system as the user who will run SecureTransport.

2.  Download the SecureTransport install package for your operating system:  
    `SecureTransport_5.5_Install_<OS>-<processor>_<BuildNumber>.zip`
      
    where the placeholders represent the following:
    -   `<OS>` is the operating system: `aix` (for IBM AIX), `linux` (for Linux)
    -   `<processor>` is the type of processor running the operating system: `power-64` or `x86-64`.
    -   `<BuildNumber>` is the actual build number listed in the installer executable file.

3.  Copy the install package into a temporary directory and navigate to that temporary directory.

4.  Extract the installation files using the following command:

        unzip SecureTransport_5.5_Install_<OS>-<processor>_<BuildNumber>.zip

5.  Enter the following command to run the Axway Installer:

        ./setup.sh -m console

      
    The installer initializes and displays a welcome message and a prompt.

6.  Press Enter.  
    The installer will display the license agreement page by page.
    After each one there is a **Press ENTER to continue** prompt.
    After all license agreement pages are displayed, the installer displays the following prompt (for accepting or rejecting the license agreement):

        [1] I accept the terms of the license agreement.
        [2] I do not accept the terms of the license agreement.
        Enter a number [1-2] to select an option or (Previous, Quit).
        :>2

7.  Enter 1 to accept the license agreement. Enter 2 to reject it and cancel the installation.

8.  On the prompt for the Axway installer directory:  
    

    -   To accept the default installation directory, press Enter. The default installation directory for Axway Installer is `/<userHome>/Axway` , where `<userHome>` represents the home directory of the user running the installation.
    -   To change the installation location, enter 1 and then enter the absolute path to your desired installation directory.

      
    In this directory, the Axway installer files are deployed. It is used as the parent directory for the default SecureTransport installation location which you specify at a later step (10).  
    

    <table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top"><span>SecureTransport</span> should not share the same installer directory with another Axway products.         </td>
      </tr>
</table>

9.  Choose the installation type. Press Enter to accept the default, SecureTransport Server.  
    

        ----------------------------------------
        Modules
        ----------------------------------------
        Select the modules you want to install, then type Next to continue the
                                    configuration.

        Axway SecureTransport V5.5:
        1 :[x] Server
        2 :[ ] Edge
        3 :[ ] ServerDocker
        4 :[ ] EdgeDocker
        Enter a number[1-4] (Next, Previous, Quit)
        :>Next

    <table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The <code>EdgeDocker</code> and <code>ServerDocker</code> modules  are used <b>ONLY</b> in the docker image build process and are not supported for other purposes. For more information, refer to the <span>SecureTransport</span> Containerized Deployment Guide.         </td>
      </tr>
</table>

10. Specify the SecureTransport installation directory:
      
    
    -   To accept the default location, press Enter. The default SecureTransport installation folder is `<AxwayHome>/SecureTransport`, where `<AxwayHome>` is the directory you specified in the previous installation directory step.
    -   To change the SecureTransport installation location, enter 1 and enter the absolute path to your desired installation directory.
          
        Consider the following:   
        
        -   Do not use the directory where you copied the installer files.
        -   All SecureTransport Servers in a cluster must use the same installation directory.
        -   The name of the SecureTransport installation directory cannot contain space characters, the tab character, or the `~` character. For example, `/root/Axway/STServer` is valid, but `/root/Axway/ST   Server` is not.

11. On the database selection prompt, select the external database type for SecureTransport to use.

    <table cellpadding="0" cellspacing="0">   <col/>   <col/>   <col/>      <tr>         <td valign="top">         </td>         <td valign="top"><span><b>Note</b></span>         </td>         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">For installation using the embedded database, see <a href="../installing_securetransport_embedded_db_unix" xrefformat="{paratext}">Install SecureTransport to use the embedded database</a>.         </td>      </tr></table>

12. Supply the database settings. Depending on the type of database you are connecting to, the required settings vary.  
    
    -   **Host** – The FQDN or IP address of the system or cluster

    -   **Port** – The number of the port used to access the server or cluster. Defaults: 1521 for Oracle, 1433 for Microsoft SQL Server, 5432 for PostgreSQL.

    -   **Login Name** – The name of the user authorized to create the SecureTransport schema and populate it

    -   **Password** – The password for the user, not displayed.

    -   **Service Name** – Used to connect to the Oracle server or cluster

    -   **Database Name** – Used to connect to the Microsoft SQL Server or the PostgreSQL Server

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
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Make sure that all potential certificates for connections between <span>SecureTransport</span> and your  database either have no key usage specified or include a Digital Signature key usage extension.         </td>
      </tr>
</table>

    -   **Certificate File** - The public key certificate file. TrustStore files are not supported for PosgreSQL.

    -   **Use Proxy Authentication** - Set this option to `true` to use the native Oracle proxy authentication feature. You also need to provide the user name of the proxied account.

    -   **Use Kerberos mode** - This option is supported only for Oracle databases. When set to `true`, SecureTransport will connect to the database password-less using Kerberos authentication. Note that the Oracle database server must already be configured for Kerberos. Check the [prerequisites](https://docs.axway.com/bundle/SecureTransport_55_AdministratorGuide_allOS_en_HTML5/page/Content/AdministratorsGuide/setup/Configure-Oracle-Kerberos.htm#Prerequi). When configuring Kerberos mode:  
        
        -   Do not enter **Password** and **Login name**.
        -   If you want SecureTransport to refer to the Kerberos configuration file `(krb5.conf`) directly from the specified location, check the **Use Kerberos configuration file** checkbox. If this option is unchecked, SecureTransport will copy the file locally during installation and synchronize it between nodes using the System Configuration Files functionality.
        -   Specify the storage location of the **Kerberos configuration file** (`krb5.conf`).
        -   Specify the storage location of the **Kerberos credentials cache file**

    -   **Use Kerberos configuration file**: the specified Kerberos configuration file (ktb5.conf) will be used to establish the connection.  
        For more information, refer to [Connect to Oracle database using Kerberos Authentication](https://docs.axway.com/bundle/SecureTransport_55_AdministratorGuide_allOS_en_HTML5/page/Content/AdministratorsGuide/setup/Configure-Oracle-Kerberos.htm) in the SecureTransport 5.5 Administrator's Guide.

13. The value for **Use existing database schema** depends on whether you are installing the SecureTransport on a stand-alone server or the first server of an Enterprise Cluster, or on another clustered server:
    -   If you are installing the first server in a cluster or a stand-alone server, accept the default so that the installer creates the database schema.
    -   If you are installing the second or a subsequent server in the cluster, set **Use existing database schema** to `true` to use the database schema created when you installed the first server.

      
    When you have entered all the settings, press **Enter** to accept the values.  
    The installer tests the connection to the database. If the installer cannot connect, it displays an error message and you must correct the database settings.

14. When the installer verifies the database connection, it displays the default SecureTransport ports, nightly log rotation, and import secret file configuration:

15. Accept or modify the default settings.  
    If you selected **Use existing database schema** for the second or subsequent server in an Enterprise Cluster, the following three fields are not available.
    -   **SSL Admin UI Port** – The port used to connect to the Administration Tool. When you install SecureTransport as a non-root user, the default value for Admin port number is 8444.
    -   **Tomcat Shutdown Port** – The port used to shut down the Tomcat server

      
    The following field is always available:
    -   **Enable Nightly Log Rotation** – Select if you want the system to perform automatic backup and purging of log files on a nightly basis. When this feature is enabled, SecureTransport Server backups log files, generated on the respective day, and creates a new one for the subsequent day. The server takes a back up and creates a new log file at 23:59 or 00:00 hours, depending on the log file type. This option is enabled by default. You can enable or disable the nightly log rotation after installation. For more information, see the <span cshid="admin" data-version="5.3.5">*SecureTransport Administrator's Guide*</span>.
    -   **Secret File Path** – The path to the secret (`taeh`)file you copied to this system. If you leave it blank, the installer creates a new secret file.
    -   If you are installing the first server in an Enterprise Cluster, you can specify a secret file or have the installer create one. Before you install SecureTransport on the other cluster nodes, you must copy the secret file to those systems.
    -   If you are installing the second or a subsequent server in the cluster, you must use the secret file you copied from the first server. For more information, see [Secret file](../../../prereqs_overview/secret_file).
    -   **ClusterAuto-Register IP/FQDN** – To automatically register a node in an Enterprise Cluster, specify it by its IP address or FQDN. Otherwise, leave the field empty. You can add a SecureTransport Server to the cluster at a later stage using the Administration Tool. For more information, see [Add a server to a cluster](https://docs.axway.com/bundle/SecureTransport_55_AdministratorGuide_allOS_en_HTML5/page/Content/AdministratorsGuide/large_enterprise_clustering/t_st_add_server_to_cluster.htm).

      
    When you have modified these values as required for your installation, press **Enter**.  
    The installer prepares the installation execution and displays its last prompt:

16. Press **Enter** to start the installation.  
    The installer displays progress messages as it completes the installation tasks. When the installation is complete, a success message is displayed.

17. Press **Enter** to exit the installer or select update mode to apply patches or service packs without leaving the installer.

The installer also creates a log file, `<AxwayHome>/install.log`.

After successfully installing SecureTransport, you must perform a number of post-installation steps, such as applying your SecureTransport licenses, and enabling, configuring, and starting the SecureTransport services. For more information, see the <span cshid="gs" data-version="5.3.5">*SecureTransport Getting Started Guide*</span>.

**Related topics:**

-   [Install SecureTransport to use the embedded database](../installing_securetransport_embedded_db_unix)
-   [Run SecureTransport as a service on UNIX-based platforms after non-root installation](../running_st_as_service_unix)
