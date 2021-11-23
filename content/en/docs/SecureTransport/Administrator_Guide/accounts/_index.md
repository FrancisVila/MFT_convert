{
    "title": "Manage Accounts",
    "linkTitle": "Manage accounts",
    "weight": "120"
}Use the pages of the **Accounts** menu to create and manage login accounts for users, administrators and partners.

> **Note:**
>
> In order for login by email to function properly, all user accounts must be assigned unique email addresses. Additionally, the client password reset feature will not work if emails assigned to users accounts are not unique.

## Accounts overview

An {{< SecureTransport/componentlongname  >}} *account* contains information about a user or an internal system that processes {{< SecureTransport/componentshortname  >}} file transfers. {{< SecureTransport/componentshortname  >}} supports two kinds of accounts: *user* and *service*.

## User accounts

A *user account* is typically external to your enterprise. A user account consists of settings such as the account name, contact information, login information, *subscription* information (the *applications* this user account uses to process file transfers), *transfer site* information, and *certificate* information. User accounts connect to {{< SecureTransport/componentshortname  >}} through subscriptions to one or more applications. For details, see [User accounts](useraccounts#AccountsMenu_2253641766_1100353).

## Service accounts

A *service account* is typically used to represent processes on systems internal to your enterprise. It consists of settings, transfer site information and certificate information. Instead of subscribing to an application, however, a service account uses a *connector* to connect to one or more applications. For details, see [Manage service accounts](t_st_serviceaccounts#AccountsMenu_2253641766_1060038).

## Subscriptions, transfer sites, and certificates

A subscription defines how files are submitted to and received from applications. For details, see [Manage subscriptions](c_st_subscriptions/t_st_subscriptions#AccountsMenu_2253641766_1247370).

A transfer site is a location such as a local folder or protocol server used by {{< SecureTransport/componentshortname  >}} to pull data from or send data to during a transfer. For details, see [Transfer sites](transfersites#AccountsMenu_2253641766_1151145).

A certificate can be one of three types: login, partner, or private. Each certificate type can be used by the account for different purposes. For details, see [Manage login certificates](c_st_usercertificates/t_st_usercertificates#AccountsMenu_2253641766_1090701).

## Applications

An application is an instance of an *application type*. An application type is a workflow definition that is triggered by either data arrival or a scheduled event. An application is created when you configure an application type, name it and save it. For more information, see [Applications](../applications).

 

**Related topics:**

-   [User accounts](useraccounts)
-   [Duplicate an account](t_st_duplicateaccount)
-   [User certificates](c_st_usercertificates)
-   [Transfer sites](transfersites)
-   [Transfer profiles](t_st_transferprofiles)
-   [Subscriptions](c_st_subscriptions)
-   [Control login name case sensitivity](t_st_controlloginnamecasesensitivity)
-   [Configure a secret question](t_st_password_reset/t_st_secretquestion)
