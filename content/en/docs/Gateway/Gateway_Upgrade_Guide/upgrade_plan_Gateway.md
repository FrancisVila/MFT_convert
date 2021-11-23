{
    "title": "Plan the upgrade",
    "linkTitle": "Plan the migration",
    "weight": "40"
}If you are responsible for upgrading an existing {{< Gateway/componentshortname  >}} installation to {{< Gateway/componentshortname  >}} {{< Gateway/componentversion  >}}, read this section to help you plan your upgrade activities.

## Should I upgrade?

Before you upgrade, determine if upgrading is appropriate for your environment and production requirements:

-   Review the {{< Gateway/componentshortname >}} {{< Gateway/doctyperelnotes >}} for:
    -   New features
    -   Fixed issues
    -   Known limitations
-   Evaluate the effort required for this upgrade. You should consider:
    -   Length and impact of product down time: the existing {{< Gateway/gatewayname >}} is be stopped in the course of the upgrade process.

## Minimum version requirement

To upgrade to {{< Gateway/componentshortname  >}} {{< Gateway/componentversion  >}}, you must have {{< Gateway/componentshortname  >}} 6.16 installed.

You can verify the {{< Gateway/gatewayname  >}} version usig the `peladm –Identity` command or consulting the `*.out `files.

## Upgrade method

The upgrade method used is to install a new version of the product. Commands are provided for exporting the configuration from the old {{< Gateway/gatewayname  >}} installation to the new one.

Links to documentation set for Axway Gateway {{< Gateway/releasenumber  >}}:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
