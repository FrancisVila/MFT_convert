{
    "title": "Manage Accounts",
    "linkTitle": "Manage accounts",
    "weight": "120"
}Use the pages of the **Accounts** menu to create and manage login accounts for users, administrators and partners.

> **Note:**
>
> In order for login by email to function properly, all user accounts must be assigned unique email addresses. Additionally, the client password reset feature will not work if emails assigned to users accounts are not unique.

## Accounts overview

An <span class="mc-variable axway_variables.Component_Long_Name variable">Axway SecureTransport</span> *account* contains information about a user or an internal system that processes <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> file transfers. <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> supports two kinds of accounts: *user* and *service*.

## User accounts

A *user account* is typically external to your enterprise. A user account consists of settings such as the account name, contact information, login information, *subscription* information (the *applications* this user account uses to process file transfers), *transfer site* information, and *certificate* information. User accounts connect to <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> through subscriptions to one or more applications. For details, see <a href="useraccounts#AccountsMenu_2253641766_1100353" class="MCXref xref">User accounts</a>.

## Service accounts

A *service account* is typically used to represent processes on systems internal to your enterprise. It consists of settings, transfer site information and certificate information. Instead of subscribing to an application, however, a service account uses a *connector* to connect to one or more applications. For details, see <a href="t_st_serviceaccounts#AccountsMenu_2253641766_1060038" class="MCXref xref">Manage service accounts</a>.

## Subscriptions, transfer sites, and certificates

A subscription defines how files are submitted to and received from applications. For details, see <a href="c_st_subscriptions/t_st_subscriptions#AccountsMenu_2253641766_1247370" class="MCXref xref">Manage subscriptions</a>.

A transfer site is a location such as a local folder or protocol server used by <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> to pull data from or send data to during a transfer. For details, see <a href="transfersites#AccountsMenu_2253641766_1151145" class="MCXref xref">Transfer sites</a>.

A certificate can be one of three types: login, partner, or private. Each certificate type can be used by the account for different purposes. For details, see <a href="c_st_usercertificates/t_st_usercertificates#AccountsMenu_2253641766_1090701" class="MCXref xref">Manage login certificates</a>.

## Applications

An application is an instance of an *application type*. An application type is a workflow definition that is triggered by either data arrival or a scheduled event. An application is created when you configure an application type, name it and save it. For more information, see <a href="../applications" class="MCXref xref">Applications</a>.

 

**Related topics:**

-   <a href="useraccounts" class="MCXref xref">User accounts</a>
-   <a href="t_st_duplicateaccount" class="MCXref xref">Duplicate an account</a>
-   <a href="c_st_usercertificates" class="MCXref xref">User certificates</a>
-   <a href="transfersites" class="MCXref xref">Transfer sites</a>
-   <a href="t_st_transferprofiles" class="MCXref xref">Transfer profiles</a>
-   <a href="c_st_subscriptions" class="MCXref xref">Subscriptions</a>
-   <a href="t_st_controlloginnamecasesensitivity" class="MCXref xref">Control login name case sensitivity</a>
-   <a href="t_st_password_reset/t_st_secretquestion" class="MCXref xref">Configure a secret question</a>
