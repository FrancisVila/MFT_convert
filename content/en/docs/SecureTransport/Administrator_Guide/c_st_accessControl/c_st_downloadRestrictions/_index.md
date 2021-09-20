{
    "title": "Download restrictions",
    "linkTitle": "Download restrictions",
    "weight": "230"
}Use download restrictions to allow or deny permission for users to download files based on user class. For each user class, you can specify upload permissions that allow or deny the user the ability to view, create, or modify files and directories.

The order of the entries in the list in the *Download* pane of the *Restrictions* page is important because SecureTransport applies the download restrictions starting with the last in the list and proceeding to the first. Once the user class for the user downloading the file is established, SecureTransport applies the last entry for that user class or for all user classes (\*) that has a file pattern that matches the file to be downloaded. If no entry matches, SecureTransport allows the download.

For each user class, put the entries with more general paths before those with more specific paths. For example, to allow users to download from the `/outgoing` directory only, put an entry that allows downloads from that path after an entry that denies download from all locations (\*).

Configure download restrictions on SecureTransport Server only.

The following topic describes how to manage download restrictions:

-   [Manage download restrictions](t_st_downloadrestrictions) - Provides how-to instructions for managing download restrictions.
