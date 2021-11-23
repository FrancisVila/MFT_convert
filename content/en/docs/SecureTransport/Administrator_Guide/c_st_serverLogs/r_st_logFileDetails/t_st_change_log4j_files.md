{
    "title": "Modify the log4j files",
    "linkTitle": "Modify the log4j files",
    "weight": "330"
}You can set up the rotation of several log files based on the file size by editing the files listed under [Log4j files](../r_st_log4j_files#AppServerLogs_558321163_1039127).

## Configure Log rotation to a file per file-size

In this example, the configuration file is the TM log: `<FILEDRIVEHOME>/conf/tm-log4j.xml`. The example uses `FILEDRIVEHOME` instead of `<FILEDRIVEHOME>` to represent the {{< SecureTransport/componentshortname  >}} installation directory to avoid confusion with the syntactic use of pointed brackets in XML.

Change:



    <DailyRollingFileAppender name="ServerLog" fileName="FILEDRIVEHOME/var/logs/tm.log" append="true" rotateDirectory="FILEDRIVEHOME/var/db/hist/logs/" datePattern="'.'yyyy-MM-dd">
      <PatternLayout pattern="%d{ISO8601} [%t] %p %c %equals{%x}{[]}{} - %m%n%ex"/>
    </DailyRollingFileAppender>

To:



    <RollingFile name="ServerLog" fileName="FILEDRIVEHOME/var/logs/tm.log" append="true" filePattern="FILEDRIVEHOME/var/db/hist/logs/%d{yyyy-MM-dd}.tm.log">
      <PatternLayout pattern="%d{ISO8601} [%t] %p %c %equals{%x}{[]}{} - %m%n%ex"/>
      <DefaultRolloverStrategy max="5">
        <Delete basePath="FILEDRIVEHOME/var/db/hist/logs/" maxDepth="2">
          <IfFileName glob="*.tm.log" />
          <IfLastModified age="5d" />
        </Delete>
      </DefaultRolloverStrategy>
      <Policies>
        <TimeBasedTriggeringPolicy />
      </Policies>
    </RollingFile>

 

You can use any of the log4j file appenders.

> **Note:**
>
> For another way to manage log file rotation, see Log Entry Maintenance application.

## Attach logger to a non-blocking asynchronous appender

In some cases when the log messages are directed to a flat file, the rotation of the file might take a considerable amount of time during which certain {{< SecureTransport/securetransportname  >}} processes (including user log-in) are unavailable. This might happen, for example, when rotating a large log to a file which is hosted on a remote location.

In this case, you might consider attaching the rotating log to an asynchronous appender which is explicitly defined as not-blocking. To achieve this, use the following sample:



    <Async name="ServerLog" bufferSize="20000" blocking="false" includeLocation="false">
      <AppenderRef ref="DailyAppender"/>
    </Async>
    <DailyRollingFileAppender name="DailyAppender" fileName="FILEDRIVEHOME/var/logs/tm.log" append="true" rotateDirectory="FILEDRIVEHOME/var/db/hist/logs/" datePattern="'.'yyyy-MM-dd">
      <PatternLayout pattern="%d{ISO8601} [%t] %p %c %equals{%x}{[]}{} - %m%n%ex"/>
    </DailyRollingFileAppender>

> **Note:**
>
> It is recommended to set the buffer size according to the size of your log. In case the limit is reached during rotation, the logger might stop.

**Related topics:**

-   [Log4j files](../r_st_log4j_files)
-   [Database log files](../c_st_database_log_files)
-   [FTPD log file](../c_st_ftpd_log_file)
-   [Admin log file](../c_st_admin_log_file)
-   [General log files](../c_st_general_log_files)
-   [Redirect log4j output from the database](../t_st_redirect_log4j_output_from_database)
-   [Control log fallback from database to file](../t_st_control_log_fallback_from_database_to_file)
-   [Server log rotation and monitor scheduling](../t_st_server_log_rotation_scheduling)
