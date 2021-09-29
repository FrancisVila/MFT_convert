{
    "title": "Procedure examples",
    "linkTitle": "Procedure examples",
    "weight": "240"
}The command files described below provide the outlines for establishing
end of transfer procedures using a syntax applicable to the Windows NT
operating system.

You can modify the file names and the method to activate CFTUTIL to
work on other operating systems. See [About CFTUTIL: Transfer
CFT utility](../../../c_intro_userinterfaces/about_cftutil).

#### <span id="Submitting_an_END_command"></span>Submitting an END command

The end of send procedure described in this example, is used to declare
correct transmission by the END command.

The name of the procedure to be activated is determined by the value
of the EXECSF parameter of CFTPARM.

Example

If the IDF of the file sent is PAY and if EXECSF = SF&IDF.CMD, the
name of the file associated with this procedure is:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>SFPAY.CMD.REM<br />
REM<br />
REM<br />
--------------------------------------------------------<br />
REM EXAMPLE OF A PROCEDURE SUBMITTED BY CFT AT THE END<br />
REM OF FILE TRANSMISSION<br />
REM<br />
REM This procedure declares that the current transfer<br />
REM changes to the X state.<br />
REM<br />
REM LIST OF SYMBOLIC VARIABLES<br />
REM<br />
REM PART &amp;PART PARTNER NAME<br />
REM IDT &amp;IDT TRANSFER IDENTIFIER<br />
REM<br />
REM ---------------------------------------------------<br />
CFTUTIL END PART=&amp;PART,IDT=&amp;IDT</td>
</tr>
</tbody>
</table>

#### <span id="Submitting_an_end_of_receive_procedure"></span>Submitting an end of receive procedure

The end of receive procedure, described in this next example, is used
to execute a particular type of processing on receiving a file with an
identifier (IDF) PAY.

The name of the procedure to be activated is determined by the value
of the EXECRF parameter of CFTPARM.

Example

If EXECRF = RF&IDF.CMD, the name of the file associated with this
procedure is: RFPAY.CMD.

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>REM<br />
REM<br />
--------------------------------------------------------<br />
REM<br />
REM EXAMPLE OF A PROCEDURE SUBMITTED BY CFT AT THE END<br />
REM OF FILE RECEPTION<br />
REM This procedure executes the MYPROG program, passing<br />
REM the following symbolic variables as parameters:<br />
REM LIST OF SYMBOLIC VARIABLES<br />
REM<br />
REM PART &amp;PART PARTNER NAME<br />
REM IDF &amp;IDF FILE IDENTIFIER<br />
REM IDT &amp;IDT TRANSFER IDENTIFIER<br />
REM EDATE &amp;EDATE END OF TRANSFER DATE<br />
REM ETIME &amp;ETIME END OF TRANSFER TIME<br />
REM FNAME &amp;FNAME NAME OF FILE RECEIVED<br />
REM<br />
REM<br />
REM ----------------------------------------------------<br />
MYPROG &amp;PART &amp;IDF &amp;IDT &amp;EDATE &amp;ETIME &amp;FNAME</td>
</tr>
</tbody>
</table>

If the transfer came from the SITEA partner, with a transfer IDT of
A0112102, and if the execution of this procedure is interrupted before
being completed, the user can re-activate it by the following command:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>CFTUTIL SUBMIT<br />
     PART     =    
SITEA,<br />
     IDT     =    
A0112102</td>
</tr>
</tbody>
</table>

#### <span id="Sending_a_response_message"></span>Sending a response message

In PeSIT D CFT profile, PeSIT E or ODETTE protocols, the end of transfer
procedure can activate the sending to the party of a response message
intended to inform that the transfer has been correctly completed. At
the party end, the initial transfer entry changes to the (supplementary)
A Acknowledged state.

The end of receive procedure described in this third example, is used
to activate this transmission on receiving a file with an identifier (IDF)
PAY.

The name of the procedure to be activated is determined by the value
of the EXECRF parameter of CFTPARM.

Example

If EXECRF = RM&IDF.CMD, the name of the file associated with this
procedure is: RMPAY.CMD.

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>REM<br />
REM<br />
------------------------------------------------------<br />
REM<br />
REM EXAMPLE OF A PROCEDURE SUBMITTED BY CFT AT THE END<br />
REM FILE RECEPTION<br />
REM<br />
REM This procedure allows an acknowledgement message<br />
REM to be sent at the end of file reception<br />
REM<br />
REM LIST OF SYMBOLIC VARIABLES<br />
REM<br />
REM PART &amp;PART PARTNER NAME<br />
REM IDT &amp;IDT TRANSFER IDENTIFIER<br />
REM<br />
REM ---------------------------------------------------<br />
CFTUTIL SEND TYPE=REPLY, PART=&amp;PART, IDM=MES1, IDT=&amp;idt,<br />
MSG=’File PAY received’</td>
</tr>
</tbody>
</table>
