{
    "title": "execrm",
    "linkTitle": "execrm",
    "weight": "900"
}### <span id="execrm"></span>execrm

#### <span id="execrm_CFTPARM"></span>CFTPARM

\[EXECRM = filename\]
    {string 64}

Generic name of the file describing
the procedures to be executed on completion of reception of a message.

This name may include the following symbolic variables:

-   &IDM, &PARM
-   &PART, &RPART,
    &SPART, &GROUP
-   &RUSER, &SUSER,
    &USERID
-   &RAPPL, &SAPPL

The character ‘&’ designates the char\_symb character defined in
the Transfer CFT *Operations Guide* corresponding to your OS

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
