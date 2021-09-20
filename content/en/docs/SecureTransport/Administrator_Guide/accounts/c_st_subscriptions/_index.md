{
    "title": "Subscriptions",
    "linkTitle": "Subscriptions",
    "weight": "190"
}A subscription provides a functional connection between a user account and an application.

For each subscription, SecureTransport creates a subscription folder and stores and manages all files that are transferred or transformed as a result of the application activity. A single application can have subscriptions from multiple accounts and a single account can subscribe to multiple applications. An account can subscribe to new instances of the same application as long as each instance has a unique subscription folder name.

Additional transfer configurations are possible for subscriptions. Use subscriptions to trigger the execution of specific actions, defined in the respective application, when a subscription event occurs, such as an incoming file transfer in the dedicated subscription folder.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The application is not triggered if the file is uploaded into another folder first and is then moved or copied into the subscription folder.         </td>
      </tr>
</table>

The following topics describe how to manage subscriptions:

-   [Encryption options](r_st_encryption_options) - Lists the subscription encryption options.
-   [Post-transmission actions](r_st_post_transmission_actions) - Lists the subscription post-transmission actions.
-   [Manage subscriptions](t_st_subscriptions) - Provides how-to instructions for managing subscriptions.
