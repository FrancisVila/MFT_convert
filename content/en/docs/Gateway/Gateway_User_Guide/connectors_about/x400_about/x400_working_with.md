{
    "title": "Working with X.400",
    "linkTitle": "Working with X.400",
    "weight": "300"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Connectors

[Working with X.400 on Gateway](#working_with_x400)

[Submitting an X.400 Transfer Request](#submitting_x400_transfer_request)

[After the transfer](#after_transfer)

This topic describes the parameters in Gateway that enable X.420 transfers.

<span id="working_with_x400"></span>

## Working with X.400 on Gateway

Before transferring messages using X.400 you need to [configure Gateway and create various objects](../x400_configuring).

After completing these tasks, you can:

-   Send X.400 messages to remote partners
-   Receive X.400 messages from remote partners

<span id="submitting_x400_transfer_request"></span>

## Submitting an X.400 Transfer Request

You can use any of the following methods to create an X.400 (X.420) Transfer Request:

-   [Create and submit a Transfer Request](../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_(gui)) using the Gateway GUI.
-   Use the <span class="code" style="font-weight: bold;">peltrans</span> online command to create a Transfer Request. Refer to [Additional Transfer Request parameters for X.400](../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_cli/transfer_req_parameter_list#x400_transfer_parameters) for a list of <span class="code" style="font-weight: bold;">peltrans</span> parameters specifically for X.420 transfers.
-   Use GikAPI commands. Refer to [C API Transfer and Selection parameters](../../../customizing_gw_about/c_api_about/c_api_trans_and_sel_paras#x400) for specific X.420 parameters.
-   Use Axway Integrator to initiate X.420 transfers (not described in this documentation)

<span id="after_transfer"></span>

## After the transfer

To check that transfers have been made successfully, or to help you analyze problems, you can view the Mailbox and the Log file.

### Using the Mailbox

For each X.400 transfer you make using Gateway, Gateway records a transfer record in the Mailbox.

### Using the Log file

By default, Gateway generates traces of network activities that it records to the log file.

Related topics

[Working with File Transfer Requests](../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_(gui))

[Working with Transfers (command line)](../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_cli)

[Viewing and managing Mailbox contents](../../../transfers_start_here/monitoring_transfers_start_here/viewing_and_managing_mailbox_contents_(gui))

[Working with Logs](../../../transfers_start_here/monitoring_transfers_start_here/log_files/working_with_logs_(gui))

[X.400 log messages](../../../log_messages_about/x400_messages)

[About X.400](../)

[X.400 connector](../x400_connector)

[Configuring Gateway for X.400](../x400_configuring)

[Managing X.400 partners](../x400_managing_partners)

[C API Transfer and Selection parameters](../../../customizing_gw_about/c_api_about/c_api_trans_and_sel_paras)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
