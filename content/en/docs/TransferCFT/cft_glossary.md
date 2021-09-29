{
    "title": "Glossary",
    "linkTitle": "Glossary",
    "weight": "210"
}# <span id="CFT_Glossary"></span>Glossary



##### A



#### <span id="Acceptance_by_CFT_"></span>Acceptance by <span>Transfer CFT</span>:



Process whereby a transfer request is taken into account by Transfer

CFT when it is recorded in the catalog.



#### <span id="Accounting"></span>Accounting file:



File containing the descriptive and quantitative properties of all successfully

completed transfers (defined via CFTACCNT, file created via CFTFILE TYPE=ACCNT).



#### <span id="Acknowledgement_anticipation_window_"></span>Acknowledgement anticipation window:



Parameter determining the number of synchronization points that the

file sender can set without waiting for an explicit response from the

receiver for each point.



This mechanism is used by the PeSIT protocols.



#### <span id="Acknowledgement__EERP__"></span>Acknowledgement (EERP):



See EERP (End to End Response) acknowledgement.



#### <span id="Authorized_identifiers_"></span>Authorized identifiers:



List of model file identifiers (IDFs) governed by the same transfer

authorizations or denials (user-defined in the CFTAUTH command).



#### <span id="Availability_for_the_monitor_"></span>Availability for <span>Transfer CFT</span>:



Process whereby a request is made available to the monitor when it is

processed in the communication medium.



#### <span id="Availability_for_the_partner_"></span>Availability for the partner:



Process whereby a file is made available to a partner so that it can

be sent on reception of the request from the partner. The file can be

made available implicitly (see Implicit send) or explicitly, in which

case the transfer is put on hold in the catalog (SEND STATE=HOLD).



##### B



#### <span id="Broadcast"></span>Broadcast:



Sending of a file or group of files to a set of partners defined in

a list via a single request (partner list defined in CFTDEST).



#### <span id="Broadcast_list_"></span>Broadcast list:



List defined in parameter or file form to send a file or group of files

to one or more partners via a single request (user-defined in the CFTDEST

command).



##### C



#### <span id="Card__parameter__"></span>Card (parameter):



