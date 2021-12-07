{
    "title": "Transfer CFT messages: CFTH",
    "linkTitle": "CFTH messages",
    "weight": "310"
}This topic lists the CFTHxx  (CFT xnnx) messages and provides the type,  a description, consequence, and corrective actions when applicable.

**Message format**

Earlier versions of Transfer CFT used a different message format than version 3.1.3 and higher. This document displays both formats when applicable and available, otherwise only the v23 is used. Using the CFTLOG Format = V24 setting, the log displays as shown:

CFTXXX: fixed text message &lt;variables>

**Example**

CFTLOG FORMAT=\[V23,V24\]

For V23: `CFTT57I PART=&part IDF=&idf IDT=&idt &str transfer started`

For V24: `CFTT57I &str transfer started   <IDTU=&idtu PART=&part IDF=&idf IDT=&idt>`

```
V23 format
V24 format
Error
<span id="CFTH01E"></span>CFTH01E PART=&part Context area allocation failure
CS=&scs
CFTH01E Context area allocation failure <PART=&part CS=&cs>
Explanation
Cannot allocate the working area necessary for the transfer.
Consequence
In REQUESTER mode, the transfer is refused with a {{< TransferCFT/componentshortname >}}
122 diagnostic code and a MALLOC protocol diagnostic message.
In SERVER
mode, the incoming call is rejected. In this case, as the partner's name
is not known, the value UNKNOWN
is displayed.
```

 

```
V23 format
V24 format
Error
<span id="CFTH02E"></span>CFTH02E PART=&part TFIL Exchange buffer allocation
failure CS=&scs
CFTH02E TFIL Exchange buffer allocation failure <PART=&part CS=&cs>
Explanation
Cannot allocate the working area required to exchange information
between the PROTOCOL task and the FILE task.
Consequence
In REQUESTER mode, the transfer is refused with a {{< TransferCFT/componentshortname >}}
122 code and a MALLOC protocol diagnostic message.
In SERVER mode, the incoming call is rejected. In this
case, as the partner's name is not known, the value UNKNOWN
is displayed.
```

 

```
V23 format
V24 format
Error
<span id="CFTH03E"></span>CFTH03E PART=&part
Error sending data on network NCR=&ncr NCS=&ncs NET=&net
CFTH03E Error sending data on network <PART=&part NCR=&ncr NCS=&cs NET=&net>
Explanation
Cannot send a message on the network.
Consequence
The transfer is interrupted with a {{< TransferCFT/componentshortname >}} 302 code
and a protocol diagnostic message indicating the specific error code of
the error that occurred during the send request. This code is expressed
in hexadecimal.
```

 

```
V23 format
V24 format
Error
<span id="CFTH04E"></span>CFTH04E PART=&part
Mismatch between header and FPDU size
CFTH04E Mismatch between header and FPDU size <PART=&part>
Explanation
The transfer is aborted. A 318 protocol code, transported
by an ABORT FPDU, is reported to the remote partner.
```

 

```
V23 format
V24 format
Error
<span id="CFTH05E"></span>CFTH05E: PART=&part ,&message
CFTH05E <PART=&part &message>
Explanation
Inconsistent FPDU received.
The end of the message is then set to one of the following
values:

-   Unknown FPDU
    type=n:

Reception of an FPDU, for which the type byte in the
header is unknown

-   Missing PI number
    n into FPDU fpdu:

Reception of an FPDU with missing mandatory PI

-   PGI n in PGI
    into FPDU fpdu:

Reception of an FPDU embedding a PGI in a PGI

-   Invalid length
    n for PI n into FPDU fpdu:

Reception of an FPDU with a PI of invalid length

-   Unknown PI number
    n into FPDU fpdu:

Reception of an FDPU with an unwanted PI
Consequence
The transfer is aborted. A 318 protocol code, transported by
an ABORT FPDU, is reported to the remote partner.
```

 

```
V23 format
V24 format
Error
<span id="CFTH06E"></span>CFTH06E PART=&part Error &cr while formatting
FPDU
CFTH06E Error &cr while formatting FPDU <PART=&part >
Explanation
Problem encountered while formatting an FPDU.

-   -1  PGI
    embedded in a PGI
-   -2  Output
    buffer overflow
-   -3  End
    of PGI without PGI
-   -4  External/internal
    type error
-   -5  End
    of FPDU with PGI not closed
-   -8  Invalid
    PI length
-   -11  FPDU
    description pointer null

Consequence
The transfer is aborted. A 220 protocol code, transported by
an ABORT FPDU, is reported to the remote partner.
```

 

```
V23 format
V24 format
Error
<span id="CFTH07E"></span>CFTH07E PART=&part TFIL task Synchronization error
CR=&cr CS=&scs
CFTH07E TFIL task Synchronization error <PART=&part CR= &cr CS=&cs>
Explanation
Problem encountered when sending a {{< TransferCFT/componentshortname >}} internal
message to the FILE task.
Consequence
The transfer
is aborted by the protocol task (network disconnection). However, as the
FILE task is not protected by a time-out, the request remains in the C status in the catalog.
```

 

```
V23 format
V24 format
Error
<span id="CFTH08E"></span>CFTH08E PART=&part Network release response error
NCR=&ncr NCS=&ncs
CFTH08E Network release response error <PART=&part NCR=&ncr NCS=&cs>
Explanation
Cannot respond to a network connection failure indication.
Consequence
This incident has no impact on the previous transfer (whether
terminated or interrupted).
```

 

```
V23 format
V24 format
Error
<span id="CFTH09E"></span>CFTH09E PART=&part Network connect request local
error NCR=&ncr NCS=&ncs
CFTH09E Network connect request local error <PART=&part NCR=&ncr NCS=&cs NET=&net>
Explanation
Cannot make an outgoing connection request on the network.
For a general -6 code (maximum number of connections reached on the resource),
the transfer is refused with a {{< TransferCFT/componentshortname >}} 416 diagnostic code and a
MAXCNX protocol diagnostic message.
The transfer will be retried (minimum time-out equal to
the WSCAN parameter of the CFTCAT command), without incrementing the retry
counter.
```

 

```
V23 format
V24 format
Error
<span id="CFTH10E"></span>CFTH10E PART=&part Network connect reject RECOV=&recov
L= &local R=&reason D=&ncs
CFTH10E Network connect reject <PART=&part RECOV=&recov L=&local R=&reason D=&ncs NET=&net>
Explanation
The physical connection has been refused.
Consequence
Depending
on the origin of the refusal and the RECOV code, the transfer is set to
the K state (diagnostics code
303) or remains set to the D state
(diagnostics code 302) and will be retried.
```

 

```
V23 format
V24 format
Error
<span id="CFTH11E"></span>CFTH11E PART=&part Error Opening session EV=&pevent
ST=&pstate
CFTH11E Error Opening session <PART=&part EV=&pevent ST=&pstate>
Explanation
Problem opening a PeSIT session with a remote partner after
establishing the network session.
Consequence
The transfer
is aborted with a {{< TransferCFT/componentshortname >}} 451 diagnostic code.
```

 

```
V23 format
V24 format
Error
<span id="CFTH12E"></span>CFTH12E PART=&part Logon reject logon
CFTH12E Logon reject <PART=&part &str>
Explanation
The PESIT pre-connection phase, logon, is refused by the
SERVER partner (the correct response is ACK0 in EBCDIC). The string received
is included in the message.
Consequence
The transfer
is aborted with one of the following possible diagnostic codes:

-   903: invalid
    password
-   970: password
    expired, or
-   963: unknown acknowledgment of a pre-connection request

```

 

