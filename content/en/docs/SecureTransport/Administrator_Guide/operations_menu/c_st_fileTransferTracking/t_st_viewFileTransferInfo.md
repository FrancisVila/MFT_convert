{
    "title": "View file transfer information",
    "linkTitle": "View file transfer information",
    "weight": "140"
}Use the *File Tracking* page to search for file tracking information and view information about the file transfers.

-   <a href="#View" class="MCXref xref">View and export log statistics about transferred files</a>
-   <a href="#Search" class="MCXref xref">Search file tracking information</a>
-   <a href="#View2" class="MCXref xref">View MDN receipt information about a transfer</a>
-   <a href="#View3" class="MCXref xref">View detailed information about a file transfer</a>
-   <a href="#View4" class="MCXref xref">View transfer history of a file</a>
-   <a href="#View5" class="MCXref xref">View detailed information about an AR execution</a>

<span id="View"></span>

## View and export log statistics about transferred files

Use the following procedure to view and export file transfer log statistics.

1.  Select **Operations > File Tracking**.  
    The *File Tracking* page is displayed.
2.  Click **Export Log** to export the displayed file tracking data to a `.csv` file. You cannot export all the records from the database at one time.
3.  Choose whether to save or open the file
4.  Click **OK**.

<span id="Search"></span>

## Search file tracking information

Use the following procedure to search file tracking information.

1.  Select **Operations > File Tracking**.
2.  On the *File Tracking* page, specify the search criteria.  
    1.  In the *Search for transfers* pane, specify whether you want to search based on time the transfer started or completed and the time frame in which to search.
    2.  (Optional) Specify the account or login associated with the transfer for which you are searching.
    3.  (Optional) Specify whether to search for inbound or outbound transfers.
    4.  (Optional) Specify whether you want to include successful transfers, transfers currently in progress, paused transfers, failed transfers, or failed subtransmissions. You can specify more than one.
3.  (Optional) Show the Advanced Search fields and specify additional search criteria.  
    1.  Specify the file name, class, site associated or Core ID with the transfer for which you are searching.
    2.  Specify transfers initiated by the server or the user.
    3.  Specify the protocols used for the transfers. You can use Control+click and Shift+click to select more than one.
    4.  Specify whether the transfer was secure or non-secure.
    5.  Specify whether the transfer was resubmitted or not resubmitted.
    6.  Specify the application associated with the transfer. You can use **Control + click** and **Shift + click** to select more than one.

> **Note:**
>
> Resubmitted files can be:- the transfer that is resubmitted with the "Resubmit“ button or the REST API resourceNot Resubmitted files can be:- the transfer that is NOT resubmitted with the "Resubmit“ button or the REST API resource;- the transfer that is started from the Resubmit button or the REST API;- the transfer that is without the Resubmit button.

4\. When ready, click **Search**.

<span id="View2"></span>

## View MDN receipt information about a transfer

Use the following procedure to view MDN receipt information.

1.  Select **Operations > File Tracking**.  
    The *File Tracking* page is displayed.
2.  Click the MDN receipt icon for a specific transfer. An MDN receipt icon is displayed only when a receipt for the transfer is available in the system and the transfer was successful. To enable MDN receipts, see <a href="../../../c_st_setup/c_st_certificates/r_st_certificatestogenerate#SetupMenu_1217491348_1023232" class="MCXref xref">Certificates to generate during initial setup</a>.  
    The *MDN Receipt* dialog box is displayed. You can either view the MDN receipt or click **Verify** to view the MDN signature and file integrity check results. Clicking **Close** returns you to the *File Tracking* page.

<span id="View3"></span>

## View detailed information about a file transfer

Use the following procedure to view detailed status information.

1.  Select **Operations > File Tracking**.  
    The *File Tracking* page is displayed.
2.  Click the status icon or the file name for a specific transfer.  
    The *Status Detail* dialog box is displayed.  
    <img src="/Images/SecureTransport/Operations_FileTracking_StatusDetail.png" class="mediumWidth" alt="Status Detail" />

The *Status Detail* dialog box shows the following information:

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Name         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Status         </td>
         <td>Displays the transfer status: Processed, In Progress, Failed, Aborted, or Failed Subtransmission.         </td>
      </tr>
      <tr>
         <td>Time         </td>
         <td>Displays the date and time the transfer was started and its duration in milliseconds.         </td>
      </tr>
      <tr>
         <td>User         </td>
         <td>Displays information about the account that performed the transfer: account name, login name, class type and user type.         </td>
      </tr>
      <tr>
         <td>Application         </td>
         <td>Displays the application instance name.         </td>
      </tr>
      <tr>
         <td>Transfer         </td>
         <td><p>Displays the transfer type, transfer site name, file name and size, transfer protocol, server name, transfer mode, remote host name, remote folder name, account folder name, real file location, success or failure details, and protocol messages. At the bottom, there are three ID links:</p>
