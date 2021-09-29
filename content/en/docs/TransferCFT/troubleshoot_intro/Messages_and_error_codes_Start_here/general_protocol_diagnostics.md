{
    "title": "General protocol diagnostics",
    "linkTitle": "General protocol diagnostics",
    "weight": "470"
}# <span id="title"></span>General Transfer CFT protocol diagnostics

## <span id="Diagnostics_format"></span>Diagnostics format

The following table defines the DIAGP formats.

DIAGP Formats

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>Format</th>
<th>Meaning</th>
</tr>
</thead>
<tbody>
<tr class="odd" data-valign="top">
<td width="23.696%"><p>XXXXXXXX</p></td>
<td width="76.304%"><p>Mnemonic code</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="23.696%"><p>L HH HHH</p></td>
<td width="76.304%"><p>Local rejection of network connection</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="23.696%"><p>R HH HHH</p></td>
<td width="76.304%"><p>Remote rejection of network connection</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="23.696%"><p>HHHHHHHH</p></td>
<td width="76.304%"><p>Error in the system or network software at operating system
level</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="23.696%"><p>eNNsNN</p></td>
<td width="76.304%"><p>(PeSIT) Unexpected event in the automaton</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="23.696%"><p>PDU iNN</p></td>
<td width="76.304%"><p>(PeSIT) FPDU does not conform to the specifications</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="23.696%"><p>XXX NNN</p></td>
<td width="76.304%"><p>(PeSIT) Received FPDU contains a diagnostic message</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="23.696%"><p>NNN HHHH</p></td>
<td width="76.304%"><p>(ODETTE) Received message contains a diagnostic message</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="23.696%"><p>XXX HHHH</p></td>
<td width="76.304%"><p>(ODETTE) Negotiation or send error</p></td>
</tr>
</tbody>
</table>

## "Mnemonic"-Type DIAGP Codes

A "Mnemonic"-type DIAGP is a "character string"
value providing information on the type of catalog entry or the status
of the transfer associated with this entry. Some codes are specific to
a single protocol.

