{
    "title": "Configuring Gateway for Sentinel monitoring",
    "linkTitle": "Configuring for Sentinel",
    "weight": "220"
}{{< Gateway/componentlongname  >}}: Connectors

[Prerequisites](#Prerequisites)

[Configuring Gateway for use with Sentinel](#Configuring_Gateway_for_use_with_Sentinel)

<span id="Prerequisites"></span>

## Prerequisites

The {{< Gateway/platformorsuiteshortname  >}} installation DVD includes three files that contain descriptions of the Sentinel objects that you use for monitoring Gateway from Sentinel. These files are located on the installation DVD in the` /extras/sentinel` folder:

-   `XFB_ALL_EN.xml` (for non-High Availability solutions)
-   `XFB_ALL_EN_HA.xml` (for SWIFTNet High Availability solutions)
-   `XFB_ALL_PB_EN.xml`

The two files `XFB_ALL_EN.xml` and `XFB_ALL_PB_EN.xml` are identical except for some request objects that use a view request scope set to "Private" in the first of these two files and "Public" in the second one.

The view request scope defines the way Sentinel manages the access to requests, either public or based on a username/password pair using profiles created in Sentinel. If PassPort AM is used together with Sentinel then the profiles used will be those from PassPort AM.

Before you can use Sentinel to monitor Gateway events, you must import one of these description files into Sentinel. If you use PassPort AM with Sentinel, use the second file. Otherwise use the first file.

**Note:** Sentinel does not currently support "Private" view request method for its objects. This is planned for a future release.

The two files: `XFB_ALL_EN.xml` and `XFB_ALL_EN_HA.xml` are identical except for the `TrackingObject` option `“nullMngt`”, which has the value “`Last`” (the updates are done relative to the last update) for SWIFTNet High Availability. Therefore, if you are not using the file provided in the delivery and generate the Tracking Object, do not forget to enable the “null management” option when using it in the context of SWIFTNet High Availability.

<span id="Configuring_Gateway_for_use_with_Sentinel"></span>

## Configuring Gateway for use with Sentinel

To configure Gateway for use with Sentinel, set up the Sentinel connector in the Gateway [configuration menu](../../../configuration_start_here/config_procedure#Configuring_Gateway):

-   In the left pane of the Gateway GUI, right-click the Gateway server that you want to configure and select **Configure**.
-   Select <span style="font-weight: bold;">Connectivity > Axway Connectivity > Sentinel</span>.
-   Complete the [Sentinel parameters](../../../configuration_start_here/config_connectors#olh_connectivity_sentinel).
-   Click <span style="font-weight: bold;">Activate</span> to enable the connector.
-   Click <span style="font-weight: bold;">OK</span>.

After you have activated the Sentinel connector in the configuration menu, Gateway automatically launches Sentinel notification at startup.

Related topics

[About Axway Sentinel](../)

[Managing .pmq files with the pmqctl command](../pmqctl)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
