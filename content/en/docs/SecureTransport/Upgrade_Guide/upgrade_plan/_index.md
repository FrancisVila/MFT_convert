{
    "title": "Plan the upgrade",
    "linkTitle": "Plan the upgrade",
    "weight": "40"
}If you are responsible for upgrading an existing SecureTransport installation to SecureTransport 5.5, read this section to help you plan your upgrade activities.

## Should I upgrade?

Before you upgrade, determine if upgrading is appropriate for your environment and production requirements:

-   Review the SecureTransport Release Notes for:
    -   New features
    -   Fixed issues
    -   Known limitations
-   Evaluate the effort required for this upgrade. You should consider:
    -   Length and impact of product down time
    -   Basic upgrade effort
    -   Specific actions that might be required due to incompatibilities or limitations. See [Upgrade paths and incompatibilities](incompatibilities).
    -   Initial validation and non-regression testing
    -   Upgrading your different operating environments, for example, test, and preproduction

## Minimum version requirement

To upgrade directly to SecureTransport 5.5, you must have SecureTransport 5.4 with the latest patch installed. See [Upgrade paths and incompatibilities](incompatibilities) for a complete list of supported upgrade paths.

## Upgrade methods

There is currently one method for upgrading to SecureTransport 5.5 from an earlier version:

-   Apply an upgrade pack – When you apply the upgrade pack, the upgrade logic auto-detects and configures settings and prepares the upgraded installation for use without any additional configuration. This includes the upgrading of clustered implementations. For upgrade instructions using an upgrade pack, refer to [Upgrade procedures](../upgrade_overview1).

See [Upgrade paths and incompatibilities](incompatibilities) to learn about incompatibilities between earlier versions of SecureTransport and this version.

## Product downtime considerations

This section lists considerations and provides strategies for performing upgrades with the minimal disruption of your production processes.

Considerations:

-   How much time does the upgrade require?
-   What scheduling constraints exist?
-   How long will it take to check the upgrade results?
-   How long will it take to roll back to the previous state if the upgrade fails?

Strategies to reduce downtime:

-   Review the upgrade prerequisites. Refer to [Pre-upgrade tasks](../before_you_upgrade).
-   Upgrade during a low volume time period.

## Acquire a license

A new license is not required when upgrading SecureTransport .

## Download the upgrade pack

After reviewing [Upgrade paths and incompatibilities](incompatibilities), go to the Axway [support site](https://support.axway.com/) and download the upgrade pack for your operating system.
