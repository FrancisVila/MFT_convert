{
    "title": "Synchronous communication services",
    "linkTitle": "Synchronous communication services",
    "weight": "260"
}# <span id="Synchronous_communication_services"></span>Synchronous communication services

This topic describes Transfer CFT synchronous communication services.

## Description of functions

<table data-cellspacing="0">
<thead>
<tr class="header">
<th><p>Function</p></th>
<th><p>Use</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>COM</p></td>
<td><p>Set the communication medium</p></td>
</tr>
<tr class="even">
<td><p>GETXINFO</p></td>
<td><p>Retrieve information concerning the last transfer made
from a synchronous request after a request of the following types: SEND,
RECV, HALT, KEEP, START, RESUME, DELETE, END, SUBMIT, SWITCH, PURGE.</p>
<p>The information is stored in a cftApiInf-type structure:</p>
<ul>
<li>Transfer
state</li>
<li>Diagnostic</li>
<li>Diagnostic
protocol</li>
<li>Value
of the PART field of CFTPARM</li>
<li>Transfer
identifier (IDT)</li>
<li>Local
transfer identifier (IDTU)</li>
<li>Transfer
type (single, cyclical, diffusion list, collection, file group)</li>
<li>Public
reference of the transfer (only for a single transfer in Send)</li>
</ul>
<p>The GETXINFO action returns an error if the communication
medium is not synchronous.</p>
<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">The public
reference of the transfer is a character string of variable length. In
the PESIT protocol, it contains 'pi13.pi3.pi4.pi11.pi12.pi61.pi62'.</td>
</tr>
</tbody>
</table></td>
</tr>
</tbody>
</table>
