{
    "title": "Line Ending and Publish To Account ",
    "linkTitle": "Line Ending and Publish To Account ",
    "weight": "280"
}The following topics provide the overview, prerequisites, configuration steps, and flow of events for the Line Ending and Publish To Account use case:

-   [Overview](#overview)
-   [Prerequisites](#prerequi)
-   [Step to configure the flow](#step)
-   [Flow of events](#flow)

**Related topics:**

-   [PGP Decryption and Publish To Account](../c_st_pgp_decryption_publish_to_account)
-   [PGP Encryption and Send To Partner](../c_st_send_to_partner)
-   [Compress and Send To Partner](../c_st_compress_send_to_partner)
-   [Decompress and Publish To Account](../c_st_decompress_publish_to_account)
-   [External Script and Publish To Account](../c_st_external_script_send_to_partnet)
-   [Send To Partner (PeSIT)](../c_st_send_to_partner_pesit)

## <span id="Overview"></span>Overview

Transform end-of-line characters of each incoming file and publish the file to the local account.

## <span id="Prerequi"></span>Prerequisites

-   Create a Route Package Template. For Route Package Template creation details, refer to [Add Route Package Template](../../../c_st_configuration/t_st_manage_route_package_templates).
-   Create an Advanced Routing application instance. For Advanced Routing application instance creation details, refer to [Create Advanced Routing application](../../../c_st_configuration/t_st_create_advanced_routing_application).
-   Create a SecureTransport user account. For user account creation details, refer to [User accounts](../../../../accounts/useraccounts).

 

## <span id="Step"></span>Step to configure the flow

1.  Create and configure a subscription to the Advanced Routing application by navigating to the account’s *Subscriptions* tab and clicking the **Subscribe…** button. For Advanced Routing subscription configuration details, refer to [Subscribe to Advanced Routing application](../../../c_st_configuration/t_st_subscribe_advanced_routing_application).
    1.  Configure the subscription folder.
    2.  (Optional) Configure the rest of the settings.
    3.  Click **Add** when done.
2.  Navigate to the *Routes* tab of the created account and assign a new route package to the account by choosing the created Route Package Template and clicking the **Assign Route** button. For assigning a route configuration details, refer to [Assign Route Package Template](../../../c_st_configuration/t_st_assign_route_package_template).
3.  Assign the subscription to the new route package by selecting **Assign** in the *Subscriptions* pane and selecting the subscription created in Step 1.
4.  Create a new route by clicking the **New Route** button in the *Specific Settings* pane. For route configuration details, refer to [New Route](../../../c_st_configuration/t_st_manage_routes).
    1.  Configure the new route’s name and (optionally) description.
    2.  Add and configure a Line Ending step by selecting it from the *-- Select Step --* drop-down menu and clicking the **Add Step** button. For Line Ending configuration details, refer to [Line Ending](../../../c_st_route_step_transformations/t_st_line_ending).
        1.  Select the source line ending format (for example, **Custom -> \\u0025** for Mainframe end-of-line characters).
        2.  Select source file encoding (for example, **X-ORACLE-WE8EBCDIC500**).
        3.  Select target line ending format (for example, **Linux(LF)**).
        4.  Select target file encoding (for example, **US-ASCII**).
        5.  (Optional) Configure the rest of the options.
        6.  Click **Save** when done.
    3.  Add and configure a Publish to Account step by selecting it from the *-- Select Step --* drop-down menu and clicking the **Add Step** button. For Publish To Account configuration details, refer to [Publish To Account](../../../c_st_route_steps/t_st_publish_to_account).
        1.  Uncheck **Proceed with route execution on step failure**.
        2.  Select an account to publish to (for example, the current account).
        3.  Select a folder to publish the file to (for example, the subscription folder configured in Step 1).
        4.  Enter the following expression in the *Publish file as* field:
        5.  `${basename(transfer.target)}.us-ascii${extension(transfer.target)}`
        6.  This expression transforms the original file name by adding `.us-ascii` before the filename extension. For example, for file `incoming.txt` the result is `incoming.us-ascii.txt`.
        7.  (Optional) Configure the rest of the settings.
        8.  Click **Save** when done.
5.  Save the route and the route package.

## <span id="Flow"></span>Flow of events

1.  A file with **\\u0025** end-of-line character and **WE8EBCDIC500** file encoding is uploaded via any protocol to the Advanced Routing subscription folder.
2.  The Advanced Routing application triggers the route.
3.  The uploaded file’s end-of-line character is changed to **LF** and the file’s encoding is changed to **US-ASCII**.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">In the end there are two files present – the incoming (original) file and transformed file. To automatically remove the incoming file, select <strong>Post Processing Action -&gt; On Success -&gt; Delete</strong> in the subscription settings.         </td>
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
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Publishing the transcoded file in <span>Advanced Routing</span> subscription folder does not trigger the route execution once again, because <em>Trigger target subscription actions</em> is <strong>unchecked</strong>.         </td>
      </tr>
</table>
