{
    "title": "fspacex",
    "linkTitle": "fspacex",
    "weight": "1390"
}### <span id="fspacex"></span>fspacex

#### CFTFILE

\[FSPACEX =
{see table below| n}\]

{0..65536}

Depending on TYPE/OS

Secondary allocation of the file to be created expressed in Kbytes
(1024).

The following table indicates for each system the default value
according to the type of file to be created. If the indicated default
value of the secondary allocation of the file to be created is "no",
the FSPACEX does not need to be defined.

<table data-border="1" data-cellspacing="0" width="90%">
<thead>
<tr class="header">
<th colspan="7"><span id="FSPACEX_Table"></span>FSPACEX Table</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<th data-valign="top" width="17%"><p>OS </p></th>
<th data-valign="top" width="10%"><p>PARM </p></th>
<th data-valign="top" width="12%"><p>PART </p></th>
<th data-valign="top" width="14%"><p>CAT </p></th>
<th data-valign="top" width="14%"><p>COM </p></th>
<th data-valign="top" width="14%"><p>LOG </p></th>
<th data-valign="top" width="20%"><p>ACCNT </p></th>
</tr>

<tr class="odd">
<td data-valign="top" width="17%"><p>z/OS (MVS)</p></td>
<td data-valign="top" width="10%"><p>50 </p></td>
<td data-valign="top" width="12%"><p>100 </p></td>
<td data-valign="top" width="14%"><p>0 </p></td>
<td data-valign="top" width="14%"><p>0 </p></td>
<td data-valign="top" width="14%"><p>50 </p></td>
<td data-valign="top" width="20%"><p>50 </p></td>
</tr>
<tr class="even">
<td data-valign="top" width="17%"><p>OS400 </p></td>
<td data-valign="top" width="10%"><p>0 </p></td>
<td data-valign="top" width="12%"><p>0 </p></td>
<td data-valign="top" width="14%"><p>0 </p></td>
<td data-valign="top" width="14%"><p>0 </p></td>
<td data-valign="top" width="14%"><p>0 </p></td>
<td data-valign="top" width="20%"><p>0 </p></td>
</tr>
<tr class="odd">
<td data-valign="top" width="17%"><p>UNIX </p></td>
<td data-valign="top" width="10%"><p>no </p></td>
<td data-valign="top" width="12%"><p>no </p></td>
<td data-valign="top" width="14%"><p>no </p></td>
<td data-valign="top" width="14%"><p>no </p></td>
<td data-valign="top" width="14%"><p>no </p></td>
<td data-valign="top" width="20%"><p>no </p></td>
</tr>
<tr class="even">
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
