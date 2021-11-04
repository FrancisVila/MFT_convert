{
    "title": "Install SecureTransport on Unix with the embedded database",
    "linkTitle": "Install SecureTransport on Unix with the embedded database",
    "weight": "100"
}Use this installation procedure to install <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> on UNIX-based platforms where the installation will use the embedded database server:

-   Stand-alone <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server
-   <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server in a Standard Cluster
-   <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge

Check the pre-installation information and prerequisites before you install.

This procedure assumes that <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> is not installed on the system. Only one instance of <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server or <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge is supported in a production environment. To upgrade an existing installation, refer to the *<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Upgrade Guide*.

Log in to the system as the user who will run <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>.

Download the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> install package for your operating system:  
`SecureTransport_5.5_Install_<OS>-<processor>_<BuildNumber>.zip`  
where the placeholders represent the following:

-   `<OS>` is the operating system: `aix` (for IBM AIX), `linux` (for Linux)
-   `<processor>` is the type of processor running the operating system: `power-64` or `x86-64`.
-   `<BuildNumber>` is the actual build number listed in the installer executable file.

Copy the install package into a temporary directory and navigate to that temporary directory.

Extract the installation files using the following commands:

    unzip SecureTransport_5.5_Install_<OS>-<processor>_<BuildNumber>.zip

Enter the following commands to run the <span class="mc-variable axway_variables.Company_Name variable">Axway</span> Installer:

    ./setup.sh -m console

  
The installer initializes and displays a welcome message and a prompt.

Press Enter.  
The installer will display the license agreement page by page.
After each one there is a **Press ENTER to continue** prompt.
After all license agreement pages are displayed, the installer displays the license agreement and the following prompt (for accepting or rejecting the license agreement):

    [1] I accept the terms of the license agreement.
    [2] I do not accept the terms of the license agreement.

    Enter a number [1-2] to select an option or (Previous, Quit).
    :>2

Enter 1 to accept the license agreement. Enter 2 to reject the license agreement and cancel the installation.

On the prompt for Installation directory, specify an installation location for <span class="mc-variable axway_variables.Company_Name variable">Axway</span> installer:  



    ----------------------------------------
                                
    Installation directory
    ----------------------------------------
    Specify the directory where you want to install the products and documentation.
    1: Installation Directory:           /<userHome>/Axway

    Enter 1 to select an option or (Next, Previous, Quit).
    :>Next

  

-   To accept the default installation directory, press Enter. The default installation directory for Axway Installer is `/<userHome>/Axway` , where `<userHome>` represents the home directory of the user running the installation.
-   To change the installation location, enter 1 and then enter the absolute path to your desired installation directory.

  
In this directory, the Axway installer files are deployed. It is used as the parent directory in the default <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> installation location which you specify at a later step (10).  

> **Note:**
>
> SecureTransport should not share the same installer directory with another Axway products.

Choose the installation type. Press Enter to accept the default, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server.  



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

> **Note:**
>
> The EdgeDocker and ServerDocker modules are used ONLY in the docker image build process and are not supported for other purposes. For more information, refer to the SecureTransport Containerized Deployment Guide.

Specify an installation directory for <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>:  



    ----------------------------------------
    Installation directory
    ----------------------------------------
    To specify the directory where the product is installed, type the path directly,
                                or press Enter to select the displayed default.
    1: Select the installation directory for SecureTransport:
    <AxwayHome>/SecureTransport

    Press 1 to change the selected option or (Next, Previous, Quit).
    :>Next

-   To accept the default location, press Enter. The default <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> installation folder is `<AxwayHome>/SecureTransport`, where `<AxwayHome>` is the directory you specified in step 8.
-   To change the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> installation location, enter 1 and enter the absolute path to your desired installation directory.

Consider the following:

-   Do not use the directory where you copied the installer files.
-   All <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Servers in a cluster must use the same installation directory.
-   The name of the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> installation directory cannot contain space characters, the tab character, or the `~` character. For example, `/root/Axway/STServer` is valid, but `/root/Axway/ST   Server` is not.

This installation directory is referred to as `<FILEDRIVEHOME>` throughout this document and other <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> documents.

On the database selection prompt, press Enter to accept the default, the embedded database.  



    ----------------------------------------

     
    Database settings
    ----------------------------------------
    [1] Embedded Database (MariaDB)
    or [1] Embedded Database (MySQL)
    [2] External Oracle Database
    [3] External Microsoft SQL Server Database 
    [4] External PostgreSQL Database
     
    Enter a number [1-4] to select an option or (Previous, Quit).
    :>1

  

> **Note:**
>
> For installation using an external database, see Install SecureTransport Server on Unix with an external database.

