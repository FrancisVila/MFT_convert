{
    "title": "Configure transfer log",
    "linkTitle": "Configure transfer log",
    "weight": "210"
}The transfer log tracks the file uploads and downloads on the system and records a lot of basic and additional information, such as whether the transfer was initiated by the server or by a user, protocol used and other information.

The tracking information is kept in the database and in a log file named `xferlog`, which is located in the `<FILEDRIVEHOME>/var/logs` directory. For information about the `xferlog` log file, see [General log files](../../c_st_serverlogs/r_st_logfiledetails/c_st_general_log_files). If you have the Enterprise Cluster (EC) option, you can store the transfer log data in a separate external database from the rest of the {{< SecureTransport/componentshortname  >}} data. See [Direct log data to separate Oracle databases](../c_st_database/t_st_separate_databases#top).

Use the *Transfer Logging* page to add and edit logging entries to determine which transfers will be logged. You can also enable this feature for a specific user class.

The following topics provide how-to instructions for managing the transfer log configuration:

-   [Add transfer logging entries](t_st_add_transfer_logging_entries) - Provides how-to instructions for adding transfer logging entries.
-   [Enable or disable transfer logging entries](t_st_enable_disable_transfer_logging_entries) - Provides how-to instructions for enabling or disabling transfer logging entries.
-   [Edit transfer logging entries](t_st_edit_transfer_logging_entries) - Provides how-to instructions for editing transfer logging entries.
-   [Delete transfer logging entries](t_st_delete_transfer_logging_entries) - Provides how-to instructions for deleting transfer logging entries.
