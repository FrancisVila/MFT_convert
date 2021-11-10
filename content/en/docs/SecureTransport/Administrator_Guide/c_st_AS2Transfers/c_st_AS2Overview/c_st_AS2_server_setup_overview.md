{
    "title": "SecureTransport AS2 server: Setup overview",
    "linkTitle": "SecureTransport AS2 server: Setup overview",
    "weight": "230"
}This topic outlines the overall steps required to set up <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> for AS2 transfers. To setup <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server for AS2, complete these steps:

1.  Configure the AS2 server control settings.
    See <a href="../../../operations_menu/extended_server_control/ext_servercontrol-add-as2" class="MCXref xref">Manage the AS2 server</a>.
2.  Configure the AS2 settings. See <a href="../../../operations_menu/extended_server_control/ext_servercontrol-add-as2" class="MCXref xref">Manage the AS2 server</a>.
3.  Configure an HTTP proxy (optional). See <a href="../../../c_st_setup/c_st_networkzones/t_st_networkzones#Specify3" class="MCXref xref">Specify proxy settings in a network zone</a>.
4.  Start Transaction Manager and AS2 servers. See <a href="../../../operations_menu/extended_server_control" class="MCXref xref">Server control</a>.
5.  Create a SiteMailbox application or a Basic or <span class="mc-variable my_project_variables.Advanced_Routing variable">Advanced Routing</span> application. See <a href="" class="MCXref xref">Manage applications</a>.
6.  Create a user account. See <a href="../../../accounts/useraccounts/t_st_create_user_account#Unlicens" class="MCXref xref">Create a user account</a>.
7.  In the user account, create a AS2 transfer site using the AS2 protocol. During this step you specify the AS2 local and remote sites in the transfer site definition. See <a href="../../" class="MCXref xref">AS2 transfers</a>.
8.  In the user account, create a subscription to the `SiteMailbox` application or to the Basic or <span class="mc-variable my_project_variables.Advanced_Routing variable">Advanced Routing</span> application and specify the AS2 transfer site. See <a href="../../../accounts/c_st_subscriptions/t_st_subscriptions#Subscrib" class="MCXref xref">Subscribe an account to an application</a>.

**Related topics:**

-   <a href="../c_st_synchronous_asynchronous_receipts" class="MCXref xref">Synchronous and asynchronous receipts</a>
-   <a href="../c_st_as2_application_framework_architecture_workflow" class="MCXref xref">AS2 and application framework: Architecture and workflow</a>
