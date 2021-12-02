{
    "title": "Query internal Transfer CFT components",
    "linkTitle": "MQUERY - Querying a component ",
    "weight": "290"
}This page describes how to use the <span id="MQUERY_command"></span>MQUERY
command to query the various {{< TransferCFT/componentshortname  >}} components.

You can use this command to check transfers that should have started but are blocked, check a scheduled job that has not started, or to provide information when troubleshooting performance issues as shown in the examples below.

The MQUERY command sends the requested internal information to display in the log.

CFTUTIL command lets you list the allocation of {{< TransferCFT/transfercftname  >}} connections:

-   The connections by partners (IN,OUT and reserved in “retry”)
-   The connections which are taken by protocols awaiting of FPDU.CONNECT (unknown partner)
-   The available connections

Global information:

-   Number of sessions
-   Number of client sessions
-   Number of server sessions
-   Number of active sessions
-   Number of inactive sessions
-   Number of server sessions with unknown Partner

Partner information is the same as global information but detailed for each partner.

#### Syntax

OBJECT = <u>CACHE</u>

\[ CONTENT = { BRIEF | FULL | STAT } \]

\[ NAME = { CAT | COMMAND | CRON | DMZ | STAT } \]

 

OBJECT = SYSTEM

\[ CONTENT = { BRIEF | FULL | STAT } \]

\[ NAME = { CFTMAIN | CFTTRK | CFTTFIL | CFTCOM | CFTTPRO | CFTEXIT | CFTPRX | CFTDSCAN } \]

 

OBJECT = STATS or PROBE

\[ CONTENT = {
| XMLFULL | RAW } \]

\[ NAME = {
| COMMAND | CRON | DMZ| STAT } \]


| Parameter  |  Description  |
| --- | --- |
| OBJECT  | Options: <u>CACHE</u> | SYSTEM | STATS | PROBE | TRACE (obsolete)  |
| NAME  |  The options available for the NAME depend on the type of OBJECT to be queried.<br/>If the object = cache (default) then the name can be set to:<br/> • CAT: Query of the catalog cache<br/> • COMMAND: Query of the command cache<br/> • CRON: Query the {{< TransferCFT/componentshortname  >}} CRON cache<br/> • DMZ: Query of the DMZ cache<br/> • STAT</li>  |
| CONTENT  |  If OBJECT=CACHE then you can select from the following values:<br/>BRIEF| FULL | STAT - or - XMLBRIEF| XMLFULL | RAW  |


### Examples

#### Querying the catalog cache

Use this command to check that transfers are not blocked by, for example, a time\_locked or partner\_locked issues.

### Querying the command cache

Check scheduled internal commands, more specifically the switch and purge commands such as checking the time that the activity occurs.

### Displaying internal technical statistics for advanced diagnostic purposes

You can use this command when troubleshooting issues, and provide this output when contacting Axway support. One example is if you encounter an issue with memory usage.

### Output raw data to troubleshoot performance

This command provides statistical information, for example to troubleshoot performance issues, when contacting Axway support.
