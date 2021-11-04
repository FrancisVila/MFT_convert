{
    "title": "PGP Encryption (partner/u2019s certificate) and send to multiple partners",
    "linkTitle": "PGP encryption (partner/u2019s certificate), and send to multiple partners",
    "weight": "280"
}The following topics provide the overview, prerequisites, configuration steps, and flow of events for the PGP Encryption and send to multiple partners use case:

-   <a href="#Overview" class="MCXref xref">Overview</a>
-   <a href="#Prerequi" class="MCXref xref">Prerequisites</a>
-   <a href="#Steps" class="MCXref xref">Steps to configure the flow</a>
-   <a href="#Flow" class="MCXref xref">Flow of events</a>

<span id="Overview"></span>

## Overview

Pull files from multiple sources and route the incoming files to multiple partners after PGP encrypting the files with the partner’s PGP certificate.

<span id="Prerequi"></span>

## Prerequisites

-   Create an <span class="mc-variable my_project_variables.Advanced_Routing variable">Advanced Routing</span> application instance. For <span class="mc-variable my_project_variables.Advanced_Routing variable">Advanced Routing</span> application instance creation details, refer to <a href="../../../c_st_configuration/t_st_create_advanced_routing_application" class="MCXref xref">Create Advanced Routing application</a>.
-   Create two partner accounts (for example, accounts with names **partner1** and **partner2**). For user account creation details, refer to <a href="../../../../accounts/useraccounts" class="MCXref xref">User accounts</a>.
    -   Create transfer site in each account to be used as a routing destination to the respective partner.

    -   **Note:**
        >
        > Modify the access level of the transfer sites to be Public, so these transfer sites can be used in routes defined outside of this account.

    -   Generate or import a partner PGP certificate in each account that is used for encrypting the files before routing them to the partner

    -   **Note:**
        >
        > Modify the access level of the certificates to be Public, so these certificates can be used in routes defined outside of this account.
-   Create two local accounts (for example, accounts with name **local1** and **local2**) and transfer sites (for example, named **target1** and **target2**) which are used as source for pulling. For user account creation details, refer to <a href="../../../../accounts/useraccounts" class="MCXref xref">User accounts</a>.

<span id="Steps"></span>

## Steps to configure the flow

1.  Create a Route Package Template by navigating to **Routes** and clicking **New Route Package Template**. For Route Package Template creation details, refer to <a href="../../../c_st_configuration/t_st_manage_route_package_templates#Add" class="MCXref xref">Add Route Package Template</a>.
    1.  Configure the new Route Package Template’s name and (optionally) description.
    2.  Create a new route by clicking the **New Route** button. For route configuration details, refer to <a href="../../../c_st_configuration/t_st_manage_routes#New" class="MCXref xref">New Route</a>.
        1.  Configure the new route’s name (for example, **Partner 1**) and (optionally) description.
        2.  Add and configure a PGP Encryption step by selecting it from the *-- Select Step --* drop-down menu and clicking the **Add Step** button. For PGP Encryption configuration details, refer to <a href="../../../c_st_route_step_transformations/t_st_pgp_encryption" class="MCXref xref">PGP Encryption</a>.
            1.  Select the **Encrypt only** option.
            2.  Select the first partner account.
            3.  Select the PGP certificate for encryption from that account.
            4.  Click **Save** when done.
        3.  Add and configure a Send To Partner step by selecting it from the *-- Select Step --* drop-down menu and clicking the **Add Step** button. For Send To Partner configuration details, refer to <a href="../../../c_st_route_steps/t_st_send_to_partner" class="MCXref xref">Send To Partner</a>.
            1.  Uncheck **Proceed with route execution on step failure**.
            2.  Select the first partner account which contains the target transfer site.
            3.  Select the transfer site from the selected account to send the file to.
            4.  Click **Save** when done.
    3.  Save the route and create a new one by clicking the **New Route** button.
        1.  Configure the new route’s name (for example, **Partner 2**) and (optionally) description.
        2.  Add and configure a PGP Encryption step by selecting it from the *-- Select Step --* drop-down menu and clicking the **Add Step** button.
            1.  Select the **Encrypt only** option.
            2.  Select the second partner account.
            3.  Select the PGP certificate for encryption from that account.
            4.  Click **Save** when done.
        3.  Add and configure a Send To Partner step by selecting it from the *-- Select Step --* drop-down menu and clicking the **Add Step** button.
            1.  Uncheck **Proceed with route execution on step failure**.
            2.  Select the second partner account which contains the target transfer site.
            3.  Select the transfer site from the selected account to send the file to.
            4.  Click **Save** when done.
    4.  Save the Route Package Template.
