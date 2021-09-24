{
    "title": "System support",
    "linkTitle": "System support",
    "weight": "50"
}This page provides basic operating system, supported feature, and file system information. Always check the [Supported Platform Guide](https://docs.axway.com/bundle/Axway_Products_SupportedPlatforms_allOS_en/resource/Axway_Products_SupportedPlatforms_allOS_en.pdf) for the latest updates.

## Platforms

Transfer CFT is deployed on the operating systems and browsers listed in this information sheet.

### Operating systems for x64

-   CentOS 6, 7
-   Debian 7, 8, 9
-   Oracle Linux 6, 7
-   Oracle Solaris 10, 11
-   Red Hat Enterprise Linux 6, 7, 8
-   SUSE Linux Enterprise Server 11, 12, 15
-   Ubuntu 16.04, 18.04, 20.04
-   Windows 10
-   Windows Server 2012, 2012 R2, 2016, 2019

### Operating systems for Z

-   Red Hat Enterprise Linux 5, 6, 7
-   SUSE Linux Enterprise Server 11
-   z/OS 2.1, 2.2, 2.3, 2.4

### Operating systems for Power

-   IBM AIX 7.1, 7.2

### Operating systems for SPARC

-   Oracle Solaris 10, 11 for SPARC

### Additional operating systems

-   HP-UX 11.31 for PA-RISC
-   HP-UX 11.31 for ia64
-   HP NonStop H and J series for ia64
-   HP NonStop L series for x86-32
-   IBM i 7.2, 7.3, 7.4

## <span id="Virtuali"></span>Virtualization support

-   Amazon Elastic Compute Cloud (EC2) instance
-   Google Cloud Platform (GCP) VM instances
-   Microsoft Azure VM instances
-   VMware EXSi Virtual Machine
-   Other: Axway provides support for Axway products running in a virtual environment in a manner identical to Axway products running on any other major x86-based system. If, however, Axway suspects that the virtualization layer is the root cause of an incident, then the customer is required to contact the appropriate virtualization support provider to resolve the virtualization issue.

## Web browsers

-   Microsoft Edge – latest version
-   Mozilla Firefox – latest version
-   Google Chrome – latest version

## File systems for multi-node

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Operating system</th>
         <th>Supported	</th>
         <th>Unsupported</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>	AIX	         </td>
         <td>GPFS, NFSv4*         </td>
         <td>NFSv3, CXFS, VeritasSF         </td>
      </tr>
      <tr>
         <td>HP-UX	         </td>
         <td>NFSv4*         </td>
         <td>	NFSv3, CXFS, VeritasSF         </td>
      </tr>
      <tr>
         <td>Linux-x86	         </td>
         <td>GPFS, NFSv4*         </td>
         <td>NFSv3, CXFS, ACFS, OCFSv1, OCFSv2, QFS, VeritasSF         </td>
      </tr>
      <tr>
         <td>Solaris	         </td>
         <td>NFSv4*         </td>
         <td>	NFSv3, CXFS, QFS, VeritasSF         </td>
      </tr>
      <tr>
         <td>Windows-x86         </td>
         <td>SMB/CIFS, GPFS	         </td>
         <td>CXFS, NFS         </td>
      </tr>
      <tr>
         <td>z/OS         </td>
         <td>	Sharing DASD across Sysplex         </td>
         <td>          </td>
      </tr>
   </tbody>
</table>

\*References to NFSv4 imply any version of NFSv4. All NFSv4 minor versions are supported, for example version 4.2.

## Cloud storage

Available on Linux-x64 and Windows x64

-   Amazon Web Services S3 (Amazon Simple Storage Service).
-   Ceph Storage Cluster using the Ceph Object Gateway and its S3 compatible API.

## Java

If you are implementing either TrustedFile or Secure Relay with Transfer CFT, ensure that you have Java JRE 8 installed.

## Standard defaults

The Internet Assigned Numbers Authority (IANA) reserves the TCP ports 1761-1768 for Transfer CFT. For more information, refer to: [www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers](http://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml?&page=31).

<table cellspacing="0">
   <col/>
         <col data-mc-conditions=""/>
   <thead>
      <tr>
         <th>Component</th>
         <th>
            <p>Port </p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>PeSIT	         </td>
         <td>1761	         </td>
      </tr>
      <tr>
         <td>SSL	         </td>
         <td>1762	         </td>
      </tr>
      <tr>
         <td>SFTP         </td>
         <td>1763         </td>
      </tr>
      <tr>
         <td>COMS	         </td>
         <td>1765	         </td>
      </tr>
      <tr>
         <td>Copilot         </td>
         <td>1766	         </td>
      </tr>
      <tr>
         <td>Transfer CFT UI (Copilot) server for <span>Central Governance</span>         </td>
         <td>1767	         </td>
      </tr>
      <tr>
         <td>REST API         </td>
         <td>1768         </td>
      </tr>
      <tr>
         <td><span>Central Governance</span>
         </td>
         <td>12553	         </td>
      </tr>
      <tr>
         <td><span>Central Governance</span> SSL         </td>
         <td>12554         </td>
      </tr>
      <tr>
         <td>
            <p><span>Secure Relay</span> MA</p>
            <p>ma.comm_port</p>
         </td>
         <td>
            <p> </p>
            <p>6801</p>
         </td>
      </tr>
      <tr>
         <td>
            <p><span>Secure Relay</span> RA</p>
            <ul>
               <li>ra.comm_port               </li>
               <li>ra.admin_port               </li>
            </ul>
         </td>
         <td>
            <p> </p>
            <ul>
               <li>6811               </li>
               <li>6810               </li>
            </ul>
         </td>
      </tr>
   </tbody>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">In this document,  the terms Transfer CFT OS/400 and Transfer CFT IBM i may be used interchangeably.         </td>
      </tr>
</table>

## Third party licenses

Available on the Axway support site, at [support.axway.com](https://support.axway.com/en/documents/document-details/id/1441679).
