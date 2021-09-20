{
    "title": "General log files",
    "linkTitle": "General log files",
    "weight": "330"
}**xferlog** – This log file contains information about uploads and downloads for all protocols.

The xferlog file records information about all the AS2, FTP(S), HTTP(S), PeSIT, SFTP, Connect:Direct, and Folder Monitor transfers made with SecureTransport Server and Edge. This information is also stored in the database.

Each server entry is composed of a single line of the format shown below. All fields are separated by spaces.

The field separator character in the xferlog file is by default a " " (space). To avoid breaking the external parsers, when the name of a transferred file contains spaces, the separator character can now be made a configurable parameter.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">To configure your own delimiter, add <code>delimiter=&lt;value&gt;</code> in <code>XferLogLayout</code> in all log4j files (<code>ftpd-log4j.xml, as2d-log4j.xml, sshd-log4j.xml, pesitd-log4j.xml, httpd-log4j.xml and tm-log4j.xml</code>).         </td>
      </tr>
</table>

For example:

    XferLogAppender name="XferLogAppender fileName="FILEDRIVEHOME/var/logs/xferlog" append="true">      <XferLogLayout dateFormat="yyyy-MM-dd HH:mm:ss,SSS"/></XferLogAppender>
     
    <XferLogAppender name="XferLogAppender" fileName="FILEDRIVEHOME/var/logs/xferlog" append="true">     <XferLogLayout delimiter=" ; " dateFormat="yyyy-MM-dd HH:mm:ss,SSS"/></XferLogAppender>

    <current_time> <transfer_time> <remote_host> <file_size> <file_name> <transfer_mode> <transfer_security> <direction> <access_mode> <user_name> <server_name> 0 *

The fields are defined in the following:

-   `<current_time>` – The current local time, for example, `Wed Oct 24 10:53:34 2012`. The format is `DDD MMM dd hh:mm:ss YYYY`, where:
    -   `DDD` – Day of the week
    -   `MMM` – Month
    -   `dd` – Day of the month
    -   `hh` – Hour
    -   `mm` – Minutes
    -   `ss` – Seconds
    -   `YYYY` – Year

-   `<transfer_time>` – Total time for the transfer, rounded off to seconds.

-   `<remote_host>` – Remote host name or IP address.  

-   `<file_size>` – Number of bytes transferred.

-   `<file_name>` – (for example: `/home/jdoe/somefile`): For virtual and anonymous users, the path given is relative to their home directory. For real users, it's relative to the filesystem root.  
    

    <table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">When a user logs in/out or performs file transfers behind a proxy or a load balancer, an additional IP address is listed: the originating IP address of the user account. In such case, the Remote Host displays the IP address of the proxy/load balancer followed by the user's original IP address. Note that when the user is not behind a proxy/load balancer, the original IP address is displayed with the Remote Host parameter, with no additional IP address.<br/>         </td>
      </tr>
</table>

-   `<transfer_mode>` – A single character indicating the type of transfer:
    -   `a` – ASCII transfer
    -   `b` – Binary transfer

-   `<transfer_security>` – A single character indicating the level of security:

    -   `s` – Secure (SSL-based)
    -   `n` – Non-secure

      
    

    <table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">If you use a File Download or File Upload agent (such as the streaming agents) to handle the file transfer, the path will be preceded by <code>STOR:</code> (for uploads) or <code>RETR:</code> (for downloads).         </td>
      </tr>
</table>

-   `<transfer_status>` – A single character indicating the upload or download status:

    -   Uploads – `i` for OK, `j` for error, and `k` for aborted
    -   Downloads – `o` for OK, `p` for error, and `q` for aborted

      
    

    <table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">In the 2.x versions of <span>SecureTransport</span> (and the 2.x and 3.x versions of <span>SecureTransport</span> for Windows), the value of this field is always <code>_</code> regardless of whether security was used.         </td>
      </tr>
</table>

-   `<access_mode>` – A single character indicating the type of user access:
    -   `a` - Anonymous
    -   `r` – Real or virtual user

-   `<user_name>` – E-mail address, as given at the password prompt, for anonymous users (for example: `jdoe@foo.com`); username for real or virtual users (for example: `jdoe`).

-   `<server_name>` – Type of server used to make the transfer (transport protocol):
    -   `ad-hoc`
    -   `as2`
    -   `c:d` (Connect:Direct)
    -   `folder` (Folder Monitor)
    -   `ftp`
    -   `http`
    -   `pesit`
    -   `ssh`

-   A zero (`0`)

-   An asterisk (`*`)

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Under HTTP/S and SSH , user aborts are treated as errors. The reason is that for FTP, the abort condition is indicated by an explicitly received ABOR command. Any other data socket reset is considered a failure. Since SSH and HTTP don't have a control connection, they resort to interpreting a socket reset as a failure. There isn't any trace of an abort being present for SSH and HTTP protocol daemons. This also includes the guaranteed delivery extension for HTTP. Therefore, the client side aborts are displayed in the <code>xferlog</code> (and FileTracking ) as inbound and outbound errors rather than inbound and outbound aborts. For SSH uploads there is an additional peculiarity: With a native SFTP Linux client, unless a kill ABRT of the child SSH process is completed, a transfer interrupt on the client side with Ctrl +C would cause <code>SSH_FXP_CLOSE</code> to be sent to <span>SecureTransport</span>, indicating FULL "successful" transfer. In this case, an "interrupted " SSH client transfer will be shown in FileTracking and the <code>xferlog</code> as successful.         </td>
      </tr>
</table>

The following is an example of a typical log entry:

    Wed Jan 11 10:55:13 2006 3 10.191.2.33 5873 /drives/c/home/Virtual/vuser/avatar.jpg b s i r vuser http 0 *

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The zero and asterisk are inserted as authentication method and authenticated user id respectively for compatibility with the <code>wu-ftp</code> log format.         </td>
      </tr>
</table>

**tools.log** – This log4j-format log file records warnings and error from internal SecureTransport components. The format and content of this file is controlled by the `<FILEDRIVEHOME>/conf/tools-log4j.xml` file.

For example, importing accounts using command-line tool might produce the following message:

    2010-11-16 00:56:14,505 PST WARN [main] com.tumbleweed.st.server.appframework.sql.SessionFactoryManagerImpl - Component type '' is unknown. Using TOOLS configuration.

**Related topics:**

-   [Log4j files](../r_st_log4j_files)
-   [Database log files](../c_st_database_log_files)
-   [FTPD log file](../c_st_ftpd_log_file)
-   [Admin log file](../c_st_admin_log_file)
-   [Modify the log4j files](../t_st_change_log4j_files)
-   [Redirect log4j output from the database](../t_st_redirect_log4j_output_from_database)
-   [Control log fallback from database to file](../t_st_control_log_fallback_from_database_to_file)
-   [Server log rotation and monitor scheduling](../t_st_server_log_rotation_scheduling)
