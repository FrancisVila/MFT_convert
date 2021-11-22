{
    "title": "Decompress and Publish To Account",
    "linkTitle": "Decompress and Publish To Account",
    "weight": "300"
}The following topics provide the overview, prerequisites, configuration steps, and flow of events for the Decompress and Publish To Account use case:

-   <a href="#Overview" class="MCXref xref">Overview</a>
-   <a href="#Prerequi" class="MCXref xref">Prerequisites</a>
-   <a href="#Steps" class="MCXref xref">Steps to configure the flow</a>
-   <a href="#Flow" class="MCXref xref">Flow of events</a>

**Related topics:**

-   <a href="../c_st_pgp_decryption_publish_to_account" class="MCXref xref">PGP Decryption and Publish To Account</a>
-   <a href="../c_st_line_ending_publish_to_account" class="MCXref xref">Line Ending and Publish To Account</a>
-   <a href="../c_st_send_to_partner" class="MCXref xref">PGP Encryption and Send To Partner</a>
-   <a href="../c_st_compress_send_to_partner" class="MCXref xref">Compress and Send To Partner</a>
-   <a href="../c_st_external_script_send_to_partnet" class="MCXref xref">External Script and Publish To Account</a>
-   <a href="../c_st_send_to_partner_pesit" class="MCXref xref">Send To Partner (PeSIT)</a>

<span id="Overview"></span>

## Overview

Decompress incoming archives and publish the result files to the local account.

<span id="Prerequi"></span>

## Prerequisites

-   Create a Route Package Template. For instructions on creating a Route Package Template, refer to <a href="../../../c_st_configuration/t_st_manage_route_package_templates#Add" class="MCXref xref">Add Route Package Template</a>.
-   Create an {{< SecureTransport/advancedrouting >}} application instance. For instructions on creating an {{< SecureTransport/advancedrouting >}} application instance, refer to .
-   Create a {{< SecureTransport/securetransportname >}} user account. For instructions on creating an user account, refer to <a href="../../../../accounts/useraccounts" class="MCXref xref">User accounts</a>.

<span id="Steps"></span>

## Steps to configure the flow

1.  Create and configure a subscription to the {{< SecureTransport/advancedrouting >}} application by navigating to the account’s *Subscriptions* tab and clicking the **Subscribe…** button. For {{< SecureTransport/advancedrouting >}} subscription configuration details, refer to <a href="../../../c_st_configuration/t_st_subscribe_advanced_routing_application" class="MCXref xref">Subscribe to Advanced Routing application</a>.
    1.  Configure the subscription folder.
    2.  (Optional) Configure the rest of the settings.
    3.  Click **Add** when done.
2.  Navigate to the *Routes* tab of the created account and assign a new route package to the account by choosing the created Route Package Template and clicking the **Assign Route** button. For assigning a route configuration details, refer to <a href="../../../c_st_configuration/t_st_assign_route_package_template" class="MCXref xref">Assign Route Package Template</a>.
3.  Assign a subscription to the new route package by selecting **Assign** in the *Subscriptions* pane and selecting the subscription created in Step 1.
4.  Create a new route by clicking the **New Route** button in the *Specific Settings* pane. For route configuration details, refer to <a href="../../../c_st_configuration/t_st_manage_routes#New" class="MCXref xref">New Route</a>.
    1.  Configure the new route’s name and (optionally) description.
    2.  Add and configure a Decompress step by selecting it from the *-- Select Step --* drop-down menu and clicking the **Add Step** button. For Decompress configuration details, refer to <a href="../../../c_st_route_step_transformations/t_st_decompress" class="MCXref xref">Decompress</a>.
        1.  (Optional) Configure the available options.

        2.  Click **Save** when done.

        3.  **Note:**
            >
            > The Decompress step automatically detects the archive type.
    3.  Add and configure a Publish to Account step by selecting it from the *-- Select Step --*drop-down menu and clicking the **Add Step** button. For Publish To Account configuration details, refer to <a href="../../../c_st_route_steps/t_st_publish_to_account" class="MCXref xref">Publish To Account</a>.
        1.  Uncheck **Proceed with route execution on step failure**.
        2.  Select an account to publish to (for example, the current account).
        3.  Select a folder to publish the file to (for example, the subscription folder configured in Step 1).
        4.  (Optional) Configure the rest of the settings.
        5.  Click **Save** when done.
5.  Save the route and the route package.

<span id="Flow"></span>

## Flow of events

1.  An archive is uploaded via any protocol to the {{< SecureTransport/advancedrouting >}} subscription folder.
2.  The {{< SecureTransport/advancedrouting >}} application triggers the route.
3.  The uploaded archive is decompressed and published to the specified folder.

> **Note:**
>
> In the end the subscription folder contains the archive file and the decompressed files. To automatically remove the archive file, select Post Processing Action &gt; On Success &gt; Delete in the subscription settings.

> **Note:**
>
> Publishing the decompressed files in Advanced Routing subscription folder does not trigger the route execution once again, because Trigger target subscription actions is unchecked.
