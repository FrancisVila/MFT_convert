{
    "title": "Ad hoc file transfers",
    "linkTitle": "Ad hoc file transfers",
    "weight": "90"
}In addition to scheduled and event-driven server-initiated file transfers, {{< SecureTransport/componentshortname  >}} supports ad hoc file transfers. Using the ST Web Client, a {{< SecureTransport/componentshortname  >}} user with the required rights can compose an email, attach one or more files, and send it to any email address. Because the files are uploaded to the {{< SecureTransport/componentshortname  >}} Server instead of sent in the email, {{< SecureTransport/componentshortname  >}} ad hoc file transfer provide the following features not available with the standard email protocol:

-   Large file size (for ST Web Client in a 32-bit browser, a maximum of 2 GB per message)
-   Choice of methods of file delivery to the mail recipient, including limits on allowed recipients and secure delivery options
-   Human-to-system (H2S) ad hoc file transfers where the {{< SecureTransport/componentshortname >}} server can process the file and forward it to another system

A message from ST Web Client can transfer at most 2 GB data.

The route the email takes to its recipient depends on the client the sender uses:

-   **ST Web Client** – The {{< SecureTransport/componentshortname >}} Server sends the email using its SMTP configuration.

The recipient has different requirements to access the files, depending on the delivery mode.

Delivery modes are:

-   **Anonymous** – The recipient clicks a link to access the files.
-   **Challenge** – The recipient must answer a question correctly to access the files.
-   **Account** – The recipient must log on to {{< SecureTransport/componentshortname >}} using ST Web Client with an existing user account.
-   **Auto-enroll** – {{< SecureTransport/componentshortname >}} creates a user account for the recipient before the recipient can access the files. The recipient must log in to {{< SecureTransport/componentshortname >}} using a temporary password and set a new password before retrieving the files.

The following features of {{< SecureTransport/componentshortname  >}} are useful for ad hoc file transfer recipients:

-   **Login by email** – The user can use an email address as the user name in a web client log in page.
-   **Unlicensed user accounts** – The user can only log in using ST Web Client to access the files and reply once to an ad hoc file transfer email.

For information about configuring ad hoc file transfers, see the following topics:

-   [Configure adhoc file transfers](../../c_st_setup/t_st_adhocconfiguration#SetupMenu_1217491348_1052091)
-   [Create a user account](../../accounts/useraccounts/t_st_create_user_account#Unlicens)
-   [Create a site template](../../c_st_advancedaccountadministration/c_st_sitetemplates/t_st_sitetemplates#Create)
-   [Create or edit a business unit](#Create)

For information about configuring H2S file transfers, see [Human to System type application](../../accounts/c_st_subscriptions/t_st_subscriptions#Human).

{{< SecureTransport/componentshortname  >}} also supports system-to-human (S2H) file transfers. S2H file transfers are like other server-initiated file transfers, except the destination is a human, not a system. For example, the {{< SecureTransport/componentshortname  >}} server can upload a large file from another server and send it to an email recipient using an S2H transfer site. The recipient of an S2H file transfer uses the same procedures to retrieve the file as the recipient of an ad hoc H2H file transfer. For more information, see [System to Human transfer sites](../../accounts/transfersites/transfersites-s2h#top).
