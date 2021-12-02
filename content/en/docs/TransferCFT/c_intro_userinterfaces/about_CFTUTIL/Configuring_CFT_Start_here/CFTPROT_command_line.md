{
    "title": "CFTPROT  - Transfer protocols",
    "linkTitle": "CFTPROT - Transfer protocol",
    "weight": "290"
}The following table lists the parameters which are common to all protocols.The CFTPROT TYPE = xxx commands are explained in the tables following the general parameters.

For network resources of the asynchronous type (not SAP), there
cannot be more than one CFTPROT object per CFTNET object.

Related
topics

-   Command syntax
    [CFTPROT](../../../command_summary#CFTPROT)
-   Object concepts
    [Transfer protocols](../../../../admin_intro/admin_config_commands/transfer_protocol_concepts)

 
Use this command to define network parameter settings.


| Parameters  | Description  |
| --- | --- |
|  <a href="../../../command_summary/parameter_intro/disctd">DISCTD</a>  |  Wait time-out (in seconds) before disconnection, in the absence of a new transfer request to the partner, in requester mode.<br/>The session established for a transfer remains active for DISCTD seconds after the completion of this transfer.<br/>If the value is 0, the wait time-out is infinite.  |
|  <a href="../../../command_summary/parameter_intro/discts">DISCTS</a><br/><a href="../../../command_summary/parameter_intro/discts">see table</a>  |  Wait time-out (in seconds) before disconnection, in the absence of a new transfer request from the partner, in server mode.<br/>The session established for a transfer remains active for DISCTS seconds after the completion of this transfer. If at the end of this time-out, no new transfer has been received, the connection is freed by the ABORT FPDU.  |
|  <a href="../../../command_summary/parameter_intro/dynam">DYNAM</a>  |  Dynamic partner identifier (8 characters) in server mode.  |
|  <a href="../../../command_summary/parameter_intro/exit">EXIT</a>  |  Identifier describing the directory EXIT.<br/>The value of this identifier corresponds to the CFTEXIT ID parameter.<br/>The identifier may contain the &amp;NPART symbolic variable.  |
|  <a href="../../../command_summary/parameter_intro/exita">EXITA</a>  |  Identifier describing the directory EXIT.<br/>The value of this identifier corresponds to the value of the CFTEXIT ID parameter.<br/>The identifier may contain the &amp;NPART symbolic variable.  |
|  <a href="../../../command_summary/parameter_intro/id">ID</a>  |  CFTPROT command identifier.<br/>This name must be referenced in the values taken by the CFTPARM PROT parameter.  |
|  <a href="../../../command_summary/parameter_intro/idf">IDF</a>  |  Used to assign an IDF to a file on receiving an NIDF.<br/>This parameter can be used in:<br/> • server mode (sender or receiver)<br/> • receiver requester following the activation of a RECV IDF=&lt;mask&gt; command</li>  |
| <a href="../../../command_summary/parameter_intro/nack">NACK</a>  |  PeSIT<br/>Enables or disables the negative acknowledgement feature.  |
| <a href="../../../command_summary/parameter_intro/net">NET</a>  |  Identifier referring to a CFTNET command associated with this protocol.  |
|  <a href="../../../command_summary/parameter_intro/rcomp">RCOMP</a>  |  Maximum compression authorized on receiving a file.<br/>This compression is negotiated between the sender and the receiver.<br/>A zero value corresponds to no compression.<br/>For more information such as usable values etc., see <a href="../../../command_summary/parameter_intro/compression">Compression</a>.  |
|  <a href="../../../command_summary/parameter_intro/restart">RESTART</a>  |  Maximum number of transfer restart attempts.<br/>An attempt is taken into account as soon as the physical connection with the remote site is correctly established.  |
|  <a href="../../../command_summary/parameter_intro/rto">RTO</a>  |  Network monitoring time-out (in seconds) excluding the protocol connection/disconnection/break phase.<br/>Corresponds to the wait time-out of a reply to an FPDU before disconnection (READ TIME OUT). If the value is 0, the wait time-out is infinite.  |
|  <a href="../../../command_summary/parameter_intro/sap">SAP</a>  |  Name of the local SAP, Service Access Point, associated with this protocol. Used to identify the "access point" at which incoming connection requests for this communication protocol are placed. The SAP supplied by a requester partner when making its connection request is retrieved by the local Transfer CFT which uses it to deduce the protocol to be used. Each CFTPROT object in a given resource class must include its specific SAP. The value of this parameter may be expressed in hexadecimal form. In this case, the first character must be "#" (number sign) (for example: #31 is understood as the ASCII character ‘1’).  |
|  <a href="../../../command_summary/parameter_intro/scomp">SCOMP</a>  |  Maximum authorized compression for sending a file. This compression is negotiated between the sender and the receiver. A zero value corresponds to no compression.  |
|  <a href="../../../command_summary/parameter_intro/srin">SRIN</a>  |  Controls the direction of transfers authorized for the Transfer CFT when it is server, accepter of the protocol connection.  |
|  <a href="../../../command_summary/parameter_intro/srout">SROUT</a>  |  Controls the direction of transfers authorized for the Transfer CFT when it is requester (initiator of the protocol connection).  |
|  <a href="../../../command_summary/parameter_intro/type#type_CFTPROT">TYPE</a>  |  Type of file transfer protocol.  |


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

<span id="PeSIT_examples"></span>

## PeSIT examples

### PeSIT profile

PeSIT protocol, SIT profile, associated
with the data exchange protocol and network resources defined by the CFTNET
ID=ACCEPTOR command.

The time-outs are the default values \[ [Compression](../../../command_summary/parameter_intro/compression)\]. Each FPDU contains a single file
record (MULTART=NO). There is no on-line compression.

### PeSIT D EXTERN profile

### PeSIT D CFT profile

### PeSIT E
