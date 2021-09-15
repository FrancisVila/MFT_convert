{
    "title": "Compress and Send To Partner",
    "linkTitle": "Compress and Send To Partner",
    "weight": "300"
}The following topics provide the overview, prerequisites, configuration steps, and flow of events for the Compress and Send To Partner use case:

-   [Overview](#overview)
-   [Prerequisites](#prerequi)
-   [Steps to configure the flow](#steps)
-   [Flow of events](#flow)

**Related topics:**

-   [PGP Decryption and Publish To Account](../c_st_pgp_decryption_publish_to_account)
-   [Line Ending and Publish To Account](../c_st_line_ending_publish_to_account)
-   [PGP Encryption and Send To Partner](../c_st_send_to_partner)
-   [Decompress and Publish To Account](../c_st_decompress_publish_to_account)
-   [External Script and Publish To Account](../c_st_external_script_send_to_partnet)
-   [Send To Partner (PeSIT)](../c_st_send_to_partner_pesit)

## <span id="Overview"></span>Overview

Compress multiple incoming files and route the archive to a remote transfer site.

## <span id="Prerequi"></span>Prerequisites

-   Create a Route Package Template. For Route Package Template creation details, refer to [Add Route Package Template](../../../c_st_configuration/t_st_manage_route_package_templates).
-   Create an Advanced Routing application instance. For Advanced Routing application instance creation details, refer to [Create Advanced Routing application](../../../c_st_configuration/t_st_create_advanced_routing_application).
-   Create a SecureTransport user account. For user account creation details, refer to [User accounts](../../../../accounts/useraccounts).
-   Create a remote transfer site.
    For remote transfer site creation details, refer to [Create a transfer site](../../../../accounts/transfersites/t_st_transfersites).

## <span id="Steps"></span>Steps to configure the flow

1.  Create and configure a subscription to the Advanced Routing application by navigating to the account’s *Subscriptions* tab and clicking the **Subscribe…** button. For Advanced Routing subscription configuration details, refer to [Subscribe to Advanced Routing application](../../../c_st_configuration/t_st_subscribe_advanced_routing_application).
    1.  Configure the subscription folder.
    2.  To await multiple files, configure a condition (for example, trigger file) on which to submit the files to the route.
    3.  (Optional) Configure the rest of the settings.
    4.  Click **Add** when done.
2.  Navigate to the *Routes* tab of the created account and assign a new route package to the account by choosing the created Route Package Template and clicking the **Assign Route** button. For assigning a route configuration details, refer to [Assign Route Package Template](../../../c_st_configuration/t_st_assign_route_package_template).
3.  Assign a subscription to the new route package by selecting **Assign** in the *Subscriptions* pane and selecting the subscription created in Step 1.
4.  Create a new route by clicking the **New Route** button in the *Specific Settings* pane. For route configuration details, refer to [New Route](../../../c_st_configuration/t_st_manage_routes).
    1.  Configure the new route’s name and (optionally) description.
    2.  Add and configure a Compress step by selecting it from the *-- Select Step --* drop-down menu and clicking the **Add Step** button. For Compress configuration details, refer to [Compress](../../../c_st_route_step_transformations/t_st_compress).
        1.  Choose name for the archive (for example, `archive-${timestamp}.zip`).
        2.  (Optional) Configure the rest of the settings.
        3.  Click **Save** when done.
    3.  Add and configure a Send To Partner step by selecting it from the *-- Select Step --* drop-down menu and clicking the **Add Step** button. For Send To Partner configuration details, refer to [Send To Partner](../../../c_st_route_steps/t_st_send_to_partner).
        1.  Uncheck **Proceed with route execution on step failure**.
        2.  Select the account which contains the target transfer site (or select **Use current account**).
        3.  Select the transfer site from the selected account to send the file to.
        4.  Click **Save** when done.
5.  Save the route and the route package.

## <span id="Flow"></span>Flow of events

1.  Multiple files are uploaded via any protocol to the Advanced Routing subscription folder.
2.  The trigger file (file with `.trigger` extension) is uploaded to the subscription folder.
3.  The Advanced Routing application triggers the route.
4.  The uploaded files are compressed into single zip archive and sent to the remote transfer site.
