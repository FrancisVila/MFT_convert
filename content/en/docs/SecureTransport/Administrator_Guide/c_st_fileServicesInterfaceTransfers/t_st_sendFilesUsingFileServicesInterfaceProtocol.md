{
    "title": "Send files using a file services interface protocol",
    "linkTitle": "Send files using a file services interface protocol",
    "weight": "230"
}For SecureTransport to send files to another system using a file services interface protocol, you must create a transfer site for a file services interface protocol, and subscribe to an application that sends files to that site.

1.  Create or identify an account to send files to the other system. For details, see [Create a user account](../../accounts/useraccounts/t_st_create_user_account).
2.  Create a transfer site in that account that references the file services interface protocol. For details, see [File services interface transfer sites](../../accounts/transfersites/r_st_fileservicesinterfaceprotocoltransfersites).
3.  Subscribe that account to an application configured to send files to that transfer site. For details, see [Subscribe an account to an application](../../accounts/c_st_subscriptions/t_st_subscriptions).

When the application sends a file to the transfer site, SecureTransport finds the information for the protocol in the protocol registry and calls a program configured for the protocol to perform the transfer.
