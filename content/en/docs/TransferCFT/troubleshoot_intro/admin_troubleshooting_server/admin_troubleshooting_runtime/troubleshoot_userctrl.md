{
    "title": "Troubleshoot user control (USERCTRL)",
    "linkTitle": "Troubleshoot user control (USERCTRL)",
    "weight": "430"
}Homogeneous transfers fail on UNIX systems

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>CFTF03E local file deselect error 00000008</p>
<p>CFTF30W SFM_COPY : invalid file name OR other error IDTU= IDF=</p>
<p>CFTF30W+IDT=</p>
<p>CFTF30W+U=expl F=&lt;temporary filename&gt; &lt;IDTU=</p></td>
</tr>
</tbody>
</table>

If a USERID is set for a CFTRECV during a homogeneous transfer, the transfer fails if the user does not have rights on the log folder.

Fix

Grant the user the right to execute $CFTDIRLOG to access the directory.
