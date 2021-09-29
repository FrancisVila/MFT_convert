{
    "title": "START - Restarting transfers",
    "linkTitle": "START - Restarting transfers",
    "weight": "370"
}# <span id="kanchor7"></span><span id="Title"></span>START - Restart transfers

This topic describes the START command and its parameters.

Only the Transfer CFT requesting the transfer can initiate
a START command.

Transfers in the H or K phasestep in the catalog change to
the D phasestep, after this command is executed. These transfers are restarted
after scanning the catalog if the required resources are available.

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>ODETTE</p></td>
<td><p>The START command has no effect on the interruption of
a RECV command. Transfer CFT in this case operates in server mode and
no restart is possible. A new RECV command has to be activated to restart
transfers.</p></td>
</tr>
</tbody>
</table>

<table data-cellspacing="0" width="90%">
<thead>
<tr class="header">
<th>Parameter</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd" data-valign="top">
<td><p><a href="../../../command_summary/parameter_intro/blknum">BLKNUM</a> </p></td>
<td width="59.777%"><p>Catalog block number. If the values '*' or ' ' are used
then all transfers are selected regardless of the block that they belong
to.</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p><a href="../../../command_summary/parameter_intro/direct">DIRECT</a> </p></td>
<td width="59.777%"><p>Transfer direction for the requests in question.</p>
<p>The possible values are:</p>
<ul>
<li><span>BOTH</span>: (default) takes both send transfers
and receive transfers into account</li>
<li><span>RECV</span>: limits the action to receive transfers</li>
<li><span>SEND</span>: limits the action to send transfers</li>
</ul></td>
</tr>
<tr class="odd" data-valign="top">
<td><p><a href="../../../command_summary/parameter_intro/force">FORCE</a> </p></td>
<td width="59.777%"><p>Indicates whether a request, that was not executed during
its time slot should be forced to immediately restart.</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p><a href="../../../command_summary/parameter_intro/ida">IDA</a></p></td>
<td width="59.777%"><p>Local identifier of the transfer assigned by the user or
user application.</p>
<p>Several catalog entries may be associated with a given
IDA. There is no default value.</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p><a href="../../../command_summary/parameter_intro/idf">IDF</a> </p></td>
<td width="59.777%"><p>Model file identifier.</p>
<p>Several catalog entries may be associated with a given
IDF. There is no default value.</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p><a href="../../../command_summary/parameter_intro/idu">IDT</a> </p></td>
<td width="59.777%"><p>Transfer identifier.</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p><a href="../../../command_summary/parameter_intro/idtu">IDTU</a> </p></td>
<td width="59.777%"><p>Transfer local counter identifier.</p></td>
</tr>
<tr class="even" data-valign="top">
<td><a href="kdate.htm">KDATE</a></td>
<td width="59.777%">Command deposit date</td>
</tr>
<tr class="odd" data-valign="top">
<td><a href="ktime.htm">KTIME</a></td>
<td width="59.777%">Command deposit time</td>
</tr>
<tr class="even" data-valign="top">
<td><a href="phase.htm">PHASE</a></td>
<td width="59.777%">Phase of a catalog entry</td>
</tr>
<tr class="odd" data-valign="top">
<td><a href="phasestep.htm">PHASESTEP</a></td>
<td width="59.777%">Phase step of a catalog entry</td>
</tr>
<tr class="even" data-valign="top">
<td><a href="../../../command_summary/parameter_intro/scope">SCOPE</a></td>
<td width="59.777%">Scope &lt;PARENT&gt; ('PARENT','ALL','CHILDREN')</td>
</tr>
<tr class="odd" data-valign="top">
<td><a href="../../../command_summary/parameter_intro/state">STATE</a></td>
<td width="59.777%">Transfer request state</td>
</tr>
<tr class="even" data-valign="top">
<td><p><a href="../../../command_summary/parameter_intro/part">PART</a> </p></td>
<td width="59.777%"><p>Partner identifier.</p>
<p>The value of this parameter may be:</p>
<ul>
<li>an <em>identifier</em>:
the command only concerns the transfers with this partner</li>
<li>a <em>mask</em>:
the command concerns the transfers with the partners, whose identifiers
correspond to this mask</li>
</ul></td>
</tr>
</tbody>
</table>

#### Example 1

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>START</p>
<p> PART = PARIS5</p></td>
</tr>
</tbody>
</table>

Restarts all the transfers, IDT = \* by default, in the send and receive
directions, DIRECT = BOTH by default, with the partner PARIS5.

#### Example 2

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>START</p>
<p> PART = PARIS5,</p>
<p> IDF = PAY,</p>
<p> DIRECT = RECV</p></td>
</tr>
</tbody>
</table>

Restarts the receive transfers for the PAY IDF from the partner PARIS5.
