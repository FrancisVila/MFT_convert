{
    "title": "Transfer services",
    "linkTitle": "Transfer services",
    "weight": "250"
}# <span id="Transfer_services"></span>Transfer services

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
