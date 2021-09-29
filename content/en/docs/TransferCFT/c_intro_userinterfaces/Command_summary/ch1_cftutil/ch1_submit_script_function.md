{
    "title": "Submit script function",
    "linkTitle": "Submit script function",
    "weight": "250"
}This section describes how to submit a script.

### \_FMSUB

\_FMSUB Function starts the execution of a batch file without waiting for the end of the execution of it.

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>_FMSUB PARM = (FILENAME)</p>
<p>RC = lrc</p></td>
</tr>
</tbody>
</table>

#### Parameters

-   FILENAME: Character set is the name of the command file to execute.
-   String1:
-   String2:
-   lrc name of a long integer variable that receives return code execution.

#### Examples

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>CHAR NAME = FILE_CMD, SIZE = 13, INIT = CONFIG.CMD</p>
<p>LONG NAME = RSC</p>
<p>_FMSUB PARM = (%FILE_CMD%), RC = LRC</p></td>
</tr>
</tbody>
</table>
