{
    "title": "Sending a NACK",
    "linkTitle": "Sending a NACK",
    "weight": "240"
}This topic describes the SEND NACK command, which sends a negative acknowledgement.

Via negative acknowledgments, the
final partner signals to the initial sender of the file that application
errors were detected.

If the initial sender does not support this function, as for example in earlier versions of Transfer CFT, the final partner does not transmit the
negative acknowledgement and the Transfer CFT log file displays:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>CFTT93W PART=XFB1 IDS=00008 Negative ack not supported by server</td>
</tr>
</tbody>
</table>

**Example**

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>cftutil send<br />
type=nack,<br />
part=&amp;part,<br />
idm=nack,<br />
msg=recu,<br />
idt=&amp;idt</p></td>
</tr>
</tbody>
</table>

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
