{
    "title": "Check the runtime",
    "linkTitle": "Check the runtime",
    "weight": "300"
}Runtime issues can include the following for the server, Copilot, CFTUTIL and other system services:

-   Abend
-   Performance
-   Start disk space, multi-node issues, restart
-   Unexpected shut down, such as when the catalog is full
-   System freezes or infinite looping
-   Service pack issues (applying or removing), also for migrating issues, updates

## Common causes

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>Issue</th>
<th colspan="5">Typical causes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td> </td>
<td><p>Hard disk bottleneck</p></td>
<td><p>Catalog</p>
<p>full</p></td>
<td><p>Network</p>
<p>bottleneck</p></td>
<td><p>Memory or processor bottleneck*</p></td>
<td><p>Corrupt</p>
<p>file or DB **</p></td>
</tr>
<tr class="even">
<td>Performance</td>
<td>Disk check</td>
<td> </td>
<td>Network checks</td>
<td>Check application</td>
<td> </td>
</tr>
<tr class="odd">
<td>Start issue</td>
<td>Disk check</td>
<td>Catalog check</td>
<td>Network checks</td>
<td>timeout</td>
<td>Check <span>Transfer CFT</span> files</td>
</tr>
<tr class="even">
<td>Unexpected stop</td>
<td>Disk check</td>
<td>Catalog check</td>
<td>Network checks</td>
<td> </td>
<td>Check <span>Transfer CFT</span> files</td>
</tr>
<tr class="odd">
<td>Transfer freeze or infinite looping</td>
<td>Disk check</td>
<td> </td>
<td>Network checks</td>
<td>Check application</td>
<td>Check <span>Transfer CFT</span> files</td>
</tr>
<tr class="even">
<td>SP and updates</td>
<td>Disk check</td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td>Crash</td>
<td>Disk check</td>
<td> </td>
<td>Network checks</td>
<td> </td>
<td>Check <span>Transfer CFT</span> files</td>
</tr>
</tbody>
</table>

\* Axway or third party software.

\*\* Transfer CFT internal database.

## Initial checks and actions

### Disk check

-   No space left on the device
    -   Free space
    -   Check Sentinel connectivity anTransfer CFTd verify the size of the runtime/data/trkapi.buf file, which may be voluminous
-   Check for problematic file transfers and output, and clean
-   Check to see if traces are set, which may lead to multiple large files in the "run" directory
-   Check to see if you have enabled dynamic catalog resizing

### Catalog check

When the catalog is full stops and you cannot restart it without a correction action to reduce the size of the catalog. Note that this does not necessarily mean that the disk is full.

-   See the [Catalog housekeeping](../../../../admin_intro/admin_monitoring_intro/housekeeping_catalog) section
-   Backup your catalog and export the existing catalog

### Export the full catalog

Create a new catalog file configured for a greater number of records, and re-import the original catalog file.

Use the command: cftmi

1.  Export the full catalog as shown in the following example.
2.  Check that the exported file is not empty.
3.  Create new catalog:
4.  Import the exported catalog file into the new catalog.
5.  Move (rename) depending on your operating system:

### Network checks

These corrective measures are often system dependent.

-   Perform basic tests such as pinging the address, and telnet (to check the port)

### Check additional products

-   Check if another product is consuming all of the CPU/memory
-   Check Central Governance interoperability, such as the Sentinel database
-   Scripts or end-of-transfer procedures may indirectly
