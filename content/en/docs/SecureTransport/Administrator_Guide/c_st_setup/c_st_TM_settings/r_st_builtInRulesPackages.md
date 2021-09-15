{
    "title": "Built-in rules packages",
    "linkTitle": "Built-in rules packages",
    "weight": "300"
}SecureTransport ships with several predefined rules packages. These packages contain rules used by SecureTransport as part of the standard functionality of the product. Because these rules and packages are part of the product, it is very important that you do not delete or modify the rules or the rules packages. This topic provides a list of the built-in packages and explains their uses.

## Streaming

The following packages control much of the functionality involved with authenticating users and executing transfers. Streaming and InStreaming packages contain the default functionality optimized for performance in the current release.

-   Streaming
-   InStreaming

## Server-initiated transfers

The following packages call agents when a server-initiated transfer is executed. Each rules package represents a different protocol.

-   FolderTransfer
-   FtpTransfer
-   HttpTransfer
-   Pesit
-   PesitTransfer
-   SshTransfer
-   STAS2

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The STAS2 package provides AS2 functionality including file transfer and handling of receipts.         </td>
      </tr>
</table>

## Ad hoc transfers

The following packages support ad hoc file transfers:

-   AddressBook
-   PackageManager

## Applications

The following packages calls the agents used in the corresponding built-in application types:

-   AdvancedRouting
-   ArchiveMaintApp
-   AuditLogMaintApp
-   AxwaySentinel
-   AxwayTransferCFT
-   BasicApp
-   FileServicesInterface
-   HumanSystem
-   LogEntryMaintApp
-   PackageRetentionMaintApp
-   SharedFolder
-   SiteMailbox
-   StandardRouter
-   TransferLogMaintApp
-   UnlicensedAccountMaintApp

The rules are required to trigger the application agent.

## Permission checking

InPermissionCheck represents an implementations of checking file permissions before allowing SecureTransport operations to continue.

InPermissionCheck contains an in-process Java agent. It's efficient and provides basic check based on UID/GID and the file permission flags. For details, see [Access](../../../c_st_accesscontrol).

-   InPermissionCheck

## Other packages

The following packages handle specific SecureTransport functionality.

The following topics describe the other Transaction Manager rules packages:

