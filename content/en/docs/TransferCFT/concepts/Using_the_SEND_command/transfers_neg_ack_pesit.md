{
    "title": "Sending a negative acknowledgement ",
    "linkTitle": "Sending a NACK",
    "weight": "230"
}This topic describes the SEND NACK command, which sends a negative acknowledgement.

Via negative acknowledgments, the
final partner signals to the initial sender of the file that application
errors were detected.

If the initial sender does not support this function, as for example in earlier versions of Transfer CFT, the final partner does not transmit the
negative acknowledgement and the Transfer CFT log file displays:


    CFTT93W PART=XFB1 IDS=00008 Negative ack not supported by server

**Example**



    cftutil send 
    type=nack,
    part=&part,
    idm=nack,
    msg=recu,
    idt=&idt

**Syntax**

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
=  { <span style="text-decoration: underline;">99991231</span>
| date } \]

\[ [MAXTIME](../../../c_intro_userinterfaces/command_summary/parameter_intro/maxtime)
= { <span style="text-decoration: underline;">23595999</span>
| time } \]

\[ [MINDATE](../../../c_intro_userinterfaces/command_summary/parameter_intro/mindate)
= { <span style="text-decoration: underline;">current
system date</span> | date } \]

\[ [MINTIME](../../../c_intro_userinterfaces/command_summary/parameter_intro/mintime)
= { <span style="text-decoration: underline;">0</span>
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
= { <span style="text-decoration: underline;">DAY</span>
| MIN | MONTH } \]

\[ [TRK](../../../c_intro_userinterfaces/command_summary/parameter_intro/trk)
= { <span style="text-decoration: underline;">UNDEFINED</span>
| ALL | SUMMARY | NO } \]
