{
    "title": "Shared file system prerequisites",
    "linkTitle": "Shared file systems",
    "weight": "190"
}This section provides general information concerning the prerequisites for shared file systems for the following types of files used with {{< TransferCFT/transfercftname  >}} in a UNIX environment.

-   Transfer CFT data files: This refers to all files managed by {{< TransferCFT/transfercftname >}} other than transferable application files (including database files), which are stored in the {{< TransferCFT/transfercftname >}} runtime directory.
-   Transferable application files: This refers to the files transferred by Transfer CFT.

## Standalone installation

You can use any POSIX compliant shared file system for both Transfer CFT data files and transferable application files.

The following table lists the file systems that are supported and tested with Transfer CFT.

<span id="Supported_fs_win"></span>Supported file systems

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Operating system         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">File system         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>AIX         </td>
         <td>GPFS, NFSv3, NFSv4*         </td>
      </tr>
      <tr>
         <td>HP-UX         </td>
         <td>NFSv3, NFSv4*         </td>
      </tr>
      <tr>
         <td>Linux-x86         </td>
         <td><p>GFS2, GPFS, GlusterFS, NFSv3, NFSv4*</p>         </td>
      </tr>
      <tr>
         <td>Solaris         </td>
         <td>NFSv4*         </td>
      </tr>
      <tr>
         <td>Windows-x86         </td>
         <td>GPFS, SMB         </td>
      </tr>
   </tbody>
</table>

\*References to NFSv4 imply any version of NFSv4. All NFSv4 minor versions are supported, for example version 4.2.

## Active/passive cluster

You can use any POSIX compliant shared file system for both Transfer CFT data files and transferable application files. Please see the [Supported file systems](#Supported_fs_win) in the Standalone installation section.

## Active/active cluster

#### {{< TransferCFT/transfercftname  >}} data files

**Supported shared file systems for multi-node, multi-host architecture (active/active)**

The following non-exhaustive table lists shared file systems that have been tested with Transfer CFT.

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Operating system         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Supported         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Unsupported         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>AIX         </td>
         <td>GPFS, NFSv4*         </td>
         <td>NFSv3, CXFS, VeritasSF         </td>
      </tr>
      <tr>
         <td>HP-UX         </td>
         <td>NFSv4*         </td>
         <td>NFSv3, CXFS, VeritasSF         </td>
      </tr>
      <tr>
         <td>Linux-x86         </td>
         <td>GPFS, GFS2, NFSv4*, AWS EFS         </td>
         <td>NFSv3, CXFS, ACFS, OCFSv1, OCFSv2, QFS, VeritasSF         </td>
      </tr>
      <tr>
         <td>Solaris         </td>
         <td>NFSv4*         </td>
         <td>NFSv3, CXFS, QFS, VeritasSF         </td>
      </tr>
      <tr>
         <td>Windows-x86         </td>
         <td>SMB/CIFS, GPFS         </td>
         <td>CXFS, NFS         </td>
      </tr>
      <tr>
         <td>z/OS         </td>
         <td>Sharing DASD across Sysplex         </td>
         <td>          </td>
      </tr>
   </tbody>
</table>

\*References to NFSv4 imply any version of NFSv4. All NFSv4 minor versions are supported, for example version 4.2.

#### {{< TransferCFT/transfercftname  >}} transferable application files

You can use any POSIX compliant shared file system for transferable application files.

Please see the [Supported file systems](#Supported_fs_win) in the Standalone installation section.
