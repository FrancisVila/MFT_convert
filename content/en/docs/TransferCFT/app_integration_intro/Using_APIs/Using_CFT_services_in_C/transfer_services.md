{
    "title": "Transfer services",
    "linkTitle": "Transfer services",
    "weight": "380"
}# <span id="Title"></span>Transfer services in C



Transfer services allow actions to be taken

on transfers with the security system performing an authorization check

when the request is submitted, and not when the request is processed by

the monitor, the behavior of unprotected IPC with an error message in

the log file.



The application can detect commands that do

not have permission for access. This lightens the workload, improving <span>Transfer CFT</span> performance, and reducing the cluttering

of the communication medium by invalid requests.



Use the transfer services to send transfer control commands to Transfer

CFT, with or without a **syntax analysis**

of these commands. The programming interface proposes a function integrating

a syntax analysis of the command to detect any errors, at the source,

and a function without syntax analysis, which provides a much smaller

coding volume.



The transfer services functions:



-   Check the validity

    of the command name

-   Analyze the syntax

    of the command parameters, if the function using the syntax analyzer is

    used

-   Place the command

    in the <span>Transfer CFT</span> communication medium



The processing performed by <span>Transfer CFT</span> is totally asynchronous.



The return code only provides an indication that the function has effectively

been taken into account but does not necessarily mean that <span>Transfer CFT</span>

has executed the command correctly. A return code indicating the success

of the function only means that the command has been correctly placed

in the communication medium.



<table data-cellspacing="0">
<colgroup>
<col/>
<col/>
</colgroup>
<thead>
<tr>
<th><p>Function</p></th>
<th><p>Use</p></th>
</tr>
</thead>
<tbody>
<tr data-valign="top">
<td width="28.255%"><p>SEND</p></td>
<td width="71.745%"><p>Send transfer request: file, message or reply</p></td>
</tr>
<tr data-valign="top">
<td width="28.255%"><p>RECV</p></td>
<td width="71.745%"><p>Receive transfer request</p></td>
</tr>
<tr data-valign="top">
<td width="28.255%"><p>HALT</p></td>
<td width="71.745%"><p>Interrupt one or more send or receive transfers with a

given partner.</p>
<p>The interrupted transfers are set to the "H"

state and can be restarted at the partner's request.</p></td>
</tr>
<tr data-valign="top">
<td width="28.255%"><p>KEEP</p></td>
<td width="71.745%"><p>Suspend one or more send or receive transfers with a given

partner.</p>
<p>The interrupted transfers are set to the "K"

state and can only be restarted by a START command.</p></td>
</tr>
<tr data-valign="top">
<td width="28.255%"><p>START</p></td>
<td width="71.745%"><p>Start one or more send or receive transfers</p></td>
</tr>
<tr data-valign="top">
<td width="28.255%"><p>DELETE</p></td>
<td width="71.745%"><p>Delete a catalog entry and any transfer in process associated

with it</p></td>
</tr>
<tr data-valign="top">
<td width="28.255%"><p>END</p></td>
<td width="71.745%"><p>Set a transfer status to executed</p>
<p>The transfer is set to the "X" state. This indicates

that end-of-transfer procedure has been correctly executed.</p></td>
</tr>
<tr data-valign="top">
<td width="28.255%"><p>SUBMIT</p></td>
<td width="71.745%"><p>Submit the end-of-transfer procedure</p></td>
</tr>
<tr data-valign="top">
<td width="28.255%"><p>SHUT</p></td>
<td width="71.745%"><p>Shut down <span>Transfer CFT</span></p></td>
</tr>
<tr data-valign="top">
<td width="28.255%"><p>SWITCH</p></td>
<td width="71.745%"><p>Switch monitoring files, LOG, STATS...</p></td>
</tr>
<tr data-valign="top">
<td width="28.255%"><p>CLOSEAPI</p></td>
<td width="71.745%"><p>Free resources allocated at opening of communication medium:

memory, network, file</p></td>
</tr>
<tr data-valign="top">
<td width="28.255%"><p>COM</p></td>
<td width="71.745%"><p>Define communication medium</p></td>
</tr>
<tr data-valign="top">
<td width="28.255%"><p>GETXINFO</p></td>
<td width="71.745%"><p>Retrieve information concerning the last transfer made

from a synchronous request</p></td>
</tr>
</tbody>
</table>



## <span id="Call Syntax"></span>Call syntax



