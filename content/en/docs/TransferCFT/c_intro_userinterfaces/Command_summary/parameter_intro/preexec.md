{
    "title": "preexec",
    "linkTitle": "preexec",
    "weight": "2670"
}### preexec

#### CFTSEND, SEND

\[ PREEXEC = filename \]

Name of the file describing the procedure to be executed in preprocessing phase, before the transfer. See [EXEC](../exec) for more information.

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note  &lt;/b&gt;" data-valign="top">To use direct script execution instead of the template script processing, preface the &lt;EXEC&gt;value with<span> 'cmd:'</span>. For example, <span>&lt;EXEC&gt;='<strong>cmd:</strong>myscript.sh &amp;PART &amp;IDT &amp;IDTU'</span>. See <a href="../../../../concepts/about_transfer_processing/proc_commands">Directly processing a program or script</a> for details, examples, restrictions, and support.</td>
</tr>
</tbody>
</table>

[Return to Command index](../../)