2.  Go to the first local account (**local1**) and create and configure a subscription to the <span class="mc-variable my_project_variables.Advanced_Routing variable">Advanced Routing</span> application by navigating to the account’s *Subscriptions* tab and clicking the **Subscribe…** button. For <span class="mc-variable my_project_variables.Advanced_Routing variable">Advanced Routing</span> subscription configuration details, refer to <a href="../../../c_st_configuration/t_st_subscribe_advanced_routing_application" class="MCXref xref">Subscribe to Advanced Routing application</a>.
    1.  Configure the subscription folder.
    2.  Select **Automatically Retrieve Files From** checkbox and choose the transfer site to pull files from (the one created as a prerequisite).
    3.  Configure a schedule for pulling the files.
    4.  (Optional) Configure the rest of the settings.
    5.  Click **Add** when done.
3.  Navigate to the *Routes* tab of the same account and assign a new route package to the account by choosing the Route Package Template created in Step 1 and clicking the **Assign Route** button.
    1.  Configure the new route package’s name and (optionally) description.

    2.  Assign a subscription to the new route package by selecting **Assign** in the *Subscriptions* pane and selecting the subscription created in Step 2.

    3.  Click **Save** when done.

    4.  **Note:**
        >
        > There’s no need to create routes within the route package as the routes inherited from the Route Package Template are sufficient for the current use case.
4.  Go to the second local account (**local2**) and create and configure a subscription to the <span class="mc-variable my_project_variables.Advanced_Routing variable">Advanced Routing</span> application by navigating to the account’s *Subscriptions* tab and clicking the **Subscribe…** button.
    1.  Configure the subscription folder.
    2.  Select **Automatically Retrieve Files From** checkbox and choose the transfer site to pull files from (the one created as a prerequisite).
    3.  Configure a schedule for pulling the files.
    4.  (Optional) Configure the rest of the settings.
    5.  Click **Add** when done.
5.  Navigate to the *Routes* tab of the same account and assign a new route package to the account by choosing the route template package created in Step 1 and clicking the **Assign Route** button.
    1.  Configure the new route package’s name and (optionally) description.

    2.  Assign a subscription to the new route package by selecting **Assign** in the *Subscriptions* pane and selecting the subscription created in Step 2.

    3.  Click **Save** when done.

    4.  **Note:**
        >
        > There’s no need to create routes within the route package as the routes inherited from the Route Package Template are sufficient for the current use case.

<span id="Flow"></span>

## Flow of events

1.  A scheduled SIT pull is triggered as configured in account **local1’s** subscription.
2.  The files from the remote site are downloaded in the local subscription folder and the <span class="mc-variable my_project_variables.Advanced_Routing variable">Advanced Routing</span> application is triggered.
3.  Files are processed by the two routes configured in the Route Package Template:
    -   The first route PGP encrypts the file with the certificate imported in **partner1** account and routes the file to **partner1**.
    -   The second route PGP encrypts the file with the certificate imported in **partner2** account and routes the file to **partner2**.
4.  A scheduled SIT pull is triggered as configured in account **local2's** subscription.
5.  The files from the remote site are downloaded in the local subscription folder and the <span class="mc-variable my_project_variables.Advanced_Routing variable">Advanced Routing</span> application is triggered.
6.  Files are processed by the two routes configured in the Route Package Template:
    -   The first route PGP encrypts the file with the certificate imported in **partner1** account and routes the file to **partner1**.
    -   The second route PGP encrypts the file with the certificate imported in **partner2** account and routes the file to **partner2**.

**Related topics:**

-   <a href="../c_st_route_based_extension" class="MCXref xref">Route files based on file name extension</a>
-   <a href="../c_st_decompress_send_to_partner_trigger" class="MCXref xref">Decompress and Send to Partner (trigger file output)</a>