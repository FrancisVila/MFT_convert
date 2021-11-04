{
    "title": "Manage uploads",
    "linkTitle": "Manage uploads",
    "weight": "80"
}This section provides instructions for monitoring and managing file uploads to ST Web Client.

## Monitor uploads

At the bottom of *Your files* panel, click **Uploads monitor**. The *Uploads monitor* box is displayed:

<img src="/Images/SecureTransport/WC_Uploads_monitor.png" class="maxWidth" alt="Web Client Monitor Uploads sample screen" />

> **Note:**
>
> To have your list of upload files persist across multiple browsers, contact your system administrator to configure the Allow this account to submit transfers using the Transfers RESTful API option for your account.

> **Note:**
>
> To delete entries from the Uploads monitor page, contact your system administrator to configure the Allow this account to submit transfers using the Transfers RESTful API option for this account.

The Uploads monitor pane displays the following information:

-   The current status of the file uploads
-   The progress of each upload
-   The overall progress of all uploads
-   The name, folder to which a file is being uploaded or is already uploaded, size, started, and speed of each upload. In Desktop mode, you can customize a column width to better fit your data. Position the mouse pointer on the column border and drag it to the desired size. Your preference will be saved; the customized column width will be applied automatically every time you open the *Uploads monitor* pane.

## Pause, resume or cancel uploads

You have the option to pause and resume one or more uploads, as well as cancel uploads. You must select the upload before canceling it. For multiple selection,
press **Ctrl** or **Shift** on your keyboard and with your mouse left-click to select multiple files.

To pause an upload:

1.  Select the uploads you want to pause. Use the **Ctrl** key to select multiple uploads.
2.  Click **Pause**.

## Resume uploads

To resume an upload:

1.  Select the uploads that are paused that you want to resume. Use the **Ctrl** key to select multiple uploads.
2.  Click **Resume**.

## Cancel uploads

To cancel an upload:

1.  Select the upload that is running that you want to cancel. Use the **Ctrl** key to select multiple uploads.
2.  Click **Cancel**.

## Remove uploads

To remove an upload:

1.  Select the upload that you want to remove. Use the **Ctrl** key to select multiple uploads.
2.  Click **Remove**.

## Filter uploads by status

You can see the processing status of each uploaded file in the *Status* column of the *Uploads Monitor* pane. The available statuses are: 

-   **Running**
-   **Completed**
-   **Paused**
-   **Canceled**
-   **Failed**
-   **Waiting**

To filter uploads by status, select the desired filter from the **All statuses** drop-down at the top-right of the pane.

## Refresh AR trigger file status

When an <span class="mc-variable my_project_variables.Advanced_Routing variable">Advanced Routing</span> trigger file is retried, it is shown in a Waiting status until all files listed in it are processed. To see if the status of a trigger file has changed:

1.  Select the trigger file.
2.  Click the **Refresh status** button at the top of the *Uploads Monitor* pane.

When all files listed in the trigger file are processed, its status changes from Waiting to Complete.

 

next topic: [Manage Mailbox](../../03-manage_mail)
