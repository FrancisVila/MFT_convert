{
    "title": "Decompress and Publish To Account",
    "linkTitle": "Decompress and Publish To Account",
    "weight": "310"
}The following topics provide the overview, prerequisites, configuration steps, and flow of events for the Decompress and Publish To Account use case:

-   [Overview](#overview)
-   [Prerequisites](#prerequi)
-   [Steps to configure the flow](#steps)
-   [Flow of events](#flow)

**Related topics:**

-   [PGP Decryption and Publish To Account](../c_st_pgp_decryption_publish_to_account)
-   [Line Ending and Publish To Account](../c_st_line_ending_publish_to_account)
-   [PGP Encryption and Send To Partner](../c_st_send_to_partner)
-   [Compress and Send To Partner](../c_st_compress_send_to_partner)
-   [External Script and Publish To Account](../c_st_external_script_send_to_partnet)
-   [Send To Partner (PeSIT)](../c_st_send_to_partner_pesit)

## <span id="Overview"></span>Overview

Decompress incoming archives and publish the result files to the local account.

## <span id="Prerequi"></span>Prerequisites

-   Create a Route Package Template. For instructions on creating a Route Package Template, refer to [Add Route Package Template](../../../c_st_configuration/t_st_manage_route_package_templates).
-   Create an Advanced Routing application instance. For instructions on creating an Advanced Routing application instance, refer to .
-   Create a SecureTransport user account. For instructions on creating an user account, refer to [User accounts](../../../../accounts/useraccounts).

## <span id="Steps"></span>Steps to configure the flow

1.  Create and configure a subscription to the Advanced Routing application by navigating to the account’s *Subscriptions* tab and clicking the **Subscribe…** button. For Advanced Routing subscription configuration details, refer to [Subscribe to Advanced Routing application](../../../c_st_configuration/t_st_subscribe_advanced_routing_application).
    1.  Configure the subscription folder.
    2.  (Optional) Configure the rest of the settings.
    3.  Click **Add** when done.
2.  Navigate to the *Routes* tab of the created account and assign a new route package to the account by choosing the created Route Package Template and clicking the **Assign Route** button. For assigning a route configuration details, refer to [Assign Route Package Template](../../../c_st_configuration/t_st_assign_route_package_template).
3.  Assign a subscription to the new route package by selecting **Assign** in the *Subscriptions* pane and selecting the subscription created in Step 1.
4.  Create a new route by clicking the **New Route** button in the *Specific Settings* pane. For route configuration details, refer to [New Route](../../../c_st_configuration/t_st_manage_routes).
    1.  Configure the new route’s name and (optionally) description.
    2.  Add and configure a Decompress step by selecting it from the *-- Select Step --* drop-down menu and clicking the **Add Step** button. For Decompress configuration details, refer to [Decompress](../../../c_st_route_step_transformations/t_st_decompress).
        1.  (Optional) Configure the available options.

        2.  Click **Save** when done.

        3.  <table cellpadding="0" cellspacing="0">   <col/>   <col/>   <col/>      <tr>         <td valign="top">         </td>         <td valign="top"><span><b>Note</b></span>         </td>         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The Decompress step automatically detects the archive type.         </td>      </tr></table>
    3.  Add and configure a Publish to Account step by selecting it from the *-- Select Step --*drop-down menu and clicking the **Add Step** button. For Publish To Account configuration details, refer to [Publish To Account](../../../c_st_route_steps/t_st_publish_to_account).
        1.  Uncheck **Proceed with route execution on step failure**.
        2.  Select an account to publish to (for example, the current account).
        3.  Select a folder to publish the file to (for example, the subscription folder configured in Step 1).
        4.  (Optional) Configure the rest of the settings.
        5.  Click **Save** when done.
5.  Save the route and the route package.

## <span id="Flow"></span>Flow of events

1.  An archive is uploaded via any protocol to the Advanced Routing subscription folder.
2.  The Advanced Routing application triggers the route.
3.  The uploaded archive is decompressed and published to the specified folder.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">In the end the subscription folder contains the archive file and the decompressed files. To automatically remove the archive file, select <strong>Post Processing Action &gt; On Success &gt; Delete</strong> in the subscription settings.         </td>
      </tr>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Publishing the decompressed files in <span>Advanced Routing</span> subscription folder does not trigger the route execution once again, because <em>Trigger target subscription actions</em> is <strong>unchecked</strong>.         </td>
      </tr>
</table>
