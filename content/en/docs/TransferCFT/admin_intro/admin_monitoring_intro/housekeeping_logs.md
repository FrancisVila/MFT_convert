{
    "title": "Housekeeping for log files ",
    "linkTitle": "Housekeeping for log files ",
    "weight": "290"
}# Housekeeping for log files



Transfer CFT logs all events, log messages, in a dedicated log file. While this information helps in detecting problems, it is important to note that the size of the Transfer CFT log files continually increases if no precautions are taken.



It is readable by the user via the Central Governance user interface or the CFTUTIL listlog command.



## Rotate or switch log files



You can customize either the rotate or switch procedure to archive and clean out old log files.



On UNIX or Windows platforms the EXEC value is not mandatory, and by default an internal procedure is used. While there are several logging (CFTLOG) parameters that you can manage with <span>Central Governance</span>, if you need to modify the EXEC procedure you are required to use CFTUTIL.



The rotate and switch procedures can use the symbolic variables, &amp;FLOG,

for the name of the log file.



### Rotate procedures



UNIX/Windows



#### Use the internal log rotation procedure



To enable the internal log rotation procedure, leave the EXEC parameter set to empty (EXEC=''). The internal procedure uses the UCONF cft.cftlog.backup\_count parameter to define the maximum number of log archives to keep.



#### Use a custom log rotation procedure



To create a custom log rotation procedure, you can use the sample file `rotate.cmd`, which is delivered with <span>Transfer CFT</span> in the &lt;runtime/exec&gt; directory, as a basis for your own procedure.



### Switch procedure



*All platforms*



You can manage the switch procedure using various methods that include, but not limited to, the following:



-   File naming: Creates a log file each day using the same file name with a timestamp extension. Existing files are not removed.







-   Archiving: Transfer CFT log files are stored in the runtime directory, log file names are cftlog-&lt;timestamp&gt; where timestamp is the date and time the switch procedure switch.cmd is triggered by <span>Transfer CFT</span>.



<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr>
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">At least one of the two files (either the log or alternate log file) must be empty prior to starting Transfer CFT.</td>
</tr>
</tbody>
</table>



#### Use the SWITCH command



To manually execute the log procedure, use the command:



<table data-cellspacing="0">
<tbody>
<tr>
<td>SWITCH TYPE=LOG</td>
</tr>
</tbody>
</table>



A file can automatically be switched to another file by means of one of 4 events:



-   a daily schedule

    set by the SWITCH parameter



-   the number of records

    written in the current log file exceeds the limit set by the MAXREC parameter

    or, depending on the OS, the file is full



-   <span>Transfer CFT</span> is

    shut down via the SHUT command



-   <table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr>
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">To customize the switch that occurs when Transfer CFT shuts down, modify the UCONF parameter <code>cft.cftlog.switch_on_stop=YES</code> (the default value is NO).</td>
</tr>
</tbody>
</table>



-   <span>Transfer CFT</span> is

    activated



#### Limit entries in the log



For each transfer, there are multiple messages generated. You can significantly reduce the number of messages by using the CONTENT=BRIEF parameter setting in the log setting (CFTLOG).



#### Sending log messages to Sentinel



When <span>Transfer CFT</span> sends log messages to Sentinel or Central Governance, you can filter by the level of severity according to its type: warning, error, or fatal error. For example, to send only FATAL errors you could set the following value:



<table data-cellspacing="0">
<tbody>
<tr>
<td>UCONFSET id=sentinel.xfb.log,value=F</td>
</tr>
</tbody>
</table>



## Creating an exclusion log filter



<span>Transfer CFT</span> can filter log messages according to predefined filters to exclude certain types of messages. To create a filter, customize the following uconf parameters to create the required filter pattern with one or more of the following characteristics:



-   cft.server.log.exclude\_filters = ID1 ID2 ID3

    -   Space separated list of filter identifiers

    -   Only the log filters in the list are activated

-   cft.server.log.exclude\_filters.ID.pattern=

    -   The pattern matches a Log messages that is to be excluded from all logs (log output, log file and Sentinel)

-   cft.server.log.exclude\_filters.ID.comment=

    -   A free field that you can use to describe the filter



**Example**



<table data-cellspacing="0">
<tbody>
<tr>
<td>CFTUTIL UCONFSET ID =cft.server.log.exclude_filters,<br/>

VALUE =cron_heartbeat<br/>

CFTUTIL UCONFSET ID =cft.server.log.exclude_filters.cron_heartbeat.pattern,<br/>

VALUE =CFTS37*ID=HEARTBEAT*<br/>

CFTUTIL UCONFSET ID =cft.server.log.exclude_filters.cron_heartbeat.comment,<br/>

VALUE ="Excludes from the log all cronjob messages concerning the ID HEARTBEAT"</td>
</tr>
</tbody>
</table>



## Create a daily log file rotation



Available on Unix, Windows, and iSeries environments



This section describes how to create daily, rolling log files that are not impacted by the number of Transfer CFT reboots.



If you need to check the current switch hour for the log, using CFTUTIL enter:



<table data-cellspacing="0">
<tbody>
<tr>
<td>mquery name=command</td>
</tr>
</tbody>
</table>



Then enter the <span>listlog </span>command:



<table data-cellspacing="0">
<tbody>
<tr>
<td><p>listlog</p>
<p>...</p>
<p>CFTI24I *** DATE=DD/MM/YYYY TIME= 00:00:00.00 SWITCH LOG</p></td>
</tr>
</tbody>
</table>



### Configure the log file switch



1.  If not already done, set the CFTLOG object's `SWITCH `parameter to the default value so that the rotation occurs at midnight. The MAXREC parameter should also be set to its default so that there is  no file rotation if the maximum records is reached.

2.  Using CFTUTIL, set the following uconf values:



<table data-cellspacing="0">
<tbody>
<tr>
<td>uconfset id=cft.cftlog.switch_on_start,value=No

<p>uconfset id=cft.cftlog.backup_count, value=6</p>
<p>uconfset id=cft.cftlog.switch_on_stop, value=No</p></td>
</tr>
</tbody>
</table>



This results in the switch being executed automatically every night at midnight, giving you a single daily log file (unless you execute another switch command), where:



-   The `cftlog` file in the `$CFTDIRLOG `folder (runtime/log) that has no extension is the current day's log.

-   The` cftlog.n` is the log file corresponding to the current day *- n* days. For example, if today is Sunday, `cftlog.2` would be Friday's log file.

-   There are a total of 7 log files in the folder, one for each day, as the <span>backup\_count</span> value is 6 (6 backups plus 1 current).



## Configure log to switch only when the current file is full



If you would like to switch the log file only when the maximum number of records is reached, and not automatically switch on starting, set the following:



1.  Using CFTUTIL, set the following uconf values:

2.  Modify the <span>CFTLOG </span>object by setting the predetermined number of records, the <span>MAXREC </span>parameter. When this value is reached the log is switched.

3.  Restart after modifying values.

