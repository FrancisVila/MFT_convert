{
    "title": "CFTPROT  - Transfer protocols",
    "linkTitle": "Protocol - CFTPROT",
    "weight": "220"
}The CFTPROT command defines a file transfer protocol application. This page describes the parameter setting command, and explains the parameters that are negotiated with the remote partner at the time the protocol connection is established.

The following table lists the parameters which are common to all protocols. The CFTPROT TYPE = xxx commands are explained in the tables following the general parameters.

For network resources of the asynchronous type (not SAP), there
cannot be more than one CFTPROT object per CFTNET object.

Related
topics

-   Object concepts
    [Transfer protocols](../../../../admin_intro/admin_config_commands/transfer_protocol_concepts)

 
Use this command to define network parameter settings.

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Parameters         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/disctd">DISCTD</a></p>         </td>
         <td><p>Wait time-out (in seconds) before disconnection, in the
absence of a new transfer request to the partner, in requester mode.</p>
<p>The session established for a transfer remains active for
DISCTD seconds after the completion of this transfer.</p>
<p>If the value is 0, the wait time-out is infinite.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/discts">DISCTS</a></p>
<p><a href="../../../command_summary/parameter_intro/discts">see table</a></p>         </td>
         <td><p>Wait time-out (in seconds) before disconnection, in the
absence of a new transfer request from the partner, in server mode.</p>
<p>The session established for a transfer remains active for
DISCTS seconds after the completion of this transfer. If at the end of
this time-out, no new transfer has been received, the connection is freed
by the ABORT FPDU.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/dynam">DYNAM</a></p>         </td>
         <td><p>Dynamic partner identifier (8 characters) in server mode.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/exit">EXIT</a> </p>         </td>
         <td><p>Identifier describing the directory EXIT.</p>
<p>The value of this identifier corresponds to the CFTEXIT
ID parameter.</p>
<p>The identifier may contain the &amp;NPART symbolic variable.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/exita">EXITA</a> </p>         </td>
         <td><p>Identifier describing the directory EXIT.</p>
<p>The value of this identifier corresponds to the value of
the CFTEXIT ID parameter.</p>
<p>The identifier may contain the &amp;NPART symbolic variable.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/id">ID</a> </p>         </td>
         <td><p>CFTPROT command identifier.</p>
<p>This name must be referenced in the values taken by the
CFTPARM PROT parameter.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/idf">IDF</a> </p>         </td>
         <td><p>Used to assign an IDF to a file on receiving an NIDF.</p>
<p>This parameter can be used in:</p>
<ul>
<li>server
mode (sender or receiver)</li>
<li>receiver
requester following the activation of a RECV IDF=&lt;mask&gt; command</li>
</ul>         </td>
      </tr>
      <tr>
         <td><a href="../../../command_summary/parameter_intro/nack">NACK</a>         </td>
         <td><p>PeSIT</p>
<p>Enables or disables the negative acknowledgement feature.</p>         </td>
      </tr>
      <tr>
         <td><a href="../../../command_summary/parameter_intro/net">NET</a>         </td>
         <td><p>Identifier referring to a CFTNET command associated with
this protocol.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/rcomp">RCOMP</a></p>         </td>
         <td><p>Maximum compression authorized on receiving a file.</p>
<p>This compression is negotiated between the sender and the
receiver.</p>
<p>A zero value corresponds to no compression.</p>
<p>For more information such as usable values etc., see <a href="../../../command_summary/parameter_intro/compression">Compression</a>.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/restart">RESTART</a></p>         </td>
         <td><p>Maximum number of transfer restart attempts.</p>
<p>An attempt is taken into account as soon as the physical
connection with the remote site is correctly established.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/rto">RTO</a> </p>         </td>
         <td><p>Network monitoring time-out (in seconds) excluding
the protocol connection/disconnection/break phase.</p>
<p>Corresponds to the wait time-out of a reply to an FPDU
before disconnection (READ TIME OUT).</p>
<p>If the value is 0, the wait time-out is infinite.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/sap">SAP</a> </p>         </td>
         <td><p>Name of the local SAP, Service Access Point, associated
