{
    "title": "srcports",
    "linkTitle": "srcports",
    "weight": "3300"
}### <span id="srcports"></span>srcports

This parameter is obsolete for CFTNET proxies.

#### CFTNET

\[ SRCPORTS = {str15, str15, ... str15} \]

A list of local ports that can contain up to 16 instances of str15. Use this parameter to define ranges of available local ports according to your environment (depending on firewall settings).

Outgoing port definitions are:

-   Default (5000 - 65535)

Examples

This defines
3 outgoing port ranges:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>SRCPORTS=(6000-6009,6010-6019,6020-6030)</td>
</tr>
</tbody>
</table>

Operating system port selection:
  

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>SRCPORTS= ()</td>
</tr>
</tbody>
</table>

1 port range
is still possible

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>SRCPORTS=(6000-6030)</td>
</tr>
</tbody>
</table>

[Return to Command index](../../)
