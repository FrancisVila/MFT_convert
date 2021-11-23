{
    "title": "PGP Encryption and Send To Partner",
    "linkTitle": "PGP Encryption and Send To Partner",
    "weight": "280"
}The following topics provide the overview, prerequisites, configuration steps, and flow of events for the PGP Encryption and Send To Partner use case:

-   [Overview](#Overview)
-   [Prerequisites](#Prerequi)
-   [Step to configure the flow](#Step)
-   [Flow of events](#Flow)

**Related topics:**

-   [PGP Decryption and Publish To Account](../c_st_pgp_decryption_publish_to_account)
-   [Line Ending and Publish To Account](../c_st_line_ending_publish_to_account)
-   [Compress and Send To Partner](../c_st_compress_send_to_partner)
-   [Decompress and Publish To Account](../c_st_decompress_publish_to_account)
-   [External Script and Publish To Account](../c_st_external_script_send_to_partnet)
-   [Send To Partner (PeSIT)](../c_st_send_to_partner_pesit)

<span id="Overview"></span>

## Overview

PGP encrypt each incoming file and route the file to a remote transfer site.

<span id="Prerequi"></span>

## Prerequisites

-   Create a Route Package Template. For Route Package Template creation details, refer to [Add Route Package Template](../../../c_st_configuration/t_st_manage_route_package_templates#Add).
-   Create an {{< SecureTransport/advancedrouting >}} application instance. For {{< SecureTransport/advancedrouting >}} application instance creation details, refer to [Create Advanced Routing application](../../../c_st_configuration/t_st_create_advanced_routing_application).
-   Create {{< SecureTransport/securetransportname >}} user account. For user account creation details, refer to [User accounts](../../../../accounts/useraccounts).
-   Create a remote transfer site.
    For remote transfer site creation details, refer to [Create a transfer site](../../../../accounts/transfersites/t_st_transfersites#Create).
-   Generate or import a Partner PGP key which is used for encryption. For instructions on generating or importing a partner PGP key, refer to [Manage login certificates](../../../../accounts/c_st_usercertificates/t_st_usercertificates#Generate)or [Manage login certificates](../../../../accounts/c_st_usercertificates/t_st_usercertificates#Import4).

<span id="Step"></span>

## Step to configure the flow

1.  Create and configure a subscription to the {{< SecureTransport/advancedrouting >}} application by navigating to the account’s *Subscriptions* tab and clicking the **Subscribe…** button. For {{< SecureTransport/advancedrouting >}} subscription configuration details, refer to [Subscribe to Advanced Routing application](../../../c_st_configuration/t_st_subscribe_advanced_routing_application).
    1.  Configure the subscription folder.
    2.  (Optional) Configure the rest of the settings.
    3.  Click **Add** when done.
2.  Navigate to the *Routes* menu of the created account and assign a new route package to the account by choosing the created Route Package Template and clicking the **Assign Route** button. For assigning a route configuration details, refer to [Assign Route Package Template](../../../c_st_configuration/t_st_assign_route_package_template).
3.  Assign a subscription to the new route package by selecting **Assign** in the *Subscriptions* pane and selecting the subscription created in Step 1.
4.  Create a new route by clicking the **New Route** button in the *Specific Settings* pane. For route configuration details, refer to [New Route](../../../c_st_configuration/t_st_manage_routes#New).
    1.  Configure the new route’s name and (optionally) description.
    2.  Add and configure a PGP Encryption step by selecting it from the *-- Select Step --* drop-down menu and clicking the **Add Step** button. For PGP Encryption configuration details, refer to [PGP Encryption](../../../c_st_route_step_transformations/t_st_pgp_encryption).
        1.  Select the **Encrypt only** option.
        2.  Configure an account from which to select PGP certificate for encryption (for example, the current account).
        3.  Select a PGP certificate for encryption from that account. PGP certificate can be specified by alias, EL or wild card symbols. If more that one certificate matches the pattern, the first one is used.
        4.  Click **Save** when done.

        <!-- -->

        1.  Add and configure a Send To Partner step by selecting it from the *-- Select Step --* drop-down menu and clicking the **Add Step** button. For Send To Partner configuration details, refer to [Send To Partner](../../../c_st_route_steps/t_st_send_to_partner).
            1.  Uncheck **Proceed with route execution on step failure**.
            2.  Select the account which contains the target transfer site (or select **Use current account**).
            3.  Select the transfer site from the selected account to send the file to.
            4.  Click **Save** when done.
5.  Save the route and the route package.

<span id="Flow"></span>

## Flow of events

1.  A file is uploaded via any protocol to the {{< SecureTransport/advancedrouting >}} subscription folder.
2.  The {{< SecureTransport/advancedrouting >}} application triggers route.
3.  The uploaded file is encrypted and sent to the remote transfer site.
