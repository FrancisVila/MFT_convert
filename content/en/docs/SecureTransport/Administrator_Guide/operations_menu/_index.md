{
    "title": "Operations",
    "linkTitle": "Operations",
    "weight": "70"
}Operations is a top-level menu in SecureTransport and SecureTransport Edge.

Use the Operations menu of the Axway SecureTransport Administration Tool to initiate operator-driven actions, planned daily tasks, statistics, monitors, and responses to events.

Administration Tool server runs as an HTTPS server using port 444 by default. The Administration Tool server starts automatically each time a UNIX-based system starts. The installer includes a startup item in the system’s `rc` directory tree. On a Windows system, the server runs as a service.

You can also manually start the Administration Tool server by executing the following commands:

-   For UNIX, go to `<FILEDRIVEHOME>/bin` and run `./start_admin`.
-   For Windows, go to `<FILEDRIVEHOME>\bin\` and run `start_admin.com`.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The Administration Tool server reserves ports 8004 and 8005 to be used by the Java-based component. These ports are used strictly for internal communication within the Administration Tool and cannot be used for other purposes.         </td>
      </tr>
</table>

## Operations menu overview

When you log in to the SecureTransport Administration Tool, the *Operations* tab is displayed. The *Operations* tab contains the following pages:

-   **Server Control** – Used to manage your FTP, HTTP, AS2, SSH, PeSIT, Transaction Manager (TM), and Monitor servers. For details, see [Server control](extended_server_control).
-   **Cluster Management** – Used to view and maintain SecureTransport Servers in cluster. For details, see [Standard Cluster](../c_st_standardclustering) and [Enterprise Cluster](../c_st_largeenterpriseclustering).
-   **Server Usage Monitor** – Used to monitor by user class the FTP, SSH and HTTP, as well as the protocol bandwidth consumed. For details, see [Server usage monitor](c_st_monitorserverusage).
-   **File Tracking** – Displays a log of the status and attributes of each file transfer. Also, used to display detailed information about a transfer and to cancel or resubmit a transfer. SecureTransport Server only. For details, see [Track file transfer activity](c_st_filetransfertracking).
-   **Server Log** – Used to view, search, and filter the logs from the SecureTransport Server. For details, see [Server log](t_st_serverlog).
-   **Audit Log** – Used to view, compare, and export log entries that SecureTransport records when any change is made to the SecureTransport configuration. For details, see [Audit log](t_st_auditlog).
-   **Server Configuration** – Used to view, change, export, and import server configuration settings. For details, see [Server configuration](c_st_serverconfiguration).
-   **Support Tool** – Used to collect information about SecureTransport and its host operating system and save it in a support information file that you can send to Axway Global Support. For details, see [Support tool](c_st_supporttool).
