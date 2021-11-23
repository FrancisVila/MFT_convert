{
    "title": "Decision Rule usage example: Routing",
    "linkTitle": "Usage Examples",
    "weight": "190"
}{{< Gateway/componentlongname  >}}: Managing Events

[Model-based routing via the GUI](#Model-based_routing)

[Configuring Gateway for routing](#Configuring)

[Results](#Results)

<span id="Model-based_routing"></span>

## Model-based routing via the GUI

This topic provides an example of how to specify the routing behavior of Gateway.

The example describes how to use the GUI to route a file from an Axway Transfer product to an FTP client via Gateway, using a Decision Rule that applies a Model as the execution type.

The resulting series of processes is summarized by the following schema:

<img src="/Images/Gateway/FTPEventExample_756x167.png" class="maxWidth" />

<span id="Configuring"></span>

## Configuring Gateway for routing

To configure your Gateway for routing you execute the following main tasks:

-   [Create the Local and Remote Sites](#Defining_local_and_remote_sites)
-   [Create the execution Model](#Defining_the_execution_model)
-   [Create the Decision Rule](#Defining_the_decision_rule)
-   [Create the Rule Table and link the Decision Rule](#Defining_the_rule_table)

The following sections provide details about how to accomplish these tasks.

<span id="Defining_local_and_remote_sites"></span>

### Creating Local and Remote Sites

Create the following Sites:

-   In Gateway:
    -   Local Site = GATEWAY
    -   Remote Site = TRANSFER
    -   FTP Template Site = TFTP
-   In Axway Transfer:
    -   Local Site = TRANSFER
    -   Remote Site = GATEWAY

<span id="Defining_the_execution_model"></span>

### Creating the execution Model

In this example, the Decision Rule specifies a Model as the execution type for the received Transfer. Create a General Model and, optionally, a corresponding Protocol Model with the same name. The General Model is mandatory for routing, because you can only define the Transfer destination in the General Model and not in a Protocol Model. For more information, refer to [About Models](../../transfers_start_here/parameters_start_here/models_start_here).

1.  Create a General Model with the following properties:
    -   Model name: MODEL\_FTP
    -   Protocol: GENERAL
    -   Destination alias: TFTP
2.  Create a Protocol Model with the following properties:
    -   Model name: MODEL\_FTP
    -   Protocol: FTP
    -   Destination: FTPCLIENT
    -   File component: '&(dir\_path)/&(file\_component)'
    -   Application name: ‘&(appli)’

The file component and application parameters are mandatory. You can define these parameters in either the General or the Protocol Model. In this example, the definition uses symbolic variables (&(appli)) to retrieve the corresponding parameter values from the incoming Transfer. Using symbolic variables not only simplifies the definition but guarantees transfer coherence.

<span id="Defining_the_decision_rule"></span>

### Creating the Decision Rule

To define a Decision Rule that applies Model-based routing, create a Transfer Change State type Decision Rule as follows:

In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the **Event Management** node.  
Gateway expands the node to display the following four sub-nodes:

-   Scheduling
-   Directory Scanning
-   Transfer Change State
-   XMS

  
Each sub-node represents a [Decision Rule/Rule Table category](../#Types_of_triggering_events).

Right-click the <span style="font-weight: bold;">Transfer Change State</span> sub-node. A context menu appears. Select<span style="font-weight: bold;"> New &gt; Decision Rule</span>.  
Gateway displays a <span style="font-style: italic;">New Decision Rule</span> window.

In the <span style="font-style: italic;">New Decision Rule</span> window, enter the following data.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>For the parameter/ condition...</p>         </th>
<th class="HeadE-Column1-Header1"><p>Enter the value...</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Name</p>         </td>
         <td><p>Rule1</p>         </td>
         <td><p>Unique name for the Decision Rule.</p>         </td>
      </tr>
      <tr>
         <td><p>Active</p>         </td>
         <td><p>Click the check box</p>         </td>
         <td><p>Activates the Decision Rule.</p>         </td>
      </tr>
      <tr>
         <td><p>Comments</p>         </td>
         <td><p>(optional descriptive text)</p>         </td>
         <td><p>Free text description of the Decision Rule. Enter up to 80 alphanumeric characters.</p>
<p>This description appears in the comment column of the Decision Rule list display pane.</p>         </td>
      </tr>
      <tr>
         <td><p>Conditions</p>         </td>
      </tr>
      <tr>
         <td><p>1st condition</p>         </td>
         <td><p>protocol = PeSIT</p>         </td>
         <td><p>The protocol used in the incoming Transfer must be PeSIT.</p>         </td>
      </tr>
      <tr>
         <td><p>2nd condition</p>         </td>
         <td><p>destination#&amp;(originator)</p>         </td>
         <td><p>The destination must be different from the originator Site in the incoming Transfer.</p>         </td>
      </tr>
      <tr>
         <td><p>3rd condition</p>         </td>
         <td><p>rec_len[ ]150,3000</p>         </td>
         <td><p>The record length must be greater than or equal to 150 and less than or equal to 3000.</p>         </td>
      </tr>
      <tr>
         <td><p>4th condition</p>         </td>
         <td><p>direction = I</p>         </td>
         <td><p>The direction must be Input.</p>
<p>Specifying the direction parameter prevents the Decision Rule from looping on input and output Transfers.</p>         </td>
      </tr>
      <tr>
         <td><p>5th condition</p>         </td>
         <td><p>file_size ][ 10,50</p>         </td>
         <td><p>The file size must not be between the values 10 and 50.</p>         </td>
      </tr>
      <tr>
         <td><p>6th condition</p>         </td>
         <td><p>state = ended</p>         </td>
         <td><p>The state of the incoming Transfer is <span style="font-style: italic;">ended</span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Processing</strong> (if all conditions match)</p>         </td>
      </tr>
      <tr>
         <td><p>Execution type</p>         </td>
         <td><p>Model</p>         </td>
         <td><p>Execute Model-based routing on output.</p>         </td>
      </tr>
      <tr>
         <td><p>Model</p>         </td>
         <td><p>MODEL_FTP</p>         </td>
         <td><p>Name of the Model to use to execute routing.</p>
<p>This Model name must correspond to the name of a General Model and can optionally correspond to a Protocol Model name. The General Model must include the <span class="code">destination_alias</span> parameter. Either the Protocol or the General Model must include the following parameters:</p>
<ul>
<li>file_component</li>
<li>appli</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Link input and output transfers</p>         </td>
         <td><p>Click the check box</p>         </td>
         <td><p>Creates a logical link between the incoming and the outgoing Transfers.</p>         </td>
      </tr>
   </tbody>
</table>

When you have finished entering the values, click <span style="font-weight: bold;">OK</span> to accept.

<span id="Defining_the_rule_table"></span>

### Creating the Rule Table

To use an existing Decision Rule, you link the Decision Rule to a Rule Table. For this example we create a Transfer Change State-type Rule Table and link the <span style="font-style: italic;">Rule1</span> Decision Rule that we created in the previous section.

Create a Transfer Change State type Rule Table as follows:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Event Management</span> node.  
    Gateway expands the node to display the following four sub-nodes:
    -   Scheduling
    -   Directory Scanning
    -   Transfer Change State
    -   XMS

      
    Each sub-node represents a [Decision Rule/Rule Table category](../#Types_of_triggering_events).
2.  Right-click the <span style="font-weight: bold;">Transfer Change State</span> sub-node. A context menu appears.  Select<span style="font-weight: bold;"> New</span> > <span style="font-weight: bold;">Rule Table</span>.  
    Gateway displays a <span style="font-style: italic;">New Rule Table</span> window.
3.  In the <span style="font-weight: bold;">General</span> tab of the <span style="font-style: italic;">New Rule Table</span> window, enter the following data:
4.  In the <span style="font-weight: bold;">Event</span> tab of the <span style="font-style: italic;">New Rule Table</span> window, do not change the defaults (no processing restrictions).
5.  In the <span style="font-weight: bold;">Linked Rules</span> tab of the <span style="font-style: italic;">New Rule Table</span> window click <span style="font-weight: bold;">Rule1</span> in the available rules list to select it. Then click the **Link** button.  
    Gateway links the <span style="font-style: italic;">Rule1</span> Decision Rule to the <span style="font-style: italic;">Routing1</span> Rule Table.
6.  Click <span style="font-weight: bold;">OK</span> to validate the new Rule Table.  
    Gateway closes the New Rule Table window and adds the <span style="font-style: italic;">Routing1</span> entry to the display of Rule Tables and Decision Rules for Transfer Change State category.

<span id="Results"></span>

## Results

Once you have created and activated the Decision Rule and linked it to a Rule Table, the supervisor component of Gateway monitors gateway activity, analyzing incoming transfers for matches to the Decision Rule.

### Incoming Transfer match

Suppose that Gateway receives an incoming transfer with the following parameter values.

-   Direction: 'I' (incoming)
-   Application: 'APPLI'
-   Destination: GATEWAY
-   Originator: TRANSFER
-   Protocol: 'PeSIT'
-   Record length: 1024
-   File component: file.txt
-   File size: 147
-   State: Ended

Gateway checks the parameters of the incoming Transfer against the conditions set in the <span style="font-style: italic;">Rule1</span> Decision Rule.

-   Condition 1: protocol is PeSIT
-   Condition 2: destination (Gateway) is not the same as the originator (Axway Transfer)
-   Condition 3: record length is between 150 and 3000
-   Condition 4: direction is incoming
-   Condition 5: file size is not between 10 and 50
-   Condition 6: the incoming file transfer is complete and passed to the <span style="font-style: italic;">ended</span> state

### Routing result

Since the six conditions specified in the <span style="font-style: italic;">Rule1</span> Decision Rule match the parameters of the incoming Transfer, Gateway applies the Model MODEL\_FTP definition. After receiving the file from Axway Transfer, Gateway immediately deposits a new Transfer Request and makes the file available to the FTP client.

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
