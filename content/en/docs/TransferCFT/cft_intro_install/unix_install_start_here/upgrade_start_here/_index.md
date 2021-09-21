{
    "title": "Update, upgrade or migrate ",
    "linkTitle": "Update, upgrade or migrate ",
    "weight": "130"
}This section is designed to assist administrators or users who are tasked with updating Transfer CFT, or upgrading or migrating from an existing Transfer CFT version to Transfer CFT 3.9.

## Updates versus upgrade or migrate

### About updates

An update brings Transfer CFT up-to-date with a patch or service pack offering fixes and minor enhancements. For example, you can update a Transfer CFT 3.1.3 SP3 to Transfer CFT 3.1.3 SP8. See [Updating Transfer CFT](update_cft_unix).

### About upgrades

An upgrade is the process of updating to a newer, enhanced version of the software. For example, you can upgrade Transfer CFT 3.1.3 to Transfer CFT 3.9. See [Upgrading Transfer CFT](upgrade_intro_ux).

As of Transfer CFT 3.4, Axway simplifies the upgrade procedure by allowing you to use the installation package to upgrade from a previous version.

Upgrading, as compared to migration, has the following advantages:

-   Allows you to update in the same location
-   You can perform this automatically using the Installer, and you can revert to previous state if needed
-   Scripts and APIs remain intact and only require a recompilation for the APIs

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">You cannot perform an upgrade on versions older than version 3.1.3.         </td>
      </tr>
</table>

Transfer CFT 3.8 and higher

After performing a Transfer CFT upgrade, you must execute the profile before performing commands with the upgraded Transfer CFT.

### About manual migrations

A migration means that an initial Transfer CFT is installed in a directory that is not removed or overwritten by the procedure.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">When migrating from a previous version of <span>Transfer CFT</span>, be sure to check the <span>Release Notes</span> for new as well as deprecated features and supported platforms for that release.         </td>
      </tr>
</table>

The general procedure for migrating from a previous version of Transfer CFT to Transfer CFT 3.9 is as follows:

1.  Export existing information from the previous version. Details vary depending on the existing Transfer CFT version.
2.  Install Transfer CFT 3.8.
3.  Import the exported information into Transfer CFT 3.9.

## Register with Central Governance

If you intend to implement Central Governance, please refer to the Transfer CFT *User's Guide &gt; [*Register with* Central Governance](https://docs.axway.com/bundle/TransferCFT_36_UsersGuide_allOS_en_HTML5/page/Content/cft_installation/migrate/register_CG.htm)* page for registration details.

## Update or upgrade using Central Governance

Central Governance simplifies the management of Transfer CFT and provides identity and access management, certificate security services, monitoring, alerting, and web dashboard services. If you are using Transfer CFT 3.9 with Central Governance, you can use the information in [Activate Central Unified Flow Management connectivity](../../../governance_services_intro/register_cg) to configure and register with Central Governance.

Central governance allows you to update to the latest Transfer CFT Service Pack or patch, or use the installation package to upgrade Transfer CFT (as of Transfer CFT 3.2.4) to a new Transfer CFT version. However, you cannot migrate Transfer CFT using Central Governance.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">You cannot perform an upgrade from <span>Central Governance</span> on the following platforms: z/OS or IBM i.         </td>
      </tr>
</table>

## Prerequisites

Important information before performing an upgrade or install auto-import procedure:

-   You must update your Transfer CFT to the most recent service pack version.
-   For Transfer CFT versions lower than 3.4, upgrade the Axway Installer to 4.10 (or higher) prior to upgrading your Transfer CFT 3.9.
-   If needed, you can uninstall an Upgrade. Doing so rolls back to the previous version before the upgrade, but all transfers and configuration modifications that were performed since the upgrade are lost.
-   Backup Transfer CFT before beginning an upgrade or migration procedure.
-   Before beginning the upgrade or migration procedure stop the existing version of Transfer CFT and the UI server.

### More information

If you encounter issues when migrating Transfer CFT, contact Axway Support at [https://support.axway.com](https://support.axway.com/).
