{
    "title": "Manage accounts",
    "linkTitle": "Manage accounts",
    "weight": "130"
}Use the pages of the **Accounts** menu to create and manage login accounts for users, administrators and partners.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">In order for login by email to function properly, all user accounts must be assigned unique email addresses. Additionally, the client password reset feature will not work if emails assigned to users accounts are not unique.         </td>
      </tr>
</table>

## Accounts overview

An Axway SecureTransport *account* contains information about a user or an internal system that processes SecureTransport file transfers. SecureTransport supports two kinds of accounts: *user* and *service*.

## User accounts

A *user account* is typically external to your enterprise. A user account consists of settings such as the account name, contact information, login information, *subscription* information (the *applications* this user account uses to process file transfers), *transfer site* information, and *certificate* information. User accounts connect to SecureTransport through subscriptions to one or more applications. For details, see [User accounts](useraccounts).

## Service accounts

A *service account* is typically used to represent processes on systems internal to your enterprise. It consists of settings, transfer site information and certificate information. Instead of subscribing to an application, however, a service account uses a *connector* to connect to one or more applications. For details, see [Manage service accounts](t_st_serviceaccounts).

## Subscriptions, transfer sites, and certificates

A subscription defines how files are submitted to and received from applications. For details, see [Manage subscriptions](c_st_subscriptions/t_st_subscriptions).

A transfer site is a location such as a local folder or protocol server used by SecureTransport to pull data from or send data to during a transfer. For details, see [Transfer sites](transfersites).

A certificate can be one of three types: login, partner, or private. Each certificate type can be used by the account for different purposes. For details, see [Manage login certificates](c_st_usercertificates/t_st_usercertificates).

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
