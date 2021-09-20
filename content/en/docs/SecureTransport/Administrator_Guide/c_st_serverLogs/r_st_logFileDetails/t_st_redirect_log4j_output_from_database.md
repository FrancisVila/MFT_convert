{
    "title": "Redirect log4j output from the database",
    "linkTitle": "Redirect log4j output from the database",
    "weight": "350"
}As listed in [Log4j files](../r_st_log4j_files), some log output is directed to both the `xferlog` file and the database.

If you set any log level to `debug` or `all`, SecureTransport produces many log messages which can overload the database. Do not log to the database for log level `debug` or `all`.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">When server log messages are stored in the database, they are displayed in the <em>Server Log</em> page. When you store the log messages in a file, they are not displayed in the <em>Server Log</em> page.         </td>
      </tr>
</table>

To direct the log messages being stored in the database to a file, modify the `ServerLog` appender for each relevant file. The example uses `FILEDRIVEHOME` instead of `<FILEDRIVEHOME>` to represent the SecureTransport installation directory to avoid confusion with the syntactic use of pointed brackets in XML. Replace the `<FILEDRIVEHOME>` with the actual installation path to the SecureTransport home folder in the XML configuration file.

Change:

    <STDBAppender name="ServerLog" locationInfo="true" maxLoggingEventQueueSize="10000" fallbackLogger="ServerLogFallback" databaseStatusCheckupDelay="60" databaseCheckupTimeout="30" idAreaBegin="-210000000000" idAreaEnd="-110000000000" driverClass="org.mysql.jdbc.Driver" initialPoolSize="30" (for AIX) driverClass="org.mariadb.jdbc.Driver" initialPoolSize="30" (for OS other than AIX) maxPoolSize="100" minPoolSize="30" acquireIncrement="7" maxStatements="4000">       <Filters>
             <STLog4JNDCFilter componentName="TM" onMatch="NEUTRAL" onMismatch="DENY"/>      </Filters>
    </STDBAppender>

**Note** The `dataSource` settings are different for each configuration file.

To:

    <DailyRollingFileAppender name="ServerLog" fileName="FILEDRIVEHOME/var/logs/tm.log" append="true" rotateDirectory="FILEDRIVEHOME/var/db/hist/logs/" datePattern="'.'yyyy-MM-dd">
          <PatternLayout pattern="%d{ISO8601} [%t] %p %c %equals{%x}{[]}{} - %m%n%ex"/>
    </DailyRollingFileAppender>

**Note** If the Server log messages are stored in a file (and it is using the DailyRollingFileAppender), rotation will be handled by the log4j files.

For example, if the File option is set to /foo/bar.log and the DatePattern set to '.'yyyy-MM-dd, on 2020-02-16 at midnight, the logging file /foo/bar.log will be copied to /foo/bar.log.2020-02-16 and logging for 2020-02-17 will continue in /foo/bar.log until it rolls over the next day.

In the `admin-log4j.xml` file there is an additional appender called `AuditLogAppender`. Change appender from:

    <STDBAppender name="AuditLogAppender" locationInfo="true" maxLoggingEventQueueSize="10000" fallbackLogger="ServerLogFallback" databaseStatusCheckupDelay="60" databaseCheckupTimeout="30" idAreaBegin="-40000000000" idAreaEnd="-30000000000" driverClass="org.mysql.jdbc.Driver" initialPoolSize="5" (for AIX) driverClass="org.mariadb.jdbc.Driver" initialPoolSize="5" (for OS other than AIX) maxPoolSize="25" minPoolSize="5" acquireIncrement="5" maxStatements="4000"      <Filters>         <STLog4JNDCFilter componentName="AUDIT" onMatch="NEUTRAL" onMismatch="DENY"/>      </Filters>
    </STDBAppender>

To:

    <DailyRollingFileAppender name="AuditLogAppender" fileName="FILEDRIVEHOME/var/logs/admin/audit-menu.log" append="true" rotateDirectory="FILEDRIVEHOME/var/db/hist/logs/admin" datePattern="'.'yyyy-MM-dd">
          <PatternLayout pattern="%d{ISO8601} [%t] %p %c %equals{%x}{[]}{} - %m%n%ex"/>
    </DailyRollingFileAppender>

**Related topics:**

-   [Log4j files](../r_st_log4j_files)
-   [Database log files](../c_st_database_log_files)
-   [FTPD log file](../c_st_ftpd_log_file)
-   [Admin log file](../c_st_admin_log_file)
-   [General log files](../c_st_general_log_files)
-   [Modify the log4j files](../t_st_change_log4j_files)
-   [Control log fallback from database to file](../t_st_control_log_fallback_from_database_to_file)
-   [Server log rotation and monitor scheduling](../t_st_server_log_rotation_scheduling)