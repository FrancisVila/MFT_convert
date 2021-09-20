{
    "title": "Log file list",
    "linkTitle": "Log file list",
    "weight": "260"
}SecureTransport writes to several log files in multiple locations. These files can be used to monitor SecureTransport processes and identify any issues that can occur. Some messages are logged directly to the database and are visible in the *Server Log* page. For more information, see [Server log](../../operations_menu/t_st_serverlog).

You can open log files in a text editor to review them and to find specific messages.

The following table describes the log files used by SecureTransport and provides the location and a brief description of each file. Several log files share the same name. When viewing the table, make sure that you note the location of the log file you want to find.

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>File name</th>
         <th>Directory</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><code>audit.log</code>
         </td>
         <td><code>&lt;FILEDRIVEHOME&gt;/<br/>var/logs/admin</code>
         </td>
         <td>Records failed administrator login attempts, embedded database restart from Administrative tool, and database configuration change events for either the embedded or external database.         </td>
      </tr>
      <tr>
         <td><code>catalina.out</code>
         </td>
         <td><code>&lt;FILEDRIVEHOME&gt;/<br/>tomcat/admin/logs</code>
         </td>
         <td>Records unhandled exceptions in Java components in the Administration Tool and information about the servlets, including information about errors.         </td>
      </tr>
      <tr>
         <td><code>catalina.out</code>
         </td>
         <td><code>&lt;FILEDRIVEHOME&gt;/<br/>tomcat/as2/logs</code>
         </td>
         <td>Records AS2 protocol connection unhandled exceptions and information about the servlets, including information about errors.         </td>
      </tr>
      <tr>
         <td><code>cmdlog</code>
         </td>
         <td><code>&lt;FILEDRIVEHOME&gt;/<br/>var/logs</code>
         </td>
         <td>Records FTP commands and arguments that are sent by FTP clients after they connect successfully.         </td>
      </tr>
      <tr>
         <td><code>migration.log</code>
         </td>
         <td><code>&lt;FILEDRIVEHOME&gt;/<br/>var/logs</code>
         </td>
         <td>Records information generated during database migration from the embedded database to an Oracle database.         </td>
      </tr>
      <tr>
         <td><code>monitor_*.out</code>
         </td>
         <td><code>&lt;FILEDRIVEHOME&gt;/<br/>var/logs</code>
         </td>
         <td>Records monitor server output in a separate file for each monitored server.         </td>
      </tr>
      <tr>
         <td>
            <p><code>mariadb_error.log</code>
</p>
            <p><code>mysql_error.log</code>
</p>
         </td>
         <td><code>&lt;FILEDRIVEHOME&gt;/<br/>var/logs</code>
         </td>
         <td>
            <p>Records information about the embedded database for <span>SecureTransport</span> Edge and <span>SecureTransport</span> Server deployments that use an embedded database.</p>
            <p>Not used in deployments that use an external database.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p><code>mariadb_slow_query.log </code>
</p>
            <p><code>mysql_slow_query.log</code>
