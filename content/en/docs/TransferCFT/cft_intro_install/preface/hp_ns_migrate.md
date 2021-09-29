{
    "title": "Migrate or upgrade Transfer CFT",
    "linkTitle": "Migrate or upgrade Transfer CFT",
    "weight": "220"
}This chapter is designed to assist administrators or users who are tasked with upgrading or migrating from an existing Transfer CFT version to Transfer CFT 3.9.

-   [Migrate](#migrate): Use this procedure to migrate an existing Transfer CFT 2.3.2 installation
-   [Upgrade](#upgrade): Use this procedure to automatically upgrade an existing Transfer CFT 3.9

## <span id="Importan"></span>Important information

Before performing a migration or upgrade procedure, you must:

-   Update your Transfer CFT to the most recent service pack version.
-   Back up Transfer CFT.
-   Set the Transfer CFT profile.
-   Stop the existing version of Transfer CFT and the UI server.

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">You can uninstall an upgrade if needed. However, doing so rolls back to the previous version before the upgrade, so all transfers and configuration modifications that were performed since the upgrade are lost.</td>
</tr>
</tbody>
</table>

## <span id="Migrate"></span>Migrate

This section describes how to migrate the following elements:

-   Partner file
-   Parameter file
-   Client exits and applications

Before performing a migration be certain to review the section [Important information](#importan).

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">You cannot migrate the Transfer CFT Guardian 2.3.2 catalog and communication files to Transfer CFT HP NonStop <span>3.9</span>.</td>
</tr>
</tbody>
</table>

### Partner and parameter files

This section explains how to extract the definitions and import them in the new environment as part of a migration.

1.  From the Transfer CFT 2.3.2 environment, export the configuration in a sequential file using the command:
2.  Transfer the file from the native environment to the OSS environment.
3.  In the Transfer CFT 3.9 OSS environment, import as follows:
    1.  Create the partner and parameter files:
    2.  Import the configuration from the generated file:

### System configuration file

Transfer CFT 2.3.2 is based on a CFGSYS configuration file. While you cannot use this configuration file in the current version of Transfer CFT, most of the previous parameters have an equivalent in the current version.

System configuration file example

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>KW     Type    Volume.Subvolume</p>
<p><a href="#cftwrk">CFTWRK</a>  default $DATA00.CFT232UD</p></td>
</tr>
<tr class="even">
<td><p>KW   AP  <a href="#cpu">CPU</a> PNL SMS  MMS <a href="#term">TERM</a>    IN       COL  SWAPF    MEAS  <a href="#cpubackup">CPUBACKUP</a></p>
<p>CFTAPP 1  0   5  9600 600 $STTI  $STTI    $0   FSWAP01   Y     1</p>
<p>CFTAPP 2  1   X  0    0   default default  $0   none     X     X</p>
<p>CFTAPP 3  0   5  0    0   default default  $0   none     X     X</p>
<p>CFTAPP 4  0   X  0    0   default default  $0   none     X     X</p></td>
</tr>
<tr class="odd">
<td><p>KW      AP  LMS  ID       <a href="#pn">PN</a>     <a href="#pri">PRI</a> CPU  OBJECT                  OUT</p>
<p>CFTTASK 1  3200 CFTMAIN  $LAMGr  150  X   $DATA00.CFT232X.CFTMGRx   $s.#amgr</p>
<p>CFTTASK 1    30 CFTLOG   $LALoG  150  X   $DATA00.CFT232X.CFTLOGx   $s.#alog</p>
<p>CFTTASK 1    30 CFTTCOM  $LACoM  150  X   $DATA00.CFT232X.CFTCOMX   $s.#acom</p>
<p>[…]</p></td>
</tr>
<tr class="even">
<td><p>KW       OP       TERM</p>
<p><a href="#cftterm">CFTTERM</a>  OPLOG    $0</p>
<p>CFTTERM  OP000001 $S.#OPOUT</p>
<p>CFTTERM  OP000002 $S.#OPOUT</p>
<p>CFTTERM  OP000003 $TRM3.#A</p></td>
</tr>
<tr class="odd">
<td><p>KW      DEF       VAL     </p>
<p><a href="#parameters">CFTDEF</a>  <a href="#cfgsys">CFGSYS</a>    $DATA00.moncfg.CFGSYS</p>
<p>CFTDEF  <a href="#trkcnf">TRKCNF</a>    $DATA00.moncfg.CONFSENT</p>
<p>CFTDEF  <a href="#cftxfb">CFTXFB</a>    $DATA00.moncfg.CONFIUI</p>
<p>CFTDEF  CFTPARM   $DATA00.monfiles.FPARM</p>
<p>CFTDEF  CFTPART   $DATA00.monfiles.FPART</p>
<p>CFTDEF  CFTCATA   $DATA00.monfiles.FCAT</p>
<p>CFTDEF  CFTCOM    $DATA00.monfiles.FCOM</p>
<p>CFTDEF  CFTLOG    $DATA00.monfiles.FLOG</p>
<p>CFTDEF  CFTLOGA   $DATA00.monfiles.FLOGA</p>
<p>CFTDEF  CFTACCNT  $DATA00.monfiles.FACCNT</p>
<p>CFTDEF  CFTACCNTA $DATA00.monfiles.FACCNTA</p>
<p>CFTDEF  CFTPKU    $DATA00.monfiles.PKIBASE</p>
<p>CFTDEF  CFTHICNF  $DATA00.monfiles.SECCNF</p>
<p>CFTDEF  CFTHINI   $DATA00.moncfg.SECINI</p>
<p>CFTDEF  CFTHPARM  $DATA00.monfiles.SECPARM</p>
<p>CFTDEF  CFTHACT   $DATA00.monfiles.SECFRACT</p>
<p>CFTDEF  CFTHOBJ   $DATA00.monfiles.SECFROBJ</p></td>
</tr>
<tr class="even">
<td><p>KW     <a href="#manager">MANAGER</a>   <a href="#nb">NB-ATTACH-SET</a></p>
<p>CFTBT    TACL     NBASCFTLI</p></td>
</tr>
<tr class="odd">
<td><p>KW       PARM                  VAL</p>
<p>TCPPARM  TCPIP^HOST^FILE       $SYSTEM.ZTCPIP.HOSTS</p>
<p>TCPPARM  TCPIP^PROCESS^NAME    $ZTC0</p>
<p>TCPPARM  TCPIP^HOST^FILE^2     $SYSTEM.ZTCPIP.HOSTS</p>
<p>TCPPARM  TCPIP^PROCESS^NAME^2  $ZTC0</p></td>
</tr>
<tr class="even">
<td><p>KW       PARM                  VAL</p>
<p><a href="#x25param">X25PARM</a>  X25^CNX^TIME^OUT       40</p></td>
</tr>
<tr class="odd">
<td><p>KW       PARM                  VAL</p>
<p>NONSTOP^RESTART^DELAY           20</p>
<p>NONSTOP^PLIST^TEMP^FILE         $DATA00.montemp.PTMPLIST</p></td>
</tr>
</tbody>
</table>

#### Equivalents in Transfer CFT 3.9

-   <span id="CFTWRK"></span>CFTWRK:
    [cft.guardian.cftwrk](hp_ns_batch.htm#cft.guardian.cftwrk)
-   <span id="CPU"></span>CPU: [cft.guardian.processor](hp_ns_batch.htm#cft.guardian.processor)
-   <span id="TERM"></span>TERM: [cft.guardian.hometerm](hp_ns_batch.htm#cft.guardian.hometerm)
-   <span id="CPUBACKUP"></span>CPUBACKUP: [cft.guardian.backup\_processor](hp_ns_batch.htm#cft.guardian.backup_processor)
-   <span id="PN"></span>PN: [cft.guardian.process\_name\_prefix](hp_ns_batch.htm#cft.guardian.process_name_prefix)
-   <span id="PRI"></span>PRI: [cft.guardian.priority](hp_ns_batch.htm#cft.guardian.priority)
-   <span id="CFTTERM"></span>CFTTERM is no longer supported.
-   <span id="parameters"></span>CFTDEF:
    -   Most parameters have become environment variables that are accessible under OSS.
    -   <span id="CFGSYS"></span>CFGSYS is deprecated.
    -   <span id="TRKCNF"></span>TRKCNF is replaced by the Sentinel configuration in UCONF.
    -   <span id="CFTXFB"></span>CFTXFB is deprecated.
-   <span id="MANAGER"></span>MANAGER: TACL is the default manager.
-   <span id="NB"></span>NB-ATTACH-SET: [cft.guardian.netbatch.attachment\_set](hp_ns_batch.htm#cft.guardian.netbatch.attachment_set).
-   <span id="X25PARAM"></span>X25PARAM is not supported.

## <span id="Upgrade"></span>Upgrade

Before performing an upgrade be certain to review the section [Important information](#importan).

### Overview

You can perform an upgrade by installing Transfer CFT 3.9 over an existing Transfer CFT 3.2.4 installation using the procedure described in [Install Transfer CFT](../installation) . However, the installation directory &lt;installation\_directory> should point to the installation directory of the existing Transfer CFT 3.2.4 installation. You can then provide the same additional parameters.

The installation procedure upgrades Transfer CFT, where the configuration of the existing installation is exported, and is automatically re-imported after the upgrade.

### After auto-importing

The installation creates a new directory called up-&lt;version> in the runtime directory. This directory stores all of the information used during the auto-import process. You can modify the extracted files and directory, and manually re-import this data at any time.

Extracted data

The auto-import directory contains the following:

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>File</th>
<th>Directory</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>cftcat.xml</td>
<td> </td>
<td>Catalog file</td>
</tr>
<tr class="even">
<td>cftcom.xml</td>
<td> </td>
<td>Communication media</td>
</tr>
<tr class="odd">
<td>cftconf.cfg</td>
<td> </td>
<td>The general Transfer CFT configuration, which is applied to the new installation (contained in CFTPARM/CFTPART internal datafiles)</td>
</tr>
<tr class="even">
<td>cftpki.cfg</td>
<td> </td>
<td>The PKI configuration that is applied to the new installation</td>
</tr>
<tr class="odd">
<td> </td>
<td>PKI directory</td>
<td>The extracted SSL certificates</td>
</tr>
</tbody>
</table>

## Client exits and applications

The following rules apply to migrating client exits and client applications:

-   The use of client exits and applications have not changed, but you must recompile the client programs to take into account the new data structure.
-   The new data structures are described in a DDL format, have the same name as in version 2.3.2, and are located in $volume.&lt;subversion>IH.

<!-- -->

-   Additionally, the C language definition derived from the DDL definition is also part of the packaging.
