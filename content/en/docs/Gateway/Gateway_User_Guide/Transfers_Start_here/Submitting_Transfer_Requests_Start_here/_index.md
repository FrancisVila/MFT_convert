{
    "title": "Submitting transfers",
    "linkTitle": "Submitting transfers",
    "weight": "110"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Transfers

## About transfers

You can use Gateway to create three types of transfer:

### 1. File transfers

The principle activity of Gateway is to handle the exchange of files between Sites. To execute a file transfer from Gateway, you create and submit a Transfer Request.

### 2. Application message transfers

When Gateway is configured to use the PeSIT protocol, you can send limited-length messages to a Remote Site. To do this, use the Application Message transfer function. This function enables you to send a short text message.

### 3. Acknowledgement message transfers

After receiving a File transfer from a Remote Site, you may need to return an acknowledgement message to the sending machine. To do this, create a message text and associate it with the local ID of the received Transfer Request. You can enter the acknowledgement text directly in the acknowledgement transfer, or alternatively, associate a file containing the message text. You can pre-program the date and time when the acknowledgement message is to be sent.

Related topics

[Working with File Transfer Requests](working_with_transfers_(gui))

[Working with Application Messages](working_with_appli_messages)

[Working with Acknowledgement Messages](working_with_ack_messages)

[Working with Transfers (command line)](working_with_transfers_cli)

[Transfers: Parameters List](working_with_transfers_cli/transfer_req_parameter_list)

[Transfer icons](transfer_icons)

[Transfer states in Gateway](transfer_states)

[Overview: File Transfers and Transfer Requests](../../ov_gateway/ov_file_transfers)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
