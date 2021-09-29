{
    "title": "CFTCRON - Script execution scheduling",
    "linkTitle": "CFTCRON - Script execution scheduling",
    "weight": "340"
}The [CRONJOB<span aria-hidden="true"> Job Scheduler</span>](javascript:void(0)) feature enables Transfer CFT to execute scripts at predetermined
dates and times. An example script, `cron-wlog.cmd`, is delivered in the installed product
packaging ($CFTDIRRUNTIME/exec on Unix/Windows). You can adapt this example to suit your local requirements.

See [Use processing scripts](../../../../concepts/about_transfer_processing/proc_commands) for details on script processing execution methods.

## CRON commands and parameters

This section describes the CRON related commands and parameters.

-   CFTPARM: Each CRONJOB is associated with a CFTPARM via a CRONTABS parameter (environment definition):
    -   The CRONTABS parameter of the CFTPARM object refers to the CRONTAB parameter of the CFTCRON objects.
    -   You can have a CRONTAB with the same value for different CFTCRON objects (in the example below, note that CRON1 and CRON4 refer to the same CRONTAB).
    -   **Example**
-   RECONFIG TYPE=CRON
    -   This sends a notification to Transfer CFT
        to reload the enabled CRONJOBs. You use this command after modifying a CFTCRON (when either inserting or deleting).
    -   The RECONFIG command does not reload CFTPARM. If
        you modify the CFTPARM CRONTABS then you must restart Transfer CFT.
-   MQUERY name=CRON
    -   Displays the log, which gives the current status of
        the enabled cronjobs.
-   ACT/INACT type=CRON
    -   To activate CRON4 in the previous example:
    -   To inactivate CRON1, enter:

For CFTCRON command parameter details, see the [Command reference](../../../command_summary).

## <span id="CFTCRON_time_syntax"></span>CFTCRON time syntax

This section provides CFTCRON examples.

The following command inserts the cronjob CRON1 in the crontab CRONTAB1.
The job my\_exec is executed every 10 minutes once Transfer CFT is started.
This means that the job is submitted on the minute at 0, 10, 20,
30, 40, 50 minutes of every hour.

**Example using template processing**

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>CFTUTIL CFTCRON id=CRON1, crontab=CRONTAB1, EXEC=my_exec,
time='m=*/10'</p></td>
</tr>
</tbody>
</table>

**Example directly processing (UNIX and Windows)**

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>CFTUTIL CFTCRON id=CRON1, crontab=CRONTAB1, EXEC='cmd:my_exec &amp;ID',
time='m=*/10'</p></td>
</tr>
</tbody>
</table>

### Time syntax

The time syntax is case sensitive. For example, a lower case m defines
minutes, while an upper case M defines months.

-   Bold characters
    are terminators
-   Italic characters
    are grammar rule non-terminators
-   A, b, c are integers

<table data-cellspacing="0" width="90%">
<thead>
<tr class="header" data-mc-conditions="">
<th><p>Rule</p></th>
<th><p>Syntax</p></th>
<th><p>Alternate syntax</p></th>
</tr>
</thead>
<tbody>
<tr class="odd" data-mc-conditions="" data-valign="top">
<td width="23.077%"><p>time</p></td>
<td width="35.647%"><p>time_element; time</p>
<p>time_element</p></td>
<td width="38.274%"><p> </p></td>
</tr>
<tr class="even" data-mc-conditions="" data-valign="top">
<td width="23.077%"><p>time_element</p></td>
<td width="35.647%"><p>seconds= content</p>
<p>minutes= content</p>
<p>hours= content</p>
<p>monthdays= content</p>
<p>weekdays= content</p>
<p>months= content</p></td>
<td width="38.274%"><p>s= content</p>
<p>m= content</p>
<p>h= content</p>
<p>D= content</p>
<p>W= content</p>
<p>M= content</p></td>
</tr>
<tr class="odd" data-mc-conditions="" data-valign="top">
<td width="23.077%"><p>content</p></td>
<td width="35.647%"><p>content_elt, content</p>
<p>content_elt</p></td>
<td width="38.274%"><p> </p></td>
</tr>
<tr class="even" data-valign="top">
<td width="23.077%"><p>content_elt</p></td>
<td width="35.647%"><p>a</p>
<p>content_set / c</p></td>
<td width="38.274%"><p> </p></td>
</tr>
<tr class="odd" data-valign="top">
<td colspan="2" width="58.724%"><p> </p></td>
<td width="38.274%"><p>z/OS (MVS) specific syntax</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="23.077%"><p>content_set</p></td>
<td width="35.647%"><p>[a:b] [a:b]</p>
<p>[a:]</p>
<p>[:b]</p>
<p>*</p></td>
<td width="38.274%"><p>&lt;a:b&gt;</p>
<p>&lt;a:&gt;</p>
<p>&lt;:b&gt;</p></td>
</tr>
</tbody>
</table>

### Time parameter descriptions

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>Symbol</th>
<th>Description</th>
<th>Values</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>s</td>
<td>Second</td>
<td>0 to 59</td>
</tr>
<tr class="even">
<td>m</td>
<td>Minute</td>
<td>0 to 59</td>
</tr>
<tr class="odd">
<td>h</td>
<td>Hour</td>
<td>0 to 23</td>
</tr>
<tr class="even">
<td>D</td>
<td>Day of the month</td>
<td>1 to 31</td>
</tr>
<tr class="odd">
<td>M</td>
<td>Month</td>
<td>1 to 12</td>
</tr>
<tr class="even">
<td>W</td>
<td>Day of the week</td>
<td>0 to 7 (0 and 7 both represent Sunday)</td>
</tr>
</tbody>
</table>

