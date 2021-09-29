{
    "title": "Receiving files",
    "linkTitle": "Receiving files",
    "weight": "210"
}This command is used to request the reception of files from a designated partner.

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">When using the PeSIT protocol, you cannot create a request for messages or replies.</td>
</tr>
</tbody>
</table>

The RECV command is executed at the level of a receiver/requester (requester because it initiated the connection). The partner is therefore the sender/server.

The characteristics of a receive transfer request can be specified in the RECV command itself or in the Central Governance flow definition, where the IDF is equal to the flow IDENTIFIER itself, or in the CFTRECV command, the ID of which is equal to the value of the IDF parameter.

When receiving files you can define parameters related to the following categories.

Free parameters
for the Transfer CFT user, such as adding comments to the transfer:

-   Sent to the
    sender
-   Local parameters

Execution control
parameters, such as specify the scheduling time for a transfer:

-   General
-   User
-   Schedule management

<!-- -->

-   Data processing
    parameters

Parameters associated
with the file received, for example the file name:

-   File management
-   Physical name
-   Physical characteristics
    (whole file)
-   Physical characteristics
    (records)