rc =      cftau (verb,param)



rc =      cftac (verb,param)



Where:



-   cftau indicates

    that syntax analysis is requested

-   cftac indicates that syntax analysis is not requested

-   &lt;verb&gt; is

    the command that you want to process

-   &lt;param&gt; is

    a character string of variable length that contains the command parameters.

    The end of the field is defined by a character initially set to low-value

-   &lt;rc&gt; is the

    return code



The available &lt;verbs&gt; are listed in the following table.



<table data-cellspacing="0">
<thead>
<tr>
<th><p>&lt;verb&gt;</p></th>
<th><p>Service</p></th>
</tr>
</thead>
<tbody>
<tr>
<td><p>SEND</p></td>
<td><p>Send</p></td>
</tr>
<tr>
<td><p>RECV</p></td>
<td><p>Receive</p></td>
</tr>
<tr>
<td><p>HALT</p></td>
<td><p>Interrupt</p></td>
</tr>
<tr>
<td><p>KEEP</p></td>
<td><p>Suspend</p></td>
</tr>
<tr>
<td><p>START</p></td>
<td><p>Retry</p></td>
</tr>
<tr>
<td><p>DELETE</p></td>
<td><p>Delete</p></td>
</tr>
<tr>
<td><p>END</p></td>
<td><p>Proceed to "X" state</p></td>
</tr>
<tr>
<td><p>SUBMIT</p></td>
<td><p>Re-submit end-of-transfer procedure</p></td>
</tr>
<tr>
<td><p>SHUT</p></td>
<td><p>Stop monitor</p></td>
</tr>
<tr>
<td><p>SWITCH</p></td>
<td><p>Switching monitoring files<br/>

(log, statistics file)</p></td>
</tr>
<tr>
<td><p>COM</p></td>
<td><p> </p></td>
</tr>
</tbody>
</table>



For more information on the parameter syntax for each command, refer to

the [Command index](../../../Command_summary.htm).



If &lt;param&gt; is not defined, CFTU will

take a default name.



As these media are not available on all systems, the function performs

an availability check.



The security check is performed on the user name, and the user group

if applicable, depending on the command:



-   IDF if present

    in parameter field: DELETE, END, HALT, KEEP, SEND, RECV, START

-   Procedure name:

    SUBMIT

-   Type: SWITCH LOG

    or ACCNT



## Return codes



<table data-cellspacing="0">
<thead>
<tr>
<th><p>Mnemonic</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr>
<td><p>CAPI_NOERR</p></td>
<td><p>No error</p></td>
</tr>
<tr>
<td><p>CAPI_FUNC_UNDEF</p></td>
<td><p>Command not valid</p></td>
</tr>
<tr>
<td><p>CAPI_CMD_LENGTH</p></td>
<td><p>cftau only</p>
<p><span>Transfer CFT</span> command string invalid, does not exist, or

greater than 1024 characters long </p></td>
</tr>
<tr>
<td><p>CAPI_KEY_NAME</p></td>
<td><p>cftau only</p>
<p>Command syntax incorrect: keyword name incorrect</p></td>
</tr>
<tr>
<td><p>CAPI_KEY_VALUE</p></td>
<td><p>cftau only</p>
<p>Command syntax incorrect: keyword value incorrect</p></td>
</tr>
<tr>
<td><p>CAPI_MEM_GET</p></td>
<td><p>Memory allocation error</p></td>
</tr>
<tr>
<td><p>CAPI_MEM_FREE</p></td>
<td><p>Memory de-allocation error</p></td>
</tr>
<tr>
<td><p>CAPI_INT_ERR1</p></td>
<td><p>Internal error 1</p></td>
</tr>
<tr>
<td><p>CAPI_INT_ERR2</p></td>
<td><p>Internal error 2</p></td>
</tr>
<tr>
<td><p>CAPI_INT_ERR3</p></td>
<td><p>Internal error 3</p></td>
</tr>
</tbody>
</table>



## Error messages



The FIELD and MSG fields of the CFTAPI COPY CLAUSE contain:



-   FIELD: name of

    the incorrect parameter detected by the <span>Transfer CFT</span> syntax analyzer

-   MSG:

    -   Either a message

        relative to the error recognized by the syntax analyzer

    -   Or an error

        message describing an incident when the command is taken into account



See [Messages

and error codes](../../../Troubleshooting/collecting_information.htm).



If no error is detected, the FIELD and MSG fields are blank.

