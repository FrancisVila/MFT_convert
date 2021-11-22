{
    "title": "Resubmit status",
    "linkTitle": "Resubmit status",
    "weight": "120"
}The resubmit status displays one of three options:

-   A **Resubmit** button for permanently failed transfers and for successful incoming transfers other than AdHoc mail, AdHoc attachment, CIT download, failed CIT upload, in-progress, retried, PeSIT in Paused state, Publish To Account Advanced Routing step, and deleted file log transfers. You can use the **Resubmit** button to try failed transfer again or to resubmit successful incoming transfers other than for those listed.
-   A **Cancel** button you can use to stop the transfer retry attempt.
-   No button if the transfer is in-progress or if it is an AdHoc mail, AdHoc attachment, CIT download, failed CIT upload, in-progress, retried, PeSIT in Paused state, Publish To Account Advanced Routing step, temporary failed transfers and deleted file log transfer.

When retrying a transfer, {{< SecureTransport/componentshortname  >}} uses either an archived copy created when the server first received the file or the original file if it is available. If there is no archive for the transfer and the original file is not available resubmit attempt fails.

> **Note:**
>
> Archived files are removed from the server periodically. You can control these settings using the Archive Maintenance application and global File Archiving configuration. For more information on the Archive Maintenance application, see Archive Maintenance application. For more information on the global File Archiving configuration, refer to File archiving global configuration.

If the transfer failed, a **Cancel** button is displayed only next to the most recent failure, as indicated by the timestamp associated with the attempt. The **Cancel** button is displayed when the transfer has a temporary failure, while the **Resubmit** button is displayed when the transfer has a permanent failure or when an incoming transfer is successful other than AdHoc mail, AdHoc attachment, CIT download, failed CIT upload, in-progress, retried, PeSIT in Paused state, Publish To Account Advanced Routing step, and deleted file log transfers. Additionally, the **Resubmit** button is not displayed for deleted transfers.

> **Note:**
>
> SecureTransport always checks if an archive copy of the file is available before checking for the original file. The modification date and time of the original file is kept in the transfer history, so if a file with the same name as the original file exists in the original location. The transfer is not resubmitted if the modification date and time do not match.

Resubmit only restarts the transfer that is resubmitted. If there is not an active subscription for the transfer, at the moment of resubmission, the subscription will be reactivated. If only a post-transmission action fails, the post-transmission action is restarted when you resubmit the transfer.

> **Note:**
>
> There are limitations on Cancel. When using Advanced Routing feature the administrator is not able to control automatic retries using the Cancel button.

**Related topics:**

-   <a href="../r_st_transfer_status" class="MCXref xref">Transfer status</a>
-   <a href="../t_st_viewfiletransferinfo" class="MCXref xref">View file transfer information</a>
-   <a href="../t_st_filetransfers" class="MCXref xref">Manage file transfers</a>
-   <a href="../r_st_transferlogmaint" class="MCXref xref">Transfer Log Maintenance application</a>
