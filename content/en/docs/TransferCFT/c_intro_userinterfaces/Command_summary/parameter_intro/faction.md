{
    "title": "faction",
    "linkTitle": "faction",
    "weight": "1060"
}### <span id="faction"></span>faction

#### <span id="faction_CFTSEND"></span>CFTSEND, SEND

**\[FACTION = {NONE
| DELETE | ERASE | ARCHIVE }\]**

Action on the file after a send transfer:

-   NONE: No action on this file on completion
    of the transfer.
-   DELETE: Delete the file after transfer. Note the following specificities:
    -   No delete occurs if you are using SELFNAME and the FNAME is set to a directory mask (for example, #dir is deleted, but #dir/\* is ignored).
    -   If a file is added to the directory while a transfer is in progress, neither this new file nor is the directory is deleted.
-   ERASE: erase the contents of the file
    after the transfer ("End Of File" mark at the beginning of the
    file)
-   **ARCHIVE**: the source file is moved to the file name specified in the ARCHIVEFNAME parameter when the transfer is completed. If the transfer fails, the file is not moved. If the target file already exists, it is overwritten.

FACTION limitations

-   ERASE is not supported when using a group of files in homogeneous mode, or when broadcasting (CFTDEST ).
-   DELETE is not supported when broadcasting (CFTDEST ).
-   ARCHIVE is not supported when using a group of files (homogeneous transfers), or when broadcasting (CFTDEST).
-   OS-specific limitations:
    -   z/OS: VSAM, PDS, and GDG files are not supported.
    -   HP NonStop: ARCHIVE is not supported with Guardian files.

#### CFTRECV, RECV

**\[FACTION = {VERIFY
| DELETE | ERASE | RENAME | RETRYRENAME }\]**

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">The RENAME option is only available on Unix platforms.</td>
</tr>
</tbody>
</table>

Action on a file before a receive transfer except when using RENAME or RETRYRENAME, which are post transfer actions.

If a receiver file with the same name already exists, Transfer CFT performs
one of the following actions:

-   VERIFY: checks that the file is empty before the transfer occurs
-   DELETE:
    deletes the file before the transfer occurs
-   ERASE:
    erases the contents of the file before the transfer occurs
-   **RENAME**: replaces the existing FNAME file after the transfer completes by renaming the WFNAME file (*Unix only*)
-   **RETRYRENAME**: Renames the file on transfer completion in the post-processing phase, and includes a configurable retry mechanism. See also [Post-transfer file renaming](../../../../app_integration_intro/spoolout).

Requirements when using RENAME or RETRYRENAME:

-   If the CFTRECV WFNAME is not defined, the transfer fails with DIAGI=138.
-   The user (userid) who performs the transfer must have adequate rights to rename the file WFNAME to file FNAME. If not, the transfer fails with DIAGI=156.

The following table shows the combined effect of the FDISP and FACTION parameters when used in a RECV command.

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">There no impact on FDISP when used in combination with RENAME or RETRYRENAME.</td>
</tr>
</tbody>
</table>

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>CFTRECV, FDISP</th>
<th>CFTRECV, FACTION</th>
<th>Comments</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>both</td>
<td>delete</td>
<td>If no file exists, the file is created. If file exists it is deleted and recreated (regardless of if it is empty or not).</td>
</tr>
<tr class="even">
<td>both</td>
<td>erase</td>
<td>If no file exists, the file is created. If file exists it is overwritten (no matter if it is empty or not).</td>
</tr>
<tr class="odd">
<td>both</td>
<td>verify</td>
<td>If no file exists, the file is created. If file exists and it is not empty, the transfer is aborted. If file exists but it is empty, the file is overwritten.</td>
</tr>
<tr class="even">
<td>new</td>
<td>verify</td>
<td>If no file exists, the file is created. If file exists the transfer is aborted (regardless of if it is empty or not).</td>
</tr>
<tr class="odd">
<td>old</td>
<td>delete</td>
<td>If no file exists, the transfer is aborted. If file exists the file is deleted and recreated (regardless of if it is empty or not).</td>
</tr>
<tr class="even">
<td>old</td>
<td>erase</td>
<td>If no file exists, the transfer is aborted. If file exists the file is overwritten (regardless of if it is empty or not).</td>
</tr>
<tr class="odd">
<td>old</td>
<td>verify</td>
<td>If no file exists, the transfer is aborted. If file exists and it is not empty, the transfer is aborted. If file exists but it is empty, the file is overwritten.</td>
</tr>
</tbody>
</table>

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>OS</th>
<th>Details</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>z/OS</p></td>
<td><p>For VSAM files, only FACTION = ERASE is accepted.</p></td>
</tr>
</tbody>
</table>

[Return to Command index](../../)[ ](#)
