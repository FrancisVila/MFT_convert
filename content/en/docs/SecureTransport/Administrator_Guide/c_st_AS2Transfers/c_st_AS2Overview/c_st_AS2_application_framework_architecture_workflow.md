{
    "title": "AS2 and application framework: Architecture and workflow",
    "linkTitle": "AS2 and application framework: Architecture and workflow",
    "weight": "230"
}AS2 transfers can be handled by an AS2 application, which is an instance of the generic Site Mailbox application type. The AS2 Site Mailbox application can perform inbound and outbound transfers from and to the same AS2 site. To this end, the respective account is subscribed to the AS2 Site Mailbox application and the subscription is associated with the AS2 site that is set up during the definition of the transfer site of the account. The application outgoing and incoming subfolders are called by default `outbox` and `inbox`.

Some basic application framework concepts, relating to the AS2 implementation in SecureTransport, are outlined here.

The following topics describe the architecture and workflow of AS2 and the application framework:

-   [Application for AS2](#applicat)
-   [AS2 site](#as2)

**Related topics:**

-   [Synchronous and asynchronous receipts](../c_st_synchronous_asynchronous_receipts)
-   [SecureTransport AS2 server: Setup overview](../c_st_as2_server_setup_overview)

## <span id="Applicat"></span>Application for AS2

The particular AS2 application that handles AS2 transfers can be an instance of the Site Mailbox application type or the Basic or Advanced Routing application types. To be able to transfer files over the AS2 protocol, the user account must be subscribed to the AS2 application and the subscriptions must have the AS2 site defined.

The AS2 application must have an outgoing subfolder `outbox` and an incoming subfolder `inbox`.

## <span id="AS2"></span>AS2 site

AS2 partnership holds a description of local and remote parties which participate in AS2 transfers. Besides identification information (local and remote IDs and remote address), the partnership holds information about data transformation of payload and MDN requirements.

The SecureTransport architecture, implemented by the application framework, introduces the site concept. A SecureTransport site has all the necessary attributes to connect to the AS2 site and transfer the contents. The only partnerships items that are not a part of the SecureTransport site specification are the following:

-   **Subfolder** – an attribute of subscription between the AS2 user account and the AS2 Site Mailbox application.
-   **Username** – an attribute of the user account for AS2.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">AS2 site does not support server-initiated inbound transfers (server pull).         </td>
      </tr>
</table>

For details, see [Manage applications](manage_applications.htm).
