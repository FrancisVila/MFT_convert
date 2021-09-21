{
    "title": "execse",
    "linkTitle": "execse",
    "weight": "910"
}### <span id="execse"></span>execse

#### <span id="execse_CFTPARM"></span>CFTPARM

\[EXECSE = filename\]
   {string
64}

Generic name of the file describing
the procedures to be executed, following an incident (Error) during a
send transfer, the transfer changing to the H or K state.

This name may include the following symbolic variables:

-   &IDF, &PARM
-   &PART, &RPART,
    &SPART, &GROUP
-   &RUSER, &SUSER,
    &USERID
-   &RAPPL, &SAPPL
-   &DIAGI, &DIAGP
-   &NIDF

The character ‘&’ designates the char\_symb character defined in
the Transfer CFT *Operations Guide* that corresponds with your OS.

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

[Return to Command index](../../)