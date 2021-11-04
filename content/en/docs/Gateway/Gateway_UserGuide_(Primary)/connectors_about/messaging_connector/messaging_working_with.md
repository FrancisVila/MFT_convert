{
    "title": "Linking Axway Gateway to Axway Messaging",
    "linkTitle": "Working with Messaging",
    "weight": "200"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Connectors

[How to link <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span> and Axway Messaging](#How_to_link_Gateway_and_Messaging)

[How to create a link from an Axway Messaging server to <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>](#Linking_Messaging_server_to_Gateway)

[How to create a link from <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span> to an Axway Messaging server](#Linking_Gateway_to_Messaging_server)

<span id="How_to_link_Gateway_and_Messaging"></span>

## How to link <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span> and Axway Messaging

The Gateway GUI enables you to create and manage links between Gateway and Axway Messaging.

You can create Gateway/Messaging links that operate in either of two directions:

-   [From an Axway Messaging server to a Gateway](#Linking_Messaging_server_to_Gateway) (<span style="font-style: italic;">IN</span> connector) outgoing Axway Messaging messages originating from a specified Axway Messaging server and queue and going to Gateway
-   [From a Gateway to an Axway Messaging server](#Linking_Gateway_to_Messaging_server) (<span style="font-style: italic;">OUT</span> connector) incoming messages to be transmitted to a specified Axway Messaging server message queue from Gateway

<span id="Linking_Messaging_server_to_Gateway"></span>

### How to create a link from an Axway Messaging server to <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>

To create a link from an Axway Messaging server to a Gateway:

1.  Create a Property List that describes the messages received from the Axway Messaging server:
    -   In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes: <span style="font-weight: bold;">Transfer Management > Parameters > Model > XMS Model</span>.
    -   Right-click <span style="font-weight: bold;">Property list</span> and select <span style="font-weight: bold;">New</span> from the context menu.  
        The <span style="font-style: italic;">New Property List</span> window is displayed.
    -   Complete the fields in the <span style="font-style: italic;">New Property List</span> window.
    -   Click <span style="font-weight: bold;">Add</span> after each property that you define to include that property in the Property List.
    -   Click <span style="font-weight: bold;">OK</span> to confirm and create the new Property List.

Refer to [Creating a Property List](../../../transfers_start_here/parameters_start_here/models_start_here/managing_property_lists#Creating_a_Property_List).

1.  Create an XMS Model for Transfers <span style="font-style: italic;">to</span> the Gateway:
    -   Select the Property List that you created in step 1.
    -   Complete the <span style="font-weight: bold;">Name</span> field for the Model.
    -   In the <span style="font-weight: bold;">Direction</span> field, select <span style="font-weight: bold;">To Gateway</span>.
    -   Click <span style="font-weight: bold;">OK</span>. The second Model window is displayed.
    -   Add the Model arguments and click <span style="font-weight: bold;">OK</span> to confirm.

Refer to [Working with XMS Models](../../../transfers_start_here/parameters_start_here/models_start_here/managing_xms_models).

1.  Create an <span style="font-style: italic;">In</span> type Axway Messaging connector:
    -   In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes: <span style="font-weight: bold;">Event Management > XMS</span>.
    -   Right-click <span style="font-weight: bold;">Connector In</span> and select <span style="font-weight: bold;">New</span>.
    -   Complete the <span style="font-style: italic;">XMS Connector In</span> window and click <span style="font-weight: bold;">OK</span> to confirm.

Refer to [Defining an In Connector](../../../managing_events_start_here/creating_an_xms_connector#Defining_IN_connector).

1.  Create an XMS-type Decision Rule:
    -   In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes: <span style="font-weight: bold;">Event Management ></span><span style="font-weight: bold;">Scheduling</span>.
    -   Right-click <span style="font-weight: bold;">New</span> and select <span style="font-weight: bold;">Decision Rule</span>.  
        The <span style="font-style: italic;">New Decision Rule</span> window is displayed.
    -   In the <span style="font-weight: bold;">Execution type</span> field, select <span style="font-weight: bold;">Model</span>.
    -   In <span style="font-weight: bold;">Model</span>, link to the XMS Model created in Step 2.

Refer to [Working with Decision Rules](../../../managing_events_start_here/working_with_rule_tables_and_decision_rules(gui)).

1.  Create an <span style="font-style: italic;">XMS-type</span> Rule Table.

Refer to [Working with Rule Tables](../../../managing_events_start_here/working_with_rule_tables_and_decision_rules(gui)).

<span id="Linking_Gateway_to_Messaging_server"></span>

### How to create a link from <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span> to an Axway Messaging server

To create a connector from a Gateway to an Axway Messaging server:

1.  Create a Property List that describes the messages received from the Gateway:
    -   In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes: <span style="font-weight: bold;">Transfer Management > Parameters > Model > XMS Model</span>.
    -   Right-click <span style="font-weight: bold;">Property list</span> and select <span style="font-weight: bold;">New</span> from the context menu.  
        The <span style="font-style: italic;">New Property List</span> window is displayed.
    -   Complete the fields in the <span style="font-style: italic;">New Property List</span> window.
    -   Click <span style="font-weight: bold;">Add</span> after each property that you define to include that property in the Property List.
    -   Click <span style="font-weight: bold;">OK</span> to confirm and create the new Property List.

Refer to [Creating a Property List](../../../transfers_start_here/parameters_start_here/models_start_here/managing_property_lists#Creating_a_Property_List).

1.  Create a Model for Transfers <span style="font-style: italic;">to</span> the Axway Messaging server:
    -   Select the Property List that you created in step 1.
    -   Complete the <span style="font-weight: bold;">Name</span> field for the Model.
    -   In the <span style="font-weight: bold;">Direction</span> field, select <span style="font-weight: bold;">From Gateway</span>.
    -   Click <span style="font-weight: bold;">OK</span>. The second Model window is displayed.
    -   Add the Model arguments and click <span style="font-weight: bold;">OK</span> to confirm.

Refer to [Working with XMS Models](../../../transfers_start_here/parameters_start_here/models_start_here/managing_xms_models).

1.  Create an <span style="font-style: italic;">Out</span> type Axway Messaging connector:
    -   In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes: <span style="font-weight: bold;">Event Management > XMS</span>.
    -   Right-click <span style="font-weight: bold;">Connector Out</span> and select <span style="font-weight: bold;">New</span>.
    -   Complete the <span style="font-style: italic;">XMS Connector Out</span> window and click <span style="font-weight: bold;">OK</span> to confirm.

Refer to [Defining an Out connector](../../../managing_events_start_here/creating_an_xms_connector#Defining_OUT_connector).

1.  Create an XMS-type Decision Rule:
    -   In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes: <span style="font-weight: bold;">Event Management > Scheduling</span>.
    -   Right-click <span style="font-weight: bold;">New</span> and select <span style="font-weight: bold;">Decision Rule</span>.  
        The <span style="font-style: italic;">New Decision Rule</span> window is displayed.
    -   In the <span style="font-weight: bold;">Execution type</span> field, select <span style="font-weight: bold;">To XMS</span>.
    -   In <span style="font-weight: bold;">Model</span>, link to the XMS Model created in Step 2.
    -   In <span style="font-weight: bold;">XMS Connector out</span>, select the Axway Messaging connector created in Step 3.

Refer to [Working with Decision Rules](../../../managing_events_start_here/working_with_rule_tables_and_decision_rules(gui)).

1.  Create a <span style="font-style: italic;">Transfer Change State</span> Rule Table.

Refer to [Working with Rule Tables](../../../managing_events_start_here/working_with_rule_tables_and_decision_rules(gui)).

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
