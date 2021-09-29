{
    "title": "type",
    "linkTitle": "type",
    "weight": "3660"
}### <span id="type"></span>type

#### ABOUT

\[ TYPE
= { ALL
| HOST | CFT } \]

Displays
the Transfer CFT product, host, and key information.

#### <span id="ACT__INACT"></span>ACT

\[TYPE = PART | TRK | CRON | FOLDER 
\]

Type of object to be deactivated.

-   PART
    = Partner
-   TRK
    = Select to restart Sentinel notification
-   CRON
    = Enables the cronjob CRON=ID

#### INACT

\[TYPE = PART | TRK | CRON | FOLDER
\]

Type of object to be deactivated.

-   PART
    = Partner
-   TRK
    = Select to stop dynamic Sentinel notification. All further
    messages are lost.
-   CRON
    = Disables the cronjob CRON=ID

#### <span id="type_CFTCOM"></span>CFTCOM

TYPE = { FILE
| TCPIP}

Type of Transfer CFT communication medium.

This parameter can take the following values:

-   FILE:
    communication is accomplished through a file
-   TCPIP:
    communication is performed through the synchronous communication medium

#### <span id="type_CFTNET"></span>CFTNET

\[TYPE = { TCP } \] 

Defines the type of network resource. This parameter can take the following
values, according to the system:

-   TCP: TCP/IP
    network access resource

#### CFTIDF

TYPE = { RECV | SEND}

The transfer direction for which this correspondence is valid. Select
either:

-   SEND:
    for send transfers
-   RECV:
    for receive transfer

#### <span id="type_CFTEXIT"></span>CFTEXIT

\[TYPE = {FILE
| ACCESS | EXEC | BOT }\] 

The type of exit program, as follows:

-   FILE (default value): Data is recorded
    in the monitor files
-   ACCESS: To use a directory type EXIT
-   EXEC: To use an end-of-transfer type EXIT
-   BOT: To use a beginning-of-transfer type EXIT

#### <span id="type_CFTACCNT"></span>CFTACCNT

\[TYPE = {FILE
| SYST }\] 

This defines the accounting type. CFTACCNT TYPE parameters are:

-   FILE (default value): Data is recorded
    in the Transfer CFT files defined in the fname
    and afname fields.
-   SYST: Data is recorded in the files
    of the operating system accounting utility. Available
    only on z/OS (MVS).

#### <span id="type_CFTPROT"></span>CFTPROT

\[TYPE = {PeSIT | ODETTE  }\]

Type
of transfer protocol.

-   PeSIT:
    PeSIT protocol
-   ODETTE:
    OFTP (ODETTE) protocol
-   SFTP: SFTP protocol

#### LISTPART

TYPE ={ALL | DEST | PART | TCP}

#### <span id="Type_table1"></span>Type table

<table data-cellspacing="0" width="90%">
<tbody>
<tr class="odd">
<td data-bgcolor="#C0C0C0" data-valign="top"><p>Value </p></td>
<td data-bgcolor="#C0C0C0" data-valign="top" width="85%"><p>Meaning </p></td>
</tr>
<tr class="even">
<td data-valign="top"><p>ALL </p></td>
<td data-valign="top" width="85%"><p>Used to query the general and network characteristics of
partners<br />
Parameters of the PARTNER file</p></td>
</tr>
<tr class="odd">
<td data-valign="top"><p>DEST </p></td>
<td data-valign="top" width="85%"><p>Used to query the parameters configured in the CFTDEST
command: concern the broadcasting lists </p></td>
</tr>
<tr class="even">
<td data-valign="top"><p>PART </p></td>
<td data-valign="top" width="85%"><p>Used to query the parameters configured in the CFTPART
command: description of the general data relative to partners </p></td>
</tr>
<tr class="odd">
<td data-valign="top"><p>TCP</p></td>
<td data-valign="top" width="85%"><p>Used to query the parameters configured in the CFTTCP command:
TCP/IP network parameters associated with each partner supporting TCP/IP </p></td>
</tr>
</tbody>
</table>

#### <span id="type_CONFIG"></span>CONFIG

