{
    "title": "Query internal Transfer CFT components",
    "linkTitle": "MQUERY - Querying a component ",
    "weight": "290"
}This page describes how to use the <span id="MQUERY_command"></span>MQUERY
command to query the various <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> components.

You can use this command to check transfers that should have started but are blocked, check a scheduled job that has not started, or to provide information when troubleshooting performance issues as shown in the examples below.

The MQUERY command sends the requested internal information to display in the log.

CFTUTIL command lets you list the allocation of <span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span> connections:

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

\[ CONTENT = { <span style="text-decoration: underline;">XMLBRIEF</span>
| XMLFULL | RAW } \]

\[ NAME = { <span style="text-decoration: underline;">CAT</span>
| COMMAND | CRON | DMZ| STAT } \]

<table>
   <th>
      <tr>
<th>Parameter         </th>
<th>  Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>OBJECT         </td>
         <td>Options: <u>CACHE</u> | SYSTEM | STATS | PROBE | TRACE (obsolete)         </td>
      </tr>
      <tr>
         <td>NAME         </td>
         <td><p>The options available for the NAME depend on the type of OBJECT to be queried.</p>
<p>If the object = cache (default) then the name can be set to:</p>
<ul>
<li>CAT: Query of the catalog cache</li>
<li>COMMAND: Query of the command cache</li>
<li>CRON: Query the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> CRON cache</li>
<li>DMZ: Query of the DMZ cache</li>
<li>STAT</li>
</ul>         </td>
      </tr>
      <tr>
         <td>CONTENT         </td>
         <td><p>If OBJECT=CACHE then you can select from the following values:</p>
<p>BRIEF| FULL | STAT
- or - XMLBRIEF| XMLFULL | RAW</p>         </td>
      </tr>
   </tbody>
</table>

### Examples

#### Querying the catalog cache

Use this command to check that transfers are not blocked by, for example, a time\_locked or partner\_locked issues.



    MQUERY NAME=CAT,CONTENT=FULL
    listlog
    =========================== TRANSFERS ======================================
    pri    minTime    minDate    reqTime    reqDate    cat_blk part
    ============================================================================
    Transfers_Non_Ready    : 0
    Transfers_Ready        : 0 ( 0 Partners )
    Transfers_Time__Locked : 2 ( 1 Partners )
    128   11:49:12      TODAY   11:49:12      TODAY 1780 PART1
    128   11:49:14      TODAY   11:49:31      TODAY 1781 PART1
    Transfers_State_Locked : 0 ( 0 Partners )
    ======================== PARTNERS =====================================
    name     count state locked diag    diagp    minTime    minDate
    =======================================================================
    Partners               : 1
    PART1      2  TLCK      2  302 L 02 045   11:55:38      TODAY
    Partners_Ready         : 0
    Partners_Time__Locked  : 1
    PART1     2  TLCK      2  302 L 02 045   11:55:38      TODAY
    Partners_State_Locked  : 0
    MQUERY Treated for USER AXWAY\ls

### Querying the command cache

Check scheduled internal commands, more specifically the switch and purge commands such as checking the time that the activity occurs.



    MQUERY NAME=COMMAND,CONTENT=FULL
    listlog
    CFTI24I  *** 3 COMMAND(S) INTO CACHE
    CFTI24I  *** DATE=28/01/2018 TIME= 18:48:00.00 SWITCH LOG
    CFTI24I  *** DATE=29/01/2018 TIME= 00:05:00.00 PURGE
    CFTI24I  *** DATE=29/01/2018 TIME= 10:57:00.00 SWITCH ACCNT -
    CFTR12I MQUERY  Treated for USER userid

### Displaying internal technical statistics for advanced diagnostic purposes

You can use this command when troubleshooting issues, and provide this output when contacting Axway support. One example is if you encounter an issue with memory usage.



    MQUERY OBJECT=STATS
    CFTI24I CFTMAIN CFTMAIN_TRANSFER_SERVER_604800=0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0
     CFTI24I CFTMAIN probe.cftmain_transfers_activated=0
     CFTI24I CFTMAIN CFTMAIN_TRANSFERS_ACTIVATED_1=0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0
    CFTI24I CFTMAIN CFTMAIN_TRANSFERS_ACTIVATED_10=0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0

### Output raw data to troubleshoot performance

This command provides statistical information, for example to troubleshoot performance issues, when contacting Axway support.



    MQUERY OBJECT=PROBE, CONTENT=RAW
    CFTI24I CFTMAIN probe.cftmain_transfers_activated=50