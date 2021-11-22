{
    "title": "Send files using a file services interface protocol",
    "linkTitle": "Send files using a file services interface protocol",
    "weight": "220"
}For {{< SecureTransport/componentshortname  >}} to send files to another system using a file services interface protocol, you must create a transfer site for a file services interface protocol, and subscribe to an application that sends files to that site.

1.  Create or identify an account to send files to the other system. For details, see <a href="../../accounts/useraccounts/t_st_create_user_account#AccountsMenu_2253641766_1058767" class="MCXref xref">Create a user account</a>.
2.  Create a transfer site in that account that references the file services interface protocol. For details, see <a href="../../accounts/transfersites/r_st_fileservicesinterfaceprotocoltransfersites#AccountsMenu_2253641766_1250399" class="MCXref xref">File services interface transfer sites</a>.
3.  Subscribe that account to an application configured to send files to that transfer site. For details, see <a href="../../accounts/c_st_subscriptions/t_st_subscriptions#Subscrib" class="MCXref xref">Subscribe an account to an application</a>.

When the application sends a file to the transfer site, {{< SecureTransport/componentshortname  >}} finds the information for the protocol in the protocol registry and calls a program configured for the protocol to perform the transfer.
