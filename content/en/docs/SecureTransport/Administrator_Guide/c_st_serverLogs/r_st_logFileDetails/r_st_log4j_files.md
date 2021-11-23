{
    "title": "Log4j files",
    "linkTitle": "Log4j files",
    "weight": "280"
}A number of the log files and some log output to the database use the log4j format. For more information, refer to the log4j documentation on the Apache web site.

Unless otherwise specified, by default, the logs are in the following format:

`%d %p [%t] %c - %m`

where:

-   `%d` is the date
-   `%p` is the error level
-   `%t` is the thread ID
-   `%c` is the Java class name
-   `%m` is the log message

You might also find Java stack traces in these logs. {{< SecureTransport/companyname  >}} Global Support can use these to determine the cause of a particular error condition.

The following table log4j configuration files in `<FILEDRIVEHOME>/conf`, the log output they control, and the default destinations.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Configuration file name         </th>
<th class="HeadE-Column1-Header1">Log output         </th>
<th class="HeadD-Column1-Header1">Destinations         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><code>admin-log4j.xml</code>         </td>
         <td>Administration Tool server         </td>
         <td><p>Database</p>
<p><code>audit.log</code></p>
<p><code>migration.log</code></p>         </td>
      </tr>
      <tr>
         <td><code>as2d-log4j.xml</code>         </td>
         <td>AS2 Server         </td>
         <td><p>Database<br />
<code>xferlog</code></p>         </td>
      </tr>
      <tr>
         <td><code>ftpd-log4j.xml</code>         </td>
         <td>FTP Server         </td>
         <td><p>Database<br />
<code>xferlog</code></p>         </td>
      </tr>
      <tr>
         <td><code>httpd-log4j.xml</code>         </td>
         <td>HTTP Server         </td>
         <td><p>Database<br />
<code>xferlog</code></p>         </td>
      </tr>
      <tr>
         <td><code>pesitd-log4j.xml</code>         </td>
         <td>PeSIT Server         </td>
         <td><p>Database<br />
<code>xferlog</code></p>         </td>
      </tr>
      <tr>
         <td><code>socks-log4j.xml</code><br />
(Only on {{< SecureTransport/componentshortname  >}} Edge)         </td>
         <td>SOCKS5 proxy         </td>
         <td><p>Database</p>         </td>
      </tr>
      <tr>
         <td><code>sshd-log4j.xml</code>         </td>
         <td>SSH Server         </td>
         <td><p>Database<br />
<code>xferlog</code></p>         </td>
      </tr>
      <tr>
         <td><p><code>tm-log4j.xml</code></p>
<p>(Only on {{< SecureTransport/componentshortname  >}} Server)</p>         </td>
         <td><p>TM Server</p>
<p>internal agents</p>         </td>
         <td><p>Database<br />
<code>xferlog</code></p>         </td>
      </tr>
      <tr>
         <td><code>tools-log4j.xml</code>         </td>
         <td><p>Data migration<br />
Export/import<br />
Various components</p>         </td>
         <td><p>Database<br />
Java console<br />
<code>tools</code><code>.log</code></p>         </td>
      </tr>
   </tbody>
</table>

In an Enterprise Cluster (EC), when the database does not accept log messages fast enough and the queue becomes full, the servers listed in the table store their log messages in a buffer file until the database can accept them. See [Control log fallback from database to file](../t_st_control_log_fallback_from_database_to_file#Control).

The behavior for each server is controlled by the following parameters in their respective log4j files:

-   `queueAwaitDefaultTimeout`: Time in milliseconds to wait for the
    queue to free up when full (default 5000 milliseconds)
-   `queueAwaitMinTimeout`: Minimum time in milliseconds of the queue
    wait period (default 50 milliseconds)
-   `queueAwaitFactor`: Factor used to adjust queue wait time (default
    1000). This value is divided by the number of events that have not
    been saved in the database, and the result is subtracted from the
    current timeout to get the time to wait until the next event is
    sent to database. If the result is less than the
    `queueAwaitMinTimeout` value, `queueAwaitMinTimeout` is used instead.

With a larger value of `queueAwaitFactor`, future events do not wait
as long and the system is more responsive. With a smaller value,
future events wait longer before they are sent to the database so
the load on the database is reduced and the system response might
be reduced.

*next-event-await-period* = maximum(`queueAwaitMinTimeout`,
*last-event-await-period* - `queueAwaitFactor` / *number-of-events*)

With the default values for the parameters, the initial value of
*next-event-await-period* is 5000 milliseconds. When there are 2
events that have not been saved to the database, the time to wait
is reduced by 1000/2 = 500 milliseconds until it reaches 50
milliseconds.

When database communication returns to normal and the database
starts to accept log messages again, *next-event-await-period* is
reset to `queueAwaitDefaultTimeout` and *number-of-events* is reset
to zero.

`date time [process ID]: username: command`

**Related topics:**

-   [Database log files](../c_st_database_log_files)
-   [FTPD log file](../c_st_ftpd_log_file)
-   [Admin log file](../c_st_admin_log_file)
-   [General log files](../c_st_general_log_files)
-   [Modify the log4j files](../t_st_change_log4j_files)
-   [Redirect log4j output from the database](../t_st_redirect_log4j_output_from_database)
-   [Control log fallback from database to file](../t_st_control_log_fallback_from_database_to_file)
-   [Server log rotation and monitor scheduling](../t_st_server_log_rotation_scheduling)
