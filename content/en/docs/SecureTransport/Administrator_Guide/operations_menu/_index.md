{
    "title": "Operations",
    "linkTitle": "Operations",
    "weight": "60"
}Operations is a top-level menu in {{< SecureTransport/componentshortname  >}} and {{< SecureTransport/securetransportedgename  >}}.

Use the Operations menu of the {{< SecureTransport/componentlongname  >}} Administration Tool to initiate operator-driven actions, planned daily tasks, statistics, monitors, and responses to events.

Administration Tool server runs as an HTTPS server using port 444 by default. The Administration Tool server starts automatically each time a UNIX-based system starts. The installer includes a startup item in the system’s `rc` directory tree. On a Windows system, the server runs as a service.

You can also manually start the Administration Tool server by executing the following commands:

-   For UNIX, go to `<FILEDRIVEHOME>/bin` and run `./start_admin`.
-   For Windows, go to `<FILEDRIVEHOME>\bin\` and run `start_admin.com`.

> **Note:**
>
> The Administration Tool server reserves ports 8004 and 8005 to be used by the Java-based component. These ports are used strictly for internal communication within the Administration Tool and cannot be used for other purposes.

## Operations menu overview

When you log in to the {{< SecureTransport/componentshortname  >}} Administration Tool, the *Operations* tab is displayed. The *Operations* tab contains the following pages:

-   **Server Control** – Used to manage your FTP, HTTP, AS2, SSH, PeSIT, Transaction Manager (TM), and Monitor servers. For details, see <a href="extended_server_control" class="MCXref xref">Server control</a>.
-   **Cluster Management** – Used to view and maintain {{< SecureTransport/componentshortname >}} Servers in cluster. For details, see <a href="../c_st_standardclustering#Standard_Clustering_3967700027_1013811" class="MCXref xref">Standard Cluster</a> and <a href="../c_st_largeenterpriseclustering#Large_Enterprise_Clustering_2746683174_1079954" class="MCXref xref">Enterprise Cluster</a>.
-   **Server Usage Monitor** – Used to monitor by user class the FTP, SSH and HTTP, as well as the protocol bandwidth consumed. For details, see <a href="c_st_monitorserverusage#ServerMenu_1832073003_1119819" class="MCXref xref">Server usage monitor</a>.
-   **File Tracking** – Displays a log of the status and attributes of each file transfer. Also, used to display detailed information about a transfer and to cancel or resubmit a transfer. {{< SecureTransport/componentshortname >}} Server only. For details, see <a href="c_st_filetransfertracking#ServerMenu_1832073003_1043287" class="MCXref xref">Track file transfer activity</a>.
-   **Server Log** – Used to view, search, and filter the logs from the {{< SecureTransport/componentshortname >}} Server. For details, see <a href="t_st_serverlog#ServerMenu_1832073003_1052443" class="MCXref xref">Server log</a>.
-   **Audit Log** – Used to view, compare, and export log entries that SecureTransport records when any change is made to the SecureTransport configuration. For details, see <a href="t_st_auditlog#top" class="MCXref xref">Audit log</a>.
-   **Server Configuration** – Used to view, change, export, and import server configuration settings. For details, see <a href="c_st_serverconfiguration#ServerMenu_1832073003_1107076" class="MCXref xref">Server configuration</a>.
-   **Support Tool** – Used to collect information about {{< SecureTransport/componentshortname >}} and its host operating system and save it in a support information file that you can send to {{< SecureTransport/companyname >}} Global Support. For details, see <a href="c_st_supporttool#top" class="MCXref xref">Support tool</a>.
