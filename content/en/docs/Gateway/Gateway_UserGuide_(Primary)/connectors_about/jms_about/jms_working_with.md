{
    "title": "Working with Axway Gateway/JMS",
    "linkTitle": "Working with JMS",
    "weight": "280"
}{{< Gateway/componentlongname  >}}: Connectors

[Working with JMS on your Gateway](#Working_with_JMS)

[Submitting a JMS Transfer Request](#Submitting_JMS_Transfer_Request)

[Receiving JMS messages](#Receiving_JMS_messages)

[Routing](#Routing)

[After the transfer](#After_transfer)

<span id="Working_with_JMS"></span>

## Working with JMS on your Gateway

Before transferring JMS messages you need to [configure Gateway and create various objects](../jms_configuring).

When you have completed these tasks, you can:

-   submit a Transfer Request to transfer a JMS message, optionally requesting a receipt
-   receive JMS messages from a JMS MOM

Gateway also enables you to route messages automatically to other users.

### Message properties

A JMS message can contain *properties*. Often, the message already contains certain properties. You can also add your own properties.

Gateway can test message properties to decide what action to take for a given message, for example for routing.

<span id="Submitting_JMS_Transfer_Request"></span>

## Submitting a JMS Transfer Request

### Transferring a message (from Gateway to JMS)

To execute a file transfer using Gateway, you create and submit a Transfer Request.

You can enter message properties in the Transfer Request object. Gateway adds these properties to the message.

### Model objects

Optionally, you can also create one or more Model objects. Models are useful when you need to repeatedly reuse the same information to accomplish a series of tasks. You also use the Model object for [Routing](#Routing).

You can enter message properties in the Model object. Gateway adds these properties to the message.

To help you complete the properties in the Model, first create a Property List.

### Simple transfer example using the GUI

The following example illustrates how to send a file. For full details, refer to the relevant sections of this documentation.

1.  [Create a New Transfer Request](../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_(gui)).
2.  In the **[General](../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_(gui)/transfer_request_general_tab)** tab, enter the following parameters:
    -   <span style="font-weight: bold;">Type</span> = TRANS
    -   <span style="font-weight: bold;">Mode</span> = Initiator
    -   <span style="font-weight: bold;">Direction</span> = Send
    -   <span style="font-weight: bold;">Destination alias</span> = &lt;Name of Remote Site that you have already created>

<!-- -->

1.  In the <span style="font-weight: bold;">[Attributes](../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_(gui)/transfer_request_attributes_tab)</span> tab, enter the following parameters:
    -   <span style="font-weight: bold;">File component</span> = &lt;name of file to send>

<!-- -->

1.  In the <span style="font-weight: bold;">[JMS](../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_(gui)/transfer_request_jms_tab)</span> tab, add your required Transfer properties.
2.  Click OK.

Gateway sends the file to the client defined in the Remote Site. The message arrives in the queue specified by the Remote Site.

In the [Mailbox](#Mailbox), you can view any properties that were added to the message.

### Simple transfer example using an online command

Alternatively, you can use the <span class="code" style="font-weight: bold;">peltrans</span> online command to send a JMS message. The following example transfers the file <span class="code">file.txt</span> via a Remote Site named <span class="code">jms\_out</span> which uses the JMS protocol in the OUT direction:

peltrans  -dest\_alias  jms\_out

          -appli  DEFAULT\_A

          -file\_component  $HOME/file.txt

          -property  "PropName1=PropValue1"

          -property  "PropName2=PropValue2"

<span id="Receiving_JMS_messages"></span>

## Receiving JMS messages

Gateway listens to the JMS queue and automatically transfers incoming JMS messages. (You do not need to create a Transfer Request object.)

You do not need to create a Model object if only one or very few messages are being received and the messages do not require routing. In this case, messages arrive at the local machine. The files are written to the incoming directory specified in the Remote Site (<span style="font-weight: bold;">Msg In directory</span>).

### Transfer attributes

You can view transfer details in the [Mailbox](#Mailbox). Here you can see message properties as well as the path and name of the file.

The file ID is unique - it is derived from the message ID. You can see header fields and properties (for example, type of message and time stamp) as well as any user-defined properties.

### Renaming Incoming JMS files

Incoming JMS files can be automatically renamed, if requested, through an application object selected using a property of the JMS message. To activate the renaming for incoming JMS files, you must update the configuration options <span class="code">jms\_rename\_files</span> and <span class="code">jms\_inbound\_appli\_property</span> in the command line as follows:

-   peluconf set -s monitor jms\_rename\_files 1  
    The default value is 0, which means no file renaming.

<!-- -->

-   peluconf set -s monitor jms\_inbound\_appli\_property %application\_name%  
    Sets the incoming message JMS property of string type that defines which application to use for file renaming.

The following transfer properties are accessible using symbolic variables for file renaming/moving:

-   x\_local\_ident
-   x\_date\_begin
-   x\_date\_end
-   x\_originator
-   x\_destination

JMS properties from the incoming message can also be used. To access a JMS property, the syntax <span class="code">&(x\_property\_\[JMS\_PROPERTY\_NAME\])</span> should be used.

### Routing received messages

For more realistic situations, when many messages are being received, you can test for message properties in a Decision Rule. Gateway examines the properties to determine what action to take with the message.

For example, you can route the message to another JMS client or transform the message in order to route it to a client using any other protocol supported by Gateway, such as EDIINT AS2.

<span id="Routing"></span>

## Routing

In Gateway, you automate routing by creating and managing Decision Rule objects. Via the Decision Rule, you define a set of conditions to match against the current transfer. For example:

-   Protocol used for the current transfer = JMS
-   Destination = Site A
-   Destination is not the same as the originating Site
-   and so on...

When all the Decision Rule conditions match those of the current transfer, Gateway applies the execution type specified for this Decision Rule to the transfer.

<span style="font-weight: bold;">Example:</span> to redirect an incoming transfer to a remote site, create a Decision Rule that applies a Model to the incoming transfer type. When Gateway detects an incoming transfer of the specified type, it applies the Model, which in turn deposits a new Transfer Request towards the desired site.

You can restrict routing to a limited set of transfers. For example, you could restrict the routing to a certain Site to transfers with the following characteristics:

-   Transfer type: TRANS
-   Transfer direction: IN
-   Transfer status: ENDED or ACKED

<span id="After_transfer"></span>

## After the transfer

To check that transfers have been made successfully, or to help you analyze problems, you can view the Mailbox and the Log file.

<span id="Mailbox"></span>

### Using the Mailbox

For each JMS transfer you make using Gateway, Gateway records a transfer record in the Mailbox.

To view the Mailbox:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Transfer Management</span> node.
2.  Click the <span style="font-weight: bold;">Transfers</span> node.

Gateway displays all currently stored Mailbox records.

1.  To obtain additional information about a Transfer Request, double-click the row representing the Transfer Request record.

### Using the Log file

By default, Gateway generates traces of transfer activities that it records to the log file.

Related topics

[About JMS](../)

[JMS connector](../jms_connector)

[About Models](../../../transfers_start_here/parameters_start_here/models_start_here)

[Configuring the Gateway/JMS environment](../jms_configuring)

[Working with File Transfer Requests](../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_(gui))

[Working with Property Lists](../../../transfers_start_here/parameters_start_here/models_start_here/managing_property_lists)

[Working with Rule Tables and Decision Rules](../../../managing_events_start_here/working_with_rule_tables_and_decision_rules(gui))

[Viewing and managing Mailbox contents](../../../transfers_start_here/monitoring_transfers_start_here/viewing_and_managing_mailbox_contents_(gui))

[Working with Logs](../../../transfers_start_here/monitoring_transfers_start_here/log_files/working_with_logs_(gui))

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