-   [ArchiveAgent](#archivea)
-   [Axway Sentinel](#sentinel)
-   [ConnectDirectTransfer](#connectd)
-   [FileServicesInterface](#fileserv)
-   [ICAPScan](#icapscan)
-   [MDNReceipting](#mdnrecei)
-   [Pesit and PesitTransfer](#pesit)
-   [PGPTransform](#pgptrans)
-   [Resubmit](#resubmit)
-   [SendToSite](#sendtosi)
-   [ServerTransferNotify](#servertr)
-   [SNMPTransferNotify](#snmptran)
-   [WebServicesAPI](#webservi)

### <span id="ArchiveA"></span>ArchiveAgent

Use this package to archive transferred files. This package is enabled by default. The package copies each transferred file to the archive directory specified in the global File Archiving configuration page. Copied files are renamed to a unique file name to avoid duplicates. The file name format is:

`<File_name><unique_file_name_modifier>`

For example:

`1223375981000_12233759819160.08926095676257206`

The location of the files is as follows:

`<archive_folder>/<account_name>/<login_name>/<relative_path_to_file>/<archived_file>`

Where:

-   `archive_folder` - The archive folder location configured in the global File Archiving configuration page.
-   `account_name` - Name of the account who performed the transfer. When there's no account (for LDAP users for example), account\_name has value of NO\_ACCOUNT.
-   `login_name` - Login name for the user who performed the transfer.
-   `relative_path_to_file` - Path to the file relative to the account's home folder.

For more information, see [Archive Maintenance application](../../../applications/applicationsarchivemaintenance) and [File archiving global configuration](../../c_st_file_archiving/t_st_file_archiving_conf) .

### <span id="Sentinel"></span>Axway Sentinel

This package is enabled by default. SecureTransport uses it to send file transfer and processing events to Axway Sentinel and to call the agent used in a Axway Sentinel Link Data Maintenance application. For more information about configuring SecureTransport to send events to Sentinel, see [Integrate Axway Sentinel](../../c_st_sentinelintegration).

### <span id="ConnectD"></span>ConnectDirectTransfer

Enable this package when you want to create and use a Connect:Direct transfer site. This package is disabled by default. For more information, see [Connect:Direct transfer sites](../../../accounts/transfersites/r_st_connectdirecttransfersites).

### <span id="FileServ"></span>FileServicesInterface

This package is used to implement transfers initiated by SecureTransport using a file services interface protocol.

### <span id="ICAPScan"></span>ICAPScan

This package is used to implement anti-virus or DLP scans initiated by SecureTransport using external ICAP servers. The package is disabled by default and must be enabled if ICAP servers are configured.

### <span id="MDNRecei"></span>MDNReceipting

This package provides functionality to generate MDN receipts for the transferred files. The package is enabled by default.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">To generate MDN receipts, create an <code>mdn</code> certificate in addition to enabling the MDNReceipting package. For more information about the <code>mdn</code> certificate, see <a href="../../c_st_certificates/r_st_certificatestogenerate" xrefformat="{paratext}">Certificates to generate during initial setup</a>.         </td>
      </tr>
</table>

### <span id="Pesit"></span>Pesit and PesitTransfer

These packages provide the functionality for PeSIT protocol operations, including authentication, server-initiated transfers, client-initiated transfers, routed transfers, and acknowledgments. They are enabled by default.

### <span id="PGPTrans"></span>PGPTransform

This package handles PGP encryption and decryption when Advanced Routing is not used. The package is enabled by default.

### <span id="Resubmit"></span>Resubmit

This package contains rules for canceling events. It is enabled by default.

### <span id="SendToSi"></span>SendToSite

Use this package when you want to upload files to a specific site without subscribing an account to an application. This package is disabled by default. This package is used with the **Send Files Directly To** option. For details, see [Subscribe an account to an application](../../../accounts/c_st_subscriptions/t_st_subscriptions).

In order to use `SendToSite` package, enable it and modify its content. For example, by adding a transfer site name as a value to the Site parameter. For details, refer to [Manage rules packages](../t_st_rulespackages).

### <span id="ServerTr"></span>ServerTransferNotify

This package implements HTML email notification for file transfers. This package is disabled by default. For more information, see [Velocity email notification package](../../../c_st_velocityemailnotificationpackage).

### <span id="SNMPTran"></span>SNMPTransferNotify

This package implements SNMP notifications for failed transfers. This package is disabled by default.

SecureTransport includes support for Simple Network Management Protocol (SNMP) v2 and v3 to help you monitor failed transfers. SecureTransport works with SNMP managers such as Hewlett-Packard OpenView Network Node Manager. You can send messages when file transfers fail after retrying the transfer the number of times allotted. SecureTransport provides a trap MIB file located at `<FILEDRIVEHOME>/conf/Transfer.mib`.

1.  Select **Operations > Server Configuration**.  
    The *Server Configuration* page is displayed.
2.  Search for `TransactionManager.SNMP.enabled` and change the value to `true`.
3.  Search for `TransactionManager.SNMP.ManagerHost` and change the value to the IP address of the SNMP manager.
4.  Search for `TransactionManager.SNMP.ManagerPort` and change the value to the port of the SNMP manager.
5.  Set the other `TransactionManager.SNMP.*` server configuration parameters as required by your SNMP manager and configuration
6.  Select **Setup > TM Settings**.  
    The *Rules Packages* page is displayed.
7.  Click **Enable SNMPTransferNotify**.
8.  Select **Operations > Server Control**.
9.  Restart the **TM Server**.
10. Repeat steps 6 through 9 on each server in your cluster.

### <span id="WebServi"></span>WebServicesAPI

This package supports the REST web service file transfer API.
