{
    "title": "Upload restrictions",
    "linkTitle": "Upload restrictions",
    "weight": "220"
}Use upload restrictions to allow or deny permission for users to upload files based on user class. For each user class, you can specify upload permissions and, for UNIX-based systems, the value of the owner, group and access permissions of the uploaded file.

The order of the entries in the list in the *Upload* pane of the *Restrictions* page is important because SecureTransport applies the upload restrictions starting with the last in the list and proceeding to the first. Once the user class for the user uploading the file is established, SecureTransport applies the last entry for that user class or for all user classes (\*) that has a file pattern that matches the file to be uploaded. If no entry matches, SecureTransport allows the upload.

For each user class, put the entries with more general paths before those with more specific paths. For example, to allow users to upload to the `/incoming` directory only, put an entry that allows uploads to that path after an entry that denies upload to all locations (\*).

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">For  metadata file upload for a protocol implemented using the file services interface, the IP address is not used to choose the user class. The upload restrictions defined for the first user class that matches the user type, name, and group control these transfers.         </td>
      </tr>
</table>

Configure upload restrictions on SecureTransport Server only.

The following topic describes how-to manage upload restrictions:

-   [Manage upload restrictions](t_st_uploadrestrictions) - Provides how-to instructions for managing upload restrictions.
