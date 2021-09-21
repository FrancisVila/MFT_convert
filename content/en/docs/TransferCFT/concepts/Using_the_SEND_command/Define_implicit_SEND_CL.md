{
    "title": "Defining an implicit SEND",
    "linkTitle": "Defining an implicit SEND",
    "weight": "220"
}Files can be made available for a transfer request either implicitly
or explicitly. The explicit mode provides more security because the server
must have authorization to make a file available. In the implicit mode,
IMPL parameter is set to yes, which enables a file to be available for
transfer without a specific request for that file.

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.982%">
            <p>Description</p>
         </td>
         <td colspan="2" rowspan="1" width="80.018%">
            <p>Use this command to make a file available for transfer 
 without it being explicitly requested. </p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="2" width="19.982%">
            <p>Parameters</p>
         </td>
         <td width="20.241%">
            <p><a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/impl">IMPL</a> </p>
         </td>
         <td width="59.777%">
            <p>The implicit send makes a file available. Select from:</p>
            <ul>
               <li>YES               </li>
               <li>NO               </li>
            </ul>
            <p>This parameter 
 must 
 be set to NO for the default model 
 file description.</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="2" rowspan="1" width="20.241%">
            <p>For other SEND parameters refer to <a href="../send_command_basics">Sending 
 files</a>.</p>
         </td>
      </tr>
</table>

For SEND command details refer to the following syntax:

[<img src="transparent.gif" width="16" height="11" alt="Closed" />Syntax](javascript:void(0))

[TYPE](../../../c_intro_userinterfaces/command_summary/parameter_intro/type)
= FILE

[IDF](../../../c_intro_userinterfaces/command_summary/parameter_intro/idf)
= identifier  

[PART](../../../c_intro_userinterfaces/command_summary/parameter_intro/part)
= identifier

\[ [ACKEXEC](../../../c_intro_userinterfaces/command_summary/parameter_intro/ackexec) = filename\]

\[ [ACKMINDATE](ackmindate.htm) = date \]

\[ [ACKMINTIME](ackmintime.htm) = time \]

\[ [ACKSTATE](ackstate.htm) = { REQUIRE | IGNORE } \]

\[ [ACKTIMEOUT](acktimeout.htm) = { 0 | n }
\]

\[ [APPCYCID](../../../c_intro_userinterfaces/command_summary/parameter_intro/appcycid)
= string \]

\[ [APPOBJID](../../../c_intro_userinterfaces/command_summary/parameter_intro/appobjid)
= string \]

\[ [ARCHIVEFNAME](archivefname.htm) = string \]

\[ [COMMENT](../../../c_intro_userinterfaces/command_summary/parameter_intro/comment)
= string \]

\[ [CYCDATE](../../../c_intro_userinterfaces/command_summary/parameter_intro/cycdate)
= date \]

\[ [CYCLE](../../../c_intro_userinterfaces/command_summary/parameter_intro/cycle)
= { 0
| n }  \]

\[ [CYCTIME](../../../c_intro_userinterfaces/command_summary/parameter_intro/cyctime)
= time \]

\[ [DACTION](../../../c_intro_userinterfaces/command_summary/parameter_intro/daction) = { <u>ERROR</u> | RESUME } \]

\[ [EXEC](../../../c_intro_userinterfaces/command_summary/parameter_intro/exec)
= filename \]

\[ [EXECSUB](../../../c_intro_userinterfaces/command_summary/parameter_intro/execsub)
= { LIST
| FILE | SUBF } \]

\[ [EXECSUBA](../../../c_intro_userinterfaces/command_summary/parameter_intro/execsuba) = {LIST | FILE | <u>SUBF</u> }\]

\[ [EXIT](../../../c_intro_userinterfaces/command_summary/parameter_intro/exit)
= identifier  \]

\[ [FACC](../../../c_intro_userinterfaces/command_summary/parameter_intro/facc)
= { ‘ ‘ | character } \]

\[ [FACTION](../../../c_intro_userinterfaces/command_summary/parameter_intro/faction)
= { NONE
| DELETE | ERASE | ARCHIVE } \]

\[ [FBLKSIZE](../../../c_intro_userinterfaces/command_summary/parameter_intro/fblksize)
= n \]

