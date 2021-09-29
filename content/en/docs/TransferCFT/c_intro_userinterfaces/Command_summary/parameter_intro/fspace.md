{
    "title": "fspace",
    "linkTitle": "fspace",
    "weight": "1380"
}### <span id="fspace"></span>fspace

#### <span id="fspace_CFTRECV"></span>CFTRECV, RECV

**\[FSPACE = {** **0**
**| n } \]**

Size of the receiver file, in Kbytes
(1 Kbyte = 1024 bytes).

This size usually corresponds to the primary allocation.

<table data-cellspacing="0">
<tbody>
<tr class="odd" data-valign="top">
<td width="26%"><p>UNIX</p></td>
<td width="74%"><p>Parameter not applicable</p></td>
</tr>
</tbody>
</table>

#### <span id="fspace_CFTSEND"></span>CFTSEND, SEND

**\[FSPACE = { 0
| n } \]**

Size of the file to be sent, in Kbytes (1 Kbyte = 1024 bytes).

This parameter does not usually need to be defined, since at each transfer
CFT automatically retrieves the size of the file it is going to send (if
necessary, check in the *Operations Guide* that this facility is
supported by the system in question).

#### <span id="fspace_CFTFILE"></span>CFTFILE

\[FSPACE
= {see [table](#fspace_table) | n}\]

{0..65536}

According to TYPE/**OS**

Primary allocation of the file to be created, expressed in Kbytes (1024).

For TYPE = COM and TYPE = CAT, this parameter should not be defined
for any system. The primary allocation of the file to be created is deduced
from the value of the RECNB parameter (number of records in the file).

The table below indicates, for each system, the default value supported
according to the type of file to be created. In this table, the FSPACE
parameter does not need to be defined when the default value of the primary
allocation of the file to be created is "no".

<table data-border="1" data-cellspacing="0">
<thead>
<tr class="header">
<th colspan="7"><span id="FSPACE_Table"></span>FSPACE</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td data-valign="top" width="17%"><p>OS </p></td>
<td data-valign="top" width="10%"><p>PARM </p></td>
<td data-valign="top" width="12%"><p>PART </p></td>
<td data-valign="top" width="14%"><p>CAT </p></td>
<td data-valign="top" width="14%"><p>COM </p></td>
<td data-valign="top" width="14%"><p>LOG </p></td>
<td data-valign="top" width="20%"><p>ACCNT </p></td>
</tr>
<tr class="even">
<td data-valign="top" width="17%"><p>MVS (z/OS)</p></td>
<td data-valign="top" width="10%"><p>50 </p></td>
<td data-valign="top" width="12%"><p>100 </p></td>
<td data-valign="top" width="14%"><p>no </p></td>
<td data-valign="top" width="14%"><p>no </p></td>
<td data-valign="top" width="14%"><p>200 </p></td>
<td data-valign="top" width="20%"><p>200 </p></td>
</tr>
<tr class="odd">
<td data-valign="top" width="17%"><p>IBM i (OS400) </p></td>
<td data-valign="top" width="10%"><p>512 </p></td>
<td data-valign="top" width="12%"><p>512 </p></td>
<td data-valign="top" width="14%"><p>no </p></td>
<td data-valign="top" width="14%"><p>no </p></td>
<td data-valign="top" width="14%"><p>512 </p></td>
<td data-valign="top" width="20%"><p>512 </p></td>
</tr>
<tr class="even">
<td data-valign="top" width="17%"><p>UNIX </p></td>
<td data-valign="top" width="10%"><p>no </p></td>
<td data-valign="top" width="12%"><p>no </p></td>
<td data-valign="top" width="14%"><p>no </p></td>
<td data-valign="top" width="14%"><p>no </p></td>
<td data-valign="top" width="14%"><p>no </p></td>
<td data-valign="top" width="20%"><p>no </p></td>
</tr>
<tr class="odd">
<td data-valign="top" width="17%"><p>Windows</p></td>
<td data-valign="top" width="10%"><p>no </p></td>
<td data-valign="top" width="12%"><p>no </p></td>
<td data-valign="top" width="14%"><p>no </p></td>
<td data-valign="top" width="14%"><p>no </p></td>
<td data-valign="top" width="14%"><p>no </p></td>
<td data-valign="top" width="20%"><p>no </p></td>
</tr>
</tbody>
</table>

[Return to Command index](../../)
