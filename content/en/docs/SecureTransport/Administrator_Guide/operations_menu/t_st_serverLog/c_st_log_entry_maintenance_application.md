{
    "title": "Log Entry Maintenance application",
    "linkTitle": "Log Entry Maintenance application",
    "weight": "150"
}The built-in <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> application type, Log Entry Maintenance, performs the exclusive function of rotating server log files.

The main characteristic features of the Log Entry Maintenance application type are:

-   User-definable schedule for transfer log daily backup or export and both. For more information, see <a href="../../../accounts/c_st_subscriptions/t_st_subscriptions#Schedule" class="MCXref xref">Scheduled downloads and tasks</a>.
-   Application-specific parameters regarding the processing of server log entries include:
    -   Expiration period for log entries until export or deletion and both.
    -   Number of records per file.
-   Support for a dedicated export folder. By default the exported entries are stored in the following location:  
    `<FILEDRIVEHOME>/var/db/hist/log-entry`

For more information, see <a href="../../../applications/applicationslogentrymaintenance#top" class="MCXref xref">Log Entry Maintenance application</a>.

**Related topics:**

-   <a href="../t_st_search_view_server_log_contents" class="MCXref xref">Search and view server log contents</a>
-   <a href="../t_st_export_results_server_log_search" class="MCXref xref">Export the results of a server log search</a>
