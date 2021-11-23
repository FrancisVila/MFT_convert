{
    "title": "SecureTransport AS2 server: Setup overview",
    "linkTitle": "SecureTransport AS2 server: Setup overview",
    "weight": "230"
}This topic outlines the overall steps required to set up {{< SecureTransport/componentshortname  >}} for AS2 transfers. To setup {{< SecureTransport/componentshortname  >}} Server for AS2, complete these steps:

1.  Configure the AS2 server control settings.
    See [Manage the AS2 server](../../../operations_menu/extended_server_control/ext_servercontrol-add-as2).
2.  Configure the AS2 settings. See [Manage the AS2 server](../../../operations_menu/extended_server_control/ext_servercontrol-add-as2).
3.  Configure an HTTP proxy (optional). See [Specify proxy settings in a network zone](../../../c_st_setup/c_st_networkzones/t_st_networkzones#Specify3).
4.  Start Transaction Manager and AS2 servers. See [Server control](../../../operations_menu/extended_server_control).
5.  Create a SiteMailbox application or a Basic or {{< SecureTransport/advancedrouting >}} application. See [Manage applications]().
6.  Create a user account. See [Create a user account](../../../accounts/useraccounts/t_st_create_user_account#Unlicens).
7.  In the user account, create a AS2 transfer site using the AS2 protocol. During this step you specify the AS2 local and remote sites in the transfer site definition. See [AS2 transfers](../../).
8.  In the user account, create a subscription to the `SiteMailbox` application or to the Basic or {{< SecureTransport/advancedrouting >}} application and specify the AS2 transfer site. See [Subscribe an account to an application](../../../accounts/c_st_subscriptions/t_st_subscriptions#Subscrib).

**Related topics:**

-   [Synchronous and asynchronous receipts](../c_st_synchronous_asynchronous_receipts)
-   [AS2 and application framework: Architecture and workflow](../c_st_as2_application_framework_architecture_workflow)
