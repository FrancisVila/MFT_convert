{
    "title": "Transfer services in COBOL",
    "linkTitle": "Transfer services in COBOL",
    "weight": "380"
}# <span id="Transfer_services_in_COBOL"></span>Transfer services in COBOL

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
    in the Transfer CFT communication medium

The processing performed by Transfer CFT is totally asynchronous.

The return code only provides an indication that the function has effectively
been taken into account but does not necessarily mean that Transfer CFT
has executed the command correctly. A return code indicating the success
of the function only means that the command has been correctly placed
in the communication medium.

<table data-cellspacing="0">
<thead>
<tr class="header">
<th><p>Function</p></th>
<th><p>Use</p></th>
</tr>
</thead>
<tbody>
<tr class="odd" data-valign="top">
<td width="28.255%"><p>SEND</p></td>
<td width="71.745%"><p>Send transfer request: file, message or reply</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="28.255%"><p>RECV</p></td>
<td width="71.745%"><p>Receive transfer request</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="28.255%"><p>HALT</p></td>
<td width="71.745%"><p>Interrupt one or more send or receive transfers with a
given partner.</p>
<p>The interrupted transfers are set to the "H"
state and can be restarted at the partner's request.</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="28.255%"><p>KEEP</p></td>
<td width="71.745%"><p>Suspend one or more send or receive transfers with a given
partner.</p>
<p>The interrupted transfers are set to the "K"
state and can only be restarted by a START command.</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="28.255%"><p>START</p></td>
<td width="71.745%"><p>Start one or more send or receive transfers</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="28.255%"><p>DELETE</p></td>
<td width="71.745%"><p>Delete a catalog entry and any transfer in process associated
with it</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="28.255%"><p>END</p></td>
<td width="71.745%"><p>Set a transfer status to executed</p>
<p>The transfer is set to the "X" state. This indicates
that end-of-transfer procedure has been correctly executed.</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="28.255%"><p>SUBMIT</p></td>
<td width="71.745%"><p>Submit the end-of-transfer procedure</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="28.255%"><p>SHUT</p></td>
<td width="71.745%"><p>Shut down <span>Transfer CFT</span></p></td>
</tr>
<tr class="even" data-valign="top">
<td width="28.255%"><p>SWITCH</p></td>
<td width="71.745%"><p>Switch monitoring files, LOG, STATS...</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="28.255%"><p>CLOSEAPI</p></td>
<td width="71.745%"><p>Free resources allocated at opening of communication medium:
memory, network, file</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="28.255%"><p>COM</p></td>
<td width="71.745%"><p>Define communication medium</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="28.255%"><p>GETXINFO</p></td>
<td width="71.745%"><p>Retrieve information concerning the last transfer made
from a synchronous request</p></td>
</tr>
</tbody>
</table>

## <span id="Call Syntax"></span>Call syntax

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>CALL     "CFTU"    
USING     &lt;verb&gt;       &lt;param&gt;    
&lt;rc&gt;<br />
CALL     "CFTC"    
USING     &lt;verb&gt;       &lt;param&gt;    
&lt;rc&gt;</td>
</tr>
</tbody>
</table>

Where:

-   CFTU indicates
    that syntax analysis is requested  
    CFTC indicates that syntax analysis is not requested
-   &lt;verb> is
    the command that you want to process
-   &lt;param> is
    a character string of variable length that contains the command parameters.
    The end of the field is defined by a character initially set to low-value

<!-- -->

-   &lt;rc> is the
    return code

The available &lt;verbs> are listed in the following table.