```
V23 format
V24 format
Error
<span id="CFTH13E"></span>CFTH13E PART=&part FPDU Remote reject DIAGI=&diagi
DIAGP=&diagp
CFTH13E FPDU Remote reject <PART=&part DIAGI=&diagi DIAGP=&diagp>
Explanation
FPDU including a diagnostic code has been received. The
DIAGP field is of the XXX NNN type.
Consequence
The transfer is aborted.
```

 

```
V23 format
V24 format
Error
<span id="CFTH14E"></span>CFTH14E PART=&part Invalid AckCONNECT FPDU &str
CFTH14E Invalid AckCONNECT FPDU <PART=&part &str>
Explanation
The AckCONNECT FPDU sent by the SERVER partner is invalid.
The field "&str" is an explicit character
string:

-   Version
    = n: The protocol version negotiated by the SERVER partner
    is invalid Window without Pacing:
    A synchronization window is specified even though the interval is null,

<!-- -->

-   Window = n too large: The synchronization
    window negotiated by the SERVER partner is too large The SIT profile does
    not allow a value greater than 16

<!-- -->

-   Pacing = n not authorized: The synchronization
    interval negotiated by the SERVER partner does not comply with the specifications
    of the SIT profile The values 1, 2 and 3 are not allowed

<!-- -->

-   Pacing = n greater than initial value = n: The synchronization
    interval negotiated by the SERVER partner is larger than that proposed

<!-- -->

-   Window = n greater than initial value = n:
    The synchronization
    window negotiated by the SERVER partner is larger than that proposed

<!-- -->

-   Resynchronization = n: The value
    of the resynchronization option negotiated by the SERVER partner does
    not comply with the specifications of the protocol

<!-- -->

-   Mismatch between header and FPDU size: The FPDU
    length indicated in the header is not equal to the length of the FPDU
    received

<!-- -->

-   Unknown FPDU: The number
    identifying the received FPDU is not referenced

<!-- -->

-   Missing PI number n into FPDU: The PI is
    mandatory for this type of FPDU

<!-- -->

-   Unknown PI number n into FPDU: The PI is
    unknown for this type of FPDU

<!-- -->

-   PGI n in PGI into FPDU: The presence
    of a PGI embedded in another PGI is invalid

<!-- -->

-   Invalid length n for PI n into FPDU: The length of the
    PI is invalid (less than minimum length or greater than maximum length)

Consequence
The transfer is aborted with DIAGI=220, DIAGP=ACO + PeSIT code.
```

 

```
V23 format
V24 format
Error
<span id="CFTH15E"></span>CFTH15E PART=&part Invalid AckCREATE FPDU &str
CFTH15E Invalid AckCREATE FPDU <PART=&part &str>
Explanation
The AckCREATE FPDU sent by the SERVER partner does not
conform.
The "&str" string is an explicit character
string:

-   NSDU
    size = n greater than initial value = n: The maximum NSDU size negotiated by the partner
    is greater than that proposed

<!-- -->

-   NSDU
    size = n too lower for LRECL = n: In the SIT profile, as segmentation is not authorized,
    a record must fit in an FPDU. The negotiated NSDU size (RUSIZE) must therefore
    be greater than the record length of the file (plus 6 for the FPDU header)

<!-- -->

-   Mismatch
    between header and FPDU size: The FPDU length indicated in the header is not
    equal to the length of the FPDU received

<!-- -->

-   Unknown
    FPDU: The number identifying the received FPDU is not
    referenced

<!-- -->

-   Missing
    PI number n into FPDU: The PI is mandatory for this type of FPDU

<!-- -->

-   Unknown
    PI number n into FPDU: The PI is unknown for this type of FPDU

<!-- -->

-   PGI n
    in PGI into FPDU: The presence of a PGI embedded in another PGI is
    invalid

<!-- -->

-   Invalid
    length n for PI n into FPDU: The length of the PI is invalid (less than minimum
    length or greater than maximum length)

Consequence
Transfer aborted with DIAGI=220, DIAGP=ACR + PeSIT code.
```

 

```
V23 format
V24 format
Error
<span id="CFTH16E"></span>CFTH16E PART=&part Invalid AckWRITE FPDU &str
CFTH16E Invalid AckWRITE FPDU <PART=&part &str>
Explanation
The AckWRITE FPDU sent by the SERVER partner does not conform.
The field "&str" is an explicit character
string:

-   Restart
    point without restart option: The remote partner proposes a restart point for
    the transfer, even though it is a new transfer

<!-- -->

-   Mismatch
    between header and FPDU size: The FPDU length indicated in the header is not
    equal to the length of the FPDU received

<!-- -->

-   Unknown
    FPDU: The number identifying the received FPDU is not
    referenced

<!-- -->

-   Missing
    PI number n into FPDU: The PI is mandatory for this type of FPDU

<!-- -->

-   Unknown
    PI number n into FPDU: The PI is unknown for this type of FPDU

<!-- -->

-   PGI n
    in PGI into FPDU: The presence of a PGI embedded in another PGI is
    invalid

<!-- -->

-   Invalid
    length n for PI n into FPDU: The length of the PI is invalid (less than minimum
    length or greater than maximum length)

Consequence
Transfer aborted with DIAGI=220, DIAGP=AWR + PeSIT code.
```

 

```
V23 format
V24 format
Error
<span id="CFTH17E"></span>CFTH17E PART=&part Invalid Check Point acknowledge
&n
CFTH17E Invalid Check Point acknowledge <PART=&part &n>
Explanation
The synchronization check point number is not correct.
```

 

```
V23 format
V24 format
Error
<span id="CFTH18E"></span>CFTH18E Incoming call reject error NCR=&ncr NCS=&ncs
NET=&net
CFTH18E Incoming call reject error <NCR=&ncr NCS=&cs NET=&net>
Explanation
Cannot refuse an incoming call.
Consequence
The transfer is aborted by the protocol task (it is not registered
in the catalog)
```

 

```
V23 format
V24 format
Error
<span id="CFTH19E"></span>CFTH19E Incoming call accept error NCR=&ncr NCS=&ncs
NET=&net
CFTH19E Incoming call accept error <NCR=&ncr NCS=&cs NET=&net>
Explanation
Cannot accept an incoming call.
Consequence
The transfer is aborted by the protocol task (it is not
registered in the catalog).
```

 

