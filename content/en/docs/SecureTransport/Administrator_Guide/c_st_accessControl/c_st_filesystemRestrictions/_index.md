{
    "title": "Filesystem restrictions",
    "linkTitle": "Filesystem restrictions",
    "weight": "210"
}Use the *Filesystem* pane of the *Restrictions* page to control rights for specific user classes to modify files and directories on the SecureTransport server.

The order of the entries in the list in the *Filesystem* pane of the *Restrictions* page is important because SecureTransport applies the filesystem restrictions starting with the last in the list and proceeding to the first. Once the user class for the user filesystem is established, SecureTransport applies the last entry for that user class or for all user classes (\*) that has a file pattern that matches the filesystem. If no entry matches, SecureTransport allows access to the filesystem.

For each user class, put the entries with more general paths before those with more specific paths. For example, to allow users to download from the `/outgoing` directory only, put an entry that allows downloads from that path after an entry that denies download from all locations (\*).

Operations that can be allowed or denied are:

-   **Delete a File** – Specifies whether or not users from the specified user class may delete files on the SecureTransport Server.

-   **Rename a File** – Specifies whether or not users from the specified user class may rename files on the SecureTransport Server.

-   **Overwrite a File** – Specifies whether or not users from the specified user class may overwrite existing files on the SecureTransport Server.

-   **Make a Directory** – Specifies whether or not users from the specified user class may create directories on the SecureTransport Server.

-   **Remove a Directory** – Specifies whether or not users from the specified user class may remove directories from the SecureTransport Server.

-   **Change File Mode** – Specifies whether or not users from the specified user class may change file access permissions on the SecureTransport Server. This option is applicable only for UNIX.

-   **Change Umask** – Specifies whether or not users from the specified user class may change the access permissions mask for new files being uploaded to the SecureTransport Server. This option is applicable only for UNIX.  
    

    <table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Under certain conditions your operating system umask configuration may take priority over the SecureTransport umask configuration. Normally, if the SecureTransport <code>Users.DefaultUmask</code> configuration option is set to some value,  the SecureTransport umask should be used. If the SecureTransport configuration option <code>Users.DefaultUmask</code> is empty, the operating system umask should be used.         </td>
      </tr>
</table>

-   **Access a File/Directory** – Specifies whether or not users from the specified user class have access to files or directories on the SecureTransport Server.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">When a ST Web Client user moves a file using cut and paste, <span>SecureTransport</span> checks the filesystem Rename a File permission. <span>SecureTransport</span> does not check the upload restrictions in this case.         </td>
      </tr>
</table>

The `Restrictions.OrderOfApplication` server configuration option defines the order of application for filesystem and upload and download restrictions. There are two available values for the option:

-   **legacy** (default) - rules are applied from bottom to top
-   **new** - rules are applied from top to bottom

Configure filesystem restrictions on SecureTransport Server only.

The following topic describes how to manage filesystem restrictions:

-   [Manage filesystem restrictions](t_st_filesystemrestrictions) - Provides how-to instructions for managing filesystem restrictions.
