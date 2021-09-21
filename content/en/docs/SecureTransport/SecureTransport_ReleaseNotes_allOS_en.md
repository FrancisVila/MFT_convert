{
    "title": "Release Notes",
    "linkTitle": "Release Notes",
    "weight": "30"
}<span id="toplink"></span>

Document version: 21 September 2021

SecureTransport 5.5 is a General Availability release. This document applies to: Axway SecureTransport Server 5.5, Axway SecureTransport Edge 5.5, and Axway SecureTransport Web Client 5.5 for all supported platforms, databases, and cluster types.

The information in this document supersedes any corresponding information in the documentation (online or printed) previously supplied for the product.

-   [About this release](#about)
-   [SecureTransport new features and enhancements](#securetransport_new_features_and_enhancements)
-   [ST Web Client new features and enhancements](#st_web_client_new_features_and_enhancements)
-   [Supported platforms and third-party software](#supporte)
-   [SecureTransport corrections and fixed issues](#securetransport_fixed_issues)
-   [ST Web Client general recommendations](#st_web_client_general_recommendations)
-   [Known issues and limitations](#known_issues_and_limitations)
-   [Documentation](#documentation)
-   [Support services](#support_services)

------------------------------------------------------------------------

## <span id="About"></span>About this release

File packages:

-   SecureTransport\_5.5\_Install\_ap-x86-64\_BN114.zip  
    MD5 checksum: b637da5ced8112d454434ffe5e4a9f2b  
    Size: 2.81 GB
-   SecureTransport\_5.5\_UP1-from-7.2\_ap-x86-64\_BN114.zip  
    MD5 checksum: 99a7e8ecfd4584e9bf7c358a1afbd571  
    Size: 2.16GB
-   SecureTransport\_5.5\_Install\_aix-power-64\_BN2306.zip  
    MD5 checksum: eb25e82d631caa83ebd77efa5bd8111b  
    Size: 513.67 MB
-   SecureTransport\_5.5\_Install\_linux-x86-64\_BN2306.zip  
    MD5 checksum: 11433f6723c0a8eed7a65036f4ea9a9c  
    Size: 930.67 MB
-   SecureTransport\_5.5\_Install\_win-x86-64\_BN2306.zip  
    MD5 checksum: 250eafebd345ae76164d7618eac9a985  
    Size: 806.82 MB
-   SecureTransport\_5.5\_UP1-from-5.4\_aix-power-64\_BN2306.zip  
    MD5 checksum: 366acaef18097f55011efb503fd42431  
    Size: 520.77 MB
-   SecureTransport\_5.5\_UP1-from-5.4\_win-x86-64\_BN2306.zip  
    MD5 checksum: f5de32ddce194137ff325ec3aec8ae48  
    Size: 814.7 MB
-   SecureTransport\_5.5\_UP1-from-5.4\_linux-x86-64\_BN2306.zip  
    MD5 checksum: b9f3f59b7a098a6cc0340031c29e720e  
    Size checksum: 937.93 MB
-   SecureTransport\_5.5\_DockerImage\_edge\_linux-x86-64\_BN2306.tar.gz  
    MD5: acb348e30f97439c6db17496de2b0979  
    Size: 448.43 MB
-   SecureTransport\_5.5\_DockerImage\_server\_linux-x86-64\_BN2306.tar.gz  
    MD5 checksum: 8d5cf77edbd62e985cad9552ce4a7003  
    Size: 460.8 MB

[Back to Top](#)

------------------------------------------------------------------------

## <span id="SecureTransport_new_features_and_enhancements"></span>SecureTransport new features and enhancements

The enhancements and improvements in SecureTransport 5.5 Release Notes are organized into several categories:

-   [Deployment enhancements](#deployme)
-   [Extensibility & API enhancements](#extensib)
-   [Reporting enhancements](#reportin)
-   [Functional enhancements](#function)
-   [Security enhancements](#%5Bsecurit)

### <span id="Deployme"></span>Deployment enhancements

1.  [Containerized deployment of SecureTransport Enterprise Cluster](#containerized)
2.  [Zero downtime in active-passive deployment](#zero)
3.  [Option to add SecureTransport Server by FQDN instead of IP address](#option)
4.  [Support for custom JDBC URLs](#support)
5.  [Start/Stop Folder Monitor and Scheduler via Admin REST API and Administration tool](st)
6.  [Report SecureTransport deployment info to Sentinel](#report)
7.  [URL binding support](#urlbind)

#### <span id="Containerized"></span>Containerized deployment of SecureTransport

Starting with the SecureTransport 5.5 release, the SecureTransport administrators have the option to deploy SecureTransport Servers or Edges as Linux (RHEL) Containers using Docker Engine as the container runtime and Kubernetes as the container orchestrator.

The containerized delivery of SecureTransport consists of two docker images (one for Edge and one for Server) that can be downloaded from the [Axway Support Portal](https://support.axway.com "Axway Support").

The support for Kubernetes as container orchestration engine:

-   Simplifies the SecureTransport Edge/Server update procedure
-   Adds the ability to manually and automatically scale the Edge/Server deployments without any additional steps

#### <span id="Zero"></span>Zero downtime in active-passive deployment

With SecureTransport 5.5, the switchover of an active Enterprise cluster to a passive one is facilitated to complete with insignificant to no downtime.

Zero downtime is a concept that allows to smoothly redirect traffic from an active Enterprise cluster to a passive Enterprise cluster without experiencing interruptions in file transfers and event logging. This feature allows you to finish current ongoing transfers on the current cluster and smoothly redirect new ones to your normally passive (backup) cluster.

This is extremely useful for preparing your initially active cluster for upgrades or maintenance while keeping running your current transfers. When necessary, you can use the same zero downtime procedure to switch back to your initial setup.

As part of this feature SecureTransport 5.5 offers the ability to perform graceful shut down of the Transaction manager, Protocol servers or the entire SecureTransport Server node.

##### <span id="Graceful"></span>Graceful shutdown of Transaction Manager

The SecureTransport Administration Tool provides the option to gracefully shut down the Transaction manager server. With this feature you can plan a Transaction Manager stop without abrupt cancellation of current transfers. Note that all protocol servers must be stopped prior Transaction Manager graceful shutdown.

A dedicated configuration option allows the SecureTransport administrator to define the period to "wait" for existing transfers to complete before initiating the shutdown process.

##### <span id="Graceful3"></span>Graceful shutdown of protocol servers

Graceful shutdown of protocol servers allows a shutdown of all servers with the selected protocol daemon without abrupt cancellation of the currently ongoing client-initiated transfer sessions.

Dedicated configuration options per protocol allow the SecureTransport administrator to define the period to "wait" for existing CITs to complete. During that period, new uploads and downloads are not permitted.

##### <span id="Graceful2"></span>Graceful shutdown of SecureTransport Server

As part of this enhancement, the SecureTransport 5.5 administrator can gracefully shut down the SecureTransport Server node. This allows you to stop the SecureTransport server without abrupt cancellation of current transfers.

The dedicated configuration options for Transaction Manager and protocols servers allow the SecureTransport administrator to define the period to "wait" for existing transfers to complete before initiating the shutdown process.

#### <span id="Option"></span>Option to add SecureTransport Server by FQDN instead of IP address

The SecureTransport administrator is given the option to add SecureTransport Server to a cluster by typing its FQDN in the following format: *\[host name\].\[domain\].\[tld\]*. The option is added to the *Operations -> Cluster Management* page in the SecureTransport Administration Tool. This feature is also implemented for external databases in an Enterprise Cluster.

#### <span id="Support"></span>Support for custom JDBC URLs

SecureTransport 5.5 allows database administrators to specify custom JDBC connection strings for Oracle and Microsoft SQL Server databases. This new feature enables SecureTransport to connect to complex Oracle database configurations like Data Guard or combination of RAC and Data Guard. The custom connection string can be configured either via the Administration Tool or the Admin REST API by using the newly introduced /configurations collection that contains resources for managing the database configuration.

#### <span id="Start/St"></span>Start/Stop Folder Monitor and Scheduler via Admin REST API and Administration tool

With SecureTransport 5.5, the option to start and/or stop the Folder Monitor and Scheduler are added to the Extended Server Control page in the SecureTransport Administration tool. As part of this feature, corresponding start and stop resources are exposed in the Admin REST API.

#### <span id="Report"></span>Report SecureTransport deployment info to Sentinel

With SecureTransport 5.5, reporting to Sentinel is enhanced with the following changes:

-   `XFB ST Info` - a new object which contains various SecureTransport deployment info including: number of active accounts, product version, current patch version, list of installed plugins and their versions, etc.
-   `XFB Transfer` - the Transfer object is now reported with an additional property: `EnvironmentId`.

The new SecureTransport 5.5 package for Sentinel is available for download on Axway Support website.

#### <span id="URLbind"></span>URL binding support

SecureTransport 5.5 offers basic support for URL binding. This allows SecureTransport servers (both SecureTransport Edge and Server) to work behind a load balancer that does not support 'sticky-sessions'. When a SecureTransport HTTP server is reached, the browser URL is replaced with the configured one allowing unobstructed processing.

[Back to Top](#)

------------------------------------------------------------------------

### <span id="Extensib"></span>Extensibility and API enhancements

1.  [End-user & Admin REST API version 2.0](#api2)
2.  [Pluggable Authorization enhancements](#pluggabl)
3.  [Pluggable Authentication expression evaluator](#pluggabl2)
4.  [Pluggable Transfer Site enhancements](#pluggabl3)
5.  [Pluggable Advanced Routing Step SPI 1.1](#pluggabl4)

#### <span id="API2"></span>End-user & Admin REST API version 2.0

With the release of SecureTransport 5.5, a new version of the End-user & Admin API services is presented: 2.0. Compared to previous versions, the 2.0 of both APIs provide more consistency and compliance with latest practices.

An important improvement is the simplified Partner onboarding by allowing you set up a partner account with bulk configurations.

The Admin API offers several new resources including options to view and change various configurations (LDAP domains, clustered management, file archiving, etc.).

Apart from new resources and consistency, the admin API includes features such as:

-   field filtering - the ability to specify preferred sets of returned data (as selections from a large list)
-   field search - the ability to find objects based on common properties (for example, get a list of all transfer sites that are using a specified host server)
-   wildcard search in File Tracking - several scenarios to retrieve file transfers by starting or trailing symbols (or both), as well as filenames containing any string, etc.

#### <span id="Pluggabl"></span>Pluggable Authorization enhancements

-   Certificate and SSL context service in Pluggable Authorization:
    -   The CertificateService allows validation of login certificate against the SecureTransport certificate stores, as well as specific certificate attributes in custom authorization flows.
    -   The SSLContext service can be used to establish secure SSL connections to external services from within the plugins.
-   An Expression evaluator service is added to allow evaluation and validation of expressions used in custom authorization plugins.

#### <span id="Pluggabl2"></span>Pluggable Authentication expression evaluator

An Expression evaluator service is added to allow evaluation and validation of expressions used in custom authentication plugins.

#### <span id="Pluggabl3"></span>Pluggable Transfer Site enhancements

-   SPI 1.7 exposes a new service - `SSLContextService` - that can be used when connecting over a secure connection to a remote partner.
-   custom parameters can be added in REST API Pull requests and used in any Transfer Site.
-   custom parameters can be added in REST API Pull requests and preserved in a sequential Advance Routing step (for example Send To Partner)
-   a generic log method added with Pluggable Transfer Sites
-   ability to notify SecureTransport for executed post-transmission actions (PTAs) to report in SecureTransport File Tracking
-   two new services are exposed - `TransferAttributesData` and `AccountAttributesData` - that can be respectively used for reading *transfer* and *account*-related attributes of the currently transferred file.
-   The Certificate Service of Pluggable Transfer Sites is now able to get the complete x509 certificate.
-   The Certificate Authentication mechanism is improved to support multiple plugins.
-   Plugins can pass two new properties through the *RemotePartner* object - one for identifying the network connection port and one for identifying the remote impersonated entity.
-   Plugins can also report executed PTAs to File Tracking.

#### <span id="Pluggabl4"></span>Pluggable Advanced Routing Step SPI 1.1

Pluggable AR Step SPI 1.1 exposes three new services - `CertificateService`, `LoggingService`, and `ExpressionEvaluatorService` - that can be used for certificate parsing and validation against the SecureTransport keystore, logging messages, and exceptions with a different log level, evaluating and validating expressions.

[Back to Top](#)

------------------------------------------------------------------------

### <span id="Reportin"></span>Reporting enhancements

1.  [Improved SecureTransport to Sentinel reporting](#improved3)
2.  [End-to-end tracking of files transferred over SFTP](#end-to-e)
3.  [New Sentinel property: Parent Cycle ID](#new)
4.  [New uniform XFB Tracked Object format](#new2)
5.  [Improved monitoring of secure server-initiated transfers](#improved)
6.  [Improved monitoring of secure client-initiated transfers](#improved2)
7.  [Audit log performance improvement](#audit)

#### <span id="Improved3"></span>Improved SecureTransport to Sentinel reporting

The reporting of transfer related events to Axway Sentinel is improved. The following Sentinel attributes are now reported in more states for both PeSIT and non-PeSIT transfers:

-   SenderId
-   ReceiverId
-   OriginalSenderId
-   FinalReceiverId
-   UserID
-   Site

In addition, the RFC code of the cipher suite used during an SSL/TLS session is now reported to Axway Sentinel in the SSLCypher attribute.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">To use this enhancement, you need to install the new version of SecureTransport Package for Sentinel.         </td>
      </tr>
</table>

#### <span id="End-to-e"></span>End-to-end tracking of files transferred over SFTP

SecureTransport 5.5 supports Sentinel end-to-end tracking of SFTP transfers established across the following Axway products: SecureTransport and Transfer CFT. The events reported in Sentinel for a single transfer are reported with the same CycleId.

End-to-end reporting covers the below SFTP file transfer cases, with SecureTransport acting as either server or client when transferring files with Transfer CFT.

#### <span id="New"></span>New Sentinel property: Parent Cycle ID

SecureTransport now reports the Parent Cycle ID in the XFB tracked object.

#### <span id="Improved"></span>Improved monitoring of secure server-initiated transfers

The Server log functionality is extended to provide detailed information about each server-initiated transfer for which an SSL connection is successfully negotiated. For such transfers, a message with the following information is shown in the server log:

-   Account name and login name on the server that initiated the transfer
-   Client IP address
-   Negotiated cipher suite

#### <span id="Improved2"></span>Improved monitoring of secure client-initiated transfers

The Server log functionality is extended to provide detailed information about each Client initiated transfer for which an SSL connection is successfully negotiated. For such transfers, a message with the following information is shown in the server log:

-   Account name and login name of the client that initiated the transfer
-   Client IP address
-   Negotiated cipher suite

#### <span id="Audit"></span>Audit log performance improvement

The SecureTransport performance is improved on auditing complex accounts with multiple routes and subscriptions.

[Back to Top](#)

------------------------------------------------------------------------

### <span id="Function"></span>Functional enhancements

1.  [File Maintenance enhancements](#fileretention)
2.  [Account Maintenance enhancements](#account)
3.  [Enhanced Authorization and Authentication Service](#eaas)
4.  [Extended LDAP domain search](#extendedldap)
5.  [Unified SPI services for all user exits](#unispi)
6.  [Configurable Pre-connection in PeSIT Transfer Sites](#configur)
7.  [PeSIT Store and Forward improvements](#pesit)
8.  [Automatic detection of the client SSL mode for PeSIT transfers](#automati)
9.  [Test SSH Transfer site connection](#test)
10. [Max Parallel Transfers per Transfer Site](#max)
11. [Alternative connection endpoints](#alternat)
12. [Support for FTP Append with server-initiated transfers using FTP](#support3)
13. [Superuser execution of External Script in Advanced Routing step](#superuse)
14. [Trace log messages from third-party libraries](#trace)
15. [Option to disable folder auto-creation for Publish steps](#disable)
16. [Improved monitoring of active users](#improved)
17. [Scheduling server-initiated file downloads using cron expressions](#scheduli)
18. [Display of user account data: account creation date, last modified](#display)
19. [Removing weekends from holiday schedule](#remove)
20. [Deprecation of status\_checker and monitor scripts](#deprecat)
21. [New method of registering SecureTransport in Central Governance](#removal)
22. [Dual authentication per User class](#dual)
23. [Folder Monitor failover improvements](#folder)

#### <span id="FileRetention"></span>File Maintenance enhancements

File management in SecureTransport is extended with new options that allow the SecureTransport administrators to automate deletion of old files in the accounts’ home folders, based on age, expiry date, or a matching file name pattern.

As part of this, the administrator can add logic and templates for email notifications regarding file deletion.

File Maintenance is introduced on a global, Business Unit, Account Template or individual User account level. A dedicated File Maintenance application is introduced to perform the actions on a defined schedule.

#### <span id="Account"></span>Account Maintenance enhancements

User account management in SecureTransport 5.5 is extended with new options that allow the SecureTransport administrator to automate the user account lifecycle management by setting criteria for the user account lifetime and prospects upon lifetime expiration – disabling, deletion or purging.

As part of this, the administrator can add logic and templates for email notifications to users about a performed action, password expiry or certificates expiry.

Account Maintenance is introduced on a global, Business Unit or individual User account level. A dedicated Account Maintenance application is introduced to perform the actions on a defined schedule.

#### <span id="EAAS"></span>Enhanced Authorization and Authentication Service

The functionality of the former Extended Authentication and Authorization add-on (EAAS) is added to the SecureTransport 5.5 core feature set and the authentication and authorization user exits. It includes:

-   Extended LDAP domain search
-   Unified `LoggingService` and `CertificateService` for all custom user exits

#### <span id="ExtendedLDAP"></span>Extended LDAP domain search

With this feature, the LDAP search in the SecureTransport Administration Tool is extended in a way that allows the SecureTransport administrator to use any LDAP parameter in a generic search query without additional appending.

#### <span id="UniSPI"></span>Unified SPI services for all user exits

The Logging, Certificate, and Expression Evaluator services have been unified to provide common functionality for all user exits. As part of this task, the `LoggingService` is added in the Advanced Routing exit, while the previously used method for logging messages is kept for backwards compatibility. The `ExpressionEvaluatorService` (the ability to evaluate user defined expressions) is added to the authentication and authorization exits.

#### <span id="Configur"></span>Configurable Pre-connection in PeSIT Transfer Sites

The PeSIT transfer site configuration is enhanced with options to add Server ID and password and validate it against a Partner ID and password in the PeSIT pre-connection phase.

#### <span id="PeSIT"></span>PeSIT Store and Forward improvements

SecureTransport 5.5 administrators are able to specify the Originator, Final destination, Store and Forward mode, and Connection timeout per PeSIT transfer site. The Originator can also be specified when creating a Send to Partner route step.

#### <span id="Automati"></span>Automatic detection of the client SSL mode for PeSIT transfers

The PeSIT Transfer Site restriction to communicate with Transfer CFT over PeSIT SSL/TLS Legacy mode only was removed and a new PeSIT listener with auto-detect SSL mode capabilities is introduced. It is able to detect the SSL mode used by the client and serve requests in both SSL COMP and SSL LEGACY modes. Dedicated configuration options allow the SecureTransport administrator to define the following settings for the listener: status, port number, key alias, key algorithm, trust algorithm, and protocol.

#### <span id="Test"></span>Test SSH Transfer site connection

SecureTransport 5.5 administrators are able to check if an SSH transfer site connection to the remote partner is configured correctly. Available both as user interface in the Administration Tool and exposed as an admin REST API resource. This allows SecureTransport administrators to:

-   Test Connection before or after saving the Transfer Site
-   Automate the testing of existing transfer sites
-   Test by overriding parameters of a Transfer Site

#### <span id="Max"></span>Max Parallel Transfers per Transfer Site

A configuration for Maximum Parallel Transfers is added to the following transfer sites:

-   AS2
-   FTP(S)
-   SSH
-   Generic-HTTP(S)

As part of this, recommended configurations for increased payload in Enterprise and Standard clusters are added.

#### <span id="Alternat"></span>Alternative connection endpoints

SecureTransport 5.5 introduces the option to add a list of alternative connection endpoints to transfer sites. These endpoints act as backup alternatives to the configured Server-Port Site Settings and are particularly useful in cases of transfer failures.

The SecureTransport administrator can provide ordered lists of endpoints (in the format of IP address or localhost entries) to FTP, HTTP(S), AS2, SSH, and PeSIT transfer sites.

#### <span id="Support3"></span>Support for FTP Append with server-initiated transfers using FTP

The FTP transfer site settings are expanded with an option to use the `APPE `(append) upload command with server-initiated transfers.

The Add Transfer Site settings page for FTP transfer sites now includes the Upload command drop-down list with the following options: `STOR`(default) or `APPE`.

As part of this feature, the upload command used is reported to Axway Sentinel and displayed in the Protocol Parameter attribute.

#### `GET version` resource updated in REST API

The `GET version` resource of the Admin REST API (v1.4 and v2.0) is updated to use the following new properties:

-   `updateLevel` returns the latest successfully installed update.
-   `updateHistory` returns all updates that are successfully installed on the current SecureTransport implementation. If the current SecureTransport service pack/patch is successfully removed, this update will be removed from update history.
-   `spiVersions` returns the supported SPIs and their versions.

#### <span id="Superuse"></span>Superuser execution of External Script in Advanced Routing step

Advanced Routing now allows super user execution of external scripts on the External script step.

#### <span id="Trace"></span>Trace log messages from third-party libraries

The Pluggable Transfer Site functionality in SecureTransport now allows tracing log messages. In this way, SecureTransport clients can log custom messages from third-party libraries.

#### <span id="Disable"></span>Option to disable folder auto-creation for Publish steps

The Publish to account step in Advanced Routing is enhanced with a check-box option to disable auto-creation of a target folder upon step execution.

#### <span id="Improved"></span>Improved monitoring of active users

The Active Users page in the SecureTransport Administration Tool shows the total of currently used licenses. The active users count is also available via the Admin REST API.

#### <span id="Scheduli"></span>Scheduling server-initiated file downloads using cron expressions

The Scheduler now supports cron expressions in Quartz v.1.8.6. Cron expressions can be used for scheduling server-initiated file downloads and maintenance jobs.

#### <span id="Display"></span>Display of user account data: account creation date, last modified

The SecureTransport 5.5 administrator can view user account related data about account creation date and date of last modification. This feature is not available for LDAP users.

#### <span id="Remove"></span>Removing weekends from holiday schedule

The SecureTransport 5.5 administrator can define weekends as regular working days in the holiday schedule.

#### <span id="Deprecat"></span>Deprecation of statuschecker and monitor scripts

The `status_checker` and `monitor` scripts available in previous versions of SecureTransport are now deprecated.

#### <span id="Removal"></span>New method of registering SecureTransport in Central Governance

Starting with SecureTransport 5.5 onward, the registration with Central Governance will occur only on Central Governance level.

As a result, the Central Governance Registration files and the dedicated page in the SecureTransport Administration Tool are removed from the product.

#### <span id="Dual"></span>Dual authentication per User class

The *Login Settings* page in the SecureTransport Administration Tool allows offers options to set dual authentication for selected User classes.

#### <span id="Folder"></span>Folder Monitor failover improvements

The Folder Monitor failover mechanism is improved to prevent execution of folder monitor service on more than one node in Enterprise Cluster.

Two new configuration options are introduced to control the heartbeat mechanism:

-   `FolderMonitor.heartbeatInterval`: heartbeat is going to be sent on specified interval of seconds. Default value is `5` sec.
-   `FolderMonitor.heartbeatTimeout`: the timeout in seconds after which the Folder Monitor holder will be changed. Default value is `60` sec.

**Note:** The SecureTransport Standard Cluster is not affected.

[Back to Top](#)

------------------------------------------------------------------------

### <span id="[Securit"></span>Security enhancements

1.  [Multi-protocol listeners](#multi-pr)
2.  [Extended list of supported ciphers and algorithms for SSH](#extended)
3.  [Policy for Minimum password age](#policy)
4.  [File Tracking and Server Log enhancements: Display of originating IP addresses of users behind proxy](#file)
5.  [HTTP "Strict-Transport-Security" header with AS2 transfers](#http)
6.  [DSA key-based authentication for SFTP transfers](#dsa)
7.  [Configurable HTTP security headers](#configur)
8.  [Configurable cipher suites per transfer site](#configur2)
9.  [Configurable minimum length for answer to secret question](#configur3)

#### <span id="Multi-pr"></span>Multi-protocol listeners

With SecureTransport 5.5, the option to add multiple listeners per protocol server is added. You can now configure additional listeners to your FTP, HTTP, AS2, SSH and PeSIT servers.

The new functionality is introduced to the revamped appearance of the Server Control screen in the SecureTransport Administration Tool.

#### <span id="Extended"></span>Extended list of supported ciphers and algorithms for SSH

The Maverick client/server and common versions are upgraded, which helps extend the list of the SSH ciphers, Key Exchange and MAC algorithms supported in SecureTransport.

#### <span id="Policy"></span>Policy for Minimum password age

The new password policy allows the SecureTransport administrator to set a minimum period (in days) for a repeated password change. This means that when a user changes their password, they will not be allowed to perform this action again until the minimum password age period expires.

#### <span id="File"></span>File Tracking and Server Log enhancements: Display of originating IP addresses of users behind proxy

File tracking now displays the original IP address of user accounts that perform transfers behind a proxy or a load balancer. As part of this enhancement, the Server Log displays the login, logout and file transfer IP address of a user behind a proxy/load balancer. The new parameter uses the `X-Forwarded-For` HTTP header for fetching the original IP address of a user account.

#### <span id="HTTP"></span>HTTP "Strict-Transport-Security" header with AS2 transfers

The `Strict Transport-Security` HTTP header is now added to AS2 server messages for improved security in AS2 transfers.

#### <span id="DSA"></span>DSA key-based authentication for SFTP transfers

SSH keys generated with DSA can be used in SSH transfer sites for initiating server transfers.

#### <span id="Configur"></span>Configurable HTTP security headers

SecureTransport adds support for security HTTP headers: `Content-Security-Policy`, `X-XSS-Protection`, `X-Content-Type-Options`, `Referrer-Policy` and `Expect-CT`.
These headers can be enabled using a dedicated Server Configuration option. The options are per HTTP server.

#### <span id="Configur2"></span>Configurable cipher suites per transfer site

This feature allows the SecureTransport administrator to configure cipher suites with a selected transfer site for secure server-initiated transfers. Available in *Advanced SSL settings* for AS2, FTP, HTTPS, SFTP and PeSIT transfer sites.

#### <span id="Configur3"></span>Configurable minimum length for answer to secret question

A dedicated Server Configuration option allows the SecureTransport administrator to configure the required minimum length of the answer to secret questions for users.

[Back to Top](#)

------------------------------------------------------------------------

## <span id="ST_Web_Client_new_features_and_enhancements"></span>ST Web Client enhancements

1.  [GZIP compression of selected static resources file formats for improved HTTP performance](#gzip)
2.  [Removed deprecated setting in ST Web Client 1.34](#removed)
3.  [More detailed information for files and folders](#more)
4.  [Alert on invalid file format](#alert)
5.  [Configurable default settings in Share dialog](#set)
6.  [Security updates](#security)
7.  [ST Web Client version information](#securetransport)
8.  [Pre-login disclaimer banner](#pre-logi)
9.  [Branding improvements](#branding)
10. [Optimized startup](#optimize)
11. [Custom links in the user menu](#custom)
12. [Warning on active uploads when navigating away](#warning)
13. [Message of the day](#message)
14. [Adjustable columns of Uploads monitor](#adjustab2)
15. [Additional ST Web Client enhancements](#addition)

### <span id="GZIP"></span>GZIP compression of selected static resources file formats for improved HTTP performance

With this feature the SecureTransport administrator can extend the list of static resources file formats for GZIP compression to reduce data traffic and loading time of all ST Web Client pages served by the HTTP server.

### <span id="Removed"></span>Removed deprecated setting in ST Web Client 1.34

The previously deprecated `features.secretQuestion.newPasswordResetApi` setting has been removed. When set to `false`, it was used to call the legacy reset password API.

### <span id="More"></span>More detailed information for files and folders

The ST Web Client end-users can see more detailed information about files and folders. The View Details dialog now shows the file's CoreID and MD5 checksum, which can be used for verifying its authenticity. For shared folders, the View Details dialog shows all the collaborators.

### <span id="Alert"></span>Alert on invalid file format

The ST Web Client shows a more informative error message when the custom configuration file (`stwebclient.config.json`) has an invalid format or cannot be accessed.

### <span id="Set"></span>Configurable default settings in Share dialog

Administrators can set the default Share dialog settings:

-   the default selection of the Action menu
-   the default states of the checkboxes located under Options and Notifications.

The defaults are applied when a folder is shared for the first time. For already shared folders, the Share dialog opens with the existing sharing settings pre-selected.

### <span id="Security"></span>Security updates

To keep the ST Web Client up to date with the latest security fixes, nearly all third-party libraries used in the client are updated to their latest versions. The jsRender library is removed, and the `Content-Security-Policy `HTTP header can be set to a more restrictive value.

### <span id="SecureTransport"></span>ST Web Client version information

An About section is added to the Welcome menu to allow end-users to quickly identify the version of the ST Web Client they are using. The About dialog contains a logo that can be customized by modifying the ST Web Client custom configuration file.

### <span id="Pre-logi"></span>Pre-login disclaimer banner

Administrators can configure a disclaimer banner that is displayed to users before they log in. The banner can contain legal statements that must be accepted before a user can continue to the login process. The disclaimer can be set to appear either before every login attempt or once per user/browser. The user confirmation is stored locally along with a content hash to ensure the disclaimer will pop again when its content changes.

### <span id="Branding"></span>Branding improvements

You can customize the colors of the ST Web Client user interface to reflect your company's branding, and add your own content on the login page and on the pages logged in users can access.

### <span id="Optimize"></span>Optimized startup time

Startup optimizations include the reduced size of the initial bundle and faster page load.

### <span id="Custom"></span>Custom links in the user menu

Custom links can be added to the ST Web client user menu. They appear between the last menu item and the Logout one. The functionality supports translations with the i18n module.

### <span id="Warning"></span>Warning on active uploads when navigating away

To prevent accidental upload interruptions, the ST Web Client displays a warning dialog when the user navigates away from the application while an upload is in progress.

### <span id="Message"></span>Message of the day

The SecureTransport 5.5 administrator can set a notification message to display to ST Web Client users after log-in.

### <span id="Adjustab2"></span>Adjustable columns of Uploads monitor

The Uploads monitor table is improved with adjustable order and size of columns: the end user can move columns and resize them to a preferred layout. The latest adjustment is preserved in a cookie.

### <span id="Addition"></span>Additional ST Web Client enhancements

-   Versioning is added to JavaScript plugins bundles using webpack plugins allows long-term browser caching of resources and to prevent downloading them multiple times.
-   Improved performance and faster loading times
-   React is adopted more extensively in ST Web Client
-   ST Web Client 5.5 uses the 2.0 version of the end-user REST API
-   Open folder from URL allows a folder to be opened typing its path in the URL `<SecureTransport URL>/path/to/folder`
-   Browser history enhancement allows the use of the browser "Go forward" and "Go back" buttons for navigation to previously opened folders
-   Accessibility help is now translatable - all labels are described in *translation.json*

[Back to Top](#)

------------------------------------------------------------------------

## <span id="Supporte"></span>Supported platforms and third-party software

1.  [Support for PostgreSQL 12](#postgresup)
2.  [SecureTransport 5.5 Virtual Appliance](#new3)
3.  [Chrome browser support](#chrome_sup)
4.  [Migration to Java 11](#java_sup)
5.  [Updated Operating System Support](#newos)
6.  [Updated Database support](#newdb)
7.  [Updated File System support](#newfs)
8.  [Updated Cloud File Storage support](#newcloud)

### <span id="PostgreSup"></span>New database support: PostgreSQL 12

SecureTransport 5.5 supports PostgreSQL 12 as an external database for Enterprise Cluster deployments. Automated migration is available for existing customers using Oracle databases.

### <span id="New3"></span>SecureTransport 5.5 Virtual Appliance

SecureTransport 5.5 is available as a 64-bit virtual appliance running SuSE Linux Enterprise Server 12 SP5.

### <span id="Chrome_sup"></span>Chrome browser support

The SecureTransport 5.5 Administration Tool is supported on the latest versions of the Google Chrome browser.

### <span id="Java_sup"></span>Migration to Java 11 - OpenJDK

The migration to Java 11- OpenJDK adds numerous optimizations and fixes multiple security vulnerabilities.

### <span id="NewOS"></span>Updated Operating System support

-   CentOS 8
-   Oracle Linux 8
-   Red Hat Enterprise Linux 8
-   Windows Server 2016
-   Windows Server 2019
-   SuSE Linux Enterprise Server 12 SP5

### <span id="NewDB"></span>Updated database support

-   Microsoft SQL Server 2017 and Microsoft SQL Server 2019
-   Oracle 18c and Oracle 19c
-   Amazon RDS for supported releases of Oracle Database and Microsoft SQL Server

### <span id="NewFS"></span>Updated File System support

-   GFS2
-   IBM Spectrum Scale (GPFS) 5

### <span id="NewCloud"></span>Updated Cloud File Storage support

-   Amazon Elastic File System (EFS)

[Back to Top](#)

------------------------------------------------------------------------

## <span id="SecureTransport_fixed_issues"></span>SecureTransport corrections and fixed issues

### Fixed security vulnerabilities

SecureTransport 5.5 provides the following fixed security vulnerabilities:

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Case ID</th>
         <th>Internal ID</th>
         <th>CVE ID</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>01144864<br/>01153461<br/>01140233<br/>01145760<br/>01147797         </td>
         <td>RDST-30212 RDST-30213<br/>         </td>
         <td>CVE-2019-17569 <br/>CVE-2020-1935<br/>CVE-2019-17569         </td>
         <td>Apache Tomcat vulnerabilities are fixed with the upgrade of the Apache Tomcat library to 7.0.103.         </td>
      </tr>
      <tr>
         <td>01055204         </td>
         <td>RDST-19886         </td>
         <td>CWE-757         </td>
         <td>
            <p><strong>Issue:</strong> Previously, TLS Fallback Signaling Cipher Suite Value" (SCSV) was not supported and this posed a risk of client-side or server-side protocol downgrade.<br/></p>
            <p><strong>Resolution:</strong> Now, with the update to Java 11, this issue is fixed.</p>
         </td>
      </tr>
      <tr>
         <td>01050795<br/>01065944<br/>01133882         </td>
         <td>RDST-21584         </td>
         <td>none         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the default ErrorReportValve was including the Apache Tomcat version number in the response headers.<br/></p>
            <p><strong>Resolution:</strong> Now, the Apache Tomcat version is not included in the response headers.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>00944323</p>
         </td>
         <td>
            <p>RDST-12178</p>
         </td>
         <td>none         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SecureTransport was vulnerable to host header (host redirection) attacks.<br/></p>
            <p><strong>Resolution:</strong> Now, two new configuration options are introduced to control the list of accepted host headers for the Admin and the Public webservices, respectively:</p>
            <ul>
               <li><code>Webservices.Admin.Host.Whitelist</code>
               </li>
               <li><code>Webservices.Public.Host.Whitelist</code>
               </li>
            </ul>
            <p>Both options accept regular expressions.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>00945674</p>
         </td>
         <td>
            <p>RDST-12181</p>
         </td>
         <td>none         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SecureTransport was using the default session ID length.</p>
            <p><strong>Resolution:</strong> Now, session ID is increased to 128 bits in length.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>00975445</p>
         </td>
         <td>
            <p>RDST-14611</p>
            <p>RDST-14583</p>
         </td>
         <td>CVE-2016-1000031         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SecureTransport was vulnerable to CVE-2016-1000031 due to an old version of Apache Commons FileUpload being used.<br/></p>
            <p><strong>Resolution:</strong> Now, SecureTransport has upgraded to a non-vulnerable version of Apache Commons FileUpload.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>00975445</p>
            <p>00994853</p>
         </td>
         <td>
            <p>RDST-14626</p>
            <p>RDST-15993</p>
         </td>
         <td>
            <p>CVE-2015-9251</p>
            <p>CVE-2012-6708</p>
         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the SecureTransport Administration Tool was vulnerable to CVE-2015-9251 and CVE-2012-6708 due to an outdated version of jQuery 1.7.</p>
            <p>The SecureTransport Administration Tool was using an outdated version of Angular 1.3.4 with several vulnerabilities, including arbitrary code execution and multiple XSS paths.</p>
            <p>Swagger-UI version was 2.2.10-1 containing outdated version of jQuery 1.7.</p>
            <p><strong>Resolution:</strong> Now, jQuery version is updated to 3.4.1 and Angular version to 1.7.9 both containing the latest security fixes. The Swagger-UI version is updated to 3.25.0.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>00976582</p>
         </td>
         <td>
            <p>RDST-14908</p>
         </td>
         <td>none         </td>
         <td>
            <p><strong>Issue:</strong> Previously, some GET requests containing sensitive data did not have appropriate Cache-Control settings.<br/></p>
            <p><strong>Resolution:</strong> Now, the Cache-Control header is configured correctly, and the user's browser does not store sensitive content in the <em>browser cache</em>.</p>
         </td>
      </tr>
      <tr>
         <td>01033585         </td>
         <td>RDST-19574         </td>
         <td>none         </td>
         <td>
            <p><b>Issue:</b> Previously, wrong header values resulted in sensitive information exposure.<br/></p>
            <p><b>Resolution:</b> Now, the error is handled properly and no sensitive information is exposed.</p>
         </td>
      </tr>
   </tbody>
</table>

### Fixed issues per SecureTransport Patches

SecureTransport 5.5 provides the following corrections and fixed issues:

1.  [Fixes in SecureTransport 5.2.1](#fixes)
2.  [Fixes in SecureTransport 5.3.1](#fixes2)
3.  [Fixes in SecureTransport 5.3.3](#fixes3)
4.  [Fixes in SecureTransport 5.3.6](#fixes4)
5.  [Fixes in SecureTransport 5.4](#fixes5)
6.  [Additional fixes](#addition)
7.  [Known issues and limitations](#known_issues_and_limitations)

#### <span id="Fixes"></span>Fixes in SecureTransport 5.2.1

<table cellspacing="0">
   <colgroup>      
   <col/>
   <col/>
   <col/>
   </colgroup>
   <thead>
      <tr>
         <th>Case ID</th>
         <th>Internal ID</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td colspan="3"><b>SecureTransport 5.2.1 SP 9 Patch 5</b>
         </td>
      </tr>
      <tr>
         <td>00906676         </td>
         <td>RDST-17645         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the ST Web Client user had to refresh the page in order to download an AdHoc attachment.<br/></p>
            <p><strong>Resolution:</strong> Now, download of an AdHoc attachment works without refreshing the page.
					</p>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>00989203         </td>
         <td>RDST-17648         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SecureTransport was vulnerable to CVE-2014-3527 and CVE-2014-0097 due to an old version of <code>spring-security-web.jar</code> used. <br/></p>
            <p><strong>Resolution:</strong> Now, the <code>spring-security-web.jar</code> dependency is removed and SecureTransport is no longer vulnerable.
					</p>
         </td>
      </tr>
      <tr>
         <td colspan="3">
            <p><strong>SecureTransport 5.2.1 SP 8 Patch 4</strong>
</p>
         </td>
      </tr>
      <tr>
         <td>00911779         </td>
         <td>RDST-14327         </td>
         <td>
            <p><strong>Issue:</strong> Previously, <code>isAlert=1</code> was wrongly reported to Sentinel when <code>EventQueue.maxRetryCount</code> was set to 1.<br/></p>
            <p><strong>Resolution:</strong> Now, <code>isAlert=1</code> is correctly reported to Sentinel regardless of the <code>EventQueue.maxRetryCount</code> value.</p>
         </td>
      </tr>
   </tbody>
</table>

#### <span id="Fixes2"></span>Fixes in SecureTransport 5.3.1

The following corrections and fixed issues have been addressed:

<table cellspacing="0">
   <colgroup>      
   <col/>
   <col/>
   <col/>
   </colgroup>
   <thead>
      <tr>
         <th>Case ID</th>
         <th>Internal ID</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td colspan="3"><b>SecureTransport 5.3.1 Patch 19</b>
         </td>
      </tr>
      <tr>
         <td>
            <p>Patch 19</p>
            <p>00921250</p>
         </td>
         <td>RDST-19618         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the SecureTransport REST API was returning duplicate JSON object entries that were containing different values with some resources.<br/></p>
            <p><strong>Resolution:</strong> Now, when a SecureTransport REST API resource contains duplicate JSON object entries, those are returned as an array data structure.  
						</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Patch 19</p>00946682         </td>
         <td>RDST-14310            <p>RDST-19624</p>         </td>
         <td>
            <p><strong>Issue:</strong> Previously, an incorrect HTTP code (<code>204 No Content</code>) was returned with some unsuccessful POST requests to the <code>subscriptions</code> resource in the SecureTransport REST API.<br/></p>
            <p><strong>Resolution:</strong> Now, the proper HTTP code is returned in the specified cases. (<code>422 - Unprocessable Entity</code>.)
						</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Patch 19</p>00993966         </td>
         <td>RDST-19630         </td>
         <td>
            <p><strong>Issue:</strong> Previously, there was a significant delay in end user login times when SecureTransport was operating under heavy load.<br/></p>
            <p><strong>Resolution:</strong> Now, delays in the end user log-in attempts are greatly minimized.<br/></p>
         </td>
      </tr>
   </tbody>
</table>

#### <span id="Fixes3"></span>Fixes in SecureTransport 5.3.3

The following corrections and fixed issues have been addressed:

<table cellspacing="0">
   <colgroup>      
   <col/>
   <col/>
   <col/>
   </colgroup>
   <thead>
      <tr>
         <th>Case ID</th>
         <th>Internal ID</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td colspan="3"><strong>SecureTransport 5.3.3 Patch 32</strong>
         </td>
      </tr>
      <tr>
         <td>
            <p>Patch 32</p>
            <p>00985109</p>
         </td>
         <td>RDST-18162         </td>
         <td>
            <p><strong>Issue:</strong> Previously, Advanced Routing was failing on Windows due to OS limitation in file path size.
						<br/></p>
            <p><strong>Resolution:</strong> Now, Advanced Routing does not fail on Windows due to OS limitation in file path size.
					</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Patch 32</p>00965624         </td>
         <td>RDST-18159         </td>
         <td>
            <p><strong>Issue:</strong> Previously, when the Admin daemon on SecureTransport Server was trying to get some properties from an Edge server over streaming protocol, but an error occurred meanwhile in the process, the hostname of that Edge server was not logged.<br/></p>
            <p><strong>Resolution:</strong> Now, the hostname of the Edge server is logged when error occurs. 
				</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Patch 32</p>00957942          </td>
         <td>RDST-18160         </td>
         <td>
            <p><strong>Issue:</strong> Previously, not enough information was logged during execution of the Archive Maintenance Application.<br/></p>
            <p><strong>Resolution:</strong> Now, detailed information like total files deleted, folder name, and execution period is logged.</p>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>
            <p>Patch 32</p>00968865         </td>
         <td>RDST-18158         </td>
         <td>
            <p><strong>Issue:</strong> Previously, wildcard pulls in the REST API Files resource were not working properly when sorting returned entries.<br/></p>
            <p><strong>Resolution:</strong> Now, the wildcard pull for this resource are working as expected.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Patch 32</p>00955625         </td>
         <td>RDST-18161         </td>
         <td>
            <p><strong>Issue:</strong> Previously, if a remote post transition action failed, transferred files could not arrive to the final destination.<br/></p>
            <p><strong>Resolution:</strong> Now, if a remote post transition action fails, transferred files arrive to the final destination successfully.</p>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>
            <p>Patch 32</p>00931791         </td>
         <td>	RDST-18157         </td>
         <td>
            <p><strong>Issue:</strong> Previously, there was a possibility of a session leak when a client logged on and immediately logged off over SSH protocol.
						This was highly dependent on the timing. <br/></p>
            <p><strong>Resolution:</strong> Now, no sessions leak in such a scenario. <br/><strong>Note:</strong> If you see the following warning on console: <code>log4j:WARN No appenders could be found for logger (sessions).</code>, you may safely ignore it.</p>
         </td>
      </tr>
      <tr>
         <td colspan="3">
            <p><strong>SecureTransport 5.3.3 Patch 30</strong>
</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Patch 30</p>
            <p>00957994</p>
         </td>
         <td>RDST-14810         </td>
         <td>
            <p><strong>Issue:</strong> Previously, when archiving was enabled and the archiving directory ran out of disk space, all file uploads were failing.
			<br/></p>
            <p><strong>Resolution:</strong> Now, when the archiving directory is full, the original file transfer processes successfully and indicates a failed sub-transmission in the archiving process.
			</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Patch 30</p>
            <p>00950376<br/>00934360
			</p>
         </td>
         <td>RDST-14811         </td>
         <td>
            <p><strong>Issue:</strong> Previously, server-initiated pull transfers were failing if a post-transmission action was set in a transfer site.
			<br/></p>
            <p><strong>Resolution:</strong> Now, transfers in such setup are successful.
			</p>
         </td>
      </tr>
      <tr>
         <td colspan="3">
            <p><strong>SecureTransport 5.3.3 Patch 29</strong>
</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Patch 29</p>
            <p>00951918<br/>00951922</p>
         </td>
         <td>RDST-13938         </td>
         <td>
            <p><strong>Issue:</strong> Previously, file globbing was not working with the REST API Files operation.<br/></p>
            <p><strong>Resolution:</strong> Now, file globbing is working properly with the REST API Files operation.</p>
         </td>
      </tr>
   </tbody>
</table>

#### <span id="Fixes4"></span>Fixes in SecureTransport 5.3.6

The following corrections and fixed issues have been addressed:

<table cellspacing="0">
   <colgroup>      
   <col/>
   <col/>
   <col/>
   </colgroup>
   <thead>
      <tr>
         <th>Case ID</th>
         <th>Internal ID</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td colspan="3"><strong>SecureTransport 5.3.6 Patch 50</strong>
         </td>
      </tr>
      <tr>
         <td>
            <p>Patch 50</p>
            <p>01070697</p>
         </td>
         <td>RDST-25085         </td>
         <td>
            <p><strong>Issue:</strong> Previously, master administrators without permissions to the Certificates page were not able to view the local certificates when creating or updating a transfer site.<br/></p>
            <p><strong>Resolution:</strong> Now, master administrators without permissions to the Certificates page can view and use the local certificates through the REST API as well as in the Administration Tool when creating or updating a transfer site.
						</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Patch 50</p>
            <p>01060712</p>
         </td>
         <td>RDST-25084         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SecureTransport was vulnerable to CVE-2017-7957 due to an outdated version of the Xstream library.<br/></p>
            <p><strong>Resolution:</strong> Now, Xstream is updated to v1.4.11.1; the denyTypes workaround, provided with SecureTransport 5.3.6 Patch 8 (RDST-7721), is removed as it’s no longer needed.
						</p>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>
            <p>Patch 50</p>
            <p>none</p>
         </td>
         <td>RDST-25077         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SecureTransport was vulnerable to CVE-2019-14379 due to an outdated version of FasterXML jackson-databind.<br/></p>
            <p><strong>Resolution:</strong> Now, SecureTransport uses updated Jackson libraries:
							</p>
            <ul>
               <li>jackson-databind v2.9.9.3               </li>
               <li>jackson-core v2.9.9               </li>
               <li>jackson-annotations v2.9.9               </li>
               <li>jackson-dataformat-yaml v2.9.9               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td colspan="3">
<p colspan="3"><strong>SecureTransport 5.3.6 Patch 49</strong>
</p>
         </td>
      </tr>
      <tr>
         <td>Patch 49<br/>01084561         </td>
         <td>RDST-24163         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the <code>Users.SecretAnswer.MinLength</code> option was incorrectly exposed in the SecureTransport EDGE server configuration settings. The option was removed with Patch 48. but the change was not reflected in the documentation.<br/></p>
            <p><strong>Resolution:</strong> Now, in a streaming (Server + Edge) deployment, the value of the <code>Users.SecretAnswer.MinLength</code> parameter can be set only from the SecureTransport Server configuration options, and the instructions on setting a minimum length for the secret question answer are up-to-date.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 49<br/>01084566         </td>
         <td>RDST-24161         </td>
         <td>
            <p><strong>Issue:</strong> Previously, when the <code>AuditLog.Enabled.CollectionLog</code> configuration option was set to <code>false</code>, SecureTransport displayed an error in the server log on unchecking the <strong>Allow this account to login to SecureTransport Server</strong> checkbox.<br/></p>
            <p><strong>Resolution:</strong> Now, when <code>AuditLog.Enabled.CollectionLog</code> set to <code>false</code>, only an information message for disallowing an account to log into SecureTransport is displayed in the server log.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 49<br/>01081029         </td>
         <td>RDST-24159         </td>
         <td>Following the latest security best practices, the storing mechanism for sensitive data in SecureTransport is further enhanced to withstand attacks.
						         </td>
      </tr>
      <tr>
         <td colspan="3">
<p colspan="3"><strong>SecureTransport 5.3.6 Patch 48</strong>
</p>
         </td>
      </tr>
      <tr>
         <td>Patch 48<br/>01058200         </td>
         <td>RDST-23609         </td>
         <td>
            <p><strong>Issue:</strong> Previously, failed to transfer files were deleted from the Connect:Direct temporary folder only on Transaction Manager start. <br/></p>
            <p><strong>Resolution:</strong> Now, a new configuration option <code>ExternalServerTransferAgent.temporaryDirectoryPurge</code> is introduced that  allows administrators to control the deletion of files from the temporary folder. <br/>Possible values:
							</p>
            <ul>
               <li><code>false </code>(default) - the temporary folder is cleared on Transaction Manager start.               </li>
               <li><code>true</code> - the temporary folder is cleared when a server-initiated push over Connect:Direct fails.               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>Patch 48<br/>01073380         </td>
         <td>RDST-23605         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the REST API allowed configuring <code>/</code> (root) as a base folder and thus setting a user home folder under <code>/</code> which could pose risks especially on root installations. <br/></p>
            <p><strong>Resolution:</strong> Now, SecureTransport checks if the absolute home folder path supplied via the REST API is a concatenation of a valid base folder path (other than <code>/</code> (root)) and the home folder path.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 48<br/>01066092         </td>
         <td>RDST-23606         </td>
         <td>
            <p><strong>Issue:</strong> Previously, when the <code>com.maverick.sshd.events</code> logger was set to debug, the message body was formatted incorrectly and included newline characters. As a result, log messages couldn't be parsed into useful information. <br/></p>
            <p><strong>Resolution:</strong> Now, the logger presents all content of the message on a single line following the SecureTransport logs convention. All events can be matched and parsed correctly.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 48<br/>01020970         </td>
         <td>RDST-23608         </td>
         <td>
            <p><strong>Issue:</strong> Previously, certain REST API end-user resources did not return information about the operation result in the response body. <br/></p>
            <p><strong>Resolution:</strong> Now, with SecureTransport End-User API version 1.5, schema definitions are added to Swagger and resources are modified to return the operation result in the response body.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 48<br/>01020970         </td>
         <td>RDST-23607         </td>
         <td>
            <p><strong>Issue:</strong> Previously, some of the <strong>/myself</strong> and <strong>/files</strong> REST API end-user resources were returning incorrect response codes. <br/></p>
            <p><strong>Resolution:</strong> Now, SecureTransport End-User API is updated to version 1.5, and the correct response codes are returned.
						</p>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>Patch 48<br/>01033091         </td>
         <td>RDST-22294         </td>
         <td>
            <p><strong>Issue:</strong> Previously, on EC setup using Oracle database, the deletion of a network zone used by more than 10,000 transfer sites could take a significant amount of time and eventually fail due to a system timeout. <br/></p>
            <p><strong>Resolution:</strong> Now, deleting a network zone is significantly faster.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 48<br/>01016532         </td>
         <td>RDST-23610         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the information about the ST_DATA tablespace in the SecureTransport Capacity Planning Guide was not detailed enough.<br/></p>
            <p><strong>Resolution:</strong> Now, the SecureTransport Capacity Planning Guide is updated with detail information about the ST_DATA tablespace.</p>
         </td>
      </tr>
      <tr>
         <td>Patch 48<br/>01039650         </td>
         <td>RDST-23612         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the SecureTransport Installation Guide was providing incomplete instructions for setting up Oracle database correctly.<br/></p>
            <p><strong>Resolution:</strong> Now, the SecureTransport Installation Guide is updated with the correct instructions to set an Oracle database.
						</p>
         </td>
      </tr>
      <tr>
         <td colspan="3">
<p colspan="3"><strong>SecureTransport 5.3.6 Patch 47</strong>
</p>
         </td>
      </tr>
      <tr>
         <td>Patch 47<br/>01054469<br/>01061573<br/>01061795         </td>
         <td>RDST-22714         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the SecureTransport Administration Tool and ST Web Client were vulnerable to CVE-2019-11358 due to an outdated version of jQuery (3.3.1).
							<br/></p>
            <p><strong>Resolution:</strong> Now, jQuery is updated to version 3.4.1 which contains the latest security fixes.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 47<br/>01066941         </td>
         <td>RDST-22716         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SecureTransport was vulnerable to CVE-2019-5427 due to an outdated version of the c3p0 library (0.9.2.1).
							<br/></p>
            <p><strong>Resolution:</strong> Now, c3p0 is updated to version 0.9.5.4 which fixes the vulnerability.
						</p>
         </td>
      </tr>
      <tr>
         <td colspan="3">
<p colspan="3"><strong>SecureTransport 5.3.6 Patch 46</strong>
</p>
         </td>
      </tr>
      <tr>
         <td>Patch 46<br/>01022572         </td>
         <td>RDST-22218         </td>
         <td>
            <p><strong>Issue:</strong> Previously, when Repository encryption was enabled, there was a delay in initiating large file downloads due to the whole file being read.
							<br/></p>
            <p><strong>Resolution:</strong> Now, the download is initiated immediately as the file is not read anymore.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 46<br/>01044707         </td>
         <td>RDST-22221         </td>
         <td>
            <p><strong>Issue:</strong> Previously, when Repository encryption was enabled, there was an exponential upload speed degradation due to the whole file being read at the beginning of every chunk upload.
							<br/></p>
            <p><strong>Resolution:</strong> Now, there is no upload speed degradation, and only the first chunk of the file is read.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 46<br/>01061137         </td>
         <td>RDST-22220         </td>
         <td>
            <p><strong>Issue:</strong> Previously, there was a memory leak in the Transaction Manager related to the caching of stfs attributes, which were never cleared.
							<br/></p>
            <p><strong>Resolution:</strong> Now, a time-based caching mechanism is used which evicts entries after the configured timeout or when the capacity is reached. The timeout and the capacity are configured by the <code>Stfs.attributes.cache.timeout</code> and <code>Stfs.attributes.cache.size</code> configuration options.
						</p>
         </td>
      </tr>
      <tr>
         <td colspan="3"><b>SecureTransport 5.3.6 Patch 45</b>
         </td>
      </tr>
      <tr>
         <td>Patch 45<br/>00949613 01039198         </td>
         <td>RDST-21847         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SecureTransport didn't limit the number of the simultaneous connections to the remote server when pulling files using the ‘Maximum number of parallel transfers’ from the subscription.
							<br/></p>
            <p><strong>Resolution:</strong> Now, SecureTransport limits the simultaneous connections to the number specified in the ‘Maximum number of parallel transfers’ field in the subscription.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 45<br/>01028659         </td>
         <td>RDST-21852         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the administrator could not set a minimum length for the secret question answers.
							<br/></p>
            <p><strong>Resolution:</strong> Now, the administrator can specify the minimum length of the secret question answers using the <code>Users.SecretAnswer.MinLength </code> configuration option.
							<br/><strong> Note</strong>: Changes to the <code>Users.SecretAnswer.MinLength </code> configuration option require Transaction Manager service restart on all nodes in the cluster.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 45<br/>01037290         </td>
         <td>RDST-21464         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SecureTransport didn’t evaluate properly the <code>User ID</code> and <code>Group ID</code> attributes for the user class custom expressions which resulted in users being assigned to an incorrect user class.
							<br/></p>
            <p><strong>Resolution:</strong> Now, UID and GID are populated in the environment as <code>DXAGENT_USERUID</code> and <code>DXAGENT_USERGID</code>, respectively, and SecureTransport determines the proper user class for a user.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 45<br/>00997187         </td>
         <td>
            <p>RDST-21477</p>
            <p>RDST-21478</p>
         </td>
         <td>
            <p><strong>Issue:</strong> Previously, when pushing files via Connect:Direct or Multipoint Binary File Transfer, temporary folders were created with hardcoded permissions(drwxr-xr-x), making pulls impossible in certain occasions.
							<br/></p>
            <p><strong>Resolution:</strong> Now, administrators can set suitable temporary directory permissions for Connect:Direct and Multipoint Binary File transfers using the <code>ExternalServerTransferAgent.temporaryDirectoryPermissions </code> configuration option.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 45<br/>01042087         </td>
         <td>RDST-20213         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SSH transfers were processing at low speeds on networks with high latency.<br/></p>
            <p><strong>Resolution:</strong> Now, new configuration settings are introduced in the <code>start_sshd</code> script to allow improving the SSH transfer speeds in high latency networks. The SecureTransport administrator can specify buffer sizes for inbound / outbound transfers, as well as values for minimum and maximum window space, as follows:
							</p>
            <ul>
               <li><code>-DrecvBufferSize</code> - 8192 by default               </li>
               <li><code>-DsendBufferSize</code> - 8192 by default               </li>
               <li><code>-Dssh.maxWindowSpace</code> - 1048576 by default               </li>
               <li><code>-Dssh.minWindowSpace</code> - 131072 by default               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>Patch 45<br/>01032957         </td>
         <td>RDST-21479         </td>
         <td>
            <p><strong>Issue:</strong> Previously, POST requests of an XML formatted Certificate object to <strong>/certificates/export</strong> in REST API v1.4 failed with response code 400(Bad Request).
							<br/></p>
            <p><strong>Resolution:</strong> Now, POST requests of XML formatted Certificates to <strong>/certificates/export</strong> are successful.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 45<br/>01032957         </td>
         <td>RDST-21465         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the documentation for the <strong>/certificates/export</strong> resource in Swagger was incomplete.
							<br/></p>
            <p><strong>Resolution:</strong> Now, the documentation for the <strong>/certificates/export</strong> resource in Swagger is updated.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 45<br/>01027570         </td>
         <td>RDST-21849         </td>
         <td>
            <p><strong>Issue:</strong> Previously, deleting subscriptions with a configured schedule prevented users from logging in and uploading files. 
							<br/></p>
            <p><strong>Resolution:</strong> Now, this issue is fixed.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 45<br/>01037795         </td>
         <td>RDST-21476         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the logger <code>com.tumbleweed.st.server.sshd.logging</code> was missing information that helps identifying the users who triggered Maverick events. 
							<br/></p>
            <p><strong>Resolution:</strong> Now, the logger provides information about the <code>accountId</code>, <code>remoteAddress</code> and <code>sessionId</code>.
						</p>
         </td>
      </tr>
      <tr>
         <td colspan="3"><strong>SecureTransport 5.3.6 Patch 43</strong>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>Patch 43<br/>01023580<br/>01003989         </td>
         <td>RDST-15308         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SecureTransport failed to transfer files containing <code>LF</code> file endings which were processed by Pluggable Transfer Sites due to an incorrectly calculated file size.
							<br/></p>
            <p><strong>Resolution:</strong> Now, this issue is fixed.
						</p>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>Patch 43<br/>01019734         </td>
         <td>RDST-18337         </td>
         <td>
            <p><strong>Issue:</strong> Previously, ST Web Client was taking a lot of time to load on IE 11 on Windows 7.
							<br/></p>
            <p><strong>Resolution:</strong> Now, ST Web Client loading times are similar across all supported browsers.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 43<br/>01011995         </td>
         <td>RDST-19285         </td>
         <td>
            <p><strong>Issue:</strong> Previously, in the case when SecureTransport was configured to move the sandbox to a local folder, it would not evaluate any expression language used in the Home folder string. This resulted in the creation of a common subfolder for all accounts that were using Advanced Routing, regardless of account type. <br/></p>
            <p><strong>Resolution:</strong> Now, a new configuration option is added: <code>AdvancedRouting.sandboxFolderLocation.expressionLanguage</code>. When set to <code>true</code>, the folder from <code>AdvancedRouting.sandboxFolderLocation</code>, if set, will be evaluated as expression language. This, for example, allows the SecureTransport administrator to separate sandbox subfolders by account type.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 43<br/>01017781         </td>
         <td>RDST-19296         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SecureTransport used to print verbose messages for SSH connections using the <code>com.maverick.sshd.events</code> package logger. <br/></p>
            <p><strong>Resolution:</strong> Now, the SecureTransport internal Maverick library is upgraded and those messages are not available on the specified logger. A new logger is introduced and must be used on debug level, using the following package: <code>com.tumbleweed.st.server.sshd.logging</code>.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 43<br/>01015773         </td>
         <td>RDST-19294         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SecureTransport was not sending PI 28 (Record Number) to Axway Sentinel with PeSIT transfers. <br/></p>
            <p><strong>Resolution:</strong> Now, SecureTransport is reporting to Axway Sentinel the Record Number with each PeSIT transfer.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 43<br/>01009818         </td>
         <td>RDST-19282         </td>
         <td>
            <p><strong>Issue:</strong> Previously, updating properties of a site template that was being used by multiple sites, was taking a lot of time or was resulting in an internal server error. <br/></p>
            <p><strong>Resolution:</strong> Now, updating properties of a site template that is being used by multiple sites, does not cause errors and takes much less time.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 43<br/>01012540<br/>01019982         </td>
         <td>RDST-19292         </td>
         <td>
            <p><strong>Issue:</strong> Previously, if the mail notification for the Route step in Advanced Routing was configured before applying Patch 39, installing patch 39 or later was reverting the <strong>Mail Template</strong> value to <code>None</code> and the SecureTransport administrator had to re-configure it. <br/></p>
            <p><strong>Resolution:</strong> Now, with the upgrade to Patch 43 the selected values for mail templates are preserved with the correct properties.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 43<br/>01009843         </td>
         <td>RDST-19287         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the transferLog maintenance application was failing to export partitions on rare occasions because of a database operation timeout. <br/></p>
            <p><strong>Resolution:</strong> Now, each transferLog partition table is successfully exported through a new database session.</p>
         </td>
      </tr>
      <tr>
         <td colspan="3"><strong>SecureTransport 5.3.6 Patch 41</strong>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>Patch 41<br/>00900125         </td>
         <td>RDST-7347         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the REST API documentation (api/v1.4/docs/index.html) was lacking descriptive information and complete model schema for <strong>/accounts</strong> resource.
							<br/></p>
            <p><strong>Resolution:</strong> Now, missing properties from the REST API documentation are added in the model schema.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 41<br/>00962638         </td>
         <td>RDST-18061         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SecureTransport did not decrypt files that were encrypted with repository encryption when performing server-initiated transfers over AS2, so the transferred files were still encrypted on the receiving side and could not be used.<br/></p>
            <p><strong>Resolution:</strong> Now, SecureTransport decrypts successfully files that are encrypted with repository encryption when performing server-initiated transfers over AS2 and the files are usable on the receiving side.</p>
         </td>
      </tr>
      <tr>
         <td>Patch 41<br/>01005467         </td>
         <td>RDST-18063         </td>
         <td>
            <p><strong>Issue:</strong> Previously, attempts to update a siteTemplate element of an existing siteTemplate using the REST API was not successful but a <code>HTTP 204 No Content</code> success status response code was returned.<br/></p>
            <p><strong>Resolution:</strong> Now siteTemplate can be updated successfully with a proper response code.
					</p>
         </td>
      </tr>
      <tr>
         <td>Patch 41<br/>01013180         </td>
         <td>RDST-18101         </td>
         <td>
            <p><strong>Issue:</strong> Previously, updating an account property via the REST API was resetting all properties to what was configured in the Business Unit.
						<br/></p>
            <p><strong>Resolution:</strong> Now, after an update via the REST API, only the affected property / properties are affected by the changes.
					</p>
         </td>
      </tr>
      <tr>
         <td>Patch 41<br/>00900125         </td>
         <td>RDST-18059         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the REST API documentation (api/v1.4/docs/index.html) was lacking descriptive information and complete model schema for /accounts resource.
						<br/></p>
            <p><strong>Resolution:</strong> Now, missing properties from the REST API documentation are added in the model schema.
				</p>
         </td>
      </tr>
      <tr>
         <td>Patch 41<br/>01014312         </td>
         <td>RDST-18108         </td>
         <td>
            <p><strong>Issue:</strong> Previously, when the <code>AuditLog.Enabled.Admin</code> configuration property was set to <code>true</code>, the audit logging was disabled in both - Server Log and Audit Log.<br/></p>
            <p><strong>Resolution:</strong>				Now, a new configuration property is introduced - <code>AuditLog.Enabled.AuditLogMenu</code>, that allows the SecureTransport administrator to disable audit logging of the Audit Log only while preserving Audit messages in the Server Log.</p>
         </td>
      </tr>
      <tr>
         <td colspan="3"><strong>SecureTransport 5.3.6 Patch 40</strong>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>Patch 40<br/>01008970<br/>01002107<br/>01007724         </td>
         <td>RDST-17231         </td>
         <td>
            <p><strong>Issue:</strong> Previously, on each subscription display (new or existing, regardless of the ownership), several Connect:Direct entries were being added to the list with transfer site types.<br/></p>
            <p><strong>Resolution:</strong> Now, this issue is fixed.
					</p>
         </td>
      </tr>
      <tr>
         <td>Patch 40<br/>00987905         </td>
         <td>RDST-17863         </td>
         <td>
            <p><strong>Issue:</strong> Previously, when file names were containing control characters, the Transfer and Xfer logs were broken and reported those files with incorrect names.<br/></p>
            <p><strong>Resolution:</strong> Now, the respective logs report those characters correctly as part of the file name.
					</p>
         </td>
      </tr>
      <tr>
         <td>Patch 40<br/>00939429         </td>
         <td>RDST-17558         </td>
         <td>
            <p><strong>Issue:</strong> Previously, subscription "Delete" PTAs did not trigger when they were set using the REST API.<br/></p>
            <p><strong>Resolution:</strong> Now, these events are successfully triggered.
					</p>
         </td>
      </tr>
      <tr>
         <td>Patch 40<br/>01008361         </td>
         <td>RDST-18056         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the chosen "Select An Account" value in the Send To Partner step was incorrectly displayed.
						<br/></p>
            <p><strong>Resolution:</strong> Now, the chosen "Select An Account" value in the Send To Partner step displays properly.
					</p>
         </td>
      </tr>
      <tr>
         <td>Patch 40<br/>00992353         </td>
         <td>RDST-18055         </td>
         <td>
            <p><strong>Issue:</strong> Previously, it was not possible to configure deletion of file if a HTTP transfer failed because of
						integrity check.<br/></p>
            <p><strong>Resolution:</strong> A new configuration option <code>Http.DeleteFileOnFailedIntegrityCheck</code> is introduced. When set to <code>true</code>, the uploaded file will be deleted if the integrity check fails.<br/><strong>Note:</strong> The default value is <code>false</code>. No restart is needed if the
value is changed.
					</p>
         </td>
      </tr>
      <tr>
         <td>Patch 40<br/>00987152         </td>
         <td>RDST-17653         </td>
         <td>The SecureTransport Administrator REST API Swagger documentation is updated with some missing properties.         </td>
      </tr>
      <tr>
         <td>Patch 40<br/>00991461         </td>
         <td>RDST-17650         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the common convention for audit log entries was broken, because in some places the username that was triggering an audit event was not passed, or appeared as "unknown" or "Admin".
<br/></p>
            <p><strong>Resolution:</strong> Now, an unknown user that triggers an audit event is logged as "System". Empty usernames are replaced with the correct ones. Quotes in these audit messages are removed.
					</p>
         </td>
      </tr>
      <tr>
         <td>Patch 40<br/>0997986         </td>
         <td>RDST-17285         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SecureTransport was relying on the operating system filesystem to check, validate and resolve file names, in this case - preserving trailing whitespaces at the end of file names.
						<br/></p>
            <p><strong>Resolution:</strong> Now, SecureTransport explicitly strips trailing whitespaces at the end of file names.
					</p>
         </td>
      </tr>
      <tr>
         <td> Patch 40<br/>00988323         </td>
         <td>RDST-17656         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SecureTransport administration tool was failing to display some pages due to old versions of <code>commons-dbcp</code> and <code>commons-pool</code> libraries. <br/></p>
            <p><strong>Resolution:</strong> Now, <code>commons-dbcp</code> and <code>commons-pool</code> libraries are updated to versions 1.4 and 1.6.
					</p>
         </td>
      </tr>
      <tr>
         <td colspan="3">
            <p><b>SecureTransport 5.3.6 Patch 39</b>
</p>
         </td>
      </tr>
      <tr>
         <td>Patch 39<br/>00982157         </td>
         <td>RDST-17505         </td>
         <td>
            <p><strong>Issue:</strong> Previously, reassigning account (with route package based on a template assigned to a specific BU) to another BU was causing an Internal Server Error.<br/></p>
            <p><strong>Resolution:</strong> Now, such attempt fails with a proper error message.
					</p>
         </td>
      </tr>
      <tr>
         <td>Patch 39<br/>00982154         </td>
         <td>RDST-17281         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SecureTransport was checking each BU, unassigned from a route package template, for accounts who have such route packages.<br/></p>
            <p><strong>Resolution:</strong> Now, SecureTransport does not perform such checks if the template does not have any BUs assigned afterwards, since it becomes globally accessible.
					</p>
         </td>
      </tr>
      <tr>
         <td>Patch 39<br/>00967577<br/>00979675         </td>
         <td>RDST-17019         </td>
         <td>
            <p><strong>Issue:</strong> Previously, it was not possible to disable archiving for <code>Send to partner</code> step.<br/></p>
            <p><strong>Resolution:</strong> Now, a new configuration option <code>AdvancedRouting.DisableSendToPartnerArchiving</code> is introduced. When set to <code>true</code>, the archiving is disabled for <code>Send to partner</code> step.
						<br/></p>
            <p><strong>Note:</strong> The default value is <code>false</code>.
					</p>
         </td>
      </tr>
      <tr>
         <td>Patch 39<br/>00953578<br/>00961378<br/>00974685         </td>
         <td>RDST-17283         </td>
         <td>
            <p><strong>Issue:</strong> Previously, if the Advanced Expression for Download Folder was not checked in the transfer site settings, remote folder was missing from file tracking report.
						<br/></p>
            <p><strong>Resolution:</strong> Now, if the Advanced Expression for Download Folder is not checked in the transfer site settings, remote folder is populated into file tracking report.
					</p>
         </td>
      </tr>
      <tr>
         <td colspan="3"><b>SecureTransport 5.3.6 Patch 38</b>
         </td>
      </tr>
      <tr>
         <td>Patch 38<br/>00976807         </td>
         <td>RDST-16665         </td>
         <td>
            <p><strong>Issue:</strong> Previously, when using the REST API to import a certificate, the access level of this certificate was not preserved.
                    <br/></p>
            <p><strong>Resolution:</strong> Now, when using the REST API to import a certificate, the access level of the imported certificate is preserved.
                </p>
         </td>
      </tr>
      <tr>
         <td>Patch 38<br/>00995494         </td>
         <td>RDST-17483         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the decompressing of <code>.zip</code> and <code>.gzip</code> archives in Advanced Routing was extremely slow, when using repository encryption under IBM AIX.
                <br/></p>
            <p><strong>Resolution:</strong> Now, there is a significant performance improvement in that scenario.
              </p>
         </td>
      </tr>
      <tr>
         <td>Patch 38<br/>00984565         </td>
         <td>RDST-16664         </td>
         <td>
            <p><strong>Issue:</strong> Previously, verbose error messages were found to be returned within the HTTP responses.
                <br/></p>
            <p><strong>Resolution:</strong> Now, generic error messages are used instead.
              </p>
         </td>
      </tr>
      <tr>
         <td colspan="3"><b>SecureTransport 5.3.6 Patch 37</b>
         </td>
      </tr>
      <tr>
         <td>Patch 37<br/>00991984         </td>
         <td>RDST-17415         </td>
         <td>
            <p><strong>Issue:</strong> Previously, additional ports opened by FTPs, HTTPs and TM services were accepting connections over TLSv1.0.<br/></p>
            <p><strong>Resolution:</strong> Now, these additional ports do not accept connections over TLSv1.0 and listen on localhost only.<br/></p>
            <p><strong> Note</strong>: The Transaction Manager and PeSIT services open random high number ports which are accessible only from <code>127.0.0.1.</code></p>
         </td>
      </tr>
      <tr>
         <td colspan="3"><b>SecureTransport 5.3.6 Patch 36</b>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>Patch 36<br/>00958217         </td>
         <td>RDST-14892         </td>
         <td>
            <p><strong>Issue:</strong> Previously, when downloading a large file from ST Web Client, the user was redirected to a timeout page after session timeout.
							<br/></p>
            <p><strong>Resolution:</strong> Now, a download polling mechanism is added to prevent the client-side session timeout. Download polling is configurable and is disabled by default. <br/></p>
            <p><strong>Note:</strong> Download polling depends on transfers API.
						The "<i>Allow this account to submit transfers using the Transfers RESTful API</i>" option must be enabled for the user.</p>
         </td>
      </tr>
      <tr>
         <td>Patch 36<br/>00978338         </td>
         <td>RDST-15896         </td>
         <td>
            <p><strong>Issue:</strong> Previously, disabling of "Share" functionality in ST Web Client <code>stwebclient.config.json</code> had incorrect behavior - "Share" was present in folders tree.
						<br/></p>
            <p><strong>Resolution:</strong> Now, "Share" functionality can be completely turned off from <code>stwebclient.config.json</code>. 
					</p>
         </td>
      </tr>
      <tr>
         <td>Patch 36<br/>00971345         </td>
         <td>RDST-15935         </td>
         <td>
            <p><strong>Issue:</strong> Previously, if a file signed with <code>-clearsign</code> option is submitted to a PGP Decrypt step for decryption / validation, advanced routing step fails with "NoSuchFileException". <br/></p>
            <p><strong>Resolution:</strong> Now the file signature is checked and removed after that, and the file is processed.<br/></p>
         </td>
      </tr>
      <tr>
         <td>Patch 36<br/>00920309<br/>00970508<br/>00973694         </td>
         <td>RDST-15902         </td>
         <td>
            <p><strong>Issue:</strong> Previously, when having an expired certificate in the keystore on IBM AIX, an error was thrown and the http and ftp daemons couldn't not start.<br/></p>
            <p><strong>Resolution:</strong> Now, when having an expired certificate in the keystore on IBM AIX, http and ftp daemons are started without errors.<br/></p>
         </td>
      </tr>
      <tr>
         <td>Patch 36<br/>00973492         </td>
         <td>RDST-15501         </td>
         <td>
            <p><strong>Issue:</strong> Previously, Advanced Routing line ending transformation step was not transforming properly LF to CRLF, when file with CRLF was provided<br/></p>
            <p><strong>Resolution:</strong> Now, Advanced Routing line ending transformation step is transforming properly LF to CRLF, when file with CRLF is provided.
					</p>
         </td>
      </tr>
      <tr>
         <td>Patch 36<br/>00976853         </td>
         <td>RDST-15933         </td>
         <td>
            <p><strong>Issue:</strong> Previously, serialization of huge amount of objects, that contain metadata links, by the REST API could fail.<br/></p>
            <p><strong>Resolution:</strong> Now, this issue is fixed.
					</p>
         </td>
      </tr>
      <tr>
         <td colspan="3"><b>SecureTransport 5.3.6 Patch 35</b>
         </td>
      </tr>
      <tr>
         <td>Patch 35<br/>00965736<br/>00969586<br/>         </td>
         <td>RDST-14275         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the number of the accounts was decreasing after a password change in the Administration Tool.<br/></p>
            <p><strong>Resolution:</strong> Now, number of the accounts remains unchanged when an account password is changed.
					</p>
         </td>
      </tr>
      <tr>
         <td>Patch 35<br/>00966110<br/>00954272<br/>00974386         </td>
         <td>RDST-14714         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SFTP transfers were failing with bigger files when a buffer size was specified.<br/></p>
            <p><strong>Resolution:</strong> Now, SFTP transfers are successful regardless if a buffer size is specified or not.<br/></p>
            <p><strong>Note:</strong>The Maverick (client/server and common) version was upgraded from 1.7.12/1.7.12 to 1.7.15/1.7.16 and 1.3.1 to 1.3.4.
					</p>
         </td>
      </tr>
      <tr>
         <td colspan="3"><b>SecureTransport 5.3.6 Patch 34</b>
         </td>
      </tr>
      <tr>
         <td>Patch 34<br/>00978764         </td>
         <td>RDST-15438         </td>
         <td>
            <p><strong>Issue:</strong> Previously, calculating the certificate chains was slow in establishing the streaming connections when having many certificates.<br/></p>
            <p><strong>Resolution:</strong> Now, this process is optimized because certificate chain calculation is performed only when a new certificate is added or imported.<br/></p>
            <p><strong>Note:</strong> In order to have the correct certificate chain on AS2 daemon, the existing certificate should be re-created or exported and then re-imported back again.
					</p>
         </td>
      </tr>
      <tr>
         <td colspan="3"><strong>SecureTransport 5.3.6 Patch 33</strong>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>Patch 33<br/>00906578         </td>
         <td>RDST-8341         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SecureTransport was vulnerable to CWE-732. 
			<br/></p>
            <p><strong>Resolution:</strong> Now, SecureTransport is no longer vulnerable to CWE-732.
			</p>
         </td>
      </tr>
      <tr>
         <td>Patch 33<br/>00910414         </td>
         <td>RDST-14457         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the end user using SecureTransport Legacy skin was not able to navigate to a parent directory when SecureTransport was behind an IBM WebSeal reverse proxy. 
				<br/></p>
            <p><strong>Resolution:</strong> Now, the end user can navigate in such a setup.
			</p>
         </td>
      </tr>
      <tr>
         <td>Patch 33<br/>00967933         </td>
         <td>RDST-14893         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the SecureTransport admin Swagger API website was not loading in Internet Explorer.
				<br/></p>
            <p><strong>Resolution:</strong> Now, it is possible to open and use Secure Transport admin Swagger API website in Internet Explorer.
			</p>
         </td>
      </tr>
      <tr>
         <td>Patch 33<br/>00950795         </td>
         <td>RDST-14887         </td>
         <td>
            <p><strong>Issue:</strong> Previously, received encrypted files over AS2 were temporarily stored with the same file name.
				<br/></p>
            <p><strong>Resolution:</strong> Now, there is a new configuration option <code>As2.Unique.Smime.Name</code> that allows SecureTransport to add a unique part to the temporary file name.<br/></p>
            <p><strong>Note:</strong> In order to apply change of value of the new configuration option, you must restart the Transaction Manager service on all nodes in the cluster.
			</p>
         </td>
      </tr>
      <tr>
         <td>Patch 33<br/>00962139         </td>
         <td>RDST-14890         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the SecureTransport Administrator was not able to fully manipulate query which was executed against LDAP on AddressBook search.<br/></p>
            <p><strong>Resolution:</strong> Now there is new property checkbox, which disables every search parameters that SecureTransport appends by default and allows the Administrator to fully define the search attributes and search query of AddressBook LDAP.</p>
         </td>
      </tr>
      <tr>
         <td>Patch 33<br/>00918358<br/>00896128         </td>
         <td>RDST-14878         </td>
         <td>
            <p><strong>Issue:</strong> Previously, with SecureTransport running on Windows server, subscriptions were not getting triggered, when a user was navigating to a folder with the same name, but different case letter sizes.
				<br/></p>
            <p><strong>Resolution:</strong> Now, with SecureTransport on Windows server, subscription gets triggered when a user goes to a folder with the same name, but different case letter sizes.
			</p>
         </td>
      </tr>
      <tr>
         <td>Patch 33<br/>00951920         </td>
         <td>RDST-13199         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the Advanced Routing decompress step was failing with <code>.gz</code> files in case the user executing the route had repository encryption enabled.<br/></p>
            <p><strong>Resolution:</strong> Now, such transfers execute successfully.
			</p>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>Patch 33<br/>00958217         </td>
         <td>RDST-13718         </td>
         <td>
            <p><strong>Issue:</strong> Previously, when downloading a large file from ST Web Client, the user was redirected to a timeout page after session timeout. <br/></p>
            <p><strong>Resolution:</strong> Now, a download polling mechanism is added to prevent the client-side session timeout. Download polling is configurable and is disabled by default. See the Readme.htm file with SecureTransport 5.3.6 Patch 33 for more info.
				<br/></p>
            <p><strong>Note:</strong> Download polling depends on transfers API.
				 The "<i>Allow this account to submit transfers using the Transfers RESTful API</i>" option must be enabled for the user.
			</p>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>Patch 33<br/>00907861         </td>
         <td>RDST-8360         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the PGP decryption was not triggered when the LDAP user was uploading PGP encrypted file in the basic application folder.<br/></p>
            <p><strong>Resolution:</strong> Now, the decryption is triggered and the file is decrypted successfully.</p>
         </td>
      </tr>
      <tr>
         <td>Patch 33<br/>00952168         </td>
         <td>RDST-14885         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the administrators did not have control over the network zones blacklisting functionality.<br/></p>
            <p><strong>Resolution:</strong> Now, a new configuration option <code>Proxy.Blacklisting.Enabled</code> is added which controls whether the blacklisting mechanism is enabled or disabled.</p>
         </td>
      </tr>
      <tr>
         <td>Patch 33<br/>00962139         </td>
         <td>RDST-14895         </td>
         <td>
            <p><strong>Issue:</strong> Previously, when the ST Web Client was requesting more AddressBook entries than defined in the <code>AddressBook.Limit.MaxDisplayEntries</code> configuration option, an error was thrown in the server log and no entries were returned.<br/></p>
            <p><strong>Resolution:</strong> Now this error is no longer thrown in the server log: instead a warning message is displayed. The value defined in the <code>AddressBook.Limit.MaxDisplayEntries</code> configuration option is now used for amount of entries which will be returned by SecureTransport, instead of being handled as a request value supplied by the user value which exceeds this.</p>
         </td>
      </tr>
      <tr>
         <td colspan="3">
            <p><strong>SecureTransport 5.3.6 Patch 32</strong>
</p>
         </td>
      </tr>
      <tr>
         <td>Patch 32<br/>00969436<br/>00969858         </td>
         <td>RDST-14591         </td>
         <td>
            <p><strong>Issue:</strong> Previously, there was a memory leak in the Transaction Manager when a new home folder or a sub-folder was created, including AdvanceRouting sandbox folder. 
				<br/></p>
            <p><strong>Resolution:</strong> Now, the memory leak is fixed in such cases.</p>
         </td>
      </tr>
      <tr>
         <td>Patch 32<br/>00954603         </td>
         <td>RDST-14589         </td>
         <td>
            <p><strong>Issue:</strong> Previously, <strong><code>AuditLog</code></strong> was slow when it had to process big collections of data.
				<br/></p>
            <p><strong>Resolution:</strong> Now, there is a new configuration option <code>AuditLog.Enabled.CollectionLog</code>. Change its value to false in order for the <strong><code>AuditLog</code></strong> to skip the Iterable objects for better performance. You can view the skipped objects in the <strong><code>AuditLog diff</code></strong>.<br/><br/><strong>Note:</strong> The default value is <code>true</code>.
			</p>
         </td>
      </tr>
      <tr>
         <td colspan="3">
            <p><strong>SecureTransport 5.3.6 Patch 31</strong>
</p>
         </td>
      </tr>
      <tr>
         <td>Patch 31<br/>00964509<br/>00962800         </td>
         <td>RDST-14582         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SecureTransport was vulnerable to CVE-2016-1000031 due to an old version of Apache Commons Fileupload being used.
							<br/></p>
            <p><strong>Resolution:</strong> Now, SecureTransport has upgraded to a non-vulnerable version of Apache Commons Fileupload. The new version is 1.3.3.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 31<br/>00963779         </td>
         <td>RDST-14131         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the Site templates drop-down wasn't alphabetically ordered.
				<br/></p>
            <p><strong>Resolution:</strong> Now, entries in the Site templates drop-down are alphabetically ordered.
			</p>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>Patch 31<br/>00967621         </td>
         <td>RDST-14138         </td>
         <td>
            <p><strong>Issue:</strong> Previously, whitespaces between <strong><code>Ssh.SIT.AllowedMacs</code></strong> and <strong><code>Ssh.AllowedMacs</code></strong> configuration options were not parsed correctly and only the first option value was used.
				<br/></p>
            <p><strong>Resolution:</strong> Now, whitespaces between <strong><code>Ssh.SIT.AllowedMacs</code></strong> and <strong><code>Ssh.AllowedMacs</code></strong> configuration options are parsed correctly and all values are being used regardless of the number of whitespaces between them.
			</p>
         </td>
      </tr>
      <tr>
         <td>Patch 31<br/>00956516         </td>
         <td>RDST-14584         </td>
         <td>
            <p><strong>Issue:</strong> Previously, <strong><code>Maximum file size allowed to archive</code></strong> text box option in File Archiving configuration did not accept empty value for size.<br/></p>
            <p><strong>Resolution:</strong> Now, <strong><code>Maximum file size allowed to archive</code></strong> text box option in File Archiving configuration accepts empty value for size.
			</p>
         </td>
      </tr>
      <tr>
         <td>Patch 31<br/>00946859         </td>
         <td>RDST-14580         </td>
         <td>
            <p><strong>Issue:</strong> Previously, there was no session timeout for SSH daemon.<br/></p>
            <p><strong>Resolution:</strong> Now, configuration option <code>Users.Session.idleTimeout</code> is used for defining maximum time of idle SSH session.
			</p>
         </td>
      </tr>
      <tr>
         <td>Patch 31<br/>00951158         </td>
         <td>RDST-14577         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SecureTransport was failing with multiple errors when multiple SSH channels were opened over one SSH connection.<br/></p>
            <p><strong>Resolution:</strong> Now, there are no errors thrown and files are being successfully uploaded over one SSH connection with multiple opened channels.
			</p>
         </td>
      </tr>
      <tr>
         <td>Patch 31<br/>00945676<br/>00836822         </td>
         <td>RDST-14128         </td>
         <td>
            <p><strong>Issue:</strong> Previously, an internal protocol address was exposed in some REST API end user resources responses.<br/></p>
            <p><strong>Resolution:</strong> Now, an internal protocol address is not exposed in some REST API end user resources responses.
			</p>
         </td>
      </tr>
      <tr>
         <td colspan="3">
            <p><strong>SecureTransport 5.3.6 Patch 30</strong>
</p>
         </td>
      </tr>
      <tr>
         <td>Patch 30<br/>00966425         </td>
         <td>RDST-14324         </td>
         <td>
            <p><strong>Issue:</strong> Previously, during SFTP logging the additional info message for authentication failure was logged.<br/></p>
            <p><strong>Resolution:</strong> Now, no such message in this case is logged.
			</p>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>Patch 30<br/>00967105         </td>
         <td>RDST-13964         </td>
         <td>
            <p><strong>Issue:</strong> Previously, when composing an adhoc message in the ST Web Client during an attachment upload, the <strong>Send</strong> button was active.<br/></p>
            <p><strong>Resolution:</strong> Now, the <strong>Send</strong> button is always inactive during attachments upload.
			</p>
         </td>
      </tr>
      <tr>
         <td>Patch 30<br/>00919197         </td>
         <td>RDST-14290         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SecureTransport was auditing all import activity.<br/></p>
            <p><strong>Resolution:</strong> Now, there is a new configuration option <code>AuditLog.Enabled.Import</code> that allows the SecureTransport administrator to control this behavior. The new option can have any of the following values: 
				<br/></p>
            <ul>
               <li><code>true</code> - the import itself should audit its work.               </li>
               <li><code>false</code> - the import is not audited, but all other activity is.               </li>
            </ul>
            <p><strong>Note:</strong> Once the import has started, the option cannot be changed before the import has finished. The default value is <code>false</code>. </p>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>Patch 30<br/>00943264<br/>00948677         </td>
         <td>RDST-14237         </td>
         <td>
            <p><strong>Issue:</strong> Previously, AS2D did not provide the complete certification chain.<br/></p>
            <p><strong>Resolution:</strong> Now, AS2D provides the complete certification chain.
			</p>
         </td>
      </tr>
      <tr>
         <td colspan="3">
            <p><strong>SecureTransport 5.3.6 Patch 29</strong>
</p>
         </td>
      </tr>
      <tr>
         <td>Patch 29<br/><i>none</i>         </td>
         <td>
            <p>RDST-13760</p>
         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the <code>compress/decompress</code> steps that uses GZIP algorithm were leaving the copies of the output files in <code>{FDH}/bin/</code> directory.
							<br/></p>
            <p><strong>Resolution:</strong> Now, the output of the both steps are in the target user's home folder.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 29<br/>00896828         </td>
         <td>RDST-14300         </td>
         <td>
            <p><strong>Issue:</strong> Previously, on some occasions the SecureTransport services were failed to start due to coherence errors.
							<br/></p>
            <p><strong>Resolution:</strong> Now, due to the Oracle recommendations, the coherence was updated to the latest version 3.7.1-16.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 29<br/>00953901         </td>
         <td>RDST-13876         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SecureTransport was sending a temporary (encrypted) PGP file in the <code>Send to Partner</code> step.
							<br/></p>
            <p><strong>Resolution:</strong> Now, SecureTransport sends the original encrypted PGP file in the <code>Send to Partner</code> step.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 29<br/>00923288         </td>
         <td>RDST-10117         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the description for the assigned route package template could not be changed to an empty string.
							<br/></p>
            <p><strong>Resolution:</strong> Now, the description for the assigned route package template can be changed to an empty string.
						</p>
         </td>
      </tr>
      <tr>
         <td colspan="3">
            <p><strong>SecureTransport 5.3.6 Patch 28</strong>
</p>
         </td>
      </tr>
      <tr>
         <td>Patch 28<br/>00947149<br/>00952168         </td>
         <td>RDST-14254         </td>
         <td>
            <p><strong>Issue:</strong> Previously, in case of Edge DNS resolution failure, SecureTransport was blacklisting the network zone.
				<br/></p>
            <p><strong>Resolution:</strong> Now, there is a new configuration option <code>Dmz.Edge.proxyDnsResolutionCheck</code>. When a connection fails, SecureTransport checks whether this failure is caused by DNS resolution failure. In such case the network zone does not get blacklisted.
				<br/></p>
            <p><strong>Note:</strong> In order to change the value of the new configuration option, you must restart the TM service. This option will take action only if <code>"Use the Edge DNS"</code> configuration is enabled in the Network zone configuration.
			</p>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>Patch 28<br/>00958643         </td>
         <td>RDST-13357         </td>
         <td>
            <p><strong>Issue:</strong> Previously, password policy was not displayed when user tried to reset password trough 'Forgot Your Password' and navigated to ST Web Client from the received password reset link.
				<br/></p>
            <p><strong>Resolution:</strong> Now, password policy is shown on the Password Reset page after following the password reset link.
			</p>
         </td>
      </tr>
      <tr>
         <td>Patch 28<br/>00933575         </td>
         <td>RDST-13261         </td>
         <td>
            <p><strong>Issue:</strong> Previously, sharing folders wasn't working in some cases when the provided e-mails contained capital letters.
				<br/></p>
            <p><strong>Resolution:</strong> Now, sharing folders functionality is working regardless of the letter case.
			</p>
         </td>
      </tr>
   </tbody>
</table>

#### <span id="Fixes5"></span>Fixes in SecureTransport 5.4

The following corrections and fixed issues have been addressed:

<table cellspacing="0">
   <colgroup>      
   <col/>
   <col/>
   <col/>
   </colgroup>
   <thead>
      <tr>
         <th>Case ID</th>
         <th>Internal ID</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td colspan="3"><strong>SecureTransport 5.4 Patch 35</strong>
         </td>
      </tr>
      <tr>
         <td>Patch 35<br/>00924916<br/>00870509         </td>
         <td>RDST-29156         </td>
         <td>
            <p><strong>Issue:</strong> Previously, unsuccessful server-initiated transfers over PeSIT were not retried and the SecureTransport File tracking was listing each such transfer as "failed" with the only option to cancel it.<br/></p>
            <p><strong>Resolution:</strong> Now, unsuccessful server-initiated transfers over PeSIT are processed correctly and the retry functionality functions as expected.</p>
         </td>
      </tr>
      <tr>
         <td>Patch 35<br/>01120127         </td>
         <td>RDST-29146         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the database maintenance operations were reported with wrong dates in the Server Log.<br/></p>
            <p><strong>Resolution:</strong> Now, the Maintenance applications report the correct dates of the performed database maintenance operations.</p>
         </td>
      </tr>
      <tr>
         <td>Patch 35<br/>01123463         </td>
         <td>RDST-29160         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the ICAP Scan Policy Expressions containing <code>flow.attributes</code> were not evaluated correctly.<br/></p>
            <p><strong>Resolution:</strong> Now, the ICAP Scan Policy Expressions are evaluated correctly.</p>
         </td>
      </tr>
      <tr>
         <td>Patch 35<br/>01109699<br/>01116498<br/>01098455         </td>
         <td>RDST-29141         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SecureTransport failed to report <code>DXAGENT_SITE_ATTR_DOWNLOAD_FOLDER</code> and <code>DXAGENT_FULLSOURCE</code> in the External Script step.<br/></p>
            <p><strong>Resolution:</strong> Now, SecureTransport exposes and reports both session variables.</p>
         </td>
      </tr>
      <tr>
         <td>Patch 35<br/>01108917<br/>01116244         </td>
         <td>RDST-29162<br/>RDST-29142         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the Decompress step was failing when the archive contained a file with the same name.<br/></p>
            <p><strong>Resolution:</strong> Now, new Collision settings are added to the Decompress step configuration.</p>
         </td>
      </tr>
      <tr>
         <td>Patch 35<br/>01106959<br/>01120021         </td>
         <td>RDST-29144         </td>
         <td>
            <p><strong>Issue:</strong> Previously, when the PASV command was disabled on the server, the transfers initiated by SecureTransport, were failing as it did not fall back to EPSV. 
				</p>
            <p><strong>Resolution:</strong> Now, when the PASV command is disabled on the server, SecureTransport falls back to EPSV.</p>
         </td>
      </tr>
      <tr>
         <td>Patch 35<br/>01096025         </td>
         <td>RDST-29159         </td>
         <td>
            <p><strong>Issue:</strong> Previously, sending an invalid request method resulted in a Server Error which made SecureTransport vulnerable to CWE-388.<br/></p>
            <p><strong>Resolution:</strong> Now, in the case described, a <code>400 Bad Request</code> error is returned and a message is logged in the Server Log.</p>
         </td>
      </tr>
      <tr>
         <td>Patch 35<br/>01094953         </td>
         <td>RDST-29140         </td>
         <td>
            <p><strong>Issue:</strong> Previously, when multiple rules were enabled in a Login Restriction Policy, the users assigned to the policy were logging on for a longer period of time.<br/></p>
            <p><strong>Resolution:</strong> Now, regardless of the authentication method and the Login Restriction Policy, login delay is not observed.</p>
         </td>
      </tr>
      <tr>
         <td>Patch 35<br/>01050910         </td>
         <td>RDST-29161         </td>
         <td>
            <p><strong>Issue:</strong> Previously, an acknowledgment for the transfer was sent twice in case of an Advanced Routing pull. <br/></p>
            <p><strong>Resolution:</strong> Now, in the case described, the transfer acknowledgment is sent once.</p>
         </td>
      </tr>
      <tr>
         <td>Patch 35<br/>01061542         </td>
         <td>RDST-29151         </td>
         <td>
            <p><strong>Issue:</strong> Previously, it was not possible to set the <code>X-Frame-Options</code> HTTP response header for the Administration Tool server.<br/></p>
            <p><strong>Resolution:</strong> Now, the header can be enabled and set via the newly added <code>Admin.Security.FrameOptions</code> server configuration option.</p>
         </td>
      </tr>
      <tr>
         <td>Patch 35<br/>01061529<br/>01085592         </td>
         <td>RDST-29153         </td>
         <td>
            <p><strong>Issue:</strong> Previously, it was not possible to set the <code>X-Content-type-options</code> header for the Administration Tool server.<br/></p>
            <p><strong>Resolution:</strong> Now, the header can be enabled and set via the newly added <code>Admin.Security.ContentTypeOptions</code> server configuration option.</p>
         </td>
      </tr>
      <tr>
         <td>Patch 35<br/>01061533         </td>
         <td>RDST-29154         </td>
         <td>
            <p><strong>Issue:</strong> Previously, it was not possible to set the <code>X-XSS-Protection</code> header for the Administration Tool server.<br/></p>
            <p><strong>Resolution:</strong> Now, the header can be enabled and set via the newly added <code>Admin.Security.XSSProtection</code> server configuration option.</p>
         </td>
      </tr>
      <tr>
         <td>Patch 35<br/>01060196         </td>
         <td>RDST-29158         </td>
         <td>
            <p><strong>Issue:</strong> Previously, responses to the <code>HTTP OPTIONS</code> requests was disclosing the library and its version.<br/></p>
            <p><strong>Resolution:</strong> Now, the responses to this method do not contain sensitive information.</p>
         </td>
      </tr>
      <tr>
         <td>Patch 35<br/>00998198<br/>01114087         </td>
         <td>RDST-29155         </td>
         <td>
            <p><strong>Issue:</strong> Previously, sending a file located in an Advanced Routing subscription folder using the REST API triggered the AR application as well.<br/></p>
            <p><strong>Resolution:</strong> Now, when an API call is used to trigger a push of a file located in an Advanced Routing subscription folder, the AR application is not triggered.</p>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>Patch 35<br/>01050997<br/>01127635         </td>
         <td>RDST-22883         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the Administration Tool was displaying subscriptions of an account assigned to a business unit ordered by creation date.<br/></p>
            <p><strong>Resolution:</strong> Now, the subscription list is sorted alphanumerically regardless if the account belongs to a business unit or not.</p>
         </td>
      </tr>
      <tr>
         <td colspan="3"><strong>SecureTransport 5.4 Patch 34</strong>
         </td>
      </tr>
      <tr>
         <td>Patch 34<br/>01125099         </td>
         <td>RDST-27957         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SecureTransport was performing validation for host and port on all flow deployments.<br/></p>
            <p><strong>Resolution:</strong> Now, this validation is removed from the Admin REST API v1.4 and is added with the future release of Admin REST API 2.0.</p>
         </td>
      </tr>
      <tr>
         <td>Patch 34<br/>01115829         </td>
         <td>RDST-27958         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the <code>collect_support_information</code> utility was failing to generate a heap dump, causing errors. <br/></p>
            <p><strong>Resolution:</strong> Now, the script is fixed and successfully generates a heap dump.</p>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>Patch 34<br/>none         </td>
         <td>RDST-27748         </td>
         <td>The "Maximum number of parallel transfers" code has been re-factored to address possible issues with server-initiated transfers not starting as expected.         </td>
      </tr>
      <tr>
         <td>Patch 34<br/>01079070<br/>01089139         </td>
         <td>RDST-27961            <p>RDST-26944</p>         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the <code>ssh.maxPendingConnections</code> configuration option was not working correctly.
							<br/></p>
            <p><strong>Resolution:</strong> Now, the configuration option sets the server socket backlog value. It is responsible for parallel connections that are not yet accepted by the application.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 34<br/>01117016         </td>
         <td>RDST-27956         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the list of certified software for file exchange, provided in the SecureTransport Administrator's Guide, was outdated.
							<br/></p>
            <p><strong>Resolution:</strong> Now, Axway SecureTransport Mobile 1.6.0 and SecureTransport Outlook add-in are removed from the list as they are no longer supported.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 34<br/>01117038         </td>
         <td>RDST-27955         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the <code>clientLocalCertificate</code> property was not documented in all relevant transfer site representations, located in the Model section of the SecureTransport REST API documentation.  
							<br/></p>
            <p><strong>Resolution:</strong> Now, the Model section of the SecureTransport REST API documentation is updated, and <code>clientLocalCertificate</code> element is described in the models of all transfer sites that allow certificate authentication or do sign/encrypt.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 34<br/>01083161<br/>01101670<br/>01088358<br/>01116826<br/>01123552<br/>01125666         </td>
         <td>RDST-27962         </td>
         <td>
            <p><strong>Issue:</strong> Previously, sessions closed on OS level were incorrectly shown on the <em>Server Usage Monitor</em> page even after the session timeout period had elapsed.
							<br/></p>
            <p><strong>Resolution:</strong> Now, the <em>Server Usage Monitor</em> shows only the active sessions.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 34<br/>01091741         </td>
         <td>RDST-27959         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the responses to <code>GET /certificates</code> requests sometimes contained duplicate IDs.
							<br/></p>
            <p><strong>Resolution:</strong> Now, <code>GET /certificates</code> returns the correct number and order of certificates.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 34<br/>01083411         </td>
         <td>RDST-27954         </td>
         <td>
            <p><strong>Issue:</strong> Previously, when transferring files over S3 with Sentinel reporting enabled, an error message related to the file attribute resolutions was shown in the Server Log, although the transfer was successful.
							<br/></p>
            <p><strong>Resolution:</strong> Now, the error message is no longer shown.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 34<br/>01083868         </td>
         <td>RDST-27960         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SecureTransport was failing to archive the file when PGP encryption was enabled via a Basic Application subscription with a post-transmission action set to <strong>delete on success</strong>.
							<br/></p>
            <p><strong>Resolution:</strong> Now, file archiving is successful regardless of the selected post-transmission action.
						</p>
         </td>
      </tr>
      <tr>
         <td colspan="3"><strong>SecureTransport 5.4 Patch 33</strong>
         </td>
      </tr>
      <tr>
         <td>Patch 33<br/>01035961         </td>
         <td>RDST-26231<br/>RDST-26236<br/>RDST-26237<br/>RDST-26235          </td>
         <td>
            <p><strong>Issue:</strong> Previously, verbose information was found to be returned within the responses to PUT and POST requests to the <strong>/fileops</strong> resource.
							<br/></p>
            <p><strong>Resolution:</strong> Now, responses to such requests contain generic messages.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 33<br/>01107889         </td>
         <td>RDST-26811         </td>
         <td>
            <p><strong>Issue:</strong> Previously, Repository Encryption was not working for files uploaded with WinSCP over SSH to a Basic subscription folder with Encrypt Mode set to "Enabled."
							<br/></p>
            <p><strong>Resolution:</strong> Now, in the specified scenario, the uploaded file is repository encrypted.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 33<br/>01118955         </td>
         <td>RDST-27105         </td>
         <td>
            <p><strong>Issue:</strong> Previously, patch installation was failing when Oracle system privileges were assigned through a role.
							<br/></p>
            <p><strong>Resolution:</strong> Now, patch installation is successful regardless of how Oracle system privileges are assigned.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 33<br/>01116997         </td>
         <td>RDST-26958         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SecureTransport administrators were unable to update the Network Zone in a PeSIT Transfer Site via the Administration Tool; the value of the Network Zone drop-down list was always "none" regardless of the user selection.
							<br/></p>
            <p><strong>Resolution:</strong> Now, the Network Zone can be updated successfully via the Administration Tool.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 33<br/>01110967         </td>
         <td>RDST-26941         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the Firewall rule list was numbered incorrectly in the SecureTransport 5.4 Administrator's Guide.
							<br/></p>
            <p><strong>Resolution:</strong> Now, the numbering of the Firewall rules is corrected.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 33<br/>01098969         </td>
         <td>RDST-26932         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the SecureTransport Administrator's Guide was providing incomplete instructions on how to perform graceful shutdown of a SecureTransport Edge node.
							<br/></p>
            <p><strong>Resolution:</strong> Now, the <em>Graceful shutdown</em> topic contains instructions on how to perform graceful shutdown of a SecureTransport Edge node.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 33<br/>01098969         </td>
         <td>RDST-26948         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the SecureTransport Administrator's Guide was providing incomplete instructions for executing Zero downtime.
							<br/></p>
            <p><strong>Resolution:</strong> Now, the <em>Zero downtime in active-passive deployment</em> topic offers the corrected instructions for Zero downtime execution steps.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 33<br/>01100301         </td>
         <td>RDST-26940         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the documentation on the firewall rules for Enterprise Cluster was incomplete.
							<br/></p>
            <p><strong>Resolution:</strong> Now, TCP port 7 is added as a requirement when configuring firewalls for cluster members.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 33<br/>01085132         </td>
         <td>
            <p>RDST-29143</p>
            <p>RDST-27072</p>
         </td>
         <td>To help prevent patch installation problems, the SecureTransport Installation Guide and the Readme file now contain a note explicitly stating that the SecureTransport installation directory and the Axway Installer components must never be in the same directory.
						         </td>
      </tr>
      <tr>
         <td>Patch 33<br/>01103337         </td>
         <td>RDST-26947         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the documentation for using SOCKS5 as a third-party proxy server was not clear.
							<br/></p>
            <p><strong>Resolution:</strong> Now, SecureTransport Administrator's Guide is corrected.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 33<br/>01101676         </td>
         <td>RDST-26939         </td>
         <td>
            <p><strong>Issue:</strong> Previously, several items in the <em>stwebclient.config.json</em> file were not documented in the ST Web Client Configuration Guide.
							<br/></p>
            <p><strong>Resolution:</strong> Now, the ST Web Client Configuration Guide is updated with the needed configuration items.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 33<br/>01086654         </td>
         <td>RDST-26945         </td>
         <td>
            <p><strong>Issue:</strong> Previously, files containing square brackets in their names couldn't be downloaded from ST Web Client because SecureTransport treated the square brackets as wildcard characters.
							<br/></p>
            <p><strong>Resolution:</strong> Now, SecureTransport first tries to find the file, and then considers file globbing.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 33<br/>01086283         </td>
         <td>RDST-26946         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the ST Web Client users, who were not logged in, couldn't download files via direct links because the URL suffix was stripped from the URL after login.
							<br/></p>
            <p><strong>Resolution:</strong> Now, the ST Web Client users are able to download files via direct links downloaded after they log in.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 33<br/>01082955<br/>01084043<br/>01085687<br/>01087225<br/>01092139<br/>01094915<br/>01106181<br/>01106558<br/>01107926<br/>01107999<br/>01109768<br/>01111756<br/>01117961         </td>
         <td>RDST-26936         </td>
         <td>
            <p><strong>Issue:</strong> Previously, when there were more than 100 accounts, SecureTransport administrators were unable to move forward and backward through <em>User Accounts</em> pages using the arrow buttons. 
							<br/></p>
            <p><strong>Resolution:</strong> Now, SecureTransport administrators can move forward and backward through <em>User Accounts</em> pages using the arrow buttons.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 33<br/>01083398<br/>01088995         </td>
         <td>RDST-27104         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the Standard Router application was failing to route files submitted by subscribed accounts when the service account's login to SecureTransport was disabled. In this case, the service account is not associated with a login name, which in turn is used by SecureTransport to find the service account.        
							<br/></p>
            <p><strong>Resolution:</strong> Now, SecureTransport searches by the account name of the service account rather than a login name, which might not exist.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 33<br/>01084278         </td>
         <td>RDST-26938         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the <strong>Actions</strong> drop-down lists on the Extended Server Control page were not expanding on Mozilla Firefox 68.0.1.
							<br/></p>
            <p><strong>Resolution:</strong> Now, the Action drop-down lists are working correctly on Mozilla Firefox 68.0.1.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 33<br/>01071201<br/>01084204         </td>
         <td>RDST-26937         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the resubmission of inbound AS2 transfers was failing when file archiving was enabled.
							<br/></p>
            <p><strong>Resolution:</strong> Now, the file archiving functionality is redesigned, and both outbound and inbound AS2 transfers are resubmitted successfully.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 33<br/>01060654<br/>01058784         </td>
         <td>RDST-26943         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the <strong>Server</strong> and <strong>User</strong> checkboxes were not displaying on the File Tracking page.
							<br/></p>
            <p><strong>Resolution:</strong> Now, both checkboxes are visible when Advanced Search is expanded.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 33<br/>00975445         </td>
         <td>RDST-27074         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SecureTransport was using Apache Groovy library, which was reported to be vulnerable to CVE-2016-6814 and CVE-2015-3253.
							<br/></p>
            <p><strong>Resolution:</strong> Now, SecureTransport does not use Apache Groovy anymore.
						</p>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>Patch 33<br/>01021231         </td>
         <td>RDST-20136         </td>
         <td>
            <p><strong>Issue:</strong> Previously, ST Web Client users used to receive an error message in JSON format after clicking an expired download link.
							<br/></p>
            <p><strong>Resolution:</strong> Now, ST Web Client handles the error properly and displays a clear message.
						</p>
         </td>
      </tr>
      <tr>
         <td colspan="3"><strong>SecureTransport 5.4 Patch 32</strong>
         </td>
      </tr>
      <tr>
         <td>Patch 32<br/>01034544         </td>
         <td>RDST-26918         </td>
         <td>
            <p><strong>Issue:</strong> Previously, after upgrading SecureTransport 5.3.6 to 5.4 and applying Patch 12 or Patch 14, the installer displayed the product version incorrectly as SecureTransport_V5.3.6.<br/></p>
            <p><strong>Resolution:</strong> Now, the installer displays the correct version of SecureTransport.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 32<br/>01055815 <br/>         </td>
         <td>RDST-26920<br/>         </td>
         <td>
            <p><strong>Issue:</strong> Previously, an outdated version of Java in the Axway Installer made SecureTransport prone to several security vulnerabilities. <br/></p>
            <p><strong>Resolution:</strong> Now, the Axway Installer Java version is updated to 1.8.0_541 for IBM AIX, and 1.8.0_231 for Windows, Linux, and Solaris.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 32<br/>01033262 <br/>01084510         </td>
         <td>RDST-26919<br/> RDST-23786<br/> RDST-23744          </td>
         <td>
            <p><strong>Issue:</strong> Previously, the MySQL component shipped with SecureTransport was presenting several security vulnerabilities, including CVE-2019-2534.<br/></p>
            <p><strong>Resolution:</strong> Now, the MySQL component version is updated to 5.6.44.
							</p>
            <p><strong>Note:</strong> This update does not apply to SecureTransport on AIX and SUSE 11. </p>
         </td>
      </tr>
      <tr>
         <td>Patch 32<br/>01112409         </td>
         <td>RDST-26921         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SecureTransport was using version 2.10.0 of Jackson-Databind which was reported to be vulnerable to deserialization of untrusted data: <br/>            <ul>               <li value="1">CVE-2019-17267               </li>               <li value="2">CVE-2019-16943               </li>               <li value="3">CVE-2019-16942               </li>               <li value="4">CVE-2019-16335               </li>               <li value="5">CVE-2019-14540               </li>            </ul></p>
            <p><strong>Resolution:</strong> Now, SecureTransport is using Jackson-Databind 2.10.1.</p>
         </td>
      </tr>
      <tr>
         <td colspan="3"><strong>SecureTransport 5.4 Patch 31</strong>
         </td>
      </tr>
      <tr>
         <td>Patch 31<br/>01102605         </td>
         <td>RDST-26341         </td>
         <td>
            <p><strong>Issue:</strong> Previously, after executing requests to the Admin REST API <strong>/transfers</strong> resource, threads were not released.
							<br/></p>
            <p><strong>Resolution:</strong> Now, once the REST API call is completed, the used threads are closed gradually.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 31<br/>01101146         </td>
         <td>RDST-26342         </td>
         <td>
            <p><strong>Issue:</strong> Previously, in an EC environment, the execution of an external script was failing when the script was executed over 8,000 times in one session.
							<br/></p>
            <p><strong>Resolution:</strong> Now, an external script can be executed over 8,000 times in one session successfully.
						</p>
         </td>
      </tr>
      <tr>
         <td colspan="3"><strong>SecureTransport 5.4 Patch 30</strong>
         </td>
      </tr>
      <tr>
         <td>Patch 30<br/>01104837<br/>01105823<br/>01104674<br/>         </td>
         <td>RDST-25770         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SecureTransport was failing to establish a connection to OpenSSH_7.4p1 servers.
							<br/></p>
            <p><strong>Resolution:</strong> Now, the connections to OpenSSH servers are successful.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 30<br/>01102605         </td>
         <td>RDST- 25773         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the threads of the Admin service were not released after the API call was completed.
							<br/></p>
            <p><strong>Resolution:</strong> Now, once the REST API call is completed, the used threads are closed gradually.
						</p>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>Patch 30<br/>01095972         </td>
         <td>RDST-25779         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the documentation on command line client login to SecureTransport was out-of-date.
							<br/></p>
            <p><strong>Resolution:</strong> Now, the SecureTransport Administrator's Guide is updated.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 30<br/>01097884          </td>
         <td>RDST-25768         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the upgrade from Patch 24 was failing when SecureTransport was using an Oracle database which password contained an exclamation mark.
							<br/></p>
            <p><strong>Resolution:</strong> Now, the Oracle database password is escaped in the JDBC URL used during the upgrade procedure.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 30<br/>01092203         </td>
         <td>RDST-25742         </td>
         <td>
            <p><strong>Issue:</strong> Previously, when the <strong>Delete on Success</strong> option in the Post Routing Settings of an Advanced Routing subscription was enabled, SecureTransport did not always delete the source file.
							<br/></p>
            <p><strong>Resolution:</strong> Now, given <strong>Delete on Success</strong> is selected, the source file is always deleted upon success.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 30<br/>01093876         </td>
         <td>RDST-25744         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the <code>start_all</code> script was failing to start the PeSIT over Secured Socket (Legacy &amp; Comp) listener if it was the only PeSIT listener enabled.
							<br/></p>
            <p><strong>Resolution:</strong> Now, all enabled PeSIT listeners are started by executing the <code>start_all</code> command.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 30<br/>01088083         </td>
         <td>RDST-25763         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the outbound AdHoc transfers via System to Human transfer sites were failing when ICAP was enabled.
							<br/></p>
            <p><strong>Resolution:</strong> Now, when ICAP is enabled, the AdHoc transfers via System to Human transfer sites are successful.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 30<br/>01088520         </td>
         <td>RDST-25764         </td>
         <td>
            <p><strong>Issue:</strong> Previously, when a file was renamed using an internal transfer site, Advanced Routing Publish To Account or Send to Partner step, SecureTransport used to report to Sentinel the original file name instead of the new one.
							<br/></p>
            <p><strong>Resolution:</strong> Now, after a file is renamed, SecureTransport reports the new file name to Sentinel via the <code>ProtocolFileName</code> attribute.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 30<br/>01089043         </td>
         <td>RDST-25767         </td>
         <td>
            <p><strong>Issue:</strong> Previously, administrators could initiate transfers during Transaction Manager graceful shutdown through the REST API.
							<br/></p>
            <p><strong>Resolution:</strong> Now, if the Transaction Manager is in the process of graceful shutdown, all requests to the Admin REST API <strong>/transfers</strong> resource are rejected.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 30<br/>01079219         </td>
         <td>RDST-25915         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the SecureTransport Administrator's Guide was providing incomplete instructions for setting up AS2 transfers with asynchronous MDN receipts and an Advanced Routing subscription.
							<br/></p>
            <p><strong>Resolution:</strong> Now, the SecureTransport Administrator's Guide is updated to provide detailed instructions for setting up AS2 transfers with asynchronous MDN receipts and an Advanced Routing subscription.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 30<br/>01086367         </td>
         <td>RDST-23952         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the prerequisites for installing SecureTransport on CentOS were incomplete.
							<br/></p>
            <p><strong>Resolution:</strong> Now, the SecureTransport Installation Guide and SecureTransport  on AWS Installation Guide provide the requirements for installing SecureTransport on CentOS. 
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 30<br/>01071454<br/>01063234         </td>
         <td>RDST-25774         </td>
         <td>
            <p><strong>Issue:</strong> Previously, certain <code>DXAGENT</code> variables were not exposed as session variables and, therefore, couldn't be used in the Advanced Routing External Script step.  
							<br/></p>
            <p><strong>Resolution:</strong> Now, the following <code>DXAGENT</code> environment variables are exposed as session variables, and can be used in the Advanced Routing External Script step: 
							<br/><code>DXAGENT_TYPE, DXAGENT_TIMESTAMP_OUTGOING_END, DXAGENT_LOGFILENAME, DXAGENT_EDGEID, DXAGENT_SUBSCRIPTION_FOLDER, DXAGENT_APPLICATION_TYPE, DXAGENT_APPLICATION_NAME, DXAGENT_APPLICATION_NOTES, DXAGENT_SITE_ATTR_UPLOAD_FOLDER, DXAGENT_SITE_ATTR_USERNAME, DXAGENT_SITE_ATTR_HOST.</code></p>
         </td>
      </tr>
      <tr>
         <td>Patch 30<br/>01074729         </td>
         <td>RDST-25777         </td>
         <td>
            <p><strong>Issue:</strong> Previously, when the Send To Partner route step option <strong>Send trigger file for each transferred file</strong> was enabled, the subsequent route 
							steps were executed without payload.
							<br/></p>
            <p><strong>Resolution:</strong> Now, the Advanced Routing steps after the Send To Partner one are executed with payload.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 30<br/>01079065         </td>
         <td>RDST-25760         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the documentation on authentication plug-ins was missing instructions on how to update an authentication plug-in.
							<br/></p>
            <p><strong>Resolution:</strong> Now, the SecureTransport Administrator's Guide provides instructions on updating both authentication and authorization plug-ins.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 30<br/>01070385         </td>
         <td>RDST-25761         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the information in the Administrator's Guide on using flow attributes in Advanced Routing was misleading users into thinking that flow attributes can be evaluated in all fields in Advanced Routing, which is valid only if the application is operating with files.
							<br/></p>
            <p><strong>Resolution:</strong> Now, to evaluate expressions regardless of file availability, subscription attributes are exposed and can be used in Advanced Routing.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 30<br/>01057102<br/>01097717         </td>
         <td>RDST-25762         </td>
         <td>
            <p><strong>Issue:</strong> Previously, on Windows with shared storage, the Advanced Routing Send to Partner step failed to send files to transfer sites.
							<br/></p>
            <p><strong>Resolution:</strong> Now, on Windows with shared storage, the Advanced Routing Send to Partner step successfully sends files to transfer sites.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 30<br/>01015372          </td>
         <td>RDST-25765         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the <code>Pesit.Client.Inactivity.Timeout</code> configuration option, which defines the client inactivity timeout, was applicable for all PeSIT server-initiated transfers.
							<br/></p>
            <p><strong>Resolution:</strong> Now, the client inactivity timeout can be configured per PeSIT transfer site.
						</p>
         </td>
      </tr>
      <tr>
         <td colspan="3"><strong>SecureTransport 5.4 Patch 29</strong>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>Patch 29<br/>00965624         </td>
         <td>RDST-24623         </td>
         <td>
            <p><strong>Issue:</strong> Previously, when the Admin daemon on SecureTransport Server was trying to get some properties from an Edge server over streaming protocol, but an error occurred meanwhile in the process, the hostname of that Edge server was not logged.<br/></p>
            <p><strong>Resolution:</strong> Now, the hostname of the Edge server is logged when error occurs. 
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 29<br/>01081811         </td>
         <td>RDST-25222         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the documentation on using advanced expressions for subscription flow attributes in the SecureTransport Administrator's Guide was incomplete.<br/></p>
            <p><strong>Resolution:</strong> Now, the Pluggable Transfer Sites topic in the SecureTransport Administrator's Guide is updated.
							</p>
         </td>
      </tr>
      <tr>
         <td>Patch 29<br/>01067848         </td>
         <td>RDST-24422         </td>
         <td>
            <p><strong>Issue:</strong> Previously, as part of the subscription initialization, the user classes were evaluated per account subscription which resulted in slow login times for accounts with a large number of subscriptions.<br/></p>
            <p><strong>Resolution:</strong> Now, the user classes are evaluated once per login, and the number of subscriptions does not affect login time significantly.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 29<br/>01088333         </td>
         <td>RDST-25246         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the Advanced Routing Decompress step failed to unzip archives containing comments.<br/></p>
            <p><strong>Resolution:</strong> Now, the Advanced Routing Decompress step successfully executes and unzips archives with comments.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 29<br/>01081965         </td>
         <td>RDST-25224         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the description of the Login Threshold Maintenance application in the SecureTransport Administrator's Guide was confusing. <br/></p>
            <p><strong>Resolution:</strong> Now, the Applications topic provides a clear overview of the Login Threshold Maintenance application.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 29<br/>01074332         </td>
         <td>RDST-25238         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the server log message for failed connections from the Transaction Manager to a SecureTransport Edge server in a network zone, was misleading administrators into thinking that the Edge was blacklisted.<br/></p>
            <p><strong>Resolution:</strong> Now, in the specified scenario, the server log message also shows the current state (failed or denied) of the SecureTransport Edge server to which the Transaction Manager failed to connect.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 29<br/>01064759         </td>
         <td>RDST-25237         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the server-initiated pushes to Folder Monitor transfer sites were failing when an account template was used.<br/></p>
            <p><strong>Resolution:</strong> Now, the server-initiated pushes to Folder Monitor transfer sites through account templates are performed successfully.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 29<br/>01062611         </td>
         <td>RDST-25221         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the Unlicensed Accounts Maintenance application failed to delete the unlicensed accounts that had been inactive for the specified period.
							<br/></p>
            <p><strong>Resolution:</strong> Now, the application deletes from the database the unlicensed accounts after they are inactive for the specified number of days.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 29<br/>01063259         </td>
         <td>RDST-25223         </td>
         <td>
            <p><strong>Issue:</strong> Previously, when logging was redirected to a flat file, some variables that are typically reported in the server log were not exposed and therefore, not reported in the flat file.<br/></p>
            <p><strong>Resolution:</strong> Now, <code>ServerName</code> is exposed for all protocol daemons, and <code>sessionId</code> is exposed for the SSH daemon. Both variables can be configured in the layout element of the log4j file of a given protocol daemon.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 29<br/>01038798         </td>
         <td>RDST-25227         </td>
         <td>
            <p><strong>Issue:</strong> Previously, dynamic synchronization on Standard Cluster was failing to update the RecentPassword table across other nodes after changing an admin password that had been manually expired. As a result, there were differences in the nodes’ xml files of exported accounts.<br/></p>
            <p><strong>Resolution:</strong> Now, the table is successfully synchronized across the nodes upon password change.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 29<br/>01037120         </td>
         <td>RDST-25225         </td>
         <td>
            <p><strong>Issue:</strong> Previously, a SecureTransport administrator was unable to apply unique security settings for the SSH listeners.<br/></p>
            <p><strong>Resolution:</strong> Now, the security settings are part of StSSHContext, and the administrator can configure unique settings for each SSH listener.
						</p>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>Patch 29<br/>01070697         </td>
         <td>RDST-24478         </td>
         <td>
            <p><strong>Issue:</strong> Previously, master administrators without permissions to the Certificates page were not able to view the local certificates when creating or updating a transfer site.<br/></p>
            <p><strong>Resolution:</strong> Now, master administrators without permissions to the Certificates page can view and use the local certificates through the REST API as well as in the Administration Tool when creating or updating a transfer site.
						</p>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>Patch 29<br/>01084566         </td>
         <td>RDST-24160         </td>
         <td>
            <p><strong>Issue:</strong> Previously, when the <code>AuditLog.Enabled.CollectionLog</code> configuration option was set to <code>false</code>, SecureTransport displayed an error in the server log on unchecking the <strong>Allow this account to login to SecureTransport Server</strong> checkbox.<br/></p>
            <p><strong>Resolution:</strong> Now, when <code>AuditLog.Enabled.CollectionLog</code> set to <code>false</code>, only an information message for disallowing an account to log into SecureTransport is displayed in the server log.
						</p>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>Patch 29<br/>01081029         </td>
         <td>RDST-24157         </td>
         <td>Following the latest security best practices, the storing mechanism for sensitive data in SecureTransport is further enhanced to withstand attacks.
						         </td>
      </tr>
      <tr>
         <td colspan="3"><strong>SecureTransport 5.4 Patch 28</strong>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>Patch 28<br/>01039650         </td>
         <td>RDST-23620         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the SecureTransport Installation Guide was providing incomplete instructions for setting up Oracle database correctly.
							<br/></p>
            <p><strong>Resolution:</strong> Now, the SecureTransport Installation Guide is updated with the correct instructions to set an Oracle database.
						</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Patch 28<br/>01058200</p>
            <p>01054469</p>
         </td>
         <td>
            <p>RDST-23619 </p>
            <p>RDST-24060</p>
         </td>
         <td>
            <p><strong>Issue:</strong> Previously, failed to transfer files were deleted from the Connect:Direct temporary folder only on Transaction Manager start. <br/></p>
            <p><strong>Resolution:</strong> Now, a new configuration option <code>ExternalServerTransferAgent.temporaryDirectoryPurge</code> is introduced that allows administrators to control the deletion of files from the temporary folder. <br/>Possible values:
							</p>
            <ul>
               <li><code>false </code>(default) - the temporary folder is cleared on Transaction Manager start.               </li>
               <li><code>true</code> - the temporary folder is cleared when a server-initiated push over Connect:Direct fails.               </li>
            </ul>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>Patch 28<br/>01066092         </td>
         <td>RDST-23616         </td>
         <td>
            <p><strong>Issue:</strong> Previously, when the <code>com.maverick.sshd.events</code> logger was set to <code>debug</code>, the message body was formatted incorrectly and included newline characters. As a result, log messages couldn't be parsed into useful information. <br/></p>
            <p><strong>Resolution:</strong> Now, the logger presents all content of the message on a single line following the SecureTransport logs convention. All events can be matched and parsed correctly.
						</p>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>Patch 28<br/>01073380         </td>
         <td>RDST-23615         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the REST API allowed configuring the root directory (<code>/</code>) as a base folder and thus setting a user home folder under <code>/</code> which could pose risks especially on root installations. <br/></p>
            <p><strong>Resolution:</strong> Now, SecureTransport checks if the absolute home folder path supplied via the REST API is a concatenation of a valid base folder path (other than <code>/</code> (root)) and the home folder path.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 28<br/>01074891<br/>00916035         </td>
         <td>
            <p>RDST-24566</p>
            <p>RDST-24583</p>
            <p>RDST-29157</p>
         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the server log messages for successful and failed certificate authentication did not provide enough details about the certificate in use.		
							<br/></p>
            <p><strong>Resolution:</strong> Now, each time a user attempts to log in using a certificate via the following protocols: HTTPS, FTPS, SSH and PeSIT, a message is created in the server log containing the following information:
							</p>
            <ul>
               <li>The user who logged in/attempted to log in using a certificate               </li>
               <li>The certificate serial number               </li>
               <li>The certificate owner(s)                </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>Patch 28<br/>01071262<br/>01077488<br/>01076124<br/>01084043         </td>
         <td>RDST-24582         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the Transfer Log Maintenance application failed to clean up the transfer log entries from MySQL databases containing large amounts of data.
							<br/></p>
            <p><strong>Resolution:</strong> Now, the Transfer Log Maintenance application successfully cleans up the transfer log entries regardless of the MySQL database size.
							<br/></p>
            <p><strong>Note</strong>: Axway recommends using equal values for <code>Delete transfer log when*:</code> and <code>Delete in-progress transfers that started more than*:</code> on instances running with MySQL database. Otherwise, the necessary database queries might become time-consuming and even result in failure to execute the maintenance application on tables with a lot of data.
								<br/><strong>Note</strong>: On very highly utilized systems, the Transfer Log export might become slower and, in some cases, fail to complete. To keep the application running, consider using smaller values for the <code>Number of records per file:</code> option.
							</p>
         </td>
      </tr>
      <tr>
         <td>Patch 28<br/>01081923         </td>
         <td>RDST-24574         </td>
         <td>
            <p><strong>Issue:</strong> Previously, there was an error in the example of how to calculate the JAVA_MEM_MAX value, which is used to set the maximum heap size for the Java Virtual Machine(JVM).
							<br/></p>
            <p><strong>Resolution:</strong> Now, the instructions on configuring the SSH server settings are updated with the correct example calculation.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 28<br/>01071068         </td>
         <td>RDST-24562         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the login restriction policies for SSO-authenticated users were not working correctly; at times, users could not log in or experienced a logon delay.
							<br/></p>
            <p><strong>Resolution:</strong> Now, the login restriction policies are working correctly for SSO-authenticated users.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 28<br/>01061518         </td>
         <td>RDST-24565         </td>
         <td>
            <p><strong>Issue:</strong> Previously, it was possible to configure the Content-Security-Policy header only for the HTTP daemon.<br/></p>
            <p><strong>Resolution:</strong> Now, a new configuration option <code>Admin.Security.ContentSecurityPolicy</code> is introduced to allow configuring the Content-Security-Policy header for the Admin daemon.<br/></p>
            <p><strong>Note</strong>: For the Administration Tool to function correctly, you should specify the following directives as a minimum: <code>default-src 'self'; style-src 'self' 'unsafe-inline'; script-src 'self' 'unsafe-eval' 'unsafe-inline';</code>. Any deviations from the suggested values might result in unexpected behavior of SecureTransport Admin UI.</p>
         </td>
      </tr>
      <tr>
         <td>Patch 28<br/>01049419         </td>
         <td>RDST-24581         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the extended <em>Server Control</em> page was showing Folder Monitor and Scheduler as "Running" when they were disabled from the Server Configuration and therefore not performing any actions.
					</p>
            <p><strong>Resolution:</strong> Now, when <code>FolderMonitor.enable</code>/<code>Scheduler.enable</code> configuration option is set to <code>false</code>, the respective service is shown as "Disabled" on the <em>Server Control</em> page.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 28<br/>01060780         </td>
         <td>RDST-24577         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the documentation for the Core ID parameter in SecureTransport Administrator's Guide was incomplete.
							<br/></p>
            <p><strong>Resolution:</strong> Now, the SecureTransport Administrator's Guide is updated with detail descriptions of the Session ID, Transfer ID, and Core ID parameters.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 28<br/>01060187         </td>
         <td>RDST-24564         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the swagger-ui component contained an outdated version of the <em>remarkable</em> library which was vulnerable to Denial of Service (DoS) attacks.
							<br/></p>
            <p><strong>Resolution:</strong> Now, the <em>remarkable</em> library is upgraded to its latest version (2.0.0) which does not contain the flaw.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 28<br/>01060185         </td>
         <td>RDST-24571         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SecureTransport was vulnerable to CWE-116.
							<br/></p>
            <p><strong>Resolution:</strong> Now, when using the TransferMode parameter under <strong>/files</strong> endpoints, the error message contains properly escaped JavaScript based on the Content Type of the request.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 28<br/>01056323         </td>
         <td>RDST-24567         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the <code>resubmitted</code> parameter was missing from the responses to GET requests to <strong>/transfers</strong>.
						<br/></p>
            <p><strong>Resolution:</strong> Now, the response to GET requests to <strong>/transfers</strong> contains the <code>resubmitted</code> parameter.</p>
         </td>
      </tr>
      <tr>
         <td>Patch 28<br/>01054971         </td>
         <td>RDST-24575         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SecureTransport occasionally displayed an error for inserting a duplicate entry when persisting the server log in a database.
							<br/></p>
            <p><strong>Resolution:</strong> Now, the persistence mechanism is improved, and the error is no longer displayed.
						</p>
         </td>
      </tr>
      <tr>
         <td colspan="3"><strong>SecureTransport 5.4 Patch 27</strong>
         </td>
      </tr>
      <tr>
         <td>Patch 27<br/>01043389<br/>01082236<br/>01074579         </td>
         <td>RDST-24000         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the last login time and the number of successful and failed login attempts, displayed in the user account settings, were not updating for LDAP accounts mapped to virtual users with externally stored passwords.<br/></p>
            <p><strong>Resolution:</strong> Now, those attributes show the correct information for LDAP accounts mapped to virtual users with externally stored passwords.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 27<br/>01032979         </td>
         <td>RDST-23996         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the status of an administrator account with an expired password was not visualized correctly on the Administrators page. On attempt to use the REST API with an expired admin password, the response code contained only a "401 Authentication required" error without details that can help in identifying the problem.
							<br/></p>
            <p><strong>Resolution:</strong> Now, in the specified case, the account status is displayed correctly on the Administrators page, and the API response contains a password expiration message.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 27<br/>01060192         </td>
         <td>RDST-23998         </td>
         <td>
            <p><strong>Issue:</strong> Previously, when sending a request containing invalid data to the end-user REST API, the response included technical details about the application.<br/></p>
            <p><strong>Resolution:</strong> Now, the application provides only a generic error and returns a 400 Bad Request response code. The stack trace that holds the sensitive technical information is redirected to the Server Log.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 27<br/>01059356<br/>01054469         </td>
         <td>RDST-22128         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the SecureTransport Administration Tool and ST Web Client were vulnerable to CVE-2019-11358 due to an outdated version of jQuery (3.3.1).
							<br/></p>
            <p><strong>Resolution:</strong> Now, jQuery is updated to version 3.4.1 which contains the latest security fixes.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 27<br/>01062788         </td>
         <td>RDST-23999         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SecureTransport was failing to evaluate a path from a Windows server to a Unix or Unix-like server defined in a transfer site using expression language.
							<br/></p>
            <p><strong>Resolution:</strong> Now, SecureTransport evaluates the path correctly.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 27<br/>01071935         </td>
         <td>RDST-24001         </td>
         <td>
            <p><strong>Issue:</strong> Previously, on the extended view of the Server Control page, the Key Alias field could not display the full key alias name if it was longer than 20 characters.
						<br/></p>
            <p><strong>Resolution:</strong> Now, if the key alias name is longer than 20 characters, it is shown truncated with an ellipsis, and the full name is displayed on mouseover.</p>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>Patch 27<br/>01022572         </td>
         <td>RDST-19454         </td>
         <td>
            <p><strong>Issue:</strong> Previously, with Repository encryption enabled, there was a delay in initiating large file downloads due to the whole file being read. <br/></p>
            <p><strong>Resolution:</strong> Now, the download is initiated immediately as the file is not read anymore.
						</p>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>Patch 27<br/>01044707<br/>01073403         </td>
         <td>RDST-22222         </td>
         <td>
            <p><strong>Issue:</strong> Previously, when Repository encryption was enabled, there was an exponential upload speed degradation due to the whole file being read at the beginning of every chunk upload.
							<br/></p>
            <p><strong>Resolution:</strong> Now, there is no upload speed degradation, and only the first chunk of the file is read.
						</p>
         </td>
      </tr>
      <tr>
         <td colspan="3"><strong>SecureTransport 5.4 Patch 26</strong>
         </td>
      </tr>
      <tr>
         <td>Patch 26<br/>01055835<br/>01070003         </td>
         <td>RDST-23976         </td>
         <td>
            <p><strong>Issue:</strong> Previously, when user was logged in through HTTPD on SecureTransport Edge, an error was displayed in the Server log about missing <code>ShowHiddenFiles</code> configuration option.
							<br/></p>
            <p><strong>Resolution:</strong> Now, the <code>ShowHiddenFiles</code> configuration option is added to SecureTransport Edge.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 26<br/>01071692<br/>01071170         </td>
         <td>RDST-23961         </td>
         <td>
            <p><strong>Issue:</strong> Previously, after kernel upgrade from 3.10.0-957.5.1.el7.x86_64 to 3.10.0-957.21.3.el7.x86_64, users were no longer able to establish FTPS connections to the server because the SSL handshake could not be completed.
							<br/></p>
            <p><strong>Resolution:</strong> Now, FTPS connections are established and the SSL handshake is completed successfully.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 26<br/>01052165         </td>
         <td>RDST-23967         </td>
         <td>
            <p><strong>Issue:</strong> Previously, when a custom transfer site was used as a source for an Advanced Routing flow with the <b>First Matching Route rule</b> set, SecureTransport did not execute the routes correctly in certain scenarios. <br/></p>
            <p><strong>Resolution:</strong> Now, SecureTransport executes the routes correctly in all scenarios under the conditions described.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 26<br/>01038731         </td>
         <td>RDST-23971         </td>
         <td>
            <p><strong>Issue:</strong> Previously, <code>status_pesitd</code> and <code>status_as2d</code> scripts were always returning status <b>Disabled</b> for the corresponding protocol servers. <br/></p>
            <p><strong>Resolution:</strong> Now, SecureTransport returns the correct statuses on executing these scripts.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 26<br/>01055198         </td>
         <td>RDST-23964         </td>
         <td>
            <p><strong>Issue:</strong> Previously, resubmitting file transfers based on the <code>cycleId</code> attribute via the REST API <code>/transfers/resubmit </code> resource was unsuccessful.
							<br/></p>
            <p><strong>Resolution:</strong> Now, such resubmits are successful.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 26<br/>01046287         </td>
         <td>RDST-23977         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SecureTransport was not reporting the RETURNMESSAGE value to Axway Sentinel in case of failed transfers.
							<br/></p>
            <p><strong>Resolution:</strong> Now, the RETURNMESSAGE value is properly reported to Axway Sentinel in case of failed transfers.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 26<br/>01026928         </td>
         <td>RDST-23968         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the HTTP Strict-Transport-Security (HSTS) header was missing in responses to some <code>login.jspx</code> requests when using HSTS in the Admin component.
							<br/></p>
            <p><strong>Resolution:</strong> Now, the security headers are present in these responses.</p>
         </td>
      </tr>
      <tr>
         <td>Patch 26<br/>01069466<br/>01065639         </td>
         <td>RDST-23975         </td>
         <td>
            <p><strong>Issue:</strong> Previously, establishing a test connection to a Microsoft SQL Server database was failing because special characters in the password were escaped in the JDBC URL, leading to authentication errors.
							<br/></p>
            <p><strong>Resolution:</strong> Now, establishing a test connection to a Microsoft SQL Server database occurs successfully.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 26<br/>01021461<br/>01062008         </td>
         <td>RDST-23972         </td>
         <td>
            <p><strong>Issue:</strong> Previously, an incorrect flag was reported to Sentinel when a file transfer was denied by the ICAP server.
							<br/></p>
            <p><strong>Resolution:</strong> Now, when a file transfer is denied by the ICAP server, an Alert flag is reported to Sentinel.
						</p>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>Patch 26<br/>01034470         </td>
         <td>RDST-20418         </td>
         <td>
            <p><strong>Issue:</strong> Previously, it was not possible to use the <code>substring</code> function in the account temple fields.
							<br/></p>
            <p><strong>Resolution:</strong> Now, <code>substring</code> is added to the expression language functions and can be used in the account template fields. <br/></p>
            <ul>
               <li>Syntax: <code>${substring(variable, beginIndex,endIndex)}</code>.  <br/>               </li>
               <li>Example: <code>/${substring(stenv.loginname,0,1)}</code>.
						               </li>
            </ul>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>Patch 26<br/>01029676         </td>
         <td>RDST-19425         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the <code>/file</code> resource in the end user API was not working with file globbing. <br/></p>
            <p><strong>Resolution:</strong> Now, the <code>/file</code> resource in the end user API works properly with file paths containing GLOB characters.
						</p>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>Patch 26<br/>00949613<br/>01039198         </td>
         <td>RDST-21848         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SecureTransport did not limit the number of the simultaneous connections to the remote server when pulling files using the <b>Maximum number of parallel transfers</b> value as configured in the subscription.
							<br/></p>
            <p><strong>Resolution:</strong> Now, SecureTransport limits the simultaneous connections to the number specified in the <b>Maximum number of parallel transfers</b> value as configured in the subscription.
						</p>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>Patch 26<br/>01027570         </td>
         <td>RDST-21470         </td>
         <td>
            <p><strong>Issue:</strong> Previously, deleting subscriptions with a configured schedule was preventing users from logging in and uploading files. <br/></p>
            <p><strong>Resolution:</strong> Now, the deletion of subscriptions with configured schedules does not affect user login or file upload.
						</p>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>Patch 26<br/>01032957         </td>
         <td>RDST-21490         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the documentation for the <code>/certificates/export</code> resource in Swagger was incomplete.
							<br/></p>
            <p><strong>Resolution:</strong> Now, the documentation for the <code>/certificates/export</code> resource in Swagger is updated.
						</p>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>Patch 26<br/>01037795         </td>
         <td>RDST-21491         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the logger <code>com.tumbleweed.st.server.sshd.logging</code> was missing information that helps identifying the users who triggered Maverick events. <br/></p>
            <p><strong>Resolution:</strong> Now, the logger provides information about the <code>accountId</code>, <code>remoteAddress</code> and <code>sessionId</code>.
						</p>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>Patch 26<br/>00997187         </td>
         <td>RDST-21492<br/>RDST-21493         </td>
         <td>
            <p><strong>Issue:</strong> Previously, when pushing files via Connect:Direct or Multipoint Binary File Transfer, temporary folders were created with hardcoded permissions(drwxr-xr-x), making pulls impossible in certain occasions.
							<br/></p>
            <p><strong>Resolution:</strong> Now, administrators can set suitable temporary directory permissions for Connect:Direct and Multipoint Binary File transfers using the <code>ExternalServerTransferAgent.temporaryDirectoryPermissions </code> configuration option.
						</p>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>Patch 26<br/>01032957         </td>
         <td>RDST-21494         </td>
         <td>
            <p><strong>Issue:</strong> Previously, POST requests of an XML formatted Certificate object to <code>/certificates/export</code> in REST API v1.4 failed with response code 400(Bad Request).
							<br/></p>
            <p><strong>Resolution:</strong> Now, POST requests of XML formatted Certificates to <code>/certificates/export</code> are successful.
						</p>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>Patch 26<br/>01037290         </td>
         <td>RDST-21489         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SecureTransport was not evaluating properly the <code>User ID</code> and <code>Group ID</code> attributes for the user class custom expressions which resulted in users being assigned to an incorrect user class.
							<br/></p>
            <p><strong>Resolution:</strong> Now, UID and GID are populated in the environment as <code>DXAGENT_USERUID</code> and <code>DXAGENT_USERGID</code> respectively, and SecureTransport determines the proper user class for a user.
						</p>
         </td>
      </tr>
      <tr>
         <td colspan="3"><strong>SecureTransport 5.4 Patch 25</strong>
         </td>
      </tr>
      <tr>
         <td>Patch 25<br/>01036738<br/>         </td>
         <td>RDST-23125<br/>         </td>
         <td>
            <p><strong>Issue:</strong> Previously, on EC setup using Oracle database with two active servers, resubmitting transfers failed with “Error during transfer operation" due to the transfer being processed by one of the servers and the sandbox environment was created on the other one.<br/></p>
            <p><strong>Resolution:</strong> Now, a new logic for processing outgoing events that were triggered on resubmitting is implemented: the cluster node, which triggers the file resubmission, processes the outgoing event. In this case, the local sandbox folder contains the archived file, and the latter can be restored successfully.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 25<br/>01057760         </td>
         <td>RDST-23119         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the COREID parameter was ignored in the GET requests to the <code>/transfers</code> endpoint in the end user API. As a result, instead of the transfer with the specified COREID, a list of all transfers was returned.<br/></p>
            <p><strong>Resolution:</strong> Now, a GET request to the <code>/transfers</code> endpoint in the end user API returns only the transfer with the specified COREID.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 25<br/>01046608         </td>
         <td>RDST-23124         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the exchange of AS2 messages between two SecureTransport 5.4 servers occasionally failed with one of the following errors: "MIC comparison failed" or "insufficient-message-security." <br/></p>
            <p><strong>Resolution:</strong> Now, the exchange of AS2 messages between two SecureTransport 5.4 servers is successful.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 25<br/>01047179<br/>01061023         </td>
         <td>RDST-23112         </td>
         <td>
            <p><strong>Issue:</strong> Previously, when the home folder of an account template was defined using the <code>STSESSION_LDAP_DIR_*</code> variable with replace function, the file transfer failed due to the variable not being resolved correctly. <br/></p>
            <p><strong>Resolution:</strong> Now, the <code>STSESSION_LDAP_DIR_*</code> variable is resolved correctly, and the expressions with it are evaluated successfully.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 25<br/>01051236         </td>
         <td>RDST-23120         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SecureTransport couldn't authenticate an account if it existed in any default LDAP domain other than the first one SecureTransport was bound to. The issue was caused by the SecureTransport LDAP search mechanism: the search would stop if the account was not found in the first server of the first domain and would not continue to the second domain.<br/></p>
            <p><strong>Resolution:</strong> Now, SecureTransport tries to bind to at least one server in a domain. 
							</p>
            <ul>
               <li>If binding to the first server fails, SecureTransport continues to the next server.               </li>
               <li>If binding to the first server is successful, SecureTransport tries to find the requested user in it. In case the user is not found there, subsequent calls to other servers in that domain are not permitted. If the user is not found in the domain, SecureTransport continues searching in the other default domains.               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>Patch 25<br/>01043646         </td>
         <td>RDST-23122         </td>
         <td>
            <p><strong>Issue:</strong> Previously, in a streaming environment, SecureTransport failed to send asynchronous AS2-MDN receipts via HTTPS and errors were reported in the server log and on recipient site.<br/></p>
            <p><strong>Resolution:</strong> Now, both the AS2 transfer and the asynchronous AS2-MDN receipt are successfully sent and received via HTTPS.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 25<br/>01050865<br/>01052765         </td>
         <td>RDST-23121         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the Admin REST API returned non-working links to the transfer details in the responses to pull requests to the <code>/transfers/pull</code> resource when:
							            <ul>               <li value="1">the request was submitted over PeSIT               </li>               <li value="2">the request was submitted over FolderMonitor and the destination folder was a subscription folder.                 </li>            </ul></p>
            <p><strong>Resolution:</strong> Now, the returned link is correct and leads to the transfer details.</p>
         </td>
      </tr>
      <tr>
         <td>Patch 25<br/>01047427<br/>01054449<br/>01049461         </td>
         <td>RDST-23115         </td>
         <td>
            <p><strong>Issue:</strong> Previously, an excessive CPU usage was observed on the EC node that didn't hold the Folder Monitor (started second) caused by an infinite loop with no pause time.<br/></p>
            <p><strong>Resolution:</strong> Now, a sleep period is added for the loop mentioned above to prevent high CPU usage.
						</p>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>Patch 25<br/>01061137         </td>
         <td>RDST-22219         </td>
         <td>
            <p><strong>Issue:</strong> Previously, there was a memory leak in the Transaction Manager related to caching of <code>stfs</code> attributes, which were never cleared.
							<br/></p>
            <p><strong>Resolution:</strong> Now, a time-based caching mechanism is used which evicts entries after the configured timeout or when the capacity is reached. The newly added <code>Stfs.attributes.cache.timeout</code> and <code>Stfs.attributes.cache.size</code> configuration options control the timeout and the capacity, respectively.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 25<br/>01015105<br/>01050707<br/>01037370         </td>
         <td>RDST-23959         </td>
         <td>
            <p><strong>Issue:</strong> Previously, a memory leak in the Transaction Manager caused big heap occupancy and excessive garbage collection activity leading to cluster issues.<br/></p>
            <p><strong>Resolution:</strong> Now, the memory leak mentioned above is fixed, and the cluster outages are resolved.
						</p>
         </td>
      </tr>
      <tr>
         <td colspan="3"><strong>SecureTransport 5.4 Patch 24</strong>
         </td>
      </tr>
      <tr>
         <td>Patch 24<br/>01037115         </td>
         <td>RDST-22706         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SecureTransport was using Oracle Java Runtime Environment version 1.8.0_162 and IBM AIX Java Runtime Environment version 1.8.0_507.<br/></p>
            <p><strong>Resolution:</strong> Now, SecureTransport is using Oracle Java Runtime Environment version 1.8.0_212 and IBM AIX Java Runtime Environment version 1.8.0_527.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 24<br/>01061477         </td>
         <td>RDST-22671         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SecureTransport was exposed to the following vulnerabilities due to an outdated version of Apache Tomcat (7.0.85):</p>
            <ul>
               <li>CVE-2019-0232               </li>
               <li>CVE-2019-0221               </li>
               <li>CVE-2018-11784               </li>
               <li>CVE-2018-8034               </li>
               <li>CVE-2018-8014               </li>
               <li>CVE-2018-1336               </li>
            </ul>
            <p>					Now, Apache Tomcat version is updated to 7.0.94 and SecureTransport is no longer exposed to these vulnerabilities						</p>
         </td>
      </tr>
      <tr>
         <td colspan="3"><strong>SecureTransport 5.4 Patch 23</strong>
         </td>
      </tr>
      <tr>
         <td>Patch 23<br/>01026928         </td>
         <td>RDST-22554         </td>
         <td>
            <p><strong>Issue:</strong> Previously, in the SecureTransport Administrator's tool, some GET requests were incorrectly handled like POST requests and processed with status OK, even though an incorrect HTTP method was used, and this behavior could pose security risks.<br/></p>
            <p><strong>Resolution:</strong> Now, when an incorrect HTTP GET method is used with the request, an error response code is returned: <code>HTTP 405 Method Not Allowed</code>.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 23<br/>01026928<br/>01061567         </td>
         <td>RDST-22548         </td>
         <td>
            <p><strong>Issue:</strong> Previously, when users tried to open a valid hidden directory which they didn't have access to, the server responded with a <code>HTTP 403 Forbidden</code> message, making the file system prone to directory-enumeration attacks. <br/></p>
            <p><strong>Resolution:</strong> Now, in the specified case, a <code>HTTP 404 Not Found</code> message is returned which prevents directory-name guessing.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 23<br/>01026928         </td>
         <td>RDST-22556         </td>
         <td>
            <p><strong>Issue:</strong> Previously, verbose server information was displayed in the <code>Server</code> header of HTTP responses in the SecureTransport Administration Tool.<br/></p>
            <p><strong>Resolution:</strong> Now, there is a new configuration option <code>Admin.ServerHeaderTokens</code> that allows an administrator to control the information displayed in the Server HTTP response header for the Administration Tool. Possible values are:
							</p>
            <ul>
               <li><code>None</code> - no information is displayed               </li>
               <li><code>Prod </code> - the product name, <em>SecureTransport</em>, is displayed               </li>
               <li><code>OS</code> - the operating system on which SecureTransport is running is displayed               </li>
               <li><code>Full</code> - default; the product name, build number, and the operating system are displayed               </li>
            </ul>
            <p>
					In addition, the behavior of the <code>Http.ServerHeaderTokens</code> configuration option (which controls the <code>Server</code> HTTP header in ST Web Client responses) has been changed to be consistent with <code>Admin.ServerHeaderTokens</code>.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 23<br/>01026928         </td>
         <td>RDST-22547         </td>
         <td>
            <p><strong>Issue:</strong> Previously, when a custom unexpected header was added to some of the SecureTransport Administrator's tool requests, the server was returning a <code>HTTP 500 Internal Server Error</code> that contained sensitive data.<br/></p>
            <p><strong>Resolution:</strong> Now, the server handles unexpected headers correctly by returning a <code>HTTP 400 Bad Request</code> error.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 23<br/>01026928         </td>
         <td>RDST-22555         </td>
         <td>
            <p><strong>Issue:</strong> Previously, application content served over HTTPS was cached due to the <code>Cache-Control: private</code> directive in HTTP headers of the SecureTransport Administrator's Tool requests. <br/></p>
            <p><strong>Resolution:</strong> Now, there is a new configuration option <code>Admin.ControlCaching</code> that allows a SecureTransport administrator to control resource caching behavior. Possible values are <code>true</code> or <code>false</code>. When the option is set to <code>true</code>, the setting of the header is <code>Cache-Control: no-cache, no-store</code> on all static and non-static requests. 
							<br/></p>
            <p><strong>Note:</strong> When requests are not being cached, performance degradation may occur. After changing the value of the <code>Admin.ControlCaching</code>, the Admin service must be restarted.
							</p>
         </td>
      </tr>
      <tr>
         <td>Patch 23<br/>01026928         </td>
         <td>RDST-22557         </td>
         <td>
            <p><strong>Issue:</strong> Previously, some client-side ST Web Client restrictions could be manipulated and processed. <br/></p>
            <p><strong>Resolution:</strong> Now, user-defined input is validated on the server-side in sync with the client-side logic. When the user is not permitted to perform an action, a <code>HTTP 401 Unauthorized</code> error is returned. 
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 23<br/>01025773         </td>
         <td>RDST-22546         </td>
         <td>
            <p><strong>Issue:</strong> Previously, when uploading malicious content in a Mailbox message, the content remained present on the server even if ICAP Scanning was enabled. <br/></p>
            <p><strong>Resolution:</strong> Now, when ICAP Scanning is enabled, a scan is performed upon saving a draft or sending a message. The scan is done according to the settings of the ICAP Server. If malicious content is detected, it is immediately deleted from the server and a <code>HTTP 406 Not Acceptable</code> error is returned. 
						</p>
         </td>
      </tr>
      <tr>
         <td colspan="3"><strong>SecureTransport 5.4 Patch 21</strong>
         </td>
      </tr>
      <tr>
         <td>Patch 21<br/>01023832<br/>01041772<br/>01048066<br/>01052077<br/>01055223<br/>01052013<br/>01051077<br/>01061357         </td>
         <td>RDST-22117         </td>
         <td>
            <p><strong>Issue:</strong> Previously, Server Log and Transfer Log Maintenance applications failed to export all specified for rotation entries when SecureTransport was running on MySQL database. <br/></p>
            <p><strong>Resolution:</strong> Now, both applications successfully export all specified for rotation entries when SecureTransport is running on MySQL database.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 21<br/>01039713         </td>
         <td>RDST-22113         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the transfer site (AWS) S3 settings were not visible to Delegated administrators created with Read Only or Checker rights.<br/></p>
            <p><strong>Resolution:</strong> Now, transfer site (AWS) S3 settings are exposed to Delegated administrators with Read Only or Checker rights.
						</p>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>Patch 21<br/>01039178<br/>01057362         </td>
         <td>RDST-21145         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the decompression of large archived files as part of a route was lagging when repository encryption was enabled. <br/></p>
            <p><strong>Resolution:</strong> Now, the compression/decompression library was replaced with Zip4j, which significantly decreases the Desteps execution time.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 21<br/>01044549         </td>
         <td>RDST-22110         </td>
         <td>
            <p><strong>Issue:</strong> Previously, when the <code>usage</code> parameter was not populated in a request, the api/v1.4/certificates resource returned incorrect certificate objects.<br/></p>
            <p><strong>Resolution:</strong> Now, in the specified case, the api/v1.4/certificates resource returns certificate objects according to the "offset".
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 21<br/>01049438         </td>
         <td>RDST-22116         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the Line Folding step in Advanced Routing was not working correctly and folded up to 4096 lines when used with large files.<br/></p>
            <p><strong>Resolution:</strong> Now, the Line Folding step is working correctly with files of any size.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 21<br/>01021339         </td>
         <td>RDST-22112         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SecureTransport patches could not be applied if the server was running on MSSQL 2014 Standard Edition database without partitioning.<br/></p>
            <p><strong>Resolution:</strong> Now, SecureTransport patches can be successfully applied on servers running on MSSQL 2014 Standard Edition regardless of partitioning.
						</p>
         </td>
      </tr>
      <tr>
         <td>01039450<br/>00979797<br/>00915027         </td>
         <td>RDST-22111         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SecureTransport did not remove <code>.stfs/attrs</code> files from the Folder Monitor's download folder when the Post transformation action for pushed files was set to delete.<br/></p>
            <p><strong>Resolution:</strong> Now, in the specified case, SecureTransport removes all the <code>.stfs/attrs</code> files from Folder Monitor's download folder.</p>
         </td>
      </tr>
      <tr>
         <td>01049438         </td>
         <td>RDST-22116         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the Line Folding step in Advanced Routing was not working correctly and folded up to 4096 lines when used with large files.<br/></p>
            <p><strong>Resolution:</strong> Now, the Line Folding step is working correctly with files of any size.</p>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td colspan="3"><strong>SecureTransport 5.4 Patch 20</strong>
         </td>
      </tr>
      <tr>
         <td>Patch 20<br/>00934232<br/>00963524<br/>00969089<br/>00969102<br/>00987665<br/>01045760         </td>
         <td>RDST-21786         </td>
         <td>
            <p><strong>Issue:</strong> Previously, no SSL/TLS related information about newly successfully established connections
							was logged in SecureTransport.<br/></p>
            <p><strong>Resolution:</strong> Now, five new configuration options are introduced, each dedicated to a protocol
							server connection: <br/><code>SSLLogging.Http, SSLLogging.Ftp, SSLLogging.Ssh, SSLLogging.As2, and SSLLogging.Pesit</code><br/>							When you set the respective option to <code>true</code>, SSL/TLS security information
							(remote address (host), cipher suite and TLS/SSL protocol version) for each successfully established protocol connection
							is added to the ServerLog. When you set the option to <code>false</code>, SSL/TLS security information is not added to the ServerLog.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 20<br/>01033484         </td>
         <td>RDST-21798         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SecureTransport did not report to Axway Sentinel the <code>STATE=SENT</code> when ICAP was enabled.<br/></p>
            <p><strong>Resolution:</strong> Now, SecureTransport reports the <code>STATE=SENT</code> to Axway Sentinel when ICAP is enabled.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 20<br/>01044490         </td>
         <td>RDST-21796         </td>
         <td>
            <p><strong>Issue:</strong> Previously, DXAGENT_TARGET was not being populated when Axway Sentinel was enabled and configured and the administrator was using REST API to submit server-initiated transfers pull requests.<br/></p>
            <p><strong>Resolution:</strong> Now, DXAGENT_TARGET is populated on REST API pull requests regardless of the Axway Sentinel configuration in SecureTransport.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 20<br/>01032772         </td>
         <td>RDST-21801         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SecureTransport was not generating new CoreID values for inbound files if files with the same name from the same account were transferred in a previous session. <br/></p>
            <p><strong>Resolution:</strong> Now, new CoreID values are generated for all inbound transfers regardless of the file names and sessions.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 20<br/>01046988<br/>01042218<br/>01052063<br/>01033837<br/>01034384         </td>
         <td>RDST-21797<br/>RDST-21795<br/>RDST-21800<br/>RDST-21250         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the <code>DXAGENT_TRANSFERSAPI_*</code> environment variables were not exposed by SecureTransport in transfer sites.<br/></p>
            <p><strong>Resolution:</strong> Now, the <code>DXAGENT_TRANSFERSAPI_*</code> environment variables are populated and resolved correctly.
						</p>
         </td>
      </tr>
      <tr>
         <td colspan="3"><b>SecureTransport 5.4 Patch 19</b>
         </td>
      </tr>
      <tr>
         <td>Patch 19<br/>01012009         </td>
         <td>RDST-21390         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the SecureTransport administrator could not import a certificate of type PKCS12 with non-encrypted parts.<br/></p>
            <p><strong>Resolution:</strong> Now, such certificates can be imported and used as expected.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 19<br/>01031334         </td>
         <td>RDST-21388         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the SecureTransport Administrator's Guide did not include sufficient info about the way the File Tracking was logging PeSIT transfers. <br/></p>
            <p><strong>Resolution:</strong> Now, a dedicated note is added to the SecureTransport Administrator's Guide.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 19<br/>01043834         </td>
         <td>RDST-21387         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the ST Web Client Configuration Guide contained an incorrect reference to fileOperations configuration. <br/></p>
            <p><strong>Resolution:</strong> Now, the ST Web Client Configuration Guide is updated with the correct information.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 19<br/>01033091         </td>
         <td>RDST-21396         </td>
         <td>
            <p><strong>Issue:</strong> Previously, if a network zone was used by multiple transfer sites, its deletion could take a significant amount of time and even time out.<br/></p>
            <p><strong>Resolution:</strong> Now, if such a zone is not attached to a transfer site, deletion occurs instantly; otherwise the delete action is denied.
						</p>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>Patch 19<br/>01049071         </td>
         <td>RDST-21163         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the SТ Web Client did not load properly when the <code>Http.ServerHeaderTokens</code> server option was set to <code>"None"</code>. <br/></p>
            <p><strong>Resolution:</strong> Now, the ST Web Client loads normally when <code>Http.ServerHeaderTokens</code> is configured to <code>"None"</code>.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 19<br/>01043138         </td>
         <td>RDST-21389         </td>
         <td>
            <p><strong>Issue:</strong> Previously, there was inconsistent reporting of Sentinel states during server-initiated transfer pull.
							The inconsistency was as follows:
							</p>
            <ul>
               <li>Internal transfer sites - when fixed file name was used as download pattern, the <code>TO_EXECUTE</code>
									state was reported, instead of <code>SUBMITTED</code> state.
								Also, the <code>filename</code> attribute was populated with subscription folder, instead of fixed file name.               </li>
               <li>Custom connectors - regardless of the remote download pattern, the state was always
								<code>TO_EXECUTE</code>, instead of <code>SUBMITTED</code> state.               </li>
            </ul>
            <p>
						Now, during server-initiated transfer pull, the <code>SUBMITTED</code> state is reported with the correct filename attribute, regardless of the remote download pattern. <br/><b>Note:</b> For custom connectors, now there is way to report both the remote download folder and
							remote download pattern. In order for custom connectors to have consistent states during pull, the
							connector <b>must</b> report the remote download pattern and could optionally report the remote download folder.
							</p>
         </td>
      </tr>
      <tr>
         <td>Patch 19<br/>01040027         </td>
         <td>RDST-21392         </td>
         <td>
            <p><strong>Issue:</strong> Previously, in some cases, attempts to change PGP keys in an advanced routing PGP encryption step resulted in an error with the following message:"Please specify account for encryption setting".<br/></p>
            <p><strong>Resolution:</strong> Now, the SecureTransport administrator can successfully change PGP keys in the advanced routing PGP encryption step.</p>
         </td>
      </tr>
      <tr>
         <td>Patch 19<br/>01042013         </td>
         <td>RDST-21391         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SecureTransport was not sending proper response codes for failed push transfers through the REST API.<br/></p>
            <p><strong>Resolution:</strong> Now, response codes are sent for failed push transfer through the REST API in the following cases: incorrect file name or site name, incorrect account credentials, stopping of Transaction Manager or protocol servers.</p>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td colspan="3"><strong>SecureTransport 5.4 Patch 18</strong>
         </td>
      </tr>
      <tr>
         <td>Patch 18<br/>01021339         </td>
         <td>RDST-21372         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SecureTransport used to fetch all application properties during advanced routing in order to evaluate the subscription folder. <br/></p>
            <p><strong>Resolution:</strong> Now, during subscription folder evaluation, SecureTransport fetches only the needed properties of the application.</p>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>Patch 18<br/>00962139         </td>
         <td>RDST-14891         </td>
         <td>
            <p><strong>Issue:</strong> Previously, when the SТ Web Client was requesting more AddressBook entries than defined in the <code>AddressBook.Limit.MaxDisplayEntries</code> configuration option, an error was shown in the server log, and no or random entries were returned.
						</p>
            <p><strong>Resolution:</strong> Now, instead of throwing an error in the server log, a warning message is displayed. The value defined in the <code>AddressBook.Limit.MaxDisplayEntries</code> configuration option is now used for specifying the number of entries that will be shown in the Address book.</p>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>Patch 18<br/>01009843         </td>
         <td>RDST-19286         </td>
         <td>
            <p><strong>Issue:</strong> Previously, on rare occasions, the transferLog maintenance application was failing to export partitions due to a database operation timeout.
							<br/></p>
            <p><strong>Resolution:</strong> Now, each transferLog partition table is exported through a new database session.
						</p>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>Patch 18<br/>01015773<br/>01047817         </td>
         <td>RDST-19293         </td>
         <td>
            <p><strong>Issue:</strong> Previously, Sentinel was not displaying the number of records in a transfered file over PeSIT due to the RecordNumber attribute value not being sent by SecureTransport to Axway Sentinel. <br/></p>
            <p><strong>Resolution:</strong> Now, SecureTransport reports the RecordNumber to Axway Sentinel with each PeSIT transfer, and Sentinel displays the correct number of records (PI28) when the transfer is finished.  
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 18<br/>01033095 <br/>00921250         </td>
         <td>RDST-21367         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the SecureTransport REST API was returning duplicate JSON object entries that were containing different values with some resources.<br/></p>
            <p><strong>Resolution:</strong> Now, when a SecureTransport REST API resource contains duplicate JSON object entries, those are returned as an array data structure.  
						</p>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>Patch 18<br/>01033095 <br/> 00946682         </td>
         <td>RDST-19552         </td>
         <td>
            <p><strong>Issue:</strong> Previously, an incorrect HTTP code (<code>204 No Content</code>) was returned with some unsuccessful POST requests to the <code>subscriptions</code> resource in the SecureTransport REST API.<br/></p>
            <p><strong>Resolution:</strong> Now, the proper HTTP code is returned in the specified cases. (<code>422 - Unprocessable Entity</code>.)
						</p>
         </td>
      </tr>
      <tr>
         <td colspan="3"><strong>SecureTransport 5.4 Patch 17</strong>
         </td>
      </tr>
      <tr>
         <td>Patch 17<br/>01032979         </td>
         <td>RDST-21298         </td>
         <td>
            <p><strong>Issue:</strong>	Previously, when an administrator was trying to authenticate with an expired password via the REST API, SecureTransport returned an error in HTML format.<br/></p>
            <p><strong>Resolution:</strong> Now, when an administrator attempts to authenticate with an expired password via the REST API, SecureTransport returns a message in json/xml format.</p>
         </td>
      </tr>
      <tr>
         <td>Patch 17<br/>01022268         </td>
         <td>RDST-21301         </td>
         <td>
            <p><strong>Issue:</strong>	Previously, REST API deleting (without purging) of an account with a home folder located on Amazon EFS that contained more than 10 000 files, could take up to 40 seconds.<br/></p>
            <p><strong>Resolution:</strong> Now, in the specified case, such an account is deleted almost instantly.</p>
         </td>
      </tr>
      <tr>
         <td>Patch 17<br/>01023817         </td>
         <td>RDST-21313         </td>
         <td>
            <p><strong>Issue:</strong>	Previously, the timestamp for the "Last modified" property of files and folders (as reported by the SecureTransport SFTP server) did not include seconds.<br/></p>
            <p><strong>Resolution:</strong> Now, the timestamp for the "Last modified" property of files and folders (as reported by the SecureTransport SFTP server) includes seconds.</p>
         </td>
      </tr>
      <tr>
         <td>Patch 17<br/>01021602<br/>01028269         </td>
         <td>RDST-21314         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the SecureTransport Administrator's Guide did not include the complete list of supported SSH cipher suites.<br/></p>
            <p><strong>Resolution:</strong> Now, the <em>SecureTransport cipher suites</em> in the SecureTransport Administrator's Guide offers the complete list of supported SSH cipher suites, including MACs, KEXs and public keys.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 17<br/>01030844         </td>
         <td>RDST-21299         </td>
         <td>
            <p><strong>Issue:</strong> Previously, it was not possible to enable the “Allow this account to login to SecureTransport Server” option for an account if the option was disabled during the account's creation.<br/></p>
            <p><strong>Resolution:</strong> Now, this option can be enabled after the account's creation.
						</p>
         </td>
      </tr>
      <tr>
         <td colspan="3"><strong>SecureTransport 5.4 Patch 16</strong>
         </td>
      </tr>
      <tr>
         <td>Patch 16<br/>01024156         </td>
         <td>RDST-21274         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the server log and the File Tracking were displaying an error that the transfer did not go through when archiving was disabled on the SendToPartner step in Advanced Routing, while archiving was enabled globally.<br/></p>
            <p><strong>Resolution:</strong> Now, file archiving is working in all cases without errors.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 16<br/>01033837<br/>01034384	         </td>
         <td>RDST-21250         </td>
         <td>
            <p><strong>Issue:</strong> Previously, download/pull of files when using advanced expressions for the download folder in the Transfer Site was not successful when the destination folder was a subscription folder and the value needed to evaluate this expression was passed as a custom property for transfer pull. <br/></p>
            <p><strong>Resolution:</strong> Now, these advanced expressions for are properly evaluated.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 16<br/>01025615         </td>
         <td>RDST-21268         </td>
         <td>
            <p><strong>Issue:</strong> Previously, it was not possible to enable an existing account to log in to SecureTransport, unless this option was enabled with the account creation.<br/></p>
            <p><strong>Resolution:</strong> Now, it is possible to toggle this option with an existing account.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 16<br/>01027677         </td>
         <td>RDST-21265         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the logger of the <code>BaseServerTransferAgent</code> class was missing some of the log messages.<br/></p>
            <p><strong>Resolution:</strong> Now, all messages are logged accurately.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 16<br/>01007233         </td>
         <td>RDST-21270         </td>
         <td>
            <p><strong>Issue:</strong> Previously, in SecureTransport cluster setup, file deletion with some file systems was failing across all nodes on Advanced Routing transfers.<br/></p>
            <p><strong>Resolution:</strong> Now, file deletion with these file systems processes successfully across all nodes on Advanced Routing transfers.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 16<br/>01009858         </td>
         <td>RDST-21273         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SecureTransport would search across all backup LDAP servers (when configured for a specific domain) after an incorrect user login attempt.<br/></p>
            <p><strong>Resolution:</strong> Now, SecureTransport does not search across all backup LDAP servers (when configured for a specific domain) when user credentials input is incorrect.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 16<br/>01021231         </td>
         <td>RDST-21266         </td>
         <td>
            <p><strong>Issue:</strong> Previously, when a user sent a file using AdHoc with a configured expiration time for the download link, the package maintenance application would run after link expiration period (thus deleting the package), and the recipient would get an HTTP error 500 on file download attempt.<br/></p>
            <p><strong>Resolution:</strong> Now, in the case described, the recipient receives a HTTP error code 404, indicating that the download link to the respective file has expired.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 16<br/>01024580         </td>
         <td>RDST-21267         </td>
         <td>
            <p><strong>Issue:</strong> Previously, ST Web Client was adding a tilde '~' symbol at the end of the root URL after account authentication due to issues with WAF and blocked requests.<br/></p>
            <p><strong>Resolution:</strong> Now, the tilde '~' symbol is not added to the ST Web Client root URL.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 16<br/>01032553         </td>
         <td>RDST-21252         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the Connect:Direct transfer folder was deleted on Transaction Manager launch.<br/></p>
            <p><strong>Resolution:</strong> Now, a new configuration option is added: <code>ConnectDirectTransferAgent.transfersFolder.purge</code>. When set to <code>false</code>, the folder from <code>ConnectDirectTransferAgent.transfersFolder</code> will not be deleted on Transaction Manager launch.
						</p>
         </td>
      </tr>
      <tr>
         <td colspan="3"><strong>SecureTransport 5.4 Patch 15</strong>
         </td>
      </tr>
      <tr>
         <td>Patch 15<br/>01031931         </td>
         <td>RDST-21182         </td>
         <td>
            <p><strong>Issue:</strong> Previously, after applying SecureTransport 5.4 Patch 11, there was a performance degradation with downloads of files over SFTP.
							<br/></p>
            <p><strong>Resolution:</strong> Now, the performance degradation of file downloads over SFTP is mitigated. 
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 15<br/>00890670         </td>
         <td>RDST-21183         </td>
         <td>
            <p><strong>Issue:</strong> Previously, it was not possible to create an Account Template with mapped home folders for SiteMinder users.
							<br/></p>
            <p><strong>Resolution:</strong> Now, SecureTransport can be configured to explicitly use the SiteMinder attributes and thus enable Account Templates to be created for SiteMinder users with mapped home folders. 						
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 15<br/>01028370         </td>
         <td>RDST-21184         </td>
         <td>
            <p><strong>Issue:</strong> Previously, when SecureTransport was receiving files in ASCII mode over PeSIT protocol from Transfer CFT, the file line endings were corrupted.
							<br/></p>
            <p><strong>Resolution:</strong> Now, when performing such transfers, the file integrity is correct and the line endings are properly preserved.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 15<br/>01025754<br/>01027067<br/>01027889         </td>
         <td>RDST-21190         </td>
         <td>
            <p><strong>Issue:</strong> Previously, a server-initiated transfer pull via SSH using an Advanced Routing subscription was processed successfully but an error was logged in the Server Log.
							<br/></p>
            <p><strong>Resolution:</strong> Now, there are no errors present in the Server Log and the pull is executed successfully.
						</p>
         </td>
      </tr>
      <tr>
         <td colspan="3"><strong>SecureTransport 5.4 Patch 14</strong>
         </td>
      </tr>
      <tr>
         <td>Patch 14<br/>01006400 <br/>01014971<br/>01030597         </td>
         <td>RDST-21176         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SecureTransport administrators were unable to add nodes in Enterprise Cluster environment after upgrade to Patch 6 and later.
							<br/></p>
            <p><strong>Resolution:</strong> Now, this issue is resolved and adding nodes to Enterprise Cluster environment is possible.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 14<br/>01025773         </td>
         <td>RDST-21172         </td>
         <td>
            <p><strong>Issue:</strong> Previously, with SecureTransport logs exported in CSV format, some ICAP Settings column fields were vulnerable to MS Excel formula injections.<br/></p>
            <p><strong>Resolution:</strong> Now, the vulnerable ICAP Settings column fields are properly escaped.</p>
         </td>
      </tr>
      <tr>
         <td colspan="3"><strong>SecureTransport 5.4 Patch 13</strong>
         </td>
      </tr>
      <tr>
         <td>Patch 13<br/>01014822         </td>
         <td>RDST-19355         </td>
         <td>
            <p><strong>Issue:</strong> Previously, Transfer status was not returned in REST API query response when the destination folder was a subscription folder.<br/></p>
            <p><strong>Resolution:</strong>Now, the transfer status is returned correctly regardless of the destination folder.</p>
         </td>
      </tr>
      <tr>
         <td>Patch 13<br/>01025773         </td>
         <td>RDST-19364         </td>
         <td>
            <p><strong>Issue:</strong> Previously, with SecureTransport logs exported in CSV format, some ICAP Settings column fields were vulnerable to MS Excel formula injections.<br/></p>
            <p><strong>Resolution:</strong> Now, the vulnerable ICAP Settings column fields are properly escaped.</p>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>Patch 13<br/>01017781         </td>
         <td>RDST-18905         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SecureTransport used to print verbose messages for SSH connections using the <code>com.maverick.sshd.events</code> package logger. <br/></p>
            <p><strong>Resolution:</strong> Now, the SecureTransport internal Maverick library is upgraded and those messages are not available on the specified logger. A new logger is introduced and must be used on debug level, using the following package: <code>com.tumbleweed.st.server.sshd.logging</code>.
						</p>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>Patch 13<br/>01014822         </td>
         <td>RDST-18338         </td>
         <td>
            <p><strong>Issue:</strong> Previously, Transfer status was not returned in REST API query response when the destination folder was a subscription folder.
							<br/></p>
            <p><strong>Resolution:</strong> Now, the transfer status is returned correctly regardless of the destination folder.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 13<br/>01018381         </td>
         <td>RDST-19352         </td>
         <td>
            <p><strong>Issue:</strong> Previously, updating values of the <code>FolderMonitor.pollInternal</code> and <code>FolderMonitor.fileDelayInterval</code> configuration properties was requiring a Transaction Manager for changes to take effect.
							<br/></p>
            <p><strong>Resolution:</strong> Now, changes to the values of those properties are applied instantly.
						</p>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>Patch 13<br/>00967933         </td>
         <td>RDST-14894         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the SecureTransport admin Swagger API website was not loading in Internet Explorer.
							<br/></p>
            <p><strong>Resolution:</strong> Now, it is possible to open and use Secure Transport admin Swagger API website in Internet Explorer.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 13<br/>01009858         </td>
         <td>RDST-19351         </td>
         <td>
            <p><strong>Issue:</strong> Previously, when multiple LDAP servers were configured under a domain, SecureTransport was searching across all LDAP servers for a user even when passing wrong credentials.
							<br/></p>
            <p><strong>Resolution:</strong> Now, if SecureTransport does not find a record for the user in the first available LDAP database, it does not try to connect to backup LDAP servers.
						</p>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>Patch 13<br/>01025773         </td>
         <td>RDST-18957         </td>
         <td>
            <p><strong>Issue:</strong> Previously, <code>Title</code> and <code>Notes</code> fields in "Setup -&gt;Network Zones -&gt;New Network Zone -&gt;New Node" were vulnerable to DOM based XSS attack.
							<br/></p>
            <p><strong>Resolution:</strong> Now, <code>Title</code> and <code>Notes</code> fields are protected against XSS attack.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 13<br/>01020296         </td>
         <td>RDST-19359         </td>
         <td>
            <p><strong>Issue:</strong> Previously, connection to MySQL was failing if the database password contained some special characters.
							<br/></p>
            <p><strong>Resolution:</strong> Now, connection to MySQL is successful regardless of characters used into the database password.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 13<br/>01012163         </td>
         <td>RDST-19354         </td>
         <td>
            <p><strong>Issue:</strong> Previously, when ICAP scans were enabled, there was inconsistency in the "Status" column values in File Tracking Export and File Tracking as displayed in the SecureTransport Administration Tool.
							<br/></p>
            <p><strong>Resolution:</strong> Now, the "Status" column values across File Tracking and File Tracking Export are consistent.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 13<br/>01022268         </td>
         <td>RDST-19362         </td>
         <td>
            <p><strong>Issue:</strong> Previously, account deletion through REST API was reporting an error after 2 minutes if the account's home folder was on the Amazon EFS and was containing a large number of files.
							<br/></p>
            <p><strong>Resolution:</strong> Now, account deletion through REST API in the specified case occurs faster and does not report any errors.
						</p>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>Patch 13<br/>00900125         </td>
         <td>RDST-18058         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the REST API documentation (api/v1.4/docs/index.html) was lacking descriptive information and complete model schema for /accounts resource.
							<br/></p>
            <p><strong>Resolution:</strong> Now, missing properties from the REST API documentation are added in the model schema.
						</p>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>Patch 13<br/>00987905         </td>
         <td>RDST-17306         </td>
         <td>
            <p><strong>Issue:</strong> Previously, when file names were containing control characters, the Transfer and Xfer logs were broken and reported those files with incorrect names.<br/></p>
            <p><strong>Resolution:</strong> Now, the respective logs report those characters correctly as part of the file name.
						</p>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>Patch 13<br/>00997986         </td>
         <td>RDST-17284         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SecureTransport was relying on the operating system filesystem to check, validate and resolve file names, in this case - preserving trailing whitespaces at the end of file names.
							<br/></p>
            <p><strong>Resolution:</strong> Now, SecureTransport explicitly strips trailing whitespaces at the end of file names.
						</p>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>Patch 13<br/>00953578<br/>00961378<br/>00974685         </td>
         <td>RDST-17282         </td>
         <td>
            <p><strong>Issue:</strong> Previously, if the Advanced Expression for Download Folder was not checked in the transfer site settings, remote folder was missing from file tracking report.
							<br/></p>
            <p><strong>Resolution:</strong> Now, if the Advanced Expression for Download Folder is not checked in the transfer site settings, remote folder is populated into file tracking report.
						</p>
         </td>
      </tr>
      <tr>
         <td colspan="3"><strong>SecureTransport 5.4 Patch 12</strong>
         </td>
      </tr>
      <tr>
         <td>01017427         </td>
         <td>RDST-18978         </td>
         <td>
            <p><strong>Issue:</strong> Previously, transfer resubmit was not working with SecureTransport running on Windows and using CIFS shares for home folders and archiving.
						<br/></p>
            <p><strong>Resolution:</strong> Now, the resubmit action is successful when having the home folders and archiving on such setup.
					</p>
         </td>
      </tr>
      <tr>
         <td>01004562<br/>01017037         </td>
         <td>RDST-18976         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the mail templates selection in routes was reverted to "None" after saving the Route.
						<br/></p>
            <p><strong>Resolution:</strong> Now, mail templates in routes are saved successfully.
					</p>
         </td>
      </tr>
      <tr>
         <td>01017008         </td>
         <td>RDST-18977         </td>
         <td>
            <p><strong>Issue:</strong> Previously, an attempt to create a Connect:Direct transfer site when using a site template with placeholders triggered a server error.
						<br/></p>
            <p><strong>Resolution:</strong> Now, the creation of a Connect:Direct transfer site when using a site template with placeholders executes successfully.
					</p>
         </td>
      </tr>
      <tr>
         <td>01021639<br/>01021341         </td>
         <td>RDST-18979         </td>
         <td>
            <p><strong>Issue:</strong> Previously, it was not possible to open Route Package Templates and Route Packages with configured ‘Notifications’.
						<br/></p>
            <p><strong>Resolution:</strong> Now, Route Package Templates and Route Packages with configured ‘Notifications’ can be opened successfully.
					</p>
         </td>
      </tr>
      <tr>
         <td colspan="3"><strong>SecureTransport 5.4 Patch 11</strong>
         </td>
      </tr>
      <tr>
         <td>Patch 11<br/>01017388<br/>01006884         </td>
         <td>RDST-18902         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SSH transfers were processing at low speeds on networks with high latency.<br/></p>
            <p><strong>Resolution:</strong> Now, new configuration settings are introduced in the <code>start_sshd</code> script to allow improving the SSH transfer speeds in high latency networks. The SecureTransport administrator can specify buffer sizes for inbound / outbound transfers, as well as values for minimum and maximum window space, as follows:
						</p>
            <ul>
               <li><code>-DrecvBufferSize</code> - 8192 by default               </li>
               <li><code>-DsendBufferSize</code> - 8192 by default               </li>
               <li><code>-Dssh.maxWindowSpace</code> - 1048576 by default               </li>
               <li><code>-Dssh.minWindowSpace</code> - 131072 by default               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>Patch 11<br/>00998751         </td>
         <td>RDST-18886         </td>
         <td>
            <p><strong>Issue:</strong> Previously, when the <code>Publish To Account</code> step was trying to send a file considered as malware, the final file status was <code>In progress</code>.
						<br/></p>
            <p><strong>Resolution:</strong> Now, such file transfer is marked as <code>Failed</code>.
					</p>
         </td>
      </tr>
      <tr>
         <td>Patch 11<br/>01010222         </td>
         <td>RDST-18881         </td>
         <td>
            <p><strong>Issue:</strong> Previously, when working with Amazon S3 Pluggable transfer sites, SecureTransport was not putting failing proxies in denied state after reaching the maximum transfer attempts.<br/></p>
            <p><strong>Resolution:</strong> Now, SecureTransport is working correctly when using proxies and S3 transfer sites.
					</p>
         </td>
      </tr>
      <tr>
         <td>Patch 11<br/>01015981         </td>
         <td>RDST-18904         </td>
         <td>
            <p><strong>Issue:</strong> Previously, a SecureTransport 5.4 upgrade attempt to Patch 5 or later was failing throwing the following error:
						<code>"java.sql.SQLException: ORA-02443: Cannot drop constraint - nonexistent constraint"</code>.<br/></p>
            <p><strong>Resolution:</strong> Now, this issue is fixed and an upgrade to a patch later than Patch 5 proceeds successfully.
					</p>
         </td>
      </tr>
      <tr>
         <td>Patch 11<br/>01013258         </td>
         <td>RDST-18889         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SecureTransport was trying to pull all files at once, ignoring the maximum allowed number of parallel transfers when using the REST API call <code>HOSTNAME/api/v1.4/transfers/pull</code> to trigger a transfer on a transfer site.<br/></p>
            <p><strong>Resolution:</strong> Now, if the <code>maxParallelSitPulls</code> parameter is added in the <code>/transfers/pull</code> POST request, its value applies in both cases - pull existing subscription or pull destination directory, if no subscription was found. If this parameter is not present in the request, the subscription configuration is used. For pulling destination directory without subscription, use the Transfer Site <code>maxParallelSitPulls</code> value.
					</p>
         </td>
      </tr>
      <tr>
         <td>Patch 11<br/>01003493         </td>
         <td>RDST-18888         </td>
         <td>
            <p><strong>Issue:</strong> Previously, an upgrade to SecureTransport 5.4 Patch 6 introduced connectivity issues to the Oracle database when the password was containing exclamation mark symbols.<br/></p>
            <p><strong>Resolution:</strong> Now, this issue is fixed.
					</p>
         </td>
      </tr>
      <tr>
         <td>Patch 11<br/>01007780         </td>
         <td>RDST-18357         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the PSO plugin could not read its configuration.<br/></p>
            <p><strong>Resolution:</strong> Now, the PSO plugin successfully reads its configuration.
					</p>
         </td>
      </tr>
      <tr>
         <td>Patch 11<br/>01006783         </td>
         <td>RDST-18879         </td>
         <td>
            <p><strong>Issue:</strong> Previously, getting information for the global route template or user route package could be very slow.<br/></p>
            <p><strong>Resolution:</strong> Now, there is performance improvement while getting global route template or user route package information.
					</p>
         </td>
      </tr>
      <tr>
         <td>Patch 11<br/>01015266         </td>
         <td>RDST-18890         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the SecureTransport administrator was unable to add an underscore symbol in the hostname field for the Transfer Site server.<br/></p>
            <p><strong>Resolution:</strong> Now, the SecureTransport administrator is able to add underscore symbol in the hostname field for the Transfer Site server.
					</p>
         </td>
      </tr>
      <tr>
         <td>Patch 11<br/>00978203         </td>
         <td>RDST-18883         </td>
         <td>
            <p><strong>Issue:</strong> Previously, a regular expression string used in the Folder Monitor Transfer site / "Upload location” was not properly evaluated in the File Tracking page.<br/></p>
            <p><strong>Resolution:</strong> Now regular expression used in 'Upload Folder' is evaluated properly.
					</p>
         </td>
      </tr>
      <tr>
         <td>Patch 11<br/>00998821         </td>
         <td>RDST-18885         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the option 'Audit Log Rights' was not selected when a delegated administrator was configured with 'Read Only' or 'Checker Rights' privileges.
						<br/></p>
            <p><strong>Resolution:</strong> Now, the option 'Audit Log Rights' is automatically selected when a delegated administrator is configured with either 'Read Only' or 'Checker Rights' privileges.
					</p>
         </td>
      </tr>
      <tr>
         <td>Patch 11<br/>00993661         </td>
         <td>RDST-18884         </td>
         <td>
            <p><strong>Issue:</strong> Previously, an attempt to create a new Delegated Administrator was resulting in producing many duplicate entries for the selection of a Parent Administrator.
						<br/></p>
            <p><strong>Resolution:</strong> Now, the option to select a Parent Administrator does not contain duplicate entries.
					</p>
         </td>
      </tr>
      <tr>
         <td colspan="3"><strong>SecureTransport 5.4 Patch 10</strong>
         </td>
      </tr>
      <tr>
         <td>
            <p>Patch 10<br/>00971186</p>
            <p>00946383</p>
         </td>
         <td>RDST-18155         </td>
         <td>
            <p><strong>Issue:</strong> Previously, all files and directories in a current account directory were visible.<br/></p>
            <p><strong>Resolution:</strong> Now, two new configuration options are introduced: <code>ShowOwnedFilesOnly</code> and <code>ShowHiddenFiles</code>. The possible values with each are <code>true</code> or <code>false</code>.
							</p>
            <ul>
               <li>When <code>ShowOwnedFilesOnly</code> is <code>false</code>, all files and directories in the current account directory will be visible. When set to <code>true</code>, only files and directories owned by that account will be visible. Default value is <code>false</code>.               </li>
               <li>The <code>ShowHiddenFiles</code> configures on the server side whether to show hidden files or not. When <code>ShowHiddenFiles</code> is <code>true</code> hidden files will be displayed. When set to <code>false</code>, only files that are not hidden will be displayed. Default value is <code>true</code>.               </li>
            </ul><strong>Note:</strong> The configuration option <code>ShowOwnedFilesOnly</code> will take action
						only on Unix-like Operation Systems.
					         </td>
      </tr>
      <tr>
         <td colspan="3"><strong>SecureTransport 5.4 Patch 9</strong>
         </td>
      </tr>
      <tr>
         <td>Patch 9<br/>01001051         </td>
         <td>RDST-18149         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the HTTP POST request was including a CRSF header without any value when a user was resetting their password.<br/></p>
            <p><strong>Resolution:</strong> Now, the HTTP POST request was including a does not contain a CRSF header when a user is resetting their password.
					</p>
         </td>
      </tr>
      <tr>
         <td>Patch 9<br/>01011604         </td>
         <td>RDST-17891         </td>
         <td>
            <p><strong>Issue:</strong> Previously, automatic sync on Standard Cluster was not updating across other nodes when deleting login restriction policy rules.<br/></p>
            <p><strong>Resolution:</strong> Now, the automatic sync on login restriction rules works correctly.
					</p>
         </td>
      </tr>
      <tr>
         <td>Patch 9<br/>01011171         </td>
         <td>RDST-17889         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the <code>LoginPolicy_BusinessUnit</code>, <code>LoginRestrictionPolicy</code> and <code>LoginRestrictionRule</code> tables were not included into the <code>sync_tables.conf</code> file.<br/></p>
            <p><strong>Resolution:</strong> Now, the <code>LoginPolicy_BusinessUnit</code>, <code>LoginRestrictionPolicy</code> and <code>LoginRestrictionRule</code> tables are included into the <code>sync_tables.conf</code> file.
					</p>
         </td>
      </tr>
      <tr>
         <td>Patch 9<br/>00998825         </td>
         <td>RDST-17386         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the Business Unit property "Allow Login Restriction Policy modifying" was not included during account export.<br/></p>
            <p><strong>Resolution:</strong> Now, this property is included during a Business Unit export and also properly imported during import.
					</p>
         </td>
      </tr>
      <tr>
         <td>Patch 9<br/>01006925         </td>
         <td>RDST-18150

         </td>
         <td>
            <p><strong>Issue:</strong> Previously, processing cycles for Pluggable Transfer Sites were not linked.
						<br/></p>
            <p><strong>Resolution:</strong> Now, processing cycles for Pluggable Transfer Sites are linked.
					</p>
         </td>
      </tr>
      <tr>
         <td>Patch 9<br/>00991762         </td>
         <td>RDST-18146         </td>
         <td>
            <p><strong>Issue:</strong> Previously, when a user was using a certificate for authentication, the account page did not display settings and information about failed or successful login attempts.
						<br/></p>
            <p><strong>Resolution:</strong> Now, the account page displays information and settings for failed and successful login attempts, regardless of the user authentication type.
					</p>
         </td>
      </tr>
      <tr>
         <td colspan="3"><strong>SecureTransport 5.4 Patch 8</strong>
         </td>
      </tr>
      <tr>
         <td>00985610<br/>00990434         </td>
         <td>RDST-18139         </td>
         <td>
            <p><strong>Issue:</strong> Previously, when email is sent with attachment file with selected option "Send attachment link only", when clicking the download link in the email we get an HTTP 500 error.
						<br/></p>
            <p><strong>Resolution:</strong> Now, download link in the email works successfully.
					</p>
         </td>
      </tr>
      <tr>
         <td> 00997338         </td>
         <td>RDST-17410         </td>
         <td>
            <p><strong>Issue:</strong> Previously, administrators with "Read Only" rights for a specific business unit could not view the certificates of a user belonging to that business unit using RESTful service.
					<br/></p>
            <p><strong>Resolution:</strong> Now, administrators with "Read Only" rights for a specific business unit can successfully list the certificates of a user belonging to that business unit using RESTful service.</p>
         </td>
      </tr>
      <tr>
         <td>00997151         </td>
         <td>RDST-17413         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SecureTransport did not check list of recent passwords when updating administrator password using RESTful service.
						<br/></p>
            <p><strong>Resolution:</strong> Now, SecureTransport checks list of recent passwords during administrator password update.
					</p>
         </td>
      </tr>
      <tr>
         <td>01003185         </td>
         <td>RDST-17411         </td>
         <td>
            <p><strong>Issue:</strong> Previously, Transfer Site Owner Not Reported to Sentinel in case of Send to partner step execution.<br/></p>
            <p><strong>Resolution:</strong> Now, Transfer Site Owner is reported to Sentinel in the RECEIVERID attribute.
					</p>
         </td>
      </tr>
      <tr>
         <td colspan="3">
            <p><b>SecureTransport 5.4 Patch 7</b>
</p>
         </td>
      </tr>
      <tr>
         <td>00989029<br/>00990463         </td>
         <td>RDST-17074					         </td>
         <td>
            <p><strong>Issue:</strong> Previously, in rare occasions due to concurrency issue Folder Monitor downloads was failing with an error for creating destination directory.<br/></p>
            <p><strong>Resolution:</strong> Now, folder monitor downloads do not fail in the above described case.
					</p>
         </td>
      </tr>
      <tr>
         <td>00997148         </td>
         <td>RDST-17072         </td>
         <td>
            <p><strong>Issue:</strong> Previously, administrator's failed login over basic authentication using REST API was not handled correctly.<br/></p>
            <p><strong>Resolution:</strong> Now, administrator's failed login attempts over basic authentication using REST API is handled correctly.
					</p>
         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>00980563         </td>
         <td>RDST-17075         </td>
         <td>
            <p><strong>Issue:</strong> Previously, some of the administrators could not change their passwords using REST API.<br/></p>
            <p><strong>Resolution:</strong> Now, administrators with Change Password rights are able to change their passwords. 
				</p>
         </td>
      </tr>
      <tr>
         <td colspan="3">
            <p><b>SecureTransport 5.4 Patch 6</b>
</p>
         </td>
      </tr>
      <tr>
         <td>Patch 6<br/>00999197         </td>
         <td>RDST-17946         </td>
         <td>
            <p><strong>Issue:</strong> Previously, migration of route step statuses to Oracle DB was failing.<br/></p>
            <p><strong>Resolution:</strong> Now, migration of route step statuses to Oracle DB processes successfully.
					</p>
         </td>
      </tr>
      <tr>
         <td>Patch 6<br/>00975445
					         </td>
         <td>RDST-18135
					         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SecureTransport was using Oracle ojdbc6 (11.2.0.1.0)/ ojdbc7 (12.1.0.2), MySQL (5.1.35) and MSSQL (4.2) drivers.<br/></p>
            <p><strong>Resolution:</strong> Now, SecureTransport is using Oracle ojdbc8 (12.2.0.1), MySQL (5.1.46) and MSSQL (4.2.8112.200) drivers. 
					</p>
         </td>
      </tr>
      <tr>
         <td>Patch 6<br/>00974591         </td>
         <td>RDST-16667         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the <code>APPEND</code> command in FTP protocol was not working as expected.<br/></p>
            <p><strong>Resolution:</strong> Now, <code>APPEND</code> command will append data to the end of a file on the remote host. If the file does not exist, SecureTransport	 will create it.
					</p>
         </td>
      </tr>
      <tr>
         <td colspan="3">
            <p><b>SecureTransport 5.4 Patch 5</b>
</p>
         </td>
      </tr>
      <tr>
         <td>00991915         </td>
         <td>RDST-18121         </td>
         <td>
            <p><strong>Issue:</strong> Previously, when executing a publish to account step, transfers were having different core IDs. <br/></p>
            <p><strong>Resolution:</strong> Now, when executing a publish to account step, transfers have the same core IDs.
				</p>
         </td>
      </tr>
      <tr>
         <td colspan="3">
            <p><b>SecureTransport 5.4 Patch 4</b>
</p>
         </td>
      </tr>
      <tr>
         <td>00975445         </td>
         <td>RDST-15151         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SecureTransport was vulnerable to CVE-2017-15095, CVE-2017-17485, CVE-2018-5968 and CVE-2018-7489 due to the outdated 2.8.9 version of FasterXML/ jackson-databind.<br/></p>
            <p><strong>Resolution:</strong> Now, FasterXML/jackson-databind version is updated to 2.9.5 which contains the latest security fixes.
					</p>
         </td>
      </tr>
      <tr>
         <td>00982325         </td>
         <td>RDST-16375         </td>
         <td>
            <p><strong>Issue:</strong> Previously, login restrictions on key authentication over SSH were checked twice, causing a thread lock on the second check of the session counter.<br/></p>
            <p><strong>Resolution:</strong> Now, as expected, login restrictions on key authentication over SSH are checked only once.
					</p>
         </td>
      </tr>
      <tr>
         <td>00975445         </td>
         <td>RDST-15178         </td>
         <td>
            <p><strong>Issue:</strong> Previously, private keys were saved on the file system using vulnerable <code>3DES</code> encryption.
						<br/></p>
            <p><strong>Resolution:</strong> Now, this encryption is changed to <code>AES-128</code>.<br/></p>
            <p><b>Note:</b> Internal CA should be regenerated/reimported after patch installation in order to change the file encryption algorithm.
						<br/>When the patch is uninstalled, Internal CA should be regenerated/reimported again in order to change the file encryption algorithm to <code>3DES</code>.
					</p>
         </td>
      </tr>
      <tr>
         <td>00980563         </td>
         <td>RDST-15917         </td>
         <td>
            <p><strong>Issue:</strong> Previously, an administrator could not change their own account password using the REST API.
						<br/></p>
            <p><strong>Resolution:</strong> Now, administrators may change their own settings, but cannot delete their own accounts.</p>
         </td>
      </tr>
      <tr>
         <td>00982044<br/>00984018         </td>
         <td>RDST-18114         </td>
         <td>
            <p><strong>Issue:</strong> Previously, it was not possible to search for SecureTransport accounts using the Internet Explorer browser.
						<br/></p>
            <p><strong>Resolution:</strong> Now, it is possible to search for SecureTransport accounts using the Internet Explorer browser.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>00959602</p>
            <p>00988009</p>
            <p>00975445</p>
            <p>00974783</p>
         </td>
         <td>
            <p>RDST-17506</p>
         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the SecureTransport Administration Tool was vulnerable to CVE-2015-9251 and CVE-2012-6708 due to an outdated version of jQuery 1.7.
						</p>
            <ul>
               <li>The SecureTransport Administration Tool was using an outdated version of Angular 1.3.4 which has many known vulnerabilities, including arbitrary code execution and multiple XSS paths.               </li>
               <li>Swagger-UI version was 2.2.10-1 containing outdated version of jQuery 1.7.               </li>
            </ul>
            <p><strong>Resolution:</strong> Now, jQuery version is updated to 3.3.1 and Angular version to 1.7.2 both containing the latest security fixes. The Swagger-UI version is updated to 3.17.1.
					</p>
         </td>
      </tr>
      <tr>
         <td colspan="3">
            <p><b>SecureTransport 5.4 Patch 3</b>
</p>
         </td>
      </tr>
      <tr>
         <td>00987871         </td>
         <td>RDST-15635         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SSH server-initiated transfers may fail because absolute path is not used if "<em>Upload Folder</em>" is left empty into transfer site settings.<br/></p>
            <p><strong>Resolution:</strong> Now, in this case transfers are successful and absolute path is used.</p>
         </td>
      </tr>
      <tr>
         <td>00972567<br/>00987759<br/>00984292<br/>00987914<br/>00987918         </td>
         <td>RDST-15585         </td>
         <td>
            <p><strong>Issue:</strong> Previously, setting file attributes during SFTP server-initiated push transfer is set after the transfer is completed.<br/></p>
            <p><strong>Resolution:</strong> Now, new configuration option <code>Ssh.UpdateFilePermissionsWithChmodCommand</code> is added. When <code>Ssh.UpdateFilePermissionsWithChmodCommand</code> is set to <code>true</code>, the file permissions, specified in SSH transfer site configuration are set after transfer end with chmod command. When <code>Ssh.UpdateFilePermissionsWithChmodCommand</code> is set to <code>false</code>, the file handler is opened with specified permissions. The default value is <code>true</code>.</p>
         </td>
      </tr>
      <tr>
         <td colspan="3">
            <p><b>SecureTransport 5.4 Patch 2</b>
</p>
         </td>
      </tr>
      <tr>
         <td>Patch 2<br/>00976582         </td>
         <td>RDST-15667         </td>
         <td>
            <p><strong>Issue:</strong> Previously, transfers history entries in ST Web Client were stored always in browser localStorage.
							<br/></p>
            <p><strong>Resolution:</strong> Now, transfers history entries are stored in sessionStorage when "<em>Allow this account to submit transfers using the Transfers RESTful API</em>" option is enabled for the user account.
							<br/></p>
            <p><strong>Note:</strong> When the above option is disabled, ST Web Client uses localStorage as before.
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 2<br/>00976582<br/>00983207         </td>
         <td>RDST-14794<br/>RDST-15137         </td>
         <td>
            <p><strong>Issue:</strong> Previously, some error pages in ST Web Client were vulnerable to Reflected XSS attacks.
							<br/></p>
            <p><strong>Resolution:</strong> Now, SecureTransport successfully processes all data when importing a private SSH key and exporting works as expected. 
						</p>
         </td>
      </tr>
      <tr>
         <td>Patch 2<br/>00955993         </td>
         <td>RDST-15634         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SecureTransport was not processing all data when importing and then exporting a private SSH key.
								<br/></p>
            <p><strong>Resolution:</strong> Now, SecureTransport successfully processes all data when importing a private SSH key.
							</p>
         </td>
      </tr>
      <tr>
         <td>Patch 2<br/>00959376         </td>
         <td>RDST-15877         </td>
         <td>
            <p><strong>Issue:</strong> Previously, PeSIT encoding Transfer Mode was not preserved with Advanced Routing even though the was used with the "Store And Forward Mode".
								<br/></p>
            <p><strong>Resolution:</strong> Now, encoding in PeSIT transfers is preserved in the same way as Record Format and Record Length and works as expected in Advanced Routing.
							</p>
         </td>
      </tr>
      <tr>
         <td>Patch 2<br/>00953560         </td>
         <td>RDST-15878         </td>
         <td>
            <p><strong>Issue:</strong> Previously, there was a problem when the <code>org.quartz.dataSource.DS.testOnBorrow</code> property was set to <code>true</code> in <code>FDH/conf/scheduler.properties</code>.
								<br/></p>
            <p><strong>Resolution:</strong> Now, this problem is fixed and SecureTransport works as expected with property <code>org.quartz.dataSource.DS.testOnBorrow=true</code>.
							</p>
         </td>
      </tr>
      <tr>
         <td colspan="3">
            <p><b>SecureTransport 5.4 Patch 1</b>
</p>
         </td>
      </tr>
      <tr>
         <td>Patch 1 <br/>00959203         </td>
         <td>RDST-14459         </td>
         <td>
            <p><strong>Issue:</strong> Previously, Swagger UI (2.1.4) was vulnerable to CVE 2016-5682.
								<br/></p>
            <p><strong>Resolution:</strong> Now, Swagger UI version is updated to 2.2.10-1.
							</p>
         </td>
      </tr>
   </tbody>
</table>

[Back to Top](#)

------------------------------------------------------------------------

### <span id="Addition"></span>Additional fixes

The following table contains additional fixes, which are not part of patches.

<table cellspacing="0">
   <colgroup>      
   <col/>
   <col/>
   <col/>
   </colgroup>
   <thead>
      <tr>
         <th>Case ID</th>
         <th>Internal ID</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p>00812422</p>
         </td>
         <td>
            <p>RDST-464</p>
         </td>
         <td>
            <p><strong>Issue:</strong> Previously, on SecureTransport with MySQL running on Linux, an error was incorrectly shown in the Server Log on successful administrator login using a client certificate when the certificate was specified via the <strong>issuer file</strong> option (<strong>Administrator Login options &gt; Client Certificate Settings&gt; Accept certificates issued by&gt; issuer file</strong>).</p>
            <p><strong>Resolution:</strong> Now, when a valid location is specified in the <strong>issuer file</strong> option and the administrator successfully logs in using a certificate, the server log does not show an error.</p>
         </td>
      </tr>
      <tr>
         <td>none         </td>
         <td>
            <p>RDST-480</p>
         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SecureTransport advertised UTF-8 in its FEAT response but the feature was not working.</p>
            <p><strong>Resolution:</strong> Now, an appropriate response code is returned to the OPTS UTF-8 command.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>00819846</p>
         </td>
         <td>
            <p>RDST-485</p>
         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the error message for denied CWD FTP command was misleading.</p>
            <p><strong>Resolution:</strong> Now, SecureTransport responds with '550: Permission denied' in all cases of restricted access.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>00826347<br/>01154848</p>
         </td>
         <td>
            <p>RDST-518</p>
         </td>
         <td>
            <p><strong>Issue:</strong> Previously, overwriting a decrypted file did not trigger repository encryption.</p>
            <p><strong>Resolution:</strong> Now, all newly uploaded files get encrypted. </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>00904261<br/>00861418</p>
         </td>
         <td>
            <p>RDST-1829</p>
         </td>
         <td>
            <p><strong>Issue:</strong> Previously, a few end-user REST API resources and the ST Web Client (legacy skins) pages contained internal information.</p>
            <p><strong>Resolution:</strong> Now, the ST Web Client legacy skins and the REST API do not reveal any additional data that is considered sensitive. </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>00874075</p>
         </td>
         <td>
            <p>RDST-3121</p>
         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the Monitor Server was logging 'Current ST internal session count' message several times per minute.</p>
            <p><strong>Resolution:</strong> Now, the logging is fixed.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>00878253<br/>00876266<br/>00878255</p>
         </td>
         <td>
            <p>RDST-3703</p>
         </td>
         <td>
            <p><strong>Issue:</strong> Previously, when publishing a large file to an account, the recipient was able to download or delete the file before it was fully transferred.</p>
            <p><strong>Resolution:</strong> Now, the file is not available for download or deletion until it is completely received.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>00881006</p>
         </td>
         <td>
            <p>RDST-3852</p>
         </td>
         <td>
            <p><strong>Issue:</strong> Previously, on Linux platforms, errors were shown in the File Tracking when the AdHoc functionality was used with the following upload restrictions: users were prohibited from uploading to the root (/) directory and permitted to upload in the root sub-folders (//*).</p>
            <p><strong>Resolution:</strong> Now, when the package delivery is successful, the upload restrictions does not cause errors in File Tracking.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>00896905</p>
         </td>
         <td>
            <p>RDST-6615</p>
         </td>
         <td>
            <p><strong>Issue:</strong> Previously, when downloading a file from the SecureTransport Legacy Client, the <code>Content-Type</code> HTTP response header was always set to <em>application/octet-stream</em> regardless of the download mode.</p>
            <p><strong>Resolution:</strong> Now, the <code>Content-Type</code> HTTP response header is populated based on the transfer mode.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>00911296, 00966063</p>
         </td>
         <td>
            <p>RDST-8722</p>
         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the maximum number of parallel transfers limit was disregarded when server-initiated pulls were triggered by using the <b>Retrieve Files Now</b> button under the subscription's settings.</p>
            <p><strong>Resolution:</strong> Now, in the specified scenario, the maximum number of parallel transfers limit is applied.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>00914346</p>
         </td>
         <td>
            <p>RDST-9018</p>
         </td>
         <td>
            <p><strong>Issue:</strong> Previously, due to an extra space around the delimiter in the list of the allowed HMAC algorithms in the <code>Ssh.SIT.AllowedMacs</code> configuration option, only the first HMAC in the list was advertised during the KEX.</p>
            <p><strong>Resolution:</strong> Now, the formatting of the list is corrected and the configured HMAC algorithms are advertised during the KEX.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>00924216</p>
         </td>
         <td>
            <p>RDST-10227</p>
         </td>
         <td>
            <p><strong>Issue:</strong> Previously, <code>hmac-sha2-256</code> was missing from the default list of allowed HMAC algorithms in the <code>Ssh.AllowedMacs</code> and <code>Ssh.SIT.AllowedMacs</code> configuration options.</p>
            <p><strong>Resolution:</strong> Now, <code>hmac-sha2-256</code> is added to the default configuration in the <code>Ssh.AllowedMacs</code> and <code>Ssh.SIT.AllowedMacs</code> options.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>00922462</p>
         </td>
         <td>
            <p>RDST-10464</p>
         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the SSH service port was resetting to its default (22) after installing a new node in an Enterprise Cluster.</p>
            <p><strong>Resolution:</strong> Now, after installing a new cluster node, the SSH service port number assigned to the first server is preserved.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>00928239</p>
         </td>
         <td>
            <p>RDST-10923</p>
         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the silent installation of an Enterprise Cluster node failed when performed after removing an existing DMZ node using the Administration Tool. That was because the auto-generated name for the new node was not unique.</p>
            <p><strong>Resolution:</strong> Now, SecureTransport automatically generates unique names for the new nodes.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>00937905</p>
         </td>
         <td>
            <p>RDST-11441</p>
         </td>
         <td>
            <p><strong>Issue:</strong> Previously, an SSH user session did not get terminated after disabling or locking the account.</p>
            <p><strong>Resolution:</strong> Now, the user session is immediately killed once the account is disabled.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>00946645</p>
         </td>
         <td>
            <p>RDST-12609</p>
         </td>
         <td>
            <p><strong>Issue:</strong> Previously, for accounts in a business unit, the applications in the <strong>Subscribe to</strong> drop-down list were ordered by creation date.</p>
            <p><strong>Resolution:</strong> Now, the application list is sorted alphanumerically regardless if the account belongs to a business unit or not.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>00959227</p>
         </td>
         <td>
            <p>RDST-13581</p>
         </td>
         <td>
            <p><strong>Issue:</strong> Previously, when a Folder Monitor transfer site was used to pull files for Basic Application, all transfer sites to which files were automatically sent renamed the files according to the "Receive File As" value set in Folder Monitor.</p>
            <p><strong>Resolution:</strong> Now, in the specified scenario, all transfer sites rename the file according to their "Send File As" value.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>00960829</p>
         </td>
         <td>
            <p>RDST-13602</p>
         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the installation of SecureTransport with Microsoft SQL Server was failing if the database password contained a dollar sign ($).<br/></p>
            <p><strong>Resolution:</strong> Now, the requirements for database passwords are documented in the <i>SecureTransport Installation Guide</i>.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>00971242, 00964769</p>
         </td>
         <td>
            <p>RDST-13823</p>
         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the SSH certificate authentication option was reset to its default value "Disabled" after installing a new node using the "Using existing schema" option set to <em>true</em>.</p>
            <p><strong>Resolution:</strong> Now, after installing a new cluster node, the value of the SSH certificate authentication option remains unchanged.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>00981905, 00969586</p>
         </td>
         <td>
            <p>RDST-14258</p>
         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the number of the accounts was decreasing after a password change in the Administration Tool.<br/></p>
            <p><strong>Resolution:</strong> Now, number of the accounts remains unchanged when an account password is changed.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>00973136</p>
         </td>
         <td>
            <p>RDST-14404</p>
         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the Setup menu was unavailable after navigating to <strong>Operations &gt; Support Tool</strong> in the Administration Tool.<br/></p>
            <p><strong>Resolution:</strong> Now, the Setup menu is available after navigating to <strong>Operations &gt; Support Tool</strong> in the Administration Tool.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>00970160</p>
         </td>
         <td>
            <p>RDST-14494</p>
         </td>
         <td>
            <p><strong>Issue:</strong> Previously, with the "Axway Box and Stripe in Blue" and "Jelly Ball 9" HTML templates, a click on the download link of a file did not work as expected.</p>
            <p><strong>Resolution:</strong> Now, a click on the download link of a file on either mentioned template works as expected.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>00975626, 01143857, 01044162</p>
         </td>
         <td>
            <p>RDST-14752</p>
         </td>
         <td>
            <p><strong>Issue:</strong> Previously, when pulling files from SMB and pushing to a SSH server, SecureTransport was stripping the .pgp extension while preserving the file encryption.</p>
            <p><strong>Resolution:</strong> Now, in the specified scenario, SecureTransport doesn't strip the .pgp extension from the filename.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>00978293</p>
         </td>
         <td>
            <p>RDST-14913</p>
         </td>
         <td>
            <p><strong>Issue:</strong> Previously, it was not possible to disable the TRACE method for HTTPD.</p>
            <p><strong>Resolution:</strong> Now, the SecureTransport administrators can disable the TRACE method for the HTTPD.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>00975783</p>
         </td>
         <td>
            <p>RDST-14983</p>
         </td>
         <td>
            <p><strong>Issue:</strong> Previously, server-initiated transfers over FTP using the <code>'${stenv.target}(+1)'</code> expression was incorrectly evaluated at first. A resubmission attempt was correctly processed.</p>
            <p><strong>Resolution:</strong> Now, the file transfer is correctly completed in the described scenario.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>00981541</p>
         </td>
         <td>
            <p>RDST-15052</p>
         </td>
         <td>
            <p><strong>Issue:</strong> Previously, an error was shown on attempt to enable a user to log in to SecureTransport Server if the account was created with the login option disabled.<br/></p>
            <p><strong>Resolution:</strong> Now, the <strong>Allow this account to log in to SecureTransport Server</strong> setting can be changed any time for any user.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>00980509</p>
         </td>
         <td>
            <p>RDST-15071</p>
         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the SecureTransport Administrator's Guide was providing incomplete instructions for exporting and exporting server configuration.<br/></p>
            <p><strong>Resolution:</strong> Now, the SecureTransport Administrator's Guide provides more detailed information about server configuration export and import.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>00980115</p>
         </td>
         <td>
            <p>RDST-15493</p>
         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SecureTransport did not validate the classes used in the selectorStrategy configurations.</p>
            <p><strong>Resolution:</strong> Now, if an erroneous value is used for one of the following options <code>Dmz.Edge.selectorStrategy</code>, <code>Dmz.Proxy.Address.selectorStrategy</code>, or <code>Dmz.Zone.selectorStrategy</code>, the option is set to default and the transfer is successful. In the Server log, a warning message is displayed, stating that the value for the option is erroneous and that the default one will be used.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>00990442</p>
         </td>
         <td>
            <p>RDST-15712</p>
         </td>
         <td>
            <p><strong>Issue:</strong> Previously, some of the examples in the "LDAP-related expression language and variable" topic were not clear.</p>
            <p><strong>Resolution:</strong> Now, the examples are clarified.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>00976754</p>
         </td>
         <td>
            <p>RDST-15799</p>
         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the <code>TRANSFER_STATUS_ID</code> and <code>TRANSFER_STATUS_START_TIME</code> variables were not populated in the received email notifications for FTP(S) and SFTP inbound transfers.</p>
            <p><strong>Resolution:</strong> Now, <code>TRANSFER_STATUS_ID</code> and <code>TRANSFER_STATUS_START_TIME</code> are correctly evaluated and populated in the inbound transfer email notifications regardless of the protocol.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>00994853</p>
         </td>
         <td>
            <p>RDST-15996</p>
         </td>
         <td>
            <p><strong>Issue:</strong> Previously, some error messages were revealing the web server name and version.<br/></p>
            <p><strong>Resolution:</strong> Now, generic error messages are displayed to users.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>01031515<br/>01014948<br/>01001534<br/>01006211<br/>00998200</p>
         </td>
         <td>
            <p>RDST-16564</p>
         </td>
         <td>
            <p><strong>Issue:</strong> Previously, The HTTP <code>OPTIONS</code> method was <em>enabled</em> in the SecureTransport Administration Tool.</p>
            <p><strong>Resolution:</strong> Now, the HTTP <code>OPTIONS</code> method is <em>disabled</em> in the SecureTransport Administration Tool.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>00990458</p>
         </td>
         <td>
            <p>RDST-16966</p>
         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the SSH service was failing to start when the Ssh.Host server configuration parameter was not set (default) and IPv6 was disabled.</p>
            <p><strong>Resolution:</strong> Now, when the <code>Ssh.Host</code> server configuration parameter is not set, the server starts listening on all IPv4 addresses.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>01003007</p>
         </td>
         <td>
            <p>RDST-16996</p>
         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the output of the <code>dir</code> command, executed manually on FTP connection via CLI, contained an extra blank line.</p>
            <p><strong>Resolution:</strong> Now, the blank line in the output was removed.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>01006779</p>
         </td>
         <td>
            <p>RDST-17069, RDST-17070</p>
         </td>
         <td>
            <p><strong>Issue:</strong> Previously, there was no limitation when adding Additional attributes via the REST API. </p>
            <p><strong>Resolution:</strong>Now, the key name property should start with "userVars." for all API versions except for API 2.0.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>00976582</p>
         </td>
         <td>
            <p>RDST-17224</p>
         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the internal server IP address was displayed in the Transfer-Reference response header on a request to rename a file.</p>
            <p><strong>Resolution:</strong> Now, the Transfer-Reference header does not contain the IP of the server.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>01007816</p>
         </td>
         <td>
            <p>RDST-17422</p>
         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the Monitor service was unnecessarily checking the external databases.</p>
            <p><strong>Resolution:</strong> Now, the Monitor service checks only the SecureTransport services and restart them if they are not running.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>00998718, 01001892</p>
         </td>
         <td>
            <p>RDST-17454</p>
         </td>
         <td>
            <p><strong>Issue:</strong> Previously, simultaneous logout of two user accounts, members the same User Class, were logged in one line in the Server log, while they should be separate lines.</p>
            <p><strong>Resolution:</strong> Now, SecureTransport logs separately the user account actions in the described case.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>01008574</p>
         </td>
         <td>
            <p>RDST-17493</p>
         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the Swagger Transfers resource listed "amazonS3" as a valid value for protocol.</p>
            <p><strong>Resolution:</strong> Now, the Swagger documentation is updated. The valid values for the protocol of the site are "as2", "ftp", "http","ssh", "pesit", "folder", "adhoc" as well as the protocols added with transfer site plugins.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>01020030</p>
         </td>
         <td>
            <p>RDST-18445</p>
         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the <code>MANIFEST.MF</code> file in the Custom Authorization plugin for SecureTransport was incorrect.</p>
            <p><strong>Resolution:</strong> Now, the SDK contains the correct <code>MANIFEST.MF</code> file.</p>
         </td>
      </tr>
      <tr>
         <td>01098223         </td>
         <td>RDST-30682         </td>
         <td>
            <p><strong>Issue:</strong> Previously, in some cases, SecureTransport was performing outbound file transfers without applying repository decryption which prevented files from being usable on the partner side.</p>
            <p><strong>Resolution:</strong> Now, SecureTransport correctly applies repository decryption to outbound file transfers.</p>
         </td>
      </tr>
      <tr>
         <td>01141121         </td>
         <td>RDST-30683         </td>
         <td>
            <p><strong>Issue:</strong> Previously, Oracle Coherence was started after completion of manual database synchronization. </p>
            <p><strong>Resolution:</strong> Now, this problem does not occur on completion of manual database synchronization.</p>
         </td>
      </tr>
      <tr>
         <td>01120021         </td>
         <td>RDST-30161         </td>
         <td>
            <p><strong>Issue:</strong> Previously, when the <code>PASV</code> command was disabled on the server, the transfers initiated by SecureTransport, were failing as it did not fall back to EPSV.</p>
            <p><strong>Resolution:</strong> Now, when the <code>PASV</code> command is disabled on the server, SecureTransport falls back to <code>EPSV</code>.</p>
         </td>
      </tr>
      <tr>
         <td>01139926         </td>
         <td>RDST-28827         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the Transaction Manager (TM) log did not have records when the TM was started or stopped using the respective <code>start_tm</code> and <code>stop_tm</code> scripts.</p>
            <p><strong>Resolution:</strong> Now, the TM stores records in the respective log for such events.</p>
         </td>
      </tr>
      <tr>
         <td>01119729         </td>
         <td>RDST-27571         </td>
         <td>
            <p><strong>Issue:</strong> Previously, SSH key import was unsuccessful when following the example described in the administrator's REST API Swagger documentation.</p>
            <p><strong>Resolution:</strong> Now, the behavior is fixed and SSH import occurs successfully in the case described.</p>
         </td>
      </tr>
      <tr>
         <td>01124883         </td>
         <td>RDST-27501         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the SecureTransport Installation Guide contained insufficient info regarding the Axway Installer.</p>
            <p><strong>Resolution:</strong> Now, the SecureTransport Installation Guide is updated with the required information.</p>
         </td>
      </tr>
      <tr>
         <td>01118243         </td>
         <td>RDST-26899         </td>
         <td>
            <p><strong>Issue:</strong> Previously, after a new member of an Enterprise Cluster was added, the Client Certificate Settings of the SSH service was reverting to its default value: Disabled.</p>
            <p><strong>Resolution:</strong> Now, this behavior is fixed and the Client Certificate Settings of the SSH service does not revert to its default value.</p>
         </td>
      </tr>
      <tr>
         <td>01101198         </td>
         <td>RDST-25331         </td>
         <td>
            <p><strong>Issue:</strong> Previously, accounts belonging to a Business Unit (BU) could not be edited via the administrator's REST API when the BU settings do not allow HTML Template modification of accounts assigned to it.</p>
            <p><strong>Resolution:</strong> Now, the administrator's REST API is fixed to successfully edit accounts as expected.</p>
         </td>
      </tr>
      <tr>
         <td>01088083         </td>
         <td>RDST-24483         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the SecureTransport Administrator's Guide contained insufficient info regarding the configuration option to maintain link data when Sentinel or Decision Insight is disabled.</p>
            <p><strong>Resolution:</strong> Now, the SecureTransport Administrator's Guide is updated with the needed info.</p>
         </td>
      </tr>
      <tr>
         <td>01055232<br/>01074861<br/>01069903         </td>
         <td>RDST-23411         </td>
         <td>
            <p><strong>Issue:</strong> Previously, re-imaging of existing VMs on the Axway Appliance platform was unsuccessful.</p>
            <p><strong>Resolution:</strong> Now, the introduction of SecureTransport 5.5 Virtual Appliance fixes the described issue.</p>
         </td>
      </tr>
      <tr>
         <td>01065674         </td>
         <td>RDST-22399         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the SecureTransport Administrator's Guide did not contain info that the <code>Title</code> value in the 'Private' Network Zone could not be changed from the hardcoded 'Host'.</p>
            <p><strong>Resolution:</strong> Now, the SecureTransport Administrator's Guide is updated with the needed info.</p>
         </td>
      </tr>
      <tr>
         <td>01064283         </td>
         <td>RDST-22319         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the administrator's REST API was not returning the timestamp value for the last modification of a SecureTransport account.</p>
            <p><strong>Resolution:</strong> Now, four new properties (Account Created, Last Modified, Last Login) are exposed for User Accounts, Unlicensed Users and Service Accounts. Additionally, two new properties (Account Created and Last Modified) are exposed for Account templates.</p>
         </td>
      </tr>
      <tr>
         <td>01049465         </td>
         <td>RDST-22131         </td>
         <td>
            <p><strong>Issue:</strong> Previously, when the <code>$DISPLAY</code> parameter was set and the underlying *nix OS was missing the <code>libXext.so.6</code> library, SecureTransport was failing to operate normally.</p>
            <p><strong>Resolution:</strong> Now, the SecureTransport Installation Guide is updated with a note regarding needed info.</p>
         </td>
      </tr>
      <tr>
         <td>01015970         </td>
         <td>RDST-19886         </td>
         <td>
            <p><strong>Issue:</strong> Previously, attempts to pull a file using any connector (S3, SMB, Azure) with preserved folder structure were unsuccessful when a shared folder application was used as a subscription.</p>
            <p><strong>Resolution:</strong> Now the issue is fixed and pulls of files are successfully performed in the described use case.</p>
         </td>
      </tr>
      <tr>
         <td>01139926         </td>
         <td>RDST-28824         </td>
         <td>
            <p><strong>Issue:</strong> Previously, the Server Log, tm.stdout.log, and xferlog used different date formats.</p>
            <p><strong>Resolution:</strong> Now, the default date format in all mentioned logs is set to <code>yyyy-MM-dd HH:mm:ss,SSS</code>, and can be manually changed in the log4j files.</p>
         </td>
      </tr>
      <tr>
         <td>01083411         </td>
         <td>RDST-24174         </td>
         <td>
            <p><strong>Issue:</strong> Previously, after upgrade to SecureTransport 5.4, error messages related to transfer status ID were logged on successful pull transfers via an Amazon S3 transfer site.</p>
            <p><strong>Resolution:</strong> Now, the pull and push transfers via Amazon S3 Transfer Site are successful.</p>
         </td>
      </tr>
      <tr>
         <td>01057615         </td>
         <td>RDST-23652         </td>
         <td>
            <p><b>Issue:</b> Previously, after a patch was applied on SecureTransport 5.4, the <code>rotate</code> script stopped rotating the xferlog and cmdlog files.</p>
            <p><b>Resolution:</b> Now, the rotate script rotates the xferlog and cmdlog files.</p>
         </td>
      </tr>
      <tr>
         <td>01048470         </td>
         <td>RDST-21327         </td>
         <td>
            <p><b>Issue:</b> Previously, developer's comments and debug info were visible when accessing the SecureTransport Administration Tool. </p>
            <p><b>Resolution:</b> Now, the comments in loginRestrictionPolicies-controller.js are not visible.</p>
         </td>
      </tr>
      <tr>
         <td>01034416         </td>
         <td>RDST-21133         </td>
         <td>
            <p><b>Issue:</b> Previously, it was not possible the <code>${date("yyyyMMdd")}</code> variable to be used for setting the current date in the URL path to a Generic HTTP transfer site. </p>
            <p><b>Resolution:</b> Now, the <code>${date("yyyyMMdd")}</code> variable can be used for updating the current date in the URL path from the transfer site.</p>
         </td>
      </tr>
      <tr>
         <td>01025902         </td>
         <td>RDST-20288         </td>
         <td>
            <p><b>Issue:</b> Previously, streaming breakdown occurred when longer exceptions couldn't fit in the Trace Line column of the logging_event_exception table. </p>
            <p><b>Resolution:</b> Now, the issue is fixed and server logs with more than 2048 characters are stored in the serverlog-fallback.log file.</p>
         </td>
      </tr>
      <tr>
         <td>01035961         </td>
         <td>
            <p>RDST-19961</p>
            <p>RDST-19960</p>
            <p>RDST-19959</p>
            <p>RDST-19958</p>
         </td>
         <td>
            <p><b>Issue:</b> Previously, verbose information was found to be returned within the responses to PUT and POST requests to the <code>/fileops</code> resource.
						</p>
            <p><b>Resolution:</b> Now, responses to such requests contain generic messages.</p>
         </td>
      </tr>
      <tr>
         <td>01036256         </td>
         <td>RDST-19766         </td>
         <td>
            <p><b>Issue:</b> Previously, the description of the <code>EventQueue.maxRetryCount</code> server configuration option in SecureTransport Administration Tool was incomplete.</p>
            <p><b>Resolution:</b> Now, the description of the <code>EventQueue.maxRetryCount</code> server configuration option is updated.</p>
         </td>
      </tr>
      <tr>
         <td>01033257         </td>
         <td>RDST-19581         </td>
         <td><b>Issue:</b> Previously, the error messages on attempt to create an AS2 transfer site with a duplicated name via REST API was misleading.            <p><b>Resolution:</b> Now, such attempt fails with a proper error message.</p>         </td>
      </tr>
      <tr>
         <td>01029431         </td>
         <td>RDST-19227         </td>
         <td>
            <p><b>Issue:</b> Previously, when the sshd log was redirected to a flat file, there was a difference in the account information reported in the Server Log and the flat file.</p>
            <p><b>Resolution:</b> Now, there is no difference in the account information reported in the server log and the flat file.</p>
         </td>
      </tr>
      <tr>
         <td>01021994         </td>
         <td>RDST-19078         </td>
         <td>
            <p><b>Issue:</b> Previously, user activity over the HTTPS and FTP services related to folders was not recorded in the Server log.</p>
            <p><b>Resolution:</b> Now, records for Create, Rename and Delete folders are shown in the Server logs for the FTP and HTTPS services.</p>
         </td>
      </tr>
      <tr>
         <td>01025382         </td>
         <td>RDST-19002         </td>
         <td>
            <p><b>Issue:</b> Previously, for server-initiated pull transfers over FTP and SSH, the Remote folder field was not populated under File Tracking export and Transfer Status details.</p>
            <p><b>Resolution:</b> Now, in the specified case, the Remote Folder field is populated correctly. </p>
         </td>
      </tr>
   </tbody>
</table>

[Back to Top](#)

------------------------------------------------------------------------

## <span id="ST_Web_Client_general_recommendations"></span>ST Web Client general recommendations

For optimal performance of ST Web Client, the value of `readChunkSize` must be set to 262144 in `stwebclient.config.json`.

If the user does not want to be prompted to save their password, except for setting autocomplete to off on the login page, they must disable this feature from the browser's settings.

Autocomplete is disabled by default with out-of-the-box SecureTransport in the ST Web Client interface input fields.

[Back to Top](#)

------------------------------------------------------------------------

## <span id="Known_issues_and_limitations"></span>Known issues and limitations

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Case ID</th>
         <th>Internal ID</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>01040257<br/>01064486         </td>
         <td>RDST-20438<br/>RDST-11266<br/>RDST-2590         </td>
         <td>When the Transaction Manager (TM) on a given node (in Enterprise Cluster deployments) is restarted while processing one or more active file transfers, these file transfers are not automatically re-initiated after a TM restart. Instead, such a transfer would remain in "in Progress" state and the associated <code>'.m_inproc'</code> file will be orphaned on the file system, thus preventing the automatic resubmission of the given file.<br/>								As part of this, the following behavior is observed:
								            <ul>               <li>Failover functionality is not working when Transaction Manager is suspended during files transfer processing.               </li>               <li>File locking does not perform correctly in some cases.               </li>               <li>A permanent database failure on the primary SecureTransport node does not trigger a cluster failover and recovery in an Active/Active Standard Cluster.               </li>            </ul><br/><strong>Workaround solution:</strong> A SecureTransport administrator must remove manually the ‘.m_inproc’ leftover files, associated with the corresponding transfers.         </td>
      </tr>
      <tr>
         <td>none         </td>
         <td>RDST-17108         </td>
         <td>When a user in the ST Web Client creates a subfolder named "api" in their root folder, attempts to access a direct link or refresh a page within the "api" subfolder will result in URL redirection to the end-user Swagger API Documentation.         </td>
      </tr>
      <tr>
         <td>none         </td>
         <td>RDST-22139         </td>
         <td>PeSIT transfers from CFT fail if repository encryption is enabled and the transfer is paused and then resumed.         </td>
      </tr>
      <tr>
         <td>none         </td>
         <td>RDST-27698         </td>
         <td>Password policy cannot be configured for administrators on SecureTransport Edge.         </td>
      </tr>
      <tr>
         <td>none         </td>
         <td>RDST-31458         </td>
         <td>
            <p>SecureTransport cannot resubmit files which have been already resubmitted once in an outbound transfer, performed in an Advanced Routing "Send to partner" step.</p>
         </td>
      </tr>
      <tr>
         <td>none         </td>
         <td>RDST-31663         </td>
         <td>
            <p>In rare occasions, some intermittent <code>EOFException</code> errors are thrown during the Advanced Routing "Send to partner" step processing. This has no functional impact.</p>
         </td>
      </tr>
   </tbody>
</table>

[Back to Top](#)

------------------------------------------------------------------------

## <span id="Documentation"></span>Documentation

This section describes the related documentation.

### Related documentation

Go to the Axway Documentation Portal at <https://docs.axway.com/> to find all documentation for this product version.

SecureTransport 5.5 provides the following documentation:

-   *SecureTransport Administrator's Guide* – This guide provides descriptions and usage instructions to the SecureTransport Administrator's Tool for configuration, deployment and administration of SecureTransport Servers and Edges. Also available as the Administration Tool online help.
-   *SecureTransport Appliance Guide* – This guide provides the SecureTransport Appliance installation, configuration, and operation instructions.
-   *SecureTransport Containerized Deployment Guide* – This guide describes how to deploy SecureTransport as a Docker container.
-   *SecureTransport Developer's Guide* – This guide provides descriptions and usage instructions for implementing custom pluggable components in SecureTransport.
-   *SecureTransport Getting Started Guide* – This guide explains the initial setup and configuration of SecureTransport using the SecureTransport Administrator setup interface.
-   *SecureTransport Installation Guide* – This guide provides instructions how to install and set up SecureTransport.
-   <span cshid="sec" data-version="5.3.5">*SecureTransport Security Guide*</span> – This guide provides security information necessary for the secure operation of the SecureTransport product.
-   *ST Web Client Configuration Guide* – This guide describes how to configure and customize the ST Web Client user interface.
-   *ST Web Client User Guide* – This guide describes how to use the ST Web Client.
-   *SecureTransport on AWS Installation Guide* – This guide provides installation and setup information to deploy SecureTransport on AWS (Amazon Web Services).
-   *SecureTransport on Azure Installation Guide* – This guide provides installation and setup information to deploy SecureTransport on Microsoft Azure.
-   *Third Party Licenses* – This document lists the proprietary and open source licenses of third-party software that is included or used by SecureTransport.
-   *SecureTransport Release Notes* – (current document) – This document contains information about new features and enhancements, information received after the finalization of the rest of the documentation, and a list of known and fixed issues.

[Back to Top](#)

------------------------------------------------------------------------

## <span id="Support_services"></span>Support services

The Axway Global Support team provides worldwide 24 x 7 support for customers with active support agreements.  
Email <support@axway.com> or visit Axway Support at [https://support.axway.com](https://support.axway.com/).

------------------------------------------------------------------------

Copyright © 2020 Axway. All rights reserved
