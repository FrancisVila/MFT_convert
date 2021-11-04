{
    "title": "Server log",
    "linkTitle": "Server log",
    "weight": "110"
}Use the *Server Log* page to view the contents of the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> log messages from the following <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> components: the Transaction Manager (TM) and the processes that implement the AS2, FTP, HTTP, SSH (SFTP), and SOCKS5 protocols, the Administration Tool interface (ADMIN), and auditing (AUDIT).

When you open the *Server Log* page, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> automatically loads the server log records for the past hour. This behavior is determined by the `ServerLog.InitialLoading.Enabled.Admin` server configuration option. It is available on <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge and <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server and accepts boolean values. The option is set to `true` by default. To disable the initial auto-loading of log entries on the page, set the option to `false`. When having a large number of logs, you can filter the entries based on one or more criteria to speed up reporting.

By default, the server log entries are stored in the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> database. If you have the Enterprise Cluster (EC) option and are using an Oracle database, you can store the server log data in a separate external database from the rest of the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> data. See <a href="../../c_st_setup/c_st_database/t_st_separate_databases#top" class="MCXref xref">Direct log data to separate Oracle databases</a>.

Each line in the log display include the following information:

-   **TIME** – The date and time the entry was logged. This is link you can use to display more detailed information.
-   **LEVEL** – The severity level of the entry.
-   **COMPONENT** – The name of the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> component that produced the entry.
-   **THREAD** – The ID of the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> execution thread that produced the entry.
-   **MESSAGE** – The primary log information.

On <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server, but not on <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge, the following information is also included.

-   **SESSION ID** – An identifier of the login session associated with the entry. This is a link you can use to copy the session ID into the **Session ID** field in the search criteria.
-   **TRANSFER ID** – An identifier of the file transfer associated with this entry. This is a link you can use to copy the transfer ID into the **Transfer ID** field in the search criteria.

Also, you can export the filtered log entries to a `.csv` file.

The following topics describe viewing, searching, exporting, and managing server log content:

-   <a href="t_st_search_view_server_log_contents" class="MCXref xref">Search and view server log contents</a> - Describes and provides how-to instructions on searching and viewing the server log contents.
-   <a href="t_st_export_results_server_log_search" class="MCXref xref">Export the results of a server log search</a> - Describes and provides how-to instructions on exporting the results of a server log search.
-   <a href="c_st_log_entry_maintenance_application" class="MCXref xref">Log Entry Maintenance application</a> - Describes the Log Entry Maintenance application.
