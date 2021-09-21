{
    "title": "tlvcexec",
    "linkTitle": "tlvcexec",
    "weight": "3550"
}### <span id="tlvcexec"></span>tlvcexec

#### CFTCAT

\[ TLVCEXEC = { str1...64
} \]

Batch to execute when the alert ends. The TLV parameters enable Transfer CFT to
issue alerts when a critical CAT fill threshold is reached based on a percentage of the catalog being filled, where 0% indicates empty and 100% indicates full.

This
alert generates 2 actions:

-   Sends a message
    to the LOG
-   Executes
    a batch to react to the alert, the [TLVWEXEC](#)
    parameter

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note  &lt;/b&gt;" valign="top">To use direct script execution instead of the template script processing, preface the &lt;EXEC&gt;value with<span> 'cmd:'</span>. For example, <span>&lt;EXEC&gt;='<b>cmd:</b>myscript.sh &amp;PART &amp;IDT &amp;IDTU'</span>. See <a href="../../../../concepts/about_transfer_processing/proc_commands">Directly processing a program or script</a> for details, examples, restrictions, and support.         </td>
      </tr>
</table>

#### CFTCOM FILE

\[ TLVCEXEC = { str1...512
} \]

Batch to execute when the alert ends. The TLV parameters enable Transfer CFT to
issue alerts when a critical COM fill threshold is reached based on a percentage of the catalog being filled, where 0% indicates empty and 100% indicates full.

This
alert generates 2 actions:

-   Sends a message
    to the LOG
-   Executes
    a batch to react to the alert, the [TLVWEXEC](#)
    parameter

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note  &lt;/b&gt;" valign="top">To use direct script execution instead of the template script processing, preface the &lt;EXEC&gt;value with<span> 'cmd:'</span>. For example, <span>&lt;EXEC&gt;='<b>cmd:</b>myscript.sh &amp;PART &amp;IDT &amp;IDTU'</span>. See <a href="../../../../concepts/about_transfer_processing/proc_commands">Directly processing a program or script</a> for details, examples, restrictions, and support.         </td>
      </tr>
</table>

For CFTCOM, the symbolic variables that you can use in the batch are restricted to: &SYSDATE, &SYSTIME, &CFTEVENT, &SYSDAY, &CFTNAME, &RUNTIMEDIR.

[Return to Command index](../../)