{
    "title": "Configuring OFTP",
    "linkTitle": "Configuring OFTP",
    "weight": "160"
}# <span id="About_the_Odette_Configuration"></span><span id="Configuring_Odette"></span>Configuring OFTP (ODETTE)

This topic describes the objects
that you must configure to use the OFTP protocol, before submitting a file transfer. The following list describes
each of the Transfer CFT objects. Each of these objects topics indicates
the parameters that you must set to complete the Transfer CFT OFTP configuration.

-   CFTPROT: defines
    both the application protocol type and profile
-   CFTPART: defines
    a partner and list the possible protocols for communicating with this
    partner
-   CFTxxx: is a generic
    command that defines the network parameters associated with this partner,
    for a network connection CFTTCP
-   CFTNET: defines
    the network resources associated with the protocol

The configuration is recorded in a text file interpreted by the Transfer
CFT utility, the syntax analyzer, which updates the Transfer CFT PARAMETER
and PARTNER files.

## <span id="CFTPROT_parameters_in_OFTP"></span>CFTPROT parameters in OFTP

To designate the Odette protocol, set the TYPE parameter to ODETTE.

### <span id="Restart_file_transfer"></span>Restart file transfer

To allow a restart of a file transfer interrupted during a previous
session, set the RESYNC parameter to YES.

-   If RESYNC = YES and a transfer has been interrupted (H state in the
    catalog), the transfer is resumed from the last synchronization point
    acknowledged during the previous attempt.
-   If RESYNC = NO, no attempt is made in the session to restart interrupted
    transfers, and the CFTT71E PART=&lt;part> IDF=&lt;idf> IDT=&lt;idt> remote creation reject 123 message displays in the CFTLOG file.

### <span id="Read_time_out"></span>Read time-out

To specify the read time-out for a response, set the RTO parameter. This corresponds to the wait time-out for a response to an "FPDU"
before it is assumed that communication has been interrupted. This time-out
is also used for Transfer CFT internal events.

### <span id="Data_compression"></span>Data compression

To request data compression when sending or receiving a transfer, set
the SCOMP and RCOMP parameters to 1.

These parameters are negotiated with the partner’s symmetrical parameter
during the connection phase. The smallest value is retained by Transfer
CFT as the compression option for the session.

### <span id="Synchronization_interval"></span>Synchronization interval

To
specify the synchronization interval, set the SCREDIT and RCREDIT parameters.

These parameters correspond to the maximum number of network messages
(NSDU) consecutively sent by the requester before the server acknowledges
their reception. Once the maximum number of network messages has been
sent, the requester has to wait for permission from the server (reception
of a FPDU CDT = FPDU from CREDIT) before sending other data.

These parameters are negotiated with the partner’s symmetrical parameter
during the connection phase. After negotiation, the smallest value is
selected by Transfer CFT as the CREDIT window (=synchronization interval).

In all cases, the end of the transfer phase (characterized by the sending
of a FPDU EFID) sets the local value of the authorized CREDIT to zero
(which is equivalent to a data transfer inhibition). Authorization to
transfer data again is granted at the next application connection request
(sending of a FPDU SFID). This means that the sending of a FPDU SFID sets
the local CREDIT value to the CREDIT value negotiated during the connection
phase.

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">In accordance with the operation
of the Transfer CFT transfer monitor, a transfer in process is acknowledged
by determining synchronization points. These points acknowledge the data
which have just been transferred. With the Odette protocol, the synchronization
points are taken each time a CREDIT is received or sent. All the data
sent are consequently acknowledged when the requester receives a CREDIT.
Conversely, the previously received data are acknowledged when the Server
sends a CREDIT. The CREDIT value ranges from 1 to 999. The recommended
value is *CREDIT = 4 .</td>
</tr>
</tbody>
</table>

### <span id="Two_way_exchanges"></span>Two-way exchanges

To specify the direction of transfers for each partner, you can use
the following parameters to set the SRIN and SROUT parameters to:

-   SENDER: the partner
    can only send files
-   RECEIVER: the partner
    can only receive files
-   BOTH: the partner
    can send and receive files

SRIN controls the direction of transfers authorized for the Transfer
CFT monitor when it is server, responder, while SROUT controls the direction
of transfers authorized for the Transfer CFT monitor when it is server
as  initiator.

When the value of SROUT and SRIN is not BOTH, the consistency between
the parameters is verified. If the value of one, or both, of these two
parameters is BOTH, the final value is negotiated between the partners
as displayed in the table below. The value SROUT is the transfer direction
proposed by site A, and SRIN is the transfer direction determined by site
B.

<table data-cellspacing="0">
<thead>
<tr class="header">
<th><p>If...</p></th>
<th><p>Then the final values are...</p></th>
</tr>
</thead>
<tbody>
<tr class="odd" data-valign="top">
<td><p>SROUT = BOTH and SRIN = SENDER</p></td>
<td width="50%"><p>SROUT = RECEIVER and SRIN = SENDER</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>SROUT = BOTH and SRIN = RECEIVER</p></td>
<td width="50%"><p>SROUT = SENDER and SRIN = RECEIVER</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>SRIN = BOTH and SROUT = SENDER</p></td>
<td width="50%"><p>SROUT = SENDER and SRIN = RECEIVER</p></td>
</tr>
<tr class="even" data-valign="top">
<td><p>SRIN = BOTH and SROUT = RECEIVER</p></td>
<td width="50%"><p>SROUT = RECEIVER and SRIN = SENDER</p></td>
</tr>
<tr class="odd" data-valign="top">
<td><p>SRIN  = BOTH and SROUT = BOTH</p></td>
<td width="50%"><p>SROUT = BOTH and SRIN = BOTH</p></td>
</tr>
</tbody>
</table>

The [SRIN](../../../c_intro_userinterfaces/command_summary/parameter_intro/srin) parameter,
present in the Start Session IDentification, serves as a basis for negotiation
for the FPDU SSID RESPONSE.

The SROUT parameter is present in the connection FPDU SSID.

### <span id="NSDU_size"></span>NSDU size

To set the maximum size of the NSDU, Network
Service Data
Unit, for transmission and reception
set the [SRUSIZE](../../../c_intro_userinterfaces/command_summary/parameter_intro/srusize)
and [RRUSIZE](../../../c_intro_userinterfaces/command_summary/parameter_intro/rrusize).

These parameters are negotiated with the partner during the connection
phase. Transfer CFT selects the smallest value as the maximum size for
network messages. This size, expressed in bytes, includes the control
characters conveyed by the ODETTE protocol (control byte, file record
control byte).

The selected value must be:

-   Between 128 and 32750
-   Greater than the
    maximum article size likely to be sent

### Processing method used for protocol messages

When setting the TCP parameter with CFTPROT TYPE=ODETTE command, note that:

-   TCP=OFTP: Messages are compliant with the RFC 2204 (default value).
-   TCP=CFT: Method is specific to Transfer CFT and may not be compatible with other transfer files products. This means that Odette transfer errors can be due to this incompatibly.
