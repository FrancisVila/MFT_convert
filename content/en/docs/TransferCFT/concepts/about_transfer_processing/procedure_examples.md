{
    "title": "Procedure examples",
    "linkTitle": "Procedure examples",
    "weight": "230"
}The command files described below provide the outlines for establishing
end of transfer procedures using a syntax applicable to the Windows NT
operating system.

You can modify the file names and the method to activate CFTUTIL to
work on other operating systems. See [About CFTUTIL: Transfer
CFT utility](../../../c_intro_userinterfaces/about_cftutil).

<span id="Submitting_an_END_command"></span>

#### Submitting an END command

The end of send procedure described in this example, is used to declare
correct transmission by the END command.

The name of the procedure to be activated is determined by the value
of the EXECSF parameter of CFTPARM.

Example

If the IDF of the file sent is PAY and if EXECSF = SF&IDF.CMD, the
name of the file associated with this procedure is:

<span id="Submitting_an_end_of_receive_procedure"></span>

#### Submitting an end of receive procedure

The end of receive procedure, described in this next example, is used
to execute a particular type of processing on receiving a file with an
identifier (IDF) PAY.

The name of the procedure to be activated is determined by the value
of the EXECRF parameter of CFTPARM.

Example

If EXECRF = RF&IDF.CMD, the name of the file associated with this
procedure is: RFPAY.CMD.

If the transfer came from the SITEA partner, with a transfer IDT of
A0112102, and if the execution of this procedure is interrupted before
being completed, the user can re-activate it by the following command:

<span id="Sending_a_response_message"></span>

#### Sending a response message

In PeSIT D CFT profile, PeSIT E or ODETTE protocols, the end of transfer
procedure can activate the sending to the party of a response message
intended to inform that the transfer has been correctly completed. At
the party end, the initial transfer entry changes to the (supplementary)
**A** Acknowledged state.

The end of receive procedure described in this third example, is used
to activate this transmission on receiving a file with an identifier (IDF)
PAY.

The name of the procedure to be activated is determined by the value
of the EXECRF parameter of CFTPARM.

Example

If EXECRF = RM&IDF.CMD, the name of the file associated with this
procedure is: RMPAY.CMD.