```
V23 format
V24 format
Error
<span id="CFTH20E"></span>CFTH20E Invalid CONNECT FPDU &str
CFTH20E Invalid CONNECT FPDU <&str>
Explanation
The CONNECT FPDU sent by the REQUESTER partner does not
conform.
The field "&str" is an explicit character
string:

-   CRC option
    = n: The remote partner proposes a value for the CRC
    option which does not comply with protocol specifications.

<!-- -->

-   This
    value is displayed: Only the values 0 (no CRC) and 1 (application of
    a CRC) are correct

<!-- -->

-   Version
    = n: The protocol version proposed by the remote partner
    does not comply with the specifications of the PeSIT protocol.Only the values 1 (version D) and 2 (version E)
    are allowed. The incorrect value is displayed in the message

<!-- -->

-   Window
    without Pacing: A synchronization window is specified even though
    the interval is null

<!-- -->

-   Window
    = n too large: The synchronization window negotiated by the REQUESTER
    partner is too large. The SIT profile does not allow a value greater than
    16

<!-- -->

-   Access
    = n: The correct access types are 0 for write mode,
    1 for read mode and 2 for read/write mode. The other values represent
    a violation of the protocol. The incorrect value received is displayed
    in the message.

<!-- -->

-   Resynchronization
    = n: The functional resynchronization unit is negotiated
    by the value 0 (no) or 1 (yes). Any other value is not allowed

<!-- -->

-   Pacing
    = n not authorized: The synchronization interval negotiated by the
    SERVER partner does not comply with the specifications of the SIT profile.
    The values 1, 2 and 3 are not allowed

<!-- -->

-   Application
    type relation R=sapp S=rapp: The SIT profile imposes a correlation between the
    sender and receiver applications. This correlation is not respected. The
    message displays the first byte of PI 3 and 4 of the CONNECT FPDU in numeric
    form

<!-- -->

-   Mismatch
    between header and FPDU size: The FPDU length indicated in the header is not
    equal to the length of the FPDU received

<!-- -->

-   Unknown
    FPDU: The number identifying the received FPDU is not
    referenced

<!-- -->

-   Missing
    PI number n into FPDU: The PI is mandatory for this type of FPDU

<!-- -->

-   Unknown
    PI number n into FPDU: The PI is unknown for this type of FPDU

<!-- -->

-   PGI n
    in PGI into FPDU: The presence of a PGI embedded in another PGI is
    invalid

<!-- -->

-   Invalid
    length n for PI n into FPDU: The length of the PI is invalid (less than minimum
    length or greater than maximum length)

Consequence
The transfer is aborted without trace in the catalog.
```

 

```
V23 format
V24 format
Error
<span id="CFTH21E"></span>CFTH21E PART=&part MAIN task Synchronization error
CR=&cr CS=&scs
CFTH21E MAIN task Synchronization error <PART=&part CR= &cr CS=&cs>
Explanation
{{< TransferCFT/componentshortname >}} internal synchronization error.
```

 

```
V23 format
V24 format
Error
<span id="CFTH22E"></span>CFTH22E PART=&part rejected DIAGI=&diagi <HOST=&addr>
CFTH22E NPART=&part rejected DIAGI=&diagi <HOST=&pstate>
Explanation
Where:

-   addr: The caller's IP address

{{< TransferCFT/componentshortname >}} refuses to open a protocol session following
a request to do so from a partner.
The message displays the {{< TransferCFT/componentshortname >}}
diagnostic code.
Consequence
The transfer is aborted. No trace of this attempt appears in
the catalog.
```

 

```
V23 format
V24 format
Error
<span id="CFTH23E"></span>CFTH23E NPART=&part rejected EVENT=&pevent
CFTH23E PART=&part rejected EVENT=&pevent
Explanation
{{< TransferCFT/componentshortname >}} refuses to open a protocol session for internal
reasons, following a request to do so from a partner. The event which
caused this rejection is displayed in the message.
Consequence
The transfer is aborted. No trace of this attempt appears in
the catalog.
```

 

```
V23 format
V24 format
Error
<span id="CFTH24E"></span>CFTH24E PART=&part Invalid CREATE FPDU &str
CFTH24E Invalid CREATE FPDU <PART=&part &str>
Explanation
The CREATE FPDU sent by the REQUESTER partner does not
conform. The field "&str" is an explicit character string:

-   IDT is null:
    Reception of a CREATE FPDU with a null Transfer
    Identifier (PI 13)

<!-- -->

-   Restart = n:
    Invalid value for the restart option of a transfer

<!-- -->

-   Data Code = n:
    Unknown code for the data to be transported

<!-- -->

-   Priority = n:
    Invalid priority assigned to the transfer

<!-- -->

-   Record Format
    = n: Unknown record format

<!-- -->

-   Record size =
    n greater than Pacing: The record size is greater than the synchronization
    interval

<!-- -->

-   NSDU size = n
    too lower for LRECL = n: In the SIT profile, as segmentation is not authorized,
    a record must fit in the FPDU. The negotiated NSDU size (RUSIZE) must
    therefore be greater than the record length of the file (plus 6 for the
    FPDU header).

<!-- -->

-   File Organization
    = n: Unknown file organization

<!-- -->

-   Key length without
    indexed organization: A key length is specified for a file that is not
    indexed

<!-- -->

-   Key Position
    without indexed organization: A key position is specified for a file that is
    not indexed

<!-- -->

-   Space Unit in
    record without fixed format: A file must be in fixed format for its size to
    be expressed as a number of records

<!-- -->

-   Space Unit =
    n: Space reservation unit unknown

<!-- -->

-   Mismatch between
    header and FPDU size: The FPDU length indicated in the header is not
    equal to the length of the FPDU received

<!-- -->

-   Unknown FPDU:
    The number identifying the received FPDU is not
    referenced

<!-- -->

-   Missing PI number
    n into FPDU: The PI is mandatory for this type of FPDU

<!-- -->

-   Unknown PI number
    n into FPDU: The PI is unknown for this type of FPDU

<!-- -->

-   PGI n in PGI
    into FPDU: The presence of a PGI embedded in another PGI is
    invalid

<!-- -->

-   Invalid length
    n for PI n into FPDU: The length of the PI is invalid (less than minimum
    length or greater than maximum length)

Consequence
Transfer aborted with DIAGI=220, DIAGP=CRE + PeSIT code.
```

 

```
V23 format
V24 format
Information
<span id="CFTH25I"></span>CFTH25I PART=&part Concatenation area allocation
failure CS=&scs
CFTH25I Concatenation area allocation failure <PART=&part CS=&cs>
Explanation
Cannot allocate a working area to execute the concatenation
option.
Consequence
The transfer continues but the concatenation option remains
inhibited for the rest of the session.
```

 

```
V23 format
V24 format
Error
<span id="CFTH26E"></span>CFTH26E PART=&part
Too many data without synchronization
CFTH26E Too many data without synchronization <PART=&part>
Explanation
Detection of a synchronization error.
Consequence
The transfer is aborted.
```

 

```
V23 format
V24 format
Error
<span id="CFTH27E"></span>CFTH27E PART=&part SYNC FPDU without synchronization
CFTH27E SYNC FPDU without synchronization <PART=&part>
Explanation
A synchronization FPDU was received unexpectedly as the
Functional Synchronization Unit was not negotiated at the beginning of
the session.
Consequence
The transfer
is aborted with a {{< TransferCFT/componentshortname >}} 730 diagnostic code, a protocol violation.
```

 

```
V23 format
V24 format
Error
<span id="CFTH28E"></span>CFTH28E PART=&part Invalid Checkpoint n
CFTH28E Invalid Chekpoint <PART=&part &n>
Explanation
Reception of an invalid synchronization point, which does
not follow the sequence.
Consequence
The transfer is aborted.
```

 

```
V23 format
V24 format
Error
<span id="CFTH29E"></span>CFTH29E PART=&part Invalid FPDU RC=&n
CFTH29E Invalid FPDU RC=&rc Incoming call address= &str <PART=&part>
Explanation
An inconsistent FPDU has been received. The RC code enables
the error found to be defined more specifically: this code is identical
to the one included in the PDU_iNN protocol diagnostic message.
Consequence
The transfer is aborted.
```

 