The following step depends on whether you are using MySQL or MariaDB.  
**On MySQL**, the installer displays the following dialog:

    ----------------------------------------
    Database settings
    ----------------------------------------
    Provide the settings for the MySQL database:
    1: Port:  33060
     
    Press 1 to change the selected option or (Next, Previous, Quit).
    :>Next

  

The information required is:

-   **Port:** select a new port number for the embedded database installed by SecureTransport or accept the default setting.  

  
**On MariaDB**, provide answers to the following dialog:

    ----------------------------------------
    Provide the settings for the MariaDB database:
    1: Port:                             33060
    2: Use secure connection:            true
    3: Auto generate certificates:       true
    4: Certificate Authority File Path:
    5: Server Private key File Path:
    6: Server Certificate File Path:
     
    Enter a number [1-6] to select an option or (Next, Previous, Quit).
    :>Next

  
The information required is:

-   **Port**: select a new port number for the embedded database installed by SecureTransport, or accept the default setting.
-   **Use secure connection**: When selected, the database connection will be established over a secure connection. The default value is `true`.
    -   **Auto generate certificates**: When set to true, the certificates required for a secure connection to the database will be automatically generated by <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> with a validity period of 365 days. In this case, any value in **Certificate Authority File Path**, **Server Private key File Path** or **Server Certificate File Path** is ignored.
-   **Certificate Authority File Path**: The absolute file path to the CA certificate in PEM format, used to create and sign the Server Private key and Server Certificate files.  
    Only applicable when **Use secure connection** is set to `true` and **Auto generate certificates** is set to `false`.
-   **Server Private key File Path**: A private key in PEM format, used by the MariaDB Server.  
    Only applicable when **Use secure connection** is set to `true` and **Auto generate certificates** is set to `false`.
-   **Server Certificate File Path**: an X.509 certificate in PEM format used by the MariaDB Server.  
    Only applicable when **Use secure connection** is set to `true` and **Auto generate certificates** is set to `false`.

The installer displays the default <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> ports, nightly log rotation, and import secret file configuration:

    ----------------------------------------
    Configuration
    ----------------------------------------
      Select the options that you want to enable:
      SecureTransport Ports
    1: SSL Admin UI Port:           444
    2: Tomcat Shutdown Port:        8005
    3: Enable Nightly Log Rotation: true
      Import Secret File
    To synchronize the configuration of this ST Server with another ST Server you
                                    must import the same secret file (located on the remote ST Server at:
                                    <installation path>/bin/taeh). Otherwise, leave the field empty
                                    to generate a new secret file.
    4: Secret File Path:
              
                                Enter a number [1-4] to select an option or (Next, Previous, Quit).
    :>Next

Accept or modify the default configuration.  
The information required is:

-   **SSL Admin UI Port** – The port used to connect to the Administration Tool. When you install <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> as a non-root user, the default value for Admin port number is 8444.
-   **Tomcat Shutdown Port** – The port used to shut down the Tomcat server
-   **Enable Nightly Log Rotation** – Select if you want the system to perform automatic backup and purging of log files on a nightly basis. When this feature is enabled, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server backups log files, generated on the respective day, and creates a new one for the subsequent day. The server takes a back up and creates a new log file at 23:59 or 00:00 hours, depending on the log file type. This option is enabled by default. You can enable or disable the nightly log rotation after installation. For more information, see the <span class="redirect_st_ag" cshid="admin" data-version="5.3.5">*<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Administrator's Guide*</span>, Server Log Rotation Scheduling.
-   **Secret File Path** – The path to the secret file you copied from another <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> Server installation to this system, if blank, the installer creates a secret file (See <a href="../../../prereqs_overview/secret_file#beforeinstallst_3365039947_1107715" class="MCXref xref">Secret file</a>.)

  
When you have modified these values as required for your installation, press Enter.  
The installer prepares the installation execution and displays its last prompt:

    ----------------------------------------
    Installation execution
    ----------------------------------------
    All selected products are ready to install. Type Next to start installing. If
                                not, type Previous to make changes.
    Enter (Next, Previous, Quit).
    >Next

Press Enter to start the installation.  
The installer displays progress messages as it completes the installation tasks. When the installation is complete, a success message is displayed.

Press Enter to exit the installer or select update mode to apply patches or service packs without leaving the installer.

The installer also creates a log file, `<AxwayHome>/install.log`.

After successfully installing <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>, you must perform a number of post-installation steps, such as applying your <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> licenses, and enabling, configuring, and starting the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> services. For more information, see the <span class="redirect_st_gs" cshid="gs" data-version="5.3.5">*<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Getting Started Guide*</span>.

**Related topics:**

-   <a href="../installing_securetransport_server_external_db_unix" class="MCXref xref">Install SecureTransport Server on Unix with an external database</a>
-   <a href="../running_st_as_service_unix" class="MCXref xref">Run SecureTransport as a service on UNIX-based platforms after non-root installation</a>
