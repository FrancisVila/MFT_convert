{
    "title": "Transfer CFT command guide and syntax ",
    "linkTitle": "Command guide",
    "weight": "150"
}This topic provides a useful list of Transfer CFT commands,
syntax, and parameters. For a more detailed description of the Transfer
CFT commands, refer to the link displayed below each command
syntax.

The Transfer CFT commands are presented in alphabetical order in this
summary. Each
command is presented with possible parameters and default values.

See also, [Syntax
conventions and symbolic variables.](#Syntax_conventions)

#### <span id="ABOUT"></span>ABOUT: Displays product/host information

Syntax

\[ [COMMENT](CFTUTIL/Parameter_index/comment.htm)
= string \]

\[ [TYPE](CFTUTIL/Parameter_index/type.htm)
= { ALL
| HOST | CFT } \]

\[ [KEY](CFTUTIL/Parameter_index/key.htm) = { <u>FIRST</u> | ALL } \]

[ABOUT details](CFTUTIL/Admin/about_command.htm)

#### <span id="ACT"></span>ACT: Reactivates a partner

Syntax

ID = identifier

\[ [TYPE](CFTUTIL/Parameter_index/type.htm)
= { PART
| TRK | CRON | FOLDER } \]

\[ [MODE](CFTUTIL/Parameter_index/mode.htm)
= { BOTH
| REQUESTER|
SERVER } \]

[ACT details](Transfers/Partners/Reactivate_an_object_CL.htm)

#### <span id="CFTACCNT"></span>CFTACCNT: Defines transfer accounting records

Syntax

CFTACCNT TYPE = FILE

[TYPE](CFTUTIL/Parameter_index/type.htm)
= FILE

[FNAME](CFTUTIL/Parameter_index/fname.htm)
= filename

[ID](CFTUTIL/Parameter_index/id.htm)
= identifier

\[ [AFNAME](CFTUTIL/Parameter_index/afname.htm)
= filename \]

\[ [COMMENT](CFTUTIL/Parameter_index/comment.htm)
= string \]

\[ [EXEC](CFTUTIL/Parameter_index/exec.htm)
= filename \]

\[ [LANGUAGE](CFTUTIL/Parameter_index/language.htm)
= { COBOL
| C } \]

\[ [MAXREC](CFTUTIL/Parameter_index/maxrec.htm)
= { 0
| n } \]

\[ [MODE](CFTUTIL/Parameter_index/mode.htm)
= { REPLACE
| CREATE | DELETE } \]

\[ [SWITCH](CFTUTIL/Parameter_index/switch.htm)
= { 00000000
| time } \]

\[ [FORMAT](CFTUTIL/Parameter_index/format.htm)
= { V23
| 23 | V24 | 24} \]

 

CFTACCNT TYPE = SYST

[TYPE](CFTUTIL/Parameter_index/type.htm)
= SYST

[ACCID](CFTUTIL/Parameter_index/accid.htm)
= n

[ID](CFTUTIL/Parameter_index/id.htm)
= identifier

\[ [COMMENT](CFTUTIL/Parameter_index/comment.htm)
= string \]

\[ [FORMAT](CFTUTIL/Parameter_index/format.htm)
= { V23
| 23 | V24 | 24} \]

\[ [LANGUAGE](CFTUTIL/Parameter_index/language.htm)
= { COBOL
| C } \]

\[ [MODE](CFTUTIL/Parameter_index/mode.htm)
= { REPLACE
| CREATE | DELETE } \]

[CFTACCNT details](CFTUTIL/Conf/CFTACCNT.htm)

[Transfer
accounting records](GUI/Concepts/CFTACCNT_concepts.htm)

#### <span id="CFTAPPL"></span>CFTAPPL: Defines a transfer owner

Syntax

CFTAPPL
MODE = REPLACE

[ID](CFTUTIL/Parameter_index/id.htm)
= identifier

[USERID](CFTUTIL/Parameter_index/userid.htm)
= string

\[ [COMMENT](CFTUTIL/Parameter_index/comment.htm)
= string \]

\[ [GROUPID](CFTUTIL/Parameter_index/groupid.htm)
= string \]

\[ [MODE](CFTUTIL/Parameter_index/mode.htm)
= { REPLACE
| CREATE | DELETE } \]

CFTAPPL MODE = DELETE

[ID](CFTUTIL/Parameter_index/id.htm)
= identifier

[USERID](CFTUTIL/Parameter_index/userid.htm)
= string

[DIRECT](CFTUTIL/Parameter_index/direct.htm)
= { BOTH
|  SEND
| RECV }

\[ [COMMENT](CFTUTIL/Parameter_index/comment.htm)
= string \]

\[ [GROUPID](CFTUTIL/Parameter_index/groupid.htm)
= string \]

\[ [MODE](CFTUTIL/Parameter_index/mode.htm)
= { REPLACE
| CREATE | DELETE } \]

[CFTAPPL details](CFTUTIL/Conf/CFTAPPL.htm)

Assign a transfer owner

#### CFTAUTH: Defines an Authorized Flow Definition list

Syntax

FNAME = filename

[ID](CFTUTIL/Parameter_index/id.htm) = identifier

\[ [COMMENT](CFTUTIL/Parameter_index/comment.htm)
= string \]

\[ [MODE](CFTUTIL/Parameter_index/mode.htm)
= { REPLACE
| CREATE | DELETE } \]

 

Or

 

IDF = (identifier | mask, identifier | mask, …)

[ID](CFTUTIL/Parameter_index/id.htm) = identifier

\[ [COMMENT](CFTUTIL/Parameter_index/comment.htm)
= string \]

\[ [MODE](CFTUTIL/Parameter_index/mode.htm)
= { REPLACE
| CREATE | DELETE } \]

 

#### <span id="CFTCAT"></span>CFTCAT: Defines Catalog attributes

Syntax

[FNAME](CFTUTIL/Parameter_index/fname.htm)
= filename

[ID](CFTUTIL/Parameter_index/id.htm)
= identifier  

\[ [COMMENT](CFTUTIL/Parameter_index/comment.htm)
= string \]

\[ [MODE](CFTUTIL/Parameter_index/mode.htm)
= { REPLACE
| CREATE | DELETE } \]

\[ [RH](CFTUTIL/Parameter_index/rh.htm)
= { 10
| n }  \]

\[ [RKERROR](CFTUTIL/Parameter_index/rkerror.htm)
= { KEEP
| DELETE } \]

\[ [RT](CFTUTIL/Parameter_index/rt.htm)
= { 10
| n } \]

\[ [RX](CFTUTIL/Parameter_index/rx.htm)
= { 10
| n } \]

\[ [SH](CFTUTIL/Parameter_index/sh.htm)
= { 10
| n } \]

\[ [ST](CFTUTIL/Parameter_index/st.htm)
= { 10
| n } \]

\[ [SX](CFTUTIL/Parameter_index/sx.htm)
= { 10
| n } \]

\[ [TIMEP](CFTUTIL/Parameter_index/timep.htm)
= { 23595999
| HHMMSSCC } \]

\[ [TLVCEXEC](CFTUTIL/Parameter_index/tlvcexec.htm)
= { n } \]

\[ [TLVCLEAR](CFTUTIL/Parameter_index/tlvclear.htm)
= { <u>TLVWARN-10</u> | n } \]

\[ [TLVWEXEC](CFTUTIL/Parameter_index/tlvwexec.htm)
= { n } \]

\[ [TLVWRATE](CFTUTIL/Parameter_index/tlvwrate.htm)
= { 60 | n } \]

\[ [TLVWARN](CFTUTIL/Parameter_index/tlvwarn.htm)
= { 80 | n } \]

\[ [UPDAT](CFTUTIL/Parameter_index/updat.htm)
= { 256
| n } \]

\[ [WSCAN](CFTUTIL/Parameter_index/wscan.htm)
= { 5
| n } \]

[CFTCAT details](CFTUTIL/Conf/CFTCAT.htm)

[Catalog attributes](GUI/Concepts/Catalog_parameter_concepts.htm)

#### <span id="CFTCOM"></span>CFTCOM: Defines parameters related to the communication between applications and Transfer CFT

Syntax

#### CFTCOM TYPE = FILE

[TYPE](CFTUTIL/Parameter_index/type.htm)
= FILE

[ID](CFTUTIL/Parameter_index/id.htm)
= identifier

[NAME](CFTUTIL/Parameter_index/name.htm)
= filename  

\[ [COMMENT](CFTUTIL/Parameter_index/comment.htm)
=  string
\]

\[ [MODE](CFTUTIL/Parameter_index/mode.htm)
= { REPLACE | CREATE | DELETE } \]

\[ [TLVCEXEC](CFTUTIL/Parameter_index/tlvcexec.htm)
= { n } \]

\[ [TLVCLEAR](CFTUTIL/Parameter_index/tlvclear.htm)
= { <u>TLVWARN-20</u> | n } \]

\[ [TLVWEXEC](CFTUTIL/Parameter_index/tlvwexec.htm)
= { n } \]

\[ [TLVWRATE](CFTUTIL/Parameter_index/tlvwrate.htm)
= { 60 | n } \]

\[ [TLVWARN](CFTUTIL/Parameter_index/tlvwarn.htm)
= { 70 | n } \]

\[ [WSCAN](CFTUTIL/Parameter_index/wscan.htm)
= { 60
| n } \]

 

#### CFTCOM TYPE = TCPIP

[ID](CFTUTIL/Parameter_index/id.htm)
= identifier

[HOST](CFTUTIL/Parameter_index/host.htm)
= string

[PORT](CFTUTIL/Parameter_index/port.htm)
= number

[PROTOCOL](CFTUTIL/Parameter_index/protocol.htm)
= { XHTTP }

\[ [ADDRLIST](CFTUTIL/Parameter_index/addrlist.htm)
= ( string, string, ...) \]

\[ [COMMENT](CFTUTIL/Parameter_index/comment.htm)
=  string
\]

\[ [MODE](CFTUTIL/Parameter_index/mode.htm)
= { REPLACE
| CREATE | DELETE } \]

 [CFTCOM](CFTUTIL/Conf/CFTCOM.htm)

[Communication
media](GUI/Concepts/Communication_media_concepts.htm)

#### CFTCRON<span id="CFTCRON"></span>: Define Transfer CFT cron jobs

Syntax

ID = identifier

[CRONTAB](CFTUTIL/Parameter_index/crontab.htm)
= string

[EXEC](CFTUTIL/Parameter_index/exec.htm)
= filename

[EXECPOLICY](CFTUTIL/Parameter_index/execpolicy.htm) = \[ <u>INSTANCE</u> |ALLNODES \]

[TIME](CFTUTIL/Parameter_index/time.htm)
= { string | @shutdown | @startup } \[FOR
DETAILS: [CFTCRON
time syntax](about_cftutil/configuring_cft_start_here/cftcron)\]

\[ [PARM](CFTUTIL/Parameter_index/parm.htm)
= string \]

\[ [COMMENT](CFTUTIL/Parameter_index/comment.htm)
= string \]

\[ [STATE](CFTUTIL/Parameter_index/state.htm) = { <u>ACTIVE</u> | NOACTIVE } \]

\[ [TYPE](CFTUTIL/Parameter_index/type.htm)
= { EXEC
| CFTUTIL } \]

\[ [USERID](CFTUTIL/Parameter_index/userid.htm)
= { CFT
server "userid"
| string } \]

[Define script execution](CFTUTIL/Conf/CFTCRON.htm)

#### <span id="CFTDEST"></span>CFTDEST: Definition of a list of partners 

Syntax

CFTDEST FNAME

ID = identifier

[FNAME](CFTUTIL/Parameter_index/fname.htm)
= filename

\[ [EXEC](CFTUTIL/Parameter_index/exec.htm)
= { DEST
| PART | CHILDREN} \]

\[ EXECA = { DEST
| PART | CHILDREN} \]

\[ EXECPRE = { DEST
| PART | CHILDREN} \]

\[ [COMMENT](CFTUTIL/Parameter_index/comment.htm)
= string \]

\[ [FOR](CFTUTIL/Parameter_index/for.htm)
= { BOTH
| COMMUT |
LOCAL } \]

\[ [MODE](CFTUTIL/Parameter_index/mode.htm)
= { REPLACE
| CREATE | DELETE } \]

\[ [NOPART](CFTUTIL/Parameter_index/nopart.htm)
= { ABORT
| CONTINUE | IGNORE } \]

####  

CFTDEST PART

ID = identifier

[PART](CFTUTIL/Parameter_index/part.htm)
= (identifier, identifier, ...)

\[ [EXEC](CFTUTIL/Parameter_index/exec.htm)
= { DEST
| PART } \]

\[ [COMMENT](CFTUTIL/Parameter_index/comment.htm)
= string \]

\[ [FOR](CFTUTIL/Parameter_index/for.htm)
= { BOTH
| COMMUT |
LOCAL } \]

\[ [MODE](CFTUTIL/Parameter_index/mode.htm)
= { REPLACE
| CREATE | DELETE } \]

\[ [NOPART](CFTUTIL/Parameter_index/nopart.htm)
= { ABORT
| CONTINUE | IGNORE } \]

[CFTDEST details](CFTUTIL/Conf/CFTDEST.htm)

Broadcast
list

#### <span id="CFTEXIT"></span>CFTEXIT: Activate an exit task 

Syntax

#### CFTEXIT TYPE = FILE

[ID](CFTUTIL/Parameter_index/id.htm)
= identifier

[TYPE](CFTUTIL/Parameter_index/type.htm)
= FILE

\[ [COMMENT](CFTUTIL/Parameter_index/comment.htm)
= string \]

\[ [FORMAT](CFTUTIL/Parameter_index/format.htm)
= { V23
| 23 | V24 | 24 } \]

\[ [LANGUAGE](CFTUTIL/Parameter_index/language.htm)
= { COBOL
| C } \]

\[ [MODE](CFTUTIL/Parameter_index/mode.htm)
= { REPLACE
| CREATE | DELETE } \]

\[ [PARM](CFTUTIL/Parameter_index/parm.htm)
= string \]

\[ [PROG](CFTUTIL/Parameter_index/prog.htm)
= { CFTEXIT
| string } \]

\[ [RESERV](CFTUTIL/Parameter_index/reserv.htm)
= { 16384
| n } \]

\[ [WAITTASK](CFTUTIL/Parameter_index/waittask.htm)
= { 1441
| n } \]

 

#### CFTEXIT TYPE = { FILE | ACCESS | EXEC | BOT}

[ID](CFTUTIL/Parameter_index/id.htm)
= identifier

[TYPE](CFTUTIL/Parameter_index/type.htm)
= { FILE | ACCESS | EXEC | BOT }

\[ [COMMENT](CFTUTIL/Parameter_index/comment.htm)
= string \]

\[ [FORMAT](CFTUTIL/Parameter_index/format.htm)
= { V23
| 23 | V24 | 24 } \]

\[ [LANGUAGE](CFTUTIL/Parameter_index/language.htm)
= { COBOL
| C } \]

\[ [MODE](CFTUTIL/Parameter_index/mode.htm)
= { REPLACE
| CREATE | DELETE } \]

\[ [PARM](CFTUTIL/Parameter_index/parm.htm)
= string \]

\[ [PROG](CFTUTIL/Parameter_index/prog.htm)
= { CFTEXIT
| string } \]

\[ [RESERV](CFTUTIL/Parameter_index/reserv.htm)
= { 1024
| n } \]

\[ [WAITTASK](CFTUTIL/Parameter_index/waittask.htm)
= { 1441
| n } \]

 CFTEXIT details

[Exit
tasks](Prog/Exits/Managing_exits.htm)

#### <span id="CFTEXT"></span>CFTEXT: Extract data from the parameter and partner files 

Syntax

\[ [TYPE](CFTUTIL/Parameter_index/type.htm)
= { ALL
| ACCNT | APPL | AUTH | CAT | COM | CRON | DEST | EXIT | IDF | LOG
| NET | PARM | PART | PROT | RECV | SEND | SSL | TCP | XLATE } \]

\[ [CONTENT](CFTUTIL/Parameter_index/content.htm) = { <u>FULL</u> | BRIEF } \]

\[ [FOUT](CFTUTIL/Parameter_index/fout.htm)
= filename \]

\[ [FPARM](CFTUTIL/Parameter_index/fparm.htm)
= filename \]

\[ [FPART](CFTUTIL/Parameter_index/fpart.htm)
= filename \]

\[ [ID](CFTUTIL/Parameter_index/id.htm)
= { \*
| identifier | mask } \]

[Export
configuration](Transfers/Partners/CFTEXT_command.htm)

#### <span id="CFTFILE"></span>CFTFILE: Create or delete Transfer CFT files

Syntax

[TYPE](CFTUTIL/Parameter_index/type.htm)
= { PARM | PART }

[FNAME](CFTUTIL/Parameter_index/fname.htm)
= filename  

\[ [HABFNAME](CFTUTIL/Parameter_index/habfname.htm)
= filename \]

\[ [FBLKSIZE](CFTUTIL/Parameter_index/fblksize.htm)
= { 0
|n } \]

\[ [FSPACE](CFTUTIL/Parameter_index/fspace.htm)
= n \]

\[ [FSPACEX](CFTUTIL/Parameter_index/fspacex.htm)
= n \]

\[ [MODE](CFTUTIL/Parameter_index/mode.htm)
= { CREATE
| REPLACE | DELETE } \]

 

#### CFTFILE { CAT | COM }

[TYPE](CFTUTIL/Parameter_index/type.htm)
= {  CAT
| COM }

[FNAME](CFTUTIL/Parameter_index/fname.htm)
= filename

\[ [RECNB](CFTUTIL/Parameter_index/recnb.htm)
= n \]

\[ [FBLKSIZE](CFTUTIL/Parameter_index/fblksize.htm)
= { 0
|n } \]

\[ [FSPACE](CFTUTIL/Parameter_index/fspace.htm)
= { 0
| n } \]

\[ [FSPACEX](CFTUTIL/Parameter_index/fspacex.htm)
=  { 0
| n } \]

\[ [HABFNAME](CFTUTIL/Parameter_index/habfname.htm)
= filename \]

\[ [MODE](CFTUTIL/Parameter_index/mode.htm)
= { CREATE
| REPLACE | DELETE } \]

\[ NODE = { 0
| n } \] available for TYPE=CAT

 

#### CFTFILE { ACCNT | LOG }

[TYPE](CFTUTIL/Parameter_index/type.htm)
= { ACCNT | LOG }

[FNAME](CFTUTIL/Parameter_index/fname.htm)
= filename

\[ [FBLKSIZE](CFTUTIL/Parameter_index/fblksize.htm)
= 0
| n \]

\[ [FSPACE](CFTUTIL/Parameter_index/fspace.htm)
= 0
|n \]

\[ [FSPACEX](CFTUTIL/Parameter_index/fspacex.htm)
= 0
|n \]

\[ [MODE](CFTUTIL/Parameter_index/mode.htm)
= { CREATE
| REPLACE | DELETE } \]

[Manually create internal datafile files](CFTUTIL/Conf/CFTFILE.htm)

#### CFTFOLDER

See [CFTFOLDER](CFTUTIL/Conf/CFTFOLDER.htm) for additional parameter details.

[IDF](CFTUTIL/Parameter_index/idf.htm) = string

[PART](CFTUTIL/Parameter_index/part.htm) = string

[SCANDIR](web_copilot_ui/flow_def_intro/cftfolder)
= string

[WORKDIR](web_copilot_ui/flow_def_intro/cftfolder) = string

\[ ARCHIVEDIR = string \]

\[ ENABLESUBDIR = { <u>YES</u> | NO } \]

\[ FILEIDLEDELAY = n \]

\[ METHOD = { FILE | <u>MOVE</u> }\]

\[ STATE = { <u>ACTIVE</u> | } \]

\[ INTERVAL = n \]

\[ FILECOUNT = n \]

\[ FILESIZEMIN = n \]

\[ FILESIZEMAX = n \]

\[ INCLUDEFILTER = string \]

\[ EXCLUDEFILTER = string \]

\[ RESUBMITCHANGED { <u>YES</u> | NO }\]

\[ FILTERTYPE \]

\[ GROUPID = string \]

\[ RENAMEMETHOD \]

\[ RENAMESEPARATOR = string \]

\[ USEFSEVENTS = { YES | <u>NO</u> } \]

\[ USERID = string \]

#### <span id="CFTIDF"></span>CFTIDF ID = identifier: Correspondence between the network identifier and the local identifier of a transferred model file 

Syntax

[NIDF](CFTUTIL/Parameter_index/nidf.htm)
= string

[PART](CFTUTIL/Parameter_index/part.htm)
= identifier

[TYPE](CFTUTIL/Parameter_index/type.htm)
= { RECV
| SEND }

\[ [COMMENT](CFTUTIL/Parameter_index/comment.htm)
= string \]

\[ [MODE](CFTUTIL/Parameter_index/mode.htm)
= { REPLACE
| CREATE | DELETE } \]

 [CFTIDF details](CFTUTIL/Conf/CFTIDF.htm)

[File
template/virtual file association](GUI/Concepts/Network_file_identifier_concepts.htm)

#### <span id="CFTLOG"></span>CFTLOG FNAME = filename: Log file management parameters 

Syntax

[ID](CFTUTIL/Parameter_index/id.htm)
= identifier

\[ [AFNAME](CFTUTIL/Parameter_index/afname.htm)
= filename \]

\[ [COMMENT](CFTUTIL/Parameter_index/comment.htm)
= string \]

\[ [CONTENT](CFTUTIL/Parameter_index/content.htm)
= { FULL
| BRIEF } \]

\[ [EXEC](CFTUTIL/Parameter_index/exec.htm)
= filename \]

\[ [FORMAT](CFTUTIL/Parameter_index/format.htm)
= { V23
| 23 | V24 | 24 } \]

\[ [LENGTH](CFTUTIL/Parameter_index/length.htm)
= { 160
| n } \]

\[ [MAXREC](CFTUTIL/Parameter_index/maxrec.htm)
= { 0
| n } \]

\[ [MODE](CFTUTIL/Parameter_index/mode.htm)
= { REPLACE
| CREATE | DELETE } \]

\[ [NOTIFY](CFTUTIL/Parameter_index/notify.htm)
= identifier \]

\[ [OPERMSG](CFTUTIL/Parameter_index/opermsg.htm)
= n \]

\[ [SWITCH](CFTUTIL/Parameter_index/switch.htm)
= { 00000000
| time } \]

CFTLOG details

Transfer
Log file

#### <span id="CFTNET"></span>CFTNET: Local network resources

Syntax

#### CFTNET TYPE = TCP

[HOST](CFTUTIL/Parameter_index/host.htm)
= { string | INADDR\_ANY }

[ID](CFTUTIL/Parameter_index/id.htm)
= { identifier | \*identifier }

\[ [CALL](CFTUTIL/Parameter_index/call.htm)
= { INOUT
| IN | OUT } \]

\[ [CLASS](CFTUTIL/Parameter_index/class.htm)
= { 1 | n } \]

\[ [MAXCNX](CFTUTIL/Parameter_index/maxcnx.htm)
= { 384
| n } \]

\[ [MODE](CFTUTIL/Parameter_index/mode.htm)
= { REPLACE
| CREATE | DELETE } \]

\[ [SRCHOST](CFTUTIL/Parameter_index/srchost.htm)=
{ hostname1 | n} \]

\[ [SRCPORTS](CFTUTIL/Parameter_index/srcports.htm)= { string } \]

 

#### CFTNET TYPE = SR

[HOST](CFTUTIL/Parameter_index/host.htm)
= { string | INADDR\_ANY }

[ID](CFTUTIL/Parameter_index/id.htm)
= { identifier | \*identifier }

\[ RECALLHOST = { string } \]

\[ [PORT](CFTUTIL/Parameter_index/port.htm) = {0 ...65535 } \]

\[ [SRCHOST](CFTUTIL/Parameter_index/srchost.htm) = { string } \]

\[ SSLTERM { YES | <u>NO</u> } \]

#### PROTOCOL = GENERIC

[HOST](CFTUTIL/Parameter_index/host.htm)
= string

[ID](CFTUTIL/Parameter_index/id.htm)
= identifier

INET
= identifier

[PORT](CFTUTIL/Parameter_index/port.htm)
=  n

\[ [CALL](CFTUTIL/Parameter_index/call.htm)
= { INOUT
| IN | OUT } \]

\[ [CLASS](CFTUTIL/Parameter_index/class.htm)
= { 1 | n } \]

\[ [MAXCNX](CFTUTIL/Parameter_index/maxcnx.htm)
= { 384
| n } \]

\[ [MODE](CFTUTIL/Parameter_index/mode.htm)
= { REPLACE
| CREATE | DELETE } \]

\[ [PARM](CFTUTIL/Parameter_index/parm.htm)
= string \]

\[ [SRCHOST](CFTUTIL/Parameter_index/srchost.htm)=
{ hostname1 | n} \]

 

#### CFTNET TYPE = TCP

#### PROTOCOL = SOCKS4, SOCKS5

[HOST](CFTUTIL/Parameter_index/host.htm)
= string  

[ID](CFTUTIL/Parameter_index/id.htm)
= identifier

INET
= identifier

[PORT](CFTUTIL/Parameter_index/port.htm)
=  n

\[ [CALL](CFTUTIL/Parameter_index/call.htm)
= { INOUT
| IN | OUT } \]

\[ [CLASS](CFTUTIL/Parameter_index/class.htm)
= { 1 | n } \]

\[ [MAXCNX](CFTUTIL/Parameter_index/maxcnx.htm)
= { 32
| n } \]

\[ [MODE](CFTUTIL/Parameter_index/mode.htm)
= { REPLACE
| CREATE | DELETE } \]

\[ [SRCHOST](CFTUTIL/Parameter_index/srchost.htm)=
{ hostname1 | n} \]

\[ [USER](CFTUTIL/Parameter_index/user.htm)
= string \]

 [CFTNET details](CFTUTIL/Conf/CFTNET.htm)

[Network
resources](GUI/Concepts/Network_resource_concepts.htm)

[About proxies and SOCKS](Prots/internet/use_Proxy_and_SOCKS_protocol.htm)

#### <span id="CFTPARM"></span>CFTPARM: General Transfer CFT environment parameters

Syntax

[CAT](CFTUTIL/Parameter_index/cat.htm)
= identifier

[COM](CFTUTIL/Parameter_index/com.htm)
= ( identifier ,  identifier
, ...)

[ID](CFTUTIL/Parameter_index/id.htm)
= identifier

[KEY](CFTUTIL/Parameter_index/key.htm)
= {string | #filename }

[NET](CFTUTIL/Parameter_index/net.htm)
= ( identifier ,  identifier
,...)

[PART](CFTUTIL/Parameter_index/part.htm)
= identifier  

[PARTFNAM](CFTUTIL/Parameter_index/partfnam.htm)
= filename  

[PROT](CFTUTIL/Parameter_index/prot.htm)
= ( identifier ,  identifier
, ...)

\[ [ACCNT](CFTUTIL/Parameter_index/accnt.htm)
= identifier  \]

\[ [BUFSIZE](CFTUTIL/Parameter_index/bufsize.htm)
=  { 4096
| n } \]

\[ [COMMENT](CFTUTIL/Parameter_index/comment.htm)
= string \]

\[ [CRONTABS](CFTUTIL/Parameter_index/crontab.htm)
= (crontab, crontab, …) \]

\[ [DEFAULT](CFTUTIL/Parameter_index/default.htm)
= { DEFAUT
| identifier } \]

\[ [EXECRE](CFTUTIL/Parameter_index/execre.htm)
= filename \]

\[ [EXECRF](CFTUTIL/Parameter_index/execrf.htm)
= filename \]

\[ [EXECRM](CFTUTIL/Parameter_index/execrm.htm)
= filename \]

\[ [EXECSE](CFTUTIL/Parameter_index/execse.htm)
= filename \]

\[ [EXECSF](CFTUTIL/Parameter_index/execsf.htm)
= filename \]

\[ [EXECSFA](CFTUTIL/Parameter_index/execsfa.htm)
= filename \]

\[ [EXECSM](CFTUTIL/Parameter_index/execsm.htm)
= filename  \]

\[ [EXECSMA](CFTUTIL/Parameter_index/execsma.htm)
= filename \]

\[ EXITBOT
= identifier  \]

\[ [EXITEOT](CFTUTIL/Parameter_index/exiteot.htm)
= identifier  \]

\[ [FBUFSIZE](CFTUTIL/Parameter_index/fbufsize.htm)
= { 0
|65535 } \]

\[ [LENAPPL](CFTUTIL/Parameter_index/lenappl.htm)
= { 32
| 1 } \]

\[ [LOG](CFTUTIL/Parameter_index/log.htm)
= identifier  \]

\[ [MAXTASK](CFTUTIL/Parameter_index/maxtask.htm)
= { 8
| n }  \]

\[ [MAXTRANS](CFTUTIL/Parameter_index/maxtrans.htm)
=  { 256
| 1 } \]

\[ [MODE](CFTUTIL/Parameter_index/mode.htm)
= { REPLACE
| CREATE | DELETE }  \]

\[ [NPART](CFTUTIL/Parameter_index/npart.htm)
= string \]

\[ [PKIPASSW](CFTUTIL/Parameter_index/pkipassw.htm)
= { PKIPASSW | string } \]

\[ [RCVALLER](CFTUTIL/Parameter_index/rcvaller.htm)
= { STOP
| CONTINUE } \]

\[ [SECFNAME](CFTUTIL/Parameter_index/secfname.htm)
= filename \]

\[ [SSLMTASK](CFTUTIL/Parameter_index/sslmtask.htm)
= { 8
| n } \]

\[ [SSLTTASK](CFTUTIL/Parameter_index/sslttask.htm)
=  {3
| n } \]

\[ [SSLWTASK](CFTUTIL/Parameter_index/sslwtask.htm)
= { 10
|n } \]

\[ [SSLWRESP](CFTUTIL/Parameter_index/sslwresp.htm)
= { 60
| n } \]

\[ [TRACE](CFTUTIL/Parameter_index/trace.htm)
= string \]

\[ [TRANTASK](CFTUTIL/Parameter_index/trantask.htm)
= { 3
| n } \]

\[ [TRKPART](CFTUTIL/Parameter_index/trkpart.htm)
=  { UNDEFINED
| ALL | SUMMARY | NO } \]

\[ [TRKRECV](CFTUTIL/Parameter_index/trkrecv.htm)
=  { UNDEFINED
| ALL | SUMMARY | NO } \]

\[ [TRKSEND](CFTUTIL/Parameter_index/trksend.htm)
= { UNDEFINED
| ALL | SUMMARY | NO } \]

\[ [USERCTRL](CFTUTIL/Parameter_index/userctrl.htm)
= { NO
| YES } \]

\[ [WAITRESP](CFTUTIL/Parameter_index/waitresp.htm)
= { 60
| n } \]

\[ [WAITTASK](CFTUTIL/Parameter_index/waittask.htm)
= { 10
| n } \]

[CFTPARM details](CFTUTIL/Conf/CFTPARM.htm)

[Transfer CFT general
parameters](GUI/Concepts/CFTPARM_General_parameters.htm)

#### <span id="CFTPART"></span>CFTPART ID = identifier: Partner definition parameters  

Syntax

[PROT](CFTUTIL/Parameter_index/prot.htm)
= { (identifier | mask , identifier | mask , .... ) }

\[ [COMMENT](CFTUTIL/Parameter_index/comment.htm)
= string  \]

\[ [COMMUT](CFTUTIL/Parameter_index/commut.htm)
= { YES
| NO | SERVER }   \]

\[ [CTRLPART](CFTUTIL/Parameter_index/ctrlpart.htm)
= { IGNORE
| ALL | RPART | SPART } \]

\[ [FPREFIX](CFTUTIL/Parameter_index/fprefix.htm)
= string \]

\[ [GROUP](CFTUTIL/Parameter_index/group.htm)
= identifier \]

\[ [IDF](CFTUTIL/Parameter_index/idf.htm)
= identifier  \]

\[ [IMAXTIME](CFTUTIL/Parameter_index/imaxtime.htm)
= { 23595999
| time } \]

\[ IMINTIME
= { 0
| time } \]

\[ [IPART](CFTUTIL/Parameter_index/ipart.htm)
= identifier \]

\[ [MODE](CFTUTIL/Parameter_index/mode.htm)
= { REPLACE
| CREATE | DELETE } \]

\[ [NACK](CFTUTIL/NACK.htm) = { YES | <u>NO</u> | ANY } \]

\[ [NRPART](CFTUTIL/Parameter_index/nrpart.htm)
= string \]

\[ [NRPASSW](CFTUTIL/Parameter_index/nrpassw.htm) = string  \]

\[ [NSPART](CFTUTIL/Parameter_index/nspart.htm)
= string  \]

\[ [NSPASSW](CFTUTIL/Parameter_index/nspassw.htm)
= string  \]

\[ [OMAXTIME](CFTUTIL/Parameter_index/omaxtime.htm)
= { 23595999
| time } \]

\[ [OMINTIME](CFTUTIL/Parameter_index/omintime.htm)
= { 0
| time } \]

\[ [RAUTH](CFTUTIL/Parameter_index/rauth.htm)
= { \*
| identifier } \]

\[ [SAP](CFTUTIL/Parameter_index/sap.htm)
= (string, string, …) \]

\[ [SAUTH](CFTUTIL/Parameter_index/sauth.htm)
= { \*
| identifier } \]

\[ [SSL](CFTUTIL/Parameter_index/ssl.htm)
= identifier \]

\[ [STATE](CFTUTIL/Parameter_index/state.htm)
= {ACTIVEBOTH
| ACTIVEREQ | ACTIVESERV | NOACTIVE } \]

\[ [SYST](CFTUTIL/Parameter_index/syst.htm)
= { ‘
‘ | GCOS7 | GCOS8 | GUARD | MVS | OS400 |
UNIX | VM | VMS | VSE | WINNT | BS2000 } \]

\[ [TRK](CFTUTIL/Parameter_index/trk.htm)
= { UNDEFINED
| ALL | SUMMARY | NO } \]

\[ [XLATE](CFTUTIL/Parameter_index/xlate.htm)
= identifier \]

CFTPART details

Partner
attribute concepts

#### <span id="CFTPROT"></span>CFTPROT: Transfer protocol

Syntax

CFTPROT TYPE = ODETTE

[ID](CFTUTIL/Parameter_index/id.htm)
= identifier

[NET](CFTUTIL/Parameter_index/net.htm)
= identifier

\[ [DISCTD](CFTUTIL/Parameter_index/disctd.htm)
= { 20
| n } \]

\[ [DISCTS](CFTUTIL/Parameter_index/discts.htm)
= { 65
| n } \]

\[ [DYNAM](CFTUTIL/Parameter_index/dynam.htm)
= identifier  \]

\[ [EERP](CFTUTIL/Parameter_index/EERP.htm)
= { 91
| 86 } \]

\[ [EXITA](CFTUTIL/Parameter_index/exita.htm)
= identifier \]

\[ [IDF](CFTUTIL/Parameter_index/ida.htm)
= string  \]

\[ [MODE](CFTUTIL/Parameter_index/mode.htm)
= { REPLACE
| CREATE | DELETE } \]

\[ [PAD](CFTUTIL/Parameter_index/pad.htm)
= { NO
| YES } \] &lt;Deprecated in Transfer CFT 3.5>

\[ [RCOMP](CFTUTIL/Parameter_index/rcomp.htm)
=  { 0
| 15 } \]

\[ [RCREDIT](CFTUTIL/Parameter_index/rcredit.htm)
= { 4
| n } \]

\[ [RESTART](CFTUTIL/Parameter_index/restart.htm)
= { 5
| n } \]

\[ [RESYNC](CFTUTIL/Parameter_index/resync.htm)
= { NO
| YES } \]

\[ [REVERSE](CFTUTIL/Parameter_index/reverse.htm)
= { YES
| NO } \]

\[ [RRUSIZE](CFTUTIL/Parameter_index/rrusize.htm)
= { 2048
| n } \]

\[ [RTO](CFTUTIL/Parameter_index/rto.htm)
= { 260
| n } \]

\[ [SAP](CFTUTIL/Parameter_index/sap.htm)
= string \]

\[ [SCOMP](CFTUTIL/Parameter_index/scomp.htm)
= { 0 | <u>1</u> |15 } \]

\[ [SCREDIT](CFTUTIL/Parameter_index/scredit.htm)
= { 4
| n } \]

\[ [SRIN](CFTUTIL/Parameter_index/srin.htm)
= { BOTH
| NONE | RECEIVER | SENDER } \]

\[ [SROUT](CFTUTIL/Parameter_index/srout.htm)
= { BOTH
| NONE | RECEIVER | SENDER } \]

\[ [SRUSIZE](CFTUTIL/Parameter_index/srusize.htm)
= { 2048 | n } \]

\[ [SSL](CFTUTIL/Parameter_index/ssl.htm)
= identifier \]

\[ [TCP](CFTUTIL/Parameter_index/tcp.htm)
= { CFT
| <u>OFTP</u>} \]

 

CFTPROT TYPE = PESIT

[PROF](CFTUTIL/Parameter_index/prof.htm)
= ANY

[ID](CFTUTIL/Parameter_index/id.htm)
= identifier  

[NET](CFTUTIL/Parameter_index/net.htm)
= identifier

\[ [CONCAT](CFTUTIL/Parameter_index/concat.htm)
= { NO
| <u>YES</u> } \]

\[ [DISCTC](CFTUTIL/Parameter_index/disctc.htm)
= { 60
| n } \]

\[ [DISCTD](CFTUTIL/Parameter_index/disctd.htm)
= { 10
| n } \]

\[ [DISCTR](CFTUTIL/Parameter_index/disctr.htm)
= { 45
| n } \]

\[ [DISCTS](CFTUTIL/Parameter_index/discts.htm)
= { 60
|n } \]

\[ [DYNAM](CFTUTIL/Parameter_index/dynam.htm)
= identifier \]

\[ [EXITA](CFTUTIL/Parameter_index/exita.htm)
= identifier \]

\[ [HIDE99](CFTUTIL/Parameter_index/hide99.htm)
= { NO
| YES } \]

\[ [IDF](CFTUTIL/Parameter_index/idf.htm)
= string \]

\[ [LOGON](CFTUTIL/Parameter_index/logon.htm)
= { YES
| NO } \]

\[ [MODE](CFTUTIL/Parameter_index/mode.htm)
= { REPLACE
| CREATE | DELETE } \]

\[ [MULTART](CFTUTIL/Parameter_index/multart.htm)
= { NO
| <u>YES</u> } \]

\[ [NACK](CFTUTIL/NACK.htm) = { YES | <u>NO</u> | ANY} \]

\[ [PAD](CFTUTIL/Parameter_index/pad.htm)
= { NO
| YES } \] &lt;Deprecated in Transfer CFT 3.5>

\[ [RCHKW](CFTUTIL/Parameter_index/rchkw.htm)
= { 3
| n } \]

\[ [RCOMP](CFTUTIL/Parameter_index/rcomp.htm)
= { <u>0</u>
| 15 } \]

\[ [RESTART](CFTUTIL/Parameter_index/restart.htm)
= { 5
| n } \]

\[ [RESYNC](CFTUTIL/Parameter_index/resync.htm)
= { NO
| YES } \]

\[ [REVERSE](CFTUTIL/Parameter_index/reverse.htm)
= { NO
| YES } \]

\[ [RPACING](CFTUTIL/Parameter_index/rpacing.htm)
= { 32767
| n } \]

\[ [RRUSIZE](CFTUTIL/Parameter_index/rrusize.htm)
= { 32750
|n } \]

\[ [RTO](CFTUTIL/Parameter_index/rto.htm)
= { 260
| n } \]

\[ [SAP](CFTUTIL/Parameter_index/sap.htm)
= string \]

\[ [SCHKW](CFTUTIL/Parameter_index/schkw.htm)
= { 3
| n } \]

\[ [SCOMP](CFTUTIL/Parameter_index/scomp.htm)
= { <u>0</u> | 15} \]

\[ [SEGMENT](CFTUTIL/Parameter_index/segment.htm)
= { NO
| <u>YES</u> } \]

\[ [SPACING](CFTUTIL/Parameter_index/spacing.htm)
= { 32767
| n } \]

\[ [SRIN](CFTUTIL/Parameter_index/srin.htm)
= { BOTH
| NONE | RECEIVER | SENDER } \]

\[ [SROUT](CFTUTIL/Parameter_index/srout.htm)
= { BOTH
| NONE | RECEIVER | SENDER } \]

\[ [SRUSIZE](CFTUTIL/Parameter_index/srusize.htm)
= { 32750
| n } \]

\[ [SSERV](CFTUTIL/Parameter_index/sserv.htm)
= { GSIT
| string } \]

\[ [SSL](CFTUTIL/Parameter_index/ssl.htm)
= identifier \]

 

CFTPROT TYPE = PESIT  

[PROF](CFTUTIL/Parameter_index/prof.htm)
= CFT

[ID](CFTUTIL/Parameter_index/id.htm)
= identifier

[NET](CFTUTIL/Parameter_index/net.htm)
= identifier

\[ [CONCAT](CFTUTIL/Parameter_index/concat.htm)
= { NO
| YES } \]

\[ [DISCTC](CFTUTIL/Parameter_index/disctc.htm)
= { 90
| n }  \]

\[ [DISCTD](CFTUTIL/Parameter_index/disctd.htm)
=  { 20
| n } \]

\[ [DISCTR](CFTUTIL/Parameter_index/disctr.htm)
= { 45
| n } \]

\[ [DISCTS](CFTUTIL/Parameter_index/discts.htm)
= { 65
| n } \]

\[ [DYNAM](CFTUTIL/Parameter_index/dynam.htm)
= identifier  \]

\[ [EXITA](CFTUTIL/Parameter_index/exita.htm)
= identifier  \]

\[ [HIDE99](CFTUTIL/Parameter_index/hide99.htm)
= { NO
|YES } \]

\[ [IDF](CFTUTIL/Parameter_index/idf.htm)
= string \]

\[ [MODE](CFTUTIL/Parameter_index/mode.htm)
= { REPLACE
| CREATE | DELETE } \]

\[ [MULTART](CFTUTIL/Parameter_index/multart.htm)
= { NO
| YES } \]

\[ [PAD](CFTUTIL/Parameter_index/pad.htm)
= { NO
| YES } \] &lt;Deprecated in Transfer CFT 3.5>

\[ [RCHKW](CFTUTIL/Parameter_index/rchkw.htm)
= { 2
| n }  \]

\[ [RCOMP](CFTUTIL/Parameter_index/rcomp.htm)
= { 0 |15} \]

\[ [RESTART](CFTUTIL/Parameter_index/restart.htm)
= { 5
| n } \]

\[ [RESYNC](CFTUTIL/Parameter_index/resync.htm)
= { NO
| YES } \]

\[ [REVERSE](CFTUTIL/Parameter_index/reverse.htm)
= { NO
| YES } \]

\[ [RPACING](CFTUTIL/Parameter_index/rpacing.htm)
= { 36
| n } \]

\[ [RRUSIZE](CFTUTIL/Parameter_index/rrusize.htm)
= { 4056
| n } \]

\[ RSERV
= string \]

\[ [RTO](CFTUTIL/Parameter_index/rto.htm)
= { 260
| n }  \]

\[ [SAP](CFTUTIL/Parameter_index/sap.htm)
= string \]

\[ [SCHKW](CFTUTIL/Parameter_index/schkw.htm)
= { 2
| n } \]

\[ [SCOMP](CFTUTIL/Parameter_index/scomp.htm)
= { 0| 15
} \]

\[ [SEGMENT](CFTUTIL/Parameter_index/segment.htm)
= { NO
| YES } \]

\[ [SPACING](CFTUTIL/Parameter_index/spacing.htm)
= { 36
| n } \]

\[ [SRIN](CFTUTIL/Parameter_index/srin.htm)
= { BOTH
| NONE | RECEIVER | SENDER } \]

\[ [SROUT](CFTUTIL/Parameter_index/srout.htm)
= { BOTH
| NONE | RECEIVER | SENDER } \]

\[ [SRUSIZE](CFTUTIL/Parameter_index/srusize.htm)
= { 4056
|n } \]

\[ [SSERV](CFTUTIL/Parameter_index/sserv.htm)
= { CFTPSITX | string } \]

\[ [SSL](CFTUTIL/Parameter_index/ssl.htm)
= identifier \]

 

CFTPROT TYPE = PESIT

[PROF](CFTUTIL/Parameter_index/prof.htm)
= EXTERN

[ID](CFTUTIL/Parameter_index/id.htm)
= identifier

[NET](CFTUTIL/Parameter_index/net.htm)
= identifier

\[ [CONCAT](CFTUTIL/Parameter_index/concat.htm)
= { NO
| YES } \]

\[ [DISCTC](CFTUTIL/Parameter_index/disctc.htm)
= { 90
| n } \]

\[ [DISCTD](CFTUTIL/Parameter_index/disctd.htm)
=  { 120
| n } \]

\[ [DISCTR](CFTUTIL/Parameter_index/disctr.htm)
= { 45
| n } \]

\[ [DISCTS](CFTUTIL/Parameter_index/discts.htm)
= { 165
| n } \]

\[ [DYNAM](CFTUTIL/Parameter_index/dynam.htm)
= identifier  \]

\[ [EXITA](CFTUTIL/Parameter_index/exita.htm)
= identifier   \]

\[ [HIDE99](CFTUTIL/Parameter_index/hide99.htm)
= { NO
|YES } \]

\[ [IDF](CFTUTIL/Parameter_index/idf.htm)
= string  \]

\[ [MODE](CFTUTIL/Parameter_index/mode.htm)
= { REPLACE
| CREATE | DELETE } \]

\[ [LOGON](CFTUTIL/Parameter_index/logon.htm)
= { YES
| NO } \]

\[ [MULTART](CFTUTIL/Parameter_index/multart.htm)
= { NO
| YES } \]

\[ [NACK](CFTUTIL/NACK.htm) = { YES | <u>NO</u> | ANY } \]

\[ [RCHKW](CFTUTIL/Parameter_index/rchkw.htm)
= { 2
| n } \]

\[ [RCOMP](CFTUTIL/Parameter_index/rcomp.htm)
=  { 0 | 10
|15 } \]

\[ [RESTART](CFTUTIL/Parameter_index/restart.htm)
= { 5
| n } \]

\[ [RESYNC](CFTUTIL/Parameter_index/resync.htm)
= { NO
| YES } \]

\[ [REVERSE](CFTUTIL/Parameter_index/reverse.htm)
= { YES | NO } \]

\[ [RPACING](CFTUTIL/Parameter_index/rpacing.htm)
= { 36 | n } \]

\[ [RRUSIZE](CFTUTIL/Parameter_index/rrusize.htm)
= { 4056 | n } \]

\[ [RTO](CFTUTIL/Parameter_index/rto.htm)
= { 260
| n } \]

\[ [SAP](CFTUTIL/Parameter_index/sap.htm)
= string \]

\[ [SCHKW](CFTUTIL/Parameter_index/schkw.htm)
= { 2
| n } \]

\[ [SCOMP](CFTUTIL/Parameter_index/scomp.htm)
=  { 0 | 10
| 15} \]

\[ [SEGMENT](CFTUTIL/Parameter_index/segment.htm)
= { NO | YES } \]

\[ [SPACING](CFTUTIL/Parameter_index/spacing.htm)
= { 36 | n } \]

\[ [SRIN](CFTUTIL/Parameter_index/srin.htm)
= { BOTH
| NONE | RECEIVER | SENDER } \]

\[ [SROUT](CFTUTIL/Parameter_index/srout.htm)
= { BOTH
| NONE | RECEIVER | SENDER } \]

\[ [SRUSIZE](CFTUTIL/Parameter_index/srusize.htm)
= { 4056 | n } \]

\[ [SSERV](CFTUTIL/Parameter_index/sserv.htm)
= { PESIT
| string } \]

\[ [SSL](CFTUTIL/Parameter_index/ssl.htm)
= identifier \]

 

CFTPROT TYPE = PESIT

[PROF](CFTUTIL/Parameter_index/prof.htm)
= SIT

[ID](CFTUTIL/Parameter_index/id.htm)
= identifier

[NET](CFTUTIL/Parameter_index/net.htm)
= identifier  

\[ [CONCAT](CFTUTIL/Parameter_index/concat.htm)
= { NO
| YES } \]

\[ [DISCTC](CFTUTIL/Parameter_index/disctc.htm)
= { 90
| n } \]

\[ [DISCTD](CFTUTIL/Parameter_index/disctd.htm)
= { 240 | n } \]

\[ [DISCTR](CFTUTIL/Parameter_index/disctr.htm)
= { 45 | n } \]

\[ [DISCTS](CFTUTIL/Parameter_index/discts.htm)
= { 285 | n } \]

\[ [DYNAM](CFTUTIL/Parameter_index/dynam.htm)
= identifier \]

\[ [EXITA](CFTUTIL/Parameter_index/exita.htm)
= identifier \]

\[ [IDF](CFTUTIL/Parameter_index/ida.htm)
= string \]

\[ [MODE](CFTUTIL/Parameter_index/mode.htm)
= { REPLACE
| CREATE | DELETE } \]

\[ [MULTART](CFTUTIL/Parameter_index/multart.htm)
=  { NO
| YES } \]

\[ [RCHKW](CFTUTIL/Parameter_index/rchkw.htm)
= { 2
| n } \]

\[ [RCOMP](CFTUTIL/Parameter_index/rcomp.htm)
=  { 0 |
15 } \]

\[ [RESTART](CFTUTIL/Parameter_index/restart.htm)
= { 5
| n } \]

\[ [RESYNC](CFTUTIL/Parameter_index/resync.htm)
= { NO
| YES } \]

\[ [REVERSE](CFTUTIL/Parameter_index/reverse.htm)
= { NO
| string } \]

\[ [RPACING](CFTUTIL/Parameter_index/rpacing.htm)
= { 36
| n } \]

\[ [RRUSIZE](CFTUTIL/Parameter_index/rrusize.htm)
= { 4050 | n } \]

\[ [RTO](CFTUTIL/Parameter_index/rto.htm)
= { 260 | n } \]

\[ [SAP](CFTUTIL/Parameter_index/sap.htm)
= string \]

\[ [SCHKW](CFTUTIL/Parameter_index/schkw.htm)
= { 2 | n } \]

\[ [SCOMP](CFTUTIL/Parameter_index/scomp.htm)
= { 0 | 15 } \]

\[ [SEGMENT](CFTUTIL/Parameter_index/segment.htm)
= { NO | YES } \]

\[ [SPACING](CFTUTIL/Parameter_index/spacing.htm)
= { 36
| n } \]

\[ [SRIN](CFTUTIL/Parameter_index/srin.htm)
= { BOTH
| NONE | RECEIVER | SENDER } \]

\[ [SROUT](CFTUTIL/Parameter_index/srout.htm)
= { BOTH
| NONE | RECEIVER | SENDER } \]

\[ [SRUSIZE](CFTUTIL/Parameter_index/srusize.htm)
= { 4050 | n } \]

\[ [SSL](CFTUTIL/Parameter_index/ssl.htm)
= identifier \]

 

CFTPROT TYPE = PESIT

[PROF](CFTUTIL/Parameter_index/prof.htm)
= DMZ  

[ID](CFTUTIL/Parameter_index/id.htm)
= identifier

[NET](CFTUTIL/Parameter_index/net.htm)
= identifier

\[ [CONCAT](CFTUTIL/Parameter_index/concat.htm)
= { NO
| YES } \]

\[ [CTO](CFTUTIL/Parameter_index/cto.htm)
= { 1
| n } \]

\[ [CYCLE](CFTUTIL/Parameter_index/cycle.htm)
= { 10
| n } \]

\[ [DISCTC](CFTUTIL/Parameter_index/disctc.htm)
= { 90
| n } \]

\[ [DISCTD](CFTUTIL/Parameter_index/disctd.htm)
= { 120
| n } \]

\[ [DISCTR](CFTUTIL/Parameter_index/disctr.htm)
= { 45
| n } \]

\[ [DISCTS](CFTUTIL/Parameter_index/discts.htm)
= { 65
| n  } \]

\[ [DYNAM](CFTUTIL/Parameter_index/dynam.htm)
= identifier \]

\[ [EXITA](CFTUTIL/Parameter_index/exita.htm)
= identifier \]

\[ [IDF](CFTUTIL/Parameter_index/idf.htm)
= string \]

\[ [LOGON](CFTUTIL/Parameter_index/logon.htm)
= { YES
| NO } \]

\[ [MODE](CFTUTIL/Parameter_index/mode.htm)
= { REPLACE
| CREATE | DELETE } \]

\[ [MULTART](CFTUTIL/Parameter_index/multart.htm)
= { NO
| YES } \]

\[ [PAD](CFTUTIL/Parameter_index/pad.htm)
= { NO
| YES } \] &lt;Deprecated in Transfer CFT 3.5>

\[ [PART](CFTUTIL/Parameter_index/part.htm)
= ( identifier, identifier, …) \]

\[ [RCHKW](CFTUTIL/Parameter_index/rchkw.htm)
= { 2
| n } \]

\[ [RCOMP](CFTUTIL/Parameter_index/rcomp.htm)
= { 0 | 10
| 15 } \]

\[ [RESTART](CFTUTIL/Parameter_index/restart.htm)
= { 5
| n  } \]

\[ [RESYNC](CFTUTIL/Parameter_index/resync.htm)
= { NO
| YES } \]

\[ [REVERSE](CFTUTIL/Parameter_index/reverse.htm)
= { NO
| YES } \]

\[ [RPACING](CFTUTIL/Parameter_index/rpacing.htm)
= { 36
| n } \]

\[ [RRUSIZE](CFTUTIL/Parameter_index/rrusize.htm)
= n \]

\[ [RTO](CFTUTIL/Parameter_index/rto.htm)
= { 260
| n } \]

\[ [SAP](CFTUTIL/Parameter_index/sap.htm)
= string \]

\[ [SCHKW](CFTUTIL/Parameter_index/schkw.htm)
= { 2
| n } \]

\[ [SCOMP](CFTUTIL/Parameter_index/scomp.htm)
= { 0 | 10
| 15 } \]

\[ [SEGMENT](CFTUTIL/Parameter_index/segment.htm)
= { NO
| YES } \]

\[ [SPACING](CFTUTIL/Parameter_index/spacing.htm)
= { 36
| n }\]

\[ [SRIN](CFTUTIL/Parameter_index/srin.htm)
= { BOTH
| NONE | RECEIVER | SENDER } \]

\[ [SROUT](CFTUTIL/Parameter_index/srout.htm)
= { BOTH
| NONE | RECEIVER | SENDER } \]

\[ [SSERV](CFTUTIL/Parameter_index/sserv.htm)
= { PESIT
| string } \]

\[ [SSL](CFTUTIL/Parameter_index/ssl.htm)
= identifier \]

\[ TURN
= { FILE
| MESSAGE } \]

 

[CFTPROT details](GUI/Conf/Transfer_protocol_concepts.htm)

[File
Transfer Protocol](GUI/Conf/Transfer_protocol_concepts.htm)

#### <span id="CFTRECV"></span>CFTRECV ID= identifier: Description of model file receiving parameters

Syntax

\[ [ACKEXEC](CFTUTIL/Parameter_index/ackexec.htm) = filename\]

\[ [COMMENT](CFTUTIL/Parameter_index/comment.htm)
= string \]

\[ [CYCDATE](CFTUTIL/Parameter_index/cycdate.htm)
= { 0
| date } \]

\[ [CYCTIME](CFTUTIL/Parameter_index/cyctime.htm)
= { 0
| time } \]

\[ [DELETE](CFTUTIL/Parameter_index/delete.htm)
= { NO
| YES } \]

\[ [DIRNB](CFTUTIL/Parameter_index/dirnb.htm)
= { 0
| n } \]

\[ [DUPLICATE](CFTUTIL/Parameter_index/duplicat.htm) = { string 512 } \]

\[ [EXEC](CFTUTIL/Parameter_index/exec.htm)
= filename \]

\[ EXECRALL = { <u>all</u> | parent| children} \]

\[ [EXIT](CFTUTIL/Parameter_index/exit.htm)
= identifier  \]

\[ [FACC](CFTUTIL/Parameter_index/facc.htm)
= { ‘
‘ | character } \]

\[ [FACTION](CFTUTIL/Parameter_index/faction.htm)
= { ‘
‘ | DELETE | ERASE | RENAME | VERIFY } \]

\[ [FBLKSIZE](CFTUTIL/Parameter_index/fblksize.htm)
= { 0
| n } \]

\[ [FCHECK](CFTUTIL/Parameter_index/fcheck.htm)
= { NO
| YES } \]

\[ [FCODE](CFTUTIL/Parameter_index/fcode.htm)
= { ‘
‘ |BINARY | EBCDIC | ASCII } \]

\[ FDB
= filename \]

\[ [FDELETE](CFTUTIL/Parameter_index/fdelete.htm) = <u>" "</u> |\* | C |D | K | H | T | X\]

\[ [FDISP](CFTUTIL/Parameter_index/fdisp.htm)
= { BOTH
| NEW | OLD } \]

\[ FILENOTFOUND = { <u>ABORT</u> | IGNORE } \]

\[ [FKEYLEN](CFTUTIL/Parameter_index/fkeylen.htm)
= { 0
| n } \]

\[ [FKEYPOS](CFTUTIL/Parameter_index/fkeypos.htm)
= { 0
| n } \]

\[ [FLOWNAME](CFTUTIL/Parameter_index/flowname.htm) = string \]

\[ [FLRECL](CFTUTIL/Parameter_index/flrec.htm)
=  { 0
| n  } \]

\[ [FNAME](CFTUTIL/Parameter_index/fname.htm)
= filename \]

\[ [FORCE](CFTUTIL/Parameter_index/force.htm)
= { NO
| YES }  \]

\[ [FORG](CFTUTIL/Parameter_index/forg.htm)
= { SEQ
| DIRECT | INDEXED | PART } \]

\[ [FPAD](CFTUTIL/Parameter_index/fpad.htm) = { <u>' '</u> | character } \]

\[ [FRECFM](CFTUTIL/Parameter_index/frecfm.htm)
= { ‘
‘ |F | V | U } \]

\[ [FSPACE](CFTUTIL/Parameter_index/fspace.htm)
=  { 0
| n } \]

\[ [FTYPE](CFTUTIL/Parameter_index/ftype.htm)
=  { ‘
‘ | character } \]

\[ [GROUPID](CFTUTIL/Parameter_index/groupid.htm)
= string \]

\[ [MACTION](CFTUTIL/Parameter_index/maction.htm)
=  { '
' | REPLACE } \]

\[ [MAXDATE](CFTUTIL/Parameter_index/maxdate.htm)
=  { 99991231
| date } \]

\[ MAXDURATION = ** **{<u>0</u>...32767} \]

\[ [MAXTIME](CFTUTIL/Parameter_index/maxtime.htm)
= { 23595999
| time } \]

\[ [MINDATE](CFTUTIL/Parameter_index/mindate.htm)
= { 10000101
| date } \]

\[ [MINTIME](CFTUTIL/Parameter_index/mintime.htm)
= { 0
| time } \]

\[ [MODE](CFTUTIL/Parameter_index/mode.htm)
= { REPLACE
| CREATE | DELETE } \]

\[ [NCOMP](CFTUTIL/Parameter_index/ncomp.htm)
= { 0 | 15
} \]

\[ [NETBAND](CFTUTIL/Parameter_index/netband.htm) = { 1...16} \]

\[ [NOTIFY](CFTUTIL/Parameter_index/notify.htm)
= string \]

\[ [NPAD](CFTUTIL/Parameter_index/npad.htm) = { <u>' '</u> | character } \]

\[ [NCODE](CFTUTIL/Parameter_index/ncode.htm)
= { ‘
‘ |ASCII | BINARY | EBCDIC } \] \*available only when the protocol is SFTP

\[ [OPERMSG](CFTUTIL/Parameter_index/opermsg.htm)
= { 0
| 255 } \]

\[ [PRI](CFTUTIL/Parameter_index/pri.htm)
= { 128 | n } \]

\[ [RAPPL](CFTUTIL/Parameter_index/rappl.htm)
= string \]

\[ [RKERROR](CFTUTIL/Parameter_index/rkerror.htm)
= { ' ' | DELETE | KEEP } \]

\[ [RPASSWD](CFTUTIL/Parameter_index/rpassw.htm) = string \]

\[ [RUSER](CFTUTIL/Parameter_index/ruser.htm)
= string \]

\[ [SAPPL](CFTUTIL/Parameter_index/sappl.htm)
= string \]

\[ [SERIAL](CFTUTIL/Parameter_index/serial.htm) = { <u>' '</u> | Y | Z | X } \]

\[ [SOURCEAPPL](CFTUTIL/Parameter_index/sourceappl.htm) = string \]

\[ [SPASSWD](CFTUTIL/Parameter_index/spasswd.htm) = string \]

\[ [STATE](CFTUTIL/Parameter_index/state.htm)
= { DISP | HOLD | KEEP } \]

\[ [STORAGEACCOUNT](CFTUTIL/Parameter_index/storageaccount.htm) = string \]

\[ [SUSER](CFTUTIL/Parameter_index/suser.htm)
= string \]

\[ [TARGETAPPL](CFTUTIL/Parameter_index/targetappl.htm) = string \]

\[ [TRK](CFTUTIL/Parameter_index/trk.htm)
=  { UNDEFINED
| ALL | SUMMARY | NO } \]

\[ [USERID](CFTUTIL/Parameter_index/userid.htm)
= { CFT server"userid" | string } \]

\[ [WFNAME](CFTUTIL/Parameter_index/wfname.htm)
= filename \]

\[ [WORKINGDIR](CFTUTIL/Parameter_index/workingdir.htm) = string \]

\[ [XLATE](CFTUTIL/Parameter_index/xlate.htm)
= identifier \]

 [CFTRECV details](CFTUTIL/Conf/CFTRECV.htm)

#### <span id="CFTSEND"></span>CFTSEND ID= identifier: Description of model file sending parameters

Syntax

\[ [ACKEXEC](CFTUTIL/Parameter_index/ackexec.htm) = filename\]

\[ ARCHIVEFNAME = string \]

\[ [COMMENT](CFTUTIL/Parameter_index/comment.htm)
= string \]

\[ [CYCDATE](CFTUTIL/Parameter_index/cycdate.htm)
= { 0
| date } \]

\[ [CYCLE](CFTUTIL/Parameter_index/cycle.htm)
= { 0
| n } \]

\[ [CYCTIME](CFTUTIL/Parameter_index/cyctime.htm)
= { 0
| time } \]

\[ [DELETE](CFTUTIL/Parameter_index/delete.htm)
= { NO
| YES } \]

\[ [DUPLICATE](CFTUTIL/Parameter_index/duplicat.htm) = { string 512 } \]

\[ [EXEC](CFTUTIL/Parameter_index/exec.htm)
= filename \]

\[ [EXECSUB](CFTUTIL/Parameter_index/execsub.htm)
= { LIST
| FILE | SUBF } \]

\[ [EXECSUBA](CFTUTIL/Parameter_index/execsuba.htm) = {LIST | FILE | <u>SUBF</u> } \]

\[ [EXECSUBPRE](CFTUTIL/Parameter_index/execsubpre.htm) = { LIST
| FILE | SUBF } \]

\[ [EXIT](CFTUTIL/Parameter_index/exit.htm)
=  identifier
\]

\[ [FACC](CFTUTIL/Parameter_index/facc.htm)
= { ‘
‘ | character } \]

\[ [FACTION](CFTUTIL/Parameter_index/faction.htm)
= { NONE
| DELETE | ERASE | ARCHIVE } \]

\[ [FBLKSIZE](CFTUTIL/Parameter_index/fblksize.htm)
= { 0
| n } \]

\[ [FCODE](CFTUTIL/Parameter_index/fcode.htm)
= { ‘
‘ |ASCII | BINARY | EBCDIC } \]

\[ FDB
= filename \]

\[ [FDELETE](CFTUTIL/Parameter_index/fdelete.htm) = <u>" "</u> |\* | C |D | K | H | T | X\]

\[ [FDISP](CFTUTIL/Parameter_index/fdisp.htm)
= { SHR
| OLD | CHECK } \]

\[ FILENOTFOUND = { <u>ABORT</u> | IGNORE } \]

\[ [FILTER](CFTUTIL/Parameter_index/filter.htm) = string \]

\[ [FILTERTYPE](CFTUTIL/Parameter_index/filtertype.htm) = string \]

\[ [FKEYLEN](CFTUTIL/Parameter_index/fkeylen.htm)
= { 0
| n } \]

\[ [FKEYPOS](CFTUTIL/Parameter_index/fkeypos.htm)
= { 0
| n } \]

\[ [FLOWNAME](CFTUTIL/Parameter_index/flowname.htm) = string \]

\[ [FLRECL](CFTUTIL/Parameter_index/flrec.htm)
= { 0
| n } \]

\[ [FNAME](CFTUTIL/Parameter_index/fname.htm)
 = { filename
| mask | dirname | #filename | #mask | #dirname } \]

\[ [FORCE](CFTUTIL/Parameter_index/force.htm)
= { NO
| YES } \]

\[ [FORG](CFTUTIL/Parameter_index/forg.htm)
= { SEQ
| DIRECT | INDEXED | PART } \]

\[ [FPAD](CFTUTIL/Parameter_index/fpad.htm) = { <u>' '</u> | character } \]

\[ [FRECFM](CFTUTIL/Parameter_index/frecfm.htm)
= { ‘
‘ | F | U | V } \]

\[ [FSPACE](CFTUTIL/Parameter_index/fspace.htm)
= { 0
| n } \]

\[ [FTYPE](CFTUTIL/Parameter_index/ftype.htm)
= { ‘
‘ | character } \]

\[ [GROUPID](CFTUTIL/Parameter_index/groupid.htm)
= string \]

\[ [IDA](CFTUTIL/Parameter_index/ida.htm) = string \]

\[ [IMPL](CFTUTIL/Parameter_index/impl.htm)
= { NO
| YES } \]

\[ [MAXDATE](CFTUTIL/Parameter_index/maxdate.htm)
=  { 99991231
| date } \]

\[ MAXDURATION = ** **{<u>0</u>...32767} \]

\[ [MAXTIME](CFTUTIL/Parameter_index/maxtime.htm)
= { 23595999
| time } \]

\[ [MINDATE](CFTUTIL/Parameter_index/mindate.htm)
= { 10000101|
date } \]

\[ [MINTIME](CFTUTIL/Parameter_index/mintime.htm)
= { 0
| time } \]

\[ [MODE](CFTUTIL/Parameter_index/mode.htm)
= { REPLACE
| CREATE | DELETE } \]

\[ [NBLKSIZE](CFTUTIL/Parameter_index/nblksize.htm)
= { 0
| n } \]

\[ [NCODE](CFTUTIL/Parameter_index/ncode.htm)
= { ‘
‘ |ASCII | BINARY | EBCDIC } \]

\[ [NCOMP](CFTUTIL/Parameter_index/ncomp.htm)
=  { 0 |
15
} \]

\[ [NETBAND](CFTUTIL/Parameter_index/netband.htm)
= { 1...16} \]

\[ [NFNAME](CFTUTIL/Parameter_index/nfname.htm)
=  { filename
| \*filename } \]

\[ [NKEYLEN](CFTUTIL/Parameter_index/nkeylen.htm)
= { 0
| n } \]

\[ [NKEYPOS](CFTUTIL/Parameter_index/nkeypos.htm)
= { 0|
n } \]

\[ [NLRECL](CFTUTIL/Parameter_index/nlrecl.htm)
=  { 0
| n } \]

\[ [NOTIFY](CFTUTIL/Parameter_index/notify.htm)
= string  \]

\[ [NPAD](CFTUTIL/Parameter_index/npad.htm) = { <u>' '</u> | character } \]

\[ [NRECFM](CFTUTIL/Parameter_index/nrecfm.htm)
= { ‘
‘ | F | U | V } \]

\[ [NSPACE](CFTUTIL/Parameter_index/nspace.htm)
=  { 0
| n } \]

\[ [NTYPE](CFTUTIL/Parameter_index/ntype.htm)
= character \]

\[ [OPERMSG](CFTUTIL/Parameter_index/opermsg.htm)
= { 0
| 255 } \]

\[ [PARM](CFTUTIL/Parameter_index/parm.htm)
= string  \]

\[ [PREEXEC](CFTUTIL/Parameter_index/preexec.htm) = filename \]

\[ [PRI](CFTUTIL/Parameter_index/pri.htm)
= { 128
| n } \]

\[ [RAPPL](CFTUTIL/Parameter_index/rappl.htm)
= string \]

\[ [RPASSWD](CFTUTIL/Parameter_index/rpassw.htm) = string \]

\[ [RUSER](CFTUTIL/Parameter_index/ruser.htm)
= string \]

\[ [SAPPL](CFTUTIL/Parameter_index/sappl.htm)
= string \]

\[ [SELFNAME](CFTUTIL/Parameter_index/selfname.htm)
= filename \]

\[ [SERIAL](CFTUTIL/Parameter_index/serial.htm) = { <u>' '</u> | Y | Z | X } \]

\[ [SPART](CFTUTIL/Parameter_index/spart.htm)
= string \]

\[ [SPASSWD](CFTUTIL/Parameter_index/spasswd.htm) = string \]

\[ [SOURCEAPPL](CFTUTIL/Parameter_index/sourceappl.htm) = string \]

\[ [STATE](CFTUTIL/Parameter_index/state.htm)
= { DISP
| HOLD | KEEP } \]

\[ [STORAGEACCOUNT](CFTUTIL/Parameter_index/storageaccount.htm) = string \]

\[ [SUSER](CFTUTIL/Parameter_index/suser.htm)
= string \]

\[ [](CFTUTIL/Parameter_index/targetappl.htm)[TARGETAPPL](CFTUTIL/Parameter_index/targetappl.htm) = string \]

\[ [TCYCLE](CFTUTIL/Parameter_index/tcycle.htm)
= { DAY
| MIN | MONTH } \]

\[ [TRK](CFTUTIL/Parameter_index/trk.htm)
=  { UNDEFINED
| ALL | SUMMARY | NO } \]

\[ [USERID](CFTUTIL/Parameter_index/userid.htm)
= { CFT
server "userid" | string } \]

\[ [WFNAME](CFTUTIL/Parameter_index/wfname.htm)
= filename \]

\[ [WORKINGDIR](CFTUTIL/Parameter_index/workingdir.htm) = string \]

\[ [XLATE](CFTUTIL/Parameter_index/xlate.htm)
= identifier \]

[CFTSEND details](CFTUTIL/Conf/CFTSEND.htm)

[Send
file template](GUI/Concepts/Default_SEND_template_concepts.htm)

#### <span id="CFTSSL"></span>CFTSSL ID = identifier: Security files

Syntax

[CIPHLIST](CFTUTIL/Parameter_index/ciphlist.htm)
= ( number, number, …)

[DIRECT](CFTUTIL/Parameter_index/direct.htm)
= { CLIENT
| SERVER }

\[ [CACHE](CFTUTIL/Parameter_index/cache.htm)
= { NO
| YES } \]

\[ CERFNAME
= string \]

\[ [COMMENT](CFTUTIL/Parameter_index/comment.htm)
= string \]

\[ DEPTH
= { 10
| n } \]

\[ [DNISSUER](CFTUTIL/Parameter_index/dnissuer.htm)
= ( string, string, …) \]

\[ [DNUSER](CFTUTIL/Parameter_index/dnuser.htm)
= { ( string, string, …) | ( string, OP ([see Note](#*OP)), string ) } \]

\[ [INTERCID](CFTUTIL/Parameter_index/intercid.htm)
= string \]

\[ [KEYEXT](CFTUTIL/Parameter_index/keyext.htm) = { VERIFY | NONE } \]

\[ [MODE](CFTUTIL/Parameter_index/mode.htm)
= { REPLACE
| CREATE | DELETE } \]

\[ [PARM](CFTUTIL/Parameter_index/parm.htm)
= string \]

\[ [PASSW](CFTUTIL/Parameter_index/passw.htm) = string \]

\[ [ROOTCID](CFTUTIL/Parameter_index/rootcid.htm)
= ( string, string, …) \]

\[ [TRACE](CFTUTIL/Parameter_index/trace.htm)
= { 0
| n } \]

\[ [USERCID](CFTUTIL/Parameter_index/usercid.htm)
= string \]

\[ [VERIFY](CFTUTIL/Parameter_index/verify.htm)
= { NONE| REQUIRED
| OPTIONAL } \] *\*When DIRECT=SERVER*

\[ [VERIFY](CFTUTIL/Parameter_index/verify.htm)
= { <u>NONE</u>| REQUIRED
| ENFORCED | OPTIONAL } \] *\*When DIRECT=CLIENT *

\[ [VERSION](CFTUTIL/Parameter_index/version.htm)
= { <u>TLSV1</u>  | SSLV3 | TLSV1 | SSLV3COMP | TLSV1COMP} \]

Note: <span id="OP"></span>You can configure Transfer
CFT to accept or reject SSL connections based on logical operators used
within the DN of the certificate. For details refer to [dnuser](CFTUTIL/Parameter_index/dnuser.htm)
parameter details.

[CFTSSL details](Security/Transport/Transport_security_CFTSSL.htm)

[SSL/TLS security concepts](Security/Transport/transport_security_Start_here.htm)

#### <span id="CFTTCP"></span>CFTTCP: Network parameters of a TCP/IP partner

Syntax

[HOST](CFTUTIL/Parameter_index/host.htm)
= string

[ID](CFTUTIL/Parameter_index/id.htm)
= identifier

\[ [CLASS](CFTUTIL/Parameter_index/class.htm)
= { 1
| n } \]

\[ [CNXIN](CFTUTIL/Parameter_index/cnxin.htm)
= { 2
| n } \]

\[ [CNXINOUT](CFTUTIL/Parameter_index/cnxinout.htm)
= { 4
| n } \]

\[ [CNXOUT](CFTUTIL/Parameter_index/cnxout.htm)
= { 2
| n } \]

\[ [IMAXTIME](CFTUTIL/Parameter_index/imaxtime.htm)
= { 23595999
| time } \]

\[ IMINTIME
= { 0
| time } \]

\[ [MODE](CFTUTIL/Parameter_index/mode.htm)
= { REPLACE
| CREATE | DELETE } \]

\[ [OMAXTIME](CFTUTIL/Parameter_index/omaxtime.htm)
= { 23595999
| time } \]

\[ [OMINTIME](CFTUTIL/Parameter_index/omintime.htm)
= { 0
| time } \]

\[ [RETRYM](CFTUTIL/Parameter_index/retrym.htm)
= { 12
| n } \]

\[ [RETRYN](CFTUTIL/Parameter_index/retryn.htm)
= { 4
| n } \]

\[ [RETRYW](CFTUTIL/Parameter_index/retryw.htm)
= { 1
| n } \]

\[ [VERIFY](CFTUTIL/Parameter_index/verify.htm)
= { 0
| n } \]

[TCP
attributes for a partner](GUI/Concepts/Network_resource_concepts.htm)

#### <span id="CFTUIPREF"></span>CFTUIPREF MODE=mode

MODE= { CREATE | <u>REPLACE</u> | DELETE }

[ID](CFTUTIL/Parameter_index/id.htm)
= identifier  

[TYPE](CFTUTIL/Parameter_index/type.htm) = string

\[ [COMMENT](CFTUTIL/Parameter_index/comment.htm)
= string \]

\[ [CONTENT](CFTUTIL/Parameter_index/content.htm)
= { ACTIVE
| FULL } \]

\[ [ORIGIN](CFTUTIL/Parameter_index/origin.htm) \] = string \]

#### <span id="CFTXLATE"></span>CFTXLATE FNAME = filename: Define conversion tables

Syntax

[ID](CFTUTIL/Parameter_index/id.htm)
= identifier  

\[ [COMMENT](CFTUTIL/Parameter_index/comment.htm)
= string \]

\[ [DIRECT](CFTUTIL/Parameter_index/direct.htm)
= { BOTH
| RECV | SEND } \]

\[ [FCODE](CFTUTIL/Parameter_index/fcode.htm)
= { '
' | ASCII | EBCDIC } \]

\[ [MODE](CFTUTIL/Parameter_index/mode.htm)
= { REPLACE
| CREATE | DELETE } \]

\[ [NCODE](CFTUTIL/Parameter_index/ncode.htm)
= { '
' | ASCII | EBCDIC } \]

\[ [ORIGIN](CFTUTIL/Parameter_index/origin.htm) \] = string \]

\[ TABLE \] = string \]

[Conversion
tables](GUI/Concepts/Translation_table_concepts.htm)

#### <span id="CLEARCMD"></span>CLEARCMD COMMAND = string: Delete a transfer request

Syntax

[USERID](CFTUTIL/Parameter_index/userid.htm)
= string

[INDEX](CFTUTIL/Parameter_index/index2.htm)
= number

[CLEARCMD details](Transfers/Transfer_states/CLEARCMD_command.htm)

#### <span id="CONFIG"></span>CONFIG: Designate the communication medium and the files accessed by CFTUTIL

Syntax

CONFIG TYPE = { CAT | INPUT | OUTPUT | PARM | PART }

[FNAME](CFTUTIL/Parameter_index/fname.htm) = filename

 

CONFIG TYPE = COM

MEDIACOM = FILE

[FNAME](CFTUTIL/Parameter_index/fname.htm) = filename

 

CONFIG
TYPE = COM

MEDIACOM
= TCPIP

[FNAME](CFTUTIL/Parameter_index/fname.htm)= string

\[ [HIGHPORT](CFTUTIL/Parameter_index/highport.htm)
=  { 65535
| n } \]

\[ [LOWPORT](CFTUTIL/Parameter_index/lowport.htm)
= { 5000
| n } \]

\[ PASSWORD = string } \]

\[ PROXY
= string \]

\[ [ROOTCERT](CFTUTIL/Parameter_index/rootcert.htm)
= string \]

\[ [TIMEOUT](CFTUTIL/Parameter_index/timeout.htm)
= 60
| n \]

[Setting default CFTUTIL file names](CFTUTIL/Redefining_CFTUTIL_data_media.htm)

#### <span id="COPYFILE"></span>COPYFILE IFNAME = filename: Copy files with an off-line compression or decompression option

Syntax

[OFNAME](CFTUTIL/Parameter_index/ofname.htm)
= filename

\[ [CREATE](CFTUTIL/Parameter_index/create.htm)
= { ‘
‘ | YES | NO } \]

\[ [IBLKSIZE](CFTUTIL/Parameter_index/iblksize.htm)
= { 0
| n } \]

\[ ICHARSET = string \]

\[ [ICODE](CFTUTIL/Parameter_index/icode.htm)
= { ASCII | EBCDIC } \]

\[ [ICOMP](CFTUTIL/Parameter_index/icomp.htm)
= { 0
| 15 } \]

\[ [ICT](CFTUTIL/Parameter_index/ict.htm)
=  { H
| C } \]

\[ [ILRECL](CFTUTIL/Parameter_index/ilrecl.htm)
= { 0
| n } \]

\[ [IRECFM](CFTUTIL/Parameter_index/irecfm.htm)
= { F | V | U } \]

\[ [ITYPE](CFTUTIL/Parameter_index/itype.htm)
= { ‘ ‘ | character } \]

\[ [OBLKSIZE](CFTUTIL/Parameter_index/oblksize.htm)
= { 0 |n  }
\]

\[ OCHARSET = string \]

\[ [OCODE](CFTUTIL/Parameter_index/ocode.htm)
= { ASCII | EBCDIC } \]

\[ [OCOMP](CFTUTIL/Parameter_index/ocomp.htm)
= { 0
| 15 } \]

\[ [OCT](CFTUTIL/Parameter_index/oct.htm)
= { H | C } \]

\[ [OLRECL](CFTUTIL/Parameter_index/olrecl.htm)
= { 0
|n } \]

\[ [ORECFM](CFTUTIL/Parameter_index/orecfm.htm)
= { IRECFM
value | F | V| U } \]

\[ [OSPACE](CFTUTIL/Parameter_index/ospace.htm)
= { 0
| n } \]

\[ [OTYPE](CFTUTIL/Parameter_index/otype.htm)
= { ‘
‘ | character } \]

\[ [XLATE](CFTUTIL/Parameter_index/xlate.htm) = string \]

[Copying files off-line](CFTUTIL/Admin/COPYFILE_command.htm)

#### <span id="DELETE"></span>DELETE PART = { identifier | mask }: Delete a catalog entry

Syntax

\[ [BLKNUM](CFTUTIL/Parameter_index/blknum.htm)
= { 0
| n } \]

\[ [DIRECT](CFTUTIL/Parameter_index/direct.htm)
= { BOTH
| RECV | SEND } \]

\[ [FORCE](CFTUTIL/Parameter_index/force.htm)
=  { YES
| NO
} \]

\[ [IDA](CFTUTIL/Parameter_index/ida.htm)
= identifier  \]

\[ [IDF](CFTUTIL/Parameter_index/idf.htm)
= identifier \]

\[ [IDT](CFTUTIL/Parameter_index/idu.htm)
= { \*
| transid } \]

\[ [IDTU](CFTUTIL/Parameter_index/idtu.htm)
= string \]

\[ [STATE](CFTUTIL/Parameter_index/state.htm)
= { \*
| C | D | H | K | T | X } \]

\[ KDATE
= { 0
| n } \]

\[ KTIME
= { 0
| n } \]

\[ PHASE = string \]

\[ PHASESTEP = string \]

\[ [SCOPE](CFTUTIL/Parameter_index/scope.htm) = string \]

[Deleting catalog entries](Transfers/Transfer_states/DELETE_command.htm)

#### <span id="DISPLAY"></span>DISPLAY \[ CONTENT = { listcat | identifier }\]: Display a model-formatted catalog

Syntax

\[ [DATETIMEMAX](CFTUTIL/Parameter_index/datetimemax.htm) = { 0 | <u>991231235959</u> } \]

\[ [DATETIMEMIN](CFTUTIL/Parameter_index/datetimemin.htm) = { <u>0</u> | 991231235959 } \]

\[ [DIAGI](CFTUTIL/Parameter_index/diagi.htm) = { <u>\*</u> | 0 | ERROR } \]

\[ [DIRECT](CFTUTIL/Parameter_index/direct.htm)
= { BOTH
| RECV | SEND } \]

\[ [EMPTY](CFTUTIL/Parameter_index/empty.htm)
= { ANY
| string } \]

\[ [FILE](CFTUTIL/Parameter_index/file.htm)
= filename \]

\[ [FMODEL](CFTUTIL/Parameter_index/fmodel.htm)
=  string
\]

\[ [FOUT](CFTUTIL/Parameter_index/fout.htm) = string \]

\[ [HELP](CFTUTIL/Parameter_index/help.htm)
= { NONE
| FIELDS | MODELS | COMMAND } \]

\[ [IDA](CFTUTIL/Parameter_index/ida.htm)
=  string
\]

\[ [IDF](CFTUTIL/Parameter_index/idf.htm)
= string \]

\[ [IDT](CFTUTIL/Parameter_index/idu.htm)
= string \]

\[ [IDTU](CFTUTIL/Parameter_index/idtu.htm)
= string \]

\[ [MODE](CFTUTIL/Parameter_index/mode.htm)
= { ANY
| COLUMN | LINE } \]

\[ [NA](CFTUTIL/Parameter_index/na.htm)
= { ANY
| string } \]

\[ NIDT 
= { string of 8 digits } \]

\[ [NPART](CFTUTIL/Parameter_index/npart.htm)
= string \]

\[ [PART](CFTUTIL/Parameter_index/part.htm)
= string \]

\[ [RUSER](CFTUTIL/Parameter_index/ruser.htm)
= string \]

\[ [SORTBY](CFTUTIL/Parameter_index/sortby.htm)
= string \]

\[ [SUSER](CFTUTIL/Parameter_index/suser.htm)
= string \]

\[ [STATE](CFTUTIL/Parameter_index/state.htm)
= { \*
| character } \]

\[ [TYPE](CFTUTIL/Parameter_index/type.htm)
= { \*
| FILE | MESSAGE | REPLY | ALL } \]

[Catalog output display model](CFTUTIL/Monitoring/DISPLAY_command.htm)

#### <span id="END"></span>END PART = { identifier | mask }: Change transfer to X state

Syntax

\[ [APPCYCID](CFTUTIL/Parameter_index/appcycid.htm)
= string \]

\[ [APPOBJID](CFTUTIL/Parameter_index/appobjid.htm)
= string \]

\[ APPSTATE
= string \]

\[ [SAPPL](CFTUTIL/Parameter_index/sappl.htm)
= string \]

\[ [RUSER](CFTUTIL/Parameter_index/ruser.htm)
= string \]

\[ [SUSER](CFTUTIL/Parameter_index/suser.htm)
= string \]

\[ [RPASSWD](CFTUTIL/Parameter_index/rpassw.htm)
= string \]

\[ [SPASSWD](CFTUTIL/Parameter_index/spasswd.htm)
= string \]

\[ [BLKNUM](CFTUTIL/Parameter_index/blknum.htm)
= { 0
| n } \]

\[ DIAGC = string \]

\[ [DIRECT](CFTUTIL/Parameter_index/direct.htm)
= { BOTH
| RECV | SEND } \]

\[ [FORCE](CFTUTIL/Parameter_index/force.htm)
= { NO
| YES } \]

\[ [FNAME](CFTUTIL/Parameter_index/fname.htm)
= string \]

\[ [IDA](CFTUTIL/Parameter_index/ida.htm)
= identifier \]

\[ [IDF](CFTUTIL/Parameter_index/idf.htm)
= identifier \]

\[ [IDT](CFTUTIL/Parameter_index/idu.htm)
= { \*
| transid } \]

\[ [IDTU](CFTUTIL/Parameter_index/idtu.htm)
= string \]

\[ ISTATE = { YES | <u>NO</u> } \]

\[ ISTATE
= string \]

\[ KDATE
= { 0
| n } \]

\[ KTIME
= { 0
| n } \]

\[ [NFNAME](CFTUTIL/Parameter_index/nfname.htm)
= string \]

\[ [PARM](CFTUTIL/Parameter_index/parm.htm)
= string \]

\[ PHASE = string \]

\[ PHASESTEP = string \]

\[ [PRI](CFTUTIL/Parameter_index/pri.htm) Number { 0 - <u>256</u> } \]

\[ [RAPPL](CFTUTIL/Parameter_index/rappl.htm)
= string \]

\[ [SCOPE](CFTUTIL/Parameter_index/scope.htm) = string \]

\[ [SIGFNAME](CFTUTIL/Parameter_index/sigfname.htm)
= string \]

\[ [STATE](CFTUTIL/Parameter_index/state.htm) = string \]

[END details](Transfers/Transfer_states/END_command.htm)

#### <span id="HALT"></span>HALT PART = { identifier | mask }: Suspend a transfer

Syntax

\[ [BLKNUM](CFTUTIL/Parameter_index/blknum.htm)
= { 0
| n } \]

\[ DIAGC = string \]

\[ [DIAGP](CFTUTIL/Parameter_index/diagp.htm) = string \]

\[ [DIRECT](CFTUTIL/Parameter_index/direct.htm)
= { BOTH
| RECV | SEND } \]

\[ [FORCE](CFTUTIL/Parameter_index/force.htm)
= { YES | NO
} \]

\[ [IDA](CFTUTIL/Parameter_index/ida.htm)
= identifier  \]

\[ [IDF](CFTUTIL/Parameter_index/idf.htm)
= identifier  \]

\[ [IDT](CFTUTIL/Parameter_index/idu.htm)
= { \*
| transid } \]

\[ [IDTU](CFTUTIL/Parameter_index/idtu.htm)
= string  \]

\[ [STATE](CFTUTIL/Parameter_index/state.htm) = string \]

\[ KDATE
= { 0
| n } \]

\[ KTIME
= { 0
| n } \]

\[ PHASE = string \]

\[ PHASESTEP = string \]

\[ [SCOPE](CFTUTIL/Parameter_index/scope.htm) = string \]

[Halting a transfer](Transfers/Transfer_states/HALT_command.htm)

#### HELP

Syntax

\[ CMD = { string } \]

\[ CONTENT = { <u>BRIEF</u> | DETAIL} \]

\[ OFORMAT = { <u>txt</u> | xsd } \]

#### <span id="INACT"></span>INACT ID = identifier: Inactivate a partner

Syntax

\[ [MODE](CFTUTIL/Parameter_index/mode.htm)
= { BOTH
| REQUESTER| SERVER } \]

\[ [FORCE](CFTUTIL/Parameter_index/force.htm)
= { NO
| YES } \]

\[ [TYPE](CFTUTIL/Parameter_index/type.htm)
= PART
| TRK | CRON | FOLDER \]

[INACT details](Transfers/Partners/INACT_command.htm)

#### <span id="KEEP"></span>KEEP PART = { identifier | mask }: Abort a transfer

Syntax

\[ [BLKNUM](CFTUTIL/Parameter_index/blknum.htm)
= 0
| n \]

\[ DIAGC = string \]

\[ [DIAGP](CFTUTIL/Parameter_index/diagp.htm) = string \]

\[ [DIRECT](CFTUTIL/Parameter_index/direct.htm)
= { BOTH
| RECV | SEND } \]

\[ [FORCE](CFTUTIL/Parameter_index/force.htm)
= { YES
| NO } \]

\[ [IDA](CFTUTIL/Parameter_index/ida.htm)
= identifier  \]

\[ [IDF](CFTUTIL/Parameter_index/idf.htm)
= identifier \]

\[ [IDT](CFTUTIL/Parameter_index/idu.htm)
= { \*
| transid } \]

\[ [IDTU](CFTUTIL/Parameter_index/idtu.htm)
= string  \]

\[ [STATE](CFTUTIL/Parameter_index/state.htm)
= string \]

\[ KDATE
= { 0
| n } \]

\[ KTIME
= { 0
| n } \]

\[ PHASE = string \]

\[ PHASESTEP = string \]

\[ [SCOPE](CFTUTIL/Parameter_index/scope.htm) = string \]

 [Suspend transfers](Transfers/Transfer_states/KEEP_command.htm)

#### <span id="KSTATE"></span>KSTATE IDF = identifier: Change a transfer state

Syntax

[IDTU](CFTUTIL/Parameter_index/idtu.htm)
= local transfer counter identifier

[PART](CFTUTIL/Parameter_index/part.htm)
= partner identifier

[KSTATE details](Transfers/Transfer_states/KSTATE_command.htm)

#### <span id="LISTCAT"></span>LISTCAT TYPE = { ALL | \* | FILE | MESSAGE | REPLY }: List catalog entries

Syntax

\[ [CONTENT](CFTUTIL/Parameter_index/content.htm)
= { BRIEF
| FULL | DEBUG | EXTEND | COMMUT | STAT | BLKNUM } \]

\[ [DATETIMEMAX](CFTUTIL/Parameter_index/datetimemax.htm) = { 0 | <u>991231235959</u> } \]

\[ [DATETIMEMIN](CFTUTIL/Parameter_index/datetimemin.htm) = { <u>0</u> | 991231235959 } \]

\[ [DIAGI](CFTUTIL/Parameter_index/diagi.htm) = { <u>\*</u> | 0 | ERROR } \]

\[ [DIRECT](CFTUTIL/Parameter_index/direct.htm)
= { BOTH
| RECV | SEND } \]

\[ [FILE](CFTUTIL/Parameter_index/file.htm)
= filename \]

\[ [IDA](CFTUTIL/Parameter_index/ida.htm)
= { \*
| identifier } \]

\[ [IDF](CFTUTIL/Parameter_index/idf.htm)
= { \*
| identifier } \]

\[ [IDT](CFTUTIL/Parameter_index/idu.htm)
= { \*
| transid } \]

\[ [IDTU](CFTUTIL/Parameter_index/idtu.htm)
= string  \]

\[ NIDT 
= { string of 8 digits } \]

\[ [NPART](CFTUTIL/Parameter_index/npart.htm)
= { identifier | mask } \]

\[ [PART](CFTUTIL/Parameter_index/part.htm)
= { \*
| identifier | mask } \]

\[ [SORTBY](CFTUTIL/Parameter_index/sortby.htm)
= string \]

\[ [STATE](CFTUTIL/Parameter_index/state.htm)
= { \*
| string } \]

 [LISTCAT details](CFTUTIL/Monitoring/LISTCAT_command.htm)

#### <span id="LISTCOM"></span>LISTCOM: Display contents of a communication media

Syntax

\[ [CONTENT](CFTUTIL/Parameter_index/content.htm)
= { ACTIVE
| FULL } \]

\[ [FILE](CFTUTIL/Parameter_index/file.htm)
= filename \]

\[ FIRST
= { 0
| n } \]

\[ LAST
= { 0
| max. number of records } \]

\[ [VERIFY](CFTUTIL/Parameter_index/verify.htm)
= { NO
| YES } \]

 [LISTCOM details](CFTUTIL/Monitoring/LISTCOM_command.htm) 

#### <span id="LISTLOG"></span>LISTLOG: Display and filter log content including merged nodes in cluster mode

Syntax

\[ LOGLEVEL = { F | E | W | <u>I</u> } \]

\[ LINES = { -10000 | <u>-20</u> | 10000 } \]

\[ [DATEMAX](CFTUTIL/Parameter_index/datemin_datemax.htm) = { 0 | <u>991231</u> } \]

\[ [DATEMIN](CFTUTIL/Parameter_index/datemin_datemax.htm) = { <u>0</u> | 991231 } \]

\[ [DATETIMEMAX](CFTUTIL/Parameter_index/datetimemax.htm) = { 0 | <u>99123123595999</u> } \]

\[ [DATETIMEMIN](CFTUTIL/Parameter_index/datetimemin.htm) { <u>0</u> | 99123123595999 } \]

\[ TIMEMIN = { <u>0</u>| 23595999 } \]

\[ TIMEMAX = { 0 | <u>23595999</u> } \]

\[ PATTERN = string \]

\[ DISPLAYNODEID = { <u>YES</u> | NO } \]

\[ NODE = string \]

#### LISTNODE: Display all nodes

Syntax

No parameters

[Multi-node commands](multi_node/multi_node_commands.htm)

#### <span id="LISTPARM"></span>LISTPARM: Display Transfer CFT partner details

Syntax

\[ [ID](CFTUTIL/Parameter_index/id.htm)
= { \*
| identifier } \]

\[ [CONTENT](CFTUTIL/Parameter_index/content.htm)
= { FULL
| BRIEF } \]

\[ [PART](CFTUTIL/Parameter_index/part.htm)
= identifier  \]

\[ [TYPE](CFTUTIL/Parameter_index/type.htm)
= { ACCNT | ALL
| APPL | AUTH | CAT | COM | CRON | EXIT | IDF | LOG | NET | PARM | PROT
| RECV | SEND | SSL | XLATE } \]

[LISTPARM details](CFTUTIL/Monitoring/LISTPARM.htm)

#### <span id="LISTPART"></span>LISTPART: Display partners

Syntax

\[ [ID](CFTUTIL/Parameter_index/id.htm)
= { \*
|identifier } \]

\[ [CONTENT](CFTUTIL/Parameter_index/content.htm)
= { FULL
| BRIEF } \]

\[ [TYPE](CFTUTIL/Parameter_index/type.htm)
= { ALL
| DEST | PART | TCP | } \]

[LISTPART details](Transfers/Partners/LISTPART_command.htm)

#### <span id="MQUERY"></span>MQUERY : Query one or more Transfer CFT components

Syntax

OBJECT = CACHE

\[ [OBJECT](CFTUTIL/Parameter_index/object.htm)
= { CACHE
| SYSTEM | STATS | PROBE } \]

\[ [CONTENT](CFTUTIL/Parameter_index/content.htm)
= { BRIEF
| FULL | STAT } \]

\[ [NAME](CFTUTIL/Parameter_index/name.htm)
= { CAT
| COMMAND | CRON | DMZ | STAT } \]

 

OBJECT = SYSTEM

\[ [OBJECT](CFTUTIL/Parameter_index/object.htm)
= { CACHE
| SYSTEM | STATS | PROBE } \]

\[ [CONTENT](CFTUTIL/Parameter_index/content.htm)
= { BRIEF
| FULL | STAT } \]

\[ [NAME](CFTUTIL/Parameter_index/name.htm)
= { CFTMAIN | CFTTRK | CFTTFIL | CFTCOM | CFTTPRO | CFTEXIT | CFTPRX | CFTDSCAN } \]

 

OBJECT = STATS or PROBE

\[ [OBJECT](CFTUTIL/Parameter_index/object.htm)
= { CACHE
| SYSTEM | STATS | PROBE } \]

\[ [CONTENT](CFTUTIL/Parameter_index/content.htm)
= { XMLBRIEF
| XMLFULL | RAW } \]

\[ [NAME](CFTUTIL/Parameter_index/name.htm)
= { CAT
| COMMAND | CRON | DMZ | STAT } \]

 [MQUERY details](CFTUTIL/Querying_a_component_.htm)

#### <span id="PURGE"></span>PURGE: Delete records from the catalog 

Syntax

\[ [TIMEP](CFTUTIL/Parameter_index/timep.htm)
= { 23595999
| time } \]

[PURGE details](CFTUTIL/Monitoring/Purge_catalog.htm)

#### <span id="RECONFIG"></span>RECONFIG: Reload

Syntax

\[ [TYPE](CFTUTIL/Parameter_index/type.htm)
= { CRON | UCONF | CAT | FOLDER | PARMCACHE | AM
} \]

 [Manage configuration updates](CFTUTIL/Monitoring/RECONFIG.htm)

#### <span id="RECV"></span>RECV IDF = { identifier | mask }: Request to receive transfer

Syntax

[PART](CFTUTIL/Parameter_index/part.htm)
= identifier   

\[ [ACKEXEC](CFTUTIL/Parameter_index/ackexec.htm) = filename\]

\[ [APPCYCID](CFTUTIL/Parameter_index/appcycid.htm)
= string \]

\[ [APPOBJID](CFTUTIL/Parameter_index/appobjid.htm)
= string \]

\[ [COMMENT](CFTUTIL/Parameter_index/comment.htm)
= string  \]

\[ [CYCDATE](CFTUTIL/Parameter_index/cycdate.htm)
=  date
 \]

\[ [CYCLE](CFTUTIL/Parameter_index/cycle.htm)
=  { 0
| n } \]

\[ [CYCTIME](CFTUTIL/Parameter_index/cyctime.htm)
= time \]

\[ [DACTION](CFTUTIL/Parameter_index/daction.htm) = { <u>ERROR</u> | RESUME } \]

\[ [DIRNB](CFTUTIL/Parameter_index/dirnb.htm)
= n \]

\[ [EXEC](CFTUTIL/Parameter_index/exec.htm)
= filename \]

\[ EXECRALL = { <u>all</u> | parent| children} \]

\[ [EXIT](CFTUTIL/Parameter_index/exit.htm)
= identifier  \]

\[ [FACC](CFTUTIL/Parameter_index/facc.htm)
= { ‘
‘ | character }  \]

\[ [FACTION](CFTUTIL/Parameter_index/faction.htm)
= { ‘
‘ | DELETE | ERASE | RENAME | VERIFY } \]

\[ [FBLKSIZE](CFTUTIL/Parameter_index/fblksize.htm)
= n \]

\[ [FCODE](CFTUTIL/Parameter_index/fcode.htm)
= { BINARY | EBCDIC | ASCII } \]

\[ [FCOMP](CFTUTIL/Parameter_index/fcomp.htm)
= { 0
| 15 } \]

\[ [FDATE](CFTUTIL/Parameter_index/fdate.htm)
= { 0
| date } \]

\[ FDB
= filename \]

\[ [FDISP](CFTUTIL/Parameter_index/fdisp.htm)
= { BOTH
| NEW | OLD }  \]

\[ [FILE](CFTUTIL/Parameter_index/file.htm)
= { FIRST
| ALL }  \]

\[ [FKEYLEN](CFTUTIL/Parameter_index/fkeylen.htm)
= { 0
| n }  \]

\[ [FKEYPOS](CFTUTIL/Parameter_index/fkeypos.htm)
= { 0
| n }   \]

\[ [FLRECL](CFTUTIL/Parameter_index/flrec.htm)
= n \]

\[ [FNAME](CFTUTIL/Parameter_index/fname.htm)
= filename \]

\[ [FORG](CFTUTIL/Parameter_index/forg.htm)
= { SEQ
| DIRECT | INDEXED | PART } \]

\[ [FPAD](CFTUTIL/Parameter_index/fpad.htm) = { <u>' '</u> | character } \]

\[ [FRECFM](CFTUTIL/Parameter_index/frecfm.htm)
= { ‘
‘ | F | V | U }  \]

\[ [FSPACE](CFTUTIL/Parameter_index/fspace.htm)
= n \]

\[ [FTIME](CFTUTIL/Parameter_index/ftime.htm)
= { 0 | time } \]

\[ [FTYPE](CFTUTIL/Parameter_index/ftype.htm)
=  { ‘
‘ | character } \]

\[ [IDA](CFTUTIL/Parameter_index/ida.htm)
= identifier \]

\[ [MACTION](CFTUTIL/Parameter_index/maction.htm)
= { '
' | REPLACE }  \]

\[ [MAXDATE](CFTUTIL/Parameter_index/maxdate.htm)
=  { 99991231
| date } \]

\[ MAXDURATION = ** **{<u>0</u>...32767} \]

\[ [MAXTIME](CFTUTIL/Parameter_index/maxtime.htm)
= { 23595999
| time }  \]

\[ [MINDATE](CFTUTIL/Parameter_index/mindate.htm)
= { current system date | date } \]

\[ [MINTIME](CFTUTIL/Parameter_index/mintime.htm)
= { 0
| time } \]

\[ [MODE](CFTUTIL/Parameter_index/mode.htm)
= { REPLACE
| CREATE | DELETE }  \]

\[ [NCOMP](CFTUTIL/Parameter_index/ncomp.htm)
= { 0
| 15 } \]

\[ [NETBAND](CFTUTIL/Parameter_index/netband.htm) = { 1...16} \]

\[ [NFNAME](CFTUTIL/Parameter_index/nfname.htm)
= filename \]

\[ [NFVER](CFTUTIL/Parameter_index/nfver.htm)
=  { 0
| 255 } \]

\[ [NIDF](CFTUTIL/Parameter_index/nidf.htm)
= string \]

\[ [NPAD](CFTUTIL/Parameter_index/npad.htm) = { <u>' '</u> | character } \]

\[ [PARM](CFTUTIL/Parameter_index/parm.htm)
= string \]

\[ [PRI](CFTUTIL/Parameter_index/pri.htm)
= { 128
| n } \]

\[ [PROT](CFTUTIL/Parameter_index/prot.htm) = identifier \]

\[ [RAPPL](CFTUTIL/Parameter_index/rappl.htm)
= string \]

\[ [RUSER](CFTUTIL/Parameter_index/ruser.htm)
= string \]

\[ [SAPPL](CFTUTIL/Parameter_index/sappl.htm)
= string \]

\[ [SERIAL](CFTUTIL/Parameter_index/serial.htm) = { <u>' '</u> | Y | Z | X } \]

\[ [STATE](CFTUTIL/Parameter_index/state.htm)
= { DISP
| HOLD | KEEP } \]

\[ [SUSER](CFTUTIL/Parameter_index/suser.htm)
= string \]

\[ [TCYCLE](CFTUTIL/Parameter_index/tcycle.htm)
= { DAY
| MIN | MONTH }  \]

\[ [TRK](CFTUTIL/Parameter_index/trk.htm)
= { UNDEFINED
| ALL | SUMMARY | NO } \]

\[ [WFNAME](CFTUTIL/Parameter_index/wfname.htm)
= filename \]

\[ [WORKINGDIR](CFTUTIL/Parameter_index/workingdir.htm) = string \]

\[ WSTATES = { string } \]

\[ WTIMEOUT = { integer } \]

\[ [XLATE](CFTUTIL/Parameter_index/xlate.htm)
= identifier \]

[Receiving files](Transfers/Recv_transfers/c_recv.htm)

#### <span id="RESUME"></span>RESUME: Retrieves, in server mode, a blocked send request

Syntax

[PART](CFTUTIL/Parameter_index/part.htm)
= string

\[ [DIRECT](CFTUTIL/Parameter_index/direct.htm)
= { SEND |RECV | BOTH
} \]

\[ [BLKNUM](CFTUTIL/Parameter_index/blknum.htm)
= { 0
| n } \]

\[ [FORCE](CFTUTIL/Parameter_index/force.htm)
= { NO
| YES } \]

\[ [IDA](CFTUTIL/Parameter_index/ida.htm)
= string \]

\[ [IDF](CFTUTIL/Parameter_index/idf.htm)
= string \]

\[ [IDT](CFTUTIL/Parameter_index/idu.htm)
= string \]

\[ [IDTU](CFTUTIL/Parameter_index/idtu.htm)
= string \]

\[ [STATE](CFTUTIL/Parameter_index/state.htm) = string \]

\[ KDATE
= { 0
| n } \]

\[ KTIME
= { 0
| n } \]

\[ PHASE = string \]

\[ PHASESTEP = string \]

\[ [SCOPE](CFTUTIL/Parameter_index/scope.htm) = string \]

[RESUME details](Transfers/Subm_transfers/RESUME_command.htm)

 

#### <span id="SEND"></span>SEND: Request to send transfer

[<img src="/Images/TransferCFT/transparent.gif" width="16" height="11" alt="Closed" />Syntax](javascript:void(0))

[TYPE](CFTUTIL/Parameter_index/type.htm)
= FILE

[IDF](CFTUTIL/Parameter_index/idf.htm)
= identifier  

[PART](CFTUTIL/Parameter_index/part.htm)
= identifier

\[ [ACKEXEC](CFTUTIL/Parameter_index/ackexec.htm) = filename\]

\[ ACKMINDATE = date \]

\[ ACKMINTIME = time \]

\[ ACKSTATE = { REQUIRE | IGNORE } \]

\[ ACKTIMEOUT = { 0 | n }
\]

\[ [APPCYCID](CFTUTIL/Parameter_index/appcycid.htm)
= string \]

\[ [APPOBJID](CFTUTIL/Parameter_index/appobjid.htm)
= string \]

\[ ARCHIVEFNAME = string \]

\[ [COMMENT](CFTUTIL/Parameter_index/comment.htm)
= string \]

\[ [CYCDATE](CFTUTIL/Parameter_index/cycdate.htm)
= date \]

\[ [CYCLE](CFTUTIL/Parameter_index/cycle.htm)
= { 0
| n }  \]

\[ [CYCTIME](CFTUTIL/Parameter_index/cyctime.htm)
= time \]

\[ [DACTION](CFTUTIL/Parameter_index/daction.htm) = { <u>ERROR</u> | RESUME } \]

\[ [EXEC](CFTUTIL/Parameter_index/exec.htm)
= filename \]

\[ [EXECSUB](CFTUTIL/Parameter_index/execsub.htm)
= { LIST
| FILE | SUBF } \]

\[ [EXECSUBA](CFTUTIL/Parameter_index/execsuba.htm) = {LIST | FILE | <u>SUBF</u> }\]

\[ [EXIT](CFTUTIL/Parameter_index/exit.htm)
= identifier  \]

\[ [FACC](CFTUTIL/Parameter_index/facc.htm)
= { ‘ ‘ | character } \]

\[ [FACTION](CFTUTIL/Parameter_index/faction.htm)
= { NONE
| DELETE | ERASE | ARCHIVE } \]

\[ [FBLKSIZE](CFTUTIL/Parameter_index/fblksize.htm)
= n \]

\[ [FCODE](CFTUTIL/Parameter_index/fcode.htm)
= { ASCII | BINARY | EBCDIC } \]

\[ [FDATE](CFTUTIL/Parameter_index/fdate.htm)
= date \]

\[ FDB
= filename \]

\[ [FDISP](CFTUTIL/Parameter_index/fdisp.htm)
= { SHR
| OLD | CHECK } \]

\[ [FILTER](CFTUTIL/Parameter_index/filter.htm) = string \]

\[ [FILTERTYPE](CFTUTIL/Parameter_index/filtertype.htm) = string \]

\[ [FKEYLEN](CFTUTIL/Parameter_index/fkeylen.htm)
= { 0
| n } \]

\[ [FKEYPOS](CFTUTIL/Parameter_index/fkeypos.htm)
= { 0
| n } \]

\[ [FLRECL](CFTUTIL/Parameter_index/flrec.htm)
= n \]

\[ [FNAME](CFTUTIL/Parameter_index/fname.htm)
 = { filename
| mask | dirname | #filename | #mask | #dirname } \]

\[ FNAMEABS
= { YES | NO }  \]

\[ [FORG](CFTUTIL/Parameter_index/forg.htm)
= { SEQ
| DIRECT | INDEXED } \]

\[ [FPAD](CFTUTIL/Parameter_index/fpad.htm) = { <u>' '</u> | character } \]

\[ [FRECFM](CFTUTIL/Parameter_index/frecfm.htm)
= { ‘ ‘ | F | U | V }  \]

\[ [FSPACE](CFTUTIL/Parameter_index/fspace.htm)
= n \]

\[ [FTIME](CFTUTIL/Parameter_index/ftime.htm)
= time  \]

\[ [FTYPE](CFTUTIL/Parameter_index/ftype.htm)
=  { ‘ ‘
| character } \]

\[ [IDA](CFTUTIL/Parameter_index/ida.htm)
= identifier \]

\[ [IPART](CFTUTIL/Parameter_index/ipart.htm)
= identifier \]

\[ [MAXDATE](CFTUTIL/Parameter_index/maxdate.htm)
= { 99991231
| date } \]

\[ [MAXTIME](CFTUTIL/Parameter_index/maxtime.htm)
= { 23595999
| time } \]

\[ [MINDATE](CFTUTIL/Parameter_index/mindate.htm)
= { current
system date | date } \]

\[ MAXDURATION = ** **<u>0</u>...32767} \]

\[ [MINTIME](CFTUTIL/Parameter_index/mintime.htm)
= { 0
| time } \]

\[ [NBLKSIZE](CFTUTIL/Parameter_index/nblksize.htm)
= n \]

\[ [NCODE](CFTUTIL/Parameter_index/ncode.htm)
= { ASCII | BINARY | EBCDIC } \]

\[ [NCOMP](CFTUTIL/Parameter_index/ncomp.htm)
= { 0 | 15 } \]

\[ [NETBAND](CFTUTIL/Parameter_index/netband.htm)
= { 1...16} \]

\[ [NFNAME](CFTUTIL/Parameter_index/nfname.htm)
= filename \]

\[ [NIDF](CFTUTIL/Parameter_index/nidf.htm)
= string \]

\[ [NKEYLEN](CFTUTIL/Parameter_index/nkeylen.htm)
= { 0
| n } \]

\[ [NKEYPOS](CFTUTIL/Parameter_index/nkeypos.htm)
= { 0
| n }\]

\[ [NLRECL](CFTUTIL/Parameter_index/nlrecl.htm)
= n  \]

\[ [NPAD](CFTUTIL/Parameter_index/npad.htm) = { <u>' '</u> | character } \]

\[ [NRECFM](CFTUTIL/Parameter_index/nrecfm.htm)
= { ‘
‘ | F | U | V } \]

\[ [NSPACE](CFTUTIL/Parameter_index/nspace.htm)
= { FSPACE
value | n } \]

\[ [NTYPE](CFTUTIL/Parameter_index/ntype.htm)
= { ' ' | character } \]

\[ [PARM](CFTUTIL/Parameter_index/parm.htm)
= string \]

\[ [PRESTATE](CFTUTIL/Parameter_index/prestate.htm) = { ' ' | character } \]

\[ [PREMINDATE](CFTUTIL/Parameter_index/premindate.htm) = date \]

\[ [PREMINTIME](CFTUTIL/Parameter_index/premintime.htm) = time \]

\[ [PRETIMEOUT](CFTUTIL/Parameter_index/pretimeout.htm) = { 0 | n } \]

\[ [POSTMINDATE](CFTUTIL/Parameter_index/postmindate.htm) = date \]

\[ [POSTMINTIME](CFTUTIL/Parameter_index/postmintime.htm) = time \]

\[ [PRI](CFTUTIL/Parameter_index/pri.htm)
= { 128
| n } \]

\[ [PROT](CFTUTIL/Parameter_index/prot.htm) = identifier \]

\[ [RAPPL](CFTUTIL/Parameter_index/rappl.htm)
= string \]

\[ [RUSER](CFTUTIL/Parameter_index/ruser.htm)
= string \]

\[ [SAPPL](CFTUTIL/Parameter_index/sappl.htm)
= string \]

\[ [SELFNAME](CFTUTIL/Parameter_index/selfname.htm)
 = filename
\]

\[ [SERIAL](CFTUTIL/Parameter_index/serial.htm) = { <u>' '</u> | Y | Z | X } \]

\[ [SPART](CFTUTIL/Parameter_index/spart.htm)
= identifier \]

\[ [STATE](CFTUTIL/Parameter_index/state.htm)
= { DISP
| HOLD | KEEP } \]

\[ [SUSER](CFTUTIL/Parameter_index/suser.htm)
= string \]

\[ [TCYCLE](CFTUTIL/Parameter_index/tcycle.htm)
= { DAY
| MIN | MONTH } \]

\[ [TRK](CFTUTIL/Parameter_index/trk.htm)
= { UNDEFINED
| ALL | SUMMARY | NO } \]

\[ [WORKINGDIR](CFTUTIL/Parameter_index/workingdir.htm) = string \]

\[ WPHASES = { string } \]

\[ WPHASESTEPS = { string } \]

\[ WSTATES = { string } \]

\[ WTIMEOUT = { integer } \]

\[ [XLATE](CFTUTIL/Parameter_index/xlate.htm)
= identifier \]

 

SEND TYPE = MESSAGE  

[IDM](CFTUTIL/Parameter_index/idm.htm)
= identifier  

[MSG](CFTUTIL/Parameter_index/msg.htm)
= string   

[PART](CFTUTIL/Parameter_index/part.htm)
= identifier

\[ [APPCYCID](CFTUTIL/Parameter_index/appcycid.htm)
= string \]

\[ [APPOBJID](CFTUTIL/Parameter_index/appobjid.htm)
= string \]

\[ [CYCDATE](CFTUTIL/Parameter_index/cycdate.htm)
= date \]

\[ [CYCLE](CFTUTIL/Parameter_index/cycle.htm)
= { 0
| n } \]

\[ [CYCTIME](CFTUTIL/Parameter_index/cyctime.htm)
= time \]

\[ [DACTION](CFTUTIL/Parameter_index/daction.htm) = { ERROR | RESUME} \]

\[ [EXEC](CFTUTIL/Parameter_index/exec.htm)
= filename \]

\[ [IDA](CFTUTIL/Parameter_index/ida.htm)
= identifier \]

\[ [IPART](CFTUTIL/Parameter_index/ipart.htm)
= identifier \]

\[ [MAXDATE](CFTUTIL/Parameter_index/maxdate.htm)
= { 99991231
| date  }
\]

\[ [MAXTIME](CFTUTIL/Parameter_index/maxtime.htm)
= { 23595999
| time }  \]

\[ [MINDATE](CFTUTIL/Parameter_index/mindate.htm)
= { current
system date | date } \]

\[ [MINTIME](CFTUTIL/Parameter_index/mintime.htm)
= { 0
| time } \]

\[ [PRI](CFTUTIL/Parameter_index/pri.htm)
= pri  \]

\[ [PROT](CFTUTIL/Parameter_index/prot.htm) = identifier \]

\[ [RAPPL](CFTUTIL/Parameter_index/rappl.htm)
= string \]

\[ [RUSER](CFTUTIL/Parameter_index/ruser.htm)
= string \]

\[ [SAPPL](CFTUTIL/Parameter_index/sappl.htm)
= string \]

\[ [SPART](CFTUTIL/Parameter_index/spart.htm)
= identifier \]

\[ [STATE](CFTUTIL/Parameter_index/state.htm)
= { DISP
| HOLD | KEEP } \]

\[ [SUSER](CFTUTIL/Parameter_index/suser.htm)
= string \]

\[ [TCYCLE](CFTUTIL/Parameter_index/tcycle.htm)
= { DAY
| MIN | MONTH } \]

\[ [TRK](CFTUTIL/Parameter_index/trk.htm)
= { UNDEFINED
| ALL | SUMMARY | NO } \]

 

SEND TYPE = REPLY

[IDM](CFTUTIL/Parameter_index/idm.htm)
= identifier

[IDT](CFTUTIL/Parameter_index/idu.htm)
= transid  

[MSG](CFTUTIL/Parameter_index/msg.htm)
= string   

[PART](CFTUTIL/Parameter_index/part.htm)
= identifier

\[ [APPCYCID](CFTUTIL/Parameter_index/appcycid.htm)
= string \]

\[ [APPOBJID](CFTUTIL/Parameter_index/appobjid.htm)
= string \]

\[ [CYCDATE](CFTUTIL/Parameter_index/cycdate.htm)
= date \]

\[ [CYCTIME](CFTUTIL/Parameter_index/cyctime.htm)
= time \]

\[ [EXEC](CFTUTIL/Parameter_index/exec.htm) = filename \]

\[ [IDA](CFTUTIL/Parameter_index/ida.htm) = identifier \]

\[ [IPART](CFTUTIL/Parameter_index/ipart.htm)
= string \]

\[ [MAXDATE](CFTUTIL/Parameter_index/maxdate.htm)
=  { 99991231
| date } \]

\[ [MAXTIME](CFTUTIL/Parameter_index/maxtime.htm)
= { 23595999
| time } \]

\[ [MINDATE](CFTUTIL/Parameter_index/mindate.htm)
= { current
system date | date } \]

\[ [MINTIME](CFTUTIL/Parameter_index/mintime.htm)
= { 0
| time } \]

\[ [PRI](CFTUTIL/Parameter_index/pri.htm)
= pri \]

\[ [PROT](CFTUTIL/Parameter_index/prot.htm) = identifier \]

\[ [RAPPL](CFTUTIL/Parameter_index/rappl.htm)
= string \]

\[ [RUSER](CFTUTIL/Parameter_index/ruser.htm)
= string \]

\[ [SAPPL](CFTUTIL/Parameter_index/sappl.htm)
= string \]

\[ [SUSER](CFTUTIL/Parameter_index/suser.htm)
= string \]

\[ [TCYCLE](CFTUTIL/Parameter_index/tcycle.htm)
= { DAY
| MIN | MONTH } \]

\[ [TRK](CFTUTIL/Parameter_index/trk.htm)
= { UNDEFINED
| ALL | SUMMARY | NO } \]

 

SEND TYPE = NACK

[IDM](CFTUTIL/Parameter_index/idm.htm)
= identifier

[IDT](CFTUTIL/Parameter_index/idu.htm)
= transid  

[MSG](CFTUTIL/Parameter_index/msg.htm)
= string   

[PART](CFTUTIL/Parameter_index/part.htm)
= identifier

\[ [APPCYCID](CFTUTIL/Parameter_index/appcycid.htm)
= string \]

\[ [APPOBJID](CFTUTIL/Parameter_index/appobjid.htm)
= string \]

\[ [CYCDATE](CFTUTIL/Parameter_index/cycdate.htm)
= date \]

\[ [CYCTIME](CFTUTIL/Parameter_index/cyctime.htm)
= time \]

\[ [EXEC](CFTUTIL/Parameter_index/exec.htm) = filename \]

\[ [IDA](CFTUTIL/Parameter_index/ida.htm) = identifier \]

\[ [IPART](CFTUTIL/Parameter_index/ipart.htm)
= string \]

\[ [MAXDATE](CFTUTIL/Parameter_index/maxdate.htm)
=  { 99991231
| date } \]

\[ [MAXTIME](CFTUTIL/Parameter_index/maxtime.htm)
= { 23595999
| time } \]

\[ [MINDATE](CFTUTIL/Parameter_index/mindate.htm)
= { current
system date | date } \]

\[ [MINTIME](CFTUTIL/Parameter_index/mintime.htm)
= { 0
| time } \]

\[ [PRI](CFTUTIL/Parameter_index/pri.htm)
= pri \]

\[ [PROT](CFTUTIL/Parameter_index/prot.htm) = identifier \]

\[ [RAPPL](CFTUTIL/Parameter_index/rappl.htm)
= string \]

\[ [RUSER](CFTUTIL/Parameter_index/ruser.htm)
= string \]

\[ [SAPPL](CFTUTIL/Parameter_index/sappl.htm)
= string \]

\[ [SUSER](CFTUTIL/Parameter_index/suser.htm)
= string \]

\[ [TCYCLE](CFTUTIL/Parameter_index/tcycle.htm)
= { DAY
| MIN | MONTH } \]

\[ [TRK](CFTUTIL/Parameter_index/trk.htm)
= { UNDEFINED
| ALL | SUMMARY | NO } \]

[Sending files](Transfers/Subm_transfers/SEND_command_basics.htm)

#### <span id="SHUT"></span>SHUT: Shut down Transfer CFT 

Syntax

\[ [FAST](CFTUTIL/Parameter_index/fast.htm)
= { NO
| YES | KILL } \]

\[ [RESTART](CFTUTIL/Parameter_index/restart.htm) = { YES | NO } \]

[Manage the Transfer CFT server: stop the server](../admin_intro/start_stop_cft)

#### <span id="START"></span>START: Restart transfer

Syntax

[PART](CFTUTIL/Parameter_index/part.htm)
= { identifier | mask }   

\[ [BLKNUM](CFTUTIL/Parameter_index/blknum.htm)
= { 0
| n } \]

\[ [DIRECT](CFTUTIL/Parameter_index/direct.htm)
= { BOTH
| RECV | SEND } \]

\[ [FORCE](CFTUTIL/Parameter_index/force.htm)
= YES | NO
\]

\[ [IDA](CFTUTIL/Parameter_index/ida.htm)
= identifier \]

\[ [IDF](CFTUTIL/Parameter_index/idf.htm)
= identifier \]

\[ [IDT](CFTUTIL/Parameter_index/idu.htm)
= { \*
| transid } \]

\[ [IDTU](CFTUTIL/Parameter_index/idtu.htm)
= string \]

\[ MAXDURATION = ** **{<u>0</u>...32767} \]

\[ [STATE](CFTUTIL/Parameter_index/state.htm) = string \]

\[ KDATE
= { 0
| n } \]

\[ KTIME
= { 0
| n } \]

\[ PHASE = string \]

\[ PHASESTEP = string \]

\[ [SCOPE](CFTUTIL/Parameter_index/scope.htm) = string \]

[Restart transfers](Transfers/Transfer_states/START_command.htm)

#### <span id="SUBMIT"></span>SUBMIT: Submit end-of-transfer procedure

Syntax

[PART](CFTUTIL/Parameter_index/part.htm)
= { identifier | mask }  

\[ APPSTATE =
string \]

\[ [BLKNUM](CFTUTIL/Parameter_index/blknum.htm)
= { 0
| n } \]

\[ [DIRECT](CFTUTIL/Parameter_index/direct.htm)
= { BOTH
| RECV | SEND } \]

\[ [EXEC](CFTUTIL/Parameter_index/exec.htm)
= filename \]

\[ [IDA](CFTUTIL/Parameter_index/ida.htm)
= identifier \]

\[ [IDF](CFTUTIL/Parameter_index/idf.htm)
= identifier \]

\[ [IDT](CFTUTIL/Parameter_index/idu.htm)
= { \* | transid } \]

\[ [IDTU](CFTUTIL/Parameter_index/idtu.htm)
= string \]

\[ [STATE](CFTUTIL/Parameter_index/state.htm) = string \]

\[ KDATE
= { 0
| n } \]

\[ KTIME
= { 0
| n } \]

\[ PHASE = string \]

\[ PHASESTEP = string \]

[SUBMIT details](Transfers/Transfer_states/SUBMIT_command.htm)

#### <span id="SWAITCAT"></span>SWAITCAT: Wait for a transfer state update

Syntax

[SELECT](CFTUTIL/Parameter_index/select.htm)
= expression

\[ [PHASES](CFTUTIL/Parameter_index/phases.htm)  = string \]

\[ [PHASESTEPS](CFTUTIL/Parameter_index/phasesteps.htm) = string \]

\[ STATED = string \]

\[ [STATES](CFTUTIL/Parameter_index/states.htm)
= string \]

\[ [TIMEOUT](CFTUTIL/Parameter_index/timeout.htm)
= integer \]

[SWAITCAT concepts](CFTUTIL/Admin/SWAITCAT_concepts.htm) 

[SWAITCAT examples](CFTUTIL/Admin/Sync_transfer_request_tasks.htm)

#### <span id="SWITCH"></span>SWITCH: Manually switch LOG or ACCNT files 

Syntax

\[ [TYPE](CFTUTIL/Parameter_index/type.htm)
= { LOG | ACCNT } \]

[SWITCH details](CFTUTIL/Monitoring/Switching_files_manually.htm)

Toggle
log or accounting file

#### <span id="UCONFSET"></span>UCONFSET: configuration utility

Syntax

[ID](CFTUTIL/Parameter_index/id.htm)
= string  

\[ [VALUE](CFTUTIL/Parameter_index/value.htm)
= {string} \]

[UCONF details](administration/admin_uconf/uconf_commands.htm)

#### <span id="UCONFGET"></span>UCONFGET

Syntax

[ID](CFTUTIL/Parameter_index/id.htm)
= string

[UCONF details](administration/admin_uconf/uconf_commands.htm)

#### <span id="LISTUCONF"></span>LISTUCONF

Syntax

[ID](CFTUTIL/Parameter_index/id.htm)
= string  

\[ [CONTENT](CFTUTIL/Parameter_index/content.htm) = BRIEF | FULL \]

\[ [FOUT](CFTUTIL/Parameter_index/fout.htm) = string \]

\[ [SCOPE](CFTUTIL/Parameter_index/scope.htm)
= { INSTANCE | SET | \* | ALL } \]  

\[ [VALUE](CFTUTIL/Parameter_index/value.htm) = string \]

[](administration/admin_uconf/uconf_commands.htm)

UCONF details

#### <span id="WAIT"></span>WAIT: Suspend CFTUTIL execution for the time indicated 

Syntax

\[ [DURING](CFTUTIL/Parameter_index/during.htm)
= { 0
| n } \]    \*Time
in seconds

\[ [TIME](CFTUTIL/Parameter_index/time.htm)
= { 0
| 23595999 } \]

[Suspending CFTUTIL execution](CFTUTIL/WAIT_command.htm)

#### <span id="WLOG"></span>WLOG: Request to write a message in the LOG file

Syntax

[MSG](CFTUTIL/Parameter_index/msg.htm)
= string

SEVERITY =
string

[WLOG details](CFTUTIL/Monitoring/WLOG.htm)

### <span id="Syntax_conventions"></span>Syntax conventions

The command syntax presented in this summary respects the following
general conventions.

1.  Mandatory parameters are placed
    before optional parameters.
2.  The default value of a parameter
    is placed before the other possible values in the list for this parameter.

### Typographic conventions

-   \[   \]
    Optional parameters or values are displayed between square brackets
-   {   }
    Parameter choices or values are displayed  between
    braces
-   | The vertical
    bar separates an enumerated list of parameter values
-   \_\_\_ Default values
    for a parameter are underlined
-   , A comma separates
    a list of parameter values

For more information, see [TYPOGRAPHICAL CONVENTIONS.](CFTUTIL/Parameter_index/typographical_conventions.htm)

### Symbolic variables

The following symbolic variable syntaxes are valid in a Transfer CFT
environment:

-   &VAR
-   &+VAR
-   &nVAR:
-   &p.VAR
-   &p.nVAR
-   &(-string\_prefix)
    (+string\_suffix)
    (=string\_alternate)p.nVAR

For information on using symbolic variables in Transfer
CFT, refer to the topic [Symbolic
variables](CFTUTIL/Parameter_index/symbolic_variables.htm).

### Filename usage

This name is a complete physical filename. It can
be either:

-   Created dynamically
    from symbolic variables, or
-   Correspond to the
    name of a version file

#### Using the FNAME parameter

Filename conventions are as follows:

-   filename

Transfers a file for which the name is specified by
a filename.

-   mask

The term mask means that the filename includes at
least one wild card character (\* or :). This sends a file that lists all
files that match the mask.

-   dirname

Sends a file that lists the contents of the directory.

-   #filename

For each file name that is listed in the file, this
sends the corresponding file.

-   #mask

For each file name that matches the mask, this sends
the corresponding file.

-   #dirname

For each file that exists in the directory, this sends
the corresponding file.

Note: Use the @ symbol in a UNIX environment in place
of the # symbol.

For more information on filename conventions, refer
to [Filename conventions](CFTUTIL/Parameter_index/Filename_conventions.htm).

## <span id="About_UCONF"></span>Using UCONF

In order to merge functioning for all platforms, Transfer CFT features a configuration interface that provides product uniformity
regardless of platform differences.

The basic CFTUTIL services provided are:

-   UCONFSET id=\*\*\*\*,value=\*\*\*\*
-   UCONFGET id=\*\*\*\*
-   LISTUCONF id=\*\*\*\*

This configuration replaces all prior configuring methods, such as manually
editing cft.ini, ENV\_CFT, \*.ini, trkapi.conf, and so on, which have been
replaced by a global profile file.

Additionally, UCONF can create all OS specific files that enable Transfer
CFT User Interface operations.

Accepted types include:

-   int lower/higher
           
-   bool true/false
              
-   enum (id1 id2 id3
    id4)  
-   identifier      
-   string                        
-   path (with abstract
    use of / \\) escaped by \\ :::: “/dsqfhdj”
-   fname

The ‘$’ sign is a reserved character that is used to reference an environmental
variable. You have abstract use of environment variables using the $ sign.

For example: $(CFT\_INSTALL) -à getenv(“CFT\_INSTALL”)

Variables containing a period “.” refer to sections in the configuration
file. Do not modify this file.

For example: cft.working\_dir = $(cft.runtime\_dir)

The [UCONF](uconf/UCONF.htm) table lists the new UCONF
identifiers, the default values, and the former file values.
