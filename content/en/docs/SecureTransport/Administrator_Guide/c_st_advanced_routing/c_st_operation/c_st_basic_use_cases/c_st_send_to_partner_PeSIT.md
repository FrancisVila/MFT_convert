{
    "title": "Send To Partner (PeSIT)",
    "linkTitle": "Send To Partner (PeSIT)",
    "weight": "320"
}The following topics provide the overview, prerequisites, configuration steps, and flow of events for the Send To Partner (PeSIT) use case:

-   [Overview](#Overview)
-   [Prerequisites](#Prerequi)
-   [Steps to configure the flow](#Steps)
-   [Flow of events](#Flow)

**Related topics:**

-   [PGP Decryption and Publish To Account](../c_st_pgp_decryption_publish_to_account)
-   [Line Ending and Publish To Account](../c_st_line_ending_publish_to_account)
-   [PGP Encryption and Send To Partner](../c_st_send_to_partner)
-   [Compress and Send To Partner](../c_st_compress_send_to_partner)
-   [Decompress and Publish To Account](../c_st_decompress_publish_to_account)
-   [External Script and Publish To Account](../c_st_external_script_send_to_partnet)

<span id="Overview"></span>

## Overview

Each incoming file is routed to a remote transfer site over PeSIT and the file is archived to a local folder.

<span id="Prerequi"></span>

## Prerequisites

-   Create a Route Package Template. For Route Package Template creation details, refer to [Add Route Package Template](../../../c_st_configuration/t_st_manage_route_package_templates#Add).
-   Create an {{< SecureTransport/advancedrouting >}} application instance. For {{< SecureTransport/advancedrouting >}} application instance creation details, refer to [Create Advanced Routing application](../../../c_st_configuration/t_st_create_advanced_routing_application).
-   Create a {{< SecureTransport/securetransportname >}} user account. For user account creation details, refer to [User accounts](../../../../accounts/useraccounts).
-   Create a PeSIT transfer site to route the file to. For PeSIT transfer site creation details, refer to [PeSIT transfer sites](../../../../accounts/transfersites/transfersites-pesit#Create).
-   Create a transfer profile that is used for the transfer. For transfer profile configuration details, refer to [Transfer profiles](../../../../accounts/t_st_transferprofiles).
-   Create a Folder Monitor transfer site that is used to archive the incoming files. For Folder Monitor transfer site configuration details, refer to [Folder Monitor transfer sites](../../../../accounts/transfersites/r_st_foldermonitortransfersites).

<span id="Steps"></span>

## Steps to configure the flow

1.  Create and configure a subscription to the {{< SecureTransport/advancedrouting >}} application by navigating to the account’s *Subscriptions* tab and clicking the **Subscribe…** button. For {{< SecureTransport/advancedrouting >}} subscription configuration details, refer to [Subscribe to Advanced Routing application](../../../c_st_configuration/t_st_subscribe_advanced_routing_application).
    1.  Uncheck **Proceed with route execution on step failure**.
    2.  Configure the subscription folder.
    3.  (Optional) Configure the rest of the settings.
    4.  Click **Add** when done.
2.  Navigate to the *Routes* tab of the created account and assign a new route package to the account by choosing the created Route Package Template and clicking the **Assign Route** button. For assigning a route configuration details, refer to [Assign Route Package Template](../../../c_st_configuration/t_st_assign_route_package_template).
3.  Assign a subscription to the new route package by selecting **Assign** in the *Subscriptions* pane and selecting the subscription created in Step 1.
4.  Create a new route by clicking the **New Route** button in the *Specific Settings* pane. For route configuration details, refer to [New Route](../../../c_st_configuration/t_st_manage_routes#New).
    1.  Configure the new route’s name and (optionally) description.
    2.  Add and configure a Send to Partner step by selecting it from the *-- Select Step --* drop-down menu and clicking the **Add Step** button. For Send To Partner configuration details, refer to [Send To Partner](../../../c_st_route_steps/t_st_send_to_partner).
        1.  Select the account which contains the target transfer site (or select **Use current account**).
        2.  Select the created PeSIT transfer site.
        3.  Select the created Transfer Profile.
        4.  Optionally, configure the **Advanced PeSIT Settings**. For example, to trigger Store and Forward:
            1.  Click the **Configure advanced PeSIT settings** checkbox.
            2.  Set the *Final Destination* field to the desired final destination.
        5.  (Optional) Configure the rest of the step’s settings.
        6.  Click **Save** when done.
    3.  Add and configure a Send To Partner step by selecting it from the *-- Select Step --* drop-down menu and clicking the **Add Step** button. For Send To Partner configuration details, refer to [Send To Partner](../../../c_st_route_steps/t_st_send_to_partner).
        1.  Select the account which contains the Folder Monitor transfer site (or select **Use current account**).
        2.  Select the Folder Monitor transfer site from the selected account.
        3.  Click **Save** when done.
5.  Save the route and the route package.

<span id="Flow"></span>

## Flow of events

1.  A file is uploaded via any protocol to the {{< SecureTransport/advancedrouting >}} subscription folder.
2.  The {{< SecureTransport/advancedrouting >}} application triggers route.
3.  The uploaded file is routed to the remote PeSIT transfer site and after that is archived to the folder specified in the Folder Monitor transfer site.

> **Note:**
>
> To compress the file before sending it to the archive folder, add a Compress step before the second Send To Partner step.