```
V23 format
V24 format
Error
<span id="CFTH30E"></span>CFTH30E PART=&part Invalid AckORF FPDU &str
CFTH30E Invalid AckORF FPDU <PART=&part &str>
Explanation
The AckORF FPDU sent by the SERVER partner does not conform.
The field "&str" is an explicit character
string:

-   Compression
    Indicator = n: The compression indicator has a value which does
    not comply with the specifications of the PeSIT protocol (0 no compression,
    1 compression)

<!-- -->

-   Compression
    Value without Indicator: A compression value is negotiated even though the
    indicator inhibits the compression option

<!-- -->

-   Compression
    Indicator without Value: The compression indicator is set even though the
    negotiated value is null

<!-- -->

-   Compression
    Value = n: The negotiated compression value does not comply
    with to the specifications of the PeSIT protocol

<!-- -->

-   Compression
    Negotiation: n for n: The negotiated compression is greater than the
    proposed compression

<!-- -->

-   Extended
    LRECL greater than PACING: n for n:Compression may cause a record to be extended.
    This risk, which is measurable (1 byte for 32 bytes), means that the record
    size becomes greater than the synchronization interval

<!-- -->

-   Mismatch
    between header and FPDU size: The FPDU length indicated in the header is not
    equal to the length of the FPDU received

<!-- -->

-   Unknown
    FPDU: The number identifying the received FPDU is not
    referenced

<!-- -->

-   Missing
    PI number n into FPDU: The PI is mandatory for this type of FPDU

<!-- -->

-   Unknown
    PI number n into FPDU: The PI is unknown for this type of FPDU

<!-- -->

-   PGI n
    in PGI into FPDU: The presence of a PGI embedded in another PGI is
    invalid

<!-- -->

-   Invalid
    length n for PI n into FPDU: The length of the PI is invalid (less than minimum
    length or greater than maximum length)

Consequence
Transfer aborted with DIAGI=220, DIAGP=AOF + PeSIT code.
```

 

```
V23 format
V24 format
Error
<span id="CFTH31E"></span>CFTH31E PART=&part Invalid AckTRANS.END FPDU &str
CFTH31E Invalid AckTRANS.END FPDU <PART=&part &str>
Explanation
The AckTRANSFER.END FPDU sent by the SERVER partner does
not conform.
The field "&str" is an explicit character
string:

-   Byte count mismatch
    n for n: The number of bytes transferred does not correspond
    to the {{< TransferCFT/componentshortname >}}-maintained counter

<!-- -->

-   Record count
    mismatch n for n: The number of records transferred does not correspond
    to the {{< TransferCFT/componentshortname >}}-maintained counter

<!-- -->

-   Mismatch between
    header and FPDU size: The FPDU length indicated in the header is not equal
    to the length of the FPDU received

<!-- -->

-   Unknown FPDU:
    The number identifying the received FPDU is not referenced

<!-- -->

-   Missing PI number
    n into FPDU: The PI is mandatory for this type of FPDU

<!-- -->

-   Unknown PI number
    n into FPDU: The PI is unknown for this type of FPDU

<!-- -->

-   PGI n in PGI
    into FPDU: The presence of a PGI embedded in another PGI is invalid

<!-- -->

-   Invalid length
    n for PI n into FPDU: The length of the PI is invalid (less than minimum
    length or greater than maximum length)

Consequence
Transfer aborted with DIAGI=220, DIAGP=ATE + PeSIT code.
```

 

```
V23 format
V24 format
Error
<span id="CFTH32E"></span>CFTH32E PART=&part Invalid AckMESSAGE FPDU &str
CFTH32E Invalid AckMESSAGE FPDU <PART=&part &str>
Explanation
This message is only displayed in security-enabled mode
and corresponds to a security problem.
The field "&str" is an explicit character
string:

-   Mismatch between
    header and FPDU size: The FPDU length indicated in the header is not
    equal to the length of the FPDU received

<!-- -->

-   Unknown FPDU:
    The number identifying the received FPDU is not
    referenced

<!-- -->

-   Missing PI number
    n into FPDU: The PI is mandatory for this type of FPDU

<!-- -->

-   Unknown PI number
    n into FPDU: The
    PI is unknown for this type of FPDU

<!-- -->

-   PGI n in PGI
    into FPDU: The presence of a PGI embedded in another PGI is
    invalid

<!-- -->

-   Invalid length
    n for PI n into FPDU: The length of the PI is invalid (less than minimum
    length or greater than maximum length)

Consequence
Transfer aborted with DIAGI=220, DIAGP=AMG + PeSIT code.
```

 

```
V23 format
V24 format
Error
<span id="CFTH33E"></span>CFTH33E PART=&part Invalid AckSELECT FPDU &str
CFTH33E Invalid AckSELECT FPDU <PART=&part &str>
Explanation
The AckSELECT FPDU sent by the SERVER partner does not
conform.
The field "&str" is an explicit character
string:

-   File type value
    not authorized: Reception of an AckSELECT FPDU with an invalid
    file type (PI 11) The values between 0xFFFC and 0xFFFF are invalid

<!-- -->

-   IDT is null:
    Reception of an AckSELECT FPDU with a null Transfer
    Identifier (PI 13)

<!-- -->

-   Data Code = n:
    Unknown code for the data to be transported

<!-- -->

-   Priority = n:
    Invalid priority assigned to the transfer

<!-- -->

-   Record Format
    = n: Unknown record format

<!-- -->

-   Record size =
    n greater than Pacing: The record size is greater then the synchronization
    interval

<!-- -->

-   NSDU size negotiation
    n for n: The negotiated NSDU size is greater than that proposed

<!-- -->

-   NSDU too small
    n: The negotiated NSDU size is smaller than the minimum
    authorized value (128)

<!-- -->

-   File Organization
    = n: Unknown file organization

<!-- -->

-   Key length without
    indexed organization: A key length is specified for a file that is not indexed

<!-- -->

-   Key Position
    without indexed organization: A key position is specified for a file that is not
    indexed

<!-- -->

-   Space Unit in
    record without fixed format: A file must be in fixed format for its size to be
    expressed as a number of records

<!-- -->

-   Space Unit =
    n: Space reservation unit unknown

<!-- -->

-   Mismatch between
    header and FPDU size: The FPDU length indicated in the header is not equal
    to the length of the FPDU received

<!-- -->

-   Unknown FPDU:
    The number identifying the received FPDU is not referenced

<!-- -->

-   Missing PI number
    n into FPDU: The PI is mandatory for this type of FPDU

<!-- -->

-   Unknown PI number
    n into FPDU: The PI is unknown for this type of FPDU

<!-- -->

-   PGI n in PGI
    into FPDU: The presence of a PGI embedded in another PGI is invalid

<!-- -->

-   Invalid length
    n for PI n into FPDU: The length of the PI is invalid (less than minimum
    length or greater than maximum length)

Consequence
Transfer aborted with DIAGI=220, DIAGP=ASE + PeSIT code.
```

 

