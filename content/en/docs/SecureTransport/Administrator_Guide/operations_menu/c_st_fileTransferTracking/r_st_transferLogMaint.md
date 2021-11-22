{
    "title": "Transfer Log Maintenance application",
    "linkTitle": "Transfer Log Maintenance application",
    "weight": "160"
}The built-in {{< SecureTransport/componentshortname  >}} application type, Transfer Log Maintenance, maintains the {{< SecureTransport/componentshortname  >}} transfer log by exporting and cleaning up transfer log entries on a regular basis, following a schedule you define.

A Transfer Log Maintenance type application has the following features:

-   User-definable schedule for transfer log daily backup and export or both. For more information, see <a href="#ConfigureMaintSchedule" class="MCXref xref">Configure a schedule for a maintenance application</a>.
-   Application-specific parameters regarding the processing of transfer log entries include:
    -   Expiration period for log entries until export and deletion or both
    -   A condition to export the entries before deleting them or not
    -   Delete exported files
    -   Number of records per file
-   Support for a dedicated export folder. By default the exported entries are stored in the following location:  
    `<FILEDRIVEHOME>/var/db/hist/transfer-log`

For more information, see <a href="../../../applications/applicationstransferlogmaintenance#top" class="MCXref xref">Transfer Log Maintenance application</a>.

**Related topics:**

-   <a href="" class="MCXref xref">Resubmit status</a>
-   <a href="../r_st_transfer_status" class="MCXref xref">Transfer status</a>
-   <a href="../t_st_viewfiletransferinfo" class="MCXref xref">View file transfer information</a>
-   <a href="../t_st_filetransfers" class="MCXref xref">Manage file transfers</a>
