{
    "title": "Store and forward restrictions",
    "linkTitle": "Store and forward restrictions",
    "weight": "180"
}PeSIT makes it possible to route files from one computer
to another. The store and forward mode is only defined and supported
by Transfer CFT in write transfer cases. This
topic provides information concerning the PeSIT services,
and the PI codes of associated FPDUs involved in file store and forward.

Specifically, this topic describes the FPDU functions:

-   Establishing a
    connection
-   Selecting the file
-   Transfer acknowledgement

### <span id="Establishing_the_connection__FPDU_CONNECT"></span>Establishing the connection: FPDU CONNECT

The connection phase directly connects partners in pairs. The parameters
contained in the connection FPDUs are local.

The PI 3 and PI 4 codes are defined using the NSPART
and NRPART parameters of the CFTPART object which defines
the adjacent routing node (and not the parameters which describe the final
recipient). However, the adjacent transit node is defined by the IPART
parameter of the CFTPART command which describes the final recipient.
See the Store and forward paragraph of the Transfer CFT specific
PI codes topic.

### <span id="Selecting_the_file__FPDU_CREATE"></span>Selecting the file: FPDU CREATE

From the selecting file to be transferred phase onwards, there are three
things to be distinguished:

-   Partners performing
    the transfer: these partners are the requester and the server of the PeSIT
    connection, defined above in the FPDU CONNECT
-   Partners on behalf
    of which the transfer is made: these partners are the initial sender and
    final recipient of the file
-   Parameters which
    have to be conveyed during the successive connections required to transfer
    the file through the various nodes of the network

For these reasons, the E version of PeSIT implements a more precise
addressing within FPDU CREATE:

-   PI
    3 and PI 4 codes define the names of the initial and final
    users and applications

These codes are defined by Transfer CFT using the
SAPPL, RAPPL, SUSER and RUSER parameters of
the CFTSEND or SEND commands and are sent by Transfer CFT
from the beginning to the end of the transfer.

-   PI
    61 and PI 62 define the partners on behalf of which the transfer
    is performed: these are the initial sender and final recipient of the
    file to be transferred.

These codes are defined using the NSPART
and NRPART parameters of the CFTPART command which defines
the final recipient on the initial site. These codes are sent by Transfer
CFT from the beginning to the end of the transfer, allowing the relay
monitors to perform any routing required to the next computer.

The PeSIT protocol defines three other PI codes of the FPDU CREATE which
contribute to the unambiguous identification of the transfer. The following
PI codes are consequently sent by Transfer CFT from beginning to end:

-   PI
    11 file type
-   PI
    12 file name
-   PI
    13 transfer identify

### <span id="Transfer_acknowledgement__FPDU_MSG"></span>Transfer acknowledgement: FPDU MSG

The final recipient of the file can indicate to the initial sender that
the transfer took place correctly. This end to end acknowledgement uses
the FPDU MSG of the PeSIT protocol and is initiated by the Transfer CFT
SEND TYPE = REPLY, ... command. The table below summarizes how
Transfer CFT defines the PI codes associated with the acknowledgement
message FPDU.

FPDU related PI codes and the corresponding
Transfer CFT values

<table data-cellspacing="0" width="90%">
<thead>
<tr class="header">
<th>PI</th>
<th>Description</th>
<th>Transfer
CFT value</th>
</tr>
</thead>
<tbody>
<tr class="odd" data-valign="middle">
<td data-valign="top" width="6%"><p>3 </p></td>
<td data-valign="top" width="35%"><p>Sending application’s name<br />
Sending user’s name </p></td>
<td data-valign="top" width="60%"><p>PI 4 of the acknowledged file creation request </p></td>
</tr>
<tr class="even" data-valign="middle">
<td data-valign="top" width="6%"><p>4 </p></td>
<td data-valign="top" width="35%"><p>Receiver application name<br />
Receiver user name </p></td>
<td data-valign="top" width="60%"><p>PI 4 of the acknowledged file creation request </p></td>
</tr>
<tr class="odd" data-valign="middle">
<td data-valign="top" width="6%"><p>11 </p></td>
<td data-valign="top" width="35%"><p>File type </p></td>
<td data-valign="top" width="60%"><p>PI 11 of the acknowledged file creation request </p></td>
</tr>
<tr class="even" data-valign="middle">
<td data-valign="top" width="6%"><p>12 </p></td>
<td data-valign="top" width="35%"><p>File name </p></td>
<td data-valign="top" width="60%"><p>PI 12 of the acknowledged file creation request </p></td>
</tr>
<tr class="odd" data-valign="middle">
<td data-valign="top" width="6%"><p>13 </p></td>
<td data-valign="top" width="35%"><p>Transfer ident. </p></td>
<td data-valign="top" width="60%"><p>PI 13 of the acknowledged file creation request </p></td>
</tr>
<tr class="even" data-valign="middle">
<td data-valign="top" width="6%"><p>14 </p></td>
<td data-valign="top" width="35%"><p>Requested attributes </p></td>
<td data-valign="top" width="60%"><p>(not set) </p></td>
</tr>
<tr class="odd" data-valign="middle">
<td data-valign="top" width="6%"><p>16 </p></td>
<td data-valign="top" width="35%"><p>Data code </p></td>
<td data-valign="top" width="60%"><p>(not set) </p></td>
</tr>
<tr class="even" data-valign="middle">
<td data-valign="top" width="6%"><p>51 </p></td>
<td data-valign="top" width="35%"><p>Creation date<br />
Creation time </p></td>
<td data-valign="top" width="60%"><p>PI 51 of the acknowledged file creation request </p></td>
</tr>
<tr class="odd" data-valign="middle">
<td data-valign="top" width="6%"><p>61 </p></td>
<td data-valign="top" width="35%"><p>Initial sender</p></td>
<td data-valign="top" width="60%"><p>PI 62 of the acknowledged file creation request </p></td>
</tr>
<tr class="even" data-valign="middle">
<td data-valign="top" width="6%"><p>62 </p></td>
<td data-valign="top" width="35%"><p>Final receiver</p></td>
<td data-valign="top" width="60%"><p>PI 61 of the acknowledged file creation request </p></td>
</tr>
<tr class="odd" data-valign="middle">
<td data-valign="top" width="6%"><p>91 </p></td>
<td data-valign="top" width="35%"><p>Message </p></td>
<td data-valign="top" width="60%"><p>MSG parameter of the SEND command </p></td>
</tr>
</tbody>
</table>

 

Most of the acknowledgement message PI codes are defined using the protocol
parameters which were specified at the time of the creation request (FPDU
CONNECT) for the file considered. Transfer CFT holds this information
in the catalog entry for the corresponding transfer. These are the IDT
and PART parameters of the SEND TYPE = REPLY command which allows
this catalog entry to be located.