Specific codes

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>Code</th>
<th>Protocol</th>
<th>Meaning</th>
</tr>
</thead>
<tbody>
<tr class="odd" data-valign="top">
<td width="23.623%"><p>ABOI_CD</p></td>
<td width="20.746%"><p>ODETTE</p></td>
<td width="55.631%"><p>CD send following reception of an ABORT indication (case
of a RECV IDF=* command)</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="23.623%"><p>ABORT</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p><span>Transfer CFT</span> transfer abort request</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="23.623%"><p>ABORT_I</p></td>
<td width="20.746%"><p>ODETTE</p></td>
<td width="55.631%"><p>ABORT caused by the protocol engine, following detection
of an error</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="23.623%"><p>CALL OUT</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>Call not made within the authorized call period (see OMINTIME/OMAXTIME
- OMINDATE/OMAXDATE parameters of commands CFTPART, etc.)</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="23.623%"><p>CATUPDT</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>Catalog update error (at sync point)</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="23.623%"><p>CD_ODT</p></td>
<td width="20.746%"><p>ODETTE</p></td>
<td width="55.631%"><p>(information) Indication of a "generic" entry
for file reception</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="23.623%"><p>CLOSE_RN</p></td>
<td width="20.746%"><p>ODETTE</p></td>
<td width="55.631%"><p>Reception of a "negative CLOSE RESP" interaction
from the file access task: error closing the file sent</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="23.623%"><p>CREA_RN</p></td>
<td width="20.746%"><p>ODETTE</p></td>
<td width="55.631%"><p>Reception of a "negative CREATE RESP" interaction
from the file access task: error creating the receive file</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="23.623%"><p>COLLECT</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>Indication of a "generic" entry for file collection.
This entry does not correspond to an actual transfer</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="23.623%"><p>CP</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>Transfer performed without the compression option. This
can be caused by the REQUESTER or SERVER partner as compression is negotiated</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="23.623%"><p>NONE</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p> </p></td>
</tr>
<tr class="even" data-valign="top">
<td width="23.623%"><p>CP nn%</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>Transfer performed with the compression option. The compression
rate is then displayed. This rate expresses the number of bytes to be
sent in relation to the number of bytes actually sent. The number of bytes
to be sent may be different from the number of bytes in the file if the
<span>Transfer CFT</span> truncates or pads records, depending on the parameter settings</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="23.623%"><p>DAY CYC</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>Indication of a "generic" entry for cyclic transfers
(days). This entry does not correspond to an actual transfer</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="23.623%"><p>DIFFUS</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>Indication of a "generic" entry for file broadcasting.
This entry does not correspond to an actual transfer</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="23.623%"><p>DSEL_CN</p></td>
<td width="20.746%"><p>ODETTE</p></td>
<td width="55.631%"><p>Reception of a "negative DSELECT RESP" interaction
from the file access task: error deselecting the sent file</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="23.623%"><p>END_TFIL</p></td>
<td width="20.746%"><p>ODETTE</p></td>
<td width="55.631%"><p>Sending of a "RELEASE IND" interaction to the
file access task in order to stop the task (information)</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="23.623%"><p>ERR INC</p></td>
<td width="20.746%"><p>ODETTE</p></td>
<td width="55.631%"><p>Transfer ABORT - Reason not specified</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="23.623%"><p>ERRCOMP</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>File compression error - the compression type requested
is incompatible with the file data</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="23.623%"><p>ERR LREC</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>Error sending or receiving the file data. <span>Transfer CFT</span> detects an
invalid length for the data read or to be written</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="23.623%"><p>ERR_NCAR</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>Error in the number of characters sent</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="23.623%"><p>ERR_NREC</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>Error in the number of records</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="23.623%"><p>ERRPROT</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>Protocol error when switching directions</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="23.623%"><p>ERR_UFMT</p></td>
<td width="20.746%"><p>ODETTE</p></td>
<td width="55.631%"><p>Internal error when deformatting the received FPDU</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="23.623%"><p>EVT</p></td>
<td width="20.746%"><p>ODETTE</p></td>
<td width="55.631%"><p>Reception of an unexpected event in the current phase of
the protocol automaton</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="23.623%"><p>ERRPASSW</p></td>
<td width="20.746%"><p>ODETTE</p></td>
<td width="55.631%"><p>Invalid partner LOGON password</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="23.623%"><p>EXAERR</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>Processing error in the directory EXIT task</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="23.623%"><p>EXARJT</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>Connection refusal via the directory EXIT task</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="23.623%"><p>EXATASK</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>Load error for the directory EXIT task</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="23.623%"><p>EXAWRSP</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>Waiting for a response from the directory EXIT task</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="23.623%"><p>EXIT</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>EXIT task initialization problem</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="23.623%"><p>FCON_RN</p></td>
<td width="20.746%"><p>ODETTE</p></td>
<td width="55.631%"><p>Session parameter negotiation error, implying a connection
rejection</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="23.623%"><p>FORMAT</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>FPDU formatting error</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="23.623%"><p>HOLD</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>Indication of an "on-hold" transfer, waiting
for a reception request</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="23.623%"><p>INACT</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>Transfer refused due to partner inactivity</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="23.623%"><p>INV XFER</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>Message transfer unauthorized with this protocol</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="23.623%"><p>LDT_TXT</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>Rusize is greater than MAXRUSIZE in "T"</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="23.623%"><p>LIST_FI</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>Indication of a "generic" entry for the file
list. This entry does not correspond to an actual transfer.</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="23.623%"><p>MALLOC</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>Cannot allocate the working area required for the transfer
dynamically</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="23.623%"><p>MAXCNX</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>The number of connection(s) for the resource (MAXCNX parameter
of the CFTNET command) has already been reached</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="23.623%"><p>MAXCV</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>The number of connection(s) for the partner has already been reached</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="23.623%"><p>MAXRETRY</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>Maximum number of retries exceeded (see the RETRY* parameters)</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="23.623%"><p>MAXRST</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>Maximum number of restarts for
a protocol exceeded (see the RESTART parameter of the CFTPROT command)</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="23.623%"><p>MAXTASK</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>Maximum
number of tasks exceeded (see
the MAXTASK parameter of the CFTPARM command)</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="23.623%"><p>MAXTRANS</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>Maximum
number of simultaneous transfers exceeded (see
the MAXTRANS parameter of the CFTPARM command)</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="23.623%"><p>MIN CYC</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>Indication of a "generic" entry for cyclic transfers
(minutes). This entry does not correspond to an actual transfer</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="23.623%"><p>MON CYC</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>Indication of a "generic" entry for cyclic transfers
(months). This entry does not correspond to an actual transfer.</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="23.623%"><p>MSG_NOAU</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>EERP send not authorized</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="23.623%"><p>MSG_RN</p></td>
<td width="20.746%"><p>ODETTE</p></td>
<td width="55.631%"><p>The EERP message has not been acknowledged by the partner</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="23.623%"><p>MYSELF</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>The target partner is the local site (CFTPARM PART)</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="23.623%"><p>NO AUTH</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>Non-authorized
partner or file (see the AUTH parameter, CFTAUTH command, and
the CFTPART security parameters)</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="23.623%"><p>NO NEW</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>Receive file already exists for a reception request: (CFT)RECV
FDISP=NEW</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="23.623%"><p>NO OLD</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>Receive file does not exist for a reception request: (CFT)RECV
FDISP=OLD</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="23.623%"><p>NO OPEN</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>Transfer in open mode not authorized (see the OPEN parameter
of the partner's CFTPART command)</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="23.623%"><p>NO PARM</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>Error due to incorrect <span>Transfer CFT</span> parameter settings</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="23.623%"><p>NO PART</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>Partner does not exist (no CFTPART command for this partner
identifier)</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="23.623%"><p>NO PROT</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>Protocol does not exist (no CFTPROT command for this protocol
identifier)</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="23.623%"><p>NO TURN</p></td>
<td width="20.746%"><p>ODETTE</p></td>
<td width="55.631%"><p>The <span>Transfer CFT</span> cannot hand over to the partner (CD) as the
partner handed over during the previous exchange</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="23.623%"><p>NO XLATE</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>CFTXLATE command not found for this transfer direction,
nor for the source and target alphabets</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="23.623%"><p>NOCALL</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>The partner cannot be called</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="23.623%"><p>NOCTX</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>Message for a missing or inactive context</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="23.623%"><p>NOSELECT</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>With the PeSIT protocol, SIT profile, the file selection
request (RECV command) is not authorized</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="23.623%"><p>NO_FILE</p></td>
<td width="20.746%"><p>ODETTE</p></td>
<td width="55.631%"><p>There are no more files to be sent (information)</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="23.623%"><p>NPART</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>REQUESTER
partner mismatch with SERVER partner in SIT profile. Strict naming and
consistency rules are imposed both by <span>Transfer CFT</span> and by the PESIT standard.</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="23.623%"><p>N_REL_I</p></td>
<td width="20.746%"><p>ODETTE</p></td>
<td width="55.631%"><p>Reception of a network outage indication</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="23.623%"><p>OPER</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>Transfer interrupt request by the operator</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="23.623%"><p>OUT TIME</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>The transfer has exceeded the authorized time slot (MAXDATE,
MAXTIME parameters of the command)</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="23.623%"><p>RECV ALL</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>Indication of a "generic" entry for global transfer
receptions on hold. This entry does not correspond to an actual transfer.</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="23.623%"><p>RELEASE</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>Unexpected network outage, caused by the remote partner
or the network</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="23.623%"><p>RESTART0</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>Transfer interruption (it will be restarted at the beginning
of the file)</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="23.623%"><p>RESTARTF</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>Transfer interruption (it will be restarted at the restart
point)</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="23.623%"><p>RTO</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p><span>Transfer CFT</span> time-out during the transfer phase. This time-out
corresponds to the RTO parameter of the CFTPROT command</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="23.623%"><p>R_PASSW</p></td>
<td width="20.746%"><p>ODETTE</p></td>
<td width="55.631%"><p>The password given by the partner does not correspond to
the parameter settings (CFTPART command).</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="23.623%"><p>SFNA</p></td>
<td width="20.746%"><p>ODETTE</p></td>
<td width="55.631%"><p>Reception of an SFNA FPDU corresponding to a session parameter
negotiation problem</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="23.623%"><p>SROUT</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>The partner cannot be called (SROUT parameter of the CFTPROT
command)</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="23.623%"><p>SSY TFIL</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>Error sending data to CFTTFIL</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="23.623%"><p>SYPOST</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>Communication error between <span>Transfer CFT</span> and the directory
EXIT task</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="23.623%"><p>TFIL</p></td>
<td width="20.746%"><p>ODETTE</p></td>
<td width="55.631%"><p>Reception of a transfer ABORT request originating from
the file access task</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="23.623%"><p>TIMEOUT</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>Monitoring time-out during the connection phase, due particularly
to a missing response to a pre-connection (LOGON) string or a CONNECT
FPDU. With the SIT profile, there is no pre-connection phase</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="23.623%"><p>TSK_EXIT</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>Error initializing a file EXIT task.</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="23.623%"><p>VRESID</p></td>
<td width="20.746%"><p>ODETTE</p></td>
<td width="55.631%"><p>Transfer ABORT caused by the reception of an ESID FPDU
(partner session termination request)</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="23.623%"><p>WF RENAM</p></td>
<td width="20.746%"><p> </p></td>
<td width="55.631%"><p>Cannot rename the temporary file (WFNAME parameter) in
FNAME, at the end of the transfer</p></td>
</tr>
</tbody>
</table>

