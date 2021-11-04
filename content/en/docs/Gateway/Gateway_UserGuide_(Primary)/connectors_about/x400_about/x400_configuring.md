{
    "title": "Configuring Gateway for X.400",
    "linkTitle": "Configuring for X.400",
    "weight": "270"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Connectors

[Prerequisites](#prerequisites)

[Configuring Gateway for X.400](#configuring_gw_x400)

[Configuring Axway PassPort](#configuring_pp)

[Creating objects for X.400 transfers](#creating_objects)

[Configuring partners](#configuring_partners)

<span id="prerequisites"></span>

## Prerequisites

In addition to installing Gateway (and any available patches) you must install PassPort PM V3.4.4 (or later) and the latest patch(es).

<span id="configuring_gw_x400"></span>

## Configuring Gateway for X.400

To configure Gateway for use with X.400, set up the X.400 connector in the Gateway [configuration menu](../../../configuration_start_here/config_procedure#Configuring_Gateway):

1.  In the left pane of the Gateway GUI, right-click the Gateway server that you want to configure and select <span style="font-weight: bold;">Configure</span>.
2.  Select <span style="font-weight: bold;">Connectivity > Axway Connectivity > X.400</span>.
3.  Complete the [X.400 parameters](../../../configuration_start_here/config_connectors#olh_connectivity_x400).
4.  Click <span style="font-weight: bold;">Activate</span> to enable the connector.
5.  Click <span style="font-weight: bold;">OK</span>.

<span id="configuring_pp"></span>

## Configuring Axway PassPort

To configure Gateway for use with PassPort, set up the PassPort connector in the Gateway [configuration menu](../../../configuration_start_here/config_procedure#Configuring_Gateway):

1.  In the left pane of the Gateway GUI, right-click the Gateway server that you want to configure and select <span style="font-weight: bold;">Configure</span>.
2.  Select <span style="font-weight: bold;">Connectivity > Axway Connectivity > PassPort</span>.
3.  Complete the [PassPort parameters](../../../configuration_start_here/config_connectors#olh_connectivity_passport).
4.  Click <span style="font-weight: bold;">OK</span>.

<span id="creating_objects"></span>

## Creating objects for X.400 transfers

This section describes how to create Remote Site objects for X.400 transfers.

<span id="creating_remote_site_object_for_x400"></span>

### Creating a Remote Site object for X.400 transfers

In the Remote Site object you specify the remote MTA and MS retrieve methods.

To create a Remote Site object:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:

Partner Management &gt; Sites

1.  Right-click the <span style="font-weight: bold;">Remote Site</span> sub-node, then select <span style="font-weight: bold;">New</span> to display the <span style="font-style: italic;">New Remote Site</span> window.
2.  Complete the fields on the <span style="font-weight: bold;">[General](../../../managing_partners_start_here/sites_start_here/managing_remote_sites/remote_site_general_tab)</span> tab. In the <span style="font-weight: bold;">Protocol</span> field, make sure you select <span style="font-weight: bold;">X.400</span>.
3.  Complete the fields on the <span style="font-weight: bold;">[Options](../../../managing_partners_start_here/sites_start_here/managing_remote_sites/remote_site_options_tab)</span> tab.
4.  Complete the fields on the <span style="font-weight: bold;">[X.400](../../../managing_partners_start_here/sites_start_here/managing_remote_sites/remote_site_x400_tab)</span> tab.
5.  Click <span style="font-weight: bold;">OK</span>.  
      
    Gateway creates a new Remote Site object with the specified characteristics.  
    You can create as many Remote Sites as required.

#### Using command line

Alternatively, you can create a Remote Site object using the <span class="code" style="font-weight: bold;">[peladm create\_site](../../../managing_partners_start_here/sites_start_here/managing_local_sites_cli/managing_remote_sites_cli#peladm_create_site)</span> online command.

<span id="configuring_partners"></span>

## Configuring partners

Configure X.420 partners using PassPort PM. Refer to [Managing X.400 partners](../x400_managing_partners).

 

Related topics

[About X.400](../)

[X.400 connector](../x400_connector)

[Managing X.400 partners](../x400_managing_partners)

[Working with X.400](../x400_working_with)

[X.400 log messages](../../../log_messages_about/x400_messages)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
