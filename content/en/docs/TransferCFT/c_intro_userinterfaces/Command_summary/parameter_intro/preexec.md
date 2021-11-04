{
    "title": "preexec",
    "linkTitle": "preexec",
    "weight": "2640"
}### preexec

#### CFTSEND, SEND

\[ PREEXEC = filename \]

Name of the file describing the procedure to be executed in preprocessing phase, before the transfer. See [EXEC](../exec) for more information.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>To use direct script execution instead of the template script processing, preface the &lt;EXEC&gt;value with<span class="code"> 'cmd:'</span>. For example, <span class="code">&lt;EXEC&gt;='<strong>cmd:</strong>myscript.sh &amp;PART &amp;IDT &amp;IDTU'</span>. See <a href="../../../../concepts/about_transfer_processing/proc_commands#Directly">Directly processing a program or script</a> for details, examples, restrictions, and support.         </td>
      </tr>
   </tbody>
</table>

[Return to Command index](../../)