## "L HH HHH"-Type DIAGP Codes

"L HH HHH"-type DIAGP codes correspond to network connection
rejection diagnostics. The character L indicates a local rejection. H
represents a hexadecimal digit.

The two hexadecimal numbers respectively represent:

-   REASON:
    a reason code according to the network context
-   DIAGN:
    a diagnostic code according to the network context

For the meaning of these codes, refer to the Network
Codes that correspond with the type of network used in the transfer.

## "R HH HHH"-Type DIAGP Codes

"R HH HHH"-type DIAGP codes correspond to network connection
rejection diagnostics. The character "R" indicates a remote
rejection. H represents a hexadecimal digit.

The two hexadecimal digits respectively represent:

-   REASON:
    a reason code according to the network context
-   DIAGN:
    a diagnostic code according to the network context

For the meaning of these codes, refer to the section Network
Codes corresponding to the type of network used by the transfer.

## <span id="HHHHHHHH___Type_DIAGP_Codes"></span>"HHHHHHHH"-Type DIAGP Codes

"HHHHHHHH"-type DIAGP codes correspond to the error diagnostics
specific to the network or system access software.

They are the "CS" or "NCS" codes.

Refer to
the manufacturer's documentation (system code or network codes, depending
on the type of occurrence).

## <span id="eNNsNN___Type_PeSIT_DIAGP_Codes"></span>"eNNsNN"-Type PeSIT DIAGP Codes