```
V23 format
V24 format
Error
<span id="CFTH34E"></span>CFTH34E PART=&part Invalid ORF FPDU &str
CFTH34E Invalid ORF FPDU <PART=&part &str>
Explanation
The ORF FPDU sent by the REQUESTER partner does not conform.
The field "&str" is an explicit character
string:

-   Compression
    Indicator = n: The compression indicator has a value that does not
    comply with the specifications of the PeSIT protocol (0 no compression,
    1 compression)

<!-- -->

-   Compression
    Value without Indicator: A compression value is negotiated even though the
    indicator inhibits the compression option

<!-- -->

-   Compression
    Indicator without Value: The compression indicator is set even though the negotiated
    value is null

<!-- -->

-   Compression Value
    = n: The negotiated compression value does not comply with
    the specifications of the PeSIT protocol

<!-- -->

-   Extended Record
    size greater than pacing: n for n: Compression may cause a record to be extended. This
    risk, which is measurable (1 byte for 32 bytes), means that the record
    size becomes greater than the synchronization interval

<!-- -->

-   Mismatch
    between header and FPDU size: The FPDU length indicated in the header is not equal
    to the length of the FPDU received

<!-- -->

-   Unknown
    FPDU: The number identifying the received FPDU is not referenced

<!-- -->

-   Missing
    PI number n into FPDU:The PI is mandatory for this type of FPDU

<!-- -->

-   Unknown PI number
    n into FPDU: The PI is unknown for this type of FPDU

<!-- -->

-   PGI n
    in PGI into FPDU: The presence of a PGI embedded in another PGI is invalid

<!-- -->

-   Invalid
    length n for PI n into FPDU: The length of the PI is invalid (less than minimum
    length or greater than maximum length)

Consequence
Transfer aborted with DIAGI=220, DIAGP=ORF + PeSIT code.
```

 

```
V23 format
V24 format
Error
<span id="CFTH35E"></span>CFTH35E PART=&part Invalid TRANS.END FPDU &str
CFTH35E Invalid TRANS.END FPDU <PART=&part &str>
Explanation
This message is only displayed in security-enabled mode
and corresponds to a security problem.
The field "&str" is an explicit character
string:

-   Mismatch between
    header and FPDU size: The FPDU length indicated in the header is not equal
    to the length of the FPDU received

<!-- -->

-   Unknown
    FPDU: The number identifying the received FPDU is not referenced

<!-- -->

-   Missing
    PI number n into FPDU: The PI is mandatory for this type of FPDU

<!-- -->

-   Unknown
    PI number n into FPDU: The PI is unknown for this type of FPDU

<!-- -->

-   PGI n
    in PGI into FPDU: The presence of a PGI embedded in another PGI is invalid

<!-- -->

-   Invalid
    length n for PI n into FPDU: The length of the PI is invalid (less than minimum
    length or greater than maximum length)

Consequence
Transfer aborted with DIAGI=220, DIAGP=TFE + PeSIT code.
```

 

```
V23 format
V24 format
Error
<span id="CFTH36E"></span>CFTH36E PART=&part Invalid MESSAGE FPDU &str
CFTH36E Invalid MESSAGE FPDU <PART=&part &str>
Explanation
The MESSAGE FPDU sent by the REQUESTER partner does not
conform.
The field "&str" is an explicit character
string:

-   IDT is
    null: Reception of a MESSAGE FPDU with a null Transfer Identifier
    (PI 13)

<!-- -->

-   Attribute
    = n: PI 14 in the MESSAGE FPDU is set to an invalid value
    (attribute request)

<!-- -->

-   Data
    Code = n: Unknown code for the data to be transported

<!-- -->

-   Mismatch
    between header and FPDU size: The FPDU length indicated in the header is not equal
    to the length of the FPDU received

<!-- -->

-   Unknown
    FPDU: The number identifying the received FPDU is not referenced

<!-- -->

-   Missing
    PI number n into FPDU: The PI is mandatory for this type of FPDU

<!-- -->

-   Unknown
    PI number n into FPDU: The PI is unknown for this type of FPDU

<!-- -->

-   PGI n
    in PGI into FPDU: The presence of a PGI embedded in another PGI is invalid

<!-- -->

-   Invalid
    length n for PI n into FPDU: The length of the PI is invalid (less than minimum
    length or greater than maximum length)

Consequence
Transfer aborted with DIAGI=220, DIAGP=MSG + PeSIT code.
```

 

```
V23 format
V24 format
Error
<span id="CFTH37E"></span>CFTH37E PART=&part Invalid D.MESSAGE FPDU &str
CFTH37E Invalid D.MESSAGE FPDU <PART=&part &str>
Explanation
The START of MESSAGE FPDU sent by the REQUESTER partner
does not conform.
The field "&str" is an explicit character
string:

-   IDT is
    null: Reception of a D.MESSAGE FPDU with a null Transfer
    Identifier (PI 13)

<!-- -->

-   Attribute
    = n: PI 14 of the D.MESSAGE FPDU is set to an invalid value
    (attribute request)

<!-- -->

-   Data
    Code = n: Unknown code for the data to be transported

<!-- -->

-   Mismatch
    between header and FPDU size: The FPDU length indicated in the header is not equal
    to the length of the FPDU received

<!-- -->

-   Unknown
    FPDU: The number identifying the received FPDU is not referenced

<!-- -->

-   Missing
    PI number n into FPDU: The PI is mandatory for this type of FPDU

<!-- -->

-   Unknown
    PI number n into FPDU: The PI is unknown for this type of FPDU

<!-- -->

-   PGI n
    in PGI into FPDU: The presence of a PGI embedded in another PGI is invalid

<!-- -->

-   Invalid
    length n for PI n into FPDU: The length of the PI is invalid (less than minimum
    length or greater than maximum length)

Consequence
Transfer aborted with DIAGI=220, DIAGP=DMG + PeSIT code.
```

 

```
V23 format
V24 format
Error
<span id="CFTH38E"></span>CFTH38E PART=&part Invalid READ FPDU &str
CFTH38E Invalid READ FPDU <PART=&part &str>
Explanation
The READ FPDU sent by the REQUESTER partner does not conform.
The field "&str" is an explicit character
string:

-   Restart
    point must be null for new transfer: Reception of a READ FPDU with a restart point other
    than 0 for a new transfer

<!-- -->

-   Mismatch
    between header and FPDU size: The FPDU length indicated in the header is not equal
    to the length of the FPDU received

<!-- -->

-   Unknown
    FPDU:

<!-- -->

-   Missing
    PI number n into FPDU: The PI is mandatory for this type of FPDU

<!-- -->

-   Unknown
    PI number n into FPDU: The PI is unknown for this type of FPDU

<!-- -->

-   PGI n
    in PGI into FPDU: The presence of a PGI embedded in another PGI is invalid

<!-- -->

-   Invalid
    length n for PI n into FPDU: The length of the PI is invalid (less than minimum
    length or greater than maximum length)

Consequence
Transfer aborted with DIAGI=220, DIAGP=RDF + PeSIT code.
```

 

```
V23 format
V24 format
Error
<span id="CFTH39E"></span>CFTH39E PART=&part Invalid SELECT FPDU &str
CFTH39E Invalid SELECT FPDU <PART=&part &str>
Explanation
The SELECT FPDU sent by the REQUESTER partner does not
conform.
The field "&str" is an explicit character
string:

-   IDT not
    null: Reception of a SELECT FPDU with a non-null Transfer
    Identifier (PI 13) for a new transfer

<!-- -->

-   IDT null
    with restart: Reception of a SELECT FPDU with a null Transfer Identifier
    (PI 13) for a transfer to be restarted

<!-- -->

-   Attribute
    = n: PI 15 of the SELECT FPDU is set to an invalid value
    (file attribute request)

<!-- -->

-   Restart
    = n: PI 15 of the SELECT FPDU is set to an invalid value
    (restart or new transfer)

<!-- -->

-   Priority
    = n: PI 17 of the SELECT FPDU is set to an invalid value
    (transfer priority)

<!-- -->

-   NSDU
    too small n: The negotiated NSDU size is smaller than the minimum
    allowed value (128)

<!-- -->

-   Mismatch
    between header and FPDU size: The FPDU length indicated in the header is not equal
    to the length of the FPDU received

<!-- -->

-   Unknown
    FPDU: The number identifying the received FPDU is not referenced

<!-- -->

-   Missing
    PI number n into FPDU: The PI is mandatory for this type of FPDU

<!-- -->

-   Unknown
    PI number n into FPDU: The PI is unknown for this type of FPDU

<!-- -->

-   PGI n
    in PGI into FPDU: The presence of a PGI embedded in another PGI is invalid

<!-- -->

-   Invalid
    length n for PI n into FPDU: The length of the PI is invalid (less than minimum
    length or greater than maximum length)

Consequence
Transfer aborted with DIAGI=220, DIAGP=SEL + PeSIT code.
```

 