\[ [FCODE](../../../c_intro_userinterfaces/command_summary/parameter_intro/fcode)
= { ASCII | BINARY | EBCDIC } \]

\[ [FDATE](../../../c_intro_userinterfaces/command_summary/parameter_intro/fdate)
= date \]

\[ FDB
= filename \]

\[ [FDISP](../../../c_intro_userinterfaces/command_summary/parameter_intro/fdisp)
= { SHR
| OLD | CHECK } \]

\[ [FILTER](../../../c_intro_userinterfaces/command_summary/parameter_intro/filter) = string \]

\[ [FILTERTYPE](../../../c_intro_userinterfaces/command_summary/parameter_intro/filtertype) = string \]

\[ [FKEYLEN](../../../c_intro_userinterfaces/command_summary/parameter_intro/fkeylen)
= { 0
| n } \]

\[ [FKEYPOS](../../../c_intro_userinterfaces/command_summary/parameter_intro/fkeypos)
= { 0
| n } \]

\[ [FLRECL](../../../c_intro_userinterfaces/command_summary/parameter_intro/flrec)
= n \]

\[ [FNAME](../../../c_intro_userinterfaces/command_summary/parameter_intro/fname)
 = { filename
| mask | dirname | #filename | #mask | #dirname } \]

\[ [FNAMEABS](fnameabs.htm)
= { YES | NO }  \]

\[ [FORG](../../../c_intro_userinterfaces/command_summary/parameter_intro/forg)
= { SEQ
| DIRECT | INDEXED } \]

\[ [FPAD](../../../c_intro_userinterfaces/command_summary/parameter_intro/fpad) = { <u>' '</u> | character } \]

\[ [FRECFM](../../../c_intro_userinterfaces/command_summary/parameter_intro/frecfm)
= { ‘ ‘ | F | U | V }  \]

\[ [FSPACE](../../../c_intro_userinterfaces/command_summary/parameter_intro/fspace)
= n \]

\[ [FTIME](../../../c_intro_userinterfaces/command_summary/parameter_intro/ftime)
= time  \]

\[ [FTYPE](../../../c_intro_userinterfaces/command_summary/parameter_intro/ftype)
=  { ‘ ‘
| character } \]

\[ [IDA](../../../c_intro_userinterfaces/command_summary/parameter_intro/ida)
= identifier \]

\[ [IPART](../../../c_intro_userinterfaces/command_summary/parameter_intro/ipart)
= identifier \]

\[ [MAXDATE](../../../c_intro_userinterfaces/command_summary/parameter_intro/maxdate)
= { 99991231
| date } \]

\[ [MAXTIME](../../../c_intro_userinterfaces/command_summary/parameter_intro/maxtime)
= { 23595999
| time } \]

\[ [MINDATE](../../../c_intro_userinterfaces/command_summary/parameter_intro/mindate)
= { current
system date | date } \]

\[ [MAXDURATION](maxduration.htm) = ** **<u>0</u>...32767} \]

\[ [MINTIME](../../../c_intro_userinterfaces/command_summary/parameter_intro/mintime)
= { 0
| time } \]

\[ [NBLKSIZE](../../../c_intro_userinterfaces/command_summary/parameter_intro/nblksize)
= n \]

\[ [NCODE](../../../c_intro_userinterfaces/command_summary/parameter_intro/ncode)
= { ASCII | BINARY | EBCDIC } \]

\[ [NCOMP](../../../c_intro_userinterfaces/command_summary/parameter_intro/ncomp)
= { 0 | 15 } \]

\[ [NETBAND](../../../c_intro_userinterfaces/command_summary/parameter_intro/netband)
= { 1...16} \]

\[ [NFNAME](../../../c_intro_userinterfaces/command_summary/parameter_intro/nfname)
= filename \]

\[ [NIDF](../../../c_intro_userinterfaces/command_summary/parameter_intro/nidf)
= string \]

\[ [NKEYLEN](../../../c_intro_userinterfaces/command_summary/parameter_intro/nkeylen)
= { 0
| n } \]

\[ [NKEYPOS](../../../c_intro_userinterfaces/command_summary/parameter_intro/nkeypos)
= { 0
| n }\]

\[ [NLRECL](../../../c_intro_userinterfaces/command_summary/parameter_intro/nlrecl)
= n  \]

\[ [NPAD](../../../c_intro_userinterfaces/command_summary/parameter_intro/npad) = { <u>' '</u> | character } \]

\[ [NRECFM](../../../c_intro_userinterfaces/command_summary/parameter_intro/nrecfm)
= { ‘
‘ | F | U | V } \]

\[ [NSPACE](../../../c_intro_userinterfaces/command_summary/parameter_intro/nspace)
= { FSPACE
value | n } \]

\[ [NTYPE](../../../c_intro_userinterfaces/command_summary/parameter_intro/ntype)
= { ' ' | character } \]

\[ [PARM](../../../c_intro_userinterfaces/command_summary/parameter_intro/parm)
= string \]

\[ [PRESTATE](../../../c_intro_userinterfaces/command_summary/parameter_intro/prestate) = { ' ' | character } \]

\[ [PREMINDATE](../../../c_intro_userinterfaces/command_summary/parameter_intro/premindate) = date \]

\[ [PREMINTIME](../../../c_intro_userinterfaces/command_summary/parameter_intro/premintime) = time \]

\[ [PRETIMEOUT](../../../c_intro_userinterfaces/command_summary/parameter_intro/pretimeout) = { 0 | n } \]

\[ [POSTMINDATE](../../../c_intro_userinterfaces/command_summary/parameter_intro/postmindate) = date \]

\[ [POSTMINTIME](../../../c_intro_userinterfaces/command_summary/parameter_intro/postmintime) = time \]

\[ [PRI](../../../c_intro_userinterfaces/command_summary/parameter_intro/pri)
= { 128
| n } \]

\[ [PROT](../../../c_intro_userinterfaces/command_summary/parameter_intro/prot) = identifier \]

\[ [RAPPL](../../../c_intro_userinterfaces/command_summary/parameter_intro/rappl)
= string \]

\[ [RUSER](../../../c_intro_userinterfaces/command_summary/parameter_intro/ruser)
= string \]

\[ [SAPPL](../../../c_intro_userinterfaces/command_summary/parameter_intro/sappl)
= string \]

\[ [SELFNAME](../../../c_intro_userinterfaces/command_summary/parameter_intro/selfname)
 = filename
\]

\[ [SERIAL](../../../c_intro_userinterfaces/command_summary/parameter_intro/serial) = { <u>' '</u> | Y | Z | X } \]

\[ [SPART](../../../c_intro_userinterfaces/command_summary/parameter_intro/spart)
= identifier \]

\[ [STATE](../../../c_intro_userinterfaces/command_summary/parameter_intro/state)
= { DISP
| HOLD | KEEP } \]

\[ [SUSER](../../../c_intro_userinterfaces/command_summary/parameter_intro/suser)
= string \]

\[ [TCYCLE](../../../c_intro_userinterfaces/command_summary/parameter_intro/tcycle)
= { DAY
| MIN | MONTH } \]

\[ [TRK](../../../c_intro_userinterfaces/command_summary/parameter_intro/trk)
= { UNDEFINED
| ALL | SUMMARY | NO } \]

\[ [WORKINGDIR](../../../c_intro_userinterfaces/command_summary/parameter_intro/workingdir) = string \]

\[ [WPHASES](wphases.htm) = { string } \]

\[ [WPHASESTEPS](wphasesteps.htm) = { string } \]

\[ [WSTATES](wstates.htm) = { string } \]

\[ [WTIMEOUT](wtimeout.htm) = { integer } \]

\[ [XLATE](../../../c_intro_userinterfaces/command_summary/parameter_intro/xlate)
= identifier \]

 

SEND TYPE = MESSAGE  

[IDM](../../../c_intro_userinterfaces/command_summary/parameter_intro/idm)
= identifier  

[MSG](../../../c_intro_userinterfaces/command_summary/parameter_intro/msg)
= string   

[PART](../../../c_intro_userinterfaces/command_summary/parameter_intro/part)
= identifier

\[ [APPCYCID](../../../c_intro_userinterfaces/command_summary/parameter_intro/appcycid)
= string \]

\[ [APPOBJID](../../../c_intro_userinterfaces/command_summary/parameter_intro/appobjid)
= string \]

\[ [CYCDATE](../../../c_intro_userinterfaces/command_summary/parameter_intro/cycdate)
= date \]

\[ [CYCLE](../../../c_intro_userinterfaces/command_summary/parameter_intro/cycle)
= { 0
| n } \]

\[ [CYCTIME](../../../c_intro_userinterfaces/command_summary/parameter_intro/cyctime)
= time \]

\[ [DACTION](../../../c_intro_userinterfaces/command_summary/parameter_intro/daction) = { ERROR | RESUME} \]

\[ [EXEC](../../../c_intro_userinterfaces/command_summary/parameter_intro/exec)
= filename \]

\[ [IDA](../../../c_intro_userinterfaces/command_summary/parameter_intro/ida)
= identifier \]

\[ [IPART](../../../c_intro_userinterfaces/command_summary/parameter_intro/ipart)
= identifier \]

\[ [MAXDATE](../../../c_intro_userinterfaces/command_summary/parameter_intro/maxdate)
= { 99991231
| date  }
\]

\[ [MAXTIME](../../../c_intro_userinterfaces/command_summary/parameter_intro/maxtime)
= { 23595999
| time }  \]

\[ [MINDATE](../../../c_intro_userinterfaces/command_summary/parameter_intro/mindate)
= { current
system date | date } \]

\[ [MINTIME](../../../c_intro_userinterfaces/command_summary/parameter_intro/mintime)
= { 0
| time } \]

\[ [PRI](../../../c_intro_userinterfaces/command_summary/parameter_intro/pri)
= pri  \]

\[ [PROT](../../../c_intro_userinterfaces/command_summary/parameter_intro/prot) = identifier \]

\[ [RAPPL](../../../c_intro_userinterfaces/command_summary/parameter_intro/rappl)
= string \]

\[ [RUSER](../../../c_intro_userinterfaces/command_summary/parameter_intro/ruser)
= string \]

\[ [SAPPL](../../../c_intro_userinterfaces/command_summary/parameter_intro/sappl)
= string \]

\[ [SPART](../../../c_intro_userinterfaces/command_summary/parameter_intro/spart)
= identifier \]

\[ [STATE](../../../c_intro_userinterfaces/command_summary/parameter_intro/state)
= { DISP
| HOLD | KEEP } \]

\[ [SUSER](../../../c_intro_userinterfaces/command_summary/parameter_intro/suser)
= string \]

\[ [TCYCLE](../../../c_intro_userinterfaces/command_summary/parameter_intro/tcycle)
= { DAY
| MIN | MONTH } \]

\[ [TRK](../../../c_intro_userinterfaces/command_summary/parameter_intro/trk)
= { UNDEFINED
| ALL | SUMMARY | NO } \]

 

SEND TYPE = REPLY

[IDM](../../../c_intro_userinterfaces/command_summary/parameter_intro/idm)
= identifier

[IDT](../../../c_intro_userinterfaces/command_summary/parameter_intro/idu)
= transid  

[MSG](../../../c_intro_userinterfaces/command_summary/parameter_intro/msg)
= string   

[PART](../../../c_intro_userinterfaces/command_summary/parameter_intro/part)
= identifier

\[ [APPCYCID](../../../c_intro_userinterfaces/command_summary/parameter_intro/appcycid)
= string \]

\[ [APPOBJID](../../../c_intro_userinterfaces/command_summary/parameter_intro/appobjid)
= string \]

\[ [CYCDATE](../../../c_intro_userinterfaces/command_summary/parameter_intro/cycdate)
= date \]

\[ [CYCTIME](../../../c_intro_userinterfaces/command_summary/parameter_intro/cyctime)
= time \]

\[ [EXEC](../../../c_intro_userinterfaces/command_summary/parameter_intro/exec) = filename \]

\[ [IDA](../../../c_intro_userinterfaces/command_summary/parameter_intro/ida) = identifier \]

\[ [IPART](../../../c_intro_userinterfaces/command_summary/parameter_intro/ipart)
= string \]

\[ [MAXDATE](../../../c_intro_userinterfaces/command_summary/parameter_intro/maxdate)
=  { 99991231
| date } \]

\[ [MAXTIME](../../../c_intro_userinterfaces/command_summary/parameter_intro/maxtime)
= { 23595999
| time } \]

\[ [MINDATE](../../../c_intro_userinterfaces/command_summary/parameter_intro/mindate)
= { current
system date | date } \]

\[ [MINTIME](../../../c_intro_userinterfaces/command_summary/parameter_intro/mintime)
= { 0
| time } \]

\[ [PRI](../../../c_intro_userinterfaces/command_summary/parameter_intro/pri)
= pri \]

\[ [PROT](../../../c_intro_userinterfaces/command_summary/parameter_intro/prot) = identifier \]

\[ [RAPPL](../../../c_intro_userinterfaces/command_summary/parameter_intro/rappl)
= string \]

\[ [RUSER](../../../c_intro_userinterfaces/command_summary/parameter_intro/ruser)
= string \]

\[ [SAPPL](../../../c_intro_userinterfaces/command_summary/parameter_intro/sappl)
= string \]

\[ [SUSER](../../../c_intro_userinterfaces/command_summary/parameter_intro/suser)
= string \]

\[ [TCYCLE](../../../c_intro_userinterfaces/command_summary/parameter_intro/tcycle)
= { DAY
| MIN | MONTH } \]

\[ [TRK](../../../c_intro_userinterfaces/command_summary/parameter_intro/trk)
= { UNDEFINED
| ALL | SUMMARY | NO } \]

 

SEND TYPE = NACK

[IDM](../../../c_intro_userinterfaces/command_summary/parameter_intro/idm)
= identifier

[IDT](../../../c_intro_userinterfaces/command_summary/parameter_intro/idu)
= transid  

[MSG](../../../c_intro_userinterfaces/command_summary/parameter_intro/msg)
= string   

[PART](../../../c_intro_userinterfaces/command_summary/parameter_intro/part)
= identifier

\[ [APPCYCID](../../../c_intro_userinterfaces/command_summary/parameter_intro/appcycid)
= string \]

\[ [APPOBJID](../../../c_intro_userinterfaces/command_summary/parameter_intro/appobjid)
= string \]

\[ [CYCDATE](../../../c_intro_userinterfaces/command_summary/parameter_intro/cycdate)
= date \]

\[ [CYCTIME](../../../c_intro_userinterfaces/command_summary/parameter_intro/cyctime)
= time \]

\[ [EXEC](../../../c_intro_userinterfaces/command_summary/parameter_intro/exec) = filename \]

\[ [IDA](../../../c_intro_userinterfaces/command_summary/parameter_intro/ida) = identifier \]

\[ [IPART](../../../c_intro_userinterfaces/command_summary/parameter_intro/ipart)
= string \]

\[ [MAXDATE](../../../c_intro_userinterfaces/command_summary/parameter_intro/maxdate)
=  { 99991231
| date } \]

\[ [MAXTIME](../../../c_intro_userinterfaces/command_summary/parameter_intro/maxtime)
= { 23595999
| time } \]

\[ [MINDATE](../../../c_intro_userinterfaces/command_summary/parameter_intro/mindate)
= { current
system date | date } \]

\[ [MINTIME](../../../c_intro_userinterfaces/command_summary/parameter_intro/mintime)
= { 0
| time } \]

\[ [PRI](../../../c_intro_userinterfaces/command_summary/parameter_intro/pri)
= pri \]

\[ [PROT](../../../c_intro_userinterfaces/command_summary/parameter_intro/prot) = identifier \]

\[ [RAPPL](../../../c_intro_userinterfaces/command_summary/parameter_intro/rappl)
= string \]

\[ [RUSER](../../../c_intro_userinterfaces/command_summary/parameter_intro/ruser)
= string \]

\[ [SAPPL](../../../c_intro_userinterfaces/command_summary/parameter_intro/sappl)
= string \]

\[ [SUSER](../../../c_intro_userinterfaces/command_summary/parameter_intro/suser)
= string \]

\[ [TCYCLE](../../../c_intro_userinterfaces/command_summary/parameter_intro/tcycle)
= { DAY
| MIN | MONTH } \]

\[ [TRK](../../../c_intro_userinterfaces/command_summary/parameter_intro/trk)
= { UNDEFINED
| ALL | SUMMARY | NO } \]