See [Command](#Command__parameter__) (parameter).



#### <span id="Catalog_"></span>Catalog:



File containing the control and monitoring data associated with transfers

(usage mode defined via CFTCAT, file created via CFTFILE TYPE=CAT).



#### <span id="Catalog"></span>Catalog entry:



Record corresponding to a transfer in the catalog file.



#### <span id="Catalog_identifier_"></span>Catalog identifier:



See [IDTU](#IDTU__catalog_identifier__) (catalog identifier).



#### <span id="Catalog_sharing_"></span>Catalog sharing:



Option available in some environments, whereby the user can monitor

several instances of <span>Transfer CFT</span> via a single catalog file.



#### <span id="CD__Change_Direction__"></span>CD (Change Direction):



Odette protocol service whereby a token is exchanged between partners.

Only the partner in possession of the token can send a file.



#### <span id="CFT_API_"></span>CFT API:



Programming interface used to integrate <span>Transfer CFT</span> into applications

developed in either C or COBOL.



#### <span id="CFTACCNT"></span>CFTACCNT:



Command used to define the accounting data logging mode for successfully

completed transfers.



#### <span id="CFTAPI"></span>CFTAPI:



See [CFT API](#CFT_API_).



#### <span id="CFTAUTH"></span>CFTAUTH:



Command used to define a list of file identifiers governed by the same

transfer authorizations or denials.



This list can be stored in a file or defined explicitly via the IDF

parameter in the command.



#### <span id="CFTCAT"></span>CFTCAT:



Command used to set transfer catalog management parameters.



#### <span id="CFTCOM"></span>CFTCOM:



Command used to set parameters controlling communications between user

programs and the <span>Transfer CFT</span>. See also [Communication

medium](#Communication_medium_).



#### <span id="CFTDEST"></span>CFTDEST:



Command used to define a list of partners for broadcast/collect operations.

This list can be stored in a file or defined explicitly via the PART parameter

in the command.



#### <span id="CFTFILE"></span>CFTFILE:



Command used to create or delete <span>Transfer CFT</span> files (parameter, partner,

catalog, accounting, log and communication files).



#### <span id="CFTLOG"></span>CFTLOG:



Command used to set the log file management parameters for the monitor.



#### <span id="CFTMAIN"></span>CFTMAIN:



Main <span>Transfer CFT</span> task used to schedule transfers. It controls

transfer execution and authorizations.



#### <span id="CFTNET"></span>CFTNET:



Command used to define the properties of a network resource.



#### <span id="CFTPROT"></span>CFTPROT:



Command used to define a file transfer protocol and the way in which

it is implemented.



#### <span id="CFTRECV"></span>CFTRECV:



Command used to define the properties of a given type of transfer (storage

of the data received and execution of receive operations).



#### <span id="CFTSEND"></span>CFTSEND:



Command used to define the properties of a given type of transfer (access

to the data to be sent and execution of send operations).



#### <span id="CFTTFIL"></span>CFTTFIL:



File access tasks that can be activated concurrently. Depending on the

configuration, a CFTTFIL task can be permanent or will stop on completion

of the transfers for which it was created.



#### <span id="CFTTPRO"></span>CFTTPRO:



Protocol task giving access to the resources defined via CFTNET commands

and the application-level protocols declared in CFTPROT commands.



#### <span id="CFTUTIL"></span>CFTUTIL:



Batch or line mode tool giving access to all <span>Transfer CFT</span> functions

and parameters.



#### <span id="CFTXLATE"></span>CFTXLATE:



Command used to define user conversion tables. Files can be converted

in both the send and receive modes, irrespective of the protocol used.



#### <span id="Ciphering"></span>Ciphering:



Coding or encryption technique whereby information is protected against

illicit read operations.



The information can only be read or processed by entities in possession

of the ciphering "key". See also [Cryptography](#Cryptography).



#### <span id="Closed_mode_"></span>Closed mode:



Mode whereby only the receiver can determine the physical name (location)

of the received file.



#### <span id="Collection"></span>Collection:



Reception of a file or group of files from several partners via a single

request (list of partners defined in CFTDEST).



#### <span id="Command__parameter__"></span>Command (parameter):



Command used to declare a monitor and set up the working environment.



#### <span id="Commands"></span>Commands:



Instructions used in <span>Transfer CFT</span> to configure the monitor and working

environment and to control the monitor and associated transfers.



#### <span id="Compression"></span>Compression



The types of compression are:



-   <span>01</span>:

    compression of a string of characters (compression of blank characters)

-   <span>02</span>:

    horizontal compression (repetitive characters are deleted in the record)

-   <span>04</span>:

    compression of characters (each alphanumeric character is compressed)

-   <span>08</span>:

    vertical compression (only the characters which are different from the

    previous record are transferred)



#### <span id="Communication_medium_"></span>Communication medium:



File used to transmit the requests submitted to the monitor

(defined via CFTCOM, file created via CFTFILE TYPE=COM).



#### <span id="Confidentiality"></span>Confidentiality:



Property resulting from ciphering data so that it cannot be read by

an unauthorized third party on the network.



#### <span id="Conversion"></span>Conversion:



Translation of data, character by character, from one data coding system

to another (EBCDIC to ASCII for example). The conversion can take place

"ON LINE" during transmission, or "OFF LINE" (optionally

defined in the CFTXLATE, SEND/RECV, CFTSEND/CFTRECV and CFTPART commands).



#### <span id="Conversion_table_"></span>Conversion table:



Table defining the correspondence between two coding systems and used

during conversion. The conversion table, defined for each transfer direction

and conversion mode, can be internal to <span>Transfer CFT</span> or created by the

user (CFTXLATE command).



#### <span id="Copilot"></span>Copilot:



Graphic user interface for <span>Transfer CFT</span>.



#### <span id="Credit"></span>Credit:



For the Odette protocol, maximum number of data packets that the sender

can transmit before the server must acknowledge reception by assigning

a new "credit".  



<span>Transfer CFT</span> simulates a synchronization point for each credit message

sent or received.



#### <span id="Cryptogram"></span>Cryptogram:



Data resulting from a ciphering operation.



#### <span id="Cryptography"></span>Cryptography:



Discipline comprising data transformation principles and mechanisms

with the aim of masking the meaning of data.



There are two main systems:



-   Shared-key or symmetric

    systems for which the ciphering and deciphering keys are the same; see

    [DES](#DES__IBM_Data_Encryption_Standard__) (IBM Data Encryption

     Standard)







-   <span>D</span>:

    The transfer is available (at <span>D</span>isposal)

    and will be triggered automatically as soon as the <span>Transfer CFT</span> resources

    and partner access authorizations allow it.

-   <span>H</span>:

    The transfer is pending (on <span>H</span>old)

    on the initiative of the transfer requester, an operator (HALT command)

    or the monitor subsequent to an incident. The transfer can be resumed

    by the operator or the remote partner.

-   <span>K</span>:

    The transfer is pending (<span>K</span>ept)

    on the initiative of the transfer requester, an operator (KEEP command)

    or the monitor subsequent to an incident. The transfer can only be resumed

    by the operator.

-   <span>T</span>:

    The transfer has successfully <span>T</span>erminated.

-   <span>X</span>:

    All end of transfer operations have been successfully e<span>X</span>ecuted

    and the monitor has been notified via the END command.



##### V



#### <span id="VC_"></span>VC:



Virtual circuit assigned a connection identifier and maintained throughout

the transfer (pipe, window mechanism).



#### <span id="Vertical_compression_"></span>Vertical compression:



Comparison between the current record and the previous record with the

aim of transferring only those characters that are different.



##### W



#### <span id="Writing_or_write_mode_transfer_"></span>Writing or write-mode transfer:



For the PeSIT protocol, sending of a file from the requester to the

server.