```
V23 format
V24 format
Error
<span id="CFTH40E"></span>CFTH40E PART=&part Invalid DTF FPDU (MULTART)
CFTH40E Invalid DTF FPDU (MULTART) <PART=&part>
Explanation
The DTF FPDU received is multi-record but it is not valid
(the sum of the record lengths is not equal to the total length of the
received FPDU).
Consequence
The transfer is aborted. The protocol code transported to the
remote partner is 220.
```

 

```
V23 format
V24 format
Error
<span id="CFTH41E"></span>CFTH41E PART=&part Invalid DTF.END FPDU &str
CFTH41E Invalid DTF.END FPDU <PART=&part &str>
Explanation
The DTF END (end of data) FPDU sent by the sender partner
does not conform.
The field "&str" is an explicit character
string:

-   Mismatch
    between header and FPDU size:

The FPDU length indicated in the header is not equal
to the length of the FPDU received

-   Unknown
    FPDU:

The number identifying the received FPDU is not referenced

-   Missing
    PI number n into FPDU:

The PI is mandatory for this type of FPDU

-   Unknown
    PI number n into FPDU:

The PI is unknown for this type of FPDU

-   PGI n
    in PGI into FPDU:

The presence of a PGI embedded in another PGI is invalid

-   Invalid
    length n for PI n into FPDU:

The length of the PI is invalid (less than minimum
length or greater than maximum length)
Consequence
Transfer aborted with DIAGI=220, DIAGP=DTE + PeSIT code.
```

 

```
V23 format
V24 format
Error
<span id="CFTH42E"></span>CFTH42E PART=&part Invalid SYNC FPDU &str
CFTH42E Invalid SYNC FPDU <PART=&part &str>
Explanation
The SYNC (set synchronization point) FPDU sent by the sender
partner does not conform.
The field "&str" is an explicit character
string:

-   Mismatch
    between header and FPDU size:

The FPDU length indicated in the header is not equal
to the length of the FPDU received

-   Unknown
    FPDU:

The number identifying the received FPDU is not referenced

-   Missing
    PI number n into FPDU:

The PI is mandatory for this type of FPDU

-   Unknown
    PI number n into FPDU:

The PI is unknown for this type of FPDU

-   PGI n
    in PGI into FPDU:

The presence of a PGI embedded in another PGI is invalid

-   Invalid
    length n for PI n into FPDU:

The length of the PI is invalid (less than minimum
length or greater than maximum length)
Consequence
Transfer aborted with DIAGI=220, DIAGP=SYN + PeSIT code.
```

 

```
V23 format
V24 format
Error
<span id="CFTH43E"></span>CFTH43E PART=&part Invalid AckSYNC 
FPDU &str
CFTH43E Invalid AckSYNC FPDU <PART=&part &str>
Explanation
The AckSYNC (acknowledge synchronization point) FPDU sent
by the receiver partner does not conform.
The field "&str" is an explicit character
string:

-   Mismatch
    between header and FPDU size:

The FPDU length indicated in the header is not equal
to the length of the FPDU received

-   Unknown
    FPDU:

The number identifying the received FPDU is not referenced

-   Missing
    PI number n into FPDU:

The PI is mandatory for this type of FPDU

-   Unknown
    PI number n into FPDU:

The PI is unknown for this type of FPDU

-   PGI n
    in PGI into FPDU:

The presence of a PGI embedded in another PGI is invalid

-   Invalid
    length n for PI n into FPDU:

The length of the PI is invalid (less than minimum
length or greater than maximum length)
Consequence
Transfer aborted with DIAGI=220, DIAGP=ASY + PeSIT code.
```

 

```
V23 format
V24 format
Error
<span id="CFTH44E"></span>CFTH44E PART=&part Invalid IDT FPDU &str
CFTH44E Invalid IDT FPDU <PART=&part &str>
Explanation
The IDT (transfer interrupt) FPDU sent by the partner does
not conform.
The field "&str" is an explicit character
string:

-   Mismatch
    between header and FPDU size:

The FPDU length indicated in the header is not equal
to the length of the FPDU received,

-   Unknown
    FPDU:

The number identifying the received FPDU is not referenced

-   Missing
    PI number n into FPDU:

The PI is mandatory for this type of FPDU

-   Unknown
    PI number n into FPDU:

The PI is unknown for this type of FPDU

-   PGI n
    in PGI into FPDU:

The presence of a PGI embedded in another PGI is invalid

-   Invalid
    length n for PI n into FPDU:

The length of the PI is invalid (less than minimum
length or greater than maximum length)
Consequence
Transfer aborted with DIAGI=220, DIAGP=IDT + PeSIT code.
```

 

```
V23 format
V24 format
Error
<span id="CFTH45E"></span>CFTH45E PART=&part Invalid AckIDT FPDU &str
CFTH45E Invalid AckIDT FPDU <PART=&part &str>
Explanation
The AckIDT (acknowledge transfer interrupt) FPDU sent by
the partner does not conform.
The field "&str" is an explicit character
string:

-   Mismatch
    between header and FPDU size:

The FPDU length indicated in the header is not equal
to the length of the FPDU received

-   Unknown
    FPDU:

The number identifying the received FPDU is not referenced

-   Missing
    PI number n into FPDU:

The PI is mandatory for this type of FPDU

-   Unknown
    PI number n into FPDU:

 The
PI is unknown for this type of FPDU

-   PGI n
    in PGI into FPDU:

The presence of a PGI embedded in another PGI is invalid

-   Invalid
    length n for PI n into FPDU:

The length of the PI is invalid (less than minimum
length or greater than maximum length)
Consequence
Transfer aborted with DIAGI=220, DIAGP=AID + PeSIT code.
```

 

```
V23 format
V24 format
Error
<span id="CFTH46E"></span>CFTH46E PART=&part Invalid RESYNC FPDU &str
CFTH46E Invalid RESYNC FPDU <PART=&part &str>
Explanation
The RESYNC (dynamic transfer resynchronization) FPDU sent
by the sender partner does not conform.
The field "&str" is an explicit character
string:

-   Resynchronization
    is not authorized:

Dynamic resynchronization is not authorized (CFTPROT
RESYNC parameter) or the maximum number of resynchronizations is exceeded
(CFTPROT RESTART parameter),

-   Mismatch
    between header and FPDU size:

The FPDU length indicated in the header is not equal
to the length of the FPDU received

-   Unknown
    FPDU:

The number identifying the received FPDU is not referenced

-   Missing
    PI number n into FPDU:

The PI is mandatory for this type of FPDU

-   Unknown
    PI number n into FPDU:

The PI is unknown for this type of FPDU

-   PGI n
    in PGI into FPDU:

The presence of a PGI embedded in another PGI is invalid

-   Invalid
    length n for PI n into FPDU:

The length of the PI is invalid (less than minimum
length or greater than maximum length)
Consequence
Transfer aborted with DIAGI=220, DIAGP=RST + PeSIT code.
```

 

