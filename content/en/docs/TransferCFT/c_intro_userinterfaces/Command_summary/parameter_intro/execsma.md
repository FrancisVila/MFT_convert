{
    "title": "execsma",
    "linkTitle": "execsma",
    "weight": "920"
}<span id="execsma"></span>

### execsma

<span id="execsma_CFTPARM"></span>

#### CFTPARM

\[EXECSMA = filename\]
   {string
64}

Generic name of the file describing the procedures to be executed on
receiving an acknowledgement (reply) following sending a file.

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