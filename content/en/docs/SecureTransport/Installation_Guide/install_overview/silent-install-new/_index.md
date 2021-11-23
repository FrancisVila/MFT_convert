{
    "title": "Silent installation of SecureTransport",
    "linkTitle": "Silent installation",
    "weight": "100"
}You can install SecureTransport Server or Edge in a Windows or Linux environment using a silent installation file. The purpose of using a silent file is to quickly duplicate an installation on multiple machines without running the Installer and entering the same parameters over and over again. The Installer's silent mode takes these values from existing or generated silent files. Before you can use this procedure, you must have the necessary silent files available.

1.  Generate the files needed for a silent installation - the Installer silent file and the SecureTransport configuration file.
2.  Edit the SecureTransport configuration file to specify the options for your installation.
3.  Install SecureTransport on the new environment using the Installer silent file.

## Generate the files needed for a silent installation

1.  Start the {{< SecureTransport/componentshortname >}} installation in console or GUI mode and perform configuration until just before you click **Install**.  
    This adds two `.properties` files under `<installation_root_directory>\SilentFile\<date_and_time>_install\`:  
    -   `Install_Axway_Installer_<installer-version>.properties` - the Installer silent file that you use to run a silent installation.
    -   `Install_SecureTransport_<st-version>.properties` - the SecureTransport property file that defines the options for installing SecureTransport.

2.  Open the `Axway_Installer` properties file and scroll to the end. You will see `IncludeFiles` specifying the product for installation; in the case of SecureTransport 5.5, the following declaration must be present:  


        IncludeFiles.SecureTransport = Install_SecureTransport_V5.5.properties

Do not modify anything else in the Axway\_Installer properties file except the `InstallDir` (the location of the installer files, used as a parent directory for the SecureTransport installation) and list of `IncludeFiles` (the Axway products to install).

## Modify the SecureTransport .properties file

The SecureTransport properties file, `Install_SecureTransport_<st-version>.properties`, is used to feed in the installation parameters, such as the module to install (Edge or Server), the database to use (embedded or external), the type of installation (root or non-root). The file consists of a list of key-value pairs, which are described in the [Configurable properties for silent installation](silent-install-properties) topic. It can be edited via any text editor but if you want to change the value of an encrypted property, you must use the Silent file editor tool.

The SecureTransport properties file also contains sensitive information, such as passwords, which must be supplied encrypted. The encryption algorithm is defined by the `Format`property, the default is AES128.

For example,

oraclePassword = YourEncryptedPassword

oraclePassword.Format = AES128

To disable the encryption of the password, delete the corresponding `Format` property.

<span id="Silent"></span>

### Silent File Editor

The Silent File Editor is a tool dedicated to editing your {{< SecureTransport/componentshortname  >}} `.properties` file. It is located in the directory where the SecureTransport installation files are, in `Tools/SilentFileEditor`.

-   For Windows, there are two batch files: `SilentFileEditor.bat` and `SilentFileEditorGUI.bat`.
-   For Unix, the script file is called `SilentFileEditor.sh`.

Before you run any of those files, you have to open it in an editor like Notepad and replace `"<JAVA_HOME>"` with either the `$JAVA_HOME` variable or the full path to the supported Java version (for example, `/opt/java/bin`).

#### Usage

To modify a silent file using the command line, run the script file at `<installation directory>\Tools\SilentFileEditor`.

The parameters for the Silent File Editor are:

-   The path to the silent file that you want to modify
-   Three arguments in this format:
    -   The first argument is the name of the property that you want to modify (for example, ). Each property name given must exist in the silent file.
    -   The second argument is the value that you want to assign to the property given as the first argument.
    -   The third argument is `-c` if the value is to be encrypted first and then saved in the silent file, or `-u` if the value does not need to be encrypted. Note that the encryption can only happen at the server on which SecureTransport will be installed.

Here is typical example of silent file editor usage:



    ./SilentFileEditor.sh $ST_SILENT_FILE_PATH InstallDir $ST_INSTALLDIR  -u mssqlPort $DB_PORT_NUMBER -u mssqlLoginName $DB_USER -u mssqlPassword $DB_USER_PASSWORD -c mssqlDatabaseName $DB_NAME -u mssqlHost $DB_HOSTNAME -u

Where:

-   `$ST_SILENT_FILE_PATH` is the path to silent file
-   `$ST_INSTALLDIR` is the path where SecureTransport should be installed
-   `$DB_PORT_NUMBER` is the database port number
-   `$DB_USER` is the database username
-   `$DB_USER_PASSWORD` is the database password in plaintext.
-   `$DB_NAME` is the database name
-   `$DB_HOSTNAME` is the database hostname

 

**Notes**

-   Silent file editor is only setting plain or encrypted values to keys.
-   Silent file editor cannot add new keys.
-   Silent file editor does not check if the name of the key is valid.

If needed, you can edit this file to specify different options for your installation.

## Install {{< SecureTransport/componentshortname  >}} in silent mode

Before you start the silent installation on a cluster node, review the information in [Recommendations for Clustered SecureTransport deployments](#Silent2).

Follow the instructions to install from a command line using the Installer silent file.

1.  Copy the silent files and the installation package that you used for the first installation to the new environment.
2.  Unzip the package in an empty folder.
3.  Go to the installation package directory.
4.  Run the Installer in Silent mode using the following commands:  
    -   UNIX:  
        `# ./setup.sh -s <the absolute path to the Installer silent file Install_Axway_Installer_<version>.properties>`
    -   Windows:  
        `setup64.exe -s <the absolute path to the Installer silent file Install_Axway_Installer_<version>.properties>`

<span id="Silent2"></span>

### Recommendations for Clustered {{< SecureTransport/componentshortname  >}} deployments

This subtopic contains instructions and tips to aid you to silently install {{< SecureTransport/componentshortname  >}} (Server and Edge) in clustered deployments:

-   Standard Cluster
-   Enterprise Cluster (EC) with external databases

<span id="silent_standard_cl"></span>

#### Silent installation on Standard Cluster nodes

With Standard Cluster, after you perform silent installation on your first node, you can re-use the

`Install_SecureTransport_<st-version>.properties` file for silent installation of all other nodes.

Standard Cluster works with an embedded MariaDB database (or MySQL, only on AIX). No additional edits are required. See [MariaDB- and MySQL-specific configurable properties](silent-install-properties#MariaDB-)

#### Silent installation on Enterprise Cluster nodes

In Enterprise Cluster deployments, all your SecureTransport Server nodes must have the same version as your first installed Server node. Do not attempt to add Server nodes to your cluster if the SecureTransport version does not match the one on already installed nodes.

Enterprise Cluster (EC) deployments offer the use of external databases which adds some additional steps in performing successful silent installation on all nodes. To simplify this process, you can separate the {{< SecureTransport/componentshortname  >}} Server deployments apart from the deployments. The big difference is that Server nodes are in an EC deployment (using an external database) while Edge nodes are in Standard Cluster deployment (using an embedded database).

When using external databases (Oracle, MSSQL, or PostgreSQL) you must make sure the correct values are added to the respective properties, as listed in the [table](silent-install-properties#Configur).

 

**Related topics:**

-   [Configurable properties for silent installation](silent-install-properties)
-   [Example silent installation files: SecureTransport Server with MariaDB database on Windows](silent-install-example-mariadb)
-   [Example silent installation files: SecureTransport Server with Oracle database on a Linux cluster](silent-install-cluster-externaldb)
