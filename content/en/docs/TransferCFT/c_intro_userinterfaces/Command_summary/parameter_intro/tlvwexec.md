{
    "title": "tlvwexec",
    "linkTitle": "tlvwexec",
    "weight": "3570"
}### <span id="tlvwexec"></span>tlvwexec

#### CFTCAT

\[ TLVWEXEC = { str1...64}
\]

Batch to execute when the TLVWARN is reached. The TLV parameters enable Transfer CFT to
issue alerts when a critical CAT threshold is reached based on a percentage of the catalog being filled, where 0% indicates empty and 100% indicates full.

This
alert generates 2 actions:

-   Sends a message
    to the LOG
-   Executes a batch
    to react to the alert (when CFTCAT/[TLVWARN](../tlvwarn) is reached)

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

\[ TLVWEXEC = { str1...512 }
\]

Batch to execute when the TLVWARN is reached. The TLV parameters enable Transfer CFT to
issue alerts when a critical COM threshold is reached based on a percentage of the communication media being filled, where 0% indicates empty and 100% indicates full.

This
alert generates 2 actions:

-   Sends a message
    to the LOG
-   Executes a batch
    to react to the alert (when CFTCOM/[TLVWARN](../tlvwarn) is reached)

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
