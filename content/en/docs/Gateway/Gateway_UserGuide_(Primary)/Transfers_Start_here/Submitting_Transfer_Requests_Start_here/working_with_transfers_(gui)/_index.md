{
    "title": "Transfer requests",
    "linkTitle": "Transfer Requests",
    "weight": "130"
}{{< Gateway/componentlongname  >}}: Managing Transfers

## Working with File Transfer Requests

[Submitting a Transfer Request](#Submitting_a_Transfer_Request)

[Managing records of Transfer Requests](#Managing_Transfer_Request_records)

This topic describes how to use the GUI to create and manage Transfer Requests for the exchange of files between Sites.

<span id="Submitting_a_Transfer_Request"></span>

### Submitting a Transfer Request

Before you submit a Transfer Request, you need to create various objects:

-   [Site objects](../../../managing_partners_start_here/sites_start_here), that are referenced by the Transfer object
-   (Optionally) [Application](../../parameters_start_here/applications_start_here), [Diffusion List](../../../managing_partners_start_here/diffusion_lists_start_here) and [Model](../../parameters_start_here/models_start_here) objects, that enable you to submit Transfer Requests more easily

To submit a new Transfer Request:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the **Transfer Management** node.
2.  Right-click <span style="font-weight: bold;">Transfers</span>, and then select <span style="font-weight: bold;">New > Transfer Request</span> from the context menu.  
    Gateway opens the <span style="font-style: italic;">New Transfer Request</span> window.
3.  Complete the tabs of this window according to your transfer requirements.  
    The following topics describe the fields in each tab and their possible values:
    -   [<span style="font-weight: bold;">General</span> tab](transfer_request_general_tab)
    -   [<span style="font-weight: bold;">Attributes</span> tab](transfer_request_attributes_tab)
    -   [<span style="font-weight: bold;">Details</span> tab](transfer_request_details_tab)
    -   [<span style="font-weight: bold;">PeSIT</span> tab](transfer_request_pesit_tab) (only for PeSIT)
    -   [<span style="font-weight: bold;">HTTP/FTP</span> tab](transfer_request_http_ftp_tab) (only for HTTP/FTP)
    -   [<span style="font-weight: bold;">SMTP</span> tab](transfer_request_smtp_tab) (only for SMTP)
    -   [<span style="font-weight: bold;">Trading Partner</span> tab](transfer_request_trading_partner_tab) (only for: S/MIME, EDIINT, RosettaNet)
    -   [<span style="font-weight: bold;">SWIFTNet</span> tab](transfer_request_swiftnet_tab) (only for SWIFTNet)
    -   [<span style="font-weight: bold;">JMS</span> tab](transfer_request_jms_tab) (only for JMS)
    -   [<span style="font-weight: bold;">OFTP</span> tab](transfer_request_oftp_tab) (only for OFTP)
    -   [<span style="font-weight: bold;">X420</span> tab](transfer_request_x420_tab) (only for X.400/X.420)

      
    For examples of sets of transfer parameter values, refer to [Transfer Examples](../../../transfer_examples).
4.  After completing the tabs, click <span style="font-weight: bold;">OK</span>.  
    Gateway begins processing the Transfer Request, and returns a Transfer Request identifier: <span style="font-style: italic;">local\_ident</span>. This number serves as a local identifier for your Transfer Request. You can use the <span style="font-style: italic;">local\_ident</span> number in the GUI or in certain command lines when you need to identify the Transfer Request.

<span id="Managing_Transfer_Request_records"></span>

### Managing records of Transfer Requests

Each time you submit a Transfer Request, Gateway assigns a local transfer ID number to the request and deposits a record of the Transfer Request to the Mailbox.

Use the Mailbox to monitor the status of transfers, gather information about successful and unsuccessful transfers and to re-initiate or abandon transfers according to your requirements.

To view Mailbox records of Transfer Requests:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Transfer Management</span> node.
2.  Click <span style="font-weight: bold;">Transfers</span>.  
    Gateway displays the Mailbox contents in the right pane.

Related topics

[Working with Transfers (command line)](../working_with_transfers_cli)

[Transfers: Parameters List](../working_with_transfers_cli/transfer_req_parameter_list)

[Viewing and managing Mailbox contents](../../monitoring_transfers_start_here/viewing_and_managing_mailbox_contents_(gui))

[Transfer Examples](../../../transfer_examples)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
