{
    "title": "Update, upgrade, or migrate",
    "linkTitle": "Update, upgrade or migrate ",
    "weight": "130"
}This section is designed to assist administrators or users who are tasked with updating Transfer CFT{{< TransferCFT/transfercftname  >}}, or upgrading or migrating from an existing Transfer CFT{{< TransferCFT/componentshortname  >}} version to Transfer CFT{{< TransferCFT/componentshortname  >}} 3.9{{< TransferCFT/componentversion  >}}.

## Updates versus upgrade or migrate

### About updates

An update brings Transfer CFT up-to-date with a patch or service pack offering fixes and minor enhancements. For example, you can update a Transfer CFT 3.1.3 SP3 to Transfer CFT 3.1.3 SP8. See [Updating Transfer CFT](update_cft_unix).

### About upgrades

An upgrade is the process of updating to a newer, enhanced version of the software. For example, you can upgrade Transfer CFT 3.1.3 to Transfer CFT 3.9{{< TransferCFT/releasenumber  >}}. See [Upgrading Transfer CFT](upgrade_intro_ux).

As of Transfer CFT{{< TransferCFT/componentlongname  >}} 3.4, Axway simplifies the upgrade procedure by allowing you to use the installation package to upgrade from a previous version.

Upgrading, as compared to migration, has the following advantages:

- Allows you to update in the same location
- You can perform this automatically using the Installer, and you can revert to previous state if needed
- Scripts and APIs remain intact and only require a recompilation for the APIs

> **Note**
>
> You cannot perform an upgrade on versions older than version 3.1.3.

****Transfer CFT 3.8 and higher****

After performing a Transfer CFT upgrade, you must execute the profile before performing commands with the upgraded Transfer CFT.

### About manual migrations

A migration means that an initial Transfer CFT{{< TransferCFT/componentshortname  >}} is installed in a directory that is not removed or overwritten by the procedure.

> **Note**
>
> When migrating from a previous version of Transfer CFT, be sure to check the Release Notes for new as well as deprecated features and supported platforms for that release.

The general procedure for migrating from a previous version of Transfer CFT to Transfer CFT 3.9{{< TransferCFT/componentversion  >}} is as follows:

1. Export existing information from the previous version. Details vary depending on the existing Transfer CFT version.
1. Install Transfer CFT{{< TransferCFT/transfercftname >}} 3.8.
1. Import the exported information into Transfer CFT 3.9{{< TransferCFT/componentversion >}}.

## Register with Central Governance

If you intend to implement Central Governance, please refer to the **Transfer CFT**{{< TransferCFT/componentlongname  >}} *User's Guide &gt; [*Register with* **Central Governance**](https://docs.axway.com/bundle/TransferCFT_36_UsersGuide_allOS_en_HTML5/page/Content/cft_installation/migrate/register_CG.htm)* page for registration details.

## Update or upgrade using Central Governance

Central Governance simplifies the management of Transfer CFT and provides identity and access management, certificate security services, monitoring, alerting, and web dashboard services. If you are using Transfer CFT{{< TransferCFT/componentlongname  >}} 3.9{{< TransferCFT/releasenumber  >}} with Central Governance, you can use the information in [Activate Central Unified Flow Management{{< TransferCFT/governance  >}} connectivity](../../../governance_services_intro/register_cg) to configure and register with Central Governance.

Central governance allows you to update to the latest Transfer CFT Service Pack or patch, or use the installation package to upgrade Transfer CFT{{< TransferCFT/componentlongname  >}} (as of Transfer CFT{{< TransferCFT/componentlongname  >}} 3.2.4) to a new Transfer CFT{{< TransferCFT/componentlongname  >}} version. However, you cannot migrate Transfer CFT using Central Governance.

> **Note**
>
> You cannot perform an upgrade from Central Governance on the following platforms: z/OS or IBM i.

## Prerequisites

Important information before performing an upgrade or install auto-import procedure:

- You must update your Transfer CFT{{< TransferCFT/componentshortname >}} to the most recent service pack version.
- For Transfer CFT{{< TransferCFT/componentlongname >}} versions lower than 3.4, upgrade the Axway{{< TransferCFT/companyname >}} Installer to 4.10 (or higher) prior to upgrading your Transfer CFT{{< TransferCFT/componentshortname >}} 3.9.
- If needed, you can uninstall an Upgrade. Doing so rolls back to the previous version before the upgrade, but all transfers and configuration modifications that were performed since the upgrade are lost.
- Backup Transfer CFT{{< TransferCFT/componentshortname >}} before beginning an upgrade or migration procedure.
- Before beginning the upgrade or migration procedure stop the existing version of Transfer CFT and the UI server.

### More information

If you encounter issues when migrating Transfer CFT, contact Axway Support at [https://support.axway.com](https://support.axway.com/).
