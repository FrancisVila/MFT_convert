{
    "title": "DMZ deployment",
    "linkTitle": "DMZ deployment",
    "weight": "120"
}You can further enhance the isolation and security of your enterprise network by deploying Gateway in a DMZ architecture.

Secure Relay is a secure, multi-protocol, front-end product that prevents external partners from directly accessing Gateway for file exchange. Secure Relay processes data streaming of external connections from the outside world to Gateway without any data storage (even temporary) in the DMZ. Secure Relay is compatible with any Gateway supported protocol that uses a TCP/IP network.

When you use Gateway with Secure Relay, you derive the following specific benefits:

-   All of your data is stored in your local network, protected by your firewall
-   Connections from outside the protected area are refused
-   Configuration data, including private server keys, are never stored in the DMZ
-   No decryption occurs within the DMZ
-   You can adapt the connection parameters of your Gateway to conform to the policies you establish in the DMZ

## Distribution of functions

Native Gateway functions work together with the specific Secure Relay functions to provide DMZ security.

In a Secure Relay / DMZ configuration:

-   Gateway:
    -   Manages streaming connections with the Secure Relay Router Agent situated in the DMZ
    -   Manages user access to file resources (workspaces, downloads and uploads)
    -   Handles the file transfer protocol dialog with partners
    -   Manages file transfer scheduling and monitoring
    -   Can terminate transport security communication (either SSL or SSH for SFTP) to ensure a transparent link between partner identities (X.509 certificate) and file operations
    -   Generates links with internal IT system applications by either routing files to other destinations or by direct integration
    -   Handles physical file management operations
-   Secure Relay:
    -   Manages connections with the outside world for file exchange, depending on the Gateway directives
    -   Handles data streaming of flows to and from the Internet
    -   Can terminate transport security communication (either SSL or SSH for SFTP) to ensure a transparent link between partner identities (X.509 certificate) and file operations

## Secure Relay architecture

{{< Gateway/docnamesuitesupportedplatforms  >}} Guide is divided into two basic components parts:

-   Secure Relay Master Agent   
    The {{< Gateway/securerelayname >}} Master Agent is a component that resides with and is fully integrated in the {{< Gateway/componentshortname >}} product. All of the processes that support {{< Gateway/securerelayname >}} functions are automatically included in {{< Gateway/componentshortname >}} on installation.
-   {{< Gateway/securerelayname >}} Router Agent   
    The {{< Gateway/securerelayname >}} Router Agent is a stand-alone component. You install the {{< Gateway/securerelayname >}} Router Agent on a machine located in the DMZ, independently of Gateway.

Links to documentation set for Axway Gateway {{< Gateway/releasenumber  >}}:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
