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

<table cellspacing="0">   <col/>   <tbody>      <tr>         <td>            <p>CFTPARM ID=IDPARM0, ..., CRONTABS=(CRONTAB1, CRONTAB2, CRONTAB3)</p>            <p>CFTCRON ID=CRON1, CRONTAB=CRONTAB1,STATE=ACTIVE, ...</p>            <p>CFTCRON ID=CRON2, CRONTAB=CRONTAB2,STATE=ACTIVE, ...</p>            <p>CFTCRON ID=CRON3, CRONTAB=CRONTAB3,STATE=ACTIVE, ...</p>            <p>CFTCRON ID=CRON4, CRONTAB=CRONTAB1,STATE=INACTIVE ...</p>         </td>      </tr>   </tbody></table>

**Example directly processing (UNIX and Windows)**

<table cellspacing="0">   <col/>   <tbody>      <tr>         <td>            <p>ACT type=CRON, ID=CRON4</p>         </td>      </tr>   </tbody></table>

### Time syntax

The time syntax is case sensitive. For example, a lower case m defines
minutes, while an upper case M defines months.

-   Bold characters
    are terminators
-   Italic characters
    are grammar rule non-terminators
-   A, b, c are integers

<table cellspacing="0">   <col/>   <tbody>      <tr>         <td>            <p>INACT type=CRON, ID=CRON1</p>         </td>      </tr>   </tbody></table>

### Time parameter descriptions

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CFTUTIL CFTCRON id=CRON1, crontab=CRONTAB1, EXEC=my_exec, 
 time='m=*/10'</p>
         </td>
      </tr>
   </tbody>
</table>

### Time syntax examples

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CFTUTIL CFTCRON id=CRON1, crontab=CRONTAB1, EXEC='cmd:my_exec &amp;ID', 
 time='m=*/10'</p>
         </td>
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

<table cellspacing="0" width="90%">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr data-mc-conditions="">
         <th>
            <p>Rule</p>
</th>
         <th>
            <p>Syntax</p>
</th>
         <th>
            <p>Alternate syntax</p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr data-mc-conditions="" valign="top">
         <td colspan="1" rowspan="1" width="23.077%">
            <p>time </p>
         </td>
         <td width="35.647%">
            <p>time_element; time</p>
            <p>time_element</p>
         </td>
         <td width="38.274%">
            <p> </p>
         </td>
      </tr>
      <tr data-mc-conditions="" valign="top">
         <td colspan="1" rowspan="1" width="23.077%">
            <p>time_element</p>
         </td>
         <td width="35.647%">
            <p>seconds= content</p>
            <p>minutes= content</p>
            <p>hours= content</p>
            <p>monthdays= content</p>
            <p>weekdays= content</p>
            <p>months= content</p>
         </td>
         <td width="38.274%">
            <p>s= content</p>
            <p>m= content</p>
            <p>h= content</p>
            <p>D= content</p>
            <p>W= content</p>
            <p>M= content</p>
         </td>
      </tr>
      <tr data-mc-conditions="" valign="top">
         <td colspan="1" rowspan="1" width="23.077%">
            <p>content</p>
         </td>
         <td width="35.647%">
            <p>content_elt, content</p>
            <p>content_elt </p>
         </td>
         <td width="38.274%">
            <p> </p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="23.077%">
            <p>content_elt</p>
         </td>
         <td colspan="1" rowspan="1" width="35.647%">
            <p>a</p>
            <p>content_set / c</p>
         </td>
         <td colspan="1" rowspan="1" width="38.274%">
            <p> </p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="2" rowspan="1" width="58.724%">
            <p> </p>
         </td>
         <td colspan="1" rowspan="1" width="38.274%">
            <p>z/OS (MVS) specific syntax</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="23.077%">
            <p>content_set</p>
         </td>
         <td colspan="1" rowspan="1" width="35.647%">
            <p>[a:b] [a:b]</p>
            <p>[a:]</p>
            <p>[:b]</p>
            <p>*</p>
         </td>
         <td colspan="1" rowspan="1" width="38.274%">
            <p>&lt;a:b&gt;</p>
            <p>&lt;a:&gt;</p>
            <p>&lt;:b&gt;</p>
         </td>
      </tr>
   </tbody>
</table>

Related
topics

-   Command syntax [CFTCRON](../../../command_summary)
