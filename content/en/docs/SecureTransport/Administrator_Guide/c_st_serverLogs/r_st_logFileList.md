{
    "title": "Log file list",
    "linkTitle": "Log file list",
    "weight": "250"
}{{< SecureTransport/componentshortname  >}} writes to several log files in multiple locations. These files can be used to monitor {{< SecureTransport/componentshortname  >}} processes and identify any issues that can occur. Some messages are logged directly to the database and are visible in the *Server Log* page. For more information, see [Server log](../../operations_menu/t_st_serverlog#ServerMenu_1832073003_1052443).

You can open log files in a text editor to review them and to find specific messages.

The following table describes the log files used by {{< SecureTransport/componentshortname  >}} and provides the location and a brief description of each file. Several log files share the same name. When viewing the table, make sure that you note the location of the log file you want to find.

| File name| Directory<th class="HeadD-Column1-Header1">Description      | 
| <code>audit.log</code>| <code>&lt;FILEDRIVEHOME&gt;/var/logs/admin</code>| Records failed administrator login attempts, embedded database restart from Administrative tool, and database configuration change events for either the embedded or external database.      | 
| <code>catalina.out</code>| <code>&lt;FILEDRIVEHOME&gt;/tomcat/admin/logs</code>| Records unhandled exceptions in Java components in the Administration Tool and information about the servlets, including information about errors.      | 
| <code>catalina.out</code>| <code>&lt;FILEDRIVEHOME&gt;/tomcat/as2/logs</code>| Records AS2 protocol connection unhandled exceptions and information about the servlets, including information about errors.      | 


## HTML table
<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">File name         </th>
<th class="HeadE-Column1-Header1">Directory         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><code>audit.log</code>         </td>
         <td><code>&lt;FILEDRIVEHOME&gt;/var/logs/admin</code>         </td>
         <td>Records failed administrator login attempts, embedded database restart from Administrative tool, and database configuration change events for either the embedded or external database.         </td>
      </tr>
      <tr>
         <td><code>catalina.out</code>         </td>
         <td><code>&lt;FILEDRIVEHOME&gt;/tomcat/admin/logs</code>         </td>
         <td>Records unhandled exceptions in Java components in the Administration Tool and information about the servlets, including information about errors.         </td>
      </tr>
      <tr>
         <td><code>catalina.out</code>         </td>
         <td><code>&lt;FILEDRIVEHOME&gt;/tomcat/as2/logs</code>         </td>
         <td>Records AS2 protocol connection unhandled exceptions and information about the servlets, including information about errors.         </td>
      </tr>
   </tbody>
</table>

## Notepad++ macro

|File name|Directory|Description|
| -- | -- | --      |
| <code>audit.log</code>| <code>&lt;FILEDRIVEHOME&gt;/var/logs/admin</code>| Records failed administrator login attempts, embedded database restart from Administrative tool, and database configuration change events for either the embedded or external database.      |
| <code>catalina.out</code>| <code>&lt;FILEDRIVEHOME&gt;/tomcat/admin/logs</code>| Records unhandled exceptions in Java components in the Administration Tool and information about the servlets, including information about errors.      |
| <code>catalina.out</code>| <code>&lt;FILEDRIVEHOME&gt;/tomcat/as2/logs</code>| Records AS2 protocol connection unhandled exceptions and information about the servlets, including information about errors.      |

## Manual markdown

| File name | Directory | Description |
| --- | --- | --- |
|  `audit.log` | `<FILEDRIVEHOME>/var/logs/admin` | Records failed administrator login attempts, embedded database restart from Administrative tool, and database configuration change events for either the embedded or external database.|
|  `catalina.out` | `<FILEDRIVEHOME>/tomcat/admin/logs`   | Records unhandled exceptions in Java components in the Administration Tool and information about the servlets, including information about errors.|
|  `catalina.out`| `<FILEDRIVEHOME>/tomcat/as2/logs` | Records AS2 protocol connection unhandled exceptions and information about the servlets, including information about errors.|


## Pypandoc output to='md'

 File name        Directory                             Description
  ---------------- ------------------------------------- ----------------------------------------------------------------------------
-------------------------------------------------------------------------------------------------------------
  `audit.log`      `<FILEDRIVEHOME>/var/logs/admin`      Records failed administrator login attempts, embedded database restart from
Administrative tool, and database configuration change events for either the embedded or external database.
  `catalina.out`   `<FILEDRIVEHOME>/tomcat/admin/logs`   Records unhandled exceptions in Java components in the Administration Tool a
nd information about the servlets, including information about errors.
  `catalina.out`   `<FILEDRIVEHOME>/tomcat/as2/logs`     Records AS2 protocol connection unhandled exceptions and information about t
he servlets, including information about errors.


## HTML table

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">File name         </th>
<th class="HeadE-Column1-Header1">Directory         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><code>audit.log</code>         </td>
         <td><code>&lt;FILEDRIVEHOME&gt;/var/logs/admin</code>         </td>
         <td>Records failed administrator login attempts, embedded database restart from Administrative tool, and database configuration change events for either the embedded or external database.         </td>
      </tr>
      <tr>
         <td><code>catalina.out</code>         </td>
         <td><code>&lt;FILEDRIVEHOME&gt;/tomcat/admin/logs</code>         </td>
         <td>Records unhandled exceptions in Java components in the Administration Tool and information about the servlets, including information about errors.         </td>
      </tr>
      <tr>
         <td><code>catalina.out</code>         </td>
         <td><code>&lt;FILEDRIVEHOME&gt;/tomcat/as2/logs</code>         </td>
         <td>Records AS2 protocol connection unhandled exceptions and information about the servlets, including information about errors.         </td>
      </tr>
      <tr>
         <td><code>cmdlog</code>         </td>
         <td><code>&lt;FILEDRIVEHOME&gt;/var/logs</code>         </td>
         <td>Records FTP commands and arguments that are sent by FTP clients after they connect successfully.         </td>
      </tr>
      <tr>
         <td><code>migration.log</code>         </td>
         <td><code>&lt;FILEDRIVEHOME&gt;/var/logs</code>         </td>
         <td>Records information generated during database migration from the embedded database to an Oracle database.         </td>
      </tr>
      <tr>
         <td><code>monitor_*.out</code>         </td>
         <td><code>&lt;FILEDRIVEHOME&gt;/var/logs</code>         </td>
         <td>Records monitor server output in a separate file for each monitored server.         </td>
      </tr>
      <tr>
         <td><p><code>mariadb_error.log</code></p>
<p><code>mysql_error.log</code></p>         </td>
         <td><code>&lt;FILEDRIVEHOME&gt;/var/logs</code>         </td>
         <td><p>Records information about the embedded database for {{< SecureTransport/componentshortname  >}} Edge and {{< SecureTransport/componentshortname  >}} Server deployments that use an embedded database.</p>
<p>Not used in deployments that use an external database.</p>         </td>
      </tr>
      <tr>
         <td><p><code>mariadb_slow_query.log </code></p>
<p><code>mysql_slow_query.log</code></p>         </td>
         <td><code>&lt;FILEDRIVEHOME&gt;/var/logs</code>         </td>
         <td><p>Lists queries that took longer than a given time to execute for {{< SecureTransport/componentshortname  >}} Edge and {{< SecureTransport/componentshortname  >}} Server deployments that use an embedded database. The file name and time limit are configurable in <code>internaldb.conf</code> for MariaDB and MySQL.</p>
<p>Not used in deployments that use an external database.</p>         </td>
      </tr>
      <tr>
         <td><code>serverlog-fallback.log</code>         </td>
         <td><code>&lt;FILEDRIVEHOME&gt;/var/logs/admin</code>         </td>
         <td>Records server log messages when the server log database fails for either the embedded or external database.         </td>
      </tr>
      <tr>
         <td><code>tm.stdout.log</code>         </td>
         <td><code>&lt;FILEDRIVEHOME&gt;/var/logs</code>         </td>
         <td>Records standard output from Transaction Manager processes.         </td>
      </tr>
      <tr>
         <td><code>tm_agent_error.log</code>         </td>
         <td><code>&lt;FILEDRIVEHOME&gt;/var/logs</code>         </td>
         <td>Records errors about Transaction Manager operations and in-process agents. On Unix-like systems, it also records external script's standard error (stderr).         </td>
      </tr>
      <tr>
         <td><code>tools.log</code>         </td>
         <td><code>&lt;FILEDRIVEHOME&gt;/var/logs</code>         </td>
         <td>Records warnings and errors from internal {{< SecureTransport/componentshortname  >}} components.         </td>
      </tr>
      <tr>
         <td><code>AxwaySecureTransportAdmin_SecureTransport.log</code>         </td>
         <td><code>&lt;FILEDRIVEHOME&gt;/../cygwin/var/log</code>         </td>
         <td>A Windows-specific log file where information about the <code>AxwaySecureTranportAdmin_5.3.0</code> service is recorded.         </td>
      </tr>
      <tr>
         <td><code>AxwaySecureTransportAS2d_SecureTransport.log</code>         </td>
         <td><code>&lt;FILEDRIVEHOME&gt;/../cygwin/var/log</code>         </td>
         <td>A Windows-specific log file where information about the <code>AxwaySecureTranportAS2d</code> service is recorded.         </td>
      </tr>
      <tr>
         <td><code>AxwaySecureTransportFTPd_SecureTransport.log</code>         </td>
         <td><code>&lt;FILEDRIVEHOME&gt;/../cygwin/var/log</code>         </td>
         <td>A Windows-specific log file where information about the <code>AxwaySecureTranportFTPd</code> service is recorded.         </td>
      </tr>
      <tr>
         <td><code>AxwaySecureTransportHTTPd_SecureTransport.log</code>         </td>
         <td><code>&lt;FILEDRIVEHOME&gt;/../cygwin/var/log</code>         </td>
         <td>A Windows-specific log file where information about the <code>AxwaySecureTranportHTTPd</code> service is recorded.         </td>
      </tr>
      <tr>
         <td><code>AxwaySecureTransportSSHd_SecureTransport.log</code>         </td>
         <td><code>&lt;FILEDRIVEHOME&gt;/../cygwin/var/log</code>         </td>
         <td>A Windows-specific log file where information about the <code>AxwaySecureTranportSSHd</code> service is recorded.         </td>
      </tr>
      <tr>
         <td><code>AxwaySecureTransportPeSITd_SecureTransport.log</code>         </td>
         <td><code>&lt;FILEDRIVEHOME&gt;/../cygwin/var/log</code>         </td>
         <td>A Windows-specific log file where information about the <code>AxwaySecureTransportPeSITd</code> service is recorded.         </td>
      </tr>
      <tr>
         <td><code>AxwaySecureTransportTM_SecureTransport.log</code>         </td>
         <td><code>&lt;FILEDRIVEHOME&gt;/../cygwin/var/log</code>         </td>
         <td>A Windows-specific log file where information about the <code>AxwaySecureTransportTM</code> (Transaction Manager) service is recorded.         </td>
      </tr>
      <tr>
         <td><code>AxwaySecureTransportDatabase_SecureTransport.log</code>         </td>
         <td><code>&lt;FILEDRIVEHOME&gt;/../cygwin/var/log</code>         </td>
         <td>A Windows-specific log file where information about the <code>AxwaySecureTransportMYSQL</code> or <code>AxwaySecureTransportMARIADB</code>(embedded database) service is recorded when it is used.         </td>
      </tr>
      <tr>
         <td><code>xferlog</code>         </td>
         <td><code>&lt;FILEDRIVEHOME&gt;/var/logs</code>         </td>
         <td>Records information about FTP(S), HTTP(S), SFTP, AS2, Connect:Direct, Folder Monitor, and PeSIT transfers. For more information, see <a href="../../operations_menu/c_st_filetransfertracking#ServerMenu_1832073003_1043287">Track file transfer activity</a> and <a href="../../c_st_setup/t_st_transferlogconfiguration#SetupMenu_1217491348_1147657">Configure transfer log</a>.         </td>
      </tr>
   </tbody>
</table>
