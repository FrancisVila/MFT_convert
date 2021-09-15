{
    "title": "Transfer status",
    "linkTitle": "Transfer status",
    "weight": "140"
}Transfer status is represented by an icon. The following table shows each icon and its meaning:

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Icon</th>
         <th>Status</th>
         <th>Protocols<br/>supported</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
<img alt="MDN receipt" src="Operations_FileTracking_PTAFailed.png"/>
         </td>
         <td>MDN Receipt – Click to view or verify the MDN receipt for the transfer or to view the PeSIT acknowledgment for the transfer.         </td>
         <td>All         </td>
      </tr>
      <tr>
         <td>
<img alt="Processed successfully" src="Operations_FileTracking_PTAFailed.png"/>
         </td>
         <td>Processed/Successful – The file was transferred successfully.         </td>
         <td>All         </td>
      </tr>
      <tr>
         <td>
<img alt="In progress" src="Operations_FileTracking_PTAFailed.png"/>
         </td>
         <td>In progress – The file is currently being transferred.         </td>
         <td>All         </td>
      </tr>
      <tr>
         <td>
<img alt="Paused" src="Operations_FileTracking_PTAFailed.png"/>
         </td>
         <td>Paused – The remote server has paused the PeSIT transfer.         </td>
         <td>PeSIT         </td>
      </tr>
      <tr>
         <td>
<img alt="Failed" src="Operations_FileTracking_PTAFailed.png"/>
         </td>
         <td>
            <p>Failed – The file transfer failed for some reason. Transfers intentionally aborted by file transfer clients and end users are included in this category.</p>
            <p>The <em>File Tracking</em> page provides additional information to help distinguish transfers intentionally aborted from those that failed for other reasons.</p>
         </td>
         <td>All         </td>
      </tr>
      <tr>
         <td>
<img alt="Failed subtransmission" src="Operations_FileTracking_PTAFailed.png"/>
         </td>
         <td>Failed Subtransmission – The file transfer was successful, but one or more Subtransmission actions requested failed for some reason. Subtransmission actions include post-transmission actions and data transformations such as encryption or decryption.         </td>
         <td>All         </td>
      </tr>
   </tbody>
</table>

Click each transfer status icon to view detailed status information about the file transfer.

If a padlock icon displays in the Secure Transfer column (fourth from the left), then the transfer was performed over a secure connection such as FTPS, HTTPS, or SSH.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">If a file is renamed immediately after a file transfer, both the MDN receipt creation and verification may fail.         </td>
      </tr>
</table>

**Related topics:**

-   [Resubmit status](../c_st_resubmit_status)
-   [View file transfer information](../t_st_viewfiletransferinfo)
-   [Manage file transfers](../t_st_filetransfers)
-   [Transfer Log Maintenance application](../r_st_transferlogmaint)
