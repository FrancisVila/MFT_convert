{
    "title": "Post-transmission actions",
    "linkTitle": "Post-transmission actions",
    "weight": "210"
}Subscriptions can also be set up to trigger post-transmission actions for either outgoing or incoming files. Post-transmission actions can be used to move, delete, or rename files based on the success or failure of a transfer. Using these options you can prevent files from being overwritten by renaming them, delete failed transfers, or move transferred files to a different directory on the server. You can also delete a file on the remote server after it is transferred. An expression language is provided so you do not need to specify a file name but can use patterns to control the post-transmission actions.

The following post-transmission actions are provided:

<table>
   <thead>
      <tr>
<th colspan="2" class="HeadD-Column1-Header1">Post-transmission setting         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><strong>Send Options</strong>         </td>
      </tr>
      <tr>
         <td>  On Failure         </td>
      </tr>
      <tr>
         <td>  On Success         </td>
      </tr>
      <tr>
         <td><strong>Receive Options</strong>         </td>
      </tr>
      <tr>
         <td>  On Failure         </td>
      </tr>
      <tr>
         <td>  On Temporary Failure         </td>
      </tr>
      <tr>
         <td>  On Success         </td>
      </tr>
   </tbody>
</table>

> **Note:**
>
> To preserve the original file name when using the Move/Rename File To option, use the ${stenv.target} or ${stenv\['target'\]} expressions.When using SecureTransport on the Windows platform and you are renaming a file for a post-transmission action, you cannot use the following characters: \* &lt; &gt; ? " / \\ | :.Use URL encoding instead if you need to represent one of these characters for a remote post-transmission action.If you are using SecureTransport on a UNIX-based platform, the following characters cannot be used: / . \\.When using SecureTransport on the Windows platform and you configure a post-transmission action in a subscription to move a file from one drive partition to another, no folders are created on the new drive partition and the files are not moved.

Paths specified in post-transmission options are treated as either relative to the subscription folder or an absolute path starting from the subscription folder.

-   Relative paths are resolved against the target location which might not be the subscription folder, but can be any of its subfolders. If you use ".." in the file name expression, the final destination cannot go up the folder tree past the subscription folder.
-   Absolute paths are calculated as relative to the subscription folder. The final destination here is bound to the subscription folder even when the expression uses ".." one or more times.

**Related topics:**

-   <a href="../r_st_encryption_options" class="MCXref xref">Encryption options</a>
-   <a href="../t_st_subscriptions" class="MCXref xref">Manage subscriptions</a>
