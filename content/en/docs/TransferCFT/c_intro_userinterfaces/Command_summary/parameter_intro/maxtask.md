{
    "title": "maxtask",
    "linkTitle": "maxtask",
    "weight": "1960"
}### <span id="maxtask"></span>maxtask

#### CFTPARM

**MAXTASK = { <u>8</u>
| n}    **

Enter the number of authorized file access tasks (default = 8). This refers to the number of authorized file access tasks, for example CFTTFIL. The used value may be recomputed, and be greater than the defined value, depending on the fixed number of files a task can handle on the system.

The following table indicates the maximum number supported for each
system.

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">When MAXTASK is set to one, a high TRANTASK value is useless.</td>
</tr>
</tbody>
</table>

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>OS</th>
<th>Maximum number supported</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td data-valign="top"><p>UNIX </p></td>
<td data-valign="top"><p>64</p></td>
</tr>
<tr class="even">
<td data-valign="top"><p>Windows </p></td>
<td data-valign="top"><p>64</p></td>
</tr>
<tr class="odd">
<td data-valign="top"><p>z/OS (MVS)</p></td>
<td data-valign="top"><p>400</p></td>
</tr>
<tr class="even">
<td data-valign="top"><p>IBM i</p></td>
<td data-valign="top"><p>64</p></td>
</tr>
</tbody>
</table>

The following CFTI18I  message displays in the CFTLOG when Transfer CFT is started so that you can view the actual MAXTRANS, MAXTASK, TRANTASK values.

Example

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>CFTI18I+MAXTRANS=128, MAXTASK=16, TRANTASK=3</p></td>
</tr>
</tbody>
</table>

[Return to Command index](../../)