</p>
         </td>
         <td><code>&lt;FILEDRIVEHOME&gt;/<br/>var/logs</code>
         </td>
         <td>
            <p>Lists queries that took longer than a given time to execute for <span>SecureTransport</span> Edge and <span>SecureTransport</span> Server deployments that use an embedded database. The file name and time limit are configurable in <code>internaldb.conf</code> for MariaDB and MySQL.</p>
            <p>Not used in deployments that use an external database.</p>
         </td>
      </tr>
      <tr>
         <td><code>serverlog-fallback.log</code>
         </td>
         <td><code>&lt;FILEDRIVEHOME&gt;/<br/>var/logs/admin</code>
         </td>
         <td>Records server log messages when the  server log database fails for either the embedded or external database.         </td>
      </tr>
      <tr>
         <td><code>tm.stdout.log</code>
         </td>
         <td><code>&lt;FILEDRIVEHOME&gt;/<br/>var/logs</code>
         </td>
         <td>Records standard output from Transaction Manager processes.         </td>
      </tr>
      <tr>
         <td><code>tm_agent_error.log</code>
         </td>
         <td><code>&lt;FILEDRIVEHOME&gt;/<br/>var/logs</code>
         </td>
         <td>Records errors about Transaction Manager operations and in-process agents. On Unix-like systems, it also records external script's standard error (stderr).          </td>
      </tr>
      <tr>
         <td><code>tools.log</code>
         </td>
         <td><code>&lt;FILEDRIVEHOME&gt;/<br/>var/logs</code>
         </td>
         <td>Records warnings and errors from internal <span>SecureTransport</span> components.         </td>
      </tr>
      <tr>
         <td><code>AxwaySecureTransport<br/>Admin_SecureTransport.log</code>
         </td>
         <td><code>&lt;FILEDRIVEHOME&gt;/<br/>../cygwin/var/log</code>
         </td>
         <td>A Windows-specific log file where information about the <code>AxwaySecureTranport<br/>Admin_5.3.0</code> service is recorded.         </td>
      </tr>
      <tr>
         <td><code>AxwaySecureTransport<br/>AS2d_SecureTransport.log</code>
         </td>
         <td><code>&lt;FILEDRIVEHOME&gt;/<br/>../cygwin/var/log</code>
         </td>
         <td>A Windows-specific log file where information about the <code>AxwaySecureTranport<br/>AS2d</code> service is recorded.         </td>
      </tr>
      <tr>
         <td><code>AxwaySecureTransport<br/>FTPd_SecureTransport.log</code>
         </td>
         <td><code>&lt;FILEDRIVEHOME&gt;/<br/>../cygwin/var/log</code>
         </td>
         <td>A Windows-specific log file where information about the <code>AxwaySecureTranport<br/>FTPd</code> service is recorded.         </td>
      </tr>
      <tr>
         <td><code>AxwaySecureTransport<br/>HTTPd_SecureTransport.log</code>
         </td>
         <td><code>&lt;FILEDRIVEHOME&gt;/<br/>../cygwin/var/log</code>
         </td>
         <td>A Windows-specific log file where information about the <code>AxwaySecureTranport<br/>HTTPd</code> service is recorded.         </td>
      </tr>
      <tr>
         <td><code>AxwaySecureTransport<br/>SSHd_SecureTransport.log</code>
         </td>
         <td><code>&lt;FILEDRIVEHOME&gt;/<br/>../cygwin/var/log</code>
         </td>
         <td>A Windows-specific log file where information about the <code>AxwaySecureTranport<br/>SSHd</code> service is recorded.         </td>
      </tr>
      <tr>
         <td><code>AxwaySecureTransport<br/>PeSITd_SecureTransport.log</code>
         </td>
         <td><code>&lt;FILEDRIVEHOME&gt;/<br/>../cygwin/var/log</code>
         </td>
         <td>A Windows-specific log file where information about the <code>AxwaySecureTransport<br/>PeSITd</code> service is recorded.         </td>
      </tr>
      <tr>
         <td><code>AxwaySecureTransport<br/>TM_SecureTransport.log</code>
         </td>
         <td><code>&lt;FILEDRIVEHOME&gt;/<br/>../cygwin/var/log</code>
         </td>
         <td>A Windows-specific log file where information about the <code>AxwaySecureTransportTM</code> (Transaction Manager) service is recorded.         </td>
      </tr>
      <tr>
         <td><code>AxwaySecureTransport<br/>Database_SecureTransport.log</code>
         </td>
         <td><code>&lt;FILEDRIVEHOME&gt;/<br/>../cygwin/var/log</code>
         </td>
         <td>A Windows-specific log file where information about the <code>AxwaySecureTransportMYSQL</code> or <code>AxwaySecureTransportMARIADB</code>(embedded database) service is recorded when it is used.         </td>
      </tr>
      <tr>
         <td><code>xferlog</code>
         </td>
         <td><code>&lt;FILEDRIVEHOME&gt;/<br/>var/logs</code>
         </td>
         <td>Records information about FTP(S), HTTP(S), SFTP, AS2, Connect:Direct, Folder Monitor, and PeSIT transfers. For more information, see <a href="../../operations_menu/c_st_filetransfertracking">Track file transfer activity</a> and <a href="../../c_st_setup/t_st_transferlogconfiguration">Configure transfer log</a>.         </td>
      </tr>
   </tbody>
</table>
