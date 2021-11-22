{
    "title": "Receive files using a file services interface protocol",
    "linkTitle": "Receive files using a file services interface protocol",
    "weight": "210"
}For {{< SecureTransport/componentshortname  >}} to receive files sent by another system using a file services interface protocol, you must set up access to a shared directory, create an application, and subscribe an account to that application.

1.  Determine which shared directory the systems are to use to transfer the files and make it accessible from both systems.
2.  Perform the procedure in <a href="../../applications/applicationstransferfileservicesinterface#top" class="MCXref xref">File Transfer via File Services Interface application</a>.
3.  Create or identify an account to receive the metadata files from the other system. For details, see <a href="../../accounts/useraccounts/t_st_create_user_account#AccountsMenu_2253641766_1058767" class="MCXref xref">Create a user account</a>.
4.  Subscribe that account to the file services interface application. For details, see <a href="../../accounts/c_st_subscriptions/t_st_subscriptions#Subscrib" class="MCXref xref">Subscribe an account to an application</a>.

When the remote system transfers the metadata file to the subscription folder, the file services interface application reads it and processes the transferred file based on its contents.

The following topics describe the metadata file and the location of the transferred file:

-   <a href="r_st_metadata_file" class="MCXref xref">Metadata file</a> - Lists and describes the elements in the XML metadata file.
-   <a href="c_st_location_of_transferred_file" class="MCXref xref">Location of the transferred file</a> - Describes the location of the transferred file.