TYPE = {CAT | COM | INPUT | OUTPUT
| PARM | PART}

Defines the medium concerned.

<table data-cellspacing="0" width="90%">
<tbody>
<tr class="odd">
<td data-bgcolor="#C0C0C0" data-valign="top" width="14%"><p>Value </p></td>
<td data-bgcolor="#C0C0C0" data-valign="top" width="62.746%"><p>Medium concerned </p></td>
</tr>
<tr class="even">
<td data-valign="top" width="14%"><p>CAT </p></td>
<td data-valign="top" width="62.746%"><p>Catalog file </p></td>
</tr>
<tr class="odd">
<td data-valign="top" width="14%"><p>COM </p></td>
<td data-valign="top" width="62.746%"><p>Communication medium </p></td>
</tr>
<tr class="even">
<td data-valign="top" width="14%"><p>INPUT </p></td>
<td data-valign="top" width="62.746%"><p>Command input file </p></td>
</tr>
<tr class="odd">
<td data-valign="top" width="14%"><p>OUTPUT </p></td>
<td data-valign="top" width="62.746%"><p>Report output file </p></td>
</tr>
<tr class="even">
<td data-valign="top" width="14%"><p>PARM </p></td>
<td data-valign="top" width="62.746%"><p>Parameter file </p></td>
</tr>
<tr class="odd">
<td data-valign="top" width="14%"><p>PART </p></td>
<td data-valign="top" width="62.746%"><p>Partner file </p></td>
</tr>
</tbody>
</table>

#### <span id="type_SWITCH"></span>SWITCH

\[TYPE = {LOG | ACCNT}\]

Defines the switch action for CFTLOG or CFTACCNT. File types are:

-   LOG:
    The SWITCH command stops message writing on the current log file, switches
    to the alternate log file, and then executes the procedure specified in
    the EXEC parameter of the CFTLOG
    object.

<!-- -->

-   ACCNT:
    The SWITCH command stops statistics from being written on the current
    statistical file, switches the writing to the alternate statistical file,
    and then executes the procedure specified in the EXEC
    parameter of the [CFTACCNT](../../../web_copilot_ui/conf_intro/cftaccnt) object.

#### CFTEXT

