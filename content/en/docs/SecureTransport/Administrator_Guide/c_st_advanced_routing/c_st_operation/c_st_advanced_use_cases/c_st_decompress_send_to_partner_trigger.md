{
    "title": "Decompress and Send to Partner (trigger file output)",
    "linkTitle": "Decompress and Send to Partner (trigger file output)",
    "weight": "290"
}The following topics provide the overview, prerequisites, configuration steps, and flow of events for the Decompress and Send To Partner with trigger file output use case:

-   <a href="#Overview" class="MCXref xref">Overview</a>
-   <a href="#Prerequi" class="MCXref xref">Prerequisites</a>
-   <a href="#Steps" class="MCXref xref">Steps to configure the flow:</a>
-   <a href="#Flow" class="MCXref xref">Flow of events</a>

<span id="Overview"></span>

## Overview

Decompress incoming archives, send the result files to two remote transfer sites and send a trigger file to one of them.

<span id="Prerequi"></span>

## Prerequisites

-   Create a Route Package Template. For Route Package Template creation details, refer to <a href="../../../c_st_configuration/t_st_manage_route_package_templates#Add" class="MCXref xref">Add Route Package Template</a>.
-   Create an <span class="mc-variable my_project_variables.Advanced_Routing variable">Advanced Routing</span> application instance. For <span class="mc-variable my_project_variables.Advanced_Routing variable">Advanced Routing</span> application instance creation details, refer to <a href="../../../c_st_configuration/t_st_create_advanced_routing_application" class="MCXref xref">Create Advanced Routing application</a>.
-   Create an <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> user account. For user account creation details, refer to <a href="../../../../accounts/useraccounts" class="MCXref xref">User accounts</a>.
-   Create remote transfer sites which are used as routing destinations (for example, **Partner 1 (FTP)** and **Partner 2 (HTTP)**).
    For remote transfer site creation details, refer to <a href="../../../../accounts/transfersites/t_st_transfersites#Create" class="MCXref xref">Create a transfer site</a>.

<span id="Steps"></span>

## Steps to configure the flow:

1.  Create and configure a subscription to the <span class="mc-variable my_project_variables.Advanced_Routing variable">Advanced Routing</span> application by navigating to the account’s *Subscriptions* tab and clicking the **Subscribe…** button. For <span class="mc-variable my_project_variables.Advanced_Routing variable">Advanced Routing</span> subscription configuration details, refer to <a href="../../../c_st_configuration/t_st_subscribe_advanced_routing_application" class="MCXref xref">Subscribe to Advanced Routing application</a>.
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
    3.  Add and configure a Send To Partner step by selecting it from the *-- Select Step --* drop-down menu and clicking the **Add Step** button. For Send To Partner configuration details, refer to <a href="../../../c_st_route_steps/t_st_send_to_partner" class="MCXref xref">Send To Partner</a>.
        1.  Uncheck **Proceed with route execution on step failure**.

        2.  Select the account which contains the target transfer sites (or select **Use current account**).

        3.  Select the transfer sites from the selected account to send the files to (for example, **Partner 1 (FTP)** and **Partner 2 (HTTP)**).

        4.  Select **Send trigger file**.

        5.  Specify trigger file name (for example, `${timestamp}.trigger`).

        6.  (Optional) Specify **Trigger file content** if the remote system expects trigger file with content.

        7.  **Note:**
            >
            > You can use the ${transferredfilenames} environment variable to specify the trigger file contents. This way the trigger file contains all files transferred by the step and each file is on a new line. The trigger file contains the original file names of the transferred files even if rename have been configured in the transfer site. \\r\\n (CRLF) is used as a line separator for the content of the trigger file.

        8.  Select an account and a transfer site to send the trigger file to. Usually these are the same as the ones configured in Step ii and Step iii.

        9.  Click **Save** when done.
5.  Save the route and the route package.

<span id="Flow"></span>

## Flow of events

1.  An archive file is uploaded to the <span class="mc-variable my_project_variables.Advanced_Routing variable">Advanced Routing</span> subscription folder. The archive contains two files named `text1.txt` and `text2.txt`.
2.  The <span class="mc-variable my_project_variables.Advanced_Routing variable">Advanced Routing</span> application is triggered and the archive is processed by the route.
3.  The archive is decompressed – `text1.txt` and `text2.txt` are the resulting files.
4.  The files are routed to the selected transfer sites (**Partner 1 (FTP)** and **Partner 2 (HTTP)**).
5.  A trigger file is generated with name `<current timestamp>.trigger` (for example, `1334851799648.trigger`) with contents:
    -   `text1.txt`
    -   `text2.txt`
6.  The trigger file is routed to **Partner 1 (FTP)** transfer site only.

**Related topics:**

-   <a href="../c_st_route_based_extension" class="MCXref xref">Route files based on file name extension</a>
-   <a href="../c_st_encryt_partner_certficate" class="MCXref xref">PGP Encryption (partner’s certificate) and send to multiple partners</a>