```
V23 format
V24 format
Error
<span id="CFTH47E"></span>CFTH47E PART=&part Invalid DESELECT FPDU &str
CFTH47E Invalid DESELECT FPDU <PART=&part &str>
Explanation
The DESELECT FPDU sent by the requester partner does not
conform.
The field "&str" is an explicit character
string:

-   Mismatch
    between header and FPDU size: The FPDU length indicated in the header
    is not equal to the length of the FPDU received
-   Unknown FPDU:
    The number identifying the received FPDU is not referenced
-   Missing PI number
    n into FPDU: The PI is mandatory for this type of FPDU
-   Unknown PI number
    n into FPDU: The PI is unknown for this type of FPDU
-   PGI n in PGI
    into FPDU: The presence of a PGI embedded in another PGI is invalid
-   Invalid length
    n for PI n into FPDU: The length of the PI is invalid (less than minimum
    length or greater than maximum length)

Consequence
Transfer aborted with DIAGI=220, DIAGP=DSE + PeSIT code.
```

 

```
V23 format
V24 format
Error
<span id="CFTH48E"></span>CFTH48E PART=&part Invalid DESELECT FPDU &str
CFTH48E Invalid AckREAD FPDU <PART=&part &str>
Explanation
The AckRead FPDU sent by the receiver/sender partner does
not conform.
The field "&str" is an explicit character
string:

-   Mismatch between
    header and FPDU size: The FPDU length indicated in the header is not equal
    to the length of the FPDU received
-   Unknown FPDU:
    The number identifying the received FPDU is not referenced
-   Missing PI number
    n into FPDU: The PI is mandatory for this type of FPDU
-   Unknown PI number
    n into FPDU: The PI is unknown for this type of FPDU
-   PGI n in PGI
    into FPDU: The presence of a PGI embedded in another PGI is invalid
-   Invalid length
    n for PI n into FPDU: The length of the PI is invalid (less than minimum
    length or greater than maximum length)

Consequence
Transfer aborted with DIAGI=220, DIAGP=ARD + PeSIT code.
```

 

```
V23 format
V24 format
Error
<span id="CFTH49E"></span>CFTH49E PART=&part Invalid WRITE FPDU &str
CFTH49E Invalid WRITE FPDU <PART=&part &str>
Explanation
The WRITE FPDU sent by the requester/sender partner does
not conform.
The field "&str" is an explicit character
string:

-   Mismatch
    between header and FPDU size: The FPDU length indicated in the header
    is not equal to the length of the FPDU received
-   Unknown
    FPDU: The number identifying the received FPDU is not referenced
-   Missing
    PI number n into FPDU: The PI is mandatory for this type of FPDU
-   Unknown
    PI number n into FPDU: The PI is unknown for this type of FPDU
-   PGI n
    in PGI into FPDU: The presence of a PGI embedded in another PGI is invalid
-   Invalid
    length n for PI n into FPDU: The length of the PI is invalid (less than
    minimum length or greater than maximum length)

Consequence
Transfer aborted with DIAGI=220, DIAGP=WRI + PeSIT code.
```

 

```
V23 format
V24 format
Error
<span id="CFTH50E"></span>CFTH50E PART=&part Invalid M.MESSAGE FPDU &str
CFTH50E Invalid M.MESSAGE FPDU <PART=&part &str>
Explanation
The Middle of Message FPDU sent by the requester partner
does not conform.
The field "&str" is an explicit character
string:

-   Mismatch
    between header and FPDU size: The FPDU length indicated in the header
    is not equal to the length of the FPDU received
-   Unknown
    FPDU: The number identifying the received FPDU is not referenced
-   Missing
    PI number n into FPDU: The PI is mandatory for this type of FPDU
-   Unknown
    PI number n into FPDU: The PI is unknown for this type of FPDU
-   PGI n
    in PGI into FPDU: The presence of a PGI embedded in another PGI is invalid
-   Invalid
    length n for PI n into FPDU: The length of the PI is invalid (less than
    minimum length or greater than maximum length)

Consequence
Transfer aborted with DIAGI=220, DIAGP=MMG + PeSIT code.
```

 

```
V23 format
V24 format
Error
<span id="CFTH51E"></span>CFTH51E PART=&part Invalid F.MESSAGE FPDU &str
CFTH51E Invalid F.MESSAGE FPDU <PART=&part &str>
Explanation
The End of Message FPDU sent by the requester partner does
not conform.
The field "&str" is an explicit character
string:

-   Mismatch between
    header and FPDU size: The FPDU length indicated in the header is not equal
    to the length of the FPDU received
-   Unknown FPDU:The
    number identifying the received FPDU is not referenced
-   Missing PI number
    n into FPDU:The PI is mandatory for this type of FPDU
-   Unknown PI number
    n into FPDU:The PI is unknown for this type of FPDU
-   PGI n in PGI
    into FPDU: The presence of a PGI embedded in another PGI is invalid
-   Invalid length
    n for PI n into FPDU:The length of the PI is invalid (less than minimum
    length or greater than maximum length)

Consequence
Transfer aborted with DIAGI=220, DIAGP=FMG + PeSIT code.
```

 

```
V23 format
V24 format
Error
<span id="CFTH52E"></span>CFTH52E PART=&part Invalid AckCLOSE FPDU &str
CFTH52E Invalid AckCLOSE FPDU <PART=&part &str>
Explanation
The AckCLOSE FPDU sent by the server partner does not conform.
The field "&str" is an explicit character
string:

-   Mismatch
    between header and FPDU size: The FPDU length indicated in the header
    is not equal to the length of the FPDU received
-   Unknown
    FPDU: The number identifying the received FPDU is not referenced
-   Missing
    PI number n into FPDU: The PI is mandatory for this type of FPDU
-   Unknown
    PI number n into FPDU: The PI is unknown for this type of FPDU
-   PGI n
    in PGI into FPDU: The presence of a PGI embedded in another PGI is invalid
-   Invalid
    length n for PI n into FPDU: The length of the PI is invalid (less than
    minimum length or greater than maximum length)

Consequence
Transfer aborted with DIAGI=220, DIAGP=ACF + PeSIT code.
```

 

```
V23 format
V24 format
Error
<span id="CFTH53E"></span>CFTH53E PART=&part Invalid AckDESELECT  FPDU
&str
CFTH53E Invalid AckDESELECT FPDU <PART=&part &str>
Explanation
The AckDESELECT FPDU sent by the server partner does not
conform.
The field "&str" is an explicit character
string:

-   Mismatch between
    header and FPDU size: The FPDU length indicated in the header is not equal
    to the length of the FPDU received
-   Unknown FPDU: The
    number identifying the received FPDU is not referenced
-   Missing PI number
    n into FPDU: The PI is mandatory for this type of FPDU
-   Unknown PI number
    n into FPDU: The PI is unknown for this type of FPDU
-   PGI n in PGI into
    FPDU: The presence of a PGI embedded in another PGI is invalid
-   Invalid length
    n for PI n into FPDU: The length of the PI is invalid (less than minimum
    length or greater than maximum le

Consequence
Transfer aborted with DIAGI=220, DIAGP=ADS + PeSIT code.
```

 

