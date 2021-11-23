{
    "title": "Axway PassPort PS connector",
    "linkTitle": "PassPort PS connector",
    "weight": "240"
}{{< Gateway/componentlongname  >}}: Connectors

## About PassPort PS

PassPort PS (PKI Server) is a stand-alone tool that you can use in a Public Key Infrastructure (PKI) with Gateway when Gateway communicates with partners via a secure protocol (SSL/TLS or SSH).

## Using Gateway with PassPort PS

When you use Gateway with PassPort PS, PassPort PS assures certain security functions in place of Gateway:

-   Certificate selection for exchanges with remote partners
-   Data encryption and signing

## Activating the PassPort PS connector

To configure Gateway for use with PassPort PS, set up the PassPort PS connector in the Gateway [configuration menu](../../../configuration_start_here/config_procedure#Configuring_Gateway):

-   In the left pane of the Gateway GUI, right-click the Gateway server that you want to configure and select **Configure**.
-   Select <span style="font-weight: bold;">Connectivity > Axway Connectivity > PassPort</span>.
-   Complete the [PassPort parameters](../../../configuration_start_here/config_connectors#olh_connectivity_passport).
-   Click <span style="font-weight: bold;">OK</span>.

Enter the following information to configure the PassPort AM connection:

<span class="mc-variable suite_variables.PassPortName variable">PassPort</span> Version

Select the **Use PKI Services** option

The <span class="mc-variable suite_variables.PassPortName variable">PassPort</span> server host name or IP address

The PassPort PKI port

The Component Id

The login user name  
Note: you need to set the component password by running the `pelencpass `command locally on the <span class="mc-variable suite_variables.GatewayName variable">Gateway</span> server

Also you can select the **Use TLS** option to secure the connection between <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> and <span class="mc-variable suite_variables.PassPortName variable">PassPort</span> PS. If you do that, you need to enter the following parameters:

-   The PKI SSL port
-   The <span class="mc-variable suite_variables.PassPortName variable">PassPort</span> CA location is pre-defined, but you can modify it

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
