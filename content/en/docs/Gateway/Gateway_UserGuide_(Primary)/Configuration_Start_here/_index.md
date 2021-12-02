{
    "title": "Configuration",
    "linkTitle": "Configuration",
    "weight": "60"
}{{< Gateway/componentlongname  >}}: Configuration

[Overview](#Overview)

[Platform support](#Platform_support)

[Network clients](#Network_clients)

<span id="Overview"></span>

## Overview

After installing a new version of Gateway, you need to configure it.

Although default parameters are always provided, you should verify and set the parameters for each component depending on your operational requirements.

The Gateway configuration menu enables you to make modifications to configuration parameters while Gateway is running.

Many of the modifications are taken into account immediately without having to shut down Gateway. This feature improves Gateway availability by reducing the need for shutdowns. However, after changing certain configuration parameters, you need to shut down Gateway for them to be taken into account. In this case a warning message is displayed.

<span id="Platform_support"></span>

## Platform support

Linux and Windows support the following Gateway features:

-   PEL
-   PeSIT HS D and E
-   OFTP (Odette)
-   FTP
-   SFTP
-   HTTP
-   SMTP
-   POP3
-   TCP/IP
-   RAS \*
-   SNA LU 6.2
-   TCP Server
-   Axway MFT Navigator (formerly IUI) Server
-   SSL/TLS
-   EDIINT AS1
-   EDIINT AS2
-   EDIINT AS3
-   RosettaNet
-   SWIFTNet
-   JMS
-   X.400 (X.420)

\* Windows platforms only

For specific platform versions, refer to the {{< Gateway/docnamesuitesupportedplatforms  >}} document.

<span id="Network_clients"></span>

## Network clients

This version of Gateway supports two types of network client:

-   *TCP/IP clients* that communicate via TCP/IP protocol
-   *Axway MFT Navigator clients* that deploy Java over Internet (or intranet)

Configure the required server for your type of network client(s):

-   [Navigator server](config_connectivity_paras#olh_connectivity_guiserver): for TCP/IP clients
-   [Axway MFT Navigator server](config_connectors#olh_connectivity_iui): for Axway MFT Navigator clients

Related topics

[Configuration: Procedure](config_procedure): How to access the configuration menu and configure Gateway.

[Configuration: Gateway parameters](config_gateway_paras): The **Gateway** parameters of the configuration menu.

[Configuration: Customizing Trading Partner parameters](customizing_trading_partner_paras): Advanced configuration parameters for certain trading file management situations.

[Configuration: Connectivity parameters](config_connectivity_paras): The <span style="font-weight: bold;">Connectivity</span> parameters of the configuration menu.

[Configuration: Secure Relay Router Agent parameters](../../gateway_security_guide/managing_security_start_here/config_secure_relay_ra_paras)

[Configuration: Secure Relay advanced options](../../gateway_security_guide/managing_security_start_here/config_secure_relay_adv_options)

[Configuring protocols](config_protocols_about/config_protocols)

[Configuring connectors](config_connectors): The <span style="font-weight: bold;">Axway Connectivity</span> parameters of the configuration menu.

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)