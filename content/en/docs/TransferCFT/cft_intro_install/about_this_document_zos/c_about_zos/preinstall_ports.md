{
    "title": "Ports ",
    "linkTitle": "Ports ",
    "weight": "180"
}The following list contains the default Transfer CFT port numbers used for installation. You can check in advance that these ports do not conflict with ports used by other applications on the same machine.

You may need to modify the default port numbers, depending on your configuration.

The Internet Assigned Numbers Authority (IANA) reserves the TCP ports 1761-1768 for Transfer CFT. For more information, refer to: [www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers](http://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml?&page=31).

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>Component</th>
<th><p>Port</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>PeSIT</td>
<td>1761</td>
</tr>
<tr class="even">
<td>SSL</td>
<td>1762</td>
</tr>
<tr class="odd">
<td>SFTP</td>
<td>1763</td>
</tr>
<tr class="even">
<td>COMS</td>
<td>1765</td>
</tr>
<tr class="odd">
<td>Copilot</td>
<td>1766</td>
</tr>
<tr class="even">
<td>Transfer CFT UI (Copilot) server for <span>Central Governance</span></td>
<td>1767</td>
</tr>
<tr class="odd">
<td>REST API</td>
<td>1768</td>
</tr>
<tr class="even">
<td><span>Central Governance</span></td>
<td>12553</td>
</tr>
<tr class="odd">
<td><span>Central Governance</span> SSL</td>
<td>12554</td>
</tr>
<tr class="even">
<td><p><span>Secure Relay</span> MA</p>
<p>ma.comm_port</p></td>
<td><p> </p>
<p>6801</p></td>
</tr>
<tr class="odd">
<td><p><span>Secure Relay</span> RA</p>
<ul>
<li>ra.comm_port</li>
<li>ra.admin_port</li>
</ul></td>
<td><p> </p>
<ul>
<li>6811</li>
<li>6810</li>
</ul></td>
</tr>
</tbody>
</table>

Legend:

-   PeSIT (PESITANY protocol): PeSIT in plain text
-   SSL: PeSIT protocol over SSL/TLS
-   COMS: Synchronous transfers
-   Copilot: Provides access to Transfer CFT UI server from a user Internet browser
-   Copilot for Central Governance: Provides secure access for Central Governance (mutual authentication)
-   Central Governance: Used to connect to Central Governance
