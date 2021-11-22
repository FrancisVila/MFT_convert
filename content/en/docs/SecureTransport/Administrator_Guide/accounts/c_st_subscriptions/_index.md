{
    "title": "Subscriptions",
    "linkTitle": "Subscriptions",
    "weight": "180"
}A subscription provides a functional connection between a user account and an application.

For each subscription, {{< SecureTransport/componentshortname  >}} creates a subscription folder and stores and manages all files that are transferred or transformed as a result of the application activity. A single application can have subscriptions from multiple accounts and a single account can subscribe to multiple applications. An account can subscribe to new instances of the same application as long as each instance has a unique subscription folder name.

Additional transfer configurations are possible for subscriptions. Use subscriptions to trigger the execution of specific actions, defined in the respective application, when a subscription event occurs, such as an incoming file transfer in the dedicated subscription folder.

> **Note:**
>
> The application is not triggered if the file is uploaded into another folder first and is then moved or copied into the subscription folder.

The following topics describe how to manage subscriptions:

-   <a href="r_st_encryption_options" class="MCXref xref">Encryption options</a> - Lists the subscription encryption options.
-   <a href="r_st_post_transmission_actions" class="MCXref xref">Post-transmission actions</a> - Lists the subscription post-transmission actions.
-   <a href="t_st_subscriptions" class="MCXref xref">Manage subscriptions</a> - Provides how-to instructions for managing subscriptions.
