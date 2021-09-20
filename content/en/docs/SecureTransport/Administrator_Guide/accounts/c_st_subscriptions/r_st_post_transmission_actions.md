{
    "title": "Post-transmission actions",
    "linkTitle": "Post-transmission actions",
    "weight": "220"
}Subscriptions can also be set up to trigger post-transmission actions for either outgoing or incoming files. Post-transmission actions can be used to move, delete, or rename files based on the success or failure of a transfer. Using these options you can prevent files from being overwritten by renaming them, delete failed transfers, or move transferred files to a different directory on the server. You can also delete a file on the remote server after it is transferred. An expression language is provided so you do not need to specify a file name but can use patterns to control the post-transmission actions.

The following post-transmission actions are provided:

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
<th colspan="2">Post-transmission setting</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td colspan="3"><strong>Send Options</strong>
         </td>
      </tr>
      <tr>
         <td colspan="2">  On Failure         </td>
         <td>A failure occurs when the transfer is incomplete and all retry attempts were unsuccessful. Select one of the three choices: <strong>No Action</strong>, <strong>Delete</strong>, or <strong>Move/Rename File To</strong>. Selecting <strong>No Action</strong> causes the file to stay in the new location with the file name you specified. If another file with the same name is transferred to this location, the original file is overwritten. Selecting <strong>Delete</strong> removes the file from the new location. Selecting <strong>Move/Rename File To</strong> requires you to specify a directory in the location where you are transferring the files to and to provide an expression used to rename the file.         </td>
      </tr>
      <tr>
         <td colspan="2">  On Success         </td>
         <td>Select one of the three choices: <strong>No Action</strong>, <strong>Delete</strong>, or <strong>Move/Rename File To</strong>. Selecting <strong>No Action</strong> causes the file to stay in the new location with the file name you specified. If another file with the same name is transferred to this location, the original file is overwritten. Selecting <strong>Delete</strong> removes the file from the original location. Selecting <strong>Move/Rename File To</strong> requires you to specify a directory in the location where you are transferring the files to and to provide an expression used to rename the file.         </td>
      </tr>
      <tr>
         <td colspan="3"><strong>Receive Options</strong>
         </td>
      </tr>
      <tr>
         <td colspan="2">  On Failure         </td>
         <td>A failure occurs when the transfer is incomplete and all retry attempts were unsuccessful. Select one of the three choices: <strong>No Action</strong>, <strong>Delete</strong>, or <strong>Move/Rename File To</strong>. Selecting <strong>No Action</strong> causes the file to stay in the original location. If another file with the same name is transferred to this location, the original file is overwritten. Selecting <strong>Delete</strong> removes the file from the original location. Selecting <strong>Move/Rename File To</strong> requires you to specify a directory in the location where you are transferring the files from and to provide an expression used to rename the file.         </td>
      </tr>
      <tr>
         <td colspan="2">  On Temporary Failure         </td>
         <td>A temporary failure can occur when the transfer is incomplete and a retry occurs. Select one of the three choices: <strong>No Action</strong>, <strong>Delete</strong>, or <strong>Move/Rename File To</strong>. Selecting <strong>No Action</strong> causes the file to stay in the original location. If another file with the same name is transferred to this location, the original file is overwritten. Selecting <strong>Delete</strong> removes the file from the original location. Selecting <strong>Move/Rename File To</strong> requires you to specify a directory in the location where you are transferring the files from and to provide an expression used to rename the file. On Temporary Failure is only available for server-initiated transfers         </td>
      </tr>
      <tr>
         <td colspan="2">  On Success         </td>
         <td>Select one of these choices: <strong>No Action</strong> or <strong>Move/Rename File To</strong>. Selecting <strong>No Action</strong> causes the file to stay in the original location. If another file with the same name is transferred to this location, the original file is overwritten. Selecting <strong>Move/Rename File To</strong> requires you to specify a directory in the location where you are transferring the files from and to provide an expression used to rename the file.         </td>
      </tr>
   </tbody>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">To preserve the original file name when using the <strong>Move/Rename File To</strong> option, use the <code>${stenv.target}</code> or <code>${stenv['target']}</code> expressions.<br/><br/>When using <span>SecureTransport</span> on the Windows platform and you are renaming a file for a post-transmission action, you cannot use the following characters: <code>* &lt; &gt; ? " / \ | :</code>.<br/><br/>Use URL encoding instead if you need to represent one of these characters for a remote post-transmission action.<br/><br/>If you are using <span>SecureTransport</span> on a UNIX-based platform, the following characters cannot be used: <code>/ . \</code>.<br/><br/>When using <span>SecureTransport</span> on the Windows platform and you configure a post-transmission action in a subscription to move a file from one drive partition to another, no folders are created on the new drive partition and the files are not moved.         </td>
      </tr>
</table>

Paths specified in post-transmission options are treated as either relative to the subscription folder or an absolute path starting from the subscription folder.

-   Relative paths are resolved against the target location which might not be the subscription folder, but can be any of its subfolders. If you use ".." in the file name expression, the final destination cannot go up the folder tree past the subscription folder.
-   Absolute paths are calculated as relative to the subscription folder. The final destination here is bound to the subscription folder even when the expression uses ".." one or more times.

**Related topics:**

-   [Encryption options](../r_st_encryption_options)
-   [Manage subscriptions](../t_st_subscriptions)
