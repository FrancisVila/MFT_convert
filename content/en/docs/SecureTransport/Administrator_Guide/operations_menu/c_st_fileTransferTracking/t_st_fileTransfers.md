{
    "title": "Manage file transfers",
    "linkTitle": "Manage file transfers",
    "weight": "150"
}You can restart a file transfer or cancel a file transfer.

The following topics provide how-to instructions for restarting and canceling a file transfer:

-   <a href="#Restart" class="MCXref xref">Restart a transfer</a>
-   <a href="#Cancel" class="MCXref xref">Cancel a transfer</a>

**Related topics:**

-   <a href="" class="MCXref xref">Resubmit status</a>
-   <a href="../r_st_transfer_status" class="MCXref xref">Transfer status</a>
-   <a href="../t_st_viewfiletransferinfo" class="MCXref xref">View file transfer information</a>
-   <a href="../r_st_transferlogmaint" class="MCXref xref">Transfer Log Maintenance application</a>

<span id="Restart"></span>

## Restart a transfer

If a file transfer fails permanently, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> displays a **Resubmit** button in the **RESUBMIT** column.

1.  Select **Operations > File Tracking**.  
    The *File Tracking* page is displayed.
2.  Click **Resubmit** to the left of the failed transfer you want to restart.

After you restart a file transfer, the **Resubmit** button no longer displays and a new line is added to the *File Tracking* page showing the progress of the resubmitted transfer.

<span id="Cancel"></span>

## Cancel a transfer

If a server-initiated file transfer fails temporarily and is scheduled for a retry, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> displays a **Cancel** button in the **RESUBMIT** column.

-   To cancel the file transfer retry, click **Cancel**.
