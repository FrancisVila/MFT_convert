{
    "title": "Transfer Log Maintenance application",
    "linkTitle": "Transfer Log Maintenance application",
    "weight": "160"
}The built-in {{< SecureTransport/componentshortname  >}} application type, Transfer Log Maintenance, maintains the {{< SecureTransport/componentshortname  >}} transfer log by exporting and cleaning up transfer log entries on a regular basis, following a schedule you define.

A Transfer Log Maintenance type application has the following features:

-   User-definable schedule for transfer log daily backup and export or both. For more information, see [Configure a schedule for a maintenance application](#ConfigureMaintSchedule).
-   Application-specific parameters regarding the processing of transfer log entries include:
    -   Expiration period for log entries until export and deletion or both
    -   A condition to export the entries before deleting them or not
    -   Delete exported files
    -   Number of records per file
-   Support for a dedicated export folder. By default the exported entries are stored in the following location:  
    `<FILEDRIVEHOME>/var/db/hist/transfer-log`

For more information, see [Transfer Log Maintenance application](../../../applications/applicationstransferlogmaintenance#top).

**Related topics:**

-   [Resubmit status]()
-   [Transfer status](../r_st_transfer_status)
-   [View file transfer information](../t_st_viewfiletransferinfo)
-   [Manage file transfers](../t_st_filetransfers)
