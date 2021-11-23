{
    "title": "Manage file transfers",
    "linkTitle": "Manage file transfers",
    "weight": "150"
}You can restart a file transfer or cancel a file transfer.

The following topics provide how-to instructions for restarting and canceling a file transfer:

-   [Restart a transfer](#Restart)
-   [Cancel a transfer](#Cancel)

**Related topics:**

-   [Resubmit status]()
-   [Transfer status](../r_st_transfer_status)
-   [View file transfer information](../t_st_viewfiletransferinfo)
-   [Transfer Log Maintenance application](../r_st_transferlogmaint)

<span id="Restart"></span>

## Restart a transfer

If a file transfer fails permanently, {{< SecureTransport/componentshortname  >}} displays a **Resubmit** button in the **RESUBMIT** column.

1.  Select **Operations > File Tracking**.  
    The *File Tracking* page is displayed.
2.  Click **Resubmit** to the left of the failed transfer you want to restart.

After you restart a file transfer, the **Resubmit** button no longer displays and a new line is added to the *File Tracking* page showing the progress of the resubmitted transfer.

<span id="Cancel"></span>

## Cancel a transfer

If a server-initiated file transfer fails temporarily and is scheduled for a retry, {{< SecureTransport/componentshortname  >}} displays a **Cancel** button in the **RESUBMIT** column.

-   To cancel the file transfer retry, click **Cancel**.
