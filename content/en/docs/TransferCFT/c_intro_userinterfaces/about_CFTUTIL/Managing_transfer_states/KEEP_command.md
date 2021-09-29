{
    "title": "KEEP - Suspending transfers",
    "linkTitle": "KEEP - Suspending transfers",
    "weight": "340"
}# <span id="kanchor25"></span><span id="Title"></span>KEEP - Suspend transfers

This topic describes the KEEP command, which is used to <span id="About_the_KEEP_Command"></span>suspend
one or all of the send, or one or all of the receive, transfers with selected
partners.

The difference between suspending and interrupting, a HALT, is that
the transfer can only be restarted by a manual operator command, the START
command.

The suspended transfers are set to the K
phasestep. The monitor ensures the integrity of the data in case of suspension
and, depending on the protocol used, authorizes the restarting of the
transfer from the last synchronization point set before the interruption,
or simply from the beginning of the file.

<table data-cellspacing="0" width="90%">
<thead>
<tr class="header">
<th>Parameters</th>
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
<td><a href="diagc.htm">DIAGC</a></td>
<td width="59.777%">Protocol diagnostic code</td>
</tr>
<tr class="odd" data-valign="top">
<td><a href="../../../command_summary/parameter_intro/diagp">DIAGP</a></td>
<td width="59.777%">Complimentary diagnostic information</td>
</tr>
<tr class="even" data-valign="top">
<td><p><a href="../../../command_summary/parameter_intro/direct">DIRECT</a> </p></td>
<td width="59.777%"><p>Transfer direction for the requests in question.</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p><a href="../../../command_summary/parameter_intro/ida">IDA</a> </p></td>
<td width="59.777%"><p>Local identifier of the transfer assigned by the user or
user application.</p>
<p>Several catalog entries may be associated with a given
IDA. There is no default value.</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p><a href="../../../command_summary/parameter_intro/idf">IDF</a> </p></td>
<td width="59.777%"><p>Model file identifier.</p>
<p>Several catalog entries may be associated with a given
IDF. There is no default value.</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p><a href="../../../command_summary/parameter_intro/idu">IDT</a> </p></td>
<td width="59.777%"><p>Transfer identifier.</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p><a href="../../../command_summary/parameter_intro/idtu">IDTU</a> </p></td>
<td width="59.777%"><p>Transfer local counter identifier.</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><a href="kdate.htm">KDATE</a></td>
<td width="59.777%">Command deposit date.</td>
</tr>
<tr class="even" data-valign="top">
<td><a href="ktime.htm">KTIME</a></td>
<td width="59.777%">Command deposit time.</td>
</tr>
<tr class="odd" data-valign="top">
<td><p><a href="../../../command_summary/parameter_intro/part">PART</a></p></td>
<td width="59.777%"><p>Partner identifier.</p>
<p>The associated value of this parameter can be either a:</p>
<ul>
<li><em>Identifier</em>:
the command only concerns the transfers with this partner</li>
<li><em>Mask</em>:
the command concerns the transfers with the partners, whose identifiers
correspond to this mask</li>
</ul></td>
</tr>
<tr class="even" data-valign="top">
<td><a href="phase.htm">PHASE</a></td>
<td width="59.777%">Phase of a catalog entry.</td>
</tr>
<tr class="odd" data-valign="top">
<td><a href="phasestep.htm">PHASESTEP</a></td>
<td width="59.777%">Phase step of a catalog entry.</td>
</tr>
<tr class="even" data-valign="top">
<td><a href="../../../command_summary/parameter_intro/scope">SCOPE</a></td>
<td width="59.777%">Scope &lt;PARENT&gt; ('PARENT','ALL','CHILDREN').</td>
</tr>
<tr class="odd" data-valign="top">
<td><a href="../../../command_summary/parameter_intro/state">STATE</a></td>
<td width="59.777%">Transfer request state.</td>
</tr>
</tbody>
</table>

#### Example 1

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>KEEP PART = PARIS2</td>
</tr>
</tbody>
</table>

This command suspends all transfers (IDT = \* by default) in the send
and receive directions (DIRECT = BOTH by default) with the partner PARIS2.

#### Example 2

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>KEEP</p>
<p>PART = PARIS*,</p>
<p>IDF = PAY,</p>
<p>DIRECT = RECV</p></td>
</tr>
</tbody>
</table>

This command suspends the receiving of the file PAY from a partner,
whose identifier begins with PARIS.

## Modify transfer entries parameters

The following tables describes the parameters used to modify a transfer entry in the catalog.

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>Command</th>
<th>Parameter</th>
<th>Value</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td rowspan="2">KEEP</td>
<td>DIAGC</td>
<td>string</td>
<td>Specify a comment.</td>
</tr>
<tr class="even">
<td>DIAGP</td>
<td>string</td>
<td>Specify a comment.</td>
</tr>
</tbody>
</table>
