{
    "title": "Command guide and parameters",
    "linkTitle": "Command guide and parameters",
    "weight": "130"
}# <span id="Command_index"></span>Transfer CFT command guide and syntax <span id="MAPID_command_guide"></span>



This topic provides a useful list of Transfer CFT commands,

syntax, and parameters. For a more detailed description of the Transfer

CFT commands, refer to the link displayed below each command

syntax.



The Transfer CFT commands are presented in alphabetical order in this

summary. Each

command is presented with possible parameters and default values.



See also, [Syntax

conventions and symbolic variables.](#syntax_conventions)



#### <span id="ABOUT"></span>ABOUT: Displays product/host information



Syntax



\[ [COMMENT](parameter_intro/comment)

= string \]



\[ [TYPE](parameter_intro/type)

= { ALL

| HOST | CFT } \]



\[ [KEY](parameter_intro/key) = { <u>FIRST</u> | ALL } \]



[ABOUT details](../about_cftutil/about_command)



#### <span id="ACT"></span>ACT: Reactivates a partner



Syntax



ID = identifier



\[ [TYPE](parameter_intro/type)

= { PART

| TRK | CRON | FOLDER } \]



\[ [MODE](parameter_intro/mode)

= { BOTH

| REQUESTER|

SERVER } \]



[ACT details](../about_cftutil/reactivate_an_object_cl)



#### <span id="CFTACCNT"></span>CFTACCNT: Defines transfer accounting records



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

= { COBOL

| C } \]



\[ [MAXREC](parameter_intro/maxrec)

= { 0

| n } \]



\[ [MODE](parameter_intro/mode)

= { REPLACE

| CREATE | DELETE } \]



\[ [SWITCH](parameter_intro/switch)

= { 00000000

| time } \]



\[ [FORMAT](parameter_intro/format)

= { V23

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

= { V23

| 23 | V24 | 24} \]



\[ [LANGUAGE](parameter_intro/language)

= { COBOL

| C } \]



\[ [MODE](parameter_intro/mode)

= { REPLACE

| CREATE | DELETE } \]



[CFTACCNT details](../web_copilot_ui/conf_intro/cftaccnt)



[Transfer

accounting records](../../admin_intro/admin_config_commands/cftaccnt_concepts)



#### <span id="CFTAPPL"></span>CFTAPPL: Defines a transfer owner



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

= { REPLACE

| CREATE | DELETE } \]



CFTAPPL MODE = DELETE



[ID](parameter_intro/id)

= identifier



[USERID](parameter_intro/userid)

= string



[DIRECT](parameter_intro/direct)

= { BOTH

|  SEND

| RECV }



\[ [COMMENT](parameter_intro/comment)

= string \]



\[ [GROUPID](parameter_intro/groupid)

= string \]



\[ [MODE](parameter_intro/mode)

= { REPLACE

| CREATE | DELETE } \]



[CFTAPPL details](../web_copilot_ui/flow_def_intro/cftappl)



[Assign a transfer owner](transfer_owner_cftappl.htm)



#### CFTAUTH: Defines an Authorized Flow Definition list



Syntax



FNAME = filename



[ID](parameter_intro/id) = identifier



\[ [COMMENT](parameter_intro/comment)

= string \]



\[ [MODE](parameter_intro/mode)

= { REPLACE

| CREATE | DELETE } \]



 



Or



 



IDF = (identifier | mask, identifier | mask, …)



[ID](parameter_intro/id) = identifier



\[ [COMMENT](parameter_intro/comment)

= string \]



\[ [MODE](parameter_intro/mode)

= { REPLACE

| CREATE | DELETE } \]



 



#### <span id="CFTCAT"></span>CFTCAT: Defines Catalog attributes



Syntax



[FNAME](parameter_intro/fname)

= filename



[ID](parameter_intro/id)

= identifier  



\[ [COMMENT](parameter_intro/comment)

= string \]



\[ [MODE](parameter_intro/mode)

= { REPLACE

| CREATE | DELETE } \]



\[ [RH](parameter_intro/rh)

= { 10

| n }  \]



\[ [RKERROR](parameter_intro/rkerror)

= { KEEP

| DELETE } \]



\[ [RT](parameter_intro/rt)

= { 10

| n } \]



\[ [RX](parameter_intro/rx)

= { 10

| n } \]



\[ [SH](parameter_intro/sh)

= { 10

| n } \]



\[ [ST](parameter_intro/st)

= { 10

| n } \]



\[ [SX](parameter_intro/sx)

= { 10

| n } \]



\[ [TIMEP](parameter_intro/timep)

= { 23595999

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

= { 256

| n } \]



\[ [WSCAN](parameter_intro/wscan)

= { 5

| n } \]



[CFTCAT details](../web_copilot_ui/conf_intro/cftcat)



[Catalog attributes](../../admin_intro/admin_config_commands/catalog_parameter_concepts)



#### <span id="CFTCOM"></span>CFTCOM: Defines parameters related to the communication between applications and Transfer CFT



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

= { REPLACE

| CREATE | DELETE } \]



 [CFTCOM](../web_copilot_ui/conf_intro/cftcom)



[Communication

media](../../admin_intro/admin_config_commands/communication_media_concepts)



#### CFTCRON<span id="CFTCRON"></span>: Define Transfer CFT cron jobs



Syntax



ID = identifier



[CRONTAB](parameter_intro/crontab)

= string



[EXEC](parameter_intro/exec)

= filename



[EXECPOLICY](parameter_intro/execpolicy) = \[ <u>INSTANCE</u> |ALLNODES \]



[TIME](parameter_intro/time)

= { string | @shutdown | @startup } \[FOR

DETAILS: [CFTCRON

time syntax](../web_copilot_ui/flow_def_intro/cftcron)\]



\[ [PARM](parameter_intro/parm)

= string \]



\[ [COMMENT](parameter_intro/comment)

= string \]



\[ [STATE](parameter_intro/state) = { <u>ACTIVE</u> | NOACTIVE } \]



\[ [TYPE](parameter_intro/type)

= { EXEC

| CFTUTIL } \]



\[ [USERID](parameter_intro/userid)

= { CFT

server "userid"

| string } \]



[Define script execution](../web_copilot_ui/flow_def_intro/cftcron)



#### <span id="CFTDEST"></span>CFTDEST: Definition of a list of partners 



Syntax



CFTDEST FNAME



ID = identifier



[FNAME](parameter_intro/fname)

= filename



\[ [EXEC](parameter_intro/exec)

= { DEST

| PART | CHILDREN} \]



\[ EXECA = { DEST

| PART | CHILDREN} \]



\[ EXECPRE = { DEST

| PART | CHILDREN} \]



\[ [COMMENT](parameter_intro/comment)

= string \]



\[ [FOR](parameter_intro/for)

= { BOTH

| COMMUT |

LOCAL } \]



\[ [MODE](parameter_intro/mode)

= { REPLACE

| CREATE | DELETE } \]



\[ [NOPART](parameter_intro/nopart)

= { ABORT

| CONTINUE | IGNORE } \]



####  



CFTDEST PART



ID = identifier



[PART](parameter_intro/part)

= (identifier, identifier, ...)



\[ [EXEC](parameter_intro/exec)

= { DEST

| PART } \]



\[ [COMMENT](parameter_intro/comment)

= string \]



\[ [FOR](parameter_intro/for)

= { BOTH

| COMMUT |

LOCAL } \]



\[ [MODE](parameter_intro/mode)

= { REPLACE

| CREATE | DELETE } \]



\[ [NOPART](parameter_intro/nopart)

= { ABORT

| CONTINUE | IGNORE } \]



[CFTDEST details](../web_copilot_ui/flow_def_intro/cftdest)



[Broadcast

list](partner_diffusion_list_concepts.htm)



#### <span id="CFTEXIT"></span>CFTEXIT: Activate an exit task 



Syntax



#### CFTEXIT TYPE = FILE



[ID](parameter_intro/id)

= identifier



[TYPE](parameter_intro/type)

= FILE



\[ [COMMENT](parameter_intro/comment)

= string \]



\[ [FORMAT](parameter_intro/format)

= { V23

| 23 | V24 | 24 } \]



\[ [LANGUAGE](parameter_intro/language)

= { COBOL

| C } \]



\[ [MODE](parameter_intro/mode)

= { REPLACE

| CREATE | DELETE } \]



\[ [PARM](parameter_intro/parm)

= string \]



\[ [PROG](parameter_intro/prog)

= { CFTEXIT

| string } \]



\[ [RESERV](parameter_intro/reserv)

= { 16384

| n } \]



\[ [WAITTASK](parameter_intro/waittask)

= { 1441

| n } \]



 



#### CFTEXIT TYPE = { FILE | ACCESS | EXEC | BOT}



[ID](parameter_intro/id)

= identifier



[TYPE](parameter_intro/type)

= { FILE | ACCESS | EXEC | BOT }



\[ [COMMENT](parameter_intro/comment)

= string \]



\[ [FORMAT](parameter_intro/format)

= { V23

| 23 | V24 | 24 } \]



\[ [LANGUAGE](parameter_intro/language)

= { COBOL

| C } \]



\[ [MODE](parameter_intro/mode)

= { REPLACE

| CREATE | DELETE } \]



\[ [PARM](parameter_intro/parm)

= string \]



\[ [PROG](parameter_intro/prog)

= { CFTEXIT

| string } \]



\[ [RESERV](parameter_intro/reserv)

= { 1024

| n } \]



\[ [WAITTASK](parameter_intro/waittask)

= { 1441

| n } \]



 CFTEXIT details



[Exit

tasks](../../app_integration_intro/managing_exits)



#### <span id="CFTEXT"></span>CFTEXT: Extract data from the parameter and partner files 



Syntax



\[ [TYPE](parameter_intro/type)

= { ALL

| ACCNT | APPL | AUTH | CAT | COM | CRON | DEST | EXIT | IDF | LOG

| NET | PARM | PART | PROT | RECV | SEND | SSL | TCP | XLATE } \]



\[ [CONTENT](parameter_intro/content) = { <u>FULL</u> | BRIEF } \]



\[ [FOUT](parameter_intro/fout)

= filename \]



\[ [FPARM](parameter_intro/fparm)

= filename \]



\[ [FPART](parameter_intro/fpart)

= filename \]



\[ [ID](parameter_intro/id)

= { \*

| identifier | mask } \]



[Export

configuration](../about_cftutil/configuring_cft_start_here/cftext_command)



#### <span id="CFTFILE"></span>CFTFILE: Create or delete Transfer CFT files



Syntax



[TYPE](parameter_intro/type)