<table data-cellspacing="0">
<thead>
<tr class="header">
<th><p>&lt;verb&gt;</p></th>
<th><p>Value</p></th>
<th><p>Service</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td data-valign="top" width="30.155%"><p>F-SEND</p></td>
<td data-valign="top" width="18.543%"><p>SEND</p></td>
<td data-valign="top" width="51.303%"><p>Send</p></td>
</tr>
<tr class="even">
<td data-valign="top" width="30.155%"><p>F-RECV</p></td>
<td data-valign="top" width="18.543%"><p>RECV</p></td>
<td data-valign="top" width="51.303%"><p>Receive</p></td>
</tr>
<tr class="odd">
<td data-valign="top" width="30.155%"><p>F-HALT</p></td>
<td data-valign="top" width="18.543%"><p>HALT</p></td>
<td data-valign="top" width="51.303%"><p>Interrupt</p></td>
</tr>
<tr class="even">
<td data-valign="top" width="30.155%"><p>F-KEEP</p></td>
<td data-valign="top" width="18.543%"><p>KEEP</p></td>
<td data-valign="top" width="51.303%"><p>Suspend</p></td>
</tr>
<tr class="odd">
<td data-valign="top" width="30.155%"><p>F-START</p></td>
<td data-valign="top" width="18.543%"><p>START</p></td>
<td data-valign="top" width="51.303%"><p>Retry</p></td>
</tr>
<tr class="even">
<td data-valign="top" width="30.155%"><p>F-DELETE</p></td>
<td data-valign="top" width="18.543%"><p>DELETE</p></td>
<td data-valign="top" width="51.303%"><p>Delete</p></td>
</tr>
<tr class="odd">
<td data-valign="top" width="30.155%"><p>F-END</p></td>
<td data-valign="top" width="18.543%"><p>END</p></td>
<td data-valign="top" width="51.303%"><p>Proceed to "X" state</p></td>
</tr>
<tr class="even">
<td data-valign="top" width="30.155%"><p>F-SUBMIT</p></td>
<td data-valign="top" width="18.543%"><p>SUBMIT</p></td>
<td data-valign="top" width="51.303%"><p>Re-submit end-of-transfer procedure</p></td>
</tr>
<tr class="odd">
<td data-valign="top" width="30.155%"><p>F-SHUT</p></td>
<td data-valign="top" width="18.543%"><p>SHUT</p></td>
<td data-valign="top" width="51.303%"><p>Stop monitor</p></td>
</tr>
<tr class="even">
<td data-valign="top" width="30.155%"><p>F-SWITCH</p></td>
<td data-valign="top" width="18.543%"><p>SWITCH</p></td>
<td data-valign="top" width="51.303%"><p>Switching monitoring files<br />
(log, statistics file)</p></td>
</tr>
<tr class="odd">
<td data-valign="top" width="30.155%"><p>F-CLOSEAPI</p></td>
<td data-valign="top" width="18.543%"><p>CLOSEAPI</p></td>
<td data-valign="top" width="51.303%"><p>Freeing resources allocated at the opening of the communication
medium</p></td>
</tr>
</tbody>
</table>

For more details on the parameter syntax for each command, refer to
the [Command index](../../../../c_intro_userinterfaces/command_summary).

If &lt;param> is not defined, CFTU
takes the default name.

As these media are not available on all systems, an availability check
is performed by the function.

## Return codes

<table data-bgcolor="#FFFFFF" data-cellspacing="0">
<thead>
<tr class="header">
<th><p>Mnemonic</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td data-valign="top" width="31.895%"><p>CAPI-NOERR</p></td>
<td data-valign="top" width="68.105%"><p>No error</p></td>
</tr>
<tr class="even">
<td data-valign="top" width="31.895%"><p>CAPI-FUNC-UNDEF</p></td>
<td data-valign="top" width="68.105%"><p>Command not valid</p></td>
</tr>
<tr class="odd">
<td data-valign="top" width="31.895%"><p>CAPI-CMD-LENGTH</p></td>
<td data-valign="top" width="68.105%"><p><span>Transfer CFT</span> command string invalid, does not exist, or
greater than 1024 characters long </p></td>
</tr>
<tr class="even">
<td data-valign="top" width="31.895%"><p>CAPI-KEY-NAME</p></td>
<td data-valign="top" width="68.105%"><p>Command syntax incorrect: keyword name incorrect</p></td>
</tr>
<tr class="odd">
<td data-valign="top" width="31.895%"><p>CAPI-KEY-VALUE</p></td>
<td data-valign="top" width="68.105%"><p>Command syntax incorrect: keyword value incorrect</p></td>
</tr>
<tr class="even">
<td data-valign="top" width="31.895%"><p>CAPI-MEM-GET</p></td>
<td data-valign="top" width="68.105%"><p>Memory allocation error</p></td>
</tr>
<tr class="odd">
<td data-valign="top" width="31.895%"><p>CAPI-MEM-FREE</p></td>
<td data-valign="top" width="68.105%"><p>Memory de-allocation error</p></td>
</tr>
<tr class="even">
<td data-valign="top" width="31.895%"><p>CAPI-INT-ERR1</p></td>
<td data-valign="top" width="68.105%"><p>Internal error 1</p></td>
</tr>
<tr class="odd">
<td data-valign="top" width="31.895%"><p>CAPI-INT-ERR2</p></td>
<td data-valign="top" width="68.105%"><p>Internal error 2</p></td>
</tr>
<tr class="even">
<td data-valign="top" width="31.895%"><p>CAPI-INT-ERR3</p></td>
<td data-valign="top" width="68.105%"><p>Internal error 3</p></td>
</tr>
</tbody>
</table>

## Error messages

The FIELD and MSG fields of the CFTAPI COPY CLAUSE contain:

-   FIELD: name of
    the incorrect parameter detected by the Transfer CFT syntax analyzer
-   MSG:
-   Either a message
    relative to the error recognized by the syntax analyzer
-   Or an error
    message describing an incident when the command is taken into account

See [Messages
and error codes](../../../../troubleshoot_intro/messages_and_error_codes_start_here).

If no error is detected, the FIELD and MSG fields are blank.