"eNNsNN"-type PeSIT DIAGP codes correspond to the diagnostics
representing an unexpected event in the protocol automaton (where N represents
a digit).

The two numbers respectively represent:

-   The
    event code for all protocols

For the meaning of this code, refer to [Event Codes (All
Protocols)](../event_codes).

-   The
    status code according to the protocol

For the meaning of this code, see
Status Codes for the appropriate
transfer protocol.

## <span id="PDU_iNN___Type_PeSIT_DIAG_Codes"></span>"PDU iNN"-Type PeSIT DIAGP Codes

"PDU iNN"-type PeSIT DIAGP codes correspond to the Transfer
CFT diagnostics representing the reception of a PeSIT FPDU that does not
conform to protocol specifications (where N represents a digit).

The code NN specifies the FPDU build error code.

For the meaning of this code, see [FPDU
Build Error Codes (PESIT).](#)

## <span id="XXX_NNN___Type_PeSIT_DIAG_Codes"></span>"XXX NNN"-Type PeSIT DIAGP Codes

"XXX NNN"-type PeSIT DIAGP codes correspond to the Transfer
CFT diagnostics representing the reception of an FPDU with an error diagnostic
code, where X represents a character and N a digit:

-   NNN
    indicates the PeSIT protocol diagnostic in the FPDU
    -   For the meaning of this code, refer to the section
        PESIT Protocol Diagnostic Code.
-   XXX
    represents the mnemonic code of the received FPDU - PeSIT protocol
    -   For the meaning of this code, refer to the section
        FPDU Mnemonic Codes PeSIT Protocol.

## <span id="NNN_HHHH_Type_ODETTE_DIAGP_Codes"></span>"NNN HHHH"-Type ODETTE DIAGP Codes

Transfer CFT diagnostic codes corresponding to the reception of an FPDU
with an error diagnostic code. H represents a hexadecimal digit and N
a digit:

-   NNN
    is a numeric value corresponding to the ODETTE protocol diagnostic code

For the meaning of this code, refer to the section
[Protocol Diagnostic Codes](../protocol_diagnostic_codes).

-   HHHH
    is a hexadecimal value corresponding to the Transfer CFT numeric code
    ODETTE protocol

See alsoTransfer CFT Numeric Codes ODETTE Protocol.

## <span id="XXX_HHHH_Type_ODETTE_DIAGP_Codes"></span>"XXX HHHH"-Type ODETTE DIAGP Codes

Transfer CFT diagnostic code identifying an FPDU negotiation or send
error in the ODETTE protocol (where H represents a hexadecimal digit and
X a letter):

-   XXX is a Transfer
    CFT mnemonic code - ODETTE protocol. This is an alphanumeric
    value describing the origin of the anomaly or phase during which it occurred.

See also,
Transfer CFT Mnemonic Codes ODETTE Protocol.

-   HHHH
    is a Transfer CFT numeric code - ODETTE protocol. This is a hexadecimal
    value corresponding to the internal protocol code.

See also
"[Transfer CFT ODETTE](../../../protocols_start_here/start_here_odette)"
