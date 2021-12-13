{
    "title": "Transfer CFT command guide and syntax ",
    "linkTitle": "Command guide and parameters",
    "weight": "130"
}This topic provides a useful list of  {{< TransferCFT/componentshortname  >}} commands,
syntax, and parameters. For a more detailed description of the Transfer
CFT commands, refer to the link displayed below each  command
syntax.

The  {{< TransferCFT/componentshortname  >}} commands are presented in alphabetical order in this
summary. Each
command is presented with possible parameters and default values.

See also, [Syntax
conventions and symbolic variables.](#Syntax_conventions)

<span id="ABOUT"></span>

#### ABOUT: Displays product/host information

Syntax

\[ [COMMENT](parameter_intro/comment)
= string \]

\[ [TYPE](parameter_intro/type)
= {
| HOST | CFT } \]

\[ [KEY](parameter_intro/key) = { <u>FIRST</u> | ALL } \]

[ABOUT details](../about_cftutil/about_command)

<span id="ACT"></span>

#### ACT: Reactivates a partner

Syntax

ID = identifier

\[ [TYPE](parameter_intro/type)
= {
| TRK | CRON | FOLDER } \]

\[ [MODE](parameter_intro/mode)
= {
| REQUESTER|
SERVER } \]

[ACT details](../about_cftutil/reactivate_an_object_cl)

<span id="CFTACCNT"></span>

#### CFTACCNT: Defines transfer accounting records

Syntax

CFTACCNT TYPE = FILE

[TYPE](parameter_intro/type)
= FILE

[FNAME](parameter_intro/fname)
= filename

[ID](parameter_intro/id)
= identifier

\[ [AFNAME](parameter_intro/afname)
= filename \]

\[ [COMMENT](parameter_intro/comment)
= string \]

\[ [EXEC](parameter_intro/exec)
= filename \]

\[ [LANGUAGE](parameter_intro/language)
= {
| C } \]

\[ [MAXREC](parameter_intro/maxrec)
= {
| n } \]

\[ [MODE](parameter_intro/mode)
= {
| CREATE | DELETE } \]

\[ [SWITCH](parameter_intro/switch)
= {
| time } \]

\[ [FORMAT](parameter_intro/format)
= {
| 23 | V24 | 24} \]

 

CFTACCNT TYPE = SYST

[TYPE](parameter_intro/type)
= SYST

[ACCID](parameter_intro/accid)
= n

[ID](parameter_intro/id)
= identifier

\[ [COMMENT](parameter_intro/comment)
= string \]

\[ [FORMAT](parameter_intro/format)
= {
| 23 | V24 | 24} \]

\[ [LANGUAGE](parameter_intro/language)
= {
| C } \]

\[ [MODE](parameter_intro/mode)
= {
| CREATE | DELETE } \]

[CFTACCNT details](../web_copilot_ui/conf_intro/cftaccnt)

[Transfer
accounting records](../../admin_intro/admin_config_commands/cftaccnt_concepts)

<span id="CFTAPPL"></span>

#### CFTAPPL: Defines a transfer owner

Syntax

CFTAPPL
MODE = REPLACE

[ID](parameter_intro/id)
= identifier

[USERID](parameter_intro/userid)
= string

\[ [COMMENT](parameter_intro/comment)
= string \]

\[ [GROUPID](parameter_intro/groupid)
= string \]

\[ [MODE](parameter_intro/mode)
= {
| CREATE | DELETE } \]

CFTAPPL MODE = DELETE

[ID](parameter_intro/id)
= identifier

[USERID](parameter_intro/userid)
= string

[DIRECT](parameter_intro/direct)
= {
|  SEND
| RECV }

\[ [COMMENT](parameter_intro/comment)
= string \]

\[ [GROUPID](parameter_intro/groupid)
= string \]

\[ [MODE](parameter_intro/mode)
= {
| CREATE | DELETE } \]

[CFTAPPL details](../web_copilot_ui/flow_def_intro/cftappl)

Assign a transfer owner

#### CFTAUTH: Defines an Authorized Flow Definition list

Syntax

FNAME = filename

[ID](parameter_intro/id) =

\[ [COMMENT](parameter_intro/comment)
= string \]

\[ [MODE](parameter_intro/mode)
= {
| CREATE | DELETE } \]

 

Or

 

IDF = (identifier | mask, identifier | mask, …)

[ID](parameter_intro/id) =

\[ [COMMENT](parameter_intro/comment)
= string \]

\[ [MODE](parameter_intro/mode)
= {
| CREATE | DELETE } \]

** **

<span id="CFTCAT"></span>

#### CFTCAT: Defines Catalog attributes

Syntax

[FNAME](parameter_intro/fname)
= filename

[ID](parameter_intro/id)
= identifier  

\[ [COMMENT](parameter_intro/comment)
= string \]

\[ [MODE](parameter_intro/mode)
= { <span style="text-decoration: underline;">REPLACE</span>
| CREATE | DELETE } \]

\[ [RH](parameter_intro/rh)
= { <span style="text-decoration: underline;">10</span>
| n }  \]

\[ [RKERROR](parameter_intro/rkerror)
= { <span style="text-decoration: underline;">KEEP</span>
| DELETE } \]

\[ [RT](parameter_intro/rt)
= { <span style="text-decoration: underline;">10</span>
| n } \]

\[ [RX](parameter_intro/rx)
= { <span style="text-decoration: underline;">10</span>
| n } \]

\[ [SH](parameter_intro/sh)
= { <span style="text-decoration: underline;">10</span>
| n } \]

\[ [ST](parameter_intro/st)
= { <span style="text-decoration: underline;">10</span>
| n } \]

\[ [SX](parameter_intro/sx)
= { <span style="text-decoration: underline;">10</span>
| n } \]

\[ [TIMEP](parameter_intro/timep)
= { <span style="text-decoration: underline;">23595999</span>
| HHMMSSCC } \]

\[ [TLVCEXEC](parameter_intro/tlvcexec)
= { n } \]

\[ [TLVCLEAR](parameter_intro/tlvclear)
= { <u>TLVWARN-10</u> | n } \]

\[ [TLVWEXEC](parameter_intro/tlvwexec)
= { n } \]

\[ [TLVWRATE](parameter_intro/tlvwrate)
= { 60 | n } \]

\[ [TLVWARN](parameter_intro/tlvwarn)
= { 80 | n } \]

\[ [UPDAT](parameter_intro/updat)
= { <span style="text-decoration: underline;">256</span>
| n } \]

\[ [WSCAN](parameter_intro/wscan)
= { <span style="text-decoration: underline;">5</span>
| n } \]

[CFTCAT details](../web_copilot_ui/conf_intro/cftcat)

[Catalog attributes](../../admin_intro/admin_config_commands/catalog_parameter_concepts)

<span id="CFTCOM"></span>

#### CFTCOM: Defines parameters related to the communication between applications and  <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>

Syntax

#### CFTCOM TYPE = FILE

[TYPE](parameter_intro/type)
= FILE

[ID](parameter_intro/id)
= identifier

[NAME](parameter_intro/name)
= filename  

\[ [COMMENT](parameter_intro/comment)
=  string
\]

\[ [MODE](parameter_intro/mode)
= { REPLACE | CREATE | DELETE } \]

\[ [TLVCEXEC](parameter_intro/tlvcexec)
= { n } \]

\[ [TLVCLEAR](parameter_intro/tlvclear)
= { <u>TLVWARN-20</u> | n } \]

\[ [TLVWEXEC](parameter_intro/tlvwexec)
= { n } \]

\[ [TLVWRATE](parameter_intro/tlvwrate)
= { 60 | n } \]

\[ [TLVWARN](parameter_intro/tlvwarn)
= { 70 | n } \]

\[ [WSCAN](parameter_intro/wscan)
= { 60
| n } \]

 

#### CFTCOM TYPE = TCPIP

[ID](parameter_intro/id)
= identifier

[HOST](parameter_intro/host)
= string

[PORT](parameter_intro/port)
= number

[PROTOCOL](parameter_intro/protocol)
= { XHTTP }

\[ [ADDRLIST](parameter_intro/addrlist)
= ( string, string, ...) \]

\[ [COMMENT](parameter_intro/comment)
=  string
\]

\[ [MODE](parameter_intro/mode)
= { <span style="text-decoration: underline;">REPLACE</span>
| CREATE | DELETE } \]

<span style="font-weight: bold;"> </span>[CFTCOM](../web_copilot_ui/conf_intro/cftcom)

[Communication
media](../../admin_intro/admin_config_commands/communication_media_concepts)

<span id="CFTCRON"></span>

#### CFTCRON: Define  <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> cron jobs

Syntax

ID = identifier

[CRONTAB](parameter_intro/crontab)
= string

[EXEC](parameter_intro/exec)
= filename

[EXECPOLICY](parameter_intro/execpolicy)        = \[ <u>INSTANCE</u> |ALLNODES \]

[TIME](parameter_intro/time)
= { string | @shutdown | @startup } <span style="font-weight: bold;">\[FOR
DETAILS:</span> [CFTCRON
time syntax](../web_copilot_ui/flow_def_intro/cftcron#CFTCRON_time_syntax)<span style="font-weight: bold;">\]</span>

\[ [PARM](parameter_intro/parm)
= string \]

\[ [COMMENT](parameter_intro/comment)
= string \]

\[ [STATE](parameter_intro/state) = { <u>ACTIVE</u> | NOACTIVE } \]

\[ [TYPE](parameter_intro/type)
= { <span style="text-decoration: underline;">EXEC</span>
| CFTUTIL } \]

\[ [USERID](parameter_intro/userid)
= { <span style="text-decoration: underline;">CFT
server "userid"</span>
| string } \]

[Define script execution](../web_copilot_ui/flow_def_intro/cftcron)

<span id="CFTDEST"></span>

#### CFTDEST: Definition of a list of partners 

Syntax

CFTDEST FNAME

ID = identifier

[FNAME](parameter_intro/fname)
= filename

\[ [EXEC](parameter_intro/exec)
= { <span style="text-decoration: underline;">DEST</span>
| PART | CHILDREN} \]

\[ EXECA = { <span style="text-decoration: underline;">DEST</span>
| PART | CHILDREN} \]

\[ EXECPRE = { <span style="text-decoration: underline;">DEST</span>
| PART | CHILDREN} \]

\[ [COMMENT](parameter_intro/comment)
= string \]

\[ [FOR](parameter_intro/for)
= { <span style="text-decoration: underline;">BOTH</span>
| COMMUT |
LOCAL } \]

\[ [MODE](parameter_intro/mode)
= { <span style="text-decoration: underline;">REPLACE</span>
| CREATE | DELETE } \]

\[ [NOPART](parameter_intro/nopart)
= { <span style="text-decoration: underline;">ABORT</span>
| CONTINUE | IGNORE } \]

####  

CFTDEST PART

ID = identifier

[PART](parameter_intro/part)
= (identifier, identifier, ...)

\[ [EXEC](parameter_intro/exec)
= { <span style="text-decoration: underline;">DEST</span>
| PART } \]

\[ [COMMENT](parameter_intro/comment)
= string \]

\[ [FOR](parameter_intro/for)
= { <span style="text-decoration: underline;">BOTH</span>
| COMMUT |
LOCAL } \]

\[ [MODE](parameter_intro/mode)
= { <span style="text-decoration: underline;">REPLACE</span>
| CREATE | DELETE } \]

\[ [NOPART](parameter_intro/nopart)
= { <span style="text-decoration: underline;">ABORT</span>
| CONTINUE | IGNORE } \]

[CFTDEST details](../web_copilot_ui/flow_def_intro/cftdest)

Broadcast
list

<span id="CFTEXIT"></span>

#### CFTEXIT: Activate an exit task 

Syntax

#### CFTEXIT TYPE = FILE

[ID](parameter_intro/id)
= identifier

<span style="font-weight: normal;">[TYPE](parameter_intro/type)
= FILE</span>

\[ [COMMENT](parameter_intro/comment)
= string \]

\[ [FORMAT](parameter_intro/format)
= { <span style="text-decoration: underline;">V23</span>
| 23 | V24 | 24 } \]

\[ [LANGUAGE](parameter_intro/language)
= { <span style="text-decoration: underline;">COBOL</span>
| C } \]

\[ [MODE](parameter_intro/mode)
= { <span style="text-decoration: underline;">REPLACE</span>
| CREATE | DELETE } \]

\[ [PARM](parameter_intro/parm)
= string \]

\[ [PROG](parameter_intro/prog)
= { <span style="text-decoration: underline;">CFTEXIT</span>
| string } \]

\[ [RESERV](parameter_intro/reserv)
= { <span style="text-decoration: underline;">16384</span>
| n } \]

\[ [WAITTASK](parameter_intro/waittask)
= { <span style="text-decoration: underline;">1441</span>
| n } \]

 

#### <span style="font-weight: normal;">CFTEXIT TYPE = { FILE | ACCESS | EXEC | BOT}</span>

[ID](parameter_intro/id)
= identifier

[TYPE](parameter_intro/type)
= { FILE | ACCESS |  EXEC | BOT }

\[ [COMMENT](parameter_intro/comment)
= string \]

\[ [FORMAT](parameter_intro/format)
= { <span style="text-decoration: underline;">V23</span>
| 23 | V24 | 24 } \]

\[ [LANGUAGE](parameter_intro/language)
= { <span style="text-decoration: underline;">COBOL</span>
| C } \]

\[ [MODE](parameter_intro/mode)
= { <span style="text-decoration: underline;">REPLACE</span>
| CREATE | DELETE } \]

\[ [PARM](parameter_intro/parm)
= string \]

\[ [PROG](parameter_intro/prog)
= { <span style="text-decoration: underline;">CFTEXIT</span>
| string } \]

\[ [RESERV](parameter_intro/reserv)
= { <span style="text-decoration: underline;">1024</span>
| n } \]

\[ [WAITTASK](parameter_intro/waittask)
= { <span style="text-decoration: underline;">1441</span>
| n } \]

<span style="font-weight: bold;"> </span>CFTEXIT details

[Exit
tasks](../../app_integration_intro/managing_exits)

<span id="CFTEXT"></span>

#### CFTEXT: Extract data from the parameter and partner files 

Syntax

\[ [TYPE](parameter_intro/type)
= { <span style="text-decoration: underline;">ALL</span>
| ACCNT | APPL | AUTH | CAT | COM | CRON | DEST |  EXIT | IDF | LOG
|  NET | PARM | PART | PROT | RECV | SEND | SSL |  TCP |  XLATE } \]

\[ [CONTENT](parameter_intro/content) = { <u>FULL</u> | BRIEF } \]

\[ [FOUT](parameter_intro/fout)
= filename \]

\[ [FPARM](parameter_intro/fparm)
= filename \]

\[ [FPART](parameter_intro/fpart)
= filename \]

\[ [ID](parameter_intro/id)
= { <span style="text-decoration: underline;">\*</span>
| identifier | mask } \]

[Export
configuration](../about_cftutil/configuring_cft_start_here/cftext_command)

<span id="CFTFILE"></span>

#### CFTFILE: Create or delete  <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> files

Syntax

[TYPE](parameter_intro/type)
= { PARM | PART }

[FNAME](parameter_intro/fname)
= filename  

\[ [HABFNAME](parameter_intro/habfname)
= filename \]

\[ [FBLKSIZE](parameter_intro/fblksize)
= { <span style="text-decoration: underline;">0</span>
|n } \]

\[ [FSPACE](parameter_intro/fspace)
= n \]

\[ [FSPACEX](parameter_intro/fspacex)
= n \]

\[ [MODE](parameter_intro/mode)
= { <span style="text-decoration: underline;">CREATE</span>
| REPLACE | DELETE } \]

 

#### CFTFILE { CAT | COM }

[TYPE](parameter_intro/type)
= {  CAT
| COM }

[FNAME](parameter_intro/fname)
= filename

\[ [RECNB](parameter_intro/recnb)
= n \]

\[ [FBLKSIZE](parameter_intro/fblksize)
= { <span style="text-decoration: underline;">0</span>
|n } \]

\[ [FSPACE](parameter_intro/fspace)
= { <span style="text-decoration: underline;">0</span>
| n } \]

\[ [FSPACEX](parameter_intro/fspacex)
=  { <span style="text-decoration: underline;">0</span>
| n } \]

\[ [HABFNAME](parameter_intro/habfname)
= filename \]

\[ [MODE](parameter_intro/mode)
= { <span style="text-decoration: underline;">CREATE</span>
| REPLACE | DELETE } \]

\[ NODE = { <span style="text-decoration: underline;">0</span>
| n } \] available for TYPE=CAT

 

#### CFTFILE { ACCNT | LOG }

[TYPE](parameter_intro/type)
= { ACCNT | LOG }

[FNAME](parameter_intro/fname)
= filename

\[ [FBLKSIZE](parameter_intro/fblksize)
= <span style="text-decoration: underline;">0</span>
| n \]

\[ [FSPACE](parameter_intro/fspace)
= <span style="text-decoration: underline;">0</span>
|n \]

\[ [FSPACEX](parameter_intro/fspacex)
= <span style="text-decoration: underline;">0</span>
|n \]

\[ [MODE](parameter_intro/mode)
= { <span style="text-decoration: underline;">CREATE</span>
| REPLACE | DELETE } \]

[Manually create internal datafile files](../../admin_intro/admin_commands_intro/cftfile)

#### CFTFOLDER

See [CFTFOLDER](../web_copilot_ui/flow_def_intro/cftfolder) for additional parameter details.

[IDF](parameter_intro/idf) = string
        &lt;/p>

[PART](parameter_intro/part) = string
        &lt;/p>

[SCANDIR](../web_copilot_ui/flow_def_intro/cftfolder#SCANDIR)
        = string&lt;/p>

[WORKDIR](../web_copilot_ui/flow_def_intro/cftfolder#WORKDIR) = string
        &lt;/p>

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

<span id="CFTIDF"></span>

#### CFTIDF ID = identifier: Correspondence between the network identifier and the local identifier of a transferred model file 

Syntax

[NIDF](parameter_intro/nidf)
= string

[PART](parameter_intro/part)
= identifier

[TYPE](parameter_intro/type)
= { <span style="text-decoration: underline;">RECV</span>
| SEND }

\[ [COMMENT](parameter_intro/comment)
= string \]

\[ [MODE](parameter_intro/mode)
= { <span style="text-decoration: underline;">REPLACE</span>
| CREATE | DELETE } \]

<span style="font-weight: bold;"> </span>[CFTIDF details](../web_copilot_ui/flow_def_intro/cftidf)

[File
template/virtual file association](../../concepts/cft_configuration_concepts_start_here/network_file_identifier_concepts)

<span id="CFTLOG"></span>

#### CFTLOG FNAME = filename: Log file management parameters 

Syntax

[ID](parameter_intro/id)
= identifier

\[ [AFNAME](parameter_intro/afname)
= filename \]

\[ [COMMENT](parameter_intro/comment)
= string \]

\[ [CONTENT](parameter_intro/content)
= { <span style="text-decoration: underline;">FULL</span>
| BRIEF } \]

\[ [EXEC](parameter_intro/exec)
= filename \]

\[ [FORMAT](parameter_intro/format)
= { <span style="text-decoration: underline;">V23</span>
| 23 | V24 | 24 } \]

\[ [LENGTH](parameter_intro/length)
= { <span style="text-decoration: underline;">160</span>
| n } \]

\[ [MAXREC](parameter_intro/maxrec)
= { <span style="text-decoration: underline;">0</span>
| n } \]

\[ [MODE](parameter_intro/mode)
= { <span style="text-decoration: underline;">REPLACE</span>
| CREATE | DELETE } \]

\[ [NOTIFY](parameter_intro/notify)
= identifier \]

\[ [OPERMSG](parameter_intro/opermsg)
= n \]

\[ [SWITCH](parameter_intro/switch)
= { <span style="text-decoration: underline;">00000000</span>
| time } \]

CFTLOG details

Transfer
Log file

<span id="CFTNET"></span>

#### CFTNET: Local network resources

Syntax

#### CFTNET TYPE = TCP

[HOST](parameter_intro/host)
= { string | INADDR\_ANY }

[ID](parameter_intro/id)
= { identifier | \*identifier }

\[ [CALL](parameter_intro/call)
= { <span style="text-decoration: underline;">INOUT</span>
| IN | OUT } \]

\[ [CLASS](parameter_intro/class)
= { 1 | n } \]

\[ [MAXCNX](parameter_intro/maxcnx)
= { <span style="text-decoration: underline;">384</span>
| n } \]

\[ [MODE](parameter_intro/mode)
= { <span style="text-decoration: underline;">REPLACE</span>
| CREATE | DELETE } \]

\[ [SRCHOST](parameter_intro/srchost)=
{ hostname1 | n} \]

\[ [SRCPORTS](parameter_intro/srcports)= { string } \]

 

#### CFTNET TYPE = SR

[HOST](parameter_intro/host)
= { string | INADDR\_ANY }

[ID](parameter_intro/id)
= { identifier | \*identifier }

\[ RECALLHOST = { string } \]

\[ [PORT](parameter_intro/port) = {0 ...65535 } \]

\[ [SRCHOST](parameter_intro/srchost)    = { string } \]

\[ SSLTERM           { YES | <u>NO</u> } \]

#### PROTOCOL = GENERIC

[HOST](parameter_intro/host)
= string

[ID](parameter_intro/id)
= identifier

INET
= identifier

[PORT](parameter_intro/port)
=  n

\[ [CALL](parameter_intro/call)
= { <span style="text-decoration: underline;">INOUT</span>
| IN | OUT } \]

\[ [CLASS](parameter_intro/class)
= { 1 | n } \]

\[ [MAXCNX](parameter_intro/maxcnx)
= { <span style="text-decoration: underline;">384</span>
| n } \]

\[ [MODE](parameter_intro/mode)
= { <span style="text-decoration: underline;">REPLACE</span>
| CREATE | DELETE } \]

\[ [PARM](parameter_intro/parm)
= string \]

\[ [SRCHOST](parameter_intro/srchost)=
{ hostname1 | n} \]

 

#### CFTNET TYPE = TCP

#### PROTOCOL = SOCKS4, SOCKS5

[HOST](parameter_intro/host)
= string  

[ID](parameter_intro/id)
= identifier

INET
= identifier

[PORT](parameter_intro/port)
=  n

\[ [CALL](parameter_intro/call)
= { <span style="text-decoration: underline;">INOUT</span>
| IN | OUT } \]

\[ [CLASS](parameter_intro/class)
= { 1 | n } \]

\[ [MAXCNX](parameter_intro/maxcnx)
= { <span style="text-decoration: underline;">32</span>
| n } \]

\[ [MODE](parameter_intro/mode)
= { <span style="text-decoration: underline;">REPLACE</span>
| CREATE | DELETE } \]

\[ [SRCHOST](parameter_intro/srchost)=
{ hostname1 | n} \]

\[ [USER](parameter_intro/user)
= string \]

 [CFTNET details](../web_copilot_ui/conf_intro/cftnet)

[Network
resources](../../admin_intro/admin_config_commands/network_resource_concepts)

[About proxies and SOCKS](../../protocols_start_here/ipv6/use_proxy_and_socks_protocol)

<span id="CFTPARM"></span>

#### CFTPARM: General  <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> environment parameters

Syntax

[CAT](parameter_intro/cat)
= identifier

[COM](parameter_intro/com)
= ( identifier ,  identifier
, ...)

[ID](parameter_intro/id)
= identifier

[KEY](parameter_intro/key)
= {string | #filename }

[NET](parameter_intro/net)
= ( identifier ,  identifier
,...)

[PART](parameter_intro/part)
= identifier  

[PARTFNAM](parameter_intro/partfnam)
= filename  

[PROT](parameter_intro/prot)
= ( identifier ,  identifier
, ...)

\[ [ACCNT](parameter_intro/accnt)
= identifier  \]

\[ [BUFSIZE](parameter_intro/bufsize)
=  { <span style="text-decoration: underline;">4096</span>
| n } \]

\[ [COMMENT](parameter_intro/comment)
= string \]

\[ [CRONTABS](parameter_intro/crontab)
= (crontab, crontab, …) \]

\[ [DEFAULT](parameter_intro/default)
= { <span style="text-decoration: underline;">DEFAUT</span>
| identifier } \]

\[ [EXECRE](parameter_intro/execre)
= filename \]

\[ [EXECRF](parameter_intro/execrf)
= filename \]

\[ [EXECRM](parameter_intro/execrm)
= filename \]

\[ [EXECSE](parameter_intro/execse)
= filename \]

\[ [EXECSF](parameter_intro/execsf)
= filename \]

\[ [EXECSFA](parameter_intro/execsfa)
= filename \]

\[ [EXECSM](parameter_intro/execsm)
= filename  \]

\[ [EXECSMA](parameter_intro/execsma)
= filename \]

\[ EXITBOT
= identifier  \]

\[ [EXITEOT](parameter_intro/exiteot)
= identifier  \]

\[ [FBUFSIZE](parameter_intro/fbufsize)
= { <span style="text-decoration: underline;">0</span>
|65535 } \]

\[ [LENAPPL](parameter_intro/lenappl)
= { <span style="text-decoration: underline;">32</span>
| 1 } \]

\[ [LOG](parameter_intro/log)
= identifier  \]

\[ [MAXTASK](parameter_intro/maxtask)
= { <span style="text-decoration: underline;">8</span>
| n }  \]

\[ [MAXTRANS](parameter_intro/maxtrans)
=  { <span style="text-decoration: underline;">256</span>
| 1 } \]

\[ [MODE](parameter_intro/mode)
= { <span style="text-decoration: underline;">REPLACE</span>
| CREATE | DELETE }  \]

\[ [NPART](parameter_intro/npart)
= string \]

\[ [PKIPASSW](parameter_intro/pkipassw)
= { PKIPASSW | string } \]

\[ [RCVALLER](parameter_intro/rcvaller)
= { <span style="text-decoration: underline;">STOP</span>
| CONTINUE } \]

\[ [SECFNAME](parameter_intro/secfname)
= filename \]

\[ [SSLMTASK](parameter_intro/sslmtask)
= { <span style="text-decoration: underline;">8</span>
| n } \]

\[ [SSLTTASK](parameter_intro/sslttask)
=  {<span style="text-decoration: underline;">3</span>
| n } \]

\[ [SSLWTASK](parameter_intro/sslwtask)
= { <span style="text-decoration: underline;">10</span>
|n } \]

\[ [SSLWRESP](parameter_intro/sslwresp)
= { <span style="text-decoration: underline;">60</span>
| n } \]

\[ [TRACE](parameter_intro/trace)
= string \]

\[ [TRANTASK](parameter_intro/trantask)
= { <span style="text-decoration: underline;">3</span>
| n } \]

\[ [TRKPART](parameter_intro/trkpart)
=  { <span style="text-decoration: underline;">UNDEFINED</span>
| ALL | SUMMARY | NO } \]

\[ [TRKRECV](parameter_intro/trkrecv)
=  { <span style="text-decoration: underline;">UNDEFINED</span>
| ALL | SUMMARY | NO } \]

\[ [TRKSEND](parameter_intro/trksend)
= { <span style="text-decoration: underline;">UNDEFINED</span>
| ALL | SUMMARY | NO } \]

\[ [USERCTRL](parameter_intro/userctrl)
= { <span style="text-decoration: underline;">NO</span>
| YES } \]

\[ [WAITRESP](parameter_intro/waitresp)
= { <span style="text-decoration: underline;">60</span>
| n } \]

\[ [WAITTASK](parameter_intro/waittask)
= { <span style="text-decoration: underline;">10</span>
| n } \]

[CFTPARM details](../web_copilot_ui/conf_intro/cftparm)

[Transfer CFT general
parameters](../../admin_intro/admin_config_commands/cftparm_general_parameters)

<span id="CFTPART"></span>

#### CFTPART ID = identifier: Partner definition parameters  

Syntax

[PROT](parameter_intro/prot)
= { (identifier | mask , identifier | mask , .... ) }

\[ [COMMENT](parameter_intro/comment)
= string  \]

\[ [COMMUT](parameter_intro/commut)
= { <span style="text-decoration: underline;">YES</span>
| NO | SERVER }   \]

\[ [CTRLPART](parameter_intro/ctrlpart)
= { <span style="text-decoration: underline;">IGNORE</span>
| ALL | RPART | SPART } \]

\[ [FPREFIX](parameter_intro/fprefix)
= string \]

\[ [GROUP](parameter_intro/group)
= identifier \]

\[ [IDF](parameter_intro/idf)
= identifier  \]

\[ [IMAXTIME](parameter_intro/imaxtime)
= { <span style="text-decoration: underline;">23595999</span>
| time } \]

\[ IMINTIME
= { <span style="text-decoration: underline;">0</span>
| time } \]

\[ [IPART](parameter_intro/ipart)
= identifier \]

\[ [MODE](parameter_intro/mode)
= { <span style="text-decoration: underline;">REPLACE</span>
| CREATE | DELETE } \]

\[ [NACK](parameter_intro/nack) = { YES | <u>NO</u> | ANY } \]

\[ [NRPART](parameter_intro/nrpart)
= string \]

\[ [NRPASSW](parameter_intro/nrpassw) = string  \]

\[ [NSPART](parameter_intro/nspart)
= string  \]

\[ [NSPASSW](parameter_intro/nspassw)
= string  \]

\[ [OMAXTIME](parameter_intro/omaxtime)
= { <span style="text-decoration: underline;">23595999</span>
| time } \]

\[ [OMINTIME](parameter_intro/omintime)
= { <span style="text-decoration: underline;">0</span>
| time } \]

\[ [RAUTH](parameter_intro/rauth)
= { <span style="text-decoration: underline;">\*</span>
| identifier } \]

\[ [SAP](parameter_intro/sap)
= (string, string, …) \]

\[ [SAUTH](parameter_intro/sauth)
= { <span style="text-decoration: underline;">\*</span>
| identifier } \]

\[ [SSL](parameter_intro/ssl)
= identifier \]

\[ [STATE](parameter_intro/state)
= {<span style="text-decoration: underline;">ACTIVEBOTH</span>
| ACTIVEREQ | ACTIVESERV | NOACTIVE } \]

\[ [SYST](parameter_intro/syst)
= { ‘<span style="text-decoration: underline;">
‘</span> | GCOS7 | GCOS8 | GUARD |  MVS |  OS400 |
UNIX | VM | VMS |  VSE | WINNT | BS2000 } \]

\[ [TRK](parameter_intro/trk)
= { <span style="text-decoration: underline;">UNDEFINED</span>
| ALL | SUMMARY | NO } \]

\[ [XLATE](parameter_intro/xlate)
= identifier \]

CFTPART details

Partner
attribute concepts

<span id="CFTPROT"></span>

#### CFTPROT: Transfer protocol

Syntax

CFTPROT TYPE = ODETTE

[ID](parameter_intro/id)
= identifier

[NET](parameter_intro/net)
= identifier

\[ [DISCTD](parameter_intro/disctd)
= { <span style="text-decoration: underline;">20</span>
| n } \]

\[ [DISCTS](parameter_intro/discts)
= { <span style="text-decoration: underline;">65</span>
| n } \]

\[ [DYNAM](parameter_intro/dynam)
= identifier  \]

\[ [EERP](parameter_intro/eerp)
= { <span style="text-decoration: underline;">91</span>
| 86 } \]

\[ [EXITA](parameter_intro/exita)
= identifier \]

\[ [IDF](parameter_intro/ida)
= string  \]

\[ [MODE](parameter_intro/mode)
= { <span style="text-decoration: underline;">REPLACE</span>
| CREATE | DELETE } \]

\[ [PAD](parameter_intro/pad)
= { <span style="text-decoration: underline;">NO</span>
| YES } \] &lt;Deprecated in Transfer CFT 3.5>

\[ [RCOMP](parameter_intro/rcomp)
=  { <span style="text-decoration: none;">0</span>
| 15 } \]

\[ [RCREDIT](parameter_intro/rcredit)
= { <span style="text-decoration: underline;">4</span>
| n } \]

\[ [RESTART](parameter_intro/restart)
= { <span style="text-decoration: underline;">5</span>
| n } \]

\[ [RESYNC](parameter_intro/resync)
= { <span style="text-decoration: underline;">NO</span>
| YES } \]

\[ [REVERSE](parameter_intro/reverse)
= { <span style="text-decoration: underline;">YES</span>
| NO } \]

\[ [RRUSIZE](parameter_intro/rrusize)
= { <span style="text-decoration: underline;">2048</span>
| n } \]

\[ [RTO](parameter_intro/rto)
= { <span style="text-decoration: underline;">260</span>
| n } \]

\[ [SAP](parameter_intro/sap)
= string \]

\[ [SCOMP](parameter_intro/scomp)
= { 0 | <u>1</u> |15 } \]

\[ [SCREDIT](parameter_intro/scredit)
= { <span style="text-decoration: underline;">4</span>
| n } \]

\[ [SRIN](parameter_intro/srin)
= { <span style="text-decoration: underline;">BOTH</span>
| NONE | RECEIVER | SENDER } \]

\[ [SROUT](parameter_intro/srout)
= { <span style="text-decoration: underline;">BOTH</span>
| NONE | RECEIVER | SENDER } \]

\[ [SRUSIZE](parameter_intro/srusize)
= { 2048 | n } \]

\[ [SSL](parameter_intro/ssl)
= identifier \]

\[ [TCP](parameter_intro/tcp)
= { <span style="text-decoration: none;">CFT</span>
| <u>OFTP</u>} \]

 

CFTPROT TYPE = PESIT

[PROF](parameter_intro/prof)
= ANY

[ID](parameter_intro/id)
= identifier  

[NET](parameter_intro/net)
= identifier

\[ [CONCAT](parameter_intro/concat)
= { <span style="text-decoration: none;">NO</span>
| <u>YES</u> } \]

\[ [DISCTC](parameter_intro/disctc)
= { <span style="text-decoration: underline;">60</span>
| n } \]

\[ [DISCTD](parameter_intro/disctd)
= { <span style="text-decoration: underline;">10</span>
| n } \]

\[ [DISCTR](parameter_intro/disctr)
= { <span style="text-decoration: underline;">45</span>
| n } \]

\[ [DISCTS](parameter_intro/discts)
= { <span style="text-decoration: underline;">60</span>
|n } \]

\[ [DYNAM](parameter_intro/dynam)
= identifier \]

\[ [EXITA](parameter_intro/exita)
= identifier \]

\[ [HIDE99](parameter_intro/hide99)
= { <span style="text-decoration: underline;">NO</span>
| YES } \]

\[ [IDF](parameter_intro/idf)
= string \]

\[ [LOGON](parameter_intro/logon)
= { <span style="text-decoration: underline;">YES</span>
| NO } \]

\[ [MODE](parameter_intro/mode)
= { <span style="text-decoration: underline;">REPLACE</span>
| CREATE | DELETE } \]

\[ [MULTART](parameter_intro/multart)
= { NO
| <u>YES</u> } \]

\[ [NACK](parameter_intro/nack) = { YES | <u>NO</u> | ANY} \]

\[ [PAD](parameter_intro/pad)
= { <span style="text-decoration: underline;">NO</span>
| YES } \] &lt;Deprecated in Transfer CFT 3.5>

\[ [RCHKW](parameter_intro/rchkw)
= { <span style="text-decoration: underline;">3</span>
| n } \]

\[ [RCOMP](parameter_intro/rcomp)
= { <u>0</u>  
| 15 } \]

\[ [RESTART](parameter_intro/restart)
= { <span style="text-decoration: underline;">5</span>
| n } \]

\[ [RESYNC](parameter_intro/resync)
= { <span style="text-decoration: underline;">NO</span>
| YES } \]

\[ [REVERSE](parameter_intro/reverse)
= { <span style="text-decoration: underline;">NO</span>
| YES } \]

\[ [RPACING](parameter_intro/rpacing)
= { <span style="text-decoration: underline;">32767</span>
| n } \]

\[ [RRUSIZE](parameter_intro/rrusize)
= { <span style="text-decoration: underline;">32750</span>
|n } \]

\[ [RTO](parameter_intro/rto)
= { <span style="text-decoration: underline;">260</span>
| n } \]

\[ [SAP](parameter_intro/sap)
= string \]

\[ [SCHKW](parameter_intro/schkw)
= { <span style="text-decoration: underline;">3</span>
| n } \]

\[ [SCOMP](parameter_intro/scomp)
= { <u>0</u> | 15} \]

\[ [SEGMENT](parameter_intro/segment)
= { NO
| <u>YES</u> } \]

\[ [SPACING](parameter_intro/spacing)
= { <span style="text-decoration: underline;">32767</span>
| n } \]

\[ [SRIN](parameter_intro/srin)
= { <span style="text-decoration: underline;">BOTH</span>
| NONE | RECEIVER | SENDER } \]

\[ [SROUT](parameter_intro/srout)
= { <span style="text-decoration: underline;">BOTH</span>
| NONE | RECEIVER | SENDER } \]

\[ [SRUSIZE](parameter_intro/srusize)
= { <span style="text-decoration: underline;">32750</span>
| n } \]

\[ [SSERV](parameter_intro/sserv)
= { <span style="text-decoration: underline;">GSIT</span>
| string } \]

<span style="font-weight: normal;">\[ [SSL](parameter_intro/ssl)
= identifier \]</span>

 

CFTPROT TYPE = PESIT  

[PROF](parameter_intro/prof)
= CFT

[ID](parameter_intro/id)
= identifier

[NET](parameter_intro/net)
= identifier

\[ [CONCAT](parameter_intro/concat)
= { <span style="text-decoration: underline;">NO</span>
| YES } \]

\[ [DISCTC](parameter_intro/disctc)
= { <span style="text-decoration: underline;">90</span>
| n }  \]

\[ [DISCTD](parameter_intro/disctd)
=  { 20
| n } \]

\[ [DISCTR](parameter_intro/disctr)
= { <span style="text-decoration: underline;">45</span>
| n } \]

\[ [DISCTS](parameter_intro/discts)
= { <span style="text-decoration: underline;">65</span>
| n } \]

\[ [DYNAM](parameter_intro/dynam)
= identifier  \]

\[ [EXITA](parameter_intro/exita)
= identifier  \]

\[ [HIDE99](parameter_intro/hide99)
= { <span style="text-decoration: underline;">NO</span>
|YES } \]

\[ [IDF](parameter_intro/idf)
= string \]

\[ [MODE](parameter_intro/mode)
= { <span style="text-decoration: underline;">REPLACE</span>
| CREATE | DELETE } \]

\[ [MULTART](parameter_intro/multart)
= { <span style="text-decoration: underline;">NO</span>
| YES } \]

\[ [PAD](parameter_intro/pad)
= { <span style="text-decoration: underline;">NO</span>
| YES } \] &lt;Deprecated in Transfer CFT 3.5>

\[ [RCHKW](parameter_intro/rchkw)
= { <span style="text-decoration: underline;">2</span>
| n }  \]

\[ [RCOMP](parameter_intro/rcomp)
= { 0 |<span style="text-decoration: underline;">15</span>} \]

\[ [RESTART](parameter_intro/restart)
= { <span style="text-decoration: underline;">5</span>
| n } \]

\[ [RESYNC](parameter_intro/resync)
= { <span style="text-decoration: underline;">NO</span>
| YES } \]

\[ [REVERSE](parameter_intro/reverse)
= { <span style="text-decoration: underline;">NO</span>
| YES } \]

\[ [RPACING](parameter_intro/rpacing)
= { <span style="text-decoration: underline;">36</span>
| n } \]

\[ [RRUSIZE](parameter_intro/rrusize)
= { <span style="text-decoration: underline;">4056</span>
| n } \]

\[ RSERV
= string \]

\[ [RTO](parameter_intro/rto)
= { <span style="text-decoration: underline;">260</span>
| n }  \]

\[ [SAP](parameter_intro/sap)
= string \]

\[ [SCHKW](parameter_intro/schkw)
= { <span style="text-decoration: underline;">2</span>
| n } \]

\[ [SCOMP](parameter_intro/scomp)
= { 0| <span style="text-decoration: underline;">15</span>
} \]

\[ [SEGMENT](parameter_intro/segment)
= { <span style="text-decoration: underline;">NO</span>
| YES } \]

\[ [SPACING](parameter_intro/spacing)
= { <span style="text-decoration: underline;">36</span>
| n } \]

\[ [SRIN](parameter_intro/srin)
= { <span style="text-decoration: underline;">BOTH</span>
| NONE | RECEIVER | SENDER } \]

\[ [SROUT](parameter_intro/srout)
= { <span style="text-decoration: underline;">BOTH</span>
| NONE | RECEIVER | SENDER } \]

\[ [SRUSIZE](parameter_intro/srusize)
= { <span style="text-decoration: underline;">4056</span>
|n } \]

\[ [SSERV](parameter_intro/sserv)
= { CFTPSITX | string } \]

\[ [SSL](parameter_intro/ssl)
= identifier \]

 

CFTPROT TYPE = PESIT

[PROF](parameter_intro/prof)
= EXTERN

[ID](parameter_intro/id)
= identifier

[NET](parameter_intro/net)
= identifier

\[ [CONCAT](parameter_intro/concat)
= { <span style="text-decoration: underline;">NO</span>
| YES } \]

\[ [DISCTC](parameter_intro/disctc)
= { <span style="text-decoration: underline;">90</span>
| n } \]

\[ [DISCTD](parameter_intro/disctd)
=  { <span style="text-decoration: underline;">120</span>
| n } \]

\[ [DISCTR](parameter_intro/disctr)
= { <span style="text-decoration: underline;">45</span>
| n } \]

\[ [DISCTS](parameter_intro/discts)
= { <span style="text-decoration: underline;">165</span>
| n } \]

\[ [DYNAM](parameter_intro/dynam)
= identifier  \]

\[ [EXITA](parameter_intro/exita)
= identifier   \]

\[ [HIDE99](parameter_intro/hide99)
= { <span style="text-decoration: underline;">NO</span>
|YES } \]

\[ [IDF](parameter_intro/idf)
= string  \]

\[ [MODE](parameter_intro/mode)
= { <span style="text-decoration: underline;">REPLACE</span>
| CREATE | DELETE } \]

\[ [LOGON](parameter_intro/logon)
= { <span style="text-decoration: underline;">YES</span>
| NO } \]

\[ [MULTART](parameter_intro/multart)
= { <span style="text-decoration: underline;">NO</span>
| YES } \]

\[ [NACK](parameter_intro/nack) = { YES | <u>NO</u> | ANY } \]

\[ [RCHKW](parameter_intro/rchkw)
= { <span style="text-decoration: underline;">2</span>
| n } \]

\[ [RCOMP](parameter_intro/rcomp)
=  { 0 | <span style="text-decoration: underline;">10</span>
|15 } \]

\[ [RESTART](parameter_intro/restart)
= { <span style="text-decoration: underline;">5</span>
| n } \]

\[ [RESYNC](parameter_intro/resync)
= { <span style="text-decoration: underline;">NO</span>
| YES } \]

\[ [REVERSE](parameter_intro/reverse)
= { YES | NO } \]

\[ [RPACING](parameter_intro/rpacing)
= { 36 | n } \]

\[ [RRUSIZE](parameter_intro/rrusize)
= { 4056 | n } \]

\[ [RTO](parameter_intro/rto)
= { <span style="text-decoration: underline;">260</span>
| n } \]

\[ [SAP](parameter_intro/sap)
= string \]

\[ [SCHKW](parameter_intro/schkw)
= { <span style="text-decoration: underline;">2</span>
| n } \]

\[ [SCOMP](parameter_intro/scomp)
=  { 0 | <span style="text-decoration: underline;">10</span>
| 15} \]

\[ [SEGMENT](parameter_intro/segment)
= { NO | YES } \]

\[ [SPACING](parameter_intro/spacing)
= { 36 | n } \]

\[ [SRIN](parameter_intro/srin)
= { <span style="text-decoration: underline;">BOTH</span>
| NONE | RECEIVER | SENDER } \]

\[ [SROUT](parameter_intro/srout)
= { <span style="text-decoration: underline;">BOTH</span>
| NONE | RECEIVER | SENDER } \]

\[ [SRUSIZE](parameter_intro/srusize)
= { 4056 | n } \]

\[ [SSERV](parameter_intro/sserv)
= { <span style="text-decoration: underline;">PESIT</span>
| string } \]

\[ [SSL](parameter_intro/ssl)
= identifier \]

 

CFTPROT TYPE = PESIT

[PROF](parameter_intro/prof)
= SIT

[ID](parameter_intro/id)
= identifier

[NET](parameter_intro/net)
= identifier  

\[ [CONCAT](parameter_intro/concat)
= { <span style="text-decoration: underline;">NO</span>
| YES } \]

\[ [DISCTC](parameter_intro/disctc)
= { <span style="text-decoration: underline;">90</span>
| n } \]

\[ [DISCTD](parameter_intro/disctd)
= { 240 | n } \]

\[ [DISCTR](parameter_intro/disctr)
= { 45 | n } \]

\[ [DISCTS](parameter_intro/discts)
= { 285 | n } \]

\[ [DYNAM](parameter_intro/dynam)
= identifier \]

\[ [EXITA](parameter_intro/exita)
= identifier \]

\[ [IDF](parameter_intro/ida)
= string \]

\[ [MODE](parameter_intro/mode)
= { <span style="text-decoration: underline;">REPLACE</span>
| CREATE | DELETE } \]

\[ [MULTART](parameter_intro/multart)
=  { <span style="text-decoration: underline;">NO</span>
| YES } \]

\[ [RCHKW](parameter_intro/rchkw)
= { <span style="text-decoration: underline;">2</span>
| n } \]

\[ [RCOMP](parameter_intro/rcomp)
=  { 0 |
15 } \]

\[ [RESTART](parameter_intro/restart)
= { <span style="text-decoration: underline;">5</span>
| n } \]

\[ [RESYNC](parameter_intro/resync)
= { <span style="text-decoration: underline;">NO</span>
| YES } \]

\[ [REVERSE](parameter_intro/reverse)
= { <span style="text-decoration: underline;">NO</span>
| string } \]

\[ [RPACING](parameter_intro/rpacing)
= { <span style="text-decoration: underline;">36</span>
| n } \]

\[ [RRUSIZE](parameter_intro/rrusize)
= { 4050 | n } \]

\[ [RTO](parameter_intro/rto)
= { 260 | n } \]

\[ [SAP](parameter_intro/sap)
= string \]

\[ [SCHKW](parameter_intro/schkw)
= { 2 | n } \]

\[ [SCOMP](parameter_intro/scomp)
= { 0 | 15 } \]

\[ [SEGMENT](parameter_intro/segment)
= { NO | YES } \]

\[ [SPACING](parameter_intro/spacing)
= { <span style="text-decoration: underline;">36</span>
| n } \]

\[ [SRIN](parameter_intro/srin)
= { <span style="text-decoration: underline;">BOTH</span>
| NONE | RECEIVER | SENDER } \]

\[ [SROUT](parameter_intro/srout)
= { <span style="text-decoration: underline;">BOTH</span>
| NONE | RECEIVER | SENDER } \]

\[ [SRUSIZE](parameter_intro/srusize)
= { 4050 | n } \]

\[ [SSL](parameter_intro/ssl)
= identifier \]

 

CFTPROT TYPE = PESIT

[PROF](parameter_intro/prof)
= DMZ  

[ID](parameter_intro/id)
= identifier

[NET](parameter_intro/net)
= identifier

\[ [CONCAT](parameter_intro/concat)
= { <span style="text-decoration: underline;">NO</span>
| YES } \]

\[ [CTO](parameter_intro/cto)
= { <span style="text-decoration: underline;">1</span>
| n } \]

\[ [CYCLE](parameter_intro/cycle)
= { <span style="text-decoration: underline;">10</span>
| n } \]

\[ [DISCTC](parameter_intro/disctc)
= { <span style="text-decoration: underline;">90</span>
| n } \]

\[ [DISCTD](parameter_intro/disctd)
= { <span style="text-decoration: underline;">120</span>
| n } \]

\[ [DISCTR](parameter_intro/disctr)
= { <span style="text-decoration: underline;">45</span>
| n } \]

\[ [DISCTS](parameter_intro/discts)
= { <span style="text-decoration: underline;">65</span>
| n  } \]

\[ [DYNAM](parameter_intro/dynam)
= identifier \]

\[ [EXITA](parameter_intro/exita)
= identifier \]

\[ [IDF](parameter_intro/idf)
= string \]

\[ [LOGON](parameter_intro/logon)
= { <span style="text-decoration: underline;">YES</span>
| NO } \]

\[ [MODE](parameter_intro/mode)
= { <span style="text-decoration: underline;">REPLACE</span>
| CREATE | DELETE } \]

\[ [MULTART](parameter_intro/multart)
= { <span style="text-decoration: underline;">NO</span>
| YES } \]

\[ [PAD](parameter_intro/pad)
= { <span style="text-decoration: underline;">NO</span>
| YES } \] &lt;Deprecated in Transfer CFT 3.5>

\[ [PART](parameter_intro/part)
= ( identifier, identifier, …) \]

\[ [RCHKW](parameter_intro/rchkw)
= { <span style="text-decoration: underline;">2</span>
| n } \]

\[ [RCOMP](parameter_intro/rcomp)
= { 0 | <span style="text-decoration: underline;">10</span>
| 15 } \]

\[ [RESTART](parameter_intro/restart)
= { <span style="text-decoration: underline;">5</span>
| n  } \]

\[ [RESYNC](parameter_intro/resync)
= { <span style="text-decoration: underline;">NO</span>
| YES } \]

\[ [REVERSE](parameter_intro/reverse)
= { <span style="text-decoration: underline;">NO</span>
| YES } \]

\[ [RPACING](parameter_intro/rpacing)
= { <span style="text-decoration: underline;">36</span>
| n } \]

\[ [RRUSIZE](parameter_intro/rrusize)
= n \]

\[ [RTO](parameter_intro/rto)
= { <span style="text-decoration: underline;">260</span>
| n } \]

\[ [SAP](parameter_intro/sap)
= string \]

\[ [SCHKW](parameter_intro/schkw)
= { <span style="text-decoration: underline;">2</span>
| n } \]

\[ [SCOMP](parameter_intro/scomp)
= { 0 | <span style="text-decoration: underline;">10</span>
| 15 } \]

\[ [SEGMENT](parameter_intro/segment)
= { <span style="text-decoration: underline;">NO</span>
| YES } \]

\[ [SPACING](parameter_intro/spacing)
= { <span style="text-decoration: underline;">36</span>
| n }\]

\[ [SRIN](parameter_intro/srin)
= { <span style="text-decoration: underline;">BOTH</span>
| NONE | RECEIVER | SENDER } \]

\[ [SROUT](parameter_intro/srout)
= { <span style="text-decoration: underline;">BOTH</span>
| NONE | RECEIVER | SENDER } \]

\[ [SSERV](parameter_intro/sserv)
= { <span style="text-decoration: underline;">PESIT</span>
| string } \]

\[ [SSL](parameter_intro/ssl)
= identifier \]

\[ TURN
= { <span style="text-decoration: underline;">FILE</span>
| MESSAGE } \]

 

[CFTPROT details](../../admin_intro/admin_config_commands/transfer_protocol_concepts)

[File
Transfer Protocol](../../admin_intro/admin_config_commands/transfer_protocol_concepts)

<span id="CFTRECV"></span>

#### CFTRECV ID= identifier: Description of model file receiving parameters

Syntax

\[ [ACKEXEC](parameter_intro/ackexec) = filename\]

\[ [COMMENT](parameter_intro/comment)
= string \]

\[ [CYCDATE](parameter_intro/cycdate)
= { <span style="text-decoration: underline;">0</span>
| date } \]

\[ [CYCTIME](parameter_intro/cyctime)
= { <span style="text-decoration: underline;">0</span>
| time } \]

\[ [DELETE](parameter_intro/delete)
= { <span style="text-decoration: underline;">NO</span>
| YES } \]

\[ [DIRNB](parameter_intro/dirnb)
= { <span style="text-decoration: underline;">0</span>
| n } \]

\[ [DUPLICATE](parameter_intro/duplicat) = { string 512 } \]

\[ [EXEC](parameter_intro/exec)
= filename \]

\[ EXECRALL = { <u>all</u> | parent| children} \]

\[ [EXIT](parameter_intro/exit)
= identifier  \]

\[ [FACC](parameter_intro/facc)
= { <span style="text-decoration: underline;">‘
‘</span> | character } \]

\[ [FACTION](parameter_intro/faction)
= { <span style="text-decoration: underline;">‘
‘</span> | DELETE | ERASE |  RENAME | VERIFY  } \]

\[ [FBLKSIZE](parameter_intro/fblksize)
= { <span style="text-decoration: underline;">0</span>
| n } \]

\[ [FCHECK](parameter_intro/fcheck)
= { <span style="text-decoration: underline;">NO</span>
| YES } \]

\[ [FCODE](parameter_intro/fcode)
= { <span style="text-decoration: underline;">‘
‘</span> |BINARY | EBCDIC | ASCII } \]

\[ FDB
= filename \]

\[ [FDELETE](parameter_intro/fdelete) = <u>" "</u> |\* | C |D | K | H | T | X\]

\[ [FDISP](parameter_intro/fdisp)
= { <span style="text-decoration: underline;">BOTH</span>
| NEW | OLD } \]

\[ FILENOTFOUND = { <u>ABORT</u> | IGNORE } \]

\[ [FKEYLEN](parameter_intro/fkeylen)
= { <span style="text-decoration: underline;">0</span>
| n } \]

\[ [FKEYPOS](parameter_intro/fkeypos)
= { <span style="text-decoration: underline;">0</span>
| n } \]

\[ [FLOWNAME](parameter_intro/flowname) = string \]

\[ [FLRECL](parameter_intro/flrec)
=  { <span style="text-decoration: underline;">0</span>
| n  } \]

\[ [FNAME](parameter_intro/fname)
= filename \]

\[ [FORCE](parameter_intro/force)
= { <span style="text-decoration: underline;">NO</span>
| YES }  \]

\[ [FORG](parameter_intro/forg)
= { <span style="text-decoration: underline;">SEQ</span>
| DIRECT | INDEXED | PART } \]

\[ [FPAD](parameter_intro/fpad) = { <u>' '</u> | character } \]

\[ [FRECFM](parameter_intro/frecfm)
= { <span style="text-decoration: underline;">‘
‘</span> |F | V | U } \]

\[ [FSPACE](parameter_intro/fspace)
=  { <span style="text-decoration: underline;">0</span>
| n } \]

\[ [FTYPE](parameter_intro/ftype)
=  { <span style="text-decoration: underline;">‘
‘</span> | character } \]

\[ [GROUPID](parameter_intro/groupid)
= string \]

\[ [MACTION](parameter_intro/maction)
=  { <span style="text-decoration: underline;">'
'</span> | REPLACE } \]

\[ [MAXDATE](parameter_intro/maxdate)
=  { <span style="text-decoration: underline;">99991231</span>
| date } \]

\[ MAXDURATION = ** **{<u>0</u>...32767} \]

\[ [MAXTIME](parameter_intro/maxtime)
= { <span style="text-decoration: underline;">23595999</span>
| time } \]

\[ [MINDATE](parameter_intro/mindate)
= { <span style="text-decoration: underline;">10000101</span>
| date } \]

\[ [MINTIME](parameter_intro/mintime)
= { <span style="text-decoration: underline;">0</span>
| time } \]

\[ [MODE](parameter_intro/mode)
= { <span style="text-decoration: underline;">REPLACE</span>
| CREATE | DELETE } \]

\[ [NCOMP](parameter_intro/ncomp)
= { 0 | <span style="text-decoration: underline;">15</span>
} \]

\[ [NETBAND](parameter_intro/netband) = { 1...16} \]

\[ [NOTIFY](parameter_intro/notify)
= string \]

\[ [NPAD](parameter_intro/npad) = { <u>' '</u> | character } \]

\[ [NCODE](parameter_intro/ncode)
= { <span style="text-decoration: underline;">‘
‘</span> |ASCII | BINARY | EBCDIC } \] \*available only when the protocol is SFTP

\[ [OPERMSG](parameter_intro/opermsg)
= { <span style="text-decoration: underline;">0</span>
| 255 } \]

\[ [PRI](parameter_intro/pri)
= { 128 | n } \]

\[ [RAPPL](parameter_intro/rappl)
= string \]

\[ [RKERROR](parameter_intro/rkerror)
= { ' ' | DELETE | KEEP } \]

\[ [RPASSWD](parameter_intro/rpassw) = string \]

\[ [RUSER](parameter_intro/ruser)
= string \]

\[ [SAPPL](parameter_intro/sappl)
= string \]

\[ [SERIAL](parameter_intro/serial) = { <u>' '</u> | Y | Z | X } \]

\[ [SOURCEAPPL](parameter_intro/sourceappl) =  string \]

\[ [SPASSWD](parameter_intro/spasswd) = string \]

\[ [STATE](parameter_intro/state)
= { DISP | HOLD | KEEP } \]

\[ [STORAGEACCOUNT](parameter_intro/storageaccount) = string \]

\[ [SUSER](parameter_intro/suser)
= string \]

\[ [TARGETAPPL](parameter_intro/targetappl) = string \]

\[ [TRK](parameter_intro/trk)
=  { UNDEFINED
| ALL | SUMMARY | NO } \]

\[ [USERID](parameter_intro/userid)
= { CFT server"userid" | string } \]

\[ [WFNAME](parameter_intro/wfname)
= filename \]

\[ [WORKINGDIR](parameter_intro/workingdir) = string \]

\[ [XLATE](parameter_intro/xlate)
= identifier \]

<span style="font-weight: bold;"> </span>[CFTRECV details](../web_copilot_ui/flow_def_intro/cftrecv)

<span id="CFTSEND"></span>

#### CFTSEND ID= identifier: Description of model file sending parameters

Syntax

\[ [ACKEXEC](parameter_intro/ackexec) = filename\]

\[ ARCHIVEFNAME = string \]

\[ [COMMENT](parameter_intro/comment)
= string \]

\[ [CYCDATE](parameter_intro/cycdate)
= { <span style="text-decoration: underline;">0</span>
| date } \]

\[ [CYCLE](parameter_intro/cycle)
= { <span style="text-decoration: underline;">0</span>
| n } \]

\[ [CYCTIME](parameter_intro/cyctime)
= { <span style="text-decoration: underline;">0</span>
| time } \]

\[ [DELETE](parameter_intro/delete)
= { <span style="text-decoration: underline;">NO</span>
| YES } \]

\[ [DUPLICATE](parameter_intro/duplicat) = { string 512 } \]

\[ [EXEC](parameter_intro/exec)
= filename \]

\[ [EXECSUB](parameter_intro/execsub)
= { <span style="text-decoration: underline;">LIST</span>
| FILE | SUBF } \]

\[ [EXECSUBA](parameter_intro/execsuba) = {LIST | FILE | <u>SUBF</u> } \]

\[ [EXECSUBPRE](parameter_intro/execsubpre) = { <span style="text-decoration: underline;">LIST</span>
| FILE | SUBF } \]

\[ [EXIT](parameter_intro/exit)
=  identifier
\]

\[ [FACC](parameter_intro/facc)
= { <span style="text-decoration: underline;">‘
‘</span> | character } \]

\[ [FACTION](parameter_intro/faction)
= { <span style="text-decoration: underline;">NONE</span>
| DELETE | ERASE | ARCHIVE } \]

\[ [FBLKSIZE](parameter_intro/fblksize)
= { <span style="text-decoration: underline;">0</span>
| n } \]

\[ [FCODE](parameter_intro/fcode)
= { <span style="text-decoration: underline;">‘
‘</span> |ASCII | BINARY | EBCDIC } \]

\[ FDB
= filename \]

\[ [FDELETE](parameter_intro/fdelete) = <u>" "</u> |\* | C |D | K | H | T | X\]

\[ [FDISP](parameter_intro/fdisp)
= { <span style="text-decoration: underline;">SHR</span>
| OLD | CHECK } \]

\[ FILENOTFOUND =  { <u>ABORT</u> | IGNORE } \]

\[ [FILTER](parameter_intro/filter) = string \]

\[ [FILTERTYPE](parameter_intro/filtertype) = string \]

\[ [FKEYLEN](parameter_intro/fkeylen)
= { <span style="text-decoration: underline;">0</span>
| n } \]

\[ [FKEYPOS](parameter_intro/fkeypos)
= { <span style="text-decoration: underline;">0</span>
| n } \]

\[ [FLOWNAME](parameter_intro/flowname) = string \]

\[ [FLRECL](parameter_intro/flrec)
= { <span style="text-decoration: underline;">0</span>
| n } \]

\[ [FNAME](parameter_intro/fname)
 = { <span style="text-decoration: underline;">filename</span>
| mask | dirname | #filename | #mask | #dirname } \]

\[ [FORCE](parameter_intro/force)
= { <span style="text-decoration: underline;">NO</span>
| YES } \]

\[ [FORG](parameter_intro/forg)
= { <span style="text-decoration: underline;">SEQ</span>
| DIRECT | INDEXED | PART } \]

\[ [FPAD](parameter_intro/fpad) = { <u>' '</u> | character } \]

\[ [FRECFM](parameter_intro/frecfm)
= { <span style="text-decoration: underline;">‘
‘</span> | F | U | V } \]

\[ [FSPACE](parameter_intro/fspace)
= { <span style="text-decoration: underline;">0</span>
| n } \]

\[ [FTYPE](parameter_intro/ftype)
= { <span style="text-decoration: underline;">‘
‘</span> | character } \]

\[ [GROUPID](parameter_intro/groupid)
= string \]

\[ [IDA](parameter_intro/ida) = string \]

\[ [IMPL](parameter_intro/impl)
= { <span style="text-decoration: underline;">NO</span>
| YES } \]

\[ [MAXDATE](parameter_intro/maxdate)
=  { <span style="text-decoration: underline;">99991231</span>
| date } \]

\[ MAXDURATION = ** **{<u>0</u>...32767} \]

\[ [MAXTIME](parameter_intro/maxtime)
= { <span style="text-decoration: underline;">23595999</span>
| time } \]

\[ [MINDATE](parameter_intro/mindate)
= { <span style="text-decoration: underline;">10000101</span>|
date } \]

\[ [MINTIME](parameter_intro/mintime)
= { <span style="text-decoration: underline;">0</span>
| time } \]

\[ [MODE](parameter_intro/mode)
= { <span style="text-decoration: underline;">REPLACE</span>
| CREATE | DELETE } \]

\[ [NBLKSIZE](parameter_intro/nblksize)
= { <span style="text-decoration: underline;">0</span>
| n } \]

\[ [NCODE](parameter_intro/ncode)
= { <span style="text-decoration: underline;">‘
‘</span> |ASCII | BINARY | EBCDIC } \]

\[ [NCOMP](parameter_intro/ncomp)
=  { 0 |
<span style="text-decoration: underline;">15</span>
} \]

\[ [NETBAND](parameter_intro/netband)
= { 1...16} \]

\[ [NFNAME](parameter_intro/nfname)
=  { filename
| \*filename } \]

\[ [NKEYLEN](parameter_intro/nkeylen)
= { <span style="text-decoration: underline;">0</span>
| n } \]

\[ [NKEYPOS](parameter_intro/nkeypos)
= { <span style="text-decoration: underline;">0</span>|
n } \]

\[ [NLRECL](parameter_intro/nlrecl)
=  { <span style="text-decoration: underline;">0</span>
| n } \]

\[ [NOTIFY](parameter_intro/notify)
= string  \]

\[ [NPAD](parameter_intro/npad) = { <u>' '</u> | character } \]

\[ [NRECFM](parameter_intro/nrecfm)
= { <span style="text-decoration: underline;">‘
‘</span> | F | U | V } \]

\[ [NSPACE](parameter_intro/nspace)
=  { <span style="text-decoration: underline;">0</span>
| n } \]

\[ [NTYPE](parameter_intro/ntype)
= character \]

\[ [OPERMSG](parameter_intro/opermsg)
= { <span style="text-decoration: underline;">0</span>
| 255 } \]

\[ [PARM](parameter_intro/parm)
= string  \]

\[ [PREEXEC](parameter_intro/preexec) = filename \]

\[ [PRI](parameter_intro/pri)
= { <span style="text-decoration: underline;">128</span>
| n } \]

\[ [RAPPL](parameter_intro/rappl)
= string \]

\[ [RPASSWD](parameter_intro/rpassw) = string \]

\[ [RUSER](parameter_intro/ruser)
= string \]

\[ [SAPPL](parameter_intro/sappl)
= string \]

\[ [SELFNAME](parameter_intro/selfname)
= filename \]

\[ [SERIAL](parameter_intro/serial) = { <u>' '</u> | Y | Z | X } \]

\[ [SPART](parameter_intro/spart)
= string \]

\[ [SPASSWD](parameter_intro/spasswd) = string \]

\[ [SOURCEAPPL](parameter_intro/sourceappl) =  string \]

\[ [STATE](parameter_intro/state)
= { <span style="text-decoration: underline;">DISP</span>
| HOLD | KEEP } \]

\[ [STORAGEACCOUNT](parameter_intro/storageaccount) = string \]

\[ [SUSER](parameter_intro/suser)
= string \]

\[ [](parameter_intro/targetappl)[TARGETAPPL](parameter_intro/targetappl) = string \]

\[ [TCYCLE](parameter_intro/tcycle)
= { <span style="text-decoration: underline;">DAY</span>
| MIN | MONTH } \]

\[ [TRK](parameter_intro/trk)
=  { <span style="text-decoration: underline;">UNDEFINED</span>
| ALL | SUMMARY | NO } \]

\[ [USERID](parameter_intro/userid)
= { <span style="text-decoration: underline;">CFT
server "userid"</span> | string } \]

\[ [WFNAME](parameter_intro/wfname)
= filename \]

\[ [WORKINGDIR](parameter_intro/workingdir) = string \]

\[ [XLATE](parameter_intro/xlate)
= identifier \]

[CFTSEND details](../web_copilot_ui/flow_def_intro/cftsend)

[Send
file template](../../concepts/cft_configuration_concepts_start_here/default_send_template_concepts)

<span id="CFTSSL"></span>

#### CFTSSL ID = identifier: Security files

Syntax

[CIPHLIST](parameter_intro/ciphlist)
= ( number, number, …)

[DIRECT](parameter_intro/direct)
= { <span style="text-decoration: underline;">CLIENT</span>
| SERVER }

\[ [CACHE](parameter_intro/cache)
= { <span style="text-decoration: underline;">NO</span>
| YES } \]

\[ CERFNAME
= string \]

\[ [COMMENT](parameter_intro/comment)
= string \]

\[ DEPTH
= { <span style="text-decoration: underline;">10</span>
| n } \]

\[ [DNISSUER](parameter_intro/dnissuer)
= ( string, string, …) \]

\[ [DNUSER](parameter_intro/dnuser)
= { ( string, string, …) | ( string, OP ([see Note](#*OP)), string ) } \]

\[ [INTERCID](parameter_intro/intercid)
= string \]

\[ [KEYEXT](parameter_intro/keyext) = { VERIFY | NONE } \]

\[ [MODE](parameter_intro/mode)
= { <span style="text-decoration: underline;">REPLACE</span>
| CREATE | DELETE } \]

\[ [PARM](parameter_intro/parm)
= string \]

\[ [PASSW](parameter_intro/passw) = string \]

\[ [ROOTCID](parameter_intro/rootcid)
= ( string, string, …) \]

\[ [TRACE](parameter_intro/trace)
= { <span style="text-decoration: underline;">0</span>
| n } \]

\[ [USERCID](parameter_intro/usercid)
= string \]

\[ [VERIFY](parameter_intro/verify)
= { NONE| <span style="text-decoration: underline;">REQUIRED</span>
| OPTIONAL } \] *\*When DIRECT=SERVER*

\[ [VERIFY](parameter_intro/verify)
= { <u>NONE</u>| <span style="text-decoration: none;">REQUIRED</span>
| ENFORCED | OPTIONAL } \] *\*When DIRECT=CLIENT *

\[ [VERSION](parameter_intro/version)
= { <u>TLSV1</u>  | SSLV3 | TLSV1 | SSLV3COMP | TLSV1COMP} \]

<span style="font-weight: bold;">Note</span>: <span id="OP"></span>You can configure Transfer
CFT to accept or reject SSL connections based on logical operators used
within the DN of the certificate. For details refer to [dnuser](parameter_intro/dnuser)
parameter details.

[CFTSSL details](../../transport_security_start_here/configuring_transport_security_start_here/transport_security_cftssl)

[SSL/TLS security concepts](../../transport_security_start_here)

<span id="CFTTCP"></span>

#### CFTTCP: Network parameters of a TCP/IP partner

Syntax

[HOST](parameter_intro/host)
= string

[ID](parameter_intro/id)
= identifier

\[ [CLASS](parameter_intro/class)
= { <span style="text-decoration: underline;">1</span>
| n } \]

\[ [CNXIN](parameter_intro/cnxin)
= { <span style="text-decoration: underline;">2</span>
| n } \]

\[ [CNXINOUT](parameter_intro/cnxinout)
= { <span style="text-decoration: underline;">4</span>
| n } \]

\[ [CNXOUT](parameter_intro/cnxout)
= { <span style="text-decoration: underline;">2</span>
| n } \]

\[ [IMAXTIME](parameter_intro/imaxtime)
= { <span style="text-decoration: underline;">23595999</span>
| time } \]

\[ IMINTIME
= { <span style="text-decoration: underline;">0</span>
| time } \]

\[ [MODE](parameter_intro/mode)
= { <span style="text-decoration: underline;">REPLACE</span>
| CREATE | DELETE } \]

\[ [OMAXTIME](parameter_intro/omaxtime)
= { <span style="text-decoration: underline;">23595999</span>
| time } \]

\[ [OMINTIME](parameter_intro/omintime)
= { <span style="text-decoration: underline;">0</span>
| time } \]

\[ [RETRYM](parameter_intro/retrym)
= { <span style="text-decoration: underline;">12</span>
| n } \]

\[ [RETRYN](parameter_intro/retryn)
= { <span style="text-decoration: underline;">4</span>
| n } \]

\[ [RETRYW](parameter_intro/retryw)
= { <span style="text-decoration: underline;">1</span>
| n } \]

\[ [VERIFY](parameter_intro/verify)
= { <span style="text-decoration: underline;">0</span>
| n } \]

[TCP
attributes for a partner](../../admin_intro/admin_config_commands/network_resource_concepts)

<span id="CFTUIPREF"></span>

#### CFTUIPREF MODE=mode

MODE= { CREATE | <u>REPLACE</u> | DELETE }

[ID](parameter_intro/id)
= identifier  

[TYPE](parameter_intro/type) = string

\[ [COMMENT](parameter_intro/comment)
= string \]

\[ [CONTENT](parameter_intro/content)
= { <span style="text-decoration: underline;">ACTIVE</span>
| FULL } \]

\[ [ORIGIN](parameter_intro/origin) \] = string \]

<span id="CFTXLATE"></span>

#### CFTXLATE FNAME = filename: Define conversion tables

Syntax

[ID](parameter_intro/id)
= identifier  

\[ [COMMENT](parameter_intro/comment)
= string \]

\[ [DIRECT](parameter_intro/direct)
= { <span style="text-decoration: underline;">BOTH</span>
| RECV | SEND } \]

\[ [FCODE](parameter_intro/fcode)
= { <span style="text-decoration: underline;">'
'</span> | ASCII | EBCDIC } \]

\[ [MODE](parameter_intro/mode)
= { <span style="text-decoration: underline;">REPLACE</span>
| CREATE | DELETE } \]

\[ [NCODE](parameter_intro/ncode)
= { <span style="text-decoration: underline;">'
'</span> | ASCII | EBCDIC } \]

\[ [ORIGIN](parameter_intro/origin) \] = string \]

\[ TABLE \] = string \]

[Conversion
tables](../../concepts/cft_configuration_concepts_start_here/translation_table_concepts)

<span id="CLEARCMD"></span>

#### CLEARCMD COMMAND = string: Delete a transfer request

Syntax

[USERID](parameter_intro/userid)
= string

INDEX
= number

[CLEARCMD details](../about_cftutil/managing_transfer_states/clearcmd_command)

<span id="CONFIG"></span>

#### CONFIG: Designate the communication medium and the files accessed by CFTUTIL

<span style="font-weight: normal;">Syntax</span>

CONFIG TYPE = { CAT | INPUT | OUTPUT | PARM | PART }

[<span style="font-weight: normal;">FNAME</span>](parameter_intro/fname)<span style="font-weight: normal;"> = filename </span>

 

CONFIG TYPE = COM

MEDIACOM = FILE

[<span style="font-weight: normal;">FNAME</span>](parameter_intro/fname)<span style="font-weight: normal;"> = filename </span>

 

<span style="font-family: Arial, sans-serif;font-size: 10pt;">CONFIG
TYPE = COM</span>

MEDIACOM
= TCPIP

[<span style="font-weight: normal;">FNAME</span>](parameter_intro/fname)<span style="font-weight: normal;">= string </span>

\[ [HIGHPORT](parameter_intro/highport)
=  { <span style="text-decoration: underline;">65535</span>
| n } \]

\[ [LOWPORT](parameter_intro/lowport)
= { <span style="text-decoration: underline;">5000</span>
| n } \]

\[ PASSWORD = string } \]

\[ PROXY
= string \]

\[ [ROOTCERT](parameter_intro/rootcert)
= string \]

\[ [TIMEOUT](parameter_intro/timeout)
= <span style="text-decoration: underline;">60</span>
| n \]

[Setting default CFTUTIL file names](../about_cftutil/redefining_cftutil_data_media)

<span id="COPYFILE"></span>

#### COPYFILE IFNAME = filename: Copy files with an off-line compression or decompression option

Syntax

[OFNAME](parameter_intro/ofname)
= filename

\[ [CREATE](parameter_intro/create)
= { <span style="text-decoration: underline;">‘
‘</span> | YES | NO } \]

\[ [IBLKSIZE](parameter_intro/iblksize)
= { <span style="text-decoration: underline;">0</span>
| n } \]

\[ ICHARSET = string \]

\[ [ICODE](parameter_intro/icode)
= { ASCII | EBCDIC } \]

\[ [ICOMP](parameter_intro/icomp)
= { <span style="text-decoration: underline;">0</span>
| 15 } \]

\[ [ICT](parameter_intro/ict)
=  { <span style="text-decoration: underline;">H</span>
| C } \]

\[ [ILRECL](parameter_intro/ilrecl)
= { <span style="text-decoration: underline;">0</span>
| n } \]

\[ [IRECFM](parameter_intro/irecfm)
= { F | V | U } \]

\[ [ITYPE](parameter_intro/itype)
= { ‘ ‘ | character } \]

\[ [OBLKSIZE](parameter_intro/oblksize)
= { 0 |n  }
\]

\[ OCHARSET = string \]

\[ [OCODE](parameter_intro/ocode)
= { ASCII | EBCDIC } \]

\[ [OCOMP](parameter_intro/ocomp)
= { <span style="text-decoration: underline;">0</span>
| 15 } \]

\[ [OCT](parameter_intro/oct)
= { H | C } \]

\[ [OLRECL](parameter_intro/olrecl)
= { <span style="text-decoration: underline;">0</span>
|n } \]

\[ [ORECFM](parameter_intro/orecfm)
= { <span style="text-decoration: underline;">IRECFM
value</span> | F | V| U } \]

\[ [OSPACE](parameter_intro/ospace)
= { <span style="text-decoration: underline;">0</span>
| n } \]

\[ [OTYPE](parameter_intro/otype)
= { <span style="text-decoration: underline;">‘
‘</span> | character } \]

\[ [XLATE](parameter_intro/xlate) = string \]

[Copying files off-line](../../admin_intro/admin_commands_intro/copyfile_command)

<span id="DELETE"></span>

#### DELETE PART = { identifier | mask }: Delete a catalog entry

Syntax

\[ [BLKNUM](parameter_intro/blknum)
= { <span style="text-decoration: underline;">0</span>
| n } \]

\[ [DIRECT](parameter_intro/direct)
= { <span style="text-decoration: underline;">BOTH</span>
| RECV | SEND } \]

\[ [FORCE](parameter_intro/force)
=  { YES
| <span style="text-decoration: underline;">NO</span>
} \]

\[ [IDA](parameter_intro/ida)
= identifier  \]

\[ [IDF](parameter_intro/idf)
= identifier \]

\[ [IDT](parameter_intro/idu)
= { <span style="text-decoration: underline;">\*</span>
| transid } \]

\[ [IDTU](parameter_intro/idtu)
= string \]

\[ [STATE](parameter_intro/state)
= { <span style="text-decoration: underline;">\*</span>
| C | D | H | K | T | X } \]

\[ KDATE
= { <span style="text-decoration: underline;">0</span>
| n } \]

\[ KTIME
= { <span style="text-decoration: underline;">0</span>
| n } \]

\[ PHASE = string \]

\[ PHASESTEP = string \]

\[ [SCOPE](parameter_intro/scope) = string \]

[Deleting catalog entries](../../admin_intro/admin_commands_intro/delete_command)

<span id="DISPLAY"></span>

#### DISPLAY \[ CONTENT = { <span style="text-decoration: underline;">listcat</span> | identifier }\]: Display a model-formatted catalog

Syntax

\[ [DATETIMEMAX](parameter_intro/datetimemax) = { 0 | <u>991231235959</u> } \]

\[ [DATETIMEMIN](parameter_intro/datetimemin) = { <u>0</u> | 991231235959 } \]

\[ [DIAGI](parameter_intro/diagi) = { <u>\*</u> | 0 | ERROR } \]

\[ [DIRECT](parameter_intro/direct)
= { <span style="text-decoration: underline;">BOTH</span>
| RECV | SEND } \]

\[ [EMPTY](parameter_intro/empty)
= { <span style="text-decoration: underline;">ANY</span>
| string } \]

\[ [FILE](parameter_intro/file)
= filename \]

\[ [FMODEL](parameter_intro/fmodel)
=  string
\]

\[ [FOUT](parameter_intro/fout) = string \]

\[ [HELP](parameter_intro/help)
= { <span style="text-decoration: underline;">NONE</span>
| FIELDS | MODELS | COMMAND } \]

\[ [IDA](parameter_intro/ida)
=  string
\]

\[ [IDF](parameter_intro/idf)
= string \]

\[ [IDT](parameter_intro/idu)
= string \]

\[ [IDTU](parameter_intro/idtu)
= string \]

\[ [MODE](parameter_intro/mode)
= { <span style="text-decoration: underline;">ANY</span>
| COLUMN | LINE } \]

\[ [NA](parameter_intro/na)
= { <span style="text-decoration: underline;">ANY</span>
| string } \]

\[ NIDT 
= { string of 8 digits } \]

\[ [NPART](parameter_intro/npart)
= string \]

\[ [PART](parameter_intro/part)
= string \]

\[ [RUSER](parameter_intro/ruser)
= string \]

\[ [SORTBY](parameter_intro/sortby)
= string \]

\[ [SUSER](parameter_intro/suser)
= string \]

\[ [STATE](parameter_intro/state)
= { <span style="text-decoration: underline;">\*</span>
| character } \]

\[ [TYPE](parameter_intro/type)
= { <span style="text-decoration: underline;">\*</span>
| FILE | MESSAGE | REPLY | ALL } \]

[Catalog output display model](../about_cftutil/monitoring_cftutil_intro/display_command)

<span id="END"></span>

#### END PART = { identifier | mask }: Change transfer to X state

Syntax

\[ [APPCYCID](parameter_intro/appcycid)  
= string \]

\[ [APPOBJID](parameter_intro/appobjid)  
= string \]

\[ APPSTATE  
= string \]

\[ [SAPPL](parameter_intro/sappl)  
= string \]

\[ [RUSER](parameter_intro/ruser)  
= string \]

\[ [SUSER](parameter_intro/suser)  
= string \]

\[ [RPASSWD](parameter_intro/rpassw)  
= string \]

\[ [SPASSWD](parameter_intro/spasswd)  
= string \]

\[ [BLKNUM](parameter_intro/blknum)
= { <span style="text-decoration: underline;">0</span>
| n } \]

\[ DIAGC = string \]

\[ [DIRECT](parameter_intro/direct)
= { <span style="text-decoration: underline;">BOTH</span>
| RECV | SEND } \]

\[ [FORCE](parameter_intro/force)
= { <span style="text-decoration: underline;">NO</span>
| YES } \]

\[ [FNAME](parameter_intro/fname)  
= string \]

\[ [IDA](parameter_intro/ida)
= identifier \]

\[ [IDF](parameter_intro/idf)
= identifier \]

\[ [IDT](parameter_intro/idu)
= { <span style="text-decoration: underline;">\*</span>
| transid } \]

\[ [IDTU](parameter_intro/idtu)
= string \]

\[ ISTATE = { YES | <u>NO</u> } \]

\[ ISTATE  
= string \]

\[ KDATE
= { <span style="text-decoration: underline;">0</span>
| n } \]

\[ KTIME
= { <span style="text-decoration: underline;">0</span>
| n } \]

\[ [NFNAME](parameter_intro/nfname)  
= string \]

\[ [PARM](parameter_intro/parm)  
= string \]

\[ PHASE = string \]

\[ PHASESTEP = string \]

\[ [PRI](parameter_intro/pri) Number { 0 - <u>256</u> } \]

\[ [RAPPL](parameter_intro/rappl)  
= string \]

\[ [SCOPE](parameter_intro/scope) = string \]

\[ [SIGFNAME](parameter_intro/sigfname)  
= string \]

\[ [STATE](parameter_intro/state)  = string \]

[END details](../about_cftutil/managing_transfer_states/end_command)

<span id="HALT"></span>

#### HALT PART = { identifier | mask }: Suspend a transfer

Syntax

\[ [BLKNUM](parameter_intro/blknum)
= { <span style="text-decoration: underline;">0</span>
| n } \]

\[ DIAGC = string \]

\[ [DIAGP](parameter_intro/diagp) = string \]

\[ [DIRECT](parameter_intro/direct)
= { <span style="text-decoration: underline;">BOTH</span>
| RECV | SEND } \]

\[ [FORCE](parameter_intro/force)
= { YES | <span style="text-decoration: underline;">NO</span>
} \]

\[ [IDA](parameter_intro/ida)
= identifier  \]

\[ [IDF](parameter_intro/idf)
= identifier  \]

\[ [IDT](parameter_intro/idu)
= { <span style="text-decoration: underline;">\*</span>
| transid } \]

\[ [IDTU](parameter_intro/idtu)
= string  \]

\[ [STATE](parameter_intro/state)  = string \]

\[ KDATE
= { <span style="text-decoration: underline;">0</span>
| n } \]

\[ KTIME
= { <span style="text-decoration: underline;">0</span>
| n } \]

\[ PHASE = string \]

\[ PHASESTEP = string \]

\[ [SCOPE](parameter_intro/scope) = string \]

[Halting a transfer](../about_cftutil/managing_transfer_states/halt_command)

#### HELP

Syntax

\[ CMD = { string } \]

\[ CONTENT = { <u>BRIEF</u> | DETAIL} \]

\[ OFORMAT = { <u>txt</u> | xsd } \]

<span id="INACT"></span>

#### INACT ID = identifier: Inactivate a partner

Syntax

\[ [MODE](parameter_intro/mode)
= { <span style="text-decoration: underline;">BOTH</span>
| REQUESTER| SERVER } \]

\[ [FORCE](parameter_intro/force)
= { <span style="text-decoration: underline;">NO</span>
| YES } \]

\[ [TYPE](parameter_intro/type)
= <span style="text-decoration: underline;">PART</span>
| TRK | CRON | FOLDER \]

[INACT details](../about_cftutil/reactivate_an_object_cl/inact_command)

<span id="KEEP"></span>

#### KEEP PART = { identifier | mask }: Abort a transfer

Syntax

\[ [BLKNUM](parameter_intro/blknum)
= <span style="text-decoration: underline;">0</span>
| n \]

\[ DIAGC = string \]

\[ [DIAGP](parameter_intro/diagp) = string \]

\[ [DIRECT](parameter_intro/direct)
= { <span style="text-decoration: underline;">BOTH</span>
| RECV | SEND } \]

\[ [FORCE](parameter_intro/force)
= { <span style="text-decoration: underline;">YES</span>
| NO } \]

\[ [IDA](parameter_intro/ida)
= identifier  \]

\[ [IDF](parameter_intro/idf)
= identifier \]

\[ [IDT](parameter_intro/idu)
= { <span style="text-decoration: underline;">\*</span>
| transid } \]

\[ [IDTU](parameter_intro/idtu)
= string  \]

\[ [STATE](parameter_intro/state)
= string \]

\[ KDATE
= { <span style="text-decoration: underline;">0</span>
| n } \]

\[ KTIME
= { <span style="text-decoration: underline;">0</span>
| n } \]

\[ PHASE = string \]

\[ PHASESTEP = string \]

\[ [SCOPE](parameter_intro/scope) = string \]

<span style="font-weight: bold;"> </span>[Suspend transfers](../about_cftutil/managing_transfer_states/keep_command)

<span id="KSTATE"></span>

#### KSTATE IDF = identifier: Change a transfer state

Syntax

[IDTU](parameter_intro/idtu)
= local transfer counter identifier

[PART](parameter_intro/part)
= partner identifier

[KSTATE details](../about_cftutil/managing_transfer_states/kstate_command)

<span id="LISTCAT"></span>

#### LISTCAT TYPE = { <span style="text-decoration: underline;">ALL</span> | \* | FILE | MESSAGE | REPLY }: List catalog entries

Syntax

\[ [CONTENT](parameter_intro/content)
= { <span style="text-decoration: underline;">BRIEF</span>
| FULL | DEBUG | EXTEND | COMMUT | STAT | BLKNUM } \]

\[ [DATETIMEMAX](parameter_intro/datetimemax) = { 0 | <u>991231235959</u> } \]

\[ [DATETIMEMIN](parameter_intro/datetimemin) = { <u>0</u> | 991231235959 } \]

\[ [DIAGI](parameter_intro/diagi) = { <u>\*</u> | 0 | ERROR } \]

\[ [DIRECT](parameter_intro/direct)
= { <span style="text-decoration: underline;">BOTH</span>
| RECV | SEND } \]

\[ [FILE](parameter_intro/file)
= filename \]

\[ [IDA](parameter_intro/ida)
= { <span style="text-decoration: underline;">\*</span>
| identifier } \]

\[ [IDF](parameter_intro/idf)
= { <span style="text-decoration: underline;">\*</span>
| identifier } \]

\[ [IDT](parameter_intro/idu)
= { <span style="text-decoration: underline;">\*</span>
| transid } \]

\[ [IDTU](parameter_intro/idtu)
= string  \]

\[ NIDT 
= { string of 8 digits } \]

\[ [NPART](parameter_intro/npart)
= { identifier | mask } \]

\[ [PART](parameter_intro/part)
= { <span style="text-decoration: underline;">\*</span>
| identifier | mask } \]

\[ [SORTBY](parameter_intro/sortby)
= string \]

\[ [STATE](parameter_intro/state)
= { <span style="text-decoration: underline;">\*</span>
| string } \]

<span style="font-weight: bold;"> </span>[LISTCAT details](../about_cftutil/monitoring_cftutil_intro/listcat_command)

<span id="LISTCOM"></span>

#### LISTCOM: Display contents of a communication media

Syntax

\[ [CONTENT](parameter_intro/content)
= { <span style="text-decoration: underline;">ACTIVE</span>
| FULL } \]

\[ [FILE](parameter_intro/file)
= filename \]

\[ FIRST
= { <span style="text-decoration: underline;">0</span>
| n } \]

\[ LAST
= { <span style="text-decoration: underline;">0</span>
| max. number of records } \]

\[ [VERIFY](parameter_intro/verify)
= { <span style="text-decoration: underline;">NO</span>
| YES } \]

<span style="font-weight: bold;"> </span>[LISTCOM details](../about_cftutil/monitoring_cftutil_intro/listcom_command)<span style="font-weight: bold;"> </span>

<span id="LISTLOG"></span>

#### LISTLOG: Display and filter log content including merged nodes in cluster mode

Syntax

\[ LOGLEVEL = { F | E | W | <u>I</u> } \]

\[ LINES = { -10000 | <u>-20</u> | 10000 } \]

\[ [DATEMAX](parameter_intro/datemin_datemax) =  { 0 | <u>991231</u> } \]

\[ [DATEMIN](parameter_intro/datemin_datemax)           = { <u>0</u> | 991231 } \]

\[ [DATETIMEMAX](parameter_intro/datetimemax) = { 0 | <u>99123123595999</u> } \]

\[ [DATETIMEMIN](parameter_intro/datetimemin) { <u>0</u> | 99123123595999 } \]

\[ TIMEMIN = { <u>0</u>| 23595999 } \]

\[ TIMEMAX           = { 0 | <u>23595999</u> } \]

\[ PATTERN           =     string \]

\[ DISPLAYNODEID     = { <u>YES</u> | NO } \]

\[ NODE = string \]

#### LISTNODE: Display all nodes

Syntax

No parameters

[Multi-node commands](../../about_multinode/multi_node_commands)

<span id="LISTPARM"></span>

#### LISTPARM: Display  <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> partner details

Syntax

\[ [ID](parameter_intro/id)
= { <span style="text-decoration: underline;">\*</span>
| identifier } \]

\[ [CONTENT](parameter_intro/content)
= { <span style="text-decoration: underline;">FULL</span>
| BRIEF } \]

\[ [PART](parameter_intro/part)
= identifier  \]

\[ [TYPE](parameter_intro/type)
= { ACCNT | <span style="text-decoration: underline;">ALL</span>
| APPL | AUTH | CAT | COM | CRON | EXIT | IDF | LOG | NET | PARM | PROT
| RECV | SEND | SSL | XLATE } \]

[LISTPARM details](../about_cftutil/configuring_cft_start_here/listparm)

<span id="LISTPART"></span>

#### LISTPART: Display partners

Syntax

\[ [ID](parameter_intro/id)
= { <span style="text-decoration: underline;">\*</span>
|identifier } \]

\[ [CONTENT](parameter_intro/content)
= { <span style="text-decoration: underline;">FULL</span>
| BRIEF } \]

\[ [TYPE](parameter_intro/type)
= { <span style="text-decoration: underline;">ALL</span>
| DEST |  PART |  TCP | } \]

[LISTPART details](../about_cftutil/configuring_cft_start_here/listpart_command)

<span id="MQUERY"></span>

#### MQUERY : Query one or more <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> components

Syntax

OBJECT = CACHE

\[ [OBJECT](parameter_intro/object)
= { <span style="text-decoration: underline;">CACHE</span>
| SYSTEM | STATS | PROBE } \]

\[ [CONTENT](parameter_intro/content)
= { <span style="text-decoration: underline;">BRIEF</span>
| FULL | STAT } \]

\[ [NAME](parameter_intro/name)
= { <span style="text-decoration: underline;">CAT</span>
| COMMAND | CRON | DMZ | STAT } \]

 

OBJECT = SYSTEM

\[ [OBJECT](parameter_intro/object)
= { <span style="text-decoration: underline;">CACHE</span>
| SYSTEM | STATS | PROBE } \]

\[ [CONTENT](parameter_intro/content)
= { <span style="text-decoration: underline;">BRIEF</span>
| FULL | STAT } \]

\[ [NAME](parameter_intro/name)
= { CFTMAIN | CFTTRK | CFTTFIL | CFTCOM | CFTTPRO | CFTEXIT | CFTPRX | CFTDSCAN } \]

 

OBJECT = STATS or PROBE

\[ [OBJECT](parameter_intro/object)
= { <span style="text-decoration: underline;">CACHE</span>
| SYSTEM | STATS | PROBE } \]

\[ [CONTENT](parameter_intro/content)
= { <span style="text-decoration: underline;">XMLBRIEF</span>
| XMLFULL | RAW } \]

\[ [NAME](parameter_intro/name)
= { <span style="text-decoration: underline;">CAT</span>
| COMMAND | CRON | DMZ | STAT } \]

<span style="font-weight: bold;"> </span>[MQUERY details](../../admin_intro/admin_commands_intro/querying_a_component_)

<span id="PURGE"></span>

#### PURGE: Delete records from the catalog 

Syntax

\[ [TIMEP](parameter_intro/timep)
= { <span style="text-decoration: underline;">23595999</span>
| time } \]

[PURGE details](../../admin_intro/admin_commands_intro/purge_catalog)

<span id="RECONFIG"></span>

#### RECONFIG: Reload

Syntax

\[ [TYPE](parameter_intro/type)
= { <span style="text-decoration: underline;">CRON</span> | UCONF | CAT |  FOLDER | PARMCACHE | AM
} \]

 [Manage configuration updates](../../admin_intro/admin_commands_intro/reconfig)

<span id="RECV"></span>

#### RECV IDF = { identifier | mask }: Request to receive transfer

Syntax

[PART](parameter_intro/part)
= identifier   

\[ [ACKEXEC](parameter_intro/ackexec) = filename\]

\[ [APPCYCID](parameter_intro/appcycid)
= string \]

\[ [APPOBJID](parameter_intro/appobjid)
= string \]

\[ [COMMENT](parameter_intro/comment)
= string  \]

\[ [CYCDATE](parameter_intro/cycdate)
=  date
 \]

\[ [CYCLE](parameter_intro/cycle)
=  { <span style="text-decoration: underline;">0</span>
| n } \]

\[ [CYCTIME](parameter_intro/cyctime)
= time \]

\[ [DACTION](parameter_intro/daction) = { <u>ERROR</u> | RESUME } \]

\[ [DIRNB](parameter_intro/dirnb)
= n \]

\[ [EXEC](parameter_intro/exec)
= filename \]

\[ EXECRALL = { <u>all</u> | parent| children} \]

\[ [EXIT](parameter_intro/exit)
= identifier  \]

\[ [FACC](parameter_intro/facc)
= { <span style="text-decoration: underline;">‘
‘</span> | character }  \]

\[ [FACTION](parameter_intro/faction)
= { <span style="text-decoration: underline;">‘
‘</span> | DELETE | ERASE | RENAME | VERIFY } \]

\[ [FBLKSIZE](parameter_intro/fblksize)
= n \]

\[ [FCODE](parameter_intro/fcode)
= { BINARY | EBCDIC | ASCII } \]

\[ [FCOMP](parameter_intro/fcomp)
= { <span style="text-decoration: underline;">0</span>
| 15 } \]

\[ [FDATE](parameter_intro/fdate)
= { <span style="text-decoration: underline;">0</span>
| date } \]

\[ FDB
= filename \]

\[ [FDISP](parameter_intro/fdisp)
= { <span style="text-decoration: underline;">BOTH</span>
| NEW | OLD }  \]

\[ [FILE](parameter_intro/file)
= { <span style="text-decoration: underline;">FIRST</span>
| ALL }  \]

\[ [FKEYLEN](parameter_intro/fkeylen)
= { <span style="text-decoration: underline;">0</span>
| n }  \]

\[ [FKEYPOS](parameter_intro/fkeypos)
= { <span style="text-decoration: underline;">0</span>
| n }   \]

\[ [FLRECL](parameter_intro/flrec)
= n \]

\[ [FNAME](parameter_intro/fname)
= filename \]

\[ [FORG](parameter_intro/forg)
= { <span style="text-decoration: underline;">SEQ</span>
| DIRECT | INDEXED | PART } \]

\[ [FPAD](parameter_intro/fpad) = { <u>' '</u> | character } \]

\[ [FRECFM](parameter_intro/frecfm)
= { <span style="text-decoration: underline;">‘
‘</span> | F | V | U }  \]

\[ [FSPACE](parameter_intro/fspace)
= n \]

\[ [FTIME](parameter_intro/ftime)
= { 0 | time } \]

\[ [FTYPE](parameter_intro/ftype)
=  { <span style="text-decoration: underline;">‘
‘</span> | character } \]

\[ [IDA](parameter_intro/ida)
= identifier \]

\[ [MACTION](parameter_intro/maction)
= { <span style="text-decoration: underline;">'
'</span> | REPLACE }  \]

\[ [MAXDATE](parameter_intro/maxdate)
=  { <span style="text-decoration: underline;">99991231</span>
| date } \]

\[ MAXDURATION = ** **{<u>0</u>...32767} \]

\[ [MAXTIME](parameter_intro/maxtime)
= { <span style="text-decoration: underline;">23595999</span>
| time }  \]

\[ [MINDATE](parameter_intro/mindate)
= { current system date | date } \]

\[ [MINTIME](parameter_intro/mintime)
= { <span style="text-decoration: underline;">0</span>
| time } \]

\[ [MODE](parameter_intro/mode)
= { <span style="text-decoration: underline;">REPLACE</span>
| CREATE | DELETE }  \]

\[ [NCOMP](parameter_intro/ncomp)
= { <span style="text-decoration: underline;">0</span>
| 15 } \]

\[ [NETBAND](parameter_intro/netband) = { 1...16} \]

\[ [NFNAME](parameter_intro/nfname)
= filename \]

\[ [NFVER](parameter_intro/nfver)
=  { <span style="text-decoration: underline;">0</span>
| 255 } \]

\[ [NIDF](parameter_intro/nidf)
= string \]

\[ [NPAD](parameter_intro/npad) = { <u>' '</u> | character } \]

\[ [PARM](parameter_intro/parm)
= string \]

\[ [PRI](parameter_intro/pri)
= { <span style="text-decoration: underline;">128</span>
| n } \]

\[ [PROT](parameter_intro/prot) = identifier \]

\[ [RAPPL](parameter_intro/rappl)
= string \]

\[ [RUSER](parameter_intro/ruser)
= string \]

\[ [SAPPL](parameter_intro/sappl)
= string \]

\[ [SERIAL](parameter_intro/serial) = { <u>' '</u> | Y | Z | X } \]

\[ [STATE](parameter_intro/state)
= { <span style="text-decoration: underline;">DISP</span>
| HOLD | KEEP } \]

\[ [SUSER](parameter_intro/suser)
= string \]

\[ [TCYCLE](parameter_intro/tcycle)
= { <span style="text-decoration: underline;">DAY</span>
| MIN | MONTH }  \]

\[ [TRK](parameter_intro/trk)
= { <span style="text-decoration: underline;">UNDEFINED</span>
| ALL | SUMMARY | NO } \]

\[ [WFNAME](parameter_intro/wfname)
= filename \]

\[ [WORKINGDIR](parameter_intro/workingdir) = string \]

\[ WSTATES = { string } \]

\[ WTIMEOUT = { integer } \]

\[ [XLATE](parameter_intro/xlate)
= identifier \]

[Receiving files](../../concepts/c_recv)

<span id="RESUME"></span>

#### RESUME: Retrieves, in server mode, a blocked send request

Syntax

[PART](parameter_intro/part)
= string

\[ [DIRECT](parameter_intro/direct)
= { SEND |RECV | <span style="text-decoration: underline;">BOTH</span>
} \]

\[ [BLKNUM](parameter_intro/blknum)
= { <span style="text-decoration: underline;">0</span>
| n } \]

\[ [FORCE](parameter_intro/force)
= { <span style="text-decoration: underline;">NO</span>
| YES } \]

\[ [IDA](parameter_intro/ida)
= string \]

\[ [IDF](parameter_intro/idf)
= string \]

\[ [IDT](parameter_intro/idu)
= string \]

\[ [IDTU](parameter_intro/idtu)
= string \]

\[ [STATE](parameter_intro/state)  = string \]

\[ KDATE
= { <span style="text-decoration: underline;">0</span>
| n } \]

\[ KTIME
= { <span style="text-decoration: underline;">0</span>
| n } \]

\[ PHASE = string \]

\[ PHASESTEP = string \]

\[ [SCOPE](parameter_intro/scope) = string \]

[RESUME details](../about_cftutil/managing_transfer_states/resume_command)

<span style="font-weight: normal;"> </span>

<span id="SEND"></span>

#### SEND: Request to send transfer

<span class="MCDropDownHead dropDownHead"><img src="/Images/TransferCFT/transparent.gif" class="MCDropDown_Image_Icon" width="16" height="11" alt="Closed" />Syntax</span>

[TYPE](parameter_intro/type)
= FILE

[IDF](parameter_intro/idf)
= identifier  

[PART](parameter_intro/part)
= identifier

\[ [ACKEXEC](parameter_intro/ackexec) = filename\]

\[ ACKMINDATE = date \]

\[ ACKMINTIME = time \]

\[ ACKSTATE = { REQUIRE | IGNORE } \]

\[ ACKTIMEOUT = { 0 | n }
\]

\[ [APPCYCID](parameter_intro/appcycid)
= string \]

\[ [APPOBJID](parameter_intro/appobjid)
= string \]

\[ ARCHIVEFNAME = string \]

\[ [COMMENT](parameter_intro/comment)
= string \]

\[ [CYCDATE](parameter_intro/cycdate)
= date \]

\[ [CYCLE](parameter_intro/cycle)
= { <span style="text-decoration: underline;">0</span>
| n }  \]

\[ [CYCTIME](parameter_intro/cyctime)
= time \]

\[ [DACTION](parameter_intro/daction) = { <u>ERROR</u> | RESUME } \]

\[ [EXEC](parameter_intro/exec)
= filename \]

\[ [EXECSUB](parameter_intro/execsub)
= { <span style="text-decoration: underline;">LIST</span>
| FILE | SUBF } \]

\[ [EXECSUBA](parameter_intro/execsuba) = {LIST | FILE | <u>SUBF</u> }\]

\[ [EXIT](parameter_intro/exit)
= identifier  \]

\[ [FACC](parameter_intro/facc)
= { ‘ ‘ | character } \]

\[ [FACTION](parameter_intro/faction)
= { <span style="text-decoration: underline;">NONE</span>
| DELETE | ERASE |  ARCHIVE } \]

\[ [FBLKSIZE](parameter_intro/fblksize)
= n \]

\[ [FCODE](parameter_intro/fcode)
= { ASCII | BINARY | EBCDIC } \]

\[ [FDATE](parameter_intro/fdate)
= date \]

\[ FDB
= filename \]

\[ [FDISP](parameter_intro/fdisp)
= { <span style="text-decoration: underline;">SHR</span>
| OLD | CHECK } \]

\[ [FILTER](parameter_intro/filter) = string \]

\[ [FILTERTYPE](parameter_intro/filtertype) = string \]

\[ [FKEYLEN](parameter_intro/fkeylen)
= { <span style="text-decoration: underline;">0</span>
| n } \]

\[ [FKEYPOS](parameter_intro/fkeypos)
= { <span style="text-decoration: underline;">0</span>
| n } \]

\[ [FLRECL](parameter_intro/flrec)
= n \]

\[ [FNAME](parameter_intro/fname)
 = { filename
| mask | dirname | #filename | #mask | #dirname } \]

\[ FNAMEABS
= { YES | NO }  \]

\[ [FORG](parameter_intro/forg)
= { <span style="text-decoration: underline;">SEQ</span>
| DIRECT | INDEXED } \]

\[ [FPAD](parameter_intro/fpad) = { <u>' '</u> | character } \]

\[ [FRECFM](parameter_intro/frecfm)
= { ‘ ‘ | F | U | V }  \]

\[ [FSPACE](parameter_intro/fspace)
= n \]

\[ [FTIME](parameter_intro/ftime)
= time  \]

\[ [FTYPE](parameter_intro/ftype)
=  { ‘ ‘
| character } \]

\[ [IDA](parameter_intro/ida)
= identifier \]

\[ [IPART](parameter_intro/ipart)
= identifier \]

\[ [MAXDATE](parameter_intro/maxdate)
= { <span style="text-decoration: underline;">99991231</span>
| date } \]

\[ [MAXTIME](parameter_intro/maxtime)
= { <span style="text-decoration: underline;">23595999</span>
| time } \]

\[ [MINDATE](parameter_intro/mindate)
= { <span style="text-decoration: underline;">current
system date</span> | date } \]

\[ MAXDURATION = ** **<u>0</u>...32767} \]

\[ [MINTIME](parameter_intro/mintime)
= { <span style="text-decoration: underline;">0</span>
| time } \]

\[ [NBLKSIZE](parameter_intro/nblksize)
= n \]

\[ [NCODE](parameter_intro/ncode)
= { ASCII | BINARY | EBCDIC } \]

\[ [NCOMP](parameter_intro/ncomp)
= { 0 | 15 } \]

\[ [NETBAND](parameter_intro/netband)
= { 1...16} \]

\[ [NFNAME](parameter_intro/nfname)
= filename \]

\[ [NIDF](parameter_intro/nidf)
= string \]

\[ [NKEYLEN](parameter_intro/nkeylen)
= { <span style="text-decoration: underline;">0</span>
| n } \]

\[ [NKEYPOS](parameter_intro/nkeypos)
= { <span style="text-decoration: underline;">0</span>
| n }\]

\[ [NLRECL](parameter_intro/nlrecl)
= n  \]

\[ [NPAD](parameter_intro/npad) = { <u>' '</u> | character } \]

\[ [NRECFM](parameter_intro/nrecfm)
= { <span style="text-decoration: underline;">‘
‘</span> | F | U | V } \]

\[ [NSPACE](parameter_intro/nspace)
= { <span style="text-decoration: underline;">FSPACE
value</span> | n } \]

\[ [NTYPE](parameter_intro/ntype)
= { ' ' | character } \]

\[ [PARM](parameter_intro/parm)
= string \]

\[ [PRESTATE](parameter_intro/prestate) = { ' ' | character } \]

\[ [PREMINDATE](parameter_intro/premindate) = date \]

\[ [PREMINTIME](parameter_intro/premintime) = time \]

\[ [PRETIMEOUT](parameter_intro/pretimeout) = { 0 | n } \]

\[ [POSTMINDATE](parameter_intro/postmindate) = date \]

\[ [POSTMINTIME](parameter_intro/postmintime) = time \]

\[ [PRI](parameter_intro/pri)
= { <span style="text-decoration: underline;">128</span>
| n } \]

\[ [PROT](parameter_intro/prot) = identifier \]

\[ [RAPPL](parameter_intro/rappl)
= string \]

\[ [RUSER](parameter_intro/ruser)
= string \]

\[ [SAPPL](parameter_intro/sappl)
= string \]

\[ [SELFNAME](parameter_intro/selfname)
 = filename
\]

\[ [SERIAL](parameter_intro/serial) = { <u>' '</u> | Y | Z | X } \]

\[ [SPART](parameter_intro/spart)
= identifier \]

\[ [STATE](parameter_intro/state)
= { <span style="text-decoration: underline;">DISP</span>
| HOLD | KEEP } \]

\[ [SUSER](parameter_intro/suser)
= string \]

\[ [TCYCLE](parameter_intro/tcycle)
= { <span style="text-decoration: underline;">DAY</span>
| MIN | MONTH } \]

\[ [TRK](parameter_intro/trk)
= { <span style="text-decoration: underline;">UNDEFINED</span>
| ALL | SUMMARY | NO } \]

\[ [WORKINGDIR](parameter_intro/workingdir) = string \]

\[ WPHASES = { string } \]

\[ WPHASESTEPS = { string } \]

\[ WSTATES = { string } \]

\[ WTIMEOUT = { integer } \]

\[ [XLATE](parameter_intro/xlate)
= identifier \]

 

SEND TYPE = MESSAGE  

[IDM](parameter_intro/idm)
= identifier  

[MSG](parameter_intro/msg)
= string   

[PART](parameter_intro/part)
= identifier

\[ [APPCYCID](parameter_intro/appcycid)
= string \]

\[ [APPOBJID](parameter_intro/appobjid)
= string \]

\[ [CYCDATE](parameter_intro/cycdate)
= date \]

\[ [CYCLE](parameter_intro/cycle)
= { <span style="text-decoration: underline;">0</span>
| n } \]

\[ [CYCTIME](parameter_intro/cyctime)
= time \]

\[ [DACTION](parameter_intro/daction) = { ERROR | RESUME} \]

\[ [EXEC](parameter_intro/exec)
= filename \]

\[ [IDA](parameter_intro/ida)
= identifier \]

\[ [IPART](parameter_intro/ipart)
= identifier \]

\[ [MAXDATE](parameter_intro/maxdate)
= { <span style="text-decoration: underline;">99991231</span>
| date  }
\]

\[ [MAXTIME](parameter_intro/maxtime)
= { <span style="text-decoration: underline;">23595999</span>
| time }  \]

\[ [MINDATE](parameter_intro/mindate)
= { <span style="text-decoration: underline;">current
system date</span> | date } \]

\[ [MINTIME](parameter_intro/mintime)
= { <span style="text-decoration: underline;">0</span>
| time } \]

\[ [PRI](parameter_intro/pri)
= pri  \]

\[ [PROT](parameter_intro/prot) = identifier \]

\[ [RAPPL](parameter_intro/rappl)
= string \]

\[ [RUSER](parameter_intro/ruser)
= string \]

\[ [SAPPL](parameter_intro/sappl)
= string \]

\[ [SPART](parameter_intro/spart)
= identifier \]

\[ [STATE](parameter_intro/state)
= { <span style="text-decoration: underline;">DISP</span>
| HOLD | KEEP } \]

\[ [SUSER](parameter_intro/suser)
= string \]

\[ [TCYCLE](parameter_intro/tcycle)
= { <span style="text-decoration: underline;">DAY</span>
| MIN | MONTH } \]

\[ [TRK](parameter_intro/trk)
= { <span style="text-decoration: underline;">UNDEFINED</span>
| ALL | SUMMARY | NO } \]

 

SEND TYPE = REPLY

[IDM](parameter_intro/idm)
= identifier

[IDT](parameter_intro/idu)
= transid  

[MSG](parameter_intro/msg)
= string   

[PART](parameter_intro/part)
= identifier

\[ [APPCYCID](parameter_intro/appcycid)
= string \]

\[ [APPOBJID](parameter_intro/appobjid)
= string \]

\[ [CYCDATE](parameter_intro/cycdate)
= date \]

\[ [CYCTIME](parameter_intro/cyctime)
= time \]

\[ [EXEC](parameter_intro/exec) = filename \]

\[ [IDA](parameter_intro/ida) = identifier \]

\[ [IPART](parameter_intro/ipart)
= string \]

\[ [MAXDATE](parameter_intro/maxdate)
=  { <span style="text-decoration: underline;">99991231</span>
| date } \]

\[ [MAXTIME](parameter_intro/maxtime)
= { <span style="text-decoration: underline;">23595999</span>
| time } \]

\[ [MINDATE](parameter_intro/mindate)
= { <span style="text-decoration: underline;">current
system date</span> | date } \]

\[ [MINTIME](parameter_intro/mintime)
= { <span style="text-decoration: underline;">0</span>
| time } \]

\[ [PRI](parameter_intro/pri)
= pri \]

\[ [PROT](parameter_intro/prot) = identifier \]

\[ [RAPPL](parameter_intro/rappl)
= string \]

\[ [RUSER](parameter_intro/ruser)
= string \]

\[ [SAPPL](parameter_intro/sappl)
= string \]

\[ [SUSER](parameter_intro/suser)
= string \]

\[ [TCYCLE](parameter_intro/tcycle)
= { <span style="text-decoration: underline;">DAY</span>
| MIN | MONTH } \]

\[ [TRK](parameter_intro/trk)
= { <span style="text-decoration: underline;">UNDEFINED</span>
| ALL | SUMMARY | NO } \]

 

SEND TYPE = NACK

[IDM](parameter_intro/idm)
= identifier

[IDT](parameter_intro/idu)
= transid  

[MSG](parameter_intro/msg)
= string   

[PART](parameter_intro/part)
= identifier

\[ [APPCYCID](parameter_intro/appcycid)
= string \]

\[ [APPOBJID](parameter_intro/appobjid)
= string \]

\[ [CYCDATE](parameter_intro/cycdate)
= date \]

\[ [CYCTIME](parameter_intro/cyctime)
= time \]

\[ [EXEC](parameter_intro/exec) = filename \]

\[ [IDA](parameter_intro/ida) = identifier \]

\[ [IPART](parameter_intro/ipart)
= string \]

\[ [MAXDATE](parameter_intro/maxdate)
=  { <span style="text-decoration: underline;">99991231</span>
| date } \]

\[ [MAXTIME](parameter_intro/maxtime)
= { <span style="text-decoration: underline;">23595999</span>
| time } \]

\[ [MINDATE](parameter_intro/mindate)
= { <span style="text-decoration: underline;">current
system date</span> | date } \]

\[ [MINTIME](parameter_intro/mintime)
= { <span style="text-decoration: underline;">0</span>
| time } \]

\[ [PRI](parameter_intro/pri)
= pri \]

\[ [PROT](parameter_intro/prot) = identifier \]

\[ [RAPPL](parameter_intro/rappl)
= string \]

\[ [RUSER](parameter_intro/ruser)
= string \]

\[ [SAPPL](parameter_intro/sappl)
= string \]

\[ [SUSER](parameter_intro/suser)
= string \]

\[ [TCYCLE](parameter_intro/tcycle)
= { <span style="text-decoration: underline;">DAY</span>
| MIN | MONTH } \]

\[ [TRK](parameter_intro/trk)
= { <span style="text-decoration: underline;">UNDEFINED</span>
| ALL | SUMMARY | NO } \]

[Sending files](../../concepts/using_the_send_command/send_command_basics)

<span id="SHUT"></span>

#### SHUT: Shut down  <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> 

Syntax

\[ [FAST](parameter_intro/fast)
= { <span style="text-decoration: underline;">NO</span>
| YES | KILL } \]

\[ [RESTART](parameter_intro/restart) = { YES | NO } \]

[Manage the <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> server: stop the server](../../admin_intro/start_stop_cft#Stop__server)

<span id="START"></span>

#### START: Restart transfer

Syntax

[PART](parameter_intro/part)
= { identifier | mask }   

\[ [BLKNUM](parameter_intro/blknum)
= { <span style="text-decoration: underline;">0</span>
| n } \]

\[ [DIRECT](parameter_intro/direct)
= { <span style="text-decoration: underline;">BOTH</span>
| RECV | SEND } \]

\[ [FORCE](parameter_intro/force)
= YES | <span style="text-decoration: underline;">NO</span>
\]

\[ [IDA](parameter_intro/ida)
= identifier \]

\[ [IDF](parameter_intro/idf)
= identifier \]

\[ [IDT](parameter_intro/idu)
= { <span style="text-decoration: underline;">\*</span>
| transid } \]

\[ [IDTU](parameter_intro/idtu)
= string \]

\[ MAXDURATION = ** **{<u>0</u>...32767} \]

\[ [STATE](parameter_intro/state)  = string \]

\[ KDATE
= { <span style="text-decoration: underline;">0</span>
| n } \]

\[ KTIME
= { <span style="text-decoration: underline;">0</span>
| n } \]

\[ PHASE = string \]

\[ PHASESTEP = string \]

\[ [SCOPE](parameter_intro/scope) = string \]

[Restart transfers](../about_cftutil/managing_transfer_states/start_command)

<span id="SUBMIT"></span>

#### SUBMIT: Submit end-of-transfer procedure

Syntax

[PART](parameter_intro/part)
= { identifier | mask }  

\[ APPSTATE =
string \]

\[ [BLKNUM](parameter_intro/blknum)
= { <span style="text-decoration: underline;">0</span>
| n } \]

\[ [DIRECT](parameter_intro/direct)
= { <span style="text-decoration: underline;">BOTH</span>
| RECV | SEND } \]

\[ [EXEC](parameter_intro/exec)
= filename \]

\[ [IDA](parameter_intro/ida)
= identifier \]

\[ [IDF](parameter_intro/idf)
= identifier \]

\[ [IDT](parameter_intro/idu)
= { \* | transid } \]

\[ [IDTU](parameter_intro/idtu)
= string \]

\[ [STATE](parameter_intro/state)  = string \]

\[ KDATE
= { <span style="text-decoration: underline;">0</span>
| n } \]

\[ KTIME
= { <span style="text-decoration: underline;">0</span>
| n } \]

\[ PHASE = string \]

\[ PHASESTEP = string \]

[SUBMIT details](../about_cftutil/managing_transfer_states/submit_command)

<span id="SWAITCAT"></span>

#### SWAITCAT: Wait for a transfer state update

Syntax

[SELECT](parameter_intro/select)
= expression

\[ [PHASES](parameter_intro/phases)  = string \]

\[ [PHASESTEPS](parameter_intro/phasesteps) = string \]

\[ STATED = string \]

\[ [STATES](parameter_intro/states)
= string \]

\[ [TIMEOUT](parameter_intro/timeout)
= integer \]

[SWAITCAT concepts](../about_cftutil/managing_transfer_states/swaitcat_concepts) 

[SWAITCAT examples](../about_cftutil/managing_transfer_states/sync_transfer_request_tasks)

<span id="SWITCH"></span>

#### SWITCH: Manually switch LOG or ACCNT files 

Syntax

\[ [TYPE](parameter_intro/type)
= { LOG | ACCNT } \]

[SWITCH details](../../admin_intro/admin_commands_intro/switching_files_manually)

Toggle
log or accounting file

<span id="UCONFSET"></span>

#### UCONFSET: configuration utility

Syntax

[ID](parameter_intro/id)
= string  

\[ [VALUE](parameter_intro/value)
= {string} \]

[UCONF details](../../admin_intro/uconf/uconf_commands)

<span id="UCONFGET"></span>

#### UCONFGET

Syntax

[ID](parameter_intro/id)
= string

[UCONF details](../../admin_intro/uconf/uconf_commands)

<span id="LISTUCONF"></span>

#### LISTUCONF

Syntax

[ID](parameter_intro/id)
= string  

\[ [CONTENT](parameter_intro/content) = BRIEF | FULL \]

\[ [FOUT](parameter_intro/fout) = string \]

<span style="font-weight: normal;">\[ [SCOPE](parameter_intro/scope)
= { INSTANCE | SET | \* | ALL } \]</span>  

\[ [VALUE](parameter_intro/value) = string \]

[](../../admin_intro/uconf/uconf_commands)

UCONF details

<span id="WAIT"></span>

#### WAIT: Suspend CFTUTIL execution for the time indicated 

Syntax

\[ [DURING](parameter_intro/during)
= { <span style="text-decoration: underline;">0</span>
| n } \]    \*Time
in seconds

\[ [TIME](parameter_intro/time)
= { <span style="text-decoration: underline;">0</span>
| 23595999 } \]

[Suspending CFTUTIL execution](../about_cftutil/wait_command)

<span id="WLOG"></span>

#### WLOG: Request to write a message in the LOG file

Syntax

[MSG](parameter_intro/msg)
= string

SEVERITY =
string

[WLOG details](../../admin_intro/admin_commands_intro/wlog)

<span id="Syntax_conventions"></span>

### Syntax conventions

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

For more information, see  [TYPOGRAPHICAL CONVENTIONS.](../../gettingstarted_intro/my_first_transfer_flow_using_cg/typographical_conventions)

### Symbolic variables

The following symbolic variable syntaxes are valid in a  <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>
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
variables](symbolic_variables).

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
to [Filename conventions](filename_conventions).

<span id="About_UCONF"></span>

## Using UCONF

In order to merge functioning for all platforms,  <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> features a configuration interface that provides product uniformity
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

The [UCONF](../../admin_intro/uconf) table lists the new UCONF
identifiers, the default values, and the former file values.
