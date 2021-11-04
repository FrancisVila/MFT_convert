{
    "title": "Axway and third-party software support",
    "linkTitle": "Axway and third-party software support",
    "weight": "100"
}This section lists the <span class="mc-variable axway_variables.Company_Name variable">Axway</span> and third-party software supported for the various protocols and integrations.

<span id="Operatin2"></span>

## Operating Systems

Minor releases of supported major versions are considered safe to upgrade and are supported by SecureTransport. If a release is deprecated by the vendor, it automatically gets not supported by SecureTransport. We consider a release deprecated when it no longer receives security updates by the vendor. Deprecation notice will not be issued.

Operating systems are supported both on hardware or Type-1 hypervisors. If Axway suspects that the virtualization layer is the root cause of an incident, the customer may be required to contact their virtualization support provider to resolve it.

While <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> is expected to function properly in a virtual environment, there may be performance implications which can invalidate typical deployment recommendations.

Only 64-bit operating systems are supported.

### UNIX-like

-   Suse Linux Enterprise Server 12.x
-   Red Hat Enterprise Linux 7.x
-   Red Hat Enterprise Linux 8.x
-   Oracle Linux 7.x
-   Oracle Linux 8.x
-   CentOS 7.x
-   CentOS 8.x
-   IBM AIX 7.1 WPAR/LPAR
-   IBM AIX 7.2 WPAR/LPAR

> **Note:**
>
> CentOS 8 EOL date is December 31, 2021. SecureTransport will stop supporting this OS version on its EOL date. CentOS Stream is not supported by SecureTransport.

### Windows

-   Windows Server 2012 R2
-   Windows Server 2016
-   Windows Server 2019

<span id="Cloud"></span>

## Cloud Environments

Any cloud environments are supported using a VM running a supported operating system.

Customers should consider vendor specific limitations.

For recommended deployment instructions, refer to the deployment guides for the following cloud environments:

-   Amazon AWS
-   Microsoft Azure

<span id="Containe"></span>

## Container Environments

SecureTransport is supported in the following container environments:

-   Container Runtime: Docker Engine 19 and later stable releases
-   Container Orchestration Engine: Kubernetes 1.9 and later stable releases
-   External Database for containerized SecureTransport Edge: MySQL Enterprise Edition 5.6 or MariaDB 10.4.19.

For more details, refer to the Containerized Deployment Guide.

<span id="Database"></span>

## Databases for Enterprise Cluster

Minor releases of supported majors are considered safe to upgrade and are supported by SecureTransport. It is the customer's responsibility to keep their external databases up to date with the latest updates.

<span id="Microsof"></span>

### Microsoft SQL Server

The following major releases of Microsoft SQL Server (Standard and Enterprise Editions) are supported:

-   Microsoft SQL Server 2016
-   Microsoft SQL Server 2017
-   Microsoft SQL Server 2019

The following features are supported for all supported releases:

-   SQL Server Always On Failover Cluster Instances

### Oracle Database

The following major releases of Oracle Database are supported:

-   Oracle Database 12.2 Family (12c Release 2, 18c, 19c LTS) - Only Enterprise Edition with Partitioning License option is supported

The following features are supported for all supported releases:

-   Oracle RAC (with SCAN)
-   Kerberos authentication  
    -   Kerberos authentication is currently not supported for containerized deployments and Amazon RDS. 
    -   The Oracle database server may incorrectly interpret requests from SecureTransport as a replay attack ("Request is a replay" error message). This issue is resolved in Oracle 19.8 Patch 31716873. On previous Oracle database versions, the available workaround is to disable the Replay Cache mechanism.

### PostgreSQL

The following major releases of PostgreSQL are supported:

-   PostgreSQL 12.x

### Amazon RDS

The following database engines are supported in the Amazon RDS environment:

-   Oracle
-   Microsoft SQL Server
-   PostgreSQL

<span id="Browsers"></span>

## Browsers

Both the Administration tool and the <span class="mc-variable SecureTransport_Variables.st_web_client variable">ST Web Client</span> are supported on the latest version of the following browsers:

-   Apple Safari (not supported for Admin UI)
-   Google Chrome
-   Microsoft Edge
-   Mozilla Firefox

> **Note:**
>
> Browser must have JavaScript enabled.

<span id="Software"></span>

## Software for File Exchange

