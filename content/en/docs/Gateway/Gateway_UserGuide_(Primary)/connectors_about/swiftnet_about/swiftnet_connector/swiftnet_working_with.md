{
    "title": "Working with Axway Gateway/SWIFTNet",
    "linkTitle": "Working with SWIFTNet",
    "weight": "280"
}{{< Gateway/componentlongname  >}}: Connectors

[Working with SWIFTNet on Gateway](#Working_with_SWIFTNET)

[Submitting a SWIFTNet Transfer Request](#Submitting_SWIFTNet_Transfer_Request)

[After the transfer](#After_transfer)

<span id="Working_with_SWIFTNET"></span>

## Working with SWIFTNet on Gateway

Before transferring files or messages using SWIFTNet you need to [configure Gateway and create various objects](../swiftnet_configuring).

After completing these tasks, you can:

-   Transfer a file – submit a Transfer Request to send a file to a business partner via SWIFTNet, optionally requesting a receipt
-   Transfer a message – exchange SWIFTNet messages with remote business partners
-   Transfer an Acknowledgment Message – generate and return receipts to the sending partner

<span id="Submitting_SWIFTNet_Transfer_Request"></span>

## Submitting a SWIFTNet Transfer Request

### Transferring a file (FileAct)

To execute a FileAct file transfer using Gateway, [create and submit a Transfer Request](../../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_(gui)).

### Transferring a message (InterAct)

You can send limited-length text messages to a remote partner. To transfer a SWIFTNet InterAct message using Gateway, create and submit a Transfer Request. Perform the following operations in the *New Transfer Request* window:

1.  In the **[General](../../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_(gui)/transfer_request_general_tab)** tab, go to the <span style="font-weight: bold;">Type</span> field and select <span style="font-weight: bold;">INTERACT</span>.  
    <span style="font-weight: bold;">Note:</span> This is equivalent to type MSG using command lines.
2.  Define the message in one of two ways:
    -   In the <span style="font-weight: bold;">[Attributes](../../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_(gui)/transfer_request_attributes_tab)</span> tab, go to the <span style="font-weight: bold;">File component</span> field and enter the name of the file containing the message
    -   In the <span style="font-weight: bold;">[SWIFTNet](../../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_(gui)/transfer_request_swiftnet_tab)</span> tab, in the **InterAct** sub-tab, select the option <span style="font-weight: bold;">Send text message</span> and enter the message in the frame below

### Transferring an Acknowledgement Message (FileAct)

Real Time mode only

After receiving a File transfer from a Remote Site, you may need to return an acknowledgement message to the sending machine. To do this, create a message text and associate it with the local ID of the received Transfer Request. You can enter the acknowledgement text directly in the acknowledgement transfer, or alternatively, associate a file containing the message text. You can pre-program the date and time when the acknowledgement message is to be sent.

<span id="After_transfer"></span>

## After the transfer

To check that transfers have been made successfully, or to help you analyze problems, you can view the Mailbox and the Log file.

### Using the Mailbox

For each SWIFTNet transfer you make using Gateway, Gateway records one or more transfer records in the Mailbox. The number of records depends on the message type (FileAct or InterAct) and the routing mode (real time or SnF).

<span id="SnF"></span>

### SnF Incoming Acknowledgment

Incoming acknowledgment (Delivery Notification) messages for Store-and-Forward transfers are stored in a separate mailbox entry with type RECEIPT. This refers both to Counter Party and Third Party (received for Y-Copy and T-Copy transfers) Store-and-Forward delivery notifications, and is now consistent with the current behavior for FileAct RealTime.

The following points should be considered in order to evaluate which areas may be affected:

-   Decision decision rules can be used on Store-and-Forward delivery notifications (receipts). This is an intended feature, however it means that pre- existing decision rules could be unexpectedly triggered for incoming Store-and-Forward delivery notifications (receipts).
-   Log entries for received Store-and-Forward receipts (e.g. received Store-and-Forward delivery notification from Counter Party with status Accepted) are associated with the RECEIPT mailbox entry (new behavior) instead of the original transfer mailbox entry (old behavior).
-   The Acknowledgement (Delivery Notification) message is stored in a separate file associated with the RECEIPT (see [SWIFTNet Proof Keeping](../../swiftnet_backup_sites/swiftnet_proof_keeping))

### Using the Log file

By default, Gateway generates traces of network activities that it records to the log file.

Related topics

[Configuring the <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>/SWIFTNet environment](../swiftnet_configuring)

[Working with File Transfer Requests](../../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_(gui))

[Working with Transfers (command line)](../../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_cli)

[Working with Acknowledgement Messages](../../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_ack_messages)

[Viewing and managing Mailbox contents](../../../../transfers_start_here/monitoring_transfers_start_here/viewing_and_managing_mailbox_contents_(gui))

[Working with Logs](../../../../transfers_start_here/monitoring_transfers_start_here/log_files/working_with_logs_(gui))

[SWIFTNet File and Message Copy](../../swiftnet_header_info/swiftnet_file_copy)

[SWIFTNet system recovery](../../swiftnet_sig_list/swiftnet_system_recovery)

<a href="#" class="selected">SWIFTNet-specific user exits</a>

[SWIFTNet (SNET) log messages](../../../../log_messages_about/swiftnet_messages_(snet))

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
