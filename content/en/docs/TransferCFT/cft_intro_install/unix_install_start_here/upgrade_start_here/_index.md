{
    "title": "Update, upgrade, or migrate",
    "linkTitle": "Update, upgrade or migrate ",
    "weight": "130"
}This section is designed to assist administrators or users who are tasked with updating <span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span>, or upgrading or migrating from an existing <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> version to <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> <span class="mc-variable axway_variables.Component_Version variable">3.9</span>.

## Updates versus upgrade or migrate

### About updates

An update brings Transfer CFT up-to-date with a patch or service pack offering fixes and minor enhancements. For example, you can update a Transfer CFT 3.1.3 SP3 to Transfer CFT 3.1.3 SP8. See [Updating Transfer CFT](update_cft_unix).

### About upgrades

An upgrade is the process of updating to a newer, enhanced version of the software. For example, you can upgrade Transfer CFT 3.1.3 to Transfer CFT <span class="mc-variable axway_variables.Release_Number variable">3.9</span>. See [Upgrading Transfer CFT](upgrade_intro_ux).

As of <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> 3.4, Axway simplifies the upgrade procedure by allowing you to use the installation package to upgrade from a previous version.

Upgrading, as compared to migration, has the following advantages:

-   Allows you to update in the same location
-   You can perform this automatically using the Installer, and you can revert to previous state if needed
-   Scripts and APIs remain intact and only require a recompilation for the APIs

> **Note:**
>
> You cannot perform an upgrade on versions older than version 3.1.3.

Transfer CFT 3.8 and higher

After performing a Transfer CFT upgrade, you must execute the <span class="code">profile </span>before performing commands with the upgraded Transfer CFT.

### About manual migrations

A migration means that an initial <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> is installed in a directory that is not removed or overwritten by the procedure.

> **Note:**
>
> When migrating from a previous version of Transfer CFT, be sure to check the Release Notes for new as well as deprecated features and supported platforms for that release.

The general procedure for migrating from a previous version of Transfer CFT to Transfer CFT <span class="mc-variable axway_variables.Component_Version variable">3.9</span> is as follows:

1.  Export existing information from the previous version. Details vary depending on the existing Transfer CFT version.
2.  Install <span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span> 3.8.
3.  Import the exported information into Transfer CFT <span class="mc-variable axway_variables.Component_Version variable">3.9</span>.

## Register with <span class="mc-variable Primary.CG or_UM variable">Central Governance</span>

If you intend to implement <span class="mc-variable Primary.CG or_UM variable">Central Governance</span>, please refer to the <span class="mc-variable axway_variables.Component_Long_Name variable" style="font-style: italic;">Transfer CFT</span> *User's Guide &gt; [*Register with* <span class="mc-variable Primary.CG or_UM variable" style="font-style: italic;">Central Governance</span>](https://docs.axway.com/bundle/TransferCFT_36_UsersGuide_allOS_en_HTML5/page/Content/cft_installation/migrate/register_CG.htm)* page for registration details.

## Update or upgrade using <span class="mc-variable Primary.CG or_UM variable">Central Governance</span>

Central Governance simplifies the management of Transfer CFT and provides identity and access management, certificate security services, monitoring, alerting, and web dashboard services. If you are using <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> <span class="mc-variable axway_variables.Release_Number variable">3.9</span> with <span class="mc-variable Primary.CG or_UM variable">Central Governance</span>, you can use the information in [Activate Central <span class="mc-variable suite_variables.Governance variable">Unified Flow Management</span> connectivity](../../../governance_services_intro/register_cg) to configure and register with <span class="mc-variable Primary.CG or_UM variable">Central Governance</span>.

Central governance allows you to update to the latest Transfer CFT Service Pack or patch, or use the installation package to upgrade <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> (as of <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> 3.2.4) to a new <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> version. However, you cannot migrate Transfer CFT using <span class="mc-variable Primary.CG or_UM variable">Central Governance</span>.

> **Note:**
>
> You cannot perform an upgrade from Central Governance on the following platforms: z/OS or IBM i.

## Prerequisites

Important information before performing an upgrade or install auto-import procedure:

-   You must update your <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> to the most recent service pack version.
-   For <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> versions lower than 3.4, upgrade the <span class="mc-variable axway_variables.Company_Name variable">Axway</span> Installer to <span class="mc-variable Primary.Installer_version variable">4.10</span> (or higher) prior to upgrading your <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> <span class="mc-variable Primary.Transfer_CFT version_long variable">3.9</span>.
-   If needed, you can uninstall an Upgrade. Doing so rolls back to the previous version before the upgrade, but all transfers and configuration modifications that were performed since the upgrade are lost.
-   Backup <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> before beginning an upgrade or migration procedure.
-   Before beginning the upgrade or migration procedure stop the existing version of Transfer CFT and the UI server.

### More information

If you encounter issues when migrating Transfer CFT, contact Axway Support at [<span class="Hyperlink">https://support.axway.com</span>](https://support.axway.com/).
