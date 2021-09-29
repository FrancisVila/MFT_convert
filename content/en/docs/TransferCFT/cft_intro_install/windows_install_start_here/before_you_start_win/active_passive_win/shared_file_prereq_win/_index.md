{
    "title": "Shared file systems",
    "linkTitle": "Shared file systems",
    "weight": "210"
}This section provides general information concerning the prerequisites for shared file systems for the following types of files used with Transfer CFT in a UNIX environment.

-   Transfer CFT data files: This refers to all files managed by Transfer CFT other than transferable application files (including database files), which are stored in the Transfer CFT runtime directory.
-   Transferable application files: This refers to the files transferred by Transfer CFT.

## Standalone installation

You can use any POSIX compliant shared file system for both Transfer CFT data files and transferable application files.

The following table lists the file systems that are supported and tested with Transfer CFT.

<span id="Supported_fs_win"></span>Supported file systems

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>Operating system</th>
<th>File system</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>AIX</td>
<td>GPFS, NFSv3, NFSv4*</td>
</tr>
<tr class="even">
<td>HP-UX</td>
<td>NFSv3, NFSv4*</td>
</tr>
<tr class="odd">
<td>Linux-x86</td>
<td><p>GFS2, GPFS, GlusterFS, NFSv3, NFSv4*</p></td>
</tr>
<tr class="even">
<td>Solaris</td>
<td>NFSv4*</td>
</tr>
<tr class="odd">
<td>Windows-x86</td>
<td>GPFS, SMB</td>
</tr>
</tbody>
</table>

\*References to NFSv4 imply any version of NFSv4. All NFSv4 minor versions are supported, for example version 4.2.

## Active/passive cluster

You can use any POSIX compliant shared file system for both Transfer CFT data files and transferable application files. Please see the [Supported file systems](#supported_fs_win) in the Standalone installation section.

## Active/active cluster

#### Transfer CFT data files

**Supported shared file systems for multi-node, multi-host architecture (active/active)**

The following non-exhaustive table lists shared file systems that have been tested with Transfer CFT.

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>Operating system</th>
<th>Supported</th>
<th>Unsupported</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>AIX</td>
<td>GPFS, NFSv4*</td>
<td>NFSv3, CXFS, VeritasSF</td>
</tr>
<tr class="even">
<td>HP-UX</td>
<td>NFSv4*</td>
<td>NFSv3, CXFS, VeritasSF</td>
</tr>
<tr class="odd">
<td>Linux-x86</td>
<td>GPFS, GFS2, NFSv4*, AWS EFS</td>
<td>NFSv3, CXFS, ACFS, OCFSv1, OCFSv2, QFS, VeritasSF</td>
</tr>
<tr class="even">
<td>Solaris</td>
<td>NFSv4*</td>
<td>NFSv3, CXFS, QFS, VeritasSF</td>
</tr>
<tr class="odd">
<td>Windows-x86</td>
<td>SMB/CIFS, GPFS</td>
<td>CXFS, NFS</td>
</tr>
<tr class="even">
<td>z/OS</td>
<td>Sharing DASD across Sysplex</td>
<td> </td>
</tr>
</tbody>
</table>

\*References to NFSv4 imply any version of NFSv4. All NFSv4 minor versions are supported, for example version 4.2.

#### Transfer CFT transferable application files

You can use any POSIX compliant shared file system for transferable application files.

Please see the [Supported file systems](#supported_fs_win) in the Standalone installation section.
