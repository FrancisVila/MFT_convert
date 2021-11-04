{
    "title": "Configuring asynchronous MDN receipts with AS2 transfers",
    "linkTitle": "Configuring asynchronous MDN receipts with AS2 transfers",
    "weight": "260"
}MDN (Message Disposition Notification) receipts serve to warrant data integrity and non-repudiation in the underlying protocol, in this case AS2. Asynchronous AS2 MDN receipts are communicated in separate request from transfers, and this behavior requires specific setup for correct processing in advanced routes. It is possible to use Advanced Routing (AR) for AS2 file transfers using asynchronous MDN receipts but the available options require special out-of-the-box approaches which serve as *workarounds*. To better understand the logic of each workaround, it is important to understand where the concepts in AR and asynchronous exchange of MDN receipts differ and where they intercept.

## AS2 MDN receipts overview

The AS2 protocol requires a bi-directional partnership to be created: you must define the partner's server on your side, and the partner defines your server on theirs. This creates several use cases with this partnership and the AS2 MDN receipts configuration differs depending on the actual usage.

It is possible to use the partnership only in one direction - to send files to a partner or receive files from them (files that partner sends you). In this case the AS2-MDN is configured only for one side of the partnership.

For two-way, bi-directional communication between partners, the asynchronous AS2-MDN receipts have to be configured on both ends, for both inbound and outbound directions.

 The asynchronous AS2-MDN receipt is sent in a separate HTTP or HTTPS TCP/IP connection and is similar to an inbound transfer from a partner.

## <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> Applications for AS2 transfers

In <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span>, the setup that handles AS2 transfers can be an instance of Site Mailbox, the Basic Application or the Advanced Routing application types. A user account must be subscribed to either of these applications to be able to send / receive files over the AS2 protocol.

## AR uses Route setup for outbound transfers

With Advanced Routing, the configuration for outbound transfers is part of the Routes, not the Subscription. This presents a problem with AS2 transfers and the asynchronous MDN receipts due to the way <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> relates the received receipts to the transfers: via the Subscription.

In the cases with e.g. Site Mailbox and Basic Application, the Subscription holds the configuration for the outbound transfers, so when <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> receives a MDN, it can relate to the proper subscription and validate the MDN. With Advanced Routing, however, when a file is sent to partner via AS2 in a Route, and the MDN is returned by the partner, <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> is unable to locate the Subscription the MDN belongs to and throws an error:


    org.openas2.partner.PartnershipNotFoundException: AS2 site <AS2-sitename> is not used for sending in any subscription.

This is a direct consequence of the design of the Advanced Routing. However, this behavior can be fixed using special scenarios in which you can combine AR with other applications to achieve AS2 transfers when asynchronous MDN receipts are required.

-   Scenario 1: Combine AR with Basic application (outbound transfers only)
-   Scenario 2: Combine AR with two Basic application instances (one for inbound and one for outbound transfers)
-   Scenario 3: Combine AR with both SiteMailbox application (for both inbound and outbound transfers)

## Scenario 1: Combine AR and Basic application for outbound transfers

This approach uses a combination of an Advanced Routing instance and one Subscription to the Basic Application. Configure Advanced Routing to receive files and send them to an AS2 Site. A dummy Basic Application will be added (and subscribed to a different folder) to facilitate correct MDN processing for outbound transfers in AR. In essence, the Advanced Routing application will be used to send the files, while the Basic Application will only be used for receiving the asynchronous MDN receipts.

### Setup specifics

With this setup, you must configure:

-   One AS2 Transfer Site (in the user account).
-   An Advanced Routing instance with a Route that uses an AS2 Transfer Site to send the files in a Send To Partner step. In the subscription to this application, you must set that AS2 Transfer Site in the **Automatically retrieve files from** option. The Subscription must use a dedicated Subscription folder.
-   A Basic application with a the subscription that contains the following settings: **Send files directly to** the same AS2 Transfer Site. The Subscription must use another Subscription folder (different from the one above).

> **Note:**
>
> Even though the AS2 Site is selected in the Send files directly to Subscription option, it is not practically used to send files.

### Use case

This setup is good <u>only</u> for outbound transfers with asynchronous AS2-MDN. If your partner sends you an AS2 message (i.e. a file) you will return it back to them as the Route will be triggered from the AR subscription. This problem can be avoided if the route in the subscription sends the file to an internal server instead of to the partner AS2 Transfer Site (in the Advanced Routing Send To Partner step). If you wish to be able to send files outbound with this use case, you need another Advanced Routing instance with a route that uses an AS2 Transfer Site to send the files in a Send To Partner step, but without specifying **Automatically retrieve files from** Subscription option.

## Scenario 2: Combine AR and Basic application for both inbound and outbound transfers

This approach is similar to the one from above with outbound transfers. This time you must also configure another Basic application for inbound transfers.

Basically, here you use Advanced Routing in one Subscription, and two (dummy) Subscriptions with Basic Application. Each of the three is subscribed to a separate folder once again. The AR is used to do the actual file transfers outbound, while one of the BA Subscriptions is used to receive the files, while the other one is taking care of receiving the asynchronous MDN receipts and "bridging the gap" between the MDN receipts and the Subscriptions.

### Setup specifics

With this setup, you must configure:

-   One AS2 Transfer Site (in the user account).
-   An Advanced Routing instance with a Route that uses an AS2 Transfer Site to send the files in a Send To Partner step. The Subscription must use a dedicated Subscription folder.
-   One "outbound" Basic application that uses the same AS2 Transfer Site. In the subscription to this application, you must set that AS2 Transfer Site in the **Send files directly to** option. The Subscription must use a second, different Subscription Folder.
-   One "inbound" Basic application, that uses the same AS2 Transfer Site. In the subscription to this application, you must set that AS2 Transfer Site in the **Automatically retrieve files from** option. The Subscription must use a third, different Subscription folder.

### Use case

This setup is good for both inbound and outbound transfers with asynchronous AS2-MDN.

## Scenario 3: Combine AR for outbound and SiteMail for inbound transfers

This approach combines the use of Advanced Routing with Site Mailbox application to achieve for both inbound and outbound transfers.

Basically, here you use Advanced Routing in one Subscription. A dummy Site Mailbox application will be added (and subscribed to a different folder) to facilitate correct MDN processing in AR. In essence, the Advanced Routing will be used to send files and the Site Mailbox application will only be receiving the files and the asynchronous MDN receipts.

### Setup specifics

-   One AS2 Transfer Site (in the user account).
-   An Advanced Routing instance with a Route that uses an AS2 Transfer Site to send the files in a Send To Partner step. The Subscription must use a dedicated Subscription folder.
-   A Site Mailbox application, that uses the same AS2 Transfer Site. In the subscription to this application, you must select that AS2 Transfer Site in both the **Send files directly to** and **Automatically receive files from** Subscription options. The Subscription must use a second, different Subscription Folder.

### Use case

This setup is good for both inbound and outbound transfers with asynchronous AS2-MDN.

 
