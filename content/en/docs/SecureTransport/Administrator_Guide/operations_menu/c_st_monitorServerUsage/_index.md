{
    "title": "Server Usage Monitor",
    "linkTitle": "Server Usage Monitor",
    "weight": "100"
}**Operations &gt; Server Usage Monitor**

The *Server Usage Monitor* page presents info with current session and bandwidth usage, as follows:

-   Server sessions by User Class - lists server sessions and bandwidth as consumed by User classes
-   Bandwidth usage by login name - lists server bandwidth consumed by individual user accounts
-   Server sessions - lists each connection session per user account

You also have the option to [Auto refresh Server Usage Monitor info](#autorefresh_serverusagemonitor), as well as perform a manual refresh of the page.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The <em>Server Usage Monitor</em> page shows FTP, HTTP(S) and SSH information only. Also, you can select what info to be monitored. For more information, see <a href="../../c_st_setup/c_st_miscellaneousconfiguration/t_st_miscellaneousoptions" xrefformat="{paratext}">Set usage monitor options</a>.         </td>
      </tr>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">When in <i>cluster setup</i>, the information presented here includes all current sessions across all nodes.         </td>
      </tr>
</table>

## Server sessions by User Class

This table allows you to monitor server sessions and bandwidth as consumed by User classes. The information is distributed into columns as follows:

-   **User class**
-   **Logged in GLOBAL (HTTP/FTP/SSH)** – the number of protocol (HTTP(S)/FTP/SSH) sessions that users in the respective user class are currently connected to globally.
-   **Logged in LOCAL (HTTP/FTP/SSH)** – the number of protocol (HTTP(S)/FTP/SSH) sessions that users in the respective user class are currently connected to locally.
-   **Max allowed sessions** – the upper limitation for open concurrent sessions per user class.
-   **Bandwidth (Inbound/Outbound)** – the currently used bandwidth by the respective user class.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">For more information on the format presented in the different columns of the <i>Server sessions by User Class</i> table, see the subtopic that follows: <i>Bandwidth usage by login name</i>.         </td>
      </tr>
</table>

## <span id="Bandwidt"></span>Bandwidth usage by login name

This table allows you to monitor server bandwidth consumed by individual user accounts that are currently logged in. The information is distributed into columns as follows:

-   **Login name** – the user account login name.
-   **Logged In (HTTP/FTP/SSH)** – the number of protocol (HTTP(S)/FTP/SSH) sessions the user is currently connected to. The format used is \[total sessions (HTTP/FTP/SSH)\].  
    For example, when the respective value for a selected user is (3 (1/1/1), this means that the user currently has 3 open sessions, 1 HTTP(S), 1 FTP and 1 SSH.
-   **Max allowed (Inbound/Outbound)** – the maximum allowed traffic speed per the respective user. The format used is \[Total allowed bandwidth (Max allowed Inbound bandwidth / Max allowed Outbound bandwidth\].  
    For example, when the respective value for a selected user is (768.0 (512.0 / 256.0), this means that the user's total traffic (both Inbound and Outbound) is limited to 768 kb/sec, of which 512.0 is the maximum allowed speed for inbound, and 256 is the maximum allowed speed for outbound traffic.
-   **Bandwidth (Inbound/Outbound)** – the currently used bandwidth by the respective user. The format used is \[Total allowed bandwidth (Max allowed Inbound bandwidth / Max allowed Outbound bandwidth\].

## Server sessions

This table lists each FTP, SSH and HTTP(S) connection with the option to kill each one. The table presents the following options:

-   **Action** – use the **Kill** button for each connection to terminate the respective session.
-   **Host** – the IP address of the host location from which the user has connected.
-   **User** – the username of the respective user account.
-   **Node** – the IP address to which the user is connected.
-   **Class** – the user class the respective user belongs to.
-   **On Since** – the Date and time the respective connectivity session was established.
-   **PID** – the internal process ID of an FTP, SSH or HTTP(S) session within the server process.
-   **CMD** – the transfer command.
-   **Server Name** – the name of the server.

Select the **Include local daemon sessions** check-box to include the local sessions in the display results.

## <span id="Autorefresh_ServerUsageMonitor"></span>Auto refresh Server Usage Monitor info

Use the following procedure to enable automatic snapshot updates.

1.  On the top right corner of *Server Usage Monitor* page, type the number of seconds between updates in the **Auto refresh every \_\_\_ seconds** box.
2.  Click **Start Auto Refresh**. The button label changes to **Stop Auto Refresh** so you can later click it again to disable the automatic snapshot update.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Wile in Auto refresh mode, do not use <strong>F5</strong> on your keyboard or the <b>Refresh</b> button on the screen to refresh the browser window.         </td>
      </tr>
</table>

## Disable automatic snapshot updates

To disable automatic snapshot updates, go to the *Server Usage Monitor* page and click **Stop Auto Refresh**. The button changes back its label to **Start Auto Refresh**.