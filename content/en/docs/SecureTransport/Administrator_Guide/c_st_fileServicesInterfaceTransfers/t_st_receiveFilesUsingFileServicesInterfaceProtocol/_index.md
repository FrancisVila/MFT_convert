{
    "title": "Receive files using a file services interface protocol",
    "linkTitle": "Receive files using a file services interface protocol",
    "weight": "220"
}For SecureTransport to receive files sent by another system using a file services interface protocol, you must set up access to a shared directory, create an application, and subscribe an account to that application.

1.  Determine which shared directory the systems are to use to transfer the files and make it accessible from both systems.
2.  Perform the procedure in [File Transfer via File Services Interface application](../../applications/applicationstransferfileservicesinterface).
3.  Create or identify an account to receive the metadata files from the other system. For details, see [Create a user account](../../accounts/useraccounts/t_st_create_user_account).
4.  Subscribe that account to the file services interface application. For details, see [Subscribe an account to an application](../../accounts/c_st_subscriptions/t_st_subscriptions).

When the remote system transfers the metadata file to the subscription folder, the file services interface application reads it and processes the transferred file based on its contents.

The following topics describe the metadata file and the location of the transferred file:

-   [Metadata file](r_st_metadata_file) - Lists and describes the elements in the XML metadata file.
-   [Location of the transferred file](c_st_location_of_transferred_file) - Describes the location of the transferred file.
