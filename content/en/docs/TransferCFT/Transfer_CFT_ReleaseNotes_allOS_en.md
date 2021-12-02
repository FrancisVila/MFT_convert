{
    "title": "Axway AMPLIFY Transfer CFT 3.8 Release Notes",
    "linkTitle": "Release Notes",
    "weight": "30"
}-   [New features and enhancements](#New)
-   [Platform features](#Platform)
-   [Limitations](#Limitations)
-   [Prerequisites](#Prerequisites)
-   [Deprecated features](#Deprecat)
-   [Discontinued support](#Not%20supported)
-   [Documentation](#Documentation)
-   [Support services](#Support)

<span id="New"></span>

## New features and enhancements

This section lists new features and product enhancements added since the last major Transfer CFT release.

-   Support file transfers using Google Cloud Storage on Linux x64 systems.
-   Enhanced Internal Access Management to use custom roles and privileges, CFTROLE and CFTPRIV objects, which are defined in the general configuration.
-   Support for additional languages, French, Portuguese, Spanish in the Transfer CFT user interface.

### Minor enhancements

-   You can now customize the **Transfers** page in the user interface to manage the layout display.
-   You can define custom catalog filters.
-   Select transfers with CFTUTIL LISTCAT and DISPLAY commands using absolute and relative date and time criteria.
-   Added the NIDF field in accounting files (in V24 structures).
-   Add accounting API samples for C on IBM i.

<span id="Platform"></span>

## Platform features

The table below lists the available Transfer CFT 3.8 features according to the version and operating system where they were introduced.

<table>
   <thead>
      <tr>
<th rowspan="2"  >Function         </th>
<th colspan="5"  >  OS         </th>
      </tr>
      <tr>
<th  >Windows         </th>
<th  >UNIX         </th>
<th  >z/OS         </th>
<th  >IBM i         </th>
<th  >HP NS         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Google Cloud storage         </td>
         <td>-         </td>
         <td>3.8         </td>
         <td>-         </td>
         <td>-         </td>
         <td>-         </td>
      </tr>
      <tr>
         <td>Flow Manager         </td>
         <td>3.3.2         </td>
         <td>3.3.2         </td>
         <td>3.3.2         </td>
         <td>3.3.2         </td>
         <td>3.3.2         </td>
      </tr>
      <tr>
         <td>Flow Manager SaaS         </td>
         <td>3.6         </td>
         <td>3.6         </td>
         <td>3.6         </td>
         <td>3.6         </td>
         <td>3.6         </td>
      </tr>
      <tr>
         <td><p>Using tracking with</p>
<p>Edge Agent</p>         </td>
         <td>3.5         </td>
         <td>3.5         </td>
         <td>3.5         </td>
         <td>3.5         </td>
         <td>3.5         </td>
      </tr>
      <tr>
         <td>SAML         </td>
         <td>3.5         </td>
         <td>3.5         </td>
         <td>3.6         </td>
         <td>3.6 SP1         </td>
         <td>3.5         </td>
      </tr>
      <tr>
         <td>REST API          </td>
         <td>3.2.4         </td>
         <td>3.2.4         </td>
         <td>3.2.4         </td>
         <td>3.2.4         </td>
         <td>3.2.4         </td>
      </tr>
      <tr>
         <td>New browser-based user interface         </td>
         <td>3.3.2         </td>
         <td>3.3.2         </td>
         <td>3.3.2         </td>
         <td>3.3.2         </td>
         <td>3.3.2         </td>
      </tr>
      <tr>
         <td>Central Governance management         </td>
         <td>3.1.3         </td>
         <td>3.1.3         </td>
         <td>3.1.3         </td>
         <td>3.1.3         </td>
         <td>3.2.4         </td>
      </tr>
      <tr>
         <td>Folder monitoring         </td>
         <td>3.1.2         </td>
         <td>3.1.2         </td>
         <td>3.1.3<sup>4</sup>         </td>
         <td>3.1.3<sup>4</sup>         </td>
         <td>3.2.4         </td>
      </tr>
      <tr>
         <td>Secure Relay         </td>
         <td>3.1.2         </td>
         <td>3.1.2         </td>
         <td>3.1.3         </td>
         <td>3.1.3         </td>
         <td>-         </td>
      </tr>
      <tr>
         <td>Multi-node architecture         </td>
         <td>3.0.1         </td>
         <td>3.0.1<sup>1</sup>         </td>
         <td>3.0.1         </td>
         <td>-         </td>
         <td>-         </td>
      </tr>
      <tr>
         <td>TrustedFile (PGP S-MIME CMS)         </td>
         <td>3.0.1<sup>3</sup>         </td>
         <td>3.0.1<sup>1</sup>         </td>
         <td>3.0.1         </td>
         <td>-         </td>
         <td>-         </td>
      </tr>
      <tr>
         <td>PassPort AM         </td>
         <td>2.7.1         </td>
         <td>2.7.1<sup>1</sup>         </td>
         <td>3.0.1         </td>
         <td>3.0.1         </td>
         <td>3.2.4         </td>
      </tr>
      <tr>
         <td>SFTP         </td>
         <td>3.4         </td>
         <td>3.4 <sup>5</sup>         </td>
         <td>3.5 <sup>6</sup>         </td>
         <td>-         </td>
         <td>3.6<sup>6</sup>         </td>
      </tr>
      <tr>
         <td>IPv6         </td>
         <td>2.7.1         </td>
         <td>2.7.1<sup>1</sup>         </td>
         <td>2.7.1         </td>
         <td>2.7.1         </td>
         <td>3.3.2         </td>
      </tr>
      <tr>
         <td>pTCP         </td>
         <td>2.7.1         </td>
         <td>2.7.1<sup>1</sup>         </td>
         <td>-         </td>
         <td>-         </td>
         <td>-         </td>
      </tr>
      <tr>
         <td>UDT (excluding multi-node)         </td>
         <td>2.7.1         </td>
         <td>2.7.1<sup>2</sup>         </td>
         <td>-         </td>
         <td>-         </td>
         <td>-         </td>
      </tr>
      <tr>
         <td>SOCKS         </td>
         <td>2.7.1         </td>
         <td>2.7.1         </td>
         <td>3.0.1         </td>
         <td>2.7.1         </td>
         <td>3.3.2         </td>
      </tr>
      <tr>
         <td>Heartbeat functionality         </td>
         <td>2.7.1         </td>
         <td>2.7.1         </td>
         <td>2.7.1         </td>
         <td>2.7.1         </td>
         <td>3.2.4         </td>
      </tr>
      <tr>
         <td>Bandwidth control         </td>
         <td>3.0.1         </td>
         <td>3.0.1         </td>
         <td>3.0.1         </td>
         <td>3.0.1         </td>
         <td>3.3.2         </td>
      </tr>
      <tr>
         <td>System users (USERCTRL)         </td>
         <td>2.7.0         </td>
         <td>2.6.2         </td>
         <td>3.2.2         </td>
         <td>3.1.3         </td>
         <td>-         </td>
      </tr>
      <tr>
         <td><p><sup>1</sup>Enabled for all UNIX except SCO, UnixWare, IRIX, Tru64.</p>
<p><sup>2</sup> Enabled only for Linux-x86-32, Linux-x86-64, Linux-ia64-64.</p>
<p><sup>3</sup>Enabled for versions 3.0.1 to 3.3.2 on Windows 32-bit systems. As of Transfer CFT 3.4, Trusted File is supported on Windows 64-bit systems.</p>
<p><sup>4</sup>Limited to USS (z/OS) and IFS (IBM i) systems. On IBM i, native files folder monitoring is available for Transfer CFT 3.3.2 SP2 and higher.</p>
<p><sup>5</sup>Available on AIX, HPUX ia64, Linux, Solaris, Windows</p>
<p><sup>6</sup>For UNIX type files only</p>         </td>
      </tr>
   </tbody>
</table>

<span id="User"></span>

#### User interface comparison


| Functionality  |  Central Governance<br />  |  Transfer CFT user interface<br />  |
| --- | --- | --- |
|  Administration  | X  | X  |
| Configuration  | X*  | X  |
| Monitor transfers  | X  | X  |
| Manage transfers  | -  | X  |
| Monitor the log  | X  | X  |
| Manage certificates  | X  | X  |
| End-to-end monitoring  | X  | -  |


**Administration**: Start, stop, and restart Transfer CFT.

**Configuration**: Create configuration objects including partner definitions, transfer templates, protocols, and security profiles.

**Monitor transfers**: View the catalog file, which contains control data that is associated with transfers.

**Manage transfers**: Create, manage, and delete transfer requests.

**Monitor the log**: View log file.

**Manage certificates**: View and import certificates.

**End-to-end monitoring**: View a transfer process, from start to finish, along with all participants (sender, receiver, and intermediate participants).

\* You can perform some, but not all, configuration tasks (you can manage partner definitions and transfer templates).

#### Supported file systems for multi-node architecture

The following non-exhaustive table lists shared file systems that have been tested with Transfer CFT.

<span id="Limitations"></span>

## Limitations

-   Installation limitations include:
    -   For a Windows cluster, all machines in the cluster must have the same service definition (same name, display name, etc.)
    -   You cannot use the installation template file (initialize.properties) in a directory where the directory name contains accents
-   SFTP implementation does not support messages or the store-and-forward functionality
-   When using folder monitoring on behalf of another user (USERID):
    -   Linux: You cannot use both USERCTRL and events modes
    -   This is not supported in the obsolete folder configuration mode via UCONF parameters
-   When using AWS, Transfer CFT Windows presently only supports HTTP proxies (not HTTPS proxies)

<span id="Prerequisites"></span>

## Prerequisites

### Windows

Transfer CFT on Windows requires the **Visual C++ Redistributable Package for Visual Studio 2019** for proper functioning. This provides the necessary library files (DLL) for Transfer CFT. You must install `vcredist_x64.exe` prior to installing or upgrading Transfer CFT.

> **Note:**
>
> If the redistribution package is already installed on your Windows system, there is no need to reinstall.

### Secure Relay

Transfer CFT delivers an embedded Secure Relay MA 2.7.3. You must then additionally install the Secure Relay RA 2.7.3. Please refer to the *Secure Relay* [Installation Guide](https://docs.axway.com/bundle/SecureRelay_273_InstallationGuide_allOS_en_HTML5/page/Content/AxwayStartPageRA_install.htm) for details.

<span id="Deprecat"></span>

## Deprecated functions

The following section lists deprecated functions for Transfer CFT version 3.7 and higher:

-   Deprecated the former Habilitation Access Management method (SECUTIL).

The following section lists deprecated functions for Transfer CFT version 3.5 and higher:

-   Referencing a certificate with the PKIFNAME using the format (PKIFNAME=TXT://certificate) is no longer supported.
-   Deprecated the PAD parameter.

<span id="Not supported"></span>

## Discontinued support

Changing technologies as well as evolution in our customers systems, drives the need for Axway to modify or discontinue support for some features. The following list summarizes discontinued functions that have been announced for Transfer CFT.

### Discontinued platforms

The following platforms were previously supported, however support is discontinued in Transfer CFT 3.7 and higher:

-   Red Hat Enterprise Linux 5
-   Windows 7
-   Windows 2008, 2008 R2

The following platforms were previously supported in Transfer CFT 3.5; however, support is discontinued in Transfer CFT 3.6 and higher:

-   IBM i v7.1
-   z/OS v2.1

The following platforms were previously supported in Transfer CFT 3.2.4; however, support is discontinued in Transfer CFT 3.3.2 and higher:

-   SUSE Linux Enterprise Server 10 s390-32, s390-64
-   Red Hat Enterprise Linux 4 ia64‐64

The following platforms were previously supported in Transfer CFT 3.1.3; however, support is discontinued in Transfer CFT 3.2.4 and higher:

-   SUSE Linux Enterprise Server 10 x86‐64 (64-operating system)
-   Windows Server 2003 x86‐32, x86‐64, ia64‐64
-   Windows XP x86‐32, x86‐64
-   Windows Vista x86‐32, x86‐64
-   Red Hat Enterprise Linux 4 x86‐32, x86‐64, ia64‐64

The following platforms were previously supported in Transfer CFT 3.0.1; however, support is discontinued in Transfer CFT 3.1.3 and higher:

-   RHEL 3
-   Windows 2000

For a comprehensive list of supported platforms for Transfer CFT, please refer to the [Axway Supported Platforms Guide](https://docs.axway.com/bundle/Axway_Products_SupportedPlatforms_allOS_en/resource/Axway_Products_SupportedPlatforms_allOS_en.pdf).

Protocols

-   Protocol: EBICS is deprecated in Transfer CFT 3.4, with an EOL scheduled for 2020.

### Discontinued in Transfer CFT 3.8

-   PARTFNAM and PKIFNAME parameters in the CFTPARM object are obsolete (Windows/UNIX)
-   The Java Web Start Graphical User Interface (Copilot UI) is no longer available.

### Discontinued in Transfer CFT 3.7

-   ASIT Exits.

### Discontinued in Transfer CFT 3.6

-   EBICS - Customers should move to Axway EBICS Client. Please refer to the [EBICS Client documentation](https://docs.axway.com/bundle/EBICSClient_10_allOS_en_HTML5/page/ebics_client_documentation_home.html) for product details.

<!-- -->

-   Discontinued support of CFTCOM TYPE=MBX on Windows, OpenVMS, and z/OS platforms.

### Discontinued in Transfer CFT 3.5

-   Removed the cipher suite 9 (SSL\_RSA\_WITH\_DES\_CBC\_SHA).

### Discontinued in Transfer CFT 3.4

The following list summarizes discontinued functions for Transfer CFT version 3.4.

OS specific

-   z/OS Removed the CFTMI23A executable (COM and catalog migration utility) for migrating from version 2.3.2
-   IBM i - Removed the SI\_TEMPLIB library and the CLEANER/BACKGRND program

Platform support

Axway no longer delivers 32-bit versions of Transfer CFT, but does offer an automatic migration from an existing 32-bit version to Transfer CFT 3.4 64-bit on 64-bit OS.

### Discontinued in Transfer CFT 3.1.3 and higher

The following list summarizes discontinued functions for Transfer CFT version 3.1.3 and higher. Deprecated and discontinued features are non operational in the new version when you migrate, even though they display in the upgraded configuration. You should check for, and replace, these features as part of the migration procedure.

Interoperability

-   Composer for Transfer CFT
-   Transfer CFT Navigator

Networks and protocols

-   Networks: LU62, SNA, DSA, X.25, and DNA
-   Protocol: ETEBAC

<span id="Documentation"></span>

## Documentation

This section describes documentation enhancements and related documentation.

### Related documentation

For more information about Transfer CFT, refer to:

-   Transfer CFT 3.8 User Guide
-   Transfer CFT 3.8 Security Guide
-   Transfer CFT 3.8 UNIX Installation and Operations Guide
-   Transfer CFT 3.8 Windows Installation and Operations Guide
-   Transfer CFT 3.8 z/OS Installation and Operations Guide
-   Transfer CFT 3.8 IBM i Installation and Operations Guide
-   Transfer CFT 3.8 HP NonStop Installation and Operations Guide

<span id="Support"></span>

## Support services

The Axway Global Support team provides worldwide 24 x 7 support for customers with active support agreements.  
Email <support@axway.com> or visit Axway Sphere at [https://support.axway.com](https://support.axway.com/).

Copyright © 2021 Axway. All rights reserved.
