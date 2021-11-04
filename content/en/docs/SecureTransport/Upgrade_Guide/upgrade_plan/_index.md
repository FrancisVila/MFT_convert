{
    "title": "Upgrade planning and preparation",
    "linkTitle": "Plan the upgrade",
    "weight": "40"
}If you are responsible for upgrading an existing <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> installation to <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> <span class="mc-variable axway_variables.Component_Version variable">5.5</span>, read this section to help you plan your upgrade activities.

## Should I upgrade?

Before you upgrade, determine if upgrading is appropriate for your environment and production requirements:

-   Review the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> <span class="mc-variable suite_variables.DocTypeRelNotes variable">Release Notes</span> for:
    -   New features
    -   Fixed issues
    -   Known limitations
-   Evaluate the effort required for this upgrade. You should consider:
    -   Length and impact of product down time
    -   Basic upgrade effort
    -   Specific actions that might be required due to incompatibilities or limitations. See <a href="incompatibilities" class="MCXref xref">Upgrade paths and incompatibilities</a>.
    -   Initial validation and non-regression testing
    -   Upgrading your different operating environments, for example, test, and preproduction

## Minimum version requirement

To upgrade directly to <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> <span class="mc-variable axway_variables.Component_Version variable">5.5</span>, you must have <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> 5.4 with the latest patch installed. See <a href="incompatibilities" class="MCXref xref">Upgrade paths and incompatibilities</a> for a complete list of supported upgrade paths.

## Upgrade methods

There is currently one method for upgrading to <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> <span class="mc-variable axway_variables.Component_Version variable">5.5</span> from an earlier version:

-   Apply an upgrade pack – When you apply the upgrade pack, the upgrade logic auto-detects and configures settings and prepares the upgraded installation for use without any additional configuration. This includes the upgrading of clustered implementations. For upgrade instructions using an upgrade pack, refer to <a href="../upgrade_overview" class="MCXref xref">Upgrade procedures</a>.

See <a href="incompatibilities" class="MCXref xref">Upgrade paths and incompatibilities</a> to learn about incompatibilities between earlier versions of <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> and this version.

## Product downtime considerations

This section lists considerations and provides strategies for performing upgrades with the minimal disruption of your production processes.

Considerations:

-   How much time does the upgrade require?
-   What scheduling constraints exist?
-   How long will it take to check the upgrade results?
-   How long will it take to roll back to the previous state if the upgrade fails?

Strategies to reduce downtime:

-   Review the upgrade prerequisites. Refer to <a href="../before_you_upgrade" class="MCXref xref">Pre-upgrade tasks</a>.
-   Upgrade during a low volume time period.

## Acquire a license

A new license is not required when upgrading SecureTransport .

## Download the upgrade pack

After reviewing <a href="incompatibilities" class="MCXref xref">Upgrade paths and incompatibilities</a>, go to the <span class="mc-variable axway_variables.Company_Name variable">Axway</span> [support site](https://support.axway.com/) and download the upgrade pack for your operating system.
