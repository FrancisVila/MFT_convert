{
    "title": "Modify the log4j files",
    "linkTitle": "Modify the log4j files",
    "weight": "340"
}You can set up the rotation of several log files based on the file size by editing the files listed under [Log4j files](../r_st_log4j_files).

## Configure Log rotation to a file per file-size

In this example, the configuration file is the TM log: `<FILEDRIVEHOME>/conf/tm-log4j.xml`. The example uses `FILEDRIVEHOME` instead of `<FILEDRIVEHOME>` to represent the SecureTransport installation directory to avoid confusion with the syntactic use of pointed brackets in XML.

Change:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>&lt;DailyRollingFileAppender name="ServerLog" fileName="FILEDRIVEHOME/var/logs/tm.log" append="true" rotateDirectory="FILEDRIVEHOME/var/db/hist/logs/" datePattern="'.'yyyy-MM-dd"&gt;</p>
            <p>  &lt;PatternLayout pattern="%d{ISO8601} [%t] %p %c %equals{%x}{[]}{} - %m%n%ex"/&gt;</p>
            <p>&lt;/DailyRollingFileAppender&gt;</p>
         </td>
      </tr>
   </tbody>
</table>

To:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>&lt;RollingFile name="ServerLog" fileName="FILEDRIVEHOME/var/logs/tm.log" append="true" filePattern="FILEDRIVEHOME/var/db/hist/logs/%d{yyyy-MM-dd}.tm.log"&gt;</p>
            <p>  &lt;PatternLayout pattern="%d{ISO8601} [%t] %p %c %equals{%x}{[]}{} - %m%n%ex"/&gt;</p>
            <p>  &lt;DefaultRolloverStrategy max="5"&gt;</p>
            <p>    &lt;Delete basePath="FILEDRIVEHOME/var/db/hist/logs/" maxDepth="2"&gt;</p>
            <p>      &lt;IfFileName glob="*.tm.log" /&gt;</p>
            <p>      &lt;IfLastModified age="5d" /&gt;</p>
            <p>    &lt;/Delete&gt;</p>
            <p>  &lt;/DefaultRolloverStrategy&gt;</p>
            <p>  &lt;Policies&gt;</p>
            <p>    &lt;TimeBasedTriggeringPolicy /&gt;</p>
            <p>  &lt;/Policies&gt;</p>
            <p>&lt;/RollingFile&gt;</p>
         </td>
      </tr>
   </tbody>
</table>

 

You can use any of the log4j file appenders.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">For another way to manage log file rotation, see <a href="../../../applications/applicationslogentrymaintenance">Log Entry Maintenance application</a>.         </td>
      </tr>
</table>

## Attach logger to a non-blocking asynchronous appender

In some cases when the log messages are directed to a flat file, the rotation of the file might take a considerable amount of time during which certain SecureTransport processes (including user log-in) are unavailable. This might happen, for example, when rotating a large log to a file which is hosted on a remote location.

In this case, you might consider attaching the rotating log to an asynchronous appender which is explicitly defined as not-blocking. To achieve this, use the following sample:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>&lt;Async name="ServerLog" bufferSize="20000" blocking="false" includeLocation="false"&gt;</p>
            <p>  &lt;AppenderRef ref="DailyAppender"/&gt;</p>
            <p>&lt;/Async&gt;</p>
            <p>&lt;DailyRollingFileAppender name="DailyAppender" fileName="FILEDRIVEHOME/var/logs/tm.log" append="true" rotateDirectory="FILEDRIVEHOME/var/db/hist/logs/" datePattern="'.'yyyy-MM-dd"&gt;</p>
            <p>  &lt;PatternLayout pattern="%d{ISO8601} [%t] %p %c %equals{%x}{[]}{} - %m%n%ex"/&gt;</p>
            <p>&lt;/DailyRollingFileAppender&gt;</p>
         </td>
      </tr>
   </tbody>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">It is recommended to set the buffer size according to the size of your log. In case the limit is reached during rotation, the logger might stop.         </td>
      </tr>
</table>

**Related topics:**

-   [Log4j files](../r_st_log4j_files)
-   [Database log files](../c_st_database_log_files)
-   [FTPD log file](../c_st_ftpd_log_file)
-   [Admin log file](../c_st_admin_log_file)
-   [General log files](../c_st_general_log_files)
-   [Redirect log4j output from the database](../t_st_redirect_log4j_output_from_database)
-   [Control log fallback from database to file](../t_st_control_log_fallback_from_database_to_file)
-   [Server log rotation and monitor scheduling](../t_st_server_log_rotation_scheduling)
