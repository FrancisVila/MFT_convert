{
    "title": "Prerequisites",
    "linkTitle": "Prerequisites",
    "weight": "50"
}Before you proceed, review the *{{< SecureTransport/componentshortname  >}} Release Notes* for any updates to this preinstallation information or the installation and setup procedures.

Review the following information before starting the installer.

## Installation directory

You must install {{< SecureTransport/componentshortname  >}} on local disk storage. Installation on shared storage is not supported. (For more information, see the discussion in the *{{< SecureTransport/componentshortname  >}} Administrator's Guide* of troubleshooting performance issues due to installation on a network drive.) All nodes in an Enterprise Cluster and a Standard Cluster must use the same local installation directory path name. The name of the {{< SecureTransport/componentshortname  >}} installation directory cannot include the ~ character. For example, `/root/Axway/STServer` is valid, but `/root/Axway/ST~Server` is not valid.

> **Note:**
>
> Axway recommends installing SecureTransport in a directory path without spaces in the folder names. Other special characters in the folder names must also be avoided and the tilde (~) character cannot be used.

> **Note:**
>
> SecureTransport server installation on a private SAN logical unit LUN is a supported configuration.

## Services

After all components have been installed, the Admin service is started and, for installations that use the embedded database, the Database service is started. These services are configured according to your responses to the questions the installer asks during the installation procedure. These services are started so an administrator can configure {{< SecureTransport/componentshortname  >}} before starting any additional services.

## Server certificates

During installation, a temporary self-issued CA is generated, and then a temporary *admin* certificate, signed by this CA, is generated.

## Administration accounts

 The installer creates the following default accounts with a default user name and password:

-   Master Administrator account "`admin/admin`".
-   Setup Administrator "`setup/setup`" for the initial, one-time configuration of the system.
-   Database Setup Administrator "`dbsetup/dbsetup`" for access to the *Database Settings* page when the database is not running.
-   Account Manager "`account/account`" who can create and manage user access and export and import accounts.
-   Application Manager "`application/application`" who can create service accounts and create and configure applications.

> **Note:**
>
> For better security, change the default passwords or disable the accounts that are not used.

## Port numbers

 The installer suggests the port numbers listed below for the {{< SecureTransport/componentshortname  >}} server ports:

-   The embedded database port number – `33060`  
    This port is used for {{< SecureTransport/componentshortname >}} Edge, for {{< SecureTransport/componentshortname >}} Server Standard Clustering installations, and for {{< SecureTransport/componentshortname >}} Server stand-alone installations that use the embedded database. You can change this port after installation using the Administration Tool.
-   Oracle database listener port number –`1521`  
    This port is used for {{< SecureTransport/componentshortname >}} Server Enterprise Cluster installations that use an external Oracle database. You can change this port after installation using the Administration Tool.
-   PostgreSQL database listener port number –`5432`  
    This port is used for {{< SecureTransport/componentshortname >}} Server Enterprise Cluster installations that use an external PostgreSQL database. You can change this port after installation using the Administration Tool.
-   Microsoft SQL Server port number – `1433`  
    This port is used for {{< SecureTransport/componentshortname >}} Server Enterprise Cluster installations that use an external Microsoft SQL Server database. You can change this port after installation using the Administration Tool.
-   Admin port number – `444`  
    This is the port that the web server for the Administration Tool listens to. You must specify the Admin port number in the URL when accessing the Administration Tool, using the form, `https://<hostname>:<Admin port>/`. If you are installing {{< SecureTransport/componentshortname >}} on a UNIX-based server to run as a non-root user, 8000 is added to port numbers that are below 1024, so the default Admin port number is 8444.
-   Tomcat JK port number – `8009`  
    This is the port that the Coyote JK Connector, the internal module of the admin server that handles the execution of servlets and JSP pages, listens to. It must be greater than 1024.
-   Tomcat shutdown port number – `8005`  
    This is the port on which the admin server waits for a shutdown command.

> **Note:**
>
> After installation, the SecureTransport admin server also uses port 8004 to communicate with the Tomcat application server. If port 8004 is in use by another process, change the Admin.Http.Port system configuration parameter on the Server Configuration page and stop and restart the admin server.

## Service packs and patches

Check {{< SecureTransport/companyname  >}} Support at <a href="https://support.axway.com/" class="hyperlink">support.axway.com</a> to determine if you need to apply any service packs or patch after you install {{< SecureTransport/componentshortname  >}} and before you configure it. You can download the service pack and patch files to the system where you will install {{< SecureTransport/componentshortname  >}} before you start the installation and apply them at the end of the installation without leaving the installer.

## System requirements

The following are the system requirements for {{< SecureTransport/componentshortname  >}}.

-   Supported operating systems and versions. This also can include virtualization platforms.
-   Supported databases types and versions.
-   Hardware requirements, including RAM and disk space.
-   Supported network storage (for example, network-attached storage (NAS) or storage area network (SAN) and supported file systems.
-   Reference that describes the license keys required to perform the product installation.
-   Supported browsers for the product.

**Related topics:**

The following topics provide the {{< SecureTransport/componentshortname  >}} installation prerequisites:

-   <a href="virtualization_support" class="MCXref xref">Virtualization support</a>
-   <a href="secret_file" class="MCXref xref">Secret file</a> - prerequisites for {{< SecureTransport/componentshortname >}} Servers and {{< SecureTransport/securetransportname >}} Edges.
-   <a href="database_installation_prerequisites" class="MCXref xref">Database requirements</a>
-   <a href="installation_prerequisites_for_unix_based_servers" class="MCXref xref">General prerequisites for UNIX-based platforms</a>
-   <a href="installation_prerequisites_for_windows" class="MCXref xref">Windows platforms</a>
