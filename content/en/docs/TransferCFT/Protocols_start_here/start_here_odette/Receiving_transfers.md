{
    "title": "Receiving OFTP transfers",
    "linkTitle": "Receiving transfers",
    "weight": "200"
}After you configure the OFTP (ODETTE) environment, as described in [Configuring
OFTP](configuring_odette), you must define the transfer environment in the RECV
object to receive a request.

This topic describes the steps
that enable you to receive a request. The [previous
topic](submitting_a_transfer_request) describes the procedure that enables you to submit a transfer
request. This topic is broken down into the following sections:

-   [About
    CFTRECV](#About_CFTRECV)
-   [Receiving
    a file in text format](#Receiving_a_file_in_text_format)
-   [Defining
    the receiving file format](#Defining_the_receiving_file_format)
-   [RECV
    command](#RECV_command)

## <span id="About_CFTRECV"></span>About CFTRECV

Regardless of the protocol format conveyed, data code information is
not sent. In reception mode, the Transfer CFT monitor considers that the
data code received from the network, the NCODE parameter, is ASCII.

The translating rules indicated for the CFTRECV [FCODE](../../../CFTUTIL/Parameter_index/fcode.htm)
parameter are applied taking a network code equal to ASCII.

Translation is carried out during transmission, if you set:

-   FCODE = EBCDIC
-   FCODE = ASCII
    and an external ASCII/ASCII translation table is defined

There is no translation if FCODE = BINARY.

If you do not set the FCODE parameter, the value of the local data code
determined dynamically for each reception takes the value of the native
code of the receiving system, independently of the receiving file type
(FTYPE).

### <span id="Receiving_a_file_in_text_format"></span>Receiving a file in text format

You should have previously set the CFTPART [SYST](../../../CFTUTIL/Parameter_index/syst.htm)
parameter to UNIX.

The receiving Transfer CFT acts as if a UNIX partner is sending
the file and sets the:

-   NCODE to ASCII
-   NRECFM to V
-   NLRECL to 2048

Each record is delimited by the characters &lt;CR> and &lt;LF>.
The size of the records is 2048 bytes, &lt;CR> and &lt;LF> not included.
If a record is longer than 2048 , the monitor interrupts the transfer
with the diagnostic codes: DIAGI=230,
DIAGP=LDT\_TXT.

If the receiver file type is not defined, Transfer CFT assigns the value
contained in the table below, according to the receiving system.

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>Receiving system</th>
         <th>FTYPE default</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td data-valign="top" width="67.638%">            <p>z/OS (MVS)</p>         </td>
         <td data-valign="top" width="32.362%">            <p>‘ ’ </p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="67.638%">            <p>IBM i (OS400)</p>         </td>
         <td data-valign="top" width="32.362%">            <p>E </p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="67.638%">            <p>UNIX </p>         </td>
         <td data-valign="top" width="32.362%">            <p>T </p>         </td>
      </tr>
   </tbody>
</table>

If the FRECFM and FLRECL parameters are not defined or imposed , data
are saved, by default, in a file of variable format , with a maximum record
length of 2048 bytes.

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">To avoid protocol-related
problems, a Transfer CFT user subscribing to Atlas400 must request the
&lt;CR&gt;/&lt;LF&gt; insert option from their Transpac sales branch.
When the &lt;CR&gt;/&lt;LF&gt; delimiter is missing, a delimiter must
be inserted every 2046 characters by the OFTP gateway.         </td>
      </tr>
   </tbody>
</table>

### <span id="Defining_the_receiving_file_format"></span>Defining the receiving file format

The Transfer CFT monitor responds as if the file type set in the sending
command was set to space, where the NTYPE is assumed to be blank. It sets
the:

-   NCODE to ASCII
-   NRECFM to the value
    of the format received (U, F or V)
-   NLRECL to the:
-   value received
    if NRECMF = F or V
-   negotiated
    value of the network message size &lt;Rusize> if NRECFM = U

You must specify the FCODE and FTYPE.

If the FRECFM and FLRECL parameters are not defined or imposed by type
(FTYPE), data are saved, by default, in a file format defined by NRECFM
(default value of FRECFM), with a maximum record length equal to NLRECL
(default value FLRECL)

For a file in undefined format, if the FLRECL parameter is set to:

-   a value greater
    than the negotiated value of the network message size &lt;Rusize>,
    the maximum effective length of the records managed by the monitor equals
    the value &lt;Rusize>
-   the &lt;Rusize>
    or less, the maximum effective length of the records will be the one specified

In all cases, the integrity of the undefined format file is kept: no
truncating nor padding.

### <span id="RECV_command"></span>RECV command

The OFTP (Odette) protocol does not provide for reception requests.
It does, however, provide for two partners to be able to exchange the
right to send a file. This right first belongs to the initiator of the
connection.

If a RECV command can be initiated, it is reflected in the framework
of the Odette protocol, by the exchange of a CHANGE DIRECTION (CD) protocol
message, and makes it possible to initiate the transfers pending at the
partner end: the local monitor (sender) sends the partner the right to
send and consequently becomes a potential receiver.

When the sending partner is a Transfer CFT, transmissions must
first have been prepared by on hold commands (SEND [STATE](../../../CFTUTIL/Parameter_index/state.htm)
= HOLD).

The only command relevant for reception is RECV IDF=\*. This command
generates a generic catalog entry in the "K" state with a diagnostic
DIAGP="RECV ALL". All the files waiting to be transferred (sent)
to Transfer CFT from the partner end are released one after another. Once
each file has been received, the end-of-transfer procedure defined in
the [EXECRF](../../../CFTUTIL/Parameter_index/execrf.htm) parameter
([CFTPARM](../../admin_intro/admin_config_commands/cftparm_general_parameters))
is executed.

Once all the pending files have been received, Transfer CFT performs
the following tasks:

-   The error procedure
    defined in the [EXECRE](../../../CFTUTIL/Parameter_index/execre.htm)
    parameter is executed
-   A new catalog entry
    is created, indicating that there are no more files to be received. This
    entry is set to the H state with a diagnostic DIAGP=NO\_FILE.

For each file being transferred, received, the value of the file identifier,
the IDF, is imposed by the sending partner and will be the value of the
IDF parameter of the SEND command, or its network correspondence, the
NIDF.

Note:

-   the FILE parameter
    is ignored and systematically set to the value ALL
-   the implicit send
    is not relevant
-   if there is an
    error in a transfer before the data transfer phase (H state and diagi
    other than 0), the transfer stops  
    For the following connection, Transfer CFT activates the first waiting
    transfer, (H state and diagi other than 0), then tries to reactivate the
    entry with an error

<!-- -->

-   if there is an
    error during the data transfer phase and retrying is forbidden, the transfer
    (requester mode) is restarted from the beginning of the file

Example of receiving all the pending
files

<img src="/Images/TransferCFT/Image1689.gif" width="551" height="579" alt="Site A receives all pending files from Site B" />