### Time syntax examples

<table data-cellspacing="0" width="90%">
<thead>
<tr class="header">
<th><p>If you use this syntax…</p></th>
<th><p>The job is executed…</p></th>
</tr>
</thead>
<tbody>
<tr class="odd" data-valign="top">
<td width="32.182%"><p>m=30</p></td>
<td width="67.818%"><p>Once an hour at minute 30</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="32.182%"><p>m=1,5,40</p></td>
<td width="67.818%"><p>3 times an hour for minutes 1, 5, and 40</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="32.182%"><p>m=[30:40]/2</p></td>
<td width="67.818%"><p>Every 2 minutes, of every hour, between the minutes 30
and 40, this means on the minute for 30, 32, 34, 36, 38, 40</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="32.182%"><p>m=[:40]</p></td>
<td width="67.818%"><p>Every minute until, and including, the minute 40</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="32.182%"><p>m=[30:]</p></td>
<td width="67.818%"><p>Every minute starting at and including the minute 30</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="32.182%"><p>h=6;m=30</p></td>
<td width="67.818%"><p>Every day at 06:30:00</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="32.182%"><p>D=1;h=15;m=30</p></td>
<td width="67.818%"><p>Every first day of the month, at 15:30:00</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="32.182%"><p>D=*/2;h=6</p></td>
<td width="67.818%"><p>Every 2 days at 06:00:00, day 1, day 3, day 5...day 31.
Due to the fact that all months do not have 31 days, the following month
the job will be performed 2 days from the 31st, that means on day 2, then
day 4, day 6, and so on.</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="32.182%"><p>D=[1:7];W=0;h=4</p></td>
<td width="67.818%"><p>Every first Sunday of the month at 04:00:00</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="32.182%"><p>D=-1;h=6</p></td>
<td width="67.818%"><p>Every last day of the month at 06:00:00</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="32.182%"><p>D=[-7:-1];W=3;h=6</p></td>
<td width="67.818%"><p>Every last Wednesday of the month at 06:00:00</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="32.182%"><p>W=0</p></td>
<td width="67.818%"><p>Every Sunday at 00:00:00</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="32.182%"><p>W=1</p></td>
<td width="67.818%"><p>Every Monday at 00:00:00</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="32.182%"><p>M=1</p></td>
<td width="67.818%"><p>Every January, the first at 00:00:00</p></td>
</tr>
</tbody>
</table>

## CRONJOB messages

The possible cronjob messages are:

-   CFTI36I &str:
    Information Message about cronjobs load
-   CFTI38E &str:
    Error Message about cronjobs load
-   CFTS37I &str:
    Information Message about cronjob submit
-   CFTS39E &str:
    Error Message about cronjob submit

## CRONJOB symbolic variables

The table below lists the symbolic variables available in the CRONJOB
procedure. Define these using the EXEC parameter of the CFTCRON command.

<table data-cellspacing="0" width="90%">
<thead>
<tr class="header">
<th><p>Symbolic variable</p></th>
<th><p>Corresponding substituted value</p></th>
</tr>
</thead>
<tbody>
<tr class="odd" data-valign="top">
<td width="32.182%"><p>&amp;CFTEVENT</p></td>
<td width="67.818%">Fixed name=CRONJOB</td>
</tr>
<tr class="even" data-valign="top">
<td width="32.182%"><p>&amp;CFTNAME</p></td>
<td width="67.818%">The PART value in the command CFTPARM</td>
</tr>
<tr class="odd" data-valign="top">
<td width="32.182%"><p>&amp;SYSDATE</p></td>
<td width="67.818%"><p>System date</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="32.182%"><p>&amp;SYSTIME</p></td>
<td width="67.818%"><p>System time</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="32.182%"><p>&amp;SYSDAY</p></td>
<td width="67.818%"><p>Day of the week</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="32.182%"><p>&amp;NSUB</p></td>
<td width="67.818%"><p>Counter for all the Cronjob procedures launched</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="32.182%"><p>&amp;ID</p></td>
<td width="67.818%"><p>Cronjob Identifier</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="32.182%"><p>&amp;CRONTAB</p></td>
<td width="67.818%"><p>Crontab value</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="32.182%"><p>&amp;USERID</p></td>
<td width="67.818%"><p>User identifier indicated in CFTCRON command</p>
<p>On all platforms except z/OS, this variable is used for information purposes only (on z/OS the USERID performs the CRONJOB job submission).</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="32.182%"><p>&amp;COMMENT</p></td>
<td width="67.818%"><p>Comment value indicated in CFTCRON command</p></td>
</tr>
<tr class="odd" data-valign="top">
<td width="32.182%"><p>&amp;PARM</p></td>
<td width="67.818%"><p>Parm value indicated in CFTCRON command</p></td>
</tr>
<tr class="even" data-valign="top">
<td width="32.182%"><p>&amp;SCOUNT</p></td>
<td width="67.818%"><p>Counter for the Cronjob procedures launched for a specific
Identifier</p></td>
</tr>
</tbody>
</table>

Related
topics

-   Command syntax [CFTCRON](../../../command_summary)
