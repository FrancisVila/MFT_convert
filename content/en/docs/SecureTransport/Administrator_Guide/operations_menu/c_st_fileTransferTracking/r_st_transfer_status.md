{
    "title": "Transfer status",
    "linkTitle": "Transfer status",
    "weight": "130"
}Transfer status is represented by an icon. The following table shows each icon and its meaning:

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Icon         </th>
<th class="HeadE-Column1-Header1">Status         </th>
<th class="HeadD-Column1-Header1">Protocols<br />
supported         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><img src="/Images/SecureTransport/Operations_FileTracking_MDNReceipt.png" alt="MDN receipt" />         </td>
         <td>MDN Receipt – Click to view or verify the MDN receipt for the transfer or to view the PeSIT acknowledgment for the transfer.         </td>
         <td>All         </td>
      </tr>
      <tr>
         <td><img src="/Images/SecureTransport/TransferStatusOK.png" alt="Processed successfully" />         </td>
         <td>Processed/Successful – The file was transferred successfully.         </td>
         <td>All         </td>
      </tr>
      <tr>
         <td><img src="/Images/SecureTransport/TransferStatusRunning.png" alt="In progress" />         </td>
         <td>In progress – The file is currently being transferred.         </td>
         <td>All         </td>
      </tr>
      <tr>
         <td><img src="/Images/SecureTransport/TransferStatusPause.png" alt="Paused" />         </td>
         <td>Paused – The remote server has paused the PeSIT transfer.         </td>
         <td>PeSIT         </td>
      </tr>
      <tr>
         <td><img src="/Images/SecureTransport/TransferStatusFail.png" alt="Failed" />         </td>
         <td><p>Failed – The file transfer failed for some reason. Transfers intentionally aborted by file transfer clients and end users are included in this category.</p>
<p>The <em>File Tracking</em> page provides additional information to help distinguish transfers intentionally aborted from those that failed for other reasons.</p>         </td>
         <td>All         </td>
      </tr>
      <tr>
         <td><img src="/Images/SecureTransport/Operations_FileTracking_PTAFailed.png" alt="Failed subtransmission" />         </td>
         <td>Failed Subtransmission – The file transfer was successful, but one or more Subtransmission actions requested failed for some reason. Subtransmission actions include post-transmission actions and data transformations such as encryption or decryption.         </td>
         <td>All         </td>
      </tr>
   </tbody>
</table>

Click each transfer status icon to view detailed status information about the file transfer.

If a padlock icon displays in the Secure Transfer column (fourth from the left), then the transfer was performed over a secure connection such as FTPS, HTTPS, or SSH.

> **Note:**
>
> If a file is renamed immediately after a file transfer, both the MDN receipt creation and verification may fail.

**Related topics:**

-   [Resubmit status]()
-   [View file transfer information](../t_st_viewfiletransferinfo)
-   [Manage file transfers](../t_st_filetransfers)
-   [Transfer Log Maintenance application](../r_st_transferlogmaint)
