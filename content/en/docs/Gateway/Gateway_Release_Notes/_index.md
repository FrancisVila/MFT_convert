{
    "title": "Axway Gateway 6.17.3 Release Notes/t/t",
    "linkTitle": "Gateway Release Notes",
    "weight": "20"
}------------------------------------------------------------------------

-   [New features and enhancements](#_New_features_and)
-   [Compatibility with other Axway products](#_Compatibility_with_other)
-   [Upgrade](#_Migration)
-   [Fixed problems](#_Fixed_problems)
-   [Limitations](#Limitations)
-   [Related
    documentation](#documentation)
-   <span lang="EN-US">[Support services](#support)</span>

<span id="New"></span><span id="_New_features_and"></span>

## <span lang="EN-US">New features and enhancements</span>

This document combines changes relating to versions 6.17.0 and 6.17.3.

### Security improvements

Several improvements have been introduced to increase the overall security of Gateway:

-   **Longer keys**: maximum length of certificates with RSA keys imported in Gateway is raised to 8192 bits (formerly 4096). PEM and DER formats are supported.
    -   Only RSA-based signature algorithms are supported. Two hash algorithms are available and can be associated with RSA: MD5 and SHA-1.
-   ****Audit support:**** Gateway stores the actions performed by users on the Gateway configuration (global and objects configuration) on a dedicated file, providing visibility of the changes done on the product. This functionality cannot be disabled**.**
-   **Payload integrity:**
    You can enable the payload integrity check to assure that payload haven’t changed between the moment is has been received by Gateway and further actions: routing to Integrator or routing to a third party. The protocols for which the signature is computed in Gateway, for incoming transfers are: SWIFTNet, PeSIT and JMS.
-   **Encrypted passwords**: the password used for authorizing operations through commands (command line utility, exists, scripts) when access management is enabled is now stored in encrypted form;
-   the passwords exported through `secbase `or `pelbase `commands are now encrypted;
-   **Certificate chain limit** : for the outgoing and incoming exchanges secured with TLS, the certificate chain limit has been increased from 16K to 64K; handshake message fragmentation is implemented as described on rfc5246. OpenSSL based implementations are not compatible with Gateway’s implementation.
-   **OpenSSL**: cryptographic operations are now relying on the latest OpenSSL version (1.0.2k)

### Other enhancements

-   **Native** support for **64-bit** architecture on AIX and Windows.  
    A tool is provided to handle the migration from any platform to the new 64-bit platforms.
-   **Multiple SwiftNet backup sites**: Gateway now allows up to 4 backup sites for each SWIFTNet remote site.
-   SWIFT: Compliance with **SWIFT CSP**
-   JMS: Logging now supported by Apache **Log4j 2**
-   **Upgrade to Perl version 5.24.0**  
    Perl version 5.24.0 is required to compile the Perl exits or to run the Perl scripts.
-   **Increased maximum length for PeSIT ‘file label‘ transfer parameter**  
    The limit for transfer parameter ‘file label’ has increased from 80 chars to 256 chars.
-   **New signature for transfer user exits ExitXfer\* (perl and C)  
    **To support passing custom user data in subsequent SSH exit calls and to differentiate between SSH and TLS context, the transfer exits ExitXfer\* (perl and C) have a new signature.  
-   No longer supported in this version:ETEBAC 3 Client & Bank and ETEBAC 5 Client & Bank; Infozip and infounzip tool.

<span id="_Compatibility_with_other"></span>

## <span lang="EN-US">Compatibility with other Axway products</span>

<span lang="EN-US">This version of Gateway is compatible with:</span>

-   Axway Secure Relay Router Agent 2.7.1
-   Axway Installer 4.10.0 SP1
-   Axway PassPort 4.6 SP12
-   Axway Sentinel 4.2.0 SP3
-   Axway Integrator 3.7.3 SP4

Use Axway Gateway Navigator 6.17.2 to
access the Gateway 6.17.2 server.

<span lang="EN-US"></span>

------------------------------------------------------------------------

<span id="mig"></span><span id="_Migration"></span>

## <span lang="EN-US">Upgrade</span>

Upgrade from 6.17.2 version is supported for this release. The upgrade procedure is described in the *[Upgrade guide](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm)*.

<span id="Fixed"></span><span id="_Fixed_problems"></span>

## <span lang="EN-US">Fixed problems</span>

For detailed information about fixed problems, refer to the `release_standalone.txt `file delivered with Gateway.

<span id="Limitations"></span>

## L<span lang="EN-US">imitations</span>

 

Known limitations from Axway Gateway V6.17.3:

-   \[Win64\] As Entrust Authority IPSec Negotiator Toolkit is not available any more, exitsecs\_entrust library is not delivered on win-x86-64 platform.
-   \[Win64\] High Availability feature is not available on win-x86-64 platform yet. It will be delivered in future SPs.

Known limitations from Axway Gateway V6.16.1:

-   **ECDSA in FIPS mode**  
    Due to a structure mistmatch in OpenSSL, ECDSA ciphers are disabled in FIPS mode
-   **ECDHE in FIPS mode (XSR Termination)**  
    For the moment, ECDHE ciphers will not work with XSR termination.
-   *On UNIX only:*  
    When transferring a file via SFTP, and you are using an ASCII application, if the newline convention set on the Site does not match the transferred file's newline convention, the p\_sftp process might enter an infinite loop.  
    It is recommended to use the correct line-ending convention when using ASCII applications with SFTP.  
    If the file that needs to be downloaded has the Windows newline convention, update the Remote Site's newline convention to Windows.  
    When the newline convention on the Site is not set, Gateway will use the system’s newline convention.

<!-- -->

-   **Number of Gateway objects**  
    The Gateway server cannot display more than 4000 objects (Sites, log messages, CGates, Models, and so on). This applies to the GUI and Command line.
-   **FIPS support on Windows OS**  
    FIPS support is not available in Gateway on Windows OS.
-   **SWIFTNet statistics limitation**  
    On transferring a small file through SWIFTNet when statistics are active, the information about `SwInt:SwiftRequestRef `and `SwInt:SwiftResponseRef `may not be present in the statistics file, due to the fact a FileEvent with the TransferStatus set as final state may be received before the `ExchangeFileResponse `primitive.
-   **Preserve the old behavior with the new Purge command**  
    To reinstate the old behavior, replace with .
-   **Behavior changes related to the new trace rotation mechanism**  
    The traces generated by third-party libraries (ex: SWIFTNet RA libraries that are required at runtime) are lost after the evolution regarding trace rotation and archiving.  
    For performance reasons, the collector task should not be used for the moment to move files to another partition. Use external scripts for this job (triggered by a temporal/file monitoring rule).  
    Due to the implementation of trace rotation mechanism, the output of the SWIFTNet user exit is redirected to null device. Since the exit is a java virtual machine, the new tracing mechanism can’t be integrated, so we strongly recommend to use log4j or other logging mechanism in userexit code. A log.properties sample file is provided in the samples directory.
-   **Navigator version compatibility**  
    If you use Navigator 6.16.0 to connect to an older Gateway (e.g. 6.11.4), or reversely, it is not recommended to use the older version of Gateway Navigator (e.g 6.14.1) to connect to the newer Gateway Server (e.g: 6.16.0). Doing so poses a risk that for some operations the Navigator will crash (ex: when you go to Partner Management/Sites/Remote Sites, if you right-click on a SWIFTNet Site and click View/Modify).
-   **Resuming an interrupted transfer with FileZilla**  
    When using FileZilla as client and Gateway as server, after resuming the transfer, the transfer state in Gateway will remain "Interrupted". Only after the file will be completely received the transfer state in Gateway will be updated to "Ended" and the file size will be correctly updated.

<span id="documentation"></span>

## Documentation

A new [Upgrade guide](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/Migration/upgrade_plan_Gateway.htm) is provided. It contains information for upgrading from version 6.16 to 6.17, as well as information about upgrades or upgrades for earlier versions, previously contained in the Installation guide.

X.25 and XOT being no longer in use by Gateway customers, references to those protocols has been removed from the documentation.

Axway Gateway is accompanied by a complete set of documentation. Links point to the Axway documentation portal:

-   [Gateway User Guide](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm)
-   [Gateway Installation Guide](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm)
-   [Gateway Upgrade Guide](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm)
-   [Gateway Configuration Guide (UNIX)](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm)
-   [Gateway Security Guide](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm) (login required to access this document on the Axway documentation portal)
-   Axway Supported Platforms

All Axway documentation, including documentation specific to each Axway component, is available from the Sphere Support website: https://support.axway.com.

<span id="support"></span>

## Support services

The Axway Global Support team provides worldwide 24 x 7 support for customers with active support agreements.

Email support@axway.com or visit Axway Sphere at https://support.axway.com.

Copyright © 2018 Axway. All rights reserved

Links to documentation set for Axway Gateway {{< Gateway/releasenumber  >}}:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