<ul>
<li><span id="TransferID"></span>Transfer ID - a unique identifier of a transfer in {{< SecureTransport/componentshortname  >}}. It is used to track what happened to a file during a single transfer (e.g upload, download, push, pull). When you click on the TransferID value, {{< SecureTransport/componentshortname  >}} opens the <em>Server Log</em> page with the value pre-filled as a search criterion.</li>
<li><span id="SessionID"></span>Session ID - a session identifier in SecureTransport. It is used to track the file(s) during one or multiple transfers that happened in the same session. When you click on the SessionID value, {{< SecureTransport/componentshortname  >}} opens the <em>Server Log</em> page with the value pre-filled as a search criterion.</li>
<li><span id="CoreID"></span>Core ID - a unique file identifier in {{< SecureTransport/componentshortname  >}}. It is generated the first time the file arrives in {{< SecureTransport/componentshortname  >}}, and is stable throughout the lifespan of the file, even if its name changes. Core ID is used to track the file across different transfers and sessions. When you click on the Core ID value, {{< SecureTransport/componentshortname  >}} refreshes the <em>File Tracking</em> page with the Core ID value pre-filled as a search criterion.</li>
</ul>         </td>
      </tr>
      <tr>
         <td>Post<br />
Transmission<br />
Status         </td>
         <td>Displays the operation type, whether the operation whether the operation succeeded or failed, the result of the operation, and comments that can provide additional information, such as if a transformation was performed. Multiple operations might be displayed.         </td>
      </tr>
   </tbody>
</table>

For server-initiated transfers, the *Status Detail* box also shows the protocol messages.

For HTTP transfers, the headers are provided since there are no commands sent.

For AS2 transfers, messages are also generated from the HTTP headers.

<span id="View4"></span>

## View transfer history of a file

Use the following procedure to view the transfer history of a file.

1.  Select **Operations > File Tracking**.  
    The *File Tracking* page is displayed.

2.  Click the name of a file.  
    The *File History Details* dialog box is displayed. It lists out the file transfer [status details](#View3) starting from the last client-initiated upload or server-initiated download and ending with the first renaming or deletion of the file with the same name. If the client-initiated upload or server-initiated download is missing because the file tracking log was rotated, the dialog box shows the first event for that file name.  
    *File History Details* contains detailed information about tracked events. Those include uploads and downloads, server-initiated transfer protocol messages, PGP encryption, routing a file from one account to another, post-transmission actions, and file deletion or renaming from a client-initiated command.  

    > **Note:**
    >
    > When transfers are performed by users behind a proxy or a load balancer, an additional parameter is listed: X-Forwarded-For. This is a dedicated HTTP header which is commonly used to identify the originating IP address of the user account and is especially useful when the user is behind a proxy or a load balancer. In such case, the Remote Host displays the IP address of the proxy/load balancer, and the X-Forwarded-For parameter displays the user's original IP address. Note that when the user is not behind a proxy/load balancer, the original IP address is displayed with the Remote Host parameter, and X-Forwarded-For is hidden from view.

3.  Click **Close** to return to the *File Tracking* page.

> **Note:**
>
> When a logged in account does not have permission to delete files and tries to delete them, the File History Details dialog box is not available.

<span id="View5"></span>

## View detailed information about an AR execution

Use the following procedure to view detailed status information about an advanced route execution:

1.  Select **Operations > File Tracking**.  
    The *File Tracking* page is displayed.
2.  Click the status icon or the file name for a specific advanced route execution.  
    The *Status Detail* window is displayed. It shows detailed information about the [file transfer](#View3) and the Route Status, including the operation type, whether the route succeeded or failed, the route package name, start and end times, duration, and the execution ID.
3.  Click **Close** to return to the *File Tracking* page.

**Related topics:**

-   <a href="" class="MCXref xref">Resubmit status</a>
-   <a href="../r_st_transfer_status" class="MCXref xref">Transfer status</a>
-   <a href="../t_st_filetransfers" class="MCXref xref">Manage file transfers</a>
-   <a href="../r_st_transferlogmaint" class="MCXref xref">Transfer Log Maintenance application</a>