= { PARM | PART }



[FNAME](parameter_intro/fname)

= filename  



\[ [HABFNAME](parameter_intro/habfname)

= filename \]



\[ [FBLKSIZE](parameter_intro/fblksize)

= { 0

|n } \]



\[ [FSPACE](parameter_intro/fspace)

= n \]



\[ [FSPACEX](parameter_intro/fspacex)

= n \]



\[ [MODE](parameter_intro/mode)

= { CREATE

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

= { 0

|n } \]



\[ [FSPACE](parameter_intro/fspace)

= { 0

| n } \]



\[ [FSPACEX](parameter_intro/fspacex)

=  { 0

| n } \]



\[ [HABFNAME](parameter_intro/habfname)

= filename \]



\[ [MODE](parameter_intro/mode)

= { CREATE

| REPLACE | DELETE } \]



\[ [NODE](node.htm) = { 0

| n } \] available for TYPE=CAT



 



#### CFTFILE { ACCNT | LOG }



[TYPE](parameter_intro/type)

= { ACCNT | LOG }



[FNAME](parameter_intro/fname)

= filename



\[ [FBLKSIZE](parameter_intro/fblksize)

= 0

| n \]



\[ [FSPACE](parameter_intro/fspace)

= 0

|n \]



\[ [FSPACEX](parameter_intro/fspacex)

= 0

|n \]



\[ [MODE](parameter_intro/mode)

= { CREATE

| REPLACE | DELETE } \]



[Manually create internal datafile files](../../admin_intro/admin_commands_intro/cftfile)



#### CFTFOLDER



See [CFTFOLDER](../web_copilot_ui/flow_def_intro/cftfolder) for additional parameter details.



[IDF](parameter_intro/idf) = string



[PART](parameter_intro/part) = string



[SCANDIR](../web_copilot_ui/flow_def_intro/cftfolder)

= string



[WORKDIR](../web_copilot_ui/flow_def_intro/cftfolder) = string



\[ [ARCHIVEDIR](archivedir.htm) = string \]



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



[NIDF](parameter_intro/nidf)

= string



[PART](parameter_intro/part)

= identifier



[TYPE](parameter_intro/type)

= { RECV

| SEND }



\[ [COMMENT](parameter_intro/comment)

= string \]



\[ [MODE](parameter_intro/mode)

= { REPLACE

| CREATE | DELETE } \]



 [CFTIDF details](../web_copilot_ui/flow_def_intro/cftidf)



[File

template/virtual file association](../../concepts/cft_configuration_concepts_start_here/network_file_identifier_concepts)



#### <span id="CFTLOG"></span>CFTLOG FNAME = filename: Log file management parameters 



Syntax



[ID](parameter_intro/id)

= identifier



\[ [AFNAME](parameter_intro/afname)

= filename \]



\[ [COMMENT](parameter_intro/comment)

= string \]



\[ [CONTENT](parameter_intro/content)

= { FULL

| BRIEF } \]



\[ [EXEC](parameter_intro/exec)

= filename \]



\[ [FORMAT](parameter_intro/format)

= { V23

| 23 | V24 | 24 } \]



\[ [LENGTH](parameter_intro/length)

= { 160

| n } \]



\[ [MAXREC](parameter_intro/maxrec)

= { 0

| n } \]



\[ [MODE](parameter_intro/mode)

= { REPLACE

| CREATE | DELETE } \]



\[ [NOTIFY](parameter_intro/notify)

= identifier \]



\[ [OPERMSG](parameter_intro/opermsg)

= n \]



\[ [SWITCH](parameter_intro/switch)

= { 00000000

| time } \]



[CFTLOG details](log_parameter_concepts.htm)



[Transfer

Log file](log_parameter_concepts.htm)



#### <span id="CFTNET"></span>CFTNET: Local network resources



Syntax



#### CFTNET TYPE = TCP



[HOST](parameter_intro/host)

= { string | INADDR\_ANY }



[ID](parameter_intro/id)

= { identifier | \*identifier }



\[ [CALL](parameter_intro/call)

= { INOUT

| IN | OUT } \]



\[ [CLASS](parameter_intro/class)

= { 1 | n } \]



\[ [MAXCNX](parameter_intro/maxcnx)

= { 384

| n } \]



\[ [MODE](parameter_intro/mode)

= { REPLACE

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



\[ [SRCHOST](parameter_intro/srchost) = { string } \]



\[ SSLTERM { YES | <u>NO</u> } \]



#### PROTOCOL = GENERIC



[HOST](parameter_intro/host)

= string



[ID](parameter_intro/id)

= identifier



[INET](inet.htm)

= identifier



[PORT](parameter_intro/port)

=  n



\[ [CALL](parameter_intro/call)

= { INOUT

| IN | OUT } \]



\[ [CLASS](parameter_intro/class)

= { 1 | n } \]



\[ [MAXCNX](parameter_intro/maxcnx)

= { 384

| n } \]



\[ [MODE](parameter_intro/mode)

= { REPLACE

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



[INET](inet.htm)

= identifier



[PORT](parameter_intro/port)

=  n



\[ [CALL](parameter_intro/call)

= { INOUT

| IN | OUT } \]



\[ [CLASS](parameter_intro/class)

= { 1 | n } \]



\[ [MAXCNX](parameter_intro/maxcnx)

= { 32

| n } \]



\[ [MODE](parameter_intro/mode)

= { REPLACE

| CREATE | DELETE } \]



\[ [SRCHOST](parameter_intro/srchost)=

{ hostname1 | n} \]



\[ [USER](parameter_intro/user)

= string \]



 [CFTNET details](../web_copilot_ui/conf_intro/cftnet)



[Network

resources](../../admin_intro/admin_config_commands/network_resource_concepts)



[About proxies and SOCKS](../../protocols_start_here/ipv6/use_proxy_and_socks_protocol)



#### <span id="CFTPARM"></span>CFTPARM: General Transfer CFT environment parameters



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

=  { 4096

| n } \]



\[ [COMMENT](parameter_intro/comment)

= string \]



\[ [CRONTABS](parameter_intro/crontab)

= (crontab, crontab, …) \]



\[ [DEFAULT](parameter_intro/default)

= { DEFAUT

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



\[ [EXITBOT](exitbot.htm)

= identifier  \]



\[ [EXITEOT](parameter_intro/exiteot)

= identifier  \]



\[ [FBUFSIZE](parameter_intro/fbufsize)

= { 0

|65535 } \]



\[ [LENAPPL](parameter_intro/lenappl)

= { 32

| 1 } \]



\[ [LOG](parameter_intro/log)

= identifier  \]



\[ [MAXTASK](parameter_intro/maxtask)

= { 8

| n }  \]



\[ [MAXTRANS](parameter_intro/maxtrans)

=  { 256

| 1 } \]



\[ [MODE](parameter_intro/mode)

= { REPLACE

| CREATE | DELETE }  \]



\[ [NPART](parameter_intro/npart)

= string \]



\[ [PKIPASSW](parameter_intro/pkipassw)

= { PKIPASSW | string } \]



\[ [RCVALLER](parameter_intro/rcvaller)

= { STOP

| CONTINUE } \]



\[ [SECFNAME](parameter_intro/secfname)

= filename \]



\[ [SSLMTASK](parameter_intro/sslmtask)

= { 8

| n } \]



\[ [SSLTTASK](parameter_intro/sslttask)

=  {3

| n } \]



\[ [SSLWTASK](parameter_intro/sslwtask)

= { 10

|n } \]



\[ [SSLWRESP](parameter_intro/sslwresp)

= { 60

| n } \]



\[ [TRACE](parameter_intro/trace)

= string \]



\[ [TRANTASK](parameter_intro/trantask)

= { 3

| n } \]



\[ [TRKPART](parameter_intro/trkpart)

=  { UNDEFINED

| ALL | SUMMARY | NO } \]



\[ [TRKRECV](parameter_intro/trkrecv)

=  { UNDEFINED

| ALL | SUMMARY | NO } \]



\[ [TRKSEND](parameter_intro/trksend)

= { UNDEFINED

| ALL | SUMMARY | NO } \]



\[ [USERCTRL](parameter_intro/userctrl)

= { NO

| YES } \]



\[ [WAITRESP](parameter_intro/waitresp)

= { 60

| n } \]



\[ [WAITTASK](parameter_intro/waittask)

= { 10

| n } \]



[CFTPARM details](../web_copilot_ui/conf_intro/cftparm)



[Transfer CFT general

parameters](../../admin_intro/admin_config_commands/cftparm_general_parameters)



#### <span id="CFTPART"></span>CFTPART ID = identifier: Partner definition parameters  



Syntax



[PROT](parameter_intro/prot)

= { (identifier | mask , identifier | mask , .... ) }



\[ [COMMENT](parameter_intro/comment)

= string  \]



\[ [COMMUT](parameter_intro/commut)

= { YES

| NO | SERVER }   \]



\[ [CTRLPART](parameter_intro/ctrlpart)

= { IGNORE

| ALL | RPART | SPART } \]



\[ [FPREFIX](parameter_intro/fprefix)

= string \]



\[ [GROUP](parameter_intro/group)

= identifier \]



\[ [IDF](parameter_intro/idf)

= identifier  \]



\[ [IMAXTIME](parameter_intro/imaxtime)

= { 23595999

| time } \]



\[ [IMINTIME](imintime.htm)

= { 0

| time } \]



\[ [IPART](parameter_intro/ipart)

= identifier \]



\[ [MODE](parameter_intro/mode)

= { REPLACE

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

= { 23595999

| time } \]



\[ [OMINTIME](parameter_intro/omintime)

= { 0

| time } \]



\[ [RAUTH](parameter_intro/rauth)

= { \*

| identifier } \]



\[ [SAP](parameter_intro/sap)

= (string, string, …) \]



\[ [SAUTH](parameter_intro/sauth)

= { \*

| identifier } \]



\[ [SSL](parameter_intro/ssl)

= identifier \]



\[ [STATE](parameter_intro/state)

= {ACTIVEBOTH

| ACTIVEREQ | ACTIVESERV | NOACTIVE } \]



\[ [SYST](parameter_intro/syst)

= { ‘

‘ | GCOS7 | GCOS8 | GUARD | MVS | OS400 |

UNIX | VM | VMS | VSE | WINNT | BS2000 } \]



\[ [TRK](parameter_intro/trk)

= { UNDEFINED

| ALL | SUMMARY | NO } \]



\[ [XLATE](parameter_intro/xlate)

= identifier \]



[CFTPART details](defining_partners_concepts.htm)



[Partner

attribute concepts](defining_partners_concepts.htm)



#### <span id="CFTPROT"></span>CFTPROT: Transfer protocol



Syntax



CFTPROT TYPE = ODETTE



[ID](parameter_intro/id)

= identifier



[NET](parameter_intro/net)

= identifier



\[ [DISCTD](parameter_intro/disctd)

= { 20

| n } \]



\[ [DISCTS](parameter_intro/discts)

= { 65

| n } \]



\[ [DYNAM](parameter_intro/dynam)

= identifier  \]



\[ [EERP](parameter_intro/eerp)

= { 91

| 86 } \]



\[ [EXITA](parameter_intro/exita)

= identifier \]



\[ [IDF](parameter_intro/ida)

= string  \]



\[ [MODE](parameter_intro/mode)

= { REPLACE

| CREATE | DELETE } \]



\[ [PAD](parameter_intro/pad)

= { NO

| YES } \] &lt;Deprecated in Transfer CFT 3.5>



\[ [RCOMP](parameter_intro/rcomp)

=  { 0

| 15 } \]



\[ [RCREDIT](parameter_intro/rcredit)

= { 4

| n } \]



\[ [RESTART](parameter_intro/restart)

= { 5

| n } \]



\[ [RESYNC](parameter_intro/resync)

= { NO

| YES } \]



\[ [REVERSE](parameter_intro/reverse)

= { YES

| NO } \]



\[ [RRUSIZE](parameter_intro/rrusize)

= { 2048

| n } \]



\[ [RTO](parameter_intro/rto)

= { 260

| n } \]



\[ [SAP](parameter_intro/sap)

= string \]



\[ [SCOMP](parameter_intro/scomp)

= { 0 | <u>1</u> |15 } \]



\[ [SCREDIT](parameter_intro/scredit)

= { 4

| n } \]



\[ [SRIN](parameter_intro/srin)

= { BOTH

| NONE | RECEIVER | SENDER } \]



\[ [SROUT](parameter_intro/srout)

= { BOTH

| NONE | RECEIVER | SENDER } \]



\[ [SRUSIZE](parameter_intro/srusize)

= { 2048 | n } \]



\[ [SSL](parameter_intro/ssl)

= identifier \]



\[ [TCP](parameter_intro/tcp)

= { CFT

| <u>OFTP</u>} \]



 



CFTPROT TYPE = PESIT



[PROF](parameter_intro/prof)

= ANY



[ID](parameter_intro/id)

= identifier  



[NET](parameter_intro/net)

= identifier



\[ [CONCAT](parameter_intro/concat)

= { NO

| <u>YES</u> } \]



\[ [DISCTC](parameter_intro/disctc)

= { 60

| n } \]



\[ [DISCTD](parameter_intro/disctd)

= { 10

| n } \]



\[ [DISCTR](parameter_intro/disctr)

= { 45

| n } \]



\[ [DISCTS](parameter_intro/discts)

= { 60

|n } \]



\[ [DYNAM](parameter_intro/dynam)

= identifier \]



\[ [EXITA](parameter_intro/exita)

= identifier \]



\[ [HIDE99](parameter_intro/hide99)

= { NO

| YES } \]



\[ [IDF](parameter_intro/idf)

= string \]



\[ [LOGON](parameter_intro/logon)

= { YES

| NO } \]



\[ [MODE](parameter_intro/mode)

= { REPLACE

| CREATE | DELETE } \]



\[ [MULTART](parameter_intro/multart)

= { NO

| <u>YES</u> } \]



\[ [NACK](parameter_intro/nack) = { YES | <u>NO</u> | ANY} \]



\[ [PAD](parameter_intro/pad)

= { NO

| YES } \] &lt;Deprecated in Transfer CFT 3.5>



\[ [RCHKW](parameter_intro/rchkw)

= { 3

| n } \]



\[ [RCOMP](parameter_intro/rcomp)

= { <u>0</u>

| 15 } \]



\[ [RESTART](parameter_intro/restart)

= { 5

| n } \]



\[ [RESYNC](parameter_intro/resync)

= { NO

| YES } \]



\[ [REVERSE](parameter_intro/reverse)

= { NO

| YES } \]



\[ [RPACING](parameter_intro/rpacing)

= { 32767

| n } \]



\[ [RRUSIZE](parameter_intro/rrusize)

= { 32750

|n } \]



\[ [RTO](parameter_intro/rto)

= { 260

| n } \]



\[ [SAP](parameter_intro/sap)

= string \]



\[ [SCHKW](parameter_intro/schkw)

= { 3

| n } \]



\[ [SCOMP](parameter_intro/scomp)

= { <u>0</u> | 15} \]



\[ [SEGMENT](parameter_intro/segment)

= { NO

| <u>YES</u> } \]



\[ [SPACING](parameter_intro/spacing)

= { 32767

| n } \]



\[ [SRIN](parameter_intro/srin)

= { BOTH

| NONE | RECEIVER | SENDER } \]



\[ [SROUT](parameter_intro/srout)

= { BOTH

| NONE | RECEIVER | SENDER } \]



\[ [SRUSIZE](parameter_intro/srusize)

= { 32750

| n } \]



\[ [SSERV](parameter_intro/sserv)

= { GSIT

| string } \]



\[ [SSL](parameter_intro/ssl)

= identifier \]



 



CFTPROT TYPE = PESIT  



[PROF](parameter_intro/prof)

= CFT



[ID](parameter_intro/id)

= identifier



[NET](parameter_intro/net)

= identifier



\[ [CONCAT](parameter_intro/concat)

= { NO

| YES } \]



\[ [DISCTC](parameter_intro/disctc)

= { 90

| n }  \]



\[ [DISCTD](parameter_intro/disctd)

=  { 20

| n } \]



\[ [DISCTR](parameter_intro/disctr)

= { 45

| n } \]



\[ [DISCTS](parameter_intro/discts)

= { 65

| n } \]



\[ [DYNAM](parameter_intro/dynam)

= identifier  \]



\[ [EXITA](parameter_intro/exita)

= identifier  \]



\[ [HIDE99](parameter_intro/hide99)

= { NO

|YES } \]



\[ [IDF](parameter_intro/idf)

= string \]



\[ [MODE](parameter_intro/mode)

= { REPLACE

| CREATE | DELETE } \]



\[ [MULTART](parameter_intro/multart)

= { NO

| YES } \]



\[ [PAD](parameter_intro/pad)

= { NO

| YES } \] &lt;Deprecated in Transfer CFT 3.5>



\[ [RCHKW](parameter_intro/rchkw)

= { 2

| n }  \]



\[ [RCOMP](parameter_intro/rcomp)

= { 0 |15} \]



\[ [RESTART](parameter_intro/restart)

= { 5

| n } \]



\[ [RESYNC](parameter_intro/resync)

= { NO

| YES } \]



\[ [REVERSE](parameter_intro/reverse)

= { NO

| YES } \]



\[ [RPACING](parameter_intro/rpacing)

= { 36

| n } \]



\[ [RRUSIZE](parameter_intro/rrusize)

= { 4056

| n } \]



\[ [RSERV](rserv.htm)

= string \]



\[ [RTO](parameter_intro/rto)

= { 260

| n }  \]



\[ [SAP](parameter_intro/sap)

= string \]



\[ [SCHKW](parameter_intro/schkw)

= { 2

| n } \]



\[ [SCOMP](parameter_intro/scomp)

= { 0| 15

} \]



\[ [SEGMENT](parameter_intro/segment)

= { NO

| YES } \]



\[ [SPACING](parameter_intro/spacing)

= { 36

| n } \]



\[ [SRIN](parameter_intro/srin)

= { BOTH

| NONE | RECEIVER | SENDER } \]



\[ [SROUT](parameter_intro/srout)

= { BOTH

| NONE | RECEIVER | SENDER } \]



\[ [SRUSIZE](parameter_intro/srusize)

= { 4056

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

= { NO

| YES } \]



\[ [DISCTC](parameter_intro/disctc)

= { 90

| n } \]



\[ [DISCTD](parameter_intro/disctd)

=  { 120

| n } \]



\[ [DISCTR](parameter_intro/disctr)

= { 45

| n } \]



\[ [DISCTS](parameter_intro/discts)

= { 165

| n } \]



\[ [DYNAM](parameter_intro/dynam)

= identifier  \]



\[ [EXITA](parameter_intro/exita)

= identifier   \]



\[ [HIDE99](parameter_intro/hide99)

= { NO

|YES } \]



\[ [IDF](parameter_intro/idf)

= string  \]



\[ [MODE](parameter_intro/mode)

= { REPLACE

| CREATE | DELETE } \]



\[ [LOGON](parameter_intro/logon)

= { YES

| NO } \]



\[ [MULTART](parameter_intro/multart)

= { NO

| YES } \]



\[ [NACK](parameter_intro/nack) = { YES | <u>NO</u> | ANY } \]



\[ [RCHKW](parameter_intro/rchkw)

= { 2

| n } \]



\[ [RCOMP](parameter_intro/rcomp)

=  { 0 | 10

|15 } \]



\[ [RESTART](parameter_intro/restart)

= { 5

| n } \]



\[ [RESYNC](parameter_intro/resync)

= { NO

| YES } \]



\[ [REVERSE](parameter_intro/reverse)

= { YES | NO } \]



\[ [RPACING](parameter_intro/rpacing)

= { 36 | n } \]



\[ [RRUSIZE](parameter_intro/rrusize)

= { 4056 | n } \]



\[ [RTO](parameter_intro/rto)

= { 260

| n } \]



\[ [SAP](parameter_intro/sap)

= string \]



\[ [SCHKW](parameter_intro/schkw)

= { 2

| n } \]



\[ [SCOMP](parameter_intro/scomp)

=  { 0 | 10

| 15} \]



\[ [SEGMENT](parameter_intro/segment)

= { NO | YES } \]



\[ [SPACING](parameter_intro/spacing)

= { 36 | n } \]



\[ [SRIN](parameter_intro/srin)

= { BOTH

| NONE | RECEIVER | SENDER } \]



\[ [SROUT](parameter_intro/srout)

= { BOTH

| NONE | RECEIVER | SENDER } \]



\[ [SRUSIZE](parameter_intro/srusize)

= { 4056 | n } \]



\[ [SSERV](parameter_intro/sserv)

= { PESIT

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

= { NO

| YES } \]



\[ [DISCTC](parameter_intro/disctc)

= { 90

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

= { REPLACE

| CREATE | DELETE } \]



\[ [MULTART](parameter_intro/multart)

=  { NO

| YES } \]



\[ [RCHKW](parameter_intro/rchkw)

= { 2

| n } \]



\[ [RCOMP](parameter_intro/rcomp)

=  { 0 |

15 } \]



\[ [RESTART](parameter_intro/restart)

= { 5

| n } \]



\[ [RESYNC](parameter_intro/resync)

= { NO

| YES } \]



\[ [REVERSE](parameter_intro/reverse)

= { NO

| string } \]



\[ [RPACING](parameter_intro/rpacing)

= { 36

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

= { 36

| n } \]



\[ [SRIN](parameter_intro/srin)

= { BOTH

| NONE | RECEIVER | SENDER } \]



\[ [SROUT](parameter_intro/srout)

= { BOTH

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

= { NO

| YES } \]



\[ [CTO](parameter_intro/cto)

= { 1

| n } \]



\[ [CYCLE](parameter_intro/cycle)

= { 10

| n } \]



\[ [DISCTC](parameter_intro/disctc)

= { 90

| n } \]



\[ [DISCTD](parameter_intro/disctd)

= { 120

| n } \]



\[ [DISCTR](parameter_intro/disctr)

= { 45

| n } \]



\[ [DISCTS](parameter_intro/discts)

= { 65

| n  } \]



\[ [DYNAM](parameter_intro/dynam)

= identifier \]



\[ [EXITA](parameter_intro/exita)

= identifier \]



\[ [IDF](parameter_intro/idf)

= string \]



\[ [LOGON](parameter_intro/logon)

= { YES

| NO } \]



\[ [MODE](parameter_intro/mode)

= { REPLACE

| CREATE | DELETE } \]



\[ [MULTART](parameter_intro/multart)

= { NO

| YES } \]



\[ [PAD](parameter_intro/pad)

= { NO

| YES } \] &lt;Deprecated in Transfer CFT 3.5>



\[ [PART](parameter_intro/part)

= ( identifier, identifier, …) \]



\[ [RCHKW](parameter_intro/rchkw)

= { 2

| n } \]



\[ [RCOMP](parameter_intro/rcomp)

= { 0 | 10

| 15 } \]



\[ [RESTART](parameter_intro/restart)

= { 5

| n  } \]



\[ [RESYNC](parameter_intro/resync)

= { NO

| YES } \]



\[ [REVERSE](parameter_intro/reverse)

= { NO

| YES } \]



\[ [RPACING](parameter_intro/rpacing)

= { 36

| n } \]



\[ [RRUSIZE](parameter_intro/rrusize)

= n \]



\[ [RTO](parameter_intro/rto)

= { 260

| n } \]



\[ [SAP](parameter_intro/sap)

= string \]



\[ [SCHKW](parameter_intro/schkw)

= { 2

| n } \]



\[ [SCOMP](parameter_intro/scomp)

= { 0 | 10

| 15 } \]



\[ [SEGMENT](parameter_intro/segment)

= { NO

| YES } \]



\[ [SPACING](parameter_intro/spacing)

= { 36

| n }\]



\[ [SRIN](parameter_intro/srin)

= { BOTH

| NONE | RECEIVER | SENDER } \]



\[ [SROUT](parameter_intro/srout)

= { BOTH

| NONE | RECEIVER | SENDER } \]



\[ [SSERV](parameter_intro/sserv)

= { PESIT

| string } \]



\[ [SSL](parameter_intro/ssl)

= identifier \]



\[ [TURN](turn2.htm)

= { FILE

| MESSAGE } \]



 



[CFTPROT details](../../admin_intro/admin_config_commands/transfer_protocol_concepts)



[File

Transfer Protocol](../../admin_intro/admin_config_commands/transfer_protocol_concepts)



#### <span id="CFTRECV"></span>CFTRECV ID= identifier: Description of model file receiving parameters



Syntax



\[ [ACKEXEC](parameter_intro/ackexec) = filename\]



\[ [COMMENT](parameter_intro/comment)

= string \]



\[ [CYCDATE](parameter_intro/cycdate)

= { 0

| date } \]



\[ [CYCTIME](parameter_intro/cyctime)

= { 0

| time } \]



\[ [DELETE](parameter_intro/delete)

= { NO

| YES } \]



\[ [DIRNB](parameter_intro/dirnb)

= { 0

| n } \]



\[ [DUPLICATE](parameter_intro/duplicat) = { string 512 } \]



\[ [EXEC](parameter_intro/exec)

= filename \]



\[ [EXECRALL](execrall.htm) = { <u>all</u> | parent| children} \]



\[ [EXIT](parameter_intro/exit)

= identifier  \]



\[ [FACC](parameter_intro/facc)

= { ‘

‘ | character } \]



\[ [FACTION](parameter_intro/faction)

= { ‘

‘ | DELETE | ERASE | RENAME | VERIFY } \]



\[ [FBLKSIZE](parameter_intro/fblksize)

= { 0

| n } \]



\[ [FCHECK](parameter_intro/fcheck)

= { NO

| YES } \]



\[ [FCODE](parameter_intro/fcode)

= { ‘

‘ |BINARY | EBCDIC | ASCII } \]



\[ FDB

= filename \]



\[ [FDELETE](parameter_intro/fdelete) = <u>" "</u> |\* | C |D | K | H | T | X\]



\[ [FDISP](parameter_intro/fdisp)

= { BOTH

| NEW | OLD } \]



\[ [FILENOTFOUND](filenotfound.htm) = { <u>ABORT</u> | IGNORE } \]



\[ [FKEYLEN](parameter_intro/fkeylen)

= { 0

| n } \]



\[ [FKEYPOS](parameter_intro/fkeypos)

= { 0

| n } \]



\[ [FLOWNAME](parameter_intro/flowname) = string \]



\[ [FLRECL](parameter_intro/flrec)

=  { 0

| n  } \]



\[ [FNAME](parameter_intro/fname)

= filename \]



\[ [FORCE](parameter_intro/force)

= { NO

| YES }  \]



\[ [FORG](parameter_intro/forg)

= { SEQ

| DIRECT | INDEXED | PART } \]



\[ [FPAD](parameter_intro/fpad) = { <u>' '</u> | character } \]



\[ [FRECFM](parameter_intro/frecfm)

= { ‘

‘ |F | V | U } \]



\[ [FSPACE](parameter_intro/fspace)

=  { 0

| n } \]



\[ [FTYPE](parameter_intro/ftype)

=  { ‘

‘ | character } \]



\[ [GROUPID](parameter_intro/groupid)

= string \]



\[ [MACTION](parameter_intro/maction)

=  { '

' | REPLACE } \]



\[ [MAXDATE](parameter_intro/maxdate)

=  { 99991231

| date } \]



\[ [MAXDURATION](maxduration.htm) = ** **{<u>0</u>...32767} \]



\[ [MAXTIME](parameter_intro/maxtime)

= { 23595999

| time } \]



\[ [MINDATE](parameter_intro/mindate)

= { 10000101

| date } \]



\[ [MINTIME](parameter_intro/mintime)

= { 0

| time } \]



\[ [MODE](parameter_intro/mode)

= { REPLACE

| CREATE | DELETE } \]



\[ [NCOMP](parameter_intro/ncomp)

= { 0 | 15

} \]



\[ [NETBAND](parameter_intro/netband) = { 1...16} \]



\[ [NOTIFY](parameter_intro/notify)

= string \]



\[ [NPAD](parameter_intro/npad) = { <u>' '</u> | character } \]



\[ [NCODE](parameter_intro/ncode)

= { ‘

‘ |ASCII | BINARY | EBCDIC } \] \*available only when the protocol is SFTP



\[ [OPERMSG](parameter_intro/opermsg)

= { 0

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



\[ [SOURCEAPPL](parameter_intro/sourceappl) = string \]



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



 [CFTRECV details](../web_copilot_ui/flow_def_intro/cftrecv)



#### <span id="CFTSEND"></span>CFTSEND ID= identifier: Description of model file sending parameters



Syntax



\[ [ACKEXEC](parameter_intro/ackexec) = filename\]



\[ [ARCHIVEFNAME](archivefname.htm) = string \]



\[ [COMMENT](parameter_intro/comment)

= string \]



\[ [CYCDATE](parameter_intro/cycdate)

= { 0

| date } \]



\[ [CYCLE](parameter_intro/cycle)

= { 0

| n } \]



\[ [CYCTIME](parameter_intro/cyctime)

= { 0

| time } \]



\[ [DELETE](parameter_intro/delete)

= { NO

| YES } \]



\[ [DUPLICATE](parameter_intro/duplicat) = { string 512 } \]



\[ [EXEC](parameter_intro/exec)

= filename \]



\[ [EXECSUB](parameter_intro/execsub)

= { LIST

| FILE | SUBF } \]



\[ [EXECSUBA](parameter_intro/execsuba) = {LIST | FILE | <u>SUBF</u> } \]



\[ [EXECSUBPRE](parameter_intro/execsubpre) = { LIST

| FILE | SUBF } \]



\[ [EXIT](parameter_intro/exit)

=  identifier

\]



\[ [FACC](parameter_intro/facc)

= { ‘

‘ | character } \]



\[ [FACTION](parameter_intro/faction)

= { NONE

| DELETE | ERASE | ARCHIVE } \]



\[ [FBLKSIZE](parameter_intro/fblksize)

= { 0

| n } \]



\[ [FCODE](parameter_intro/fcode)

= { ‘

‘ |ASCII | BINARY | EBCDIC } \]



\[ FDB

= filename \]



\[ [FDELETE](parameter_intro/fdelete) = <u>" "</u> |\* | C |D | K | H | T | X\]



\[ [FDISP](parameter_intro/fdisp)

= { SHR

| OLD | CHECK } \]



\[ [FILENOTFOUND](filenotfound.htm) = { <u>ABORT</u> | IGNORE } \]



\[ [FILTER](parameter_intro/filter) = string \]



\[ [FILTERTYPE](parameter_intro/filtertype) = string \]



\[ [FKEYLEN](parameter_intro/fkeylen)

= { 0

| n } \]



\[ [FKEYPOS](parameter_intro/fkeypos)

= { 0

| n } \]



\[ [FLOWNAME](parameter_intro/flowname) = string \]



\[ [FLRECL](parameter_intro/flrec)

= { 0

| n } \]



\[ [FNAME](parameter_intro/fname)

 = { filename

| mask | dirname | #filename | #mask | #dirname } \]



\[ [FORCE](parameter_intro/force)

= { NO

| YES } \]



\[ [FORG](parameter_intro/forg)

= { SEQ

| DIRECT | INDEXED | PART } \]



\[ [FPAD](parameter_intro/fpad) = { <u>' '</u> | character } \]



\[ [FRECFM](parameter_intro/frecfm)

= { ‘

‘ | F | U | V } \]



\[ [FSPACE](parameter_intro/fspace)

= { 0

| n } \]



\[ [FTYPE](parameter_intro/ftype)

= { ‘

‘ | character } \]



\[ [GROUPID](parameter_intro/groupid)

= string \]



\[ [IDA](parameter_intro/ida) = string \]



\[ [IMPL](parameter_intro/impl)

= { NO

| YES } \]



\[ [MAXDATE](parameter_intro/maxdate)

=  { 99991231

| date } \]



\[ [MAXDURATION](maxduration.htm) = ** **{<u>0</u>...32767} \]



\[ [MAXTIME](parameter_intro/maxtime)

= { 23595999

| time } \]



\[ [MINDATE](parameter_intro/mindate)

= { 10000101|

date } \]



\[ [MINTIME](parameter_intro/mintime)

= { 0

| time } \]



\[ [MODE](parameter_intro/mode)

= { REPLACE

| CREATE | DELETE } \]



\[ [NBLKSIZE](parameter_intro/nblksize)

= { 0

| n } \]



\[ [NCODE](parameter_intro/ncode)

= { ‘

‘ |ASCII | BINARY | EBCDIC } \]



\[ [NCOMP](parameter_intro/ncomp)

=  { 0 |

15

} \]



\[ [NETBAND](parameter_intro/netband)

= { 1...16} \]



\[ [NFNAME](parameter_intro/nfname)

=  { filename

| \*filename } \]



\[ [NKEYLEN](parameter_intro/nkeylen)

= { 0

| n } \]



\[ [NKEYPOS](parameter_intro/nkeypos)

= { 0|

n } \]



\[ [NLRECL](parameter_intro/nlrecl)

=  { 0

| n } \]



\[ [NOTIFY](parameter_intro/notify)

= string  \]



\[ [NPAD](parameter_intro/npad) = { <u>' '</u> | character } \]



\[ [NRECFM](parameter_intro/nrecfm)

= { ‘

‘ | F | U | V } \]



\[ [NSPACE](parameter_intro/nspace)

=  { 0

| n } \]



\[ [NTYPE](parameter_intro/ntype)

= character \]



\[ [OPERMSG](parameter_intro/opermsg)

= { 0

| 255 } \]



\[ [PARM](parameter_intro/parm)

= string  \]



\[ [PREEXEC](parameter_intro/preexec) = filename \]



\[ [PRI](parameter_intro/pri)

= { 128

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



\[ [SOURCEAPPL](parameter_intro/sourceappl) = string \]



\[ [STATE](parameter_intro/state)

= { DISP

| HOLD | KEEP } \]



\[ [STORAGEACCOUNT](parameter_intro/storageaccount) = string \]



\[ [SUSER](parameter_intro/suser)

= string \]



\[ [](parameter_intro/targetappl)[TARGETAPPL](parameter_intro/targetappl) = string \]



\[ [TCYCLE](parameter_intro/tcycle)

= { DAY

| MIN | MONTH } \]



\[ [TRK](parameter_intro/trk)

=  { UNDEFINED

| ALL | SUMMARY | NO } \]



\[ [USERID](parameter_intro/userid)

= { CFT

server "userid" | string } \]



\[ [WFNAME](parameter_intro/wfname)

= filename \]



\[ [WORKINGDIR](parameter_intro/workingdir) = string \]



\[ [XLATE](parameter_intro/xlate)

= identifier \]



[CFTSEND details](../web_copilot_ui/flow_def_intro/cftsend)



[Send

file template](../../concepts/cft_configuration_concepts_start_here/default_send_template_concepts)



#### <span id="CFTSSL"></span>CFTSSL ID = identifier: Security files



Syntax



[CIPHLIST](parameter_intro/ciphlist)

= ( number, number, …)



[DIRECT](parameter_intro/direct)

= { CLIENT

| SERVER }



\[ [CACHE](parameter_intro/cache)

= { NO

| YES } \]



\[ [CERFNAME](cerfname.htm)

= string \]



\[ [COMMENT](parameter_intro/comment)

= string \]



\[ [DEPTH](depth.htm)

= { 10

| n } \]



\[ [DNISSUER](parameter_intro/dnissuer)

= ( string, string, …) \]



\[ [DNUSER](parameter_intro/dnuser)

= { ( string, string, …) | ( string, OP ([see Note](#op)), string ) } \]



\[ [INTERCID](parameter_intro/intercid)

= string \]



\[ [KEYEXT](parameter_intro/keyext) = { VERIFY | NONE } \]



\[ [MODE](parameter_intro/mode)

= { REPLACE

| CREATE | DELETE } \]



\[ [PARM](parameter_intro/parm)

= string \]



\[ [PASSW](parameter_intro/passw) = string \]



\[ [ROOTCID](parameter_intro/rootcid)

= ( string, string, …) \]



\[ [TRACE](parameter_intro/trace)

= { 0

| n } \]



\[ [USERCID](parameter_intro/usercid)

= string \]



\[ [VERIFY](parameter_intro/verify)

= { NONE| REQUIRED

| OPTIONAL } \] *\*When DIRECT=SERVER*


\[ [VERIFY](parameter_intro/verify)

= { <u>NONE</u>| REQUIRED

| ENFORCED | OPTIONAL } \] *\*When DIRECT=CLIENT *



\[ [VERSION](parameter_intro/version)

= { <u>TLSV1</u>  | SSLV3 | TLSV1 | SSLV3COMP | TLSV1COMP} \]



Note: <span id="OP"></span>You can configure Transfer

CFT to accept or reject SSL connections based on logical operators used

within the DN of the certificate. For details refer to [dnuser](parameter_intro/dnuser)

parameter details.



[CFTSSL details](../../transport_security_start_here/configuring_transport_security_start_here/transport_security_cftssl)



[SSL/TLS security concepts](../../transport_security_start_here)



#### <span id="CFTTCP"></span>CFTTCP: Network parameters of a TCP/IP partner



Syntax



[HOST](parameter_intro/host)

= string



[ID](parameter_intro/id)

= identifier



\[ [CLASS](parameter_intro/class)

= { 1

| n } \]



\[ [CNXIN](parameter_intro/cnxin)

= { 2

| n } \]



\[ [CNXINOUT](parameter_intro/cnxinout)

= { 4

| n } \]



\[ [CNXOUT](parameter_intro/cnxout)

= { 2

| n } \]



\[ [IMAXTIME](parameter_intro/imaxtime)

= { 23595999

| time } \]



\[ [IMINTIME](imintime.htm)

= { 0

| time } \]



\[ [MODE](parameter_intro/mode)

= { REPLACE

| CREATE | DELETE } \]



\[ [OMAXTIME](parameter_intro/omaxtime)

= { 23595999

| time } \]



\[ [OMINTIME](parameter_intro/omintime)

= { 0

| time } \]



\[ [RETRYM](parameter_intro/retrym)

= { 12

| n } \]



\[ [RETRYN](parameter_intro/retryn)

= { 4

| n } \]



\[ [RETRYW](parameter_intro/retryw)

= { 1

| n } \]



\[ [VERIFY](parameter_intro/verify)

= { 0

| n } \]



[TCP

attributes for a partner](../../admin_intro/admin_config_commands/network_resource_concepts)



#### <span id="CFTUIPREF"></span>CFTUIPREF MODE=mode



MODE= { CREATE | <u>REPLACE</u> | DELETE }



[ID](parameter_intro/id)

= identifier  



[TYPE](parameter_intro/type) = string



\[ [COMMENT](parameter_intro/comment)

= string \]



\[ [CONTENT](parameter_intro/content)

= { ACTIVE

| FULL } \]



\[ [ORIGIN](parameter_intro/origin) \] = string \]



#### <span id="CFTXLATE"></span>CFTXLATE FNAME = filename: Define conversion tables



Syntax



[ID](parameter_intro/id)

= identifier  



\[ [COMMENT](parameter_intro/comment)

= string \]



\[ [DIRECT](parameter_intro/direct)

= { BOTH

| RECV | SEND } \]



\[ [FCODE](parameter_intro/fcode)

= { '

' | ASCII | EBCDIC } \]



\[ [MODE](parameter_intro/mode)

= { REPLACE

| CREATE | DELETE } \]



\[ [NCODE](parameter_intro/ncode)

= { '

' | ASCII | EBCDIC } \]



\[ [ORIGIN](parameter_intro/origin) \] = string \]



\[ [TABLE](table.htm) \] = string \]



[Conversion

tables](../../concepts/cft_configuration_concepts_start_here/translation_table_concepts)



#### <span id="CLEARCMD"></span>CLEARCMD COMMAND = string: Delete a transfer request



Syntax



[USERID](parameter_intro/userid)

= string



[INDEX](parameter_intro/index_parameter)

= number



[CLEARCMD details](../about_cftutil/managing_transfer_states/clearcmd_command)



#### <span id="CONFIG"></span>CONFIG: Designate the communication medium and the files accessed by CFTUTIL



Syntax



CONFIG TYPE = { CAT | INPUT | OUTPUT | PARM | PART }



[FNAME](parameter_intro/fname) = filename



 



CONFIG TYPE = COM



MEDIACOM = FILE



[FNAME](parameter_intro/fname) = filename



 



CONFIG

TYPE = COM



MEDIACOM

= TCPIP



[FNAME](parameter_intro/fname)= string



\[ [HIGHPORT](parameter_intro/highport)

=  { 65535

| n } \]



\[ [LOWPORT](parameter_intro/lowport)

= { 5000

| n } \]



\[ [PASSWORD](password.htm) = string } \]



\[ PROXY

= string \]



\[ [ROOTCERT](parameter_intro/rootcert)

= string \]



\[ [TIMEOUT](parameter_intro/timeout)

= 60

| n \]



[Setting default CFTUTIL file names](../about_cftutil/redefining_cftutil_data_media)



#### <span id="COPYFILE"></span>COPYFILE IFNAME = filename: Copy files with an off-line compression or decompression option



Syntax



[OFNAME](parameter_intro/ofname)

= filename



\[ [CREATE](parameter_intro/create)

= { ‘

‘ | YES | NO } \]



\[ [IBLKSIZE](parameter_intro/iblksize)

= { 0

| n } \]



\[ [ICHARSET](icharset.htm) = string \]



\[ [ICODE](parameter_intro/icode)

= { ASCII | EBCDIC } \]



\[ [ICOMP](parameter_intro/icomp)

= { 0

| 15 } \]



\[ [ICT](parameter_intro/ict)

=  { H

| C } \]



\[ [ILRECL](parameter_intro/ilrecl)

= { 0

| n } \]



\[ [IRECFM](parameter_intro/irecfm)

= { F | V | U } \]



\[ [ITYPE](parameter_intro/itype)

= { ‘ ‘ | character } \]



\[ [OBLKSIZE](parameter_intro/oblksize)

= { 0 |n  }

\]



\[ [OCHARSET](ocharset.htm) = string \]



\[ [OCODE](parameter_intro/ocode)

= { ASCII | EBCDIC } \]



\[ [OCOMP](parameter_intro/ocomp)

= { 0

| 15 } \]



\[ [OCT](parameter_intro/oct)

= { H | C } \]



\[ [OLRECL](parameter_intro/olrecl)

= { 0

|n } \]



\[ [ORECFM](parameter_intro/orecfm)

= { IRECFM

value | F | V| U } \]



\[ [OSPACE](parameter_intro/ospace)

= { 0

| n } \]



\[ [OTYPE](parameter_intro/otype)

= { ‘

‘ | character } \]



\[ [XLATE](parameter_intro/xlate) = string \]



[Copying files off-line](../../admin_intro/admin_commands_intro/copyfile_command)



#### <span id="DELETE"></span>DELETE PART = { identifier | mask }: Delete a catalog entry



Syntax



\[ [BLKNUM](parameter_intro/blknum)

= { 0

| n } \]



\[ [DIRECT](parameter_intro/direct)

= { BOTH

| RECV | SEND } \]



\[ [FORCE](parameter_intro/force)

=  { YES

| NO

} \]



\[ [IDA](parameter_intro/ida)

= identifier  \]



\[ [IDF](parameter_intro/idf)

= identifier \]



\[ [IDT](parameter_intro/idu)

= { \*

| transid } \]



\[ [IDTU](parameter_intro/idtu)

= string \]



\[ [STATE](parameter_intro/state)

= { \*

| C | D | H | K | T | X } \]



\[ [KDATE](kdate.htm)

= { 0

| n } \]



\[ [KTIME](ktime.htm)

= { 0

| n } \]



\[ [PHASE](phase.htm) = string \]



\[ [PHASESTEP](phasestep.htm) = string \]



\[ [SCOPE](parameter_intro/scope) = string \]



[Deleting catalog entries](../../admin_intro/admin_commands_intro/delete_command)



#### <span id="DISPLAY"></span>DISPLAY \[ CONTENT = { listcat | identifier }\]: Display a model-formatted catalog



Syntax



\[ [DATETIMEMAX](parameter_intro/datetimemax) = { 0 | <u>991231235959</u> } \]



\[ [DATETIMEMIN](parameter_intro/datetimemin) = { <u>0</u> | 991231235959 } \]



\[ [DIAGI](parameter_intro/diagi) = { <u>\*</u> | 0 | ERROR } \]



\[ [DIRECT](parameter_intro/direct)

= { BOTH

| RECV | SEND } \]



\[ [EMPTY](parameter_intro/empty)

= { ANY

| string } \]



\[ [FILE](parameter_intro/file)

= filename \]



\[ [FMODEL](parameter_intro/fmodel)

=  string

\]



\[ [FOUT](parameter_intro/fout) = string \]



\[ [HELP](parameter_intro/help)

= { NONE

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

= { ANY

| COLUMN | LINE } \]



\[ [NA](parameter_intro/na)

= { ANY

| string } \]



\[ [NIDT](nidt.htm) 

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

= { \*

| character } \]



\[ [TYPE](parameter_intro/type)

= { \*

| FILE | MESSAGE | REPLY | ALL } \]



[Catalog output display model](../about_cftutil/monitoring_cftutil_intro/display_command)



#### <span id="END"></span>END PART = { identifier | mask }: Change transfer to X state



Syntax



\[ [APPCYCID](parameter_intro/appcycid)

= string \]



\[ [APPOBJID](parameter_intro/appobjid)

= string \]



\[ [APPSTATE](appstate.htm)

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

= { 0

| n } \]



\[ [DIAGC](diagc.htm) = string \]



\[ [DIRECT](parameter_intro/direct)

= { BOTH

| RECV | SEND } \]



\[ [FORCE](parameter_intro/force)

= { NO

| YES } \]



\[ [FNAME](parameter_intro/fname)

= string \]



\[ [IDA](parameter_intro/ida)

= identifier \]



\[ [IDF](parameter_intro/idf)

= identifier \]



\[ [IDT](parameter_intro/idu)

= { \*

| transid } \]



\[ [IDTU](parameter_intro/idtu)

= string \]



\[ [ISTATE](istate.htm) = { YES | <u>NO</u> } \]



\[ [ISTATE](istate.htm)

= string \]



\[ [KDATE](kdate.htm)

= { 0

| n } \]



\[ [KTIME](ktime.htm)

= { 0

| n } \]



\[ [NFNAME](parameter_intro/nfname)

= string \]



\[ [PARM](parameter_intro/parm)

= string \]



\[ [PHASE](phase.htm) = string \]



\[ [PHASESTEP](phasestep.htm) = string \]



\[ [PRI](parameter_intro/pri) Number { 0 - <u>256</u> } \]



\[ [RAPPL](parameter_intro/rappl)

= string \]



\[ [SCOPE](parameter_intro/scope) = string \]



\[ [SIGFNAME](parameter_intro/sigfname)

= string \]



\[ [STATE](parameter_intro/state) = string \]



[END details](../about_cftutil/managing_transfer_states/end_command)



#### <span id="HALT"></span>HALT PART = { identifier | mask }: Suspend a transfer



Syntax



\[ [BLKNUM](parameter_intro/blknum)

= { 0

| n } \]



\[ [DIAGC](diagc.htm) = string \]



\[ [DIAGP](parameter_intro/diagp) = string \]



\[ [DIRECT](parameter_intro/direct)

= { BOTH

| RECV | SEND } \]



\[ [FORCE](parameter_intro/force)

= { YES | NO

} \]



\[ [IDA](parameter_intro/ida)

= identifier  \]



\[ [IDF](parameter_intro/idf)

= identifier  \]



\[ [IDT](parameter_intro/idu)

= { \*

| transid } \]



\[ [IDTU](parameter_intro/idtu)

= string  \]



\[ [STATE](parameter_intro/state) = string \]



\[ [KDATE](kdate.htm)

= { 0

| n } \]



\[ [KTIME](ktime.htm)

= { 0

| n } \]



\[ [PHASE](phase.htm) = string \]



\[ [PHASESTEP](phasestep.htm) = string \]



\[ [SCOPE](parameter_intro/scope) = string \]



[Halting a transfer](../about_cftutil/managing_transfer_states/halt_command)



#### HELP



Syntax



\[ CMD = { string } \]



\[ CONTENT = { <u>BRIEF</u> | DETAIL} \]



\[ OFORMAT = { <u>txt</u> | xsd } \]



#### <span id="INACT"></span>INACT ID = identifier: Inactivate a partner



Syntax



\[ [MODE](parameter_intro/mode)

= { BOTH

| REQUESTER| SERVER } \]



\[ [FORCE](parameter_intro/force)

= { NO

| YES } \]



\[ [TYPE](parameter_intro/type)

= PART

| TRK | CRON | FOLDER \]



[INACT details](../about_cftutil/reactivate_an_object_cl/inact_command)



#### <span id="KEEP"></span>KEEP PART = { identifier | mask }: Abort a transfer



Syntax



\[ [BLKNUM](parameter_intro/blknum)

= 0

| n \]



\[ [DIAGC](diagc.htm) = string \]



\[ [DIAGP](parameter_intro/diagp) = string \]



\[ [DIRECT](parameter_intro/direct)

= { BOTH

| RECV | SEND } \]



\[ [FORCE](parameter_intro/force)

= { YES

| NO } \]



\[ [IDA](parameter_intro/ida)

= identifier  \]



\[ [IDF](parameter_intro/idf)

= identifier \]



\[ [IDT](parameter_intro/idu)

= { \*

| transid } \]



\[ [IDTU](parameter_intro/idtu)

= string  \]



\[ [STATE](parameter_intro/state)

= string \]



\[ [KDATE](kdate.htm)

= { 0

| n } \]



\[ [KTIME](ktime.htm)

= { 0

| n } \]



\[ [PHASE](phase.htm) = string \]



\[ [PHASESTEP](phasestep.htm) = string \]



\[ [SCOPE](parameter_intro/scope) = string \]



 [Suspend transfers](../about_cftutil/managing_transfer_states/keep_command)



#### <span id="KSTATE"></span>KSTATE IDF = identifier: Change a transfer state



Syntax



[IDTU](parameter_intro/idtu)

= local transfer counter identifier



[PART](parameter_intro/part)

= partner identifier



[KSTATE details](../about_cftutil/managing_transfer_states/kstate_command)



#### <span id="LISTCAT"></span>LISTCAT TYPE = { ALL | \* | FILE | MESSAGE | REPLY }: List catalog entries



Syntax



\[ [CONTENT](parameter_intro/content)

= { BRIEF

| FULL | DEBUG | EXTEND | COMMUT | STAT | BLKNUM } \]



\[ [DATETIMEMAX](parameter_intro/datetimemax) = { 0 | <u>991231235959</u> } \]



\[ [DATETIMEMIN](parameter_intro/datetimemin) = { <u>0</u> | 991231235959 } \]



\[ [DIAGI](parameter_intro/diagi) = { <u>\*</u> | 0 | ERROR } \]



\[ [DIRECT](parameter_intro/direct)

= { BOTH

| RECV | SEND } \]



\[ [FILE](parameter_intro/file)

= filename \]



\[ [IDA](parameter_intro/ida)

= { \*

| identifier } \]



\[ [IDF](parameter_intro/idf)

= { \*

| identifier } \]



\[ [IDT](parameter_intro/idu)

= { \*

| transid } \]



\[ [IDTU](parameter_intro/idtu)

= string  \]



\[ [NIDT](nidt.htm) 

= { string of 8 digits } \]



\[ [NPART](parameter_intro/npart)

= { identifier | mask } \]



\[ [PART](parameter_intro/part)

= { \*

| identifier | mask } \]



\[ [SORTBY](parameter_intro/sortby)

= string \]



\[ [STATE](parameter_intro/state)

= { \*

| string } \]



 [LISTCAT details](../about_cftutil/monitoring_cftutil_intro/listcat_command)



#### <span id="LISTCOM"></span>LISTCOM: Display contents of a communication media



Syntax



\[ [CONTENT](parameter_intro/content)

= { ACTIVE

| FULL } \]



\[ [FILE](parameter_intro/file)

= filename \]



\[ [FIRST](first.htm)

= { 0

| n } \]



\[ [LAST](last.htm)

= { 0

| max. number of records } \]



\[ [VERIFY](parameter_intro/verify)

= { NO

| YES } \]



 [LISTCOM details](../about_cftutil/monitoring_cftutil_intro/listcom_command) 



#### <span id="LISTLOG"></span>LISTLOG: Display and filter log content including merged nodes in cluster mode



Syntax



\[ [LOGLEVEL](loglevel.htm) = { F | E | W | <u>I</u> } \]



\[ [LINES](lines.htm) = { -10000 | <u>-20</u> | 10000 } \]



\[ [DATEMAX](parameter_intro/datemin_datemax) = { 0 | <u>991231</u> } \]



\[ [DATEMIN](parameter_intro/datemin_datemax) = { <u>0</u> | 991231 } \]



\[ [DATETIMEMAX](parameter_intro/datetimemax) = { 0 | <u>99123123595999</u> } \]



\[ [DATETIMEMIN](parameter_intro/datetimemin) { <u>0</u> | 99123123595999 } \]



\[ [TIMEMIN](timemin_timemax.htm) = { <u>0</u>| 23595999 } \]



\[ [TIMEMAX](timemin_timemax.htm) = { 0 | <u>23595999</u> } \]



\[ [PATTERN](pattern.htm) = string \]



\[ [DISPLAYNODEID](displaynodeid.htm) = { <u>YES</u> | NO } \]



\[ NODE = string \]



#### LISTNODE: Display all nodes



Syntax



No parameters



[Multi-node commands](../../about_multinode/multi_node_commands)



#### <span id="LISTPARM"></span>LISTPARM: Display Transfer CFT partner details



Syntax



\[ [ID](parameter_intro/id)

= { \*

| identifier } \]



\[ [CONTENT](parameter_intro/content)

= { FULL

| BRIEF } \]



\[ [PART](parameter_intro/part)

= identifier  \]



\[ [TYPE](parameter_intro/type)

= { ACCNT | ALL

| APPL | AUTH | CAT | COM | CRON | EXIT | IDF | LOG | NET | PARM | PROT

| RECV | SEND | SSL | XLATE } \]



[LISTPARM details](../about_cftutil/configuring_cft_start_here/listparm)



#### <span id="LISTPART"></span>LISTPART: Display partners



Syntax



\[ [ID](parameter_intro/id)

= { \*

|identifier } \]



\[ [CONTENT](parameter_intro/content)

= { FULL

| BRIEF } \]



\[ [TYPE](parameter_intro/type)

= { ALL

| DEST | PART | TCP | } \]



[LISTPART details](../about_cftutil/configuring_cft_start_here/listpart_command)



#### <span id="MQUERY"></span>MQUERY : Query one or more Transfer CFT components



Syntax



OBJECT = CACHE



\[ [OBJECT](parameter_intro/object)

= { CACHE

| SYSTEM | STATS | PROBE } \]



\[ [CONTENT](parameter_intro/content)

= { BRIEF

| FULL | STAT } \]



\[ [NAME](parameter_intro/name)

= { CAT

| COMMAND | CRON | DMZ | STAT } \]



 



OBJECT = SYSTEM



\[ [OBJECT](parameter_intro/object)

= { CACHE

| SYSTEM | STATS | PROBE } \]



\[ [CONTENT](parameter_intro/content)

= { BRIEF

| FULL | STAT } \]



\[ [NAME](parameter_intro/name)

= { CFTMAIN | CFTTRK | CFTTFIL | CFTCOM | CFTTPRO | CFTEXIT | CFTPRX | CFTDSCAN } \]



 



OBJECT = STATS or PROBE



\[ [OBJECT](parameter_intro/object)

= { CACHE

| SYSTEM | STATS | PROBE } \]



\[ [CONTENT](parameter_intro/content)

= { XMLBRIEF

| XMLFULL | RAW } \]



\[ [NAME](parameter_intro/name)

= { CAT

| COMMAND | CRON | DMZ | STAT } \]



 [MQUERY details](../../admin_intro/admin_commands_intro/querying_a_component_)



#### <span id="PURGE"></span>PURGE: Delete records from the catalog 



Syntax



\[ [TIMEP](parameter_intro/timep)

= { 23595999

| time } \]



[PURGE details](../../admin_intro/admin_commands_intro/purge_catalog)



#### <span id="RECONFIG"></span>RECONFIG: Reload



Syntax



\[ [TYPE](parameter_intro/type)

= { CRON | UCONF | CAT | FOLDER | PARMCACHE | AM

} \]



 [Manage configuration updates](../../admin_intro/admin_commands_intro/reconfig)



#### <span id="RECV"></span>RECV IDF = { identifier | mask }: Request to receive transfer



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

=  { 0

| n } \]



\[ [CYCTIME](parameter_intro/cyctime)

= time \]



\[ [DACTION](parameter_intro/daction) = { <u>ERROR</u> | RESUME } \]



\[ [DIRNB](parameter_intro/dirnb)

= n \]



\[ [EXEC](parameter_intro/exec)

= filename \]



\[ [EXECRALL](execrall.htm) = { <u>all</u> | parent| children} \]



\[ [EXIT](parameter_intro/exit)

= identifier  \]



\[ [FACC](parameter_intro/facc)

= { ‘

‘ | character }  \]



\[ [FACTION](parameter_intro/faction)

= { ‘

‘ | DELETE | ERASE | RENAME | VERIFY } \]



\[ [FBLKSIZE](parameter_intro/fblksize)

= n \]



\[ [FCODE](parameter_intro/fcode)

= { BINARY | EBCDIC | ASCII } \]



\[ [FCOMP](parameter_intro/fcomp)

= { 0

| 15 } \]



\[ [FDATE](parameter_intro/fdate)

= { 0

| date } \]



\[ FDB

= filename \]



\[ [FDISP](parameter_intro/fdisp)

= { BOTH

| NEW | OLD }  \]



\[ [FILE](parameter_intro/file)

= { FIRST

| ALL }  \]



\[ [FKEYLEN](parameter_intro/fkeylen)

= { 0

| n }  \]



\[ [FKEYPOS](parameter_intro/fkeypos)

= { 0

| n }   \]



\[ [FLRECL](parameter_intro/flrec)

= n \]



\[ [FNAME](parameter_intro/fname)

= filename \]



\[ [FORG](parameter_intro/forg)

= { SEQ

| DIRECT | INDEXED | PART } \]



\[ [FPAD](parameter_intro/fpad) = { <u>' '</u> | character } \]



\[ [FRECFM](parameter_intro/frecfm)

= { ‘

‘ | F | V | U }  \]



\[ [FSPACE](parameter_intro/fspace)

= n \]



\[ [FTIME](parameter_intro/ftime)

= { 0 | time } \]



\[ [FTYPE](parameter_intro/ftype)

=  { ‘

‘ | character } \]



\[ [IDA](parameter_intro/ida)

= identifier \]



\[ [MACTION](parameter_intro/maction)

= { '

' | REPLACE }  \]



\[ [MAXDATE](parameter_intro/maxdate)

=  { 99991231

| date } \]



\[ [MAXDURATION](maxduration.htm) = ** **{<u>0</u>...32767} \]



\[ [MAXTIME](parameter_intro/maxtime)

= { 23595999

| time }  \]



\[ [MINDATE](parameter_intro/mindate)

= { current system date | date } \]



\[ [MINTIME](parameter_intro/mintime)

= { 0

| time } \]



\[ [MODE](parameter_intro/mode)

= { REPLACE

| CREATE | DELETE }  \]



\[ [NCOMP](parameter_intro/ncomp)

= { 0

| 15 } \]



\[ [NETBAND](parameter_intro/netband) = { 1...16} \]



\[ [NFNAME](parameter_intro/nfname)

= filename \]



\[ [NFVER](parameter_intro/nfver)

=  { 0

| 255 } \]



\[ [NIDF](parameter_intro/nidf)

= string \]



\[ [NPAD](parameter_intro/npad) = { <u>' '</u> | character } \]



\[ [PARM](parameter_intro/parm)

= string \]



\[ [PRI](parameter_intro/pri)

= { 128

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

= { DISP

| HOLD | KEEP } \]



\[ [SUSER](parameter_intro/suser)

= string \]



\[ [TCYCLE](parameter_intro/tcycle)

= { DAY

| MIN | MONTH }  \]



\[ [TRK](parameter_intro/trk)

= { UNDEFINED

| ALL | SUMMARY | NO } \]



\[ [WFNAME](parameter_intro/wfname)

= filename \]



\[ [WORKINGDIR](parameter_intro/workingdir) = string \]



\[ [WSTATES](wstates.htm) = { string } \]



\[ [WTIMEOUT](wtimeout.htm) = { integer } \]



\[ [XLATE](parameter_intro/xlate)

= identifier \]



[Receiving files](../../concepts/c_recv)



#### <span id="RESUME"></span>RESUME: Retrieves, in server mode, a blocked send request



Syntax



[PART](parameter_intro/part)

= string



\[ [DIRECT](parameter_intro/direct)

= { SEND |RECV | BOTH

} \]



\[ [BLKNUM](parameter_intro/blknum)

= { 0

| n } \]



\[ [FORCE](parameter_intro/force)

= { NO

| YES } \]



\[ [IDA](parameter_intro/ida)

= string \]



\[ [IDF](parameter_intro/idf)

= string \]



\[ [IDT](parameter_intro/idu)

= string \]



\[ [IDTU](parameter_intro/idtu)

= string \]



\[ [STATE](parameter_intro/state) = string \]



\[ [KDATE](kdate.htm)

= { 0

| n } \]



\[ [KTIME](ktime.htm)

= { 0

| n } \]



\[ [PHASE](phase.htm) = string \]



\[ [PHASESTEP](phasestep.htm) = string \]



\[ [SCOPE](parameter_intro/scope) = string \]



[RESUME details](../about_cftutil/managing_transfer_states/resume_command)



 



#### <span id="SEND"></span>SEND: Request to send transfer



[<img src="transparent.gif" width="16" height="11" alt="Closed" />Syntax](javascript:void(0))



[TYPE](parameter_intro/type)

= FILE



[IDF](parameter_intro/idf)

= identifier  



[PART](parameter_intro/part)

= identifier



\[ [ACKEXEC](parameter_intro/ackexec) = filename\]



\[ [ACKMINDATE](ackmindate.htm) = date \]



\[ [ACKMINTIME](ackmintime.htm) = time \]



\[ [ACKSTATE](ackstate.htm) = { REQUIRE | IGNORE } \]



\[ [ACKTIMEOUT](acktimeout.htm) = { 0 | n }

\]



\[ [APPCYCID](parameter_intro/appcycid)

= string \]



\[ [APPOBJID](parameter_intro/appobjid)

= string \]



\[ [ARCHIVEFNAME](archivefname.htm) = string \]



\[ [COMMENT](parameter_intro/comment)

= string \]



\[ [CYCDATE](parameter_intro/cycdate)

= date \]



\[ [CYCLE](parameter_intro/cycle)

= { 0

| n }  \]



\[ [CYCTIME](parameter_intro/cyctime)

= time \]



\[ [DACTION](parameter_intro/daction) = { <u>ERROR</u> | RESUME } \]



\[ [EXEC](parameter_intro/exec)

= filename \]



\[ [EXECSUB](parameter_intro/execsub)

= { LIST

| FILE | SUBF } \]



\[ [EXECSUBA](parameter_intro/execsuba) = {LIST | FILE | <u>SUBF</u> }\]



\[ [EXIT](parameter_intro/exit)

= identifier  \]



\[ [FACC](parameter_intro/facc)

= { ‘ ‘ | character } \]



\[ [FACTION](parameter_intro/faction)

= { NONE

| DELETE | ERASE | ARCHIVE } \]



\[ [FBLKSIZE](parameter_intro/fblksize)

= n \]



\[ [FCODE](parameter_intro/fcode)

= { ASCII | BINARY | EBCDIC } \]



\[ [FDATE](parameter_intro/fdate)

= date \]



\[ FDB

= filename \]



\[ [FDISP](parameter_intro/fdisp)

= { SHR

| OLD | CHECK } \]



\[ [FILTER](parameter_intro/filter) = string \]



\[ [FILTERTYPE](parameter_intro/filtertype) = string \]



\[ [FKEYLEN](parameter_intro/fkeylen)

= { 0

| n } \]



\[ [FKEYPOS](parameter_intro/fkeypos)

= { 0

| n } \]



\[ [FLRECL](parameter_intro/flrec)

= n \]



\[ [FNAME](parameter_intro/fname)

 = { filename

| mask | dirname | #filename | #mask | #dirname } \]



\[ [FNAMEABS](fnameabs.htm)

= { YES | NO }  \]



\[ [FORG](parameter_intro/forg)

= { SEQ

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

= { 99991231

| date } \]



\[ [MAXTIME](parameter_intro/maxtime)

= { 23595999

| time } \]



\[ [MINDATE](parameter_intro/mindate)

= { current

system date | date } \]



\[ [MAXDURATION](maxduration.htm) = ** **<u>0</u>...32767} \]



\[ [MINTIME](parameter_intro/mintime)

= { 0

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

= { 0

| n } \]



\[ [NKEYPOS](parameter_intro/nkeypos)

= { 0

| n }\]



\[ [NLRECL](parameter_intro/nlrecl)

= n  \]



\[ [NPAD](parameter_intro/npad) = { <u>' '</u> | character } \]



\[ [NRECFM](parameter_intro/nrecfm)

= { ‘

‘ | F | U | V } \]



\[ [NSPACE](parameter_intro/nspace)

= { FSPACE

value | n } \]



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

= { 128

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

= { DISP

| HOLD | KEEP } \]



\[ [SUSER](parameter_intro/suser)

= string \]



\[ [TCYCLE](parameter_intro/tcycle)

= { DAY

| MIN | MONTH } \]



\[ [TRK](parameter_intro/trk)

= { UNDEFINED

| ALL | SUMMARY | NO } \]



\[ [WORKINGDIR](parameter_intro/workingdir) = string \]



\[ [WPHASES](wphases.htm) = { string } \]



\[ [WPHASESTEPS](wphasesteps.htm) = { string } \]



\[ [WSTATES](wstates.htm) = { string } \]



\[ [WTIMEOUT](wtimeout.htm) = { integer } \]



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

= { 0

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

= { 99991231

| date  }

\]



\[ [MAXTIME](parameter_intro/maxtime)

= { 23595999

| time }  \]



\[ [MINDATE](parameter_intro/mindate)

= { current

system date | date } \]



\[ [MINTIME](parameter_intro/mintime)

= { 0

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

= { DISP

| HOLD | KEEP } \]



\[ [SUSER](parameter_intro/suser)

= string \]



\[ [TCYCLE](parameter_intro/tcycle)

= { DAY

| MIN | MONTH } \]



\[ [TRK](parameter_intro/trk)

= { UNDEFINED

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

=  { 99991231

| date } \]



\[ [MAXTIME](parameter_intro/maxtime)

= { 23595999

| time } \]



\[ [MINDATE](parameter_intro/mindate)

= { current

system date | date } \]



\[ [MINTIME](parameter_intro/mintime)

= { 0

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

= { DAY

| MIN | MONTH } \]



\[ [TRK](parameter_intro/trk)

= { UNDEFINED

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

=  { 99991231

| date } \]



\[ [MAXTIME](parameter_intro/maxtime)

= { 23595999

| time } \]



\[ [MINDATE](parameter_intro/mindate)

= { current

system date | date } \]



\[ [MINTIME](parameter_intro/mintime)

= { 0

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

= { DAY

| MIN | MONTH } \]



\[ [TRK](parameter_intro/trk)

= { UNDEFINED

| ALL | SUMMARY | NO } \]



[Sending files](../../concepts/using_the_send_command/send_command_basics)



#### <span id="SHUT"></span>SHUT: Shut down Transfer CFT 



Syntax



\[ [FAST](parameter_intro/fast)

= { NO

| YES | KILL } \]



\[ [RESTART](parameter_intro/restart) = { YES | NO } \]



[Manage the Transfer CFT server: stop the server](../../admin_intro/start_stop_cft)



#### <span id="START"></span>START: Restart transfer



Syntax



[PART](parameter_intro/part)

= { identifier | mask }   



\[ [BLKNUM](parameter_intro/blknum)

= { 0

| n } \]



\[ [DIRECT](parameter_intro/direct)

= { BOTH

| RECV | SEND } \]



\[ [FORCE](parameter_intro/force)

= YES | NO

\]



\[ [IDA](parameter_intro/ida)

= identifier \]



\[ [IDF](parameter_intro/idf)

= identifier \]



\[ [IDT](parameter_intro/idu)

= { \*

| transid } \]



\[ [IDTU](parameter_intro/idtu)

= string \]



\[ [MAXDURATION](maxduration.htm) = ** **{<u>0</u>...32767} \]



\[ [STATE](parameter_intro/state) = string \]



\[ [KDATE](kdate.htm)

= { 0

| n } \]



\[ [KTIME](ktime.htm)

= { 0

| n } \]



\[ [PHASE](phase.htm) = string \]



\[ [PHASESTEP](phasestep.htm) = string \]



\[ [SCOPE](parameter_intro/scope) = string \]



[Restart transfers](../about_cftutil/managing_transfer_states/start_command)



#### <span id="SUBMIT"></span>SUBMIT: Submit end-of-transfer procedure



Syntax



[PART](parameter_intro/part)

= { identifier | mask }  



\[ [APPSTATE](appstate.htm) =

string \]



\[ [BLKNUM](parameter_intro/blknum)

= { 0

| n } \]



\[ [DIRECT](parameter_intro/direct)

= { BOTH

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



\[ [STATE](parameter_intro/state) = string \]



\[ [KDATE](kdate.htm)

= { 0

| n } \]



\[ [KTIME](ktime.htm)

= { 0

| n } \]



\[ [PHASE](phase.htm) = string \]



\[ [PHASESTEP](phasestep.htm) = string \]



[SUBMIT details](../about_cftutil/managing_transfer_states/submit_command)



#### <span id="SWAITCAT"></span>SWAITCAT: Wait for a transfer state update



Syntax



[SELECT](parameter_intro/select)

= expression



\[ [PHASES](parameter_intro/phases)  = string \]



\[ [PHASESTEPS](parameter_intro/phasesteps) = string \]



\[ [STATED](stated.htm) = string \]



\[ [STATES](parameter_intro/states)

= string \]



\[ [TIMEOUT](parameter_intro/timeout)

= integer \]



[SWAITCAT concepts](../about_cftutil/managing_transfer_states/swaitcat_concepts) 



[SWAITCAT examples](../about_cftutil/managing_transfer_states/sync_transfer_request_tasks)



#### <span id="SWITCH"></span>SWITCH: Manually switch LOG or ACCNT files 



Syntax



\[ [TYPE](parameter_intro/type)

= { LOG | ACCNT } \]



[SWITCH details](../../admin_intro/admin_commands_intro/switching_files_manually)



[Toggle

log or accounting file](switching_log_files.htm)



#### <span id="UCONFSET"></span>UCONFSET: configuration utility



Syntax



[ID](parameter_intro/id)

= string  



\[ [VALUE](parameter_intro/value)

= {string} \]



[UCONF details](../../admin_intro/uconf/uconf_commands)



#### <span id="UCONFGET"></span>UCONFGET



Syntax



[ID](parameter_intro/id)

= string



[UCONF details](../../admin_intro/uconf/uconf_commands)



#### <span id="LISTUCONF"></span>LISTUCONF



Syntax



[ID](parameter_intro/id)

= string  



\[ [CONTENT](parameter_intro/content) = BRIEF | FULL \]



\[ [FOUT](parameter_intro/fout) = string \]



\[ [SCOPE](parameter_intro/scope)

= { INSTANCE | SET | \* | ALL } \]  



\[ [VALUE](parameter_intro/value) = string \]



[](../../admin_intro/uconf/uconf_commands)



UCONF details



#### <span id="WAIT"></span>WAIT: Suspend CFTUTIL execution for the time indicated 



Syntax



\[ [DURING](parameter_intro/during)

= { 0

| n } \]    \*Time

in seconds



\[ [TIME](parameter_intro/time)

= { 0

| 23595999 } \]



[Suspending CFTUTIL execution](../about_cftutil/wait_command)



#### <span id="WLOG"></span>WLOG: Request to write a message in the LOG file



Syntax



[MSG](parameter_intro/msg)

= string



SEVERITY =

string



[WLOG details](../../admin_intro/admin_commands_intro/wlog)



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



For more information, see [TYPOGRAPHICAL CONVENTIONS.](../../gettingstarted_intro/my_first_transfer_flow_using_cg/typographical_conventions)



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



The [UCONF](../../admin_intro/uconf) table lists the new UCONF

identifiers, the default values, and the former file values.

