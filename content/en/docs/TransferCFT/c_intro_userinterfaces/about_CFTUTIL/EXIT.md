{
    "title": "EXIT - Quit CFTUTIL",
    "linkTitle": "EXIT - Quit CFTUTIL",
    "weight": "240"
}The command EXIT quits the CFTUTIL program.

## Parameter descriptions

**\[exitcode = n { 0 ...65535 }\]**

By default there is an code that displays when you use the EXIT command to quit CFTUTIL. However, you can use the exitcode parameter to define a specific exit code, which replaces the default value.

Example

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>&gt;CFTUTIL EXIT EXITCODE=3</p>
<p> </p>
<p>EXIT EXITCODE=3</p>
<p>CFTU00I EXIT _ Correct (EXITCODE=3)</p></td>
</tr>
</tbody>
</table>
