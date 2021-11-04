{
    "title": "Ad hoc file transfers",
    "linkTitle": "Ad hoc file transfers",
    "weight": "90"
}In addition to scheduled and event-driven server-initiated file transfers, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> supports ad hoc file transfers. Using the ST Web Client, a <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> user with the required rights can compose an email, attach one or more files, and send it to any email address. Because the files are uploaded to the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server instead of sent in the email, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> ad hoc file transfer provide the following features not available with the standard email protocol:

-   Large file size (for ST Web Client in a 32-bit browser, a maximum of 2 GB per message)
-   Choice of methods of file delivery to the mail recipient, including limits on allowed recipients and secure delivery options
-   Human-to-system (H2S) ad hoc file transfers where the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> server can process the file and forward it to another system

A message from ST Web Client can transfer at most 2 GB data.

The route the email takes to its recipient depends on the client the sender uses:

-   **ST Web Client** – The <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server sends the email using its SMTP configuration.

The recipient has different requirements to access the files, depending on the delivery mode.

Delivery modes are:

-   **Anonymous** – The recipient clicks a link to access the files.
-   **Challenge** – The recipient must answer a question correctly to access the files.
-   **Account** – The recipient must log on to <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> using ST Web Client with an existing user account.
-   **Auto-enroll** – <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> creates a user account for the recipient before the recipient can access the files. The recipient must log in to <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> using a temporary password and set a new password before retrieving the files.

The following features of <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> are useful for ad hoc file transfer recipients:

-   **Login by email** – The user can use an email address as the user name in a web client log in page.
-   **Unlicensed user accounts** – The user can only log in using ST Web Client to access the files and reply once to an ad hoc file transfer email.

For information about configuring ad hoc file transfers, see the following topics:

-   <a href="../../c_st_setup/t_st_adhocconfiguration#SetupMenu_1217491348_1052091" class="MCXref xref">Configure adhoc file transfers</a>
-   <a href="../../accounts/useraccounts/t_st_create_user_account#Unlicens" class="MCXref xref">Create a user account</a>
-   <a href="../../c_st_advancedaccountadministration/c_st_sitetemplates/t_st_sitetemplates#Create" class="MCXref xref">Create a site template</a>
-   <a href="##Create" class="MCXref xref">Create or edit a business unit</a>

For information about configuring H2S file transfers, see <a href="../../accounts/c_st_subscriptions/t_st_subscriptions#Human" class="MCXref xref">Human to System type application</a>.

<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> also supports system-to-human (S2H) file transfers. S2H file transfers are like other server-initiated file transfers, except the destination is a human, not a system. For example, the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> server can upload a large file from another server and send it to an email recipient using an S2H transfer site. The recipient of an S2H file transfer uses the same procedures to retrieve the file as the recipient of an ad hoc H2H file transfer. For more information, see <a href="../../accounts/transfersites/transfersites-s2h#top" class="MCXref xref">System to Human transfer sites</a>.
