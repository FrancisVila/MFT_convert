{
    "title": "Integration connectivity via Gateway: Overview",
    "linkTitle": "Integration connectivity via Gateway: Overview",
    "weight": "20"
}[Connectivity services for integrations](#before_you_begin)

[Configuration requirements](#config_overview)

<span id="before_you_begin"></span>

## Connectivity services for integrations

*Integration* involves transforming, enhancing, validating and routing the files and messages that transit in your network, so that they can be used by diverse applications. To perform integration operations, Axway products use the services of Axway Integrator.

*Connectivity* involves packaging, partner definition and transport between applications hosted on diverse platforms inside the enterprise, and partners outside of the enterprise network. To provide connectivity, Axway products use the services of Axway Gateway.

The topics in this book describe how to combine these sets of services in an integrated system of file and message handling.

<span id="config_overview"></span>

## Configuration requirements

### Installation architecture requirements

To provide integration and connectivity in support of your file and message handling requirements, you require the following Axway products:

-   Integrator
-   Gateway
-   Gateway Navigator
-   Composer

You must install the following Axway products on the same host machine:

-   Integrator Server
-   Gateway Server

![](/Images/Gateway/Gg_exmpl_interop_gtwIntegr_756x444.png)

Integrator / Gateway communication architecture

<span id="port_access_and_file_sharing"></span>

### Port access and file sharing requirements

The following figure illustrates port configuration and shared-directory requirements for communication between Integrator and Gateway.

<img src="/Images/Gateway/gtw_intgr_shared_folders.png" class="smallWidth" />

Shared ports and directories

![](/Images/Gateway/g_one_.gif) **Gateway Server Daemon port**

On this port, Gateway listens for remote calls to the CSAPI.

To configure Gateway to listen to remote API calls on this port, refer to [Adding the Integrator Gateway CommAdapter](#).

![](/Images/Gateway/g_two_.gif) **Integrator listening port**

On this port, Integrator listens for incoming notifications from Gateway over a socket connection.

To configure Gateway to send notifications to this port, refer to [Static Gateway configuration](#).

**![](/Images/Gateway/g_three_.gif) Shared directory**

This is a directory located on the shared platform, where Gateway and Integrator deposit undelivered notifications.

**Note**: Integrator and Gateway must share local directories with each other:

-   Integrator shares its `$CORE_DATA/tmp` directory with Gateway
-   Gateway shares its `<Gateway install directory>/run_time/tmp` directory (for the default received files directory) with Integrator
-   Integrator and Gateway share a directory where notifications are stored in stress cases  
    To configure Integrator to use this directory, refer to [Adding the Integrator Gateway CommAdapter](#).  
    To configure Gateway to use this directory, refer to [Static Gateway configuration](#).

### Machine access right requirements

Modify the machine access rights to provide full access to these directories. For example, on UNIX platforms, execute a chmod 777 command on these directories.

Related topics

[Implementing file and message exchange connectivity: General procedure](t_intgr_gtw_wkflointerop)

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
