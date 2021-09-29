{
    "title": "execrf",
    "linkTitle": "execrf",
    "weight": "890"
}### <span id="execrf"></span>execrf

#### <span id="execrf_CFTPARM"></span>CFTPARM

\[EXECRF = filename\]     {string 64}

Generic name of the file describing the procedures to be executed on
completion of the reception of a file.

This name may include the following symbolic variables:

-   &IDF, &PARM
-   &PART, &RPART,
    &SPART, &GROUP
-   &RUSER, &SUSER,
    &USERID
-   &RAPPL, &SAPPL
-   &NIDF

The character ‘&’ designates the char\_symb character defined in
the Transfer CFT *Operations Guide* corresponding to your OS.

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
