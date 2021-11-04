{
    "title": "Configuration: procedure",
    "linkTitle": "Procedure",
    "weight": "70"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Configuration

<span id="About"></span>

## About configuration

You configure Gateway using the configuration menu of the GUI.

Some changes are taken into account immediately. For other changes, you need to stop and then restart Gateway.

Configuration modifications are tracked in the standard Gateway log.

<span id="Configuring_Gateway"></span>

## Configuring Gateway

1.  In the left pane of the GUI main window, right-click the Gateway server that you want to configure and select <span style="font-weight: bold;">Configure</span> from the context menu.  
    The <span style="font-style: italic;">Configuration</span> window is displayed.
2.  In the left pane of the <span style="font-style: italic;">Configuration</span> window, select the item you want to configure.  
    Click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes.  
    The parameters are displayed in the right pane.
3.  Fill-in or modify the required configuration information.  
    Refer to:
    -   [Configuration: Gateway parameters](../config_gateway_paras)
    -   [Configuration: Connectivity parameters](../config_connectivity_paras)
    -   [Configuring protocols](../config_protocols_about/config_protocols)
    -   [Configuring connectors](../config_connectors)
4.  For <span style="font-weight: bold;">Connectivity</span> parameters only:  
    After completing the parameter fields, click <span style="font-weight: bold;">Activate</span> to enable the protocol or connector in Gateway.  
    If you no longer want to use a protocol or connector, click <span style="font-weight: bold;">Deactivate</span> to disable it.
5.  Click <span style="font-weight: bold;">OK</span> to save the changes.  
    The <span style="font-style: italic;">Configuration</span> window closes.  
    Alternatively, click <span style="font-weight: bold;">Apply</span> to make these changes and continue configuring Gateway.
6.  If Gateway displays a warning message, stop and then restart Gateway.  
    (This depends on the parameters you modified.)

At any time during configuration:

-   Click <span style="font-weight: bold;">Help</span> for contextual help information.
-   Click <span style="font-weight: bold;">Cancel</span> to abandon all changes that you have entered since you clicked <span style="font-weight: bold;">Apply</span>.

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
