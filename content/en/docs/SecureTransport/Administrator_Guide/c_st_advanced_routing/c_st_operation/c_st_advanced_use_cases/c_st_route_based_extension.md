{
    "title": "Route files based on file name extension",
    "linkTitle": "Route files based on file name extension",
    "weight": "270"
}The following topics provide the overview, prerequisites, configuration steps, and flow of events for the route files based on file name extension use case:

-   [Overview](#Overview)
-   [Prerequisites](#Prerequi)
-   [Step to configure the flow](#Step)
-   [Flow of events](#Flow)

<span id="Overview"></span>

## Overview

Identify the Routing Destination based on filename following the convention `<routing-destination>_<filename>`. The custom Expression Language function `extract(‘some_string’, '_', 2)` is utilized since it splits the given string to tokens based on a delimiter.

<span id="Prerequi"></span>

## Prerequisites

-   Create a Route Package Template. For Route Package Template creation details, refer to [Add Route Package Template](../../../c_st_configuration/t_st_manage_route_package_templates#Add).
-   Create an {{< SecureTransport/advancedrouting >}} application instance. For {{< SecureTransport/advancedrouting >}} application instance creation details, refer to [Create Advanced Routing application](../../../c_st_configuration/t_st_create_advanced_routing_application).
-   Create a {{< SecureTransport/securetransportname >}} user account. For user account creation details, refer to [User accounts](../../../../accounts/useraccounts).
-   Create two remote transfer sites (for example, named **partner1** and **partner2**) which are used as routing destinations.
    For remote transfer site creation details, refer to [Create a transfer site](../../../../accounts/transfersites/t_st_transfersites#Create).

<span id="Step"></span>

## Step to configure the flow

1.  Create and configure a subscription to the {{< SecureTransport/advancedrouting >}} application by navigating to the account’s *Subscriptions* tab and clicking the **Subscribe…** button. For {{< SecureTransport/advancedrouting >}} subscription configuration details, refer to [Subscribe to Advanced Routing application](../../../c_st_configuration/t_st_subscribe_advanced_routing_application).
    1.  Configure the subscription folder.
    2.  (Optional) Configure the rest of the settings.
    3.  Click **Add** when done.
2.  Navigate to the *Routes* tab of the created account and assign a new route package to the account by choosing the created Route Package Template and clicking the **Assign Route** button. For assigning a route configuration details, refer to [Assign Route Package Template](../../../c_st_configuration/t_st_assign_route_package_template).
3.  Assign a subscription to the new route package by selecting **Assign** in the *Subscriptions* pane and selecting the subscription created in Step 1.
4.  Configure the *Execution Rule* of the route package to be **First Matching Route**.
5.  Create a new route by clicking the **New Route** button in the *Specific Settings* pane. For route configuration details, refer to [New Route](../../../c_st_configuration/t_st_manage_routes#New).
    1.  Configure the new route’s name (for example, **Partner 1**) and (optionally) description.
    2.  Configure the *Route Condition* to be **Expression Language** and enter the following in the expression field:
    3.  `${extract(basename(transfer.target),'_',1)  eq 'partner1'}`
    4.  Add and configure a Send To Partner step by selecting it from the *-- Select Step --* drop-down menu and clicking the **Add Step** button. For Send To Partner configuration details, refer to [Send To Partner](../../../c_st_route_steps/t_st_send_to_partner).
        1.  Select the account which contains the target transfer site (or select **Use current account**).
        2.  Select the transfer site from the selected account to send the file to (for example, **partner1**).
        3.  Select **Route file as** and enter the following expression:
        4.  `${extract(basename(transfer.target),'_',1)}`
        5.  This expression extracts the *&lt;routing-destination>* from the filename (for example, `partner1_incoming.txt` returns `partner1`).
        6.  Click **Save** when done.
6.  Create another route by clicking the **New Route** button in the *Specific Settings* pane.
    1.  Configure the new route’s name (for example **Partner 2**) and (optionally) description.
    2.  Configure the *Route Condition* to be **Expression Language** and enter the following in the expression field:
    3.  `${extract(basename(transfer.target),'_',1)  eq 'partner2'}`
    4.  Add and configure a Send To Partner step by selecting it from the *-- Select Step --* drop-down menu and clicking the **Add Step** button.
        1.  Select the account which contains the target transfer site (or select **Use current account**).
        2.  Select the transfer site from the selected account to send the file to (for example, **partner2**).
        3.  Select Route file as and enter the following expression:
        4.  `${extract(basename(transfer.target),'_',2)}`
        5.  This expression extracts the *&lt;filename>* from the filename (for example, `partner2_incoming.txt` returns `incoming`).
        6.  Click **Save** when done.
7.  Save the route package.

<span id="Flow"></span>

## Flow of events

1.  A file named `partner1_filename.txt` is uploaded to the {{< SecureTransport/advancedrouting >}} subscription folder.
2.  {{< SecureTransport/advancedrouting >}} application is triggered and `partner1` is extracted from the filename.
3.  Route **Partner 1** is triggered. Route **Partner 2** is skipped.
4.  File is routed to the transfer site **partner1**.
5.  A file named `partner2_filename.txt` is uploaded to the {{< SecureTransport/advancedrouting >}} subscription folder.
6.  The {{< SecureTransport/advancedrouting >}} application is triggered and `partner2` is extracted from the filename.
7.  Route **Partner 1** is skipped. Route **Partner 2** is triggered.
8.  File is routed to the transfer site **partner2**.

**Related topics:**

-   [PGP Encryption (partner’s certificate) and send to multiple partners](../c_st_encryt_partner_certficate)
-   [Decompress and Send to Partner (trigger file output)](../c_st_decompress_send_to_partner_trigger)
