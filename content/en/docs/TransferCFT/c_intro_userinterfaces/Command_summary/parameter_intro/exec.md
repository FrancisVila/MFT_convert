{
    "title": "exec",
    "linkTitle": "exec",
    "weight": "850"
}### <span id="exec"></span>exec

#### <span id="exec_CFTSEND"></span>CFTSEND, <span id="exec Static CFTRECV"></span>CFTRECV, SEND, RECV

\[EXEC = filename\]...{string 512}

Specify the name of the file that defines the end-of-transfer procedure.

This name can include the following symbolic variables:

-   &IDF, &PARM
-   &PART, &RPART,
    &SPART, &GROUP
-   &RUSER, &SUSER,
    &USERID
-   &RAPPL, &SAPPL
-   &NIDF

Name of the file describing the procedure to be executed on completion
of the transfer. This allows a procedure to be associated with a model file identifier
(IDF), instead of including the symbolic variable &IDF at the level
of the EXECSF or EXECRF parameter of CFTPARM.

The symbolic variables possible in filename
and in the associated procedure, or set of associated procedures, are
the same as the ones authorized for the end-of-transfer procedures referred
to in CFTPARM. See [Symbolic variables](../../symbolic_variables).

-   If the EXEC parameter is defined and:
    -   If the file corresponding
        to filename exists, the associated procedure is submitted on completion
        of the transfer.
    -   If the file does
        not exist, an error message is generated and no processing is executed on completion of the transfer (even
        if the EXECSF parameter of the CFTPARM command is defined).
    -   If EXEC is set to \_NONE\_, then no processing is executed even if there is a defined EXECSF or EXECRF.
-   If this EXEC parameter is not defined, the EXECSF or EXECRF parameter
    of the CFTPARM command is taken into account.

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

#### <span id="exec_CFTLOG"></span>CFTLOG

\[EXEC = filename\]
   {string
64}

Name
of the procedure to be executed when switching to the other log file.

This procedure can access the symbolic variable &FLOG which contains
the name of the last log file used before switching (current file).

#### <span id="exec_CFTACCNT"></span>CFTACCNT

\[EXEC = filename\]    {string 64}

Name of the procedure to be executed when Transfer CFT switches to the
other statistical file.

This procedure has access to the symbolic variable &FACCNT which
contains the name of the last statistical file used before switching.

#### <span id="exec_CFTDEST"></span>CFTDEST

**\[EXEC = { <u>DEST</u> | PART | CHILDREN }\]**

The end-of-transfer procedure submit
mode.

-   DEST: When a transfer is terminated, an end-of-transfer procedure is submitted for all generic transfers (parent). The symbolic variables are substituted on the fly. For example, the &PART variable is substituted with the CFTDEST command identifier for the generic, and the partner identifier for each transfer on the list.
-   PART: An end-of-transfer procedure is submitted for each
    terminated parent and child transfer. The symbolic variables are substituted in line with
    the current record. For example, the &PART variable is substituted
    with the transfer parameter identifier.

<!-- -->

-   CHILDREN: The end-of transfer procedure is submitted for each terminated transfer in the group of transfers (children), but not for the generic (parent) catalog entry.

#### SUBMIT

**\[EXEC = filename\]**

#### CFTCRON

\[EXEC = filename\]...{string 512}

Specify the name of the file that describes the CRONJOB procedure.

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