SecureTransport is expected to work properly with any client or server software which complies with:

<table>
   <tbody>
      <tr>
         <td>Protocol         </td>
         <td>CIT / SIT         </td>
         <td>Standard/Details         </td>
      </tr>
      <tr>
         <td>FTP(S)         </td>
         <td>CIT, SIT         </td>
         <td><p>RFC 959</p>
<p>RFC 2228</p>
<p>RFC 2389</p>
<p>RFC 2428</p>
<p>RFC 2640</p>
<p>RFC 4217</p>         </td>
      </tr>
      <tr>
         <td>SFTP / SCP         </td>
         <td>CIT, SIT         </td>
         <td><p>RFC 4251</p>
<p>RFC 4252</p>
<p>RFC 4253</p>
<p>RFC 4254</p>
<p>Draft RFC - Secure Shell File Transfer Protocol</p>
<p>Draft RFC - SSH File Transfer Protocol (draft-ietf-secsh-filexfer-04.txt)</p>         </td>
      </tr>
      <tr>
         <td>AS2         </td>
         <td>CIT, SIT         </td>
         <td><p>RFC 4130 (AS2 1.0 and 1.1 protocol versions)</p>
<p>List of certified products:</p>
<p>https://www.drummondgroup.com/certified-products-2/applicability-standards/</p>         </td>
      </tr>
      <tr>
         <td>PeSIT         </td>
         <td>CIT, SIT         </td>
         <td><p>PSIT_HS_E (PeSIT rev.E)</p>
<p>pTCP protocol v2 as an extension to PeSIT rev.E</p>         </td>
      </tr>
      <tr>
         <td>HTTP         </td>
         <td>CIT, SIT         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>HTTP - JMS         </td>
         <td>SIT         </td>
         <td>Supported by <a href="https://repository.axway.com/product-extensions/views/jms-connector-for-securetransport">JMS Connector</a>         </td>
      </tr>
      <tr>
         <td>HTTP - Google Cloud Storage         </td>
         <td>SIT         </td>
         <td>Supported by <a href="https://repository.axway.com/product-extensions/views/google-cloud-storage-connector-for-securetransport">Google Cloud Storage Connector</a>         </td>
      </tr>
      <tr>
         <td>HTTP - Google Drive         </td>
         <td>SIT         </td>
         <td>Supported by <a href="https://repository.axway.com/product-extensions/views/google-drive-connector-for-securetransport">Google Drive Connector</a>         </td>
      </tr>
      <tr>
         <td>HTTP - Azure File Storage         </td>
         <td>SIT         </td>
         <td>Supported by <a href="https://repository.axway.com/product-extensions/views/azure-file-storage-connector-for-securetransport">Azure File Storage Connector</a>         </td>
      </tr>
      <tr>
         <td>HTTP - Azure Blob Storage         </td>
         <td>SIT         </td>
         <td>Supported by <a href="https://repository.axway.com/product-extensions/views/azure-blob-storage-connector-for-securetransport">Azure Blob Storage Connector</a>         </td>
      </tr>
      <tr>
         <td>HTTP - Microsoft SharePoint         </td>
         <td>SIT         </td>
         <td>Supported by <a href="https://repository.axway.com/product-extensions/views/sharepoint-connector-for-securetransport">SharePoint Connector</a>         </td>
      </tr>
      <tr>
         <td>SMB 2.x, SMB 3.x         </td>
         <td>SIT         </td>
         <td>Supported by <a href="https://repository.axway.com/product-extensions/views/smb-connector-for-securetransport">SMB Connector</a>         </td>
      </tr>
      <tr>
         <td>HTTP - Amazon S3         </td>
         <td>SIT         </td>
         <td>Supported by <a href="https://repository.axway.com/product-extensions/views/amazon-s3-connector-for-securetransport">Amazon S3 Connector</a>         </td>
      </tr>
      <tr>
         <td>HTTP - Axway Syncplicity         </td>
         <td>SIT         </td>
         <td>Supported by <a href="https://repository.axway.com/product-extensions/views/syncplicity-connector-for-securetransport">Syncplicity Connector</a>         </td>
      </tr>
      <tr>
         <td>HTTP - Apache Hadoop         </td>
         <td>SIT         </td>
         <td>Supported by <a href="https://repository.axway.com/product-extensions/views/hadoop-connector-for-securetransport">Hadoop Connector</a>         </td>
      </tr>
   </tbody>
