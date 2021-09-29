{
    "title": "fdisp",
    "linkTitle": "fdisp",
    "weight": "1160"
}### <span id="fdisp"></span>fdisp

#### <span id="fdisp_CFTRECV"></span>CFTSEND, SEND

\[FDISP = { SHR
| CHECK }\]

File sharing option:

-   SHR: Shared access, which means that
    a file can be transferred at the same time for two partners.
-   CHECK:
    If the file is modified during a transfer, the transfer is aborted.

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">The value "OLD" is deprecated and no longer available for SEND/CFTSEND.</td>
</tr>
</tbody>
</table>

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">The CHECK feature is disabled on z/OS platforms (no action occurs when FDISP=CHECK).</td>
</tr>
</tbody>
</table>

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Caution  </strong></span></td>
<td data-mc-autonum="&lt;b&gt;Caution  &lt;/b&gt;" data-valign="top">When FDISP is set to CHECK, Transfer CFT performs an FSTAT for each record, which has a significant negative impact on performance.</td>
</tr>
</tbody>
</table>

#### CFTRECV, RECV

\[FDISP = { NEW | OLD | <u>BOTH</u>
}\]

Presence check indicator of the receiver file used to determine the
action of the Transfer CFT:

-   NEW: The file must be created by Transfer
    CFT. The transfer is refused if this file already exists
-   OLD: The file must already exist.
-   BOTH: If the file does not exist, it
    is created.

#### <span id="fdisp_CFTSEND"></span>Combined parameter actions

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

[Return to Command index](../../)