```
V23 format
V24 format
Error
<span id="CFTH54E"></span>CFTH54E PART=&part Invalid CLOSE FPDU &str
CFTH54E Invalid CLOSE FPDU <PART=&part &str>
Explanation
The CLOSE (file close) FPDU sent by the requester partner
does not conform.
The field "&str" is an explicit character
string:

-   Mismatch
    between header and FPDU size: The FPDU length indicated in the header
    is not equal to the length of the FPDU received
-   Unknown
    FPDU: The number identifying the received FPDU is not referenced
-   Missing
    PI number n in FPDU: The PI is mandatory for this type of FPDU
-   Unknown
    PI number n in FPDU: The PI is unknown for this type of FPDU
-   PGI n
    in PGI into FPDU: The presence of a PGI embedded in another PGI is invalid
-   Invalid
    length n for PI n into FPDU: The length of the PI is invalid (less than
    minimum length or greater than maximum length)

Consequence
Transfer aborted with DIAGI=220, DIAGP=CRF + PeSIT code.
```

 

```
V23 format
V24 format
Error
<span id="CFTH55E"></span>CFTH55E PART=&part Invalid DTF FPDU &str
CFTH55E Invalid DTF FPDU <PART=&part &str>
Explanation
The DTF (data send) FPDU sent by the sender partner does
not conform.
The field "&str" is an explicit character
string:

-   Too much
    data without synchro

A synchronization interval, CFTPROT SPACING or RPACING
parameter, has been negotiated and the amount of data received since the
start of the transfer (or since the last synchronization FPDU) is greater
than this interval.
Consequence
Transfer aborted with DIAGI=220, DIAGP=DTF + PeSIT code.
```

 

```
V23 format
V24 format
Information
<span id="CFTH56I"></span>CFTH56I PART=&part IDS=&ids &prot &str session opened pi7=&n:&n HOST=&pstate &prot
CFTH56I &prot &str session opened <PART=&part IDS=&ids pi7=&n:&n HOST=&pstate> &prot
Explanation
An & prot session in either Requester or Server mode was opened, where &prot = PeSIT, ODETTE, or SFTP.And where:

-   PART: partner
-   PROT:
    local protocol definition (CFTPROT)
-   IDS:
    reference for this session
-   pi7:
    the window and the interval of the negotiated synchronization
-   pi2 and pi24:
    the window and the interval of the negotiated synchronization
-   HOST:
    -   Requester: The host address configured through CFTTCP for the related partner (either an IP or a logical hostname).
    -   Server: The IP address of the incoming connection.

```

 

```
V23 format
V24 format
Information
<span id="CFTH57I"></span>CFTH57I PART=&part IDS=&ids IDF=&idf IDT=&idt transfer selected pi25=&n
CFTH57I transfer selected PART=&part IDS=&ids IDF=&idf IDT=&idt
pi25=&n
Explanation
A
transfer passed the selection phase in the PeSIT session that was referenced
by the IDS field.
The field
pi25 indicate the maximum size of the negotiated message. The displayed
reference in the second message is the public transfer reference.
```

 

```
V23 format
V24 format
Information
<span id="CFTH58I"></span>CFTH58I PART=&part IDS=&ids IDF=&idf NIDT=&idt transfer deselected T=&n
CFTH58I transfer deselected <PART=&part IDS=&ids IDF=&idf NIDT=&idt T=&n>
Explanation
A transfer passed the deselection phase in the PeSIT
session referred to by the IDS. The IDS is the reference for this particular session context.
The T field indicates the armed time-out for the CFTPROT parameter:

-   disctd – requester mode,
-   discts – server mode

```

 

```
V23 format
V24 format
Information
<span id="CFTH59I"></span>CFTH59I PART=&part IDS=&ids IDM=&idm NIDT=&idt message transferred
CFTH59I message transferred PART=&part IDS=&ids IDM=&idm NIDT=&idt
Explanation
A message
transfer was carried out in the PeSIT as referenced by the IDS field,  where the IDS refers to this specific session context.
The displayed
reference in the second message is the public transfer reference.
```

 

```
V23 format
V24 format
Information
<span id="CFTH60I"></span>CFTH60I PART=&part IDS=&ids IDM=&idm NIDT=&idt [Reply | Nack] transferred
CFTH60I [Reply | Nack] transferred  PART=&part IDS=&ids IDM=&idm NIDT=&idt
Explanation
An acknowledgement
type transfer message was carried out in the PeSIT session, where
the IDS references the session context.
The
reference in the second message is the public transfer reference.
```

 

```
V23 format
V24 format
Information
<span id="CFTH61I"></span>CFTH61I PART=&part IDS=&ids ["Requester"|"Server"] &ref session closed &prot
CFTH61I &prot ["Requester"|"Server"] session closed <PART=&part IDS=&ids> &prot
Explanation
An & prot session in either Requester or Server mode was closed, where  &prot = PeSIT, ODETTE, or SFTP.
And:

-   &part: the partner identifier involved in the session
-   &ids: the reference for this session context

```

 

```
V23 format
V24 format
Information
<span id="CFTH62I"></span>CFTH62I REF=&ref
CFTH62I REF=&ref
Explanation
 

-   The transfer has passed the selection phase in the PeSIT
    session referenced by the IDS field.  
-   An acknowledgement-type message was performed in the
    PeSIT session referenced by the IDS, the session reference.
-   The pi25 field indicates the maximum size of the negotiated
    message.
-   The reference displayed in the second message is the public
    reference of the transfer (pi13.pi3.pi4.pi11.pi12.pi61.pi62).

```

 

```
V23 format
V24 format
Information
<span id="CFTH63I"></span>CFTH63I PART=&part IDS=&ids PESIT DMZ session for messages only
CFTH63I PESIT DMZ session for messages only <PART=&part IDS=&ids>
Explanation
A PeSIT DMZ session was open but only for mailing messages.
This message follows message CFTH56I, where the IDS is the session call id.
```

 

```
V23 format
V24 format
Information
<span id="CFTH64I"></span>CFTH64I PESIT session rejected L=&reason R=&diag
CFTH64I PESIT session rejected L=&local R=&reason
Explanation
Protocol connection refused at network level.

-   &reason: Network reason
-   &diag: Network diagnostic

```

 

```
V23 format
V24 format
Information
<span id="CFTH65I"></span>CFTH65I PART=&part IDS=&ids PESIT DMZ permanent session control call=&n
CFTH65I PESIT DMZ permanent session control call=&n <PART=&part IDS=&ids >
Explanation
Support for permanent links in DMZ.
{{< TransferCFT/componentshortname >}} in DMZ does not give the TURN when there are
no  more files to send, but sends
an FPDU Control Call to the initiator
{{< TransferCFT/componentshortname >}} at regular negotiated intervals to prevent the temporization from expiring.

-   &ids = Session call id
-   &call = interval for the DMZ control call

```

 

```
V23 format
V24 format
Error
<span id="CFTH66E"></span>CFTH66E Incoming calls (&count) rejected, ERROR=&error (&info1|&info2), PROTOCOL=&protocol
CFTH66E Incoming calls (&count) rejected, ERROR=&error (&info1|&info2), PROTOCOL=&protocol
Explanation
Incoming calls are rejected:

-   &count = Number of rejected calls
-   &error = Error message
-   &info1 = Additional information
-   &info2 = Additional information
-   &protocol = Protocol type when available

```
