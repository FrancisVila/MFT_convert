{
    "title": "SWIFTNet High Availability with External Correlation",
    "linkTitle": "SWIFTNet High Availability with External Correlation",
    "weight": "370"
}## Prerequisites

The prerequisites for activating the SWIFTNet *High Availability with External Correlation* feature are:

-   Each Gateway node installation from a High Availability solution must connect to SWIFT through its own SAG.
-   When installing Gateway, the High Availability option must be used.
-   Each Gateway from the High Availability environment must be assigned a unique node identifier (See About Gateway Node ID).

> **Note:**
>
> The SWIFTNet High Availability with External Correlation feature requires a valid license key in order to function.
> Enabling SWIFTNet High Availability with External Correlation without a proper license key will result in Gateway SWIFTNet processes being unable to start.

## About Gateway Node IDs

In environments where multiple Gateways are installed -for example connected to the same back-end application - it is desirable to have unique transfer identifiers for each Gateway installation. This functionality can be enabled by assigning each Gateway a unique node identifier. By default, this functionality is disabled.
A node identifier can have values from 0 to 15, for a total of 16 nodes. If set, the transfer identifier allocation changes as follows:

-   Transfer identifiers are no longer allocated contiguously. Instead, a new transfer identifier will be the next number multiple of 16 + the node identifier (thus incremented by 16). This ensures that each Gateway allocates its own subset of transfer identifiers.
-   There is no change for transfers already in the mailbox; therefore it is possible to have old transfers not conforming with the above rule. However, activating the node identifier feature should be done on a new installation.

## Setting a Gateway node identifier

The Gateway node identifier can be set using the `peluconf `command:

`peluconf set -s monitor node_id `&lt;node identifier>

where the node identifier ranges from `0 `to `15`.

> **Note:**
>
> There is no equivalent command to unset the node identifier. This implies that once activated, the node identifier feature cannot be disabled. A Gateway node can be set to a different node identifier. Ensure that each Gateway is assigned a unique node identifier.

## Enabling the SWIFTNet High Availability with External Correlation feature

You must configure some global parameters before using the SWIFTNet High Availability with External Correlation feature. This can be partially done using the Graphical User Interface, and/or the command line configuration.

Use the following steps to enable SWIFTNet High Availability with External Correlation. If not properly defined, the Gateway SWIFTNet client and server processes will be unable to start.

1.  Set the `node_id `parameter to a value between `0` and `15`.
2.  In the left pane of the main window in the user interface, right-click the Gateway server to enable High Availability and select **Configure**. The Configuration window appears.
3.  In the left pane of the Configuration window, go to **Connectivity** > **Axway connectivity** > **SWIFTNet** and select the **HA** tab.
4.  From the **High Availability Exit** drop-down list, select **Use external correlation** to enable the **High Availability with External Correlation** feature.
5.  Alternatively, enable the High Availability with External Correlation feature from the command line configuration:  
    `peluconf set -s swnet swnet_ack_userexit_option 2`
6.  Restart Gateway for the change in configuration to take effect

Links to documentation set for Axway Gateway {{< Gateway/releasenumber  >}}:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