with this protocol.</p>
<p>Used to identify the "access point" at which
incoming connection requests for this communication protocol are
placed.</p>
<p>The SAP supplied by a requester partner when making its
connection request is retrieved by the local Transfer CFT which uses it
to deduce the protocol to be used. Each CFTPROT object in a given resource
class must include its specific SAP.</p>
<p>The value of this parameter may be expressed in hexadecimal
form. In this case, the first character must be "#" (number
sign) (for example: #31 is understood as the ASCII character ‘1’).</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/scomp">SCOMP</a> </p>         </td>
         <td><p>Maximum authorized compression for sending a file.</p>
<p>This compression is negotiated between the sender and the
receiver.</p>
<p>A zero value corresponds to no compression.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/srin">SRIN</a> </p>         </td>
         <td><p>Controls the direction of transfers authorized for the
Transfer CFT when it is server, accepter of the protocol connection.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/srout">SROUT</a></p>         </td>
         <td><p>Controls the direction of transfers authorized for the
Transfer CFT when it is requester (initiator of the protocol connection).</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/type#type_CFTPROT">TYPE</a> </p>         </td>
         <td><p>Type of file transfer protocol.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Defining_ODETTE"></span>

## Defining ODETTE (OFTP)

The CFTPROT TYPE = ODETTE command is used to describe the OFTP (ODETTE)
transfer protocol.

This command is used to specify the values on which the Transfer CFT is based
during protocol negotiations concerning:

-   Credit
-   Data compression
-   Special logic

The "Credit" value designates the maximum number of data packets
which the sender can send, before the server needs to acknowledge their
receipt by assigning a new "Credit". Transfer CFT simulates
the taking of a synchronization point at each credit message sent or received.

If a transfer is interrupted, the restart point proposed by a sender
Transfer CFT corresponds to the point the send transfer was interrupted,
as detected by the sender. The restart point negotiated by a receiver
Transfer CFT always corresponds to a credit message it previously sent
(except when restarting from the beginning of the file).

The [OFTP (ODETTE)](../../../../protocols_start_here/start_here_odette)
section of the Protocols book contains a detailed explanation of the constraints
and specifics regarding the use of this particular protocol.

<table>
   <tbody>
      <tr>
         <td><p>Description</p>         </td>
         <td><p>Use this command to describe the ODETTE transfer protocol.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p><a href="../../../command_summary/parameter_intro/eerp">EERP</a></p>         </td>
         <td><p>Used to interpret the value of the ORIGINATOR and DESTINATOR
fields contained in the EERP message, according to the protocol version.</p>
<p>The End to End ResPonse service generates a message called
EERP. This message informs the file sender that the data sent arrived
correctly.</p>
<p>The first version of the protocol (1986) specifies that:</p>
<ul>
<li>the ORIGINATOR
protocol field corresponds to the file sender</li>
<li>the DESTINATOR
protocol field corresponds to the file receiver</li>
</ul>
<p>The second version (1991) specifies that:</p>
<ul>
<li>the ORIGINATOR
protocol field corresponds to the EERP sender (i.e. the file receiver)</li>
<li>the DESTINATOR
protocol field corresponds to the EERP receiver (i.e. the file sender)</li>
</ul>
<p>Note: heck the
consistency of the customized values from one end to another. If the sender
and receiver have different versions, it is not possible to acknowledge
the transfer.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/pad">PAD</a> </p>         </td>
         <td><p><em>Deprecated in</em> <span class="mc-variable axway_variables.Component_Long_Name variable" style="font-style: italic;">Transfer CFT</span><em></em><span class="mc-variable axway_variables.Release_Number variable" style="font-style: italic;">3.9</span></p>
<p>Option applying "SPECIAL LOGIC" to the data exchange
buffers.</p>
<p>This option is negotiated with the partner when the protocol
session is established (in the SSID FPDU). If the option is set to NO
for one of the partners, the "special logic" is not applied.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/rcredit">RCREDIT</a> </p>         </td>
         <td><p>Value of the "credit" (expressed as a number
of "DATA" messages) proposed by Transfer CFT when it is server.</p>
<p>This value is negotiated with the value proposed by the
requester (see the SCREDIT parameter) when the protocol session is established.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/resync">RESYNC</a> </p>         </td>
         <td><p>Option for restarting a transfer following an interruption.</p>
<p>This option is negotiated with the partner when the connection
is established: if the option is set to NO for one of the partners, transfer
restarts are not managed.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/rrusize">RRUSIZE</a></p>         </td>
         <td><p>Maximum size of NSDUs (Network Service Data Unit) being
received.</p>
<p>This parameter is negotiated with the partner (SRUSIZE
parameter if Transfer CFT), the smallest value is selected as the size
of NSDUs sent.</p>
<p>Refer to the Transfer CFT <a href="../../../../protocols_start_here">Protocol
topics</a> to optimize the definition of the value of this parameter.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/scredit">SCREDIT</a></p>         </td>
         <td><p>Value of the "credit" (expressed as a number
of "DATA" messages) proposed by Transfer CFT when it is the
requester.</p>
<p>Transfer CFT is authorized to send a number of "DATA"
protocol messages equal to the result of the negotiation (performed when
the protocol session is established), before waiting for a new "credit"
to be sent by the server.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/srusize">SRUSIZE</a></p>         </td>
         <td><p>Maximum size of NSDUs (Network Service Data Unit) being
sent.</p>
<p>This parameter is negotiated with the partner (RRUSIZE
parameter if Transfer CFT), the smallest value being selected
as the size of NSDUs sent.</p>
<p>Refer to the  <a href="../../../../protocols_start_here">Protocol
topics</a> to optimize the definition of the value of this parameter.</p>
<p>MVS connection, the maximum value of SRUSIZE is equal to the value configured in the NCP (or the equivalent) less (-) 6 bytes.</p>         </td>
      </tr>
      <tr>
         <td><p>TCP </p>         </td>
         <td><p>Processing method used for protocol messages:</p>
<ul>
<li>Transfer
CFT: activation of the method specific to Transfer CFT</li>
<li>OFTP (default value):
activation of the standard method (RFC 2204)</li>
</ul>
<p>This parameter applies in both initiator and responder
modes. </p>         </td>
      </tr>
   </tbody>
</table>

<span id="Defining_PeSIT"></span>

## Defining PeSIT

The CFTPROT TYPE = PESIT command is used to describe the PeSIT transfer
protocol.

In PeSIT, the user can specify parameters controlling the:

-   mechanisms associated
    with the synchronization points
-   format of messages
-   compression algorithms
-   CRC calculation

> **Note:**
>
> In certain environments,
> the mechanisms for repositioning in the transferred files are not operational
> with all the files supported: after a transfer interruption, transfers
> then begin again from the start of files (see the Transfer CFT Operations
> Guide specific to your OS).

The four PeSIT variants supported correspond to the four values of the
PROF parameter (CFT, SIT, EXTERN, ANY). Some parameters are only meaningful
for one or more of these variants. For clarity, these specific parameters
are grouped below according to the corresponding value(s) of the PROF
parameter.

For a detailed explanation of the constraints and specifics regarding
the use of each of these variants, refer to the Transfer CFT [Protocols](../../../../protocols_start_here).

<table>
   <tbody>
      <tr>
         <td><p>Description</p>         </td>
         <td><p>Use this command to describe the PeSIT transfer protocol.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p><a href="../../../command_summary/parameter_intro/concat">CONCAT</a></p>
<p>Only in sender mode</p>         </td>
         <td><p>Option to concatenate FPDUs (File Protocol Data Units)
in a given NSDU.</p>
<p>This option is not negotiated.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/cto">CTO</a> </p>         </td>
         <td><p>Minimum duration (in minutes) of the session, Cycle Time
Out.</p>
<p>At the end of a transfer, the wait time-out for a nfew
transfer is recalculated depending on:</p>
<ul>
<li>the time
(hour) for opening the session</li>
<li>the current
time</li>
<li>the wait
delay before disconnection (DISCTS for the protocol)</li>
<li>the duration
of the session (CTO)</li>
</ul>
<p>The session is liberated if no transfer was initiated by
the remote partner during the indicated duration.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/cycle">CYCLE</a> </p>         </td>
         <td><p>Periodicity (in minutes) for creation of a protocol
session:</p>
<ul>
<li>0: PeSIT
session open on startup</li>
<li>n: periodicity</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/disctc">DISCTC</a> </p>         </td>
         <td><p>Wait time-out (in seconds) for the reply FPDU (ACONNECT),
after the sending of a CONNECT FPDU.</p>
<p>If the value is 0, the wait time-out is infinite.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/disctr">DISCTR</a> </p>         </td>
         <td><p>Network disconnection wait time-out. Wait time-out (in
seconds) for the partner site to cut the connection, after sending an
"abort" request (ABORT FPDU).</p>
<p>If the value is 0, the wait time-out is infinite.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/hide99">HIDE99</a></p>         </td>
         <td><p>Optional parameter available only to PESIT
protocol definition (TYPE=PESIT) using the ANY profile (PROFIL=ANY/CFT).</p>
<ul>
<li>NO (Default value): no information inside
PI99 (free message PI Code) is hidden</li>
<li>YES: hide private information carried
by the protocol (physical local path of the file)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/logon">LOGON</a></p>
<p>Only in requester mode PeSIT E</p>         </td>
         <td><p>Implementation of the pre-connection phase.</p>
<p>According to the value of this parameter:</p>
<ul>
<li>YES: this phase is implemented. The
requester sends a 24-byte EBCDIC message as follows:</li>
<li><ul>
<li>byte
1 to 8: ‘PESIT ’ (PeSIT followed by 3 blank characters) (corresponding
to the protocol used)</li>
<li>byte
9 to 16: requester identifier (NSPART of CFTPART)</li>
<li>byte
17 to 24: requester password (NSPASSW of CFTPART)</li>
</ul></li>
<li>NO: this phase is not implemented: the
requester does not send a message</li>
</ul>
<p>Note: The Transfer
CFT server automatically adapts itself to the choice of the requesting
partner to send a Logon message or not.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/multart">MULTART</a></p>
<p>Only in sender mode</p>         </td>
         <td><p>Option to group several records of the file sent in a given
FPDU (multi-record FPDUs).</p>
<ul>
<li>in
sender mode, MULTART = YES is recommended if the partner supports
multi-record FPDUs</li>
</ul>
<p>The value MULTART = YES is PROHIBITED in this profile</p>
<ul>
<li>in
receiver mode, the Transfer CFT accepts multi-record FPDUs,
regardless of the value of this parameter</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/pad">PAD</a> </p>
<p>Only in requester mode CFT profile</p>         </td>
         <td><p><em>Deprecated in</em> <span class="mc-variable axway_variables.Component_Long_Name variable" style="font-style: italic;">Transfer CFT</span><em></em><span class="mc-variable axway_variables.Release_Number variable" style="font-style: italic;">3.9</span></p>
<p>Use of the CRC (Cyclic Redundancy Checksum).</p>
<p>This option is not negotiated: in server mode, Transfer
CFT always adapts itself to the choice of the requesting partner.</p>
<p>The PAD = YES option is mandatory for an access through
a PAD.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/part">PART</a> </p>         </td>
         <td><p>List of the partners (maximum of four) for which a PeSIT
session, where the transactional turn is cyclically opened..</p>
<p>Inactive partners (result of the command INACT) are not
taken into account.</p>         </td>
      </tr>
      <tr>
         <td><p>PROF </p>         </td>
         <td><p>PeSIT D or E protocol profile.</p>
<p>The profile options are:</p>
<ul>
<li>EXTERN
profile: corresponds to the
standardized definition of the PeSIT version D protocol</li>
<li>CFT profile:
the PeSIT version D protocol,
when the partner also has a Transfer CFT</li>
</ul>
<p>Its functionality level is greater than the PeSIT D EXTERN
profile specifications,</p>
<ul>
<li>ANY profile:
corresponds to the standardized
definition of the PeSIT version E protocol</li>
</ul>
<p>This profile includes the facilities of the CFT profile,
as standard.</p>
<p>Additional facilities are provided between two Transfer
CFTs, while remaining in conformity with the PeSIT E standard. These facilities
are based on the use of the PI 99 (free PI).</p>
<ul>
<li>the DMZ
profile (DeMilitarized Zone): corresponds to the normalized definition for the PeSIT protocol, version E E (refer to Managing the Turn)</li>
</ul>
<p>Note:
In
server mode, the PROF parameter can take either the EXTERN,
CFT or ANY values:
indeed, in server mode, the Transfer CFT automatically adapts
itself to the profile proposed by the requesting partner.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/rchkw">RCHKW</a></p>         </td>
         <td><p>Size of the receive mode synchronization point acknowledgement
anticipation window, expressed as a number of synchronization points.</p>
<p>Negotiated with the sender partner.</p>
<p>RCHKW=0 means that synchronization points are not acknowledged.</p>
<p>RCHKW=1 is equivalent to operation in half-duplex mode.</p>
<p>On LU6.2 networks all non-null values will be forced to
1 during protocol negotiation.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/resync">RESYNC</a></p>
<p>PeSIT D CFT
profile, PeSIT D EXTERN profile, PeSIT E</p>         </td>
         <td><p>Dynamic resynchronization of exchanges during transfer
(without interrupting the data exchange phase).</p>
<p>This option is negotiated with the partner at the time
the connection is established: if this option is set to NO for one of
the partners, dynamic resynchronization is not managed.</p>
<p>Note:
The only dynamic resynchronization
possible between two Transfer CFTs is performed when a CRC error
is detected (PAD=YES).</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/reverse">REVERSE</a></p>
<p>Only in requester mode  PeSIT
D CFT profile, PeSIT E</p>         </td>
         <td><p>Option to reuse a connection to perform two transfers in
different directions one after the other.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/rpacing">RPACING</a></p>         </td>
         <td><p>Value of the interval between synchronization points for
receive transfers (in Kbytes) (1 Kbyte = 1024 bytes) (see explanations
of the SPACING parameter).</p>
<p>This parameter is negotiated with the partner (SPACING
parameter if Transfer CFT); the smallest value is selected as
the interval between synchronization points.</p>
<p>A null value (RPACING = 0) means that synchronization points
are not set.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/rrusize">RRUSIZE</a> </p>         </td>
         <td><p>Maximum size of NSDUs being received and sent.</p>
<p>This parameter is negotiated with the partner (SRUSIZE
parameter if Transfer CFT); the smallest value is selected as
the size of NSDUs sent.</p>
<p>Refer to the Transfer CFT <a href="../../../../protocols_start_here">Protocol</a>
for more information on this parameter.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/schkw">SCHKW</a></p>         </td>
         <td><p>Size of the send mode acknowledgement anticipation window
for synchronization points, expressed as a number of synchronization points.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/segment">SEGMENT</a></p>
<p>Only in sender mode  Profile</p>         </td>
         <td><p>Option to segment file records in several FPDUs.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/spacing">SPACING</a> </p>         </td>
         <td><p>Interval between synchronization points being sent (in
Kbytes)<br />
(1 Kbyte = 1 024 bytes).</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/srusize">SRUSIZE</a></p>         </td>
         <td><p>Maximum size of NSDUs being received and sent.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/sserv">SSERV</a></p>         </td>
         <td><p>Identifies the service (protocol variant) required for
the incoming partner.</p>         </td>
      </tr>
      <tr>
         <td><p>Example [FOR DETAILS: PeSIT
examples]</p>         </td>
      </tr>
   </tbody>
</table>

<span id="SSL_parameter_in_CFTPROT"></span>

## SSL parameter

The CFTPROT object accepts the optional SSL parameter. For the declared
protocol, it sets the:

-   Default security
    profile in requester mode
-   Security profile
    in server mode

If the SSL parameter is set in a CFTPROT object, transport security
must be implemented in both the server and requester modes.

The security profile is mandatory in server mode. The default security
profile for the requester mode is optional: if it does not exist, it must
then be declared for each CFTPART object, which provides the transfer
partner definition.

The new SSL parameter is used to associate a security profile with a
protocol definition.

For a security profile related to incoming calls (server mode), the
SSL parameter value must correspond to the identifier of a DIRECT=SERVER
SSL command.

For a default security profile related to outgoing calls (client mode),
the SSL parameter value must correspond to the identifier of a DIRECT=CLIENT
SSL command.

If you do not define the CFTPROT SAP parameter when using the SSL protocol,
then the server mode for CFTSSL is not mandatory.

Syntax:  

CFTPROT  
\[SSL =     identifier,\]

<table>
   <tbody>
      <tr>
         <td><p>Description</p>         </td>
         <td><p>Use the CFTPROT object to set:</p>
<ul>
<li>Default
security profile in requester mode</li>
<li>Security
profile in server mode</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Parameter</p>         </td>
         <td><p><a href="../../../command_summary/parameter_intro/ssl">SSL</a></p>         </td>
         <td><p>SSL commands Identifier  used
for security profiles.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="PeSIT_examples"></span>

## PeSIT example

PeSIT protocol, ANY profile, associated
with the data exchange protocol and network resources defined by the CFTNET
ID=ACCEPTOR command.

The time-outs are the default values. Each FPDU contains a single file
record (MULTART=NO).

    CFTPROT     ID     = PSITE,          /* PSITE protocol               */
    TYPE    = PESIT, PROF=ANY,     /* PeSIT  E                     */
    NET     = ACCEPTOR,
    MULTART = NO,
    CONCAT  = YES
