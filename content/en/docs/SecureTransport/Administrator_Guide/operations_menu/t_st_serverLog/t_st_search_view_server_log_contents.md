{
    "title": "Search and view server log contents",
    "linkTitle": "Search and view server log contents",
    "weight": "140"
}Use the following procedure to search and view server log content.

1.  Select **Operations > Server Log**.  
    The *Server Log* page is displayed.
2.  In the *Search* pane, specify search criteria.
    1.  In the **Time Interval** drop-down list, select the time frame of the log entries to display. Choose from the following:
        -   Last Hour (default)
        -   Last 4 Hours
        -   Last 8 Hours
        -   Last 12 Hours
        -   Last 24 Hours
        -   Last 48 Hours
        -   Last 1 Week
        -   Last 2 Weeks
        -   Specific Date/Time Range – Displays field that you use to specify the range
    2.  (Optional) In the **Account or Login** field, type the name of the account or login associated with the log entries to display.
    3.  (Optional) In the **Thread** field, type the name of the thread associated with the log entries for to display.
    4.  (Optional) Under *Level*, select the levels of the log entries to display. Choose from the following:
        -   TRACE
        -   DEBUG
        -   INFO
        -   NOTICE
        -   WARN
        -   ERROR
        -   FATAL
    5.  (Optional) Under *Component*, Select the SecureTransport Server component associated with the log entries to display. Choose from the following:
        -   TM
        -   AS2D
        -   SSHD
        -   Socks
        -   ADMIN
        -   AUDIT
        -   FTPD
        -   HTTPD
        -   PESITD
    6.  (Optional) In a clustered deployment, select the **Cluster Node** associated with the log entries to display. The nodes shown are those listed on the *Cluster Management* page. To select more than one node, click **Select Multiple** and selected the nodes from the list.
3.  (Optional) Click **Advanced Search** to display more fields and specify the following:
    1.  (Optional) Using the **ST Activity** checkboxes, specify whether to display inbound or outbound SecureTransport activity.
    2.  (Optional) In the **Message** field, type a string contained in the messages to display.
    3.  (Optional) Use a link in the **Session ID** column to copy a session identifier into the **Session ID** field.
    4.  (Optional) Use a link in the **Transfer ID** column to copy a session identifier into the **Transfer ID** field.
    5.  (Optional) In the **Client** IP address field, type a string contained in the host name or IP address of the client associated with the transfer when the message to display was generated.
    6.  (Optional) In the **Edge** IP address field, type a string contained in the host name or IP address of the SecureTransport Edge associated with the transfer when the messages to display was generated.
    7.  (Optional) In the **Server** IP address field, type a string contained in the host name or IP address of the SecureTransport Server associated with the transfer when the messages to display was generated.
4.  Click **GO**.  
    The filtered log is displayed.  
    Each log entry includes a time stamp, the log level, the names of the component and thread that logged the entry, the node IP address for a node in a cluster, the log message, and session and transfer identifiers.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">In some cases, the type of a new application reported in the log message is a different form of the type you selected when you created the application.         </td>
      </tr>
</table>

**Related topics:**

-   [Export the results of a server log search](../t_st_export_results_server_log_search)
-   [Log Entry Maintenance application](../c_st_log_entry_maintenance_application)
