{
    "title": "Update, upgrade, or migrate",
    "linkTitle": "Update, upgrade, or migrate",
    "weight": "190"
}This section describes how to update, upgrade, or migrate to Transfer CFT 3.9.

## About updates

An update brings Transfer CFT up-to-date with a patch or service pack offering fixes and minor enhancements. For example, you can update a Transfer CFT 3.1.3 SP3 to Transfer CFT 3.1.3 SP8.

## About upgrades

An upgrade is the process of updating to a newer, enhanced version of the software.

This mode has the following advantages:

-   Allows you to update in the same location
-   You can perform this upgrade yet still revert to the previous state if needed
-   Scripts and APIs remain intact and only require a recompilation for the APIs

## About migrations

A migration means that an initial Transfer CFT is installed in a directory that is not removed or overwritten by the procedure.

This mode has the following advantages:

-   The new installation occurs in a new location, and the existing configuration in the existing Transfer CFT environment is not affected.
-   You can choose to use either of the versions, if needed, in case of an issue with one of the installations.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Configuration and data, such as the catalog, are in two separate locations and data are not shared.         </td>
      </tr>
</table>

This mode has the following restriction:

-   You must copy scripts and APIs from the previous version to the new installation.

## About manual migrations

The manual migration procedure, used to migrate an existing Transfer CFT to Transfer CFT 3.9, is described in this document.

The general procedure for migrating from a previous version of Transfer CFT to Transfer CFT 3.9 is:

1.  Export existing information from the previous version. Details vary depending on the existing Transfer CFT version.
2.  Import the exported information into Transfer CFT 3.9.

This mode has the following advantages:

-   Because it is manual, you can customize as needed.
-   You can migrate from versions older than version 2.7.x.

## Prerequisites

### Important information before performing an upgrade or migration procedure

-   You must update your Transfer CFT to the most recent service pack version.
-   Backup Transfer CFT before beginning an upgrade or migration procedure.
-   Before beginning the upgrade or migration procedure stop the existing version of Transfer CFT and the UI server. (I.e., you must stop all cluster nodes as a database migration occurs when performing an upgrade.)

### About license keys

-   You require a new license key if you are migrating from a version 2.x Transfer CFT to a version 3.x.
-   For details on how to apply or update a license key, and the new license key location, see the section **Apply a license key**.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">You require  as many keys as instances of <span>Transfer CFT</span> running at same time. For example, two Transfer CFT instances cannot run at the same time, on the same server, using the same license key.         </td>
      </tr>
</table>

## Prior to upgrading with a service pack

Upgrading Transfer CFT by applying a new service pack can overwrite your Transfer CFT program and production library. Therefore, as a precaution, prior to upgrading you must:     

-   Copy the existing Transfer CFT program library, for example CFTPGM in CFTPGM.O.
-   Copy the existing Transfer CFT production library, for example CFTPROD in CFTPROD.O.

The CFTPROD library contains your personal data and should not be cleared. Data may include:

-   Files, the UCONF file, Transfer CFT batch procedures, system objects (\*datara,\*jobd, \*sbsd,\*cls,\*jobq, etc.)
-   Scripts, procedures, files used by the Transfer CFT Enabler OS/400 Connector
-   Internal Access Management files

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The libraries CFTPGM.O and CFTPROD.O enable a synchronized and rapid Transfer CFT restart if required.         </td>
      </tr>
</table>

## Upgrade and migration tips and tricks

To facilitate migrations and upgrades, you may want to customize the TCPPARAM file configuration to use a new procedures library. By default, the procedures are located in CFTPROD/UTIN.

For example:

1.  Create a new library:  
    CRTLIB CFTEXEC
2.  Create a file that will contain your procedures:  
    CRTSRCPF FILE(CFTEXEC/UTIN) RCLEN(240)
3.  Copy or create your procedures in the CFTEXEC/UTIN file.
4.  Update the Transfer CFT configuration, meaning all exec values in the TCPPARAM, to use this new library.

## Register with Central Governance

If you intend to implement Central Governance, please refer to the Transfer CFT *User's Guide &gt; [*Register with* Central Governance](https://docs.axway.com/bundle/TransferCFT_36_UsersGuide_allOS_en_HTML5/page/Content/cft_installation/migrate/register_CG.htm)* page for registration details.