{
    "title": "execse",
    "linkTitle": "execse",
    "weight": "880"
}<span id="execse"></span>

### execse

<span id="execse_CFTPARM"></span>

#### CFTPARM

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
the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> *Operations Guide* that corresponds with your OS.

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