</table>

<span id="Authenti"></span>

## Authentication Providers and Directory Services

SecureTransport is expected to work properly with any LDAP server implementations that are compliant with:

-   RFC 4510 - LDAP v3
    -   TLS is only supported in Windows Server 2003 Active Directory or later

<span id="Single"></span>

## Single Sign-On (SSO)

SecureTransport is expected to work properly with any software which complies with:

-   SAML 2.0 for administrators and end-users
-   Kerberos 5 for end-users

SecureTransport only supports SAML-based Identity providers for SSO for administrators.

The client name has to be the same on all Identity Providers, SecureTransport only supports one service provider per component (Administrator and End-user).

## ICAP

SecureTransport implements the ICAP functionality adhering to the published ICAP standard, therefore it is expected that it will work with any server complying to the finalized ICAP standard (RFC 3507).

However, based on previous experience from validating ICAP servers, connecting to each additional ICAP server to SecureTransport is associated often with particularities in requests/responses for ICAP scan, which could result in behavior change and/or failures in the processing. Axway will evaluate such incidents (if any) and, whenever possible, will address them in the SecureTransport ICAP implementation to ensure operation continuity.

Incidents requiring major changes will be evaluated individually and addressed as part of the SecureTransport roadmap for new development.

<table>
   <tbody>
      <tr>
         <td>Software         </td>
         <td>Type         </td>
         <td>Version         </td>
         <td>Details         </td>
      </tr>
      <tr>
         <td>Symantec DLP         </td>
         <td>DLP         </td>
         <td>15         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>McAfee DLP         </td>
         <td>DLP         </td>
         <td>11.4         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Symantec Protection Engine for NAS         </td>
         <td>AV         </td>
         <td>8.1         </td>
         <td>AVSCAN and AVSCANREQ are supported         </td>
      </tr>
      <tr>
         <td>McAfee Web Gateway         </td>
         <td>AV         </td>
         <td>7.8.2.4         </td>
         <td>          </td>
      </tr>
   </tbody>
</table>

### Proxy Software

Supported Proxy Types:

-   HTTP(S) - supported only with HTTP(S) and AS2 transfer sites
-   HTTP(S) reverse proxy for HTTP transfers
-   SOCKS5
-   SecureTransport Edge

## PGP

SecureTransport is expected to work properly with any PGP keys which have been generated with compliance with RFC 5581.

## File Systems for User Files

-   Amazon EFS
-   CIFS
-   GFS 2
-   GlusterFS
-   IBM Spectrum Scale (GPFS) 5.x
-   NFS 3.0 - RFC 1813
-   NFS 4.0 - RFC 7530
-   NTFS
-   OCFS 2

## Compatibility with Axway Products

SecureTransport is compatible with the following Axway products for all of their supported releases.

<table>
   <tbody>
      <tr>
         <td>Software         </td>
         <td>Details         </td>
      </tr>
      <tr>
         <td>Axway Secure Client         </td>
         <td><p>FTP(S), SSH, HTTP(S)</p>
<p>As the Axway Secure Client firewall-friendly Tunnel mode uses SSL v3, you cannot use it for FTPS in FIPS transfer mode.</p>         </td>
      </tr>
      <tr>
         <td>Axway SecureTransport         </td>
         <td>FTP(S), SSH, HTTP(S), AS2, PeSIT, Ad-hoc         </td>
      </tr>
      <tr>
         <td>Axway Transfer CFT         </td>
         <td>PeSIT, SFTP (since 3.4)         </td>
      </tr>
      <tr>
         <td>Axway B2Bi         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Axway Sentinel         </td>
         <td>QLTv1         </td>
      </tr>
      <tr>
         <td>Decision Insight         </td>
         <td>QLTv1         </td>
      </tr>
      <tr>
         <td>Central Governance         </td>
         <td>version 1.1.3 SP14+         </td>
      </tr>
      <tr>
         <td>Flow Manager         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Embedded Analytics         </td>
         <td>QLTv1         </td>
      </tr>
   </tbody>
</table>

## Disclaimer

SecureTransport supports only third party software or OS releases that are supported by their vendor. End of support versions are automatically not supported by SecureTransport

Deprecation of supported operating systems and databases will be announced in advance
