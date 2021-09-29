{
    "title": "Query internal Transfer CFT components",
    "linkTitle": "Query internal Transfer CFT components",
    "weight": "340"
}This page describes how to use the <span id="MQUERY_command"></span>MQUERY
command to query the various Transfer CFT components.

You can use this command to check transfers that should have started but are blocked, check a scheduled job that has not started, or to provide information when troubleshooting performance issues as shown in the examples below.

The MQUERY command sends the requested internal information to display in the log.

CFTUTIL command lets you list the allocation of Transfer CFT connections:

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

\[ CONTENT = { XMLBRIEF
| XMLFULL | RAW } \]

\[ NAME = { CAT
| COMMAND | CRON | DMZ| STAT } \]

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>Parameter</th>
<th>  Description</th>
</tr>
</thead>
<tbody>
<tr class="odd" data-valign="top">
<td width="19.982%">OBJECT</td>
<td width="80.018%">Options: <u>CACHE</u> | SYSTEM | STATS | PROBE | TRACE (obsolete)</td>
</tr>
<tr class="even" data-valign="top">
<td width="19.982%">NAME</td>
<td width="23.009%"><p>The options available for the NAME depend on the type of OBJECT to be queried.</p>
<p>If the object = cache (default) then the name can be set to:</p>
<ul>
<li>CAT: Query of the catalog cache</li>
<li>COMMAND: Query of the command cache</li>
<li>CRON: Query the <span>Transfer CFT</span> CRON cache</li>
<li>DMZ: Query of the DMZ cache</li>
<li>STAT</li>
</ul></td>
</tr>
<tr class="odd" data-valign="top">
<td width="19.982%">CONTENT</td>
<td width="80.018%"><p>If OBJECT=CACHE then you can select from the following values:</p>
<p>BRIEF| FULL | STAT
- or - XMLBRIEF| XMLFULL | RAW</p></td>
</tr>
</tbody>
</table>

### Examples

#### Querying the catalog cache

Use this command to check that transfers are not blocked by, for example, a time\_locked or partner\_locked issues.

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>MQUERY NAME=CAT,CONTENT=FULL</p>
<p>listlog</p>
<p>=========================== TRANSFERS ======================================</p>
<p>pri minTime minDate reqTime reqDate cat_blk part</p>
<p>============================================================================</p>
<p>Transfers_Non_Ready : 0</p>
<p>Transfers_Ready : 0 ( 0 Partners )</p>
<p>Transfers_Time__Locked : 2 ( 1 Partners )</p>
<p>128 11:49:12 TODAY 11:49:12 TODAY 1780 PART1</p>
<p>128 11:49:14 TODAY 11:49:31 TODAY 1781 PART1</p>
<p>Transfers_State_Locked : 0 ( 0 Partners )</p>
<p>======================== PARTNERS =====================================</p>
<p>name count state locked diag diagp minTime minDate</p>
<p>=======================================================================</p>
<p>Partners : 1</p>
<p>PART1 2 TLCK 2 302 L 02 045 11:55:38 TODAY</p>
<p>Partners_Ready : 0</p>
<p>Partners_Time__Locked : 1</p>
<p>PART1 2 TLCK 2 302 L 02 045 11:55:38 TODAY</p>
<p>Partners_State_Locked : 0</p>
<p>MQUERY Treated for USER AXWAY\ls</p></td>
</tr>
</tbody>
</table>

### Querying the command cache

Check scheduled internal commands, more specifically the switch and purge commands such as checking the time that the activity occurs.

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>MQUERY NAME=COMMAND,CONTENT=FULL</p>
<p>listlog</p>
<p>CFTI24I *** 3 COMMAND(S) INTO CACHE</p>
<p>CFTI24I *** DATE=28/01/2018 TIME= 18:48:00.00 SWITCH LOG</p>
<p>CFTI24I *** DATE=29/01/2018 TIME= 00:05:00.00 PURGE</p>
<p>CFTI24I *** DATE=29/01/2018 TIME= 10:57:00.00 SWITCH ACCNT -</p>
<p>CFTR12I MQUERY Treated for USER userid</p></td>
</tr>
</tbody>
</table>

### Displaying internal technical statistics for advanced diagnostic purposes

You can use this command when troubleshooting issues, and provide this output when contacting Axway support. One example is if you encounter an issue with memory usage.

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>MQUERY OBJECT=STATS</p>
<p>CFTI24I CFTMAIN CFTMAIN_TRANSFER_SERVER_604800=0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0</p>
<p>CFTI24I CFTMAIN probe.cftmain_transfers_activated=0</p>
<p>CFTI24I CFTMAIN CFTMAIN_TRANSFERS_ACTIVATED_1=0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0</p>
<p>CFTI24I CFTMAIN CFTMAIN_TRANSFERS_ACTIVATED_10=0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0</p></td>
</tr>
</tbody>
</table>

### Output raw data to troubleshoot performance

This command provides statistical information, for example to troubleshoot performance issues, when contacting Axway support.

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>MQUERY OBJECT=PROBE, CONTENT=RAW</p>
<p>CFTI24I CFTMAIN probe.cftmain_transfers_activated=50</p></td>
</tr>
</tbody>
</table>
