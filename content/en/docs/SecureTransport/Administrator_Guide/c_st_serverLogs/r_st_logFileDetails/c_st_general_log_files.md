{
    "title": "General log files",
    "linkTitle": "General log files",
    "weight": "320"
}**xferlog** – This log file contains information about uploads and downloads for all protocols.

The xferlog file records information about all the AS2, FTP(S), HTTP(S), PeSIT, SFTP, Connect:Direct, and Folder Monitor transfers made with {{< SecureTransport/componentshortname  >}} Server and Edge. This information is also stored in the database.

Each server entry is composed of a single line of the format shown below. All fields are separated by spaces.

The field separator character in the xferlog file is by default a " " (space). To avoid breaking the external parsers, when the name of a transferred file contains spaces, the separator character can now be made a configurable parameter.

> **Note:**
>
> To configure your own delimiter, add delimiter=&lt;value> in XferLogLayout in all log4j files (ftpd-log4j.xml, as2d-log4j.xml, sshd-log4j.xml, pesitd-log4j.xml, httpd-log4j.xml and tm-log4j.xml).

For example:



    XferLogAppender name="XferLogAppender fileName="FILEDRIVEHOME/var/logs/xferlog" append="true">
          <XferLogLayout dateFormat="yyyy-MM-dd HH:mm:ss,SSS"/>
    </XferLogAppender>

     

    <XferLogAppender name="XferLogAppender" fileName="FILEDRIVEHOME/var/logs/xferlog" append="true">
         <XferLogLayout delimiter=" ; " dateFormat="yyyy-MM-dd HH:mm:ss,SSS"/>
    </XferLogAppender>


    <current_time> <tr> <remote_host> <file_size> <file_name> <tr> <tr> <direction> <access_mode> <user_name> <server_name> 0 *

The fields are defined in the following:

-   `<current_time>` – The current local time, for example, `Wed Oct 24 10:53:34 2012`. The format is `DDD MMM dd hh:mm:ss YYYY`, where:
    -   `DDD` – Day of the week
    -   `MMM` – Month
    -   `dd` – Day of the month
    -   `hh` – Hour
    -   `mm` – Minutes
    -   `ss` – Seconds
    -   `YYYY` – Year

-   `<tr>` – Total time for the transfer, rounded off to seconds.

-   `<remote_host>` – Remote host name or IP address.  

-   `<file_size>` – Number of bytes transferred.

-   `<file_name>` – (for example: `/home/jdoe/somefile`): For virtual and anonymous users, the path given is relative to their home directory. For real users, it's relative to the filesystem root.  

    > **Note:**
    >
    > If you use a File Download or File Upload agent (such as the streaming agents) to handle the file transfer, the path will be preceded by STOR: (for uploads) or RETR: (for downloads).

-   `<tr>` – A single character indicating the type of transfer:
    -   `a` – ASCII transfer
    -   `b` – Binary transfer

-   `<tr>` – A single character indicating the level of security:

    -   `s` – Secure (SSL-based)
    -   `n` – Non-secure

      

    > **Note:**
    >
    > In the 2.x versions of SecureTransport (and the 2.x and 3.x versions of SecureTransport for Windows), the value of this field is always \_ regardless of whether security was used.

-   `<tr>` – A single character indicating the upload or download status:

    -   Uploads – `i` for OK, `j` for error, and `k` for aborted
    -   Downloads – `o` for OK, `p` for error, and `q` for aborted

      

    > **Note:**
    >
    > Under HTTP/S and SSH , user aborts are treated as errors. The reason is that for FTP, the abort condition is indicated by an explicitly received ABOR command. Any other data socket reset is considered a failure. Since SSH and HTTP don't have a control connection, they resort to interpreting a socket reset as a failure. There isn't any trace of an abort being present for SSH and HTTP protocol daemons. This also includes the guaranteed delivery extension for HTTP. Therefore, the client side aborts are displayed in the xferlog (and FileTracking ) as inbound and outbound errors rather than inbound and outbound aborts. For SSH uploads there is an additional peculiarity: With a native SFTP Linux client, unless a kill ABRT of the child SSH process is completed, a transfer interrupt on the client side with Ctrl +C would cause SSH\_FXP\_CLOSE to be sent to SecureTransport, indicating FULL "successful" transfer. In this case, an "interrupted " SSH client transfer will be shown in FileTracking and the xferlog as successful.

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

> **Note:**
>
> The zero and asterisk are inserted as authentication method and authenticated user id respectively for compatibility with the wu-ftp log format.

The following is an example of a typical log entry:


    Wed Jan 11 10:55:13 2006 3 10.191.2.33 5873 /drives/c/home/Virtual/vuser/avatar.jpg b s i r vuser http 0 *

> **Note:**
>
> On Windows, it is not possible to modify existing cron jobs or to use cron to run any jobs other than those SecureTransport jobs documented in these topics. Instead, use the Windows Task Scheduler.

**tools.log** – This log4j-format log file records warnings and error from internal {{< SecureTransport/componentshortname  >}} components. The format and content of this file is controlled by the `<FILEDRIVEHOME>/conf/tools-log4j.xml` file.

For example, importing accounts using command-line tool might produce the following message:


    2010-11-16 00:56:14,505 PST WARN [main] com.tumbleweed.st.server.appframework.sql.SessionFactoryManagerImpl - Component type '' is unknown. Using TOOLS configuration.

**Related topics:**

-   <a href="../r_st_log4j_files" class="MCXref xref">Log4j files</a>
-   <a href="../c_st_database_log_files" class="MCXref xref">Database log files</a>
-   <a href="../c_st_ftpd_log_file" class="MCXref xref">FTPD log file</a>
-   <a href="../c_st_admin_log_file" class="MCXref xref">Admin log file</a>
-   <a href="../t_st_change_log4j_files" class="MCXref xref">Modify the log4j files</a>
-   <a href="../t_st_redirect_log4j_output_from_database" class="MCXref xref">Redirect log4j output from the database</a>
-   <a href="../t_st_control_log_fallback_from_database_to_file" class="MCXref xref">Control log fallback from database to file</a>
-   <a href="../t_st_server_log_rotation_scheduling" class="MCXref xref">Server log rotation and monitor scheduling</a>
