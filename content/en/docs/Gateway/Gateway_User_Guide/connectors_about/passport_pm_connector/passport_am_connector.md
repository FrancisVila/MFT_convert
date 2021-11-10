{
    "title": "Axway PassPort AM connector",
    "linkTitle": "PassPort AM connector",
    "weight": "250"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Connectors

## About PassPort AM

PassPort AM (Access Management) centralizes the management of users for all products of the <span class="mc-variable axway_variables.Platform_or_Suite_Short_Name variable">Axway Platform</span>. If you have installed PassPort AM, you can use it to define all your users and profiles. Gateway can then connect to PassPort AM to check user permissions.

## Activating the PassPort AM connector

To configure Gateway for use with PassPort AM, set up the PassPort AM connector in the Gateway [configuration menu](../../../configuration_start_here/config_procedure#Configuring_Gateway):

-   In the left pane of the Gateway GUI, right-click the Gateway server that you want to configure and select <span style="font-weight: bold;">Configure</span>.
-   Select <span style="font-weight: bold;">Connectivity > Axway Connectivity > PassPort</span>.
-   Complete the [PassPort parameters](../../../configuration_start_here/config_connectors#olh_connectivity_passport).
-   Click <span style="font-weight: bold;">OK</span>.

Enter the following information to configure the PassPort AM connection:

-   PassPort Version
-   Select the **Use access management** option
-   The PassPort server host name or IP address
-   The PassPort HTTP port
-   The Component Id
-   The login user name  
    **Note**: you need to set the component password by running the `pelencpass `command locally on the <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span>server.
-    Also you can select the **Use TLS** option to secure the connection between Gateway and PassPort AM. If you do that, you need to enter the following parameters:  
    -   The HTTPS port
    -   The PassPort CA location is pre-defined, but you can modify it.
    -   The Client certificate location is also pre-defined, but you can modify it.

Related topics

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
