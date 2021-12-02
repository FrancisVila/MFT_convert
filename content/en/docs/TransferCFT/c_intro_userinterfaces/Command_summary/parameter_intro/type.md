{
    "title": "type",
    "linkTitle": "type",
    "weight": "3630"
}<span id="type"></span>

### type

#### ABOUT

\[ TYPE
= {
| HOST | CFT } \]

Displays
the Transfer CFT product, host, and key information.

<span id="ACT__INACT"></span>

#### ACT

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

<span id="type_CFTCOM"></span>

#### CFTCOM

TYPE = { FILE
| TCPIP}

Type of {{< TransferCFT/componentshortname  >}} communication medium.

This parameter can take the following values:

-   FILE:
    communication is accomplished through a file
-   TCPIP:
    communication is performed through the synchronous communication medium

<span id="type_CFTNET"></span>

#### CFTNET

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

<span id="type_CFTEXIT"></span>

#### CFTEXIT

\[TYPE = {FILE
| ACCESS | EXEC | BOT }\] 

The type of exit program, as follows:

-   FILE (default value): Data is recorded
    in the monitor files
-   ACCESS: To use a directory type EXIT
-   EXEC: To use an end-of-transfer type EXIT
-   BOT: To use a beginning-of-transfer type EXIT

<span id="type_CFTACCNT"></span>

#### CFTACCNT

\[TYPE = {FILE
| SYST }\] 

This defines the accounting type. CFTACCNT TYPE parameters are:

-   FILE (default value): Data is recorded
    in the {{< TransferCFT/componentlongname >}} files defined in the fname
    and afname fields.
-   SYST: Data is recorded in the files
    of the operating system accounting utility. Available
    only on z/OS (MVS).

<span id="type_CFTPROT"></span>

#### CFTPROT

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

<span id="Type_table1"></span>

#### Type table

<span id="type_CONFIG"></span>

#### CONFIG

TYPE = {CAT | COM | INPUT | OUTPUT
| PARM | PART}

Defines the medium concerned.

<span id="type_SWITCH"></span>

#### SWITCH

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
table below](#Type_table) }\]

Defines the parameters to extract.

<span id="Type_table"></span>

#### Type table

<span id="type_LISTPARM"></span>

#### LISTPARM

TYPE = {ACCNT |
ALL | AUTH | CAT | COM | ETB | IDF | LOG | NET |PARM | PROT | RECV | SEND
| XLATE }

Defines the type of parameters to
list from the {{< TransferCFT/componentshortname  >}} parameter file.

TYPE can take the predefined values indicated in the Type table below.

#### Type table

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