\[TYPE = {[see Type
table below](#type_table) }\]

Defines the parameters to extract.

#### <span id="Type_table"></span>Type table

<table data-cellspacing="0" width="90%">
<tbody>
<tr class="odd">
<td data-bgcolor="#C0C0C0" data-valign="top" width="15%"><p>Value </p></td>
<td data-bgcolor="#C0C0C0" data-valign="top" width="50%"><p>Meaning </p></td>
<td data-bgcolor="#C0C0C0" data-valign="top" width="35%"><p>Command</p></td>
</tr>
<tr class="even">
<td data-valign="top" width="15%"><p>ALL </p></td>
<td data-valign="top" width="50%"><p>All the parameter types of the CFTPARM and CFTPART files </p></td>
<td data-valign="top" width="35%"><p> </p></td>
</tr>
<tr class="odd">
<td data-valign="top" width="15%"><p>ACCNT </p></td>
<td data-valign="top" width="50%"><p>Description of the statistical files </p></td>
<td data-valign="top" width="35%"><p>CFTACCNT </p></td>
</tr>
<tr class="even">
<td data-valign="top" width="15%"><p>AUTH </p></td>
<td data-valign="top" width="50%"><p>List of authorized files </p></td>
<td data-valign="top" width="35%"><p>CFTAUTH </p></td>
</tr>
<tr class="odd">
<td data-valign="top" width="15%"><p>CAT </p></td>
<td data-valign="top" width="50%"><p>Catalog definition </p></td>
<td data-valign="top" width="35%"><p>CFTCAT </p></td>
</tr>
<tr class="even">
<td data-valign="top" width="15%"><p>COM </p></td>
<td data-valign="top" width="50%"><p>Description of <span>Transfer CFT</span> communication methods
 </p></td>
<td data-valign="top" width="35%"><p>CFTCOM </p></td>
</tr>
<tr class="odd">
<td data-valign="top" width="15%"><p>IDF </p></td>
<td data-valign="top" width="50%"><p>File "network" identifier </p></td>
<td data-valign="top" width="35%"><p>CFTIDF </p></td>
</tr>
<tr class="even">
<td data-valign="top" width="15%"><p>LOG </p></td>
<td data-valign="top" width="50%"><p>Log file description </p></td>
<td data-valign="top" width="35%"><p>CFTLOG </p></td>
</tr>
<tr class="odd">
<td data-valign="top" width="15%"><p>NET </p></td>
<td data-valign="top" width="50%"><p>Network description </p></td>
<td data-valign="top" width="35%"><p>CFTNET </p></td>
</tr>
<tr class="even">
<td data-valign="top" width="15%"><p>PARM </p></td>
<td data-valign="top" width="50%"><p>General parameters </p></td>
<td data-valign="top" width="35%"><p>CFTPARM </p></td>
</tr>
<tr class="odd">
<td data-valign="top" width="15%"><p>PART </p></td>
<td data-valign="top" width="50%"><p>Partner definition  </p></td>
<td data-valign="top" width="35%"><p>CFTPART and <span>Transfer CFT</span> network </p></td>
</tr>
<tr class="even">
<td data-valign="top" width="15%"><p>PROT </p></td>
<td data-valign="top" width="50%"><p>Protocol definition </p></td>
<td data-valign="top" width="35%"><p>CFTPROT </p></td>
</tr>
<tr class="odd">
<td data-valign="top" width="15%"><p>RECV </p></td>
<td data-valign="top" width="50%"><p>Description of the files to be received </p></td>
<td data-valign="top" width="35%"><p>CFTRECV </p></td>
</tr>
<tr class="even">
<td data-valign="top" width="15%"><p>SEND </p></td>
<td data-valign="top" width="50%"><p>Description of the files to be sent </p></td>
<td data-valign="top" width="35%"><p>CFTSEND </p></td>
</tr>
<tr class="odd">
<td data-valign="top" width="15%"><p>XLATE </p></td>
<td data-valign="top" width="50%"><p>Translation table definition </p></td>
<td data-valign="top" width="35%"><p>CFTXLATE </p></td>
</tr>
<tr class="even">
<td data-valign="top" width="15%"><p>TCP </p></td>
<td data-valign="top" width="50%"><p>TCP/IP partner definition </p></td>
<td data-valign="top" width="35%"><p>CFTTCP </p></td>
</tr>
<tr class="odd">
<td data-valign="top" width="15%">UCONF</td>
<td data-valign="top" width="50%">Unified configuration</td>
<td data-valign="top" width="35%">CFTEXT</td>
</tr>
</tbody>
</table>

#### <span id="type_LISTPARM"></span>LISTPARM

TYPE = {ACCNT |
ALL | AUTH | CAT | COM | ETB | IDF | LOG | NET |PARM | PROT | RECV | SEND
| XLATE }

Defines the type of parameters to
list from the Transfer CFT parameter file.

TYPE can take the predefined values indicated in the Type table below.

#### Type table

<table data-cellspacing="0" width="90%">
<tbody>
<tr class="odd">
<td data-bgcolor="#C0C0C0" data-valign="top" width="19%"><p>Value </p></td>
<td data-bgcolor="#C0C0C0" data-valign="top" width="81%"><p>Definition </p></td>
</tr>
<tr class="even">
<td data-valign="top" width="19%"><p>ACCNT </p></td>
<td data-valign="top" width="81%"><p>Used to query statistical file parameters<br />
These parameters are submitted when CFTACCNT commands are entered </p></td>
</tr>
<tr class="odd">
<td data-valign="top" width="19%"><p>ALL </p></td>
<td data-valign="top" width="81%"><p>Used to query all the parameters indicated in the PARAMETER
file </p></td>
</tr>
<tr class="even">
<td data-valign="top" width="19%"><p>AUTH </p></td>
<td data-valign="top" width="81%"><p>Used to query file authorization lists<br />
These lists are customized by the CFTAUTH commands </p></td>
</tr>
<tr class="odd">
<td data-valign="top" width="19%"><p>CAT </p></td>
<td data-valign="top" width="81%"><p>Used to query catalog parameters<br />
These parameters are submitted when CFTCAT commands are entered </p></td>
</tr>
<tr class="even">
<td data-valign="top" width="19%"><p>COM </p></td>
<td data-valign="top" width="81%"><p>Used to query communication media parameters<br />
These parameters are submitted when CFTCOM commands are entered </p></td>
</tr>
<tr class="odd">
<td data-valign="top" width="19%"><p>IDF </p></td>
<td data-valign="top" width="81%"><p>Used to query file "network" identifiers<br />
Identifiers are customized by the CFTIDF commands </p></td>
</tr>
<tr class="even">
<td data-valign="top" width="19%"><p>LOG </p></td>
<td data-valign="top" width="81%"><p>Used to query log file parameters<br />
These parameters are submitted when CFTLOG commands are entered </p></td>
</tr>
<tr class="odd">
<td data-valign="top" width="19%"><p>NET </p></td>
<td data-valign="top" width="81%"><p>Used to query network characteristic parameters<br />
These parameters are submitted when CFTNET commands are entered and differ
according to the type of network configured </p></td>
</tr>
<tr class="even">
<td data-valign="top" width="19%"><p>PARM </p></td>
<td data-valign="top" width="81%"><p>Used to query general parameters<br />
These parameters are submitted when CFTPARM commands are entered </p></td>
</tr>
<tr class="odd">
<td data-valign="top" width="19%"><p>PROT </p></td>
<td data-valign="top" width="81%"><p>Used to query protocol parameters<br />
These parameters are submitted when CFTPROT commands are entered and differ
according to the protocol configured </p></td>
</tr>
<tr class="even">
<td data-valign="top" width="19%"><p>RECV </p></td>
<td data-valign="top" width="81%"><p>Used to query the parameters of the files to be received<br />
These parameters are submitted when CFTRECV commands are entered </p></td>
</tr>
<tr class="odd">
<td data-valign="top" width="19%"><p>SEND </p></td>
<td data-valign="top" width="81%"><p>Used to query the parameters of the files to be sent<br />
These parameters are submitted when CFTSEND commands are entered </p></td>
</tr>
<tr class="even">
<td data-valign="top" width="19%"><p>XLATE </p></td>
<td data-valign="top" width="81%"><p>Used to query translation tables<br />
Translation tables are customized by the CFTXLATE object</p></td>
</tr>
<tr class="odd">
<td data-valign="top" width="19%"><p>CFTFILE</p></td>
<td data-valign="top" width="81%"><p>Used to create, empty, or delete <span>Transfer CFT</span> files</p></td>
</tr>
<tr class="even">
<td data-valign="top" width="19%"><p>LISTCAT</p></td>
<td data-valign="top" width="81%"><p>Used to query the information associated with the selected
transfers, recorded in the <span>Transfer CFT</span> catalog</p></td>
</tr>
<tr class="odd">
<td data-valign="top" width="19%"><p>DISPLAY</p></td>
<td data-valign="top" width="81%"><p>Used to query the information as with the LISTCAT command.
It uses an external XML file that lists and describes customized models.
These models are used to format the output</p></td>
</tr>
<tr class="even">
<td data-valign="top" width="19%"><p>ABOUT</p></td>
<td data-valign="top" width="81%"><p>Used to display the <span>Transfer CFT</span> computer characteristics</p></td>
</tr>
</tbody>
</table>

#### RECONFIG

TYPE = { CRON | UCONF | CAT | FOLDER | PARMCACHE | AM}

-   CAT: Resize the catalog while the Transfer CFT is running (hot catalog resizing)
-   CRON: Reload the CFTCRON objects
-   FOLDER: Reload the CFTFOLDER objects
-   UCONF: Reload the dynamic UCONF parameters
-   PARMCACHE: Clear the parameter cache
-   AM: Reload roles and privileges

#### CFTUIPREF

TYPE = string

Enter a name for the object.

 

[Return to Command index](../../)
