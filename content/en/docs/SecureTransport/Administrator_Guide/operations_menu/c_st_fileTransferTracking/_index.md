{
    "title": "Track file transfer activity",
    "linkTitle": "Track file transfer activity",
    "weight": "100"
}Use the *File Tracking* page to view information about both client-initiated and server-initiated file transfers and to cancel or resubmit transfers. The *File Tracking* page is available only on {{< SecureTransport/componentshortname  >}} Server. The log {{< SecureTransport/componentshortname  >}} displays on the *File Tracking* page is the transfer log.

When you open the *File Tracking* page, {{< SecureTransport/componentshortname  >}} automatically loads the transfer log entries for the past hour. This behavior is determined by the `FileTracking.InitialLoading.Enabled.Admin` server configuration option. It accepts boolean values; the default value is `true`. To disable the initial auto-loading of log entries on the page, set the configuration option to `false`.

By default, {{< SecureTransport/componentshortname  >}} stores the transfer log entries in the {{< SecureTransport/componentshortname  >}} database. If you have the Enterprise Cluster (EC) option, you can store the transfer log data in a separate Oracle database away from the rest of the {{< SecureTransport/componentshortname  >}} data. See [Direct log data to separate Oracle databases](../../c_st_setup/c_st_database/t_st_separate_databases#top).

To control which transfers are logged, see [Configure transfer log](../../c_st_setup/t_st_transferlogconfiguration#SetupMenu_1217491348_1147657).

For each transfer listed, the *File Tracking* page displays resubmit status, transfer status, account name, login name, direction of transfer, whether action was taken by the user or server, file name, number of bytes transferred, transfer protocol, start time, and duration.

The **Resubmit** button will be displayed in the *Resubmit Status* column except in the following cases:

-   AdHoc mail transfer
-   AdHoc attachment transfer
-   CIT download
-   Failed CIT upload
-   In-progress transfer
-   Re-trying transfer
-   PeSIT transfer in Paused state
-   Publish To Account Advanced Routing step transfer
-   Deleted file transfer log
-   Temporary fail transfers

In the listed cases, no **Resubmit** button is displayed. However, resubmit is not guaranteed to succeed. It is coupled with the archiving of the transfers.

> **Note:**
>
> Due protocol specific operations, when a user pauses or resumes a client initialed transfer (CIT) two entries are observed on the File Tracking page for the interrupted transfer. The entries have the following characteristics:HTTP CIT: The File Tracking page entry for the portion of the file uploaded before the transfer is paused is marked as failed and a Resubmit button is not displayed. The second entry for the portion of the file uploaded after the transfer is resumed is marked as successful and a Resubmit button is displayed.FTP/SSH CIT: The File Tracking page entry for the portion of the file uploaded before the transfer is paused is marked as successful and a Resubmit button is displayed. The second entry for the portion of the file uploaded after the transfer is resumed is marked as successful and a Resubmit button is displayed.

> **Note:**
>
> For PeSIT transfers initiated by a partner, the LOGIN column is the name of the PeSIT transfer site that represents the partner. For all PeSIT transfers, the FILE column is the name of the transfer profile used. For the location and name of the transferred file, click the icon in the status column and refer to the detailed status. You will be able to see more comprehensive information about the transfer if you are using Axway Sentinel.

> **Note:**
>
> When an Oracle RAC database node fails, the transfers being processed by a SecureTransport server connected to the failed Oracle RAC database node, will remain in process indefinitely.

The following topics provide additional information on viewing and managing file transfer activity:

-   [Resubmit status]() - Describes the resubmit status.
-   [Transfer status](r_st_transfer_status) - Describes the transfer status.
-   [View file transfer information](t_st_viewfiletransferinfo) - Describes viewing and searching file transfer information.
-   [Manage file transfers](t_st_filetransfers) - Describes managing file transfers and provides how-to instructions for restarting and canceling file transfers.
-   [Transfer Log Maintenance application](r_st_transferlogmaint) - Describes the Transfer Log Maintenance application.
