{
    "title": "Log Entry Maintenance application",
    "linkTitle": "Log Entry Maintenance application",
    "weight": "150"
}The built-in {{< SecureTransport/componentshortname  >}} application type, Log Entry Maintenance, performs the exclusive function of rotating server log files.

The main characteristic features of the Log Entry Maintenance application type are:

-   User-definable schedule for transfer log daily backup or export and both. For more information, see [Scheduled downloads and tasks](../../../accounts/c_st_subscriptions/t_st_subscriptions#Schedule).
-   Application-specific parameters regarding the processing of server log entries include:
    -   Expiration period for log entries until export or deletion and both.
    -   Number of records per file.
-   Support for a dedicated export folder. By default the exported entries are stored in the following location:  
    `<FILEDRIVEHOME>/var/db/hist/log-entry`

For more information, see [Log Entry Maintenance application](../../../applications/applicationslogentrymaintenance#top).

**Related topics:**

-   [Search and view server log contents](../t_st_search_view_server_log_contents)
-   [Export the results of a server log search](../t_st_export_results_server_log_search)
