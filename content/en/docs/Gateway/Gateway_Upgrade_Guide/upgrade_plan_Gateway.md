{
    "title": "Plan the upgrade",
    "linkTitle": "Plan the migration",
    "weight": "40"
}If you are responsible for upgrading an existing <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> installation to <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> <span class="mc-variable axway_variables.Component_Version variable">6.17</span>, read this section to help you plan your upgrade activities.

## Should I upgrade?

Before you upgrade, determine if upgrading is appropriate for your environment and production requirements:

-   Review the <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> <span class="mc-variable suite_variables.DocTypeRelNotes variable">Release Notes</span> for:
    -   New features
    -   Fixed issues
    -   Known limitations
-   Evaluate the effort required for this upgrade. You should consider:
    -   Length and impact of product down time: the existing <span class="mc-variable suite_variables.GatewayName variable">Gateway</span> is be stopped in the course of the upgrade process.

## Minimum version requirement

To upgrade to <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> <span class="mc-variable axway_variables.Component_Version variable">6.17</span>, you must have <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> 6.16 installed.

You can verify the <span class="mc-variable suite_variables.GatewayName variable">Gateway</span> version usig the <span class="code">peladm –Identity</span> command or consulting the <span class="code">\*.out </span>files.

## Upgrade method

The upgrade method used is to install a new version of the product. Commands are provided for exporting the configuration from the old <span class="mc-variable suite_variables.GatewayName variable">Gateway</span> installation to the new one.

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
