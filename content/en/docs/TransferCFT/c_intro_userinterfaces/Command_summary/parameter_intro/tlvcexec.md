{
    "title": "tlvcexec",
    "linkTitle": "tlvcexec",
    "weight": "3520"
}<span id="tlvcexec"></span>

### <span class="mc-variable System.Title variable">tlvcexec</span>

#### CFTCAT

\[ TLVCEXEC = { str1...64
} \]

Batch to execute when the alert ends. The TLV parameters enable <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> to
issue alerts when a critical CAT fill threshold is reached based on a percentage of the catalog being filled, where 0% indicates empty and 100% indicates full.

This
alert generates 2 actions:

-   Sends a message
    to the LOG
-   Executes
    a batch to react to the alert, the <a href="#" class="selected">TLVWEXEC</a>
    parameter

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>To use direct script execution instead of the template script processing, preface the &lt;EXEC&gt;value with<span class="code"> 'cmd:'</span>. For example, <span class="code">&lt;EXEC&gt;='<strong>cmd:</strong>myscript.sh &amp;PART &amp;IDT &amp;IDTU'</span>. See <a href="../../../../concepts/about_transfer_processing/proc_commands#Directly">Directly processing a program or script</a> for details, examples, restrictions, and support.         </td>
      </tr>
   </tbody>
</table>

#### CFTCOM FILE

\[ TLVCEXEC = { str1...512
} \]

Batch to execute when the alert ends. The TLV parameters enable <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> to
issue alerts when a critical COM fill threshold is reached based on a percentage of the catalog being filled, where 0% indicates empty and 100% indicates full.

This
alert generates 2 actions:

-   Sends a message
    to the LOG
-   Executes
    a batch to react to the alert, the <a href="#" class="selected">TLVWEXEC</a>
    parameter

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>To use direct script execution instead of the template script processing, preface the &lt;EXEC&gt;value with<span class="code"> 'cmd:'</span>. For example, <span class="code">&lt;EXEC&gt;='<strong>cmd:</strong>myscript.sh &amp;PART &amp;IDT &amp;IDTU'</span>. See <a href="../../../../concepts/about_transfer_processing/proc_commands#Directly">Directly processing a program or script</a> for details, examples, restrictions, and support.         </td>
      </tr>
   </tbody>
</table>

For CFTCOM, the symbolic variables that you can use in the batch are restricted to: &SYSDATE, &SYSTIME, &CFTEVENT, &SYSDAY, &CFTNAME, &RUNTIMEDIR.

[Return to Command index](../../)
