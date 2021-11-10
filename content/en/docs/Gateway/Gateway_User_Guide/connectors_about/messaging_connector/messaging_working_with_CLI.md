{
    "title": "Linking Axway Gateway to Axway Messaging (command line)",
    "linkTitle": "Working with Messaging (command line)",
    "weight": "220"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Connectors

[How to link <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span> and Axway Messaging](#How_to_create_connector)

[Details of <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>/Axway Messaging link management commands](#Connector_managment_details)

[Creating an Axway Messaging connector](#Create_Messaging_connector)

[Creating an Axway Messaging connector Property List](#Create_proplist)

[Updating an Axway Messaging connector Property List](#Update_proplist)

[Deleting an Axway Messaging connector](#Delete_Messaging_connector)

[Displaying an Axway Messaging connector Property List](#Display_properties_list)

[Displaying all Axway Messaging connector Property Lists](#Select_properties_list)

<span id="How_to_create_connector"></span>

## How to link <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span> and Axway Messaging

You can create Gateway/Axway Messaging links that operate in either of two directions:

-   From an Axway Messaging server to Gateway (<span style="font-style: italic;">IN</span> connector)
-   From Gateway to an Axway Messaging server (<span style="font-style: italic;">OUT</span> connector)

<span id="Connecting_Messaging_to_Gtwy"></span>

### How to create a link from an Axway Messaging server to Gateway

To create a link from an Axway Messaging server to Gateway:

1.  Create a proplist (Property List) that describes the messages received from the Axway Messaging server. Use the <span class="code">peladm create\_proplist</span> command.

Example:

peladm create\_proplist -pl list1 -ap "xms\_ori:string;xms\_dest:string"

1.  Create a Model for Transfers to Gateway with the following characteristics:
    -   <span style="font-style: italic;">TO\_GTW</span> value for the protocol (-pr) attribute
    -   Specify a Property list in the <span class="code">prop\_list\_name (-pln)</span> attribute

Use the [peladm create\_model](../../../transfers_start_here/parameters_start_here/models_start_here/working_with_models_cli#peladm_create_model) command.

Example:

peladm create\_model -ml mod\_to\_gtw -pr TO\_GTW -pln list1 -oa "&(xms\_ori)" -da "&(xms\_dest)" -ty TRANS -dir O -m I -ap DEFAULT\_B

1.  Create an <span style="font-style: italic;">IN</span> type Axway Messaging connector. Use the <span class="code">peladm create\_xmsctor</span> command.

Example:

peladm create\_xmsctor -n xmsCtor1 -t IN -a Y -host mypc -p 4569 -i USER1 -pwd USER1 -rqn Q1 -mt MSG -rd c:\\temp\\recpXMS

1.  Create a Decision Rule with the following characteristics:
    -   <span style="font-style: italic;">XMS</span> value for type\_of\_decision rule type (-type) attribute
    -   <span style="font-style: italic;">MODEL</span> value for the <span class="code">execution\_type (-et)</span> attribute
    -   Specify an XMS-type Model for file routing via Gateway
    -   Specify a Property list in the <span class="code">prop\_list\_name (-pln)</span> attribute

Use the [peladm create\_decisionrule](../../../managing_events_start_here/working_with_decision_rules_cli#peladm_create_decisionrule) command.

Example:

peladm create\_decisionrule -n DT\_TO\_GTW -type XMS -pln list1 -ca "xms\_dest=SitDest" -et MODEL -ml mod\_to\_gtw

1.  Create an XMS-type Rule Table. Use the [peladm create\_ruletable](../../../managing_events_start_here/working_with_decision_rules_cli/working_with_rule_tables_cli#peladm_create_ruletable) command.

Example:

peladm create\_ruletable -n RT\_TO\_GTW -type XMS -pln list1 xcn xmsCtor1 -a "DR\_TO\_GTW"

<span id="Connecting_Gtwy_to_Messaging"></span>

### How to create a link from Gateway to an Axway Messaging server

To create a link from Gateway to an Axway Messaging server:

1.  Create a proplist (Property List) that describes the messages received from Gateway. Use the <span class="code" style="font-weight: bold;">peladm create\_proplist</span> command.

Example:

peladm create\_proplist -pl list1 -ap "xms\_ori:string;xms\_dest:string"

1.  Create a Model for Transfers to the Axway Messaging server.
    -   <span style="font-style: italic;">FROM\_GTW</span> value for the <span class="code">protocol (-pr)</span> attribute
    -   Specify a Property list in the <span class="code">prop\_list\_name (-pln)</span> attribute

Use the [peladm create\_model](../../../transfers_start_here/parameters_start_here/models_start_here/working_with_models_cli#peladm_create_model) command.

Example:

peladm create\_model -ml mod\_from\_gtw -pr FROM\_GTW -pln list1 -ma "xms\_ori=&(org\_alias); xms\_dest=&(dest\_alias); DestinationQmgr=QMGR412; DestiationQueue=FromGtw"

1.  Create an <span style="font-style: italic;">OUT</span> type Axway Messaging connector. Use the <span class="code">peladm create\_xmsctor</span> command.

Example:

peladm create\_xmsctor -n routeCtor1 -t OUT -a Y -hos mypc -p 4569 -i USER1 -pwd USER1

1.  Create an XMS-type Decision Rule, with the following characteristics:
    -   <span style="font-style: italic;">XFER\_CHANGE\_STATE</span> value for the type attribute
    -   <span style="font-style: italic;">TO\_XMS</span> value for the execution type (-et) value
    -   specifies an XMS-type Model for routing to an Axway Messaging message queue.

Use the [peladm create\_decisionrule](../../../managing_events_start_here/working_with_decision_rules_cli#peladm_create_decisionrule) command.

Example:

peladm create\_decisionrule -n DR\_FROM\_GTW -type XFER\_CHANGE\_STATE -xcn ROUTECTOR1 -et TO\_XMS -ml mod\_from\_gtw -ca \\"direction=I;protocol=PEL\\"

1.  Create a Transfer Change State-type Rule Table. Use the <span class="code">[peladm create\_ruletable](../../../managing_events_start_here/working_with_decision_rules_cli/working_with_rule_tables_cli#peladm_create_ruletable)</span> command.

Example:

peladm create\_ruletable -n RT\_FROM\_GTW -type XFER\_CHANGE\_STATE -a "DR\_FROM\_GTW"

<span id="Connector_managment_details"></span>

## Details of <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span> / Axway Messaging link management commands

The following online commands are available for managing links between Gateway and an Axway Messaging server:

-   [<span class="code">peladm create\_xmsctor</span>](#Create_Messaging_connector)
-   [<span class="code">peladm update\_xmsctor</span>](#Update_Messaging_connector)
-   [<span class="code">peladm delete\_xmsctor</span>](#Delete_Messaging_connector)
-   [<span class="code">peladm create\_proplist</span>](#Create_proplist)
-   [<span class="code">peladm update\_proplist</span>](#Update_proplist)
-   [<span class="code">peladm delete\_proplist</span>](#Delete_proplist)
-   [<span class="code">peldsp display\_xmsctor</span>](#Display_connector)
-   [<span class="code">peldsp select\_xmsctor</span>](#Select_Messaging_connector)
-   [<span class="code">peldsp display\_proplist</span>](#Display_properties_list)
-   [<span class="code">peldsp select\_proplist</span>](#Select_properties_list)

<span id="Create_Messaging_connector"></span>

## Creating an Axway Messaging connector: peladm create\_xmsctor

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><strong>Syntax</strong>         </td>
         <td><p><span class="code" style="font-weight: bold;">peladm create_xmsctor</span> [parameters]</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to create an Axway Messaging connector.</p>
<p>This command creates a connector for either:</p>
<ul>
<li>outgoing Axway Messaging messages originating from a specified Axway Messaging server and queue</li>
<li>incoming messages to be transmitted to a specified Axway Messaging server message queue</li>
</ul>
<p>Repeat the command for each required connector creation.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span class="code">-name (-n)</span>: Enter a name for the Axway Messaging connector.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-type (-t)</span>: Enter one of the following values to indicate the Axway Messaging connector type:</p>
<ul>
<li><span style="font-weight: bold;">IN</span>: for transmitting incoming file transfers to an Axway Messaging server message queue</li>
<li><span style="font-weight: bold;">OUT</span>: for transmitting the messages of an Axway Messaging server message queue to a file transfer application via a Gateway Transfer Request</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-active (-a)</span>: Enter one of the following values:</p>
<ul>
<li><span style="font-weight: bold;">Y</span> (yes) = activate the connector</li>
<li><span style="font-weight: bold;">N</span> (no): = (default) deactivate the connector</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-hostname (-host)</span>: Enter the name or the IP address of the Axway Messaging host machine to which Gateway is attached.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-port (-p)</span>: Enter the TCP access port of the Axway Messaging host machine.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-ident (-i)</span>: Enter the Gateway login identity for Axway Messaging host login.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-password (-pwd)</span>: Enter the password for Axway Messaging host login.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-log_level (-ll)</span>: Enter the required logging level:</p>
<ul>
<li><span style="font-weight: bold;">0</span> = no logging</li>
<li><span style="font-weight: bold;">1</span> = short logs</li>
<li><span style="font-weight: bold;">2</span> = full logs</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-backup_messages (-bm)</span>: For incoming messages, to save a copy of messages filtered and not handled by Decision Rules and Rule Tables in the Axway Messaging file [<span style="font-style: italic;">XMSReceptionQueue</span>]<span style="font-style: italic;"> bck,</span> enter one of the following values:</p>
<ul>
<li><span style="font-weight: bold;">Y</span> = The message is saved in the backup file</li>
<li><span style="font-weight: bold;">N</span> = The message is not saved</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-reception_queue_name (-rqn)</span>: For outgoing messages, enter the name of the Axway Messaging queue in which Gateway reads messages.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-message_type (-mt)</span>: For outgoing messages, enter one of the following values:</p>
<ul>
<li><span style="font-weight: bold;">MSG</span> = Axway Messaging message handling</li>
<li><span style="font-weight: bold;">ERROR_ACK</span> = error and acknowledgment handling</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-reception_directory (-rd)</span>: For outgoing messages, enter the directory in which Gateway stores Axway Messaging data content to be sent.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-message_size_max (-msm)</span>: Enter the maximum message size to be handled.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-compression (-c)</span>: For incoming files transferred to Axway Messaging, enter one of the following values:</p>
<ul>
<li><span style="font-weight: bold;">Y</span> = The message is compressed</li>
<li><span style="font-weight: bold;">N</span> = (default) The message is not compressed</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-delivery_mode (-dm)</span>: For incoming files transferred to Axway Messaging, enter one of the following values:</p>
<ul>
<li><span style="font-weight: bold;">PERSISTENT</span> = Persistent mode. Until the receiving application consumes the message, the receiving server stores a copy of the message in the Axway Messaging Log. If the connection between the receiving application and the receiving server fails, the receiving server does not lose the message.</li>
<li><span style="font-weight: bold;">NO_PERSISTENT</span> = Non-persistent mode. The receiving server does not store a copy of the message in the Axway Messaging Log. If the connection between the receiving application and the receiving server fails, the receiving server loses the message.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-priority (-pr)</span>: For incoming files, enter one of the following values to indicate the priority an application can use as a criteria for getting messages from a source:</p>
<ul>
<li><span style="font-weight: bold;">LOW</span> = XMS_LOW_PRIORITY: The message has low priority</li>
<li><span style="font-weight: bold;">MEDIUM</span> = XMS_MEDIUM_PRIORITY: The message has intermediate priority</li>
<li><span style="font-weight: bold;">HIGH</span> = XMS_HIGH_PRIORITY: The message has high priority</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>Enter the command:</p>
<p>   peladm create_xmsctor  -n routeCtor1  -t OUT</p>
<p>   -a Y  -hos mypc  -p 4569  -i USER1  -pwd USER1</p>
<p>Gateway creates and activates an OUT Axway Messaging connector with the properties:</p>
<ul>
<li>name = <span style="font-style: italic;">routeCtor1</span></li>
<li>host name = <span style="font-style: italic;">mypc</span></li>
<li>host TCP port =<span style="font-style: italic;">4569</span></li>
<li>user ID / User password = <span style="font-style: italic;">USER1 / USER1</span></li>
</ul>         </td>
      </tr>
   </tbody>
</table>

<span id="Update_Messaging_connector"></span>

## Updating an Axway Messaging connector: peladm update\_xmsctor

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><strong>Syntax</strong>         </td>
         <td><p><span class="code" style="font-weight: bold;">peladm update_xmsctor</span> [parameters]</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to update parameter values of an existing Axway Messaging connector.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>Mandatory</p>
<p>-name (-n): Enter the name of the Axway Messaging connector for which you want to update parameter values.</p>         </td>
      </tr>
      <tr>
         <td><p>-active (-a): Enter one of the following values:</p>
<ul>
<li><span style="font-weight: bold;">Y</span> (yes) = activate the connector</li>
<li><span style="font-weight: bold;">N</span> (no): = deactivate the connector</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-hostname (-host): Enter the name or the IP address of the Axway Messaging host machine to which Gateway is attached.</p>         </td>
      </tr>
      <tr>
         <td><p>-port (-p): Enter the TCP access port of the Axway Messaging host machine.</p>         </td>
      </tr>
      <tr>
         <td><p>-ident (-i): Enter the Gateway login identity for Axway Messaging host login.</p>         </td>
      </tr>
      <tr>
         <td><p>-password (-pwd): Enter the password for Axway Messaging host login.</p>         </td>
      </tr>
      <tr>
         <td><p>-log_level (-ll): Enter the required logging level:</p>
<ul>
<li><span style="font-weight: bold;">0</span> = no logging</li>
<li><span style="font-weight: bold;">1</span> = short logs</li>
<li><span style="font-weight: bold;">2</span> = full logs</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-backup_messages (-bm): For outgoing messages, to save a copy of messages selected via Decision Rules and Rule Tables in the Axway Messaging file <span style="font-style: italic;">XMSReceptionQueue bck,</span> enter one of the following values:</p>
<ul>
<li><span style="font-weight: bold;">Y</span> = The message is saved in the backup file</li>
<li><span style="font-weight: bold;">N</span> = The message is not saved</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-reception_queue_name (-rqn): For outgoing messages, enter the name of the Axway Messaging queue in which Gateway reads messages.</p>         </td>
      </tr>
      <tr>
         <td><p>-message_type (-mt): For outgoing messages, enter one of the following values:</p>
<ul>
<li><span style="font-weight: bold;">MSG</span> = Axway Messaging message handling</li>
<li><span style="font-weight: bold;">ERROR_ACK</span> = error and acknowledgement handling</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-reception_directory (-rd): For outgoing messages, enter the directory in which Gateway stores Axway Messaging data content to be sent.</p>         </td>
      </tr>
      <tr>
         <td><p>-message_size_max (-msm): Enter the maximum message size to be handled.</p>         </td>
      </tr>
      <tr>
         <td><p>-compression (-c): For incoming files transferred to Axway Messaging, enter one of the following values:</p>
<ul>
<li><span style="font-weight: bold;">Y</span> = The message is compressed</li>
<li><span style="font-weight: bold;">N</span> = The message is not compressed</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-delivery_mode (-dm): For incoming files transferred to Axway Messaging, enter one of the following values:</p>
<ul>
<li><span style="font-weight: bold;">PERSISTENT</span> = Persistent mode. Until the receiving application consumes the message, the receiving server stores a copy of the message in the Axway Messaging Log. If the connection between the receiving application and the receiving server fails, the receiving server does not lose the message.</li>
<li><span style="font-weight: bold;">NO_PERSISTENT</span> = Non-persistent mode. The receiving server does not store a copy of the message in the Axway Messaging Log. If the connection between the receiving application and the receiving server fails, the receiving server loses the message.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-priority (-pr): For incoming files, enter one of the following values to indicate the priority an application can use as a criteria for getting messages from a source:</p>
<ul>
<li><span style="font-weight: bold;">LOW</span> = XMS_LOW_PRIORITY: The message has low priority</li>
<li><span style="font-weight: bold;">MEDIUM</span> = XMS_MEDIUM_PRIORITY: The message has intermediate priority</li>
<li><span style="font-weight: bold;">HIGH</span> = XMS_HIGH_PRIORITY: The message has high priority</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>Enter the command:</p>
<p>   peladm update_xmsctor -n xmsCtor1 -rd c:\temp\recepXMS_2</p>
<p>Gateway sets the reception directory attribute of the Axway Messaging connector named <span style="font-style: italic;">smsCtor1</span> to<span class="code"> c:\temp\recepXMS_2</span>.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Delete_Messaging_connector"></span>

## Deleting an Axway Messaging connector: peladm delete\_xmsctor

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><strong>Syntax</strong>         </td>
         <td><p>peladm delete_xmsctor [-name]</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to delete an Axway Messaging connector.</p>
<p>Repeat the command for each connector you want to delete.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameter</p>         </td>
         <td><p>Mandatory</p>
<p><span class="code">-name (-n)</span>: Enter the name of the Axway Messaging connector you want to delete.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>Enter the command:</p>
<p>   peladm delete_xmsctor  -n xmsCtor1</p>
<p>Gateway deletes the Axway Messaging connector named <span style="font-style: italic;">xmsCtor1</span>.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Create_proplist"></span>

## Creating an Axway Messaging connector Property List: peladm create\_proplist

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p>peladm create_proplist [-properties_list] [-comments] [-add_prop]</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to create a new Property List.</p>
<p>Repeat the command for each Property List that you want to create.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span class="code">-properties_list (-pl)</span>: Enter the name of the Axway Messaging connector Property List you want to create.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-comments (-cts)</span>: Enter a free text description. Maximum: 80 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-add_prop (-ap)</span>: Add one or more properties to the list, in the form</p>
<p>prop1:type1;prop2:type2;propN:typeN</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>Enter the command:</p>
<p>   peladm create_proplist  -pl list1  -ap "xms_ori:int;xms_dest:ext"</p>
<p>Gateway creates the Property List named <span style="font-style: italic;">list1</span>.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Update_proplist"></span>

## Updating an Axway Messaging connector Property List: peladm update\_proplist

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p>peladm update_proplist [-properties_list] [-comments] [-add_prop] [-add_prop] [-update_prop] [-delete_prop]</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to update an existing Axway Messaging connector Property List.</p>
<p>Repeat the command for each Property List you want to update.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>-properties_list (-pl): Enter the name of the Axway Messaging connector Property List you want to update.</p>         </td>
      </tr>
      <tr>
         <td><p>-comments (-cts): Enter a free text description. Maximum: 80 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>-add_prop (-ap): Add one or more properties to the list, using the form:</p>
<p>prop1:type1;prop2:type2;propN:typeN</p>         </td>
      </tr>
      <tr>
         <td><p>-update_prop (-up): Update one or more properties in an existing list, using the form:</p>
<p>prop1:type1;prop2:type2;propN:typeN</p>         </td>
      </tr>
      <tr>
         <td><p>-delete_prop (-dp): Delete one or more properties from an existing list, using the form:</p>
<p>prop1;prop2;propN</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>Enter the command:</p>
<p>   <strong>peladm update_proplist  -pl list1  -up "xms_ori:int"</strong></p>
<p>Gateway sets the <span class="code">xms_ori</span> attribute of the list1 Property List to an <span style="font-style: italic;">int</span> data type value.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Delete_proplist"></span>

## Deleting an Axway Messaging connector Property List: peladm delete\_proplist

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p>peladm delete_proplist [-properties_list]</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to delete an Axway Messaging connector Property List.</p>
<p>Repeat the command for each Property List that you want to delete.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span class="code">-properties_list (-pl)</span>: Enter the name of the existing Axway Messaging connector Property List you want to delete.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>Enter the command:</p>
<p>   peladm delete_proplist  -pl list1</p>
<p>Gateway deletes the Property List named <span style="font-style: italic;">list1</span>.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Display_connector"></span>

## Displaying an Axway Messaging connector: peldsp display\_xmsctor

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p>peldsp display_xmsctor [-name]</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to display an Axway Messaging connector.</p>
<p>Repeat the command for each connector for which you want to view properties.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span class="code">-name (-n)</span>: Enter the name of the existing Axway Messaging connector you want to display.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>Enter the command:</p>
<p>   peldsp display_xmsctor  -n xmsCtor1</p>
<p>Gateway displays the properties of the Axway Messaging connector named <span style="font-style: italic;">xmsCtor1</span>.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Select_Messaging_connector"></span>

## Selecting an Axway Messaging connector: peldsp select\_xmsctor

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p>peldsp select_xmsctor [-name]</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to select an Axway Messaging connector.</p>
<p>Repeat the command for each connector you want to select.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span class="code">-name (-n)</span>: Enter the name of the existing Axway Messaging connector for which you want to display characteristics.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-type (-t)</span>: Enter one of the following connector types as a selection criteria:</p>
<ul>
<li><span style="font-weight: bold;">IN</span>: incoming file transfers to an Axway Messaging server message queue</li>
<li><span style="font-weight: bold;">OUT</span>: outgoing file transfers from an Axway Messaging server</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-active (-a)</span>: Enter one of the following activity states as a selection criteria:</p>
<ul>
<li><span style="font-weight: bold;">Y</span> (yes) = connector in active state</li>
<li><span style="font-weight: bold;">N</span> (no): = connector in inactivate state</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-reception_queue_name (-rqn)</span>: Enter the name of an Axway Messaging server reception queue.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>Enter the command:</p>
<p>   peldsp select_xmsctor</p>
<p>Gateway displays a list of all Axway Messaging connectors.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Display_properties_list"></span>

## Displaying an Axway Messaging connector Property List: peldsp display\_proplist

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p>peldsp display_proplist [-properties_list]</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to display a Property List.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span class="code">-properties_list (-pl)</span>: Enter the name of the Property List whose properties you want to display.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>Enter the command:</p>
<p>   peldsp display_proplist  -pl list1</p>
<p>Gateway displays the properties of the Property List named <span style="font-style: italic;">list1</span>.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Select_properties_list"></span>

## Displaying all Axway Messaging connector Property Lists: peldsp select\_proplist

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p>peldsp select_proplist [-properties_list]</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to select one or more Property Lists for display.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span class="code">-properties_list (-pl)</span>: Enter the names of the Property Lists you want to display.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>Enter the command:</p>
<p>   peldsp select_proplist</p>
<p>Gateway displays a list of the names of all Property Lists.</p>         </td>
      </tr>
   </tbody>
</table>

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
