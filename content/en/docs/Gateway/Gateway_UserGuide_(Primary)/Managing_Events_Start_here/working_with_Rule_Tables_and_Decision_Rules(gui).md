{
    "title": "Working with Rule Tables and Decision Rules ",
    "linkTitle": "Working with Rule Tables and Decision Rules",
    "weight": "130"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Events

[Creating a Rule Table](#Creating_a_rule_table)

[Creating a Decision Rule](#Creating_Decision_Rule)

[Viewing a Rule Table or a Decision Rule](#Viewing_a_rule_table)

[Modifying a Rule Table or a Decision Rule](#Modifying_a_rule_table)

[Deleting a Rule Table or a Decision Rule](#Deleting_a_rule_table)

[Copying a Rule Table or a Decision Rule](#Copying_a_rule_table)

[Refreshing the Decision Rule/Rule Table list display](#Refreshing_a_table_list)

[Selecting one or more Decision Rules/Rule Tables from a displayed list](#Selecting_a_table_or_rule)

<span id="Creating_a_rule_table"></span>

## Creating a Rule Table

To create a new Rule Table:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Event Management</span> node.  
    Gateway expands the node to display the following sub-nodes:
    -   Scheduling
    -   Directory Scanning
    -   Transfer Change State
    -   XMS

Each sub-node represents a [Decision Rule / Rule Table category](../#Types_of_triggering_events).

1.  To create:
    -   A Scheduling, Directory Scanning or Transfer Change State type Rule Table, right-click the sub-node that represents the corresponding category. A context menu appears. Select <span style="font-weight: bold;">New</span> then <span style="font-weight: bold;">Rule Table...</span>.
    -   An XMS-type Rule Table, you must first [create an Axway Messaging connector](../creating_an_xms_connector).  
        After creating the connector, the connector name appears in the Directory Tree structure, listed under the <span style="font-weight: bold;">Event Management</span><span style="font-style: italic;"> ></span><span style="font-weight: bold;">XMS</span> sub-node. Right-click the connector name for which you want to create the Rule Table. A context menu appears. Select <span style="font-weight: bold;">New</span> then <span style="font-weight: bold;">Rule Table...</span>.

Gateway displays the <span style="font-style: italic;">New Rule Table</span> window.

This window comprises three tabs. The names and the contents of the tabs vary depending on the Rule Table type you are creating. Click the tab names in the following table to see explanations for completing the tabs.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Rule Table type         </th>
<th class="HeadD-Column1-Header1">Tabs         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Scheduling</p>         </td>
         <td><p><a href="../rule_table_general_tab">General</a></p>
<p><a href="../rule_table_general_tab/rule_table_scheduling_event_tab">Scheduling Event</a></p>
<p><a href="../rule_table_general_tab/rule_table_linked_rules_tab">Linked rules</a></p>         </td>
      </tr>
      <tr>
         <td><p>Directory Scanning</p>         </td>
         <td><p><a href="../rule_table_general_tab">General</a></p>
<p><a href="../rule_table_general_tab/rule_table_file_event_tab">File Event</a></p>
<p><a href="../rule_table_general_tab/rule_table_linked_rules_tab">Linked rules</a></p>         </td>
      </tr>
      <tr>
         <td><p>Transfer Change State</p>         </td>
         <td><p><a href="../rule_table_general_tab">General</a></p>
<p><a href="../rule_table_general_tab/rule_table_event_tab">Event</a></p>
<p><a href="../rule_table_general_tab/rule_table_linked_rules_tab">Linked rules</a></p>         </td>
      </tr>
      <tr>
         <td><p>XMS</p>         </td>
         <td><p><a href="../rule_table_general_tab">General</a></p>
<p><a href="../rule_table_general_tab/rule_table_xms_event_tab">XMS Event</a></p>
<p><a href="../rule_table_general_tab/rule_table_linked_rules_tab">Linked rules</a></p>         </td>
      </tr>
   </tbody>
</table>

1.  After completing the tabs, click <span style="font-weight: bold;">OK</span>.  
    Alternatively, click <span style="font-weight: bold;">Close</span> to abandon the creation.

<span id="Creating_Decision_Rule"></span>

## Creating a Decision Rule

To create a new Decision Rule:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Event Management</span> node.  
    Gateway expands the node to display the following sub-nodes:
    -   Scheduling
    -   Directory Scanning
    -   Transfer Change State
    -   XMS

Each sub-node represents a [Decision Rule / Rule Table category](../#Types_of_triggering_events).

1.  To create:
    -   A Scheduling, Directory Scanning or Transfer Change State type Decision Rule, right-click the sub-node that represents the corresponding category. A context menu appears. Select<span style="font-weight: bold;"> New</span> then<span style="font-weight: bold;"> Decision Rule...</span>.
    -   An XMS-type Decision Rule, you must first [create the related Axway Messaging connector](../creating_an_xms_connector) in the GUI.  
        After creating the connector, the connector name appears in the Directory Tree structure, listed under the <span style="font-weight: bold;">Event Management</span><span style="font-style: italic;"> ></span><span style="font-weight: bold;">XMS</span> sub-node. Right-click the connector name for which you want to create the Decision Rule. A context menu appears. Select <span style="font-weight: bold;">New</span> then <span style="font-weight: bold;">Decision Rule...</span>.

Gateway displays the <span style="font-style: italic;">New Decision Rule</span> window.

1.  Complete the <span style="font-style: italic;">New Decision Rule</span> window using the following table.

### Decision Rule window

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Element         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Name</p>         </td>
         <td><p>Enter a unique name for the new Decision Rule.</p>         </td>
      </tr>
      <tr>
         <td><p>Linked</p>         </td>
         <td><p>Click the check box to activate or deactivate the Decision Rule.</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>You cannot modify this field.</p>
<p>This field displays the Decision Rule type.</p>         </td>
      </tr>
      <tr>
         <td><p>Property list</p>         </td>
         <td><p>For Axway Messaging and JMS only</p>
<p>Select a <a href="../../transfers_start_here/parameters_start_here/models_start_here/managing_property_lists">Property List</a> to use with this Decision Rule from the drop-down list.</p>
<p>The Property List you select in this field determines the contents of the <span style="font-weight: bold;">Argument</span> or <span style="font-weight: bold;">Name</span> selection box below.</p>
<p>An XMS-type Decision Rule operates over an Axway <a href="../../connectors_about/messaging_connector">Messaging connector</a>. This connector is associated with one or more Property Lists that define attributes handled over the connector.</p>
<p><span style="font-weight: bold;">Note:</span> If you create a Decision Rule and later modify it, it is not possible to modify this field (grayed out).</p>         </td>
      </tr>
      <tr>
         <td><p>Comments</p>         </td>
         <td><p>Optional</p>
<p>Enter a free-text description for the Decision Rule.<br />
Maximum: 80 alphanumeric characters.</p>
<p>This description appears in the comment column of the Decision Rule list display pane.</p>         </td>
      </tr>
      <tr>
         <td><p>Conditions</p>
<p>This pane displays the conditions list. This is a list of expressions that contain the conditions for the triggering of a Decision Rule.</p>
<p>The expressions displayed are the results of the information you enter in this section.</p>
<p>All JMS properties are preceded by <span class="code">property_</span>.</p>         </td>
      </tr>
      <tr>
         <td><p>Argument</p>         </td>
         <td><p>Select an argument to use in the triggering criteria expression for your Decision Rule.</p>
<p><span style="font-weight: bold;">For JMS:</span> select <span style="font-weight: bold;">jms property</span>, then complete the <span style="font-weight: bold;">Name</span> field.</p>         </td>
      </tr>
      <tr>
         <td><p>Name</p>         </td>
         <td><p>JMS only</p>
<p>Enter a JMS property name.<br />
If you have completed the <span style="font-weight: bold;">Property list</span> field above, select a property from the drop-down list.</p>         </td>
      </tr>
      <tr>
         <td><p>Operator</p>         </td>
         <td><p>Select an <a href="../defining_decision_rule_conditions#Operators">operator</a> to use in the triggering criteria expression for your Decision Rule.</p>         </td>
      </tr>
      <tr>
         <td><p>Value</p>         </td>
         <td><p>Enter the value you want to assign to the <span style="font-weight: bold;">Argument</span> in your triggering criteria expression.</p>
<p>To use a symbolic variable, precede the variable by the <span style="font-style: italic;font-weight: bold;">&amp;</span> character.</p>
<p>For example, you can enter file name as a symbolic variable:</p>
<p><span class="code">appli = &amp;(file_name)</span></p>
<p>When processing the expression, Gateway replaces the symbolic variable with the file name that it takes from the concerned event.</p>         </td>
      </tr>
      <tr>
         <td><p>Add</p>         </td>
         <td><p>Click <span style="font-weight: bold;">Add</span> to insert the current contents of the <span style="font-weight: bold;">Argument, Name</span> (<span style="font-style: italic;">JMS only</span>), <span style="font-weight: bold;">Operator</span> and <span style="font-weight: bold;">Value</span> fields to the conditions list.</p>         </td>
      </tr>
      <tr>
         <td><p>Update</p>         </td>
         <td><p>To change an entry in the conditions list:</p>
<ol>
<li>Highlight the entry.</li>
<li>Modify the values displayed in the <span style="font-weight: bold;">Argument</span>, <span style="font-weight: bold;">Name</span> (<span style="font-style: italic;">JMS only</span>), <span style="font-weight: bold;">Operator</span> and <span style="font-weight: bold;">Value</span> fields.</li>
<li>Click <span style="font-weight: bold;">Update</span> to transfer the new values to the entry in the list.</li>
</ol>         </td>
      </tr>
      <tr>
         <td><p>Delete</p>         </td>
         <td><p>To delete an entry in the conditions list, highlight the entry and click <span style="font-weight: bold;">Delete</span>.</p>         </td>
      </tr>
      <tr>
         <td><p>Clear</p>         </td>
         <td><p>Click <span style="font-weight: bold;">Clear</span> to remove any values that currently appear in the <span style="font-weight: bold;">Argument, Name</span> (<span style="font-style: italic;">JMS only</span>), <span style="font-weight: bold;">Operator</span> and <span style="font-weight: bold;">Value</span> fields.</p>         </td>
      </tr>
      <tr>
         <td><p>Processing (if all conditions match)</p>         </td>
      </tr>
      <tr>
         <td><p>Execution type</p>         </td>
         <td><p>Select the processing type to apply to the event:</p>
<ul>
<li><span style="font-weight: bold;">Model</span>: redirect the Transfer to another transfer whose parameters are defined in a Transfer Model.<br />
If you select this value, you must complete the <span style="font-weight: bold;">Model</span> field. Additionally, it is recommended that you select the <span style="font-weight: bold;">Link input and output transfers</span> option, located to the right of the<span style="font-weight: bold;"> Model</span> field.</li>
<li><span style="font-weight: bold;">XIB</span>: redirect the Transfer to Axway Integrator or AMTrix for processing</li>
<li><strong>To XMS</strong>: redirect the Transfer to an Axway Messaging server queue via an Axway Messaging connector</li>
<li><strong>Mailbox cleaning</strong> (<span style="font-style: italic;">for Scheduling-type Rule Tables only</span>): clean the Mailbox via an associated Purge Model</li>
<li><span style="font-weight: bold;">Perl Script</span>: apply a Perl script</li>
<li><span style="font-weight: bold;">Batch command</span>: execute a batch command or script</li>
<li><span style="font-weight: bold;">No action</span>: implement no routing</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Model</p>         </td>
         <td><p>This field is displayed if you select either <span style="font-style: italic;">Model</span> or <span style="font-style: italic;">To XMS</span> as the <span style="font-weight: bold;">Execution type</span>.</p>
<ul>
<li>For <span style="font-style: italic;">Model</span> execution types: Enter the name of the Model to apply or select a Model from the drop-down list. Keep in mind that the Model name must correspond to a General Model.</li>
<li>For <span style="font-style: italic;">To XMS</span> execution types: Enter the name of an XMS-type Model.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>XMS connector out</p>         </td>
         <td><p>This field is displayed if you select<span style="font-style: italic;"> To XMS</span> as the <span style="font-weight: bold;">Execution type</span>.</p>
<p>Select the name of the Axway Messaging connector.</p>         </td>
      </tr>
      <tr>
         <td><p>Link input and output transfers</p>         </td>
         <td><p>Not for all types of Decision Rule.</p>
<p>This field is displayed if you select <span style="font-style: italic;">Model</span> as the <span style="font-weight: bold;">Execution type</span>.</p>
<p>Select this option to create a logical link between the incoming and the outgoing Transfers.</p>         </td>
      </tr>
      <tr>
         <td><p>Purge Model</p>         </td>
         <td><p>This field is displayed if you select <span style="font-style: italic;">Mailbox cleaning</span> as the <span style="font-weight: bold;">Execution type</span> for a Scheduling-type Decision Rule.</p>
<p>Select the name of the Purge Model that you want to associate with the execution type.</p>         </td>
      </tr>
      <tr>
         <td><p>Perl script</p>         </td>
         <td><p>This field is displayed if you select <span style="font-style: italic;">Perl Script</span> as the <span style="font-weight: bold;">Execution type</span>.</p>
<p>Enter the script to apply to the current Transfer.<br />
</p>
<p>The variable <code>p_perldll</code> must contain the location of the Perl library on the current machine.</p>
<p>For more information, refer to the readme in the <code>run_time\scripts\perl</code> folder.</p>         </td>
      </tr>
      <tr>
         <td><p>Batch command</p>         </td>
         <td><p>This field is displayed if you select <span style="font-style: italic;">Batch command</span> as the <span style="font-weight: bold;">Execution type</span>.</p>
<p>Enter the command to apply to the current Transfer.<br />
Alternatively, enter the path and file name of the script to execute.</p>
<p>Refer to <a href="../working_with_decision_rules_cli/decision_rules_executing_scripts">Executing scripts as command lines from Decision Rules</a>.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Viewing_a_rule_table"></span>

## Viewing a Rule Table or a Decision Rule

To view a Rule Table or a Decision Rule:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Event Management</span> node.  
    Gateway expands the node to display the following sub-nodes:
    -   Scheduling
    -   Directory Scanning
    -   Transfer Change State
    -   XMS

Each sub-node represents a [Decision Rule / Rule Table category](../#Types_of_triggering_events).

1.  Click the sub-node that corresponds to the type of Rule Table or Decision Rule you want to view. For example, to view a Scheduling type Rule Table, click the <span style="font-weight: bold;">Scheduling</span> sub-node.

In the right pane, Gateway displays a list of the Rule Tables and Decision Rules that exist for the sub-node category.

1.  In the right pane, right-click the name of the Rule Table or Decision Rule you want to view.

<!-- -->

1.  Select <span style="font-weight: bold;">View...</span> in the context menu.

Gateway displays a read-only version of the <span style="font-style: italic;">Rule Table</span> or <span style="font-style: italic;">Decision Rule</span> window, including all relevant tabs.

1.  Use this window as necessary to view your Rule Table or Decision Rule configuration.
2.  When finished, click <span style="font-weight: bold;">Close</span>.

<span id="Modifying_a_rule_table"></span>

## Modifying a Rule Table or a Decision Rule

To modify an existing Rule Table or a Decision Rule:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Event Management</span> node.  
    Gateway expands the node to display the following sub-nodes:
    -   Scheduling
    -   Directory Scanning
    -   Transfer Change State
    -   XMS

Each sub-node represents a [Decision Rule / Rule Table category](../#Types_of_triggering_events).

1.  Click the sub-node that corresponds to the type of Rule Table or Decision Rule you want to modify. For example, to modify a Scheduling type Rule Table, click the <span style="font-weight: bold;">Scheduling</span> sub-node.

In the right pane, Gateway displays a list of the Rule Tables and Decision Rules that exist for the sub-node category.

1.  In the right pane, right-click the name of the Rule Table or Decision Rule you want to modify.

<!-- -->

1.  Select <span style="font-weight: bold;">Modify...</span> in the context menu.

Gateway displays a <span style="font-style: italic;">Rule Table</span> or <span style="font-style: italic;">Decision Rule</span> editing window, including all relevant tabs.

1.  Use this window to modify your Rule Table or Decision Rule.
2.  When finished, click <span style="font-weight: bold;">OK</span>.

<span id="Deleting_a_rule_table"></span>

## Deleting a Rule Table or a Decision Rule

To delete an existing Rule Table or a Decision Rule:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Event Management</span> node.  
    Gateway expands the node to display the following sub-nodes:
    -   Scheduling
    -   Directory Scanning
    -   Transfer Change State
    -   XMS

Each sub-node represents a [Decision Rule / Rule Table category](../#Types_of_triggering_events).

1.  Click the sub-node that corresponds to the type of Rule Table or Decision Rule you want to delete.

For example, to delete a Scheduling type Rule Table, click the <span style="font-weight: bold;">Scheduling</span> sub-node.

In the right pane, Gateway displays a list of the Rule Tables and Decision Rules that exist for the sub-node category.

1.  In the right pane, right-click the name of the Rule Table or Decision Rule you want to delete.

<!-- -->

1.  Select <span style="font-weight: bold;">Delete</span> in the context menu.

Gateway displays a dialog box enabling you to confirm or abandon the delete process.

1.  Click <span style="font-weight: bold;">Yes</span> to confirm deletion.

Gateway closes the dialog box and deletes the Rule Table or Decision Rule. The line representing the Rule Table or Decision Rule is removed from the Decision Rule/ Rule Table list display in the right pane.

<span id="Copying_a_rule_table"></span>

## Copying a Rule Table or a Decision Rule

To make copy of an existing Rule Table or a Decision Rule in the same display list as the original Rule Table or Decision Rule:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Event Management</span> node.  
    Gateway expands the node to display the following sub-nodes:
    -   Scheduling
    -   Directory Scanning
    -   Transfer Change State
    -   XMS

Each sub-node represents a [Decision Rule / Rule Table category](../#Types_of_triggering_events).

1.  Click the sub-node that corresponds to the type of Rule Table or Decision Rule you want to copy. For example, to copy a Scheduling type Rule Table, click the <span style="font-weight: bold;">Scheduling</span> sub-node.

In the right pane, Gateway displays a list of the Rule Tables and Decision Rules that exist for the sub-node category.

1.  In the right pane, right-click the name of the Rule Table or Decision Rule you want to copy.

<!-- -->

1.  Select <span style="font-weight: bold;">Copy...</span> in the context menu.

Gateway displays a <span style="font-style: italic;">Copying</span> dialog box.

1.  In the <span style="font-style: italic;">Copying</span> dialog box, enter a unique name for the copy of the Rule Table or Decision Rule. Then click <span style="font-weight: bold;">OK</span> to confirm the copy process.

Gateway closes the dialog box and creates a copy of the Rule Table or Decision Rule. It adds a new line representing the new Rule Table or Decision Rule to the Decision Rule/ Rule Table list display in the right pane. The parameters of the copy are identical the original, except for the new name. To modify parameters of the copy, use the <span style="font-weight: bold;">[Modify...](#Modifying_a_rule_table)</span> command.

<span id="Refreshing_a_table_list"></span>

## Refreshing the Decision Rule/Rule Table list display

To refresh the display of Rule Tables and/or Decision Rules in the display pane:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Event Management</span> node.  
    Gateway expands the node to display the following sub-nodes:
    -   Scheduling
    -   Directory Scanning
    -   Transfer Change State
    -   XMS

Each sub-node represents a [Decision Rule / Rule Table category](../#Types_of_triggering_events).

1.  In the Directory Tree structure, right-click the sub-node that corresponds to the type of Rule Table and/or Decision Rule list you want to refresh.

For example, to refresh the view of a Scheduling type list of Rule Tables and Decision Rules, right-click the <span style="font-weight: bold;">Scheduling</span> sub-node.

Gateway displays a context menu.

1.  In the context menu, select<span style="font-weight: bold;"> Refresh</span>.

Gateway refreshes the list of Rule Tables and Decision Rules displayed in the right pane.

<span id="Selecting_a_table_or_rule"></span>

## Selecting one or more Decision Rules / Rule Tables from a displayed list

To filter the display of Rule Tables and/or Decision Rules in the display pane according to specific criteria:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Event Management</span> node.  
    Gateway expands the node to display the following sub-nodes:
    -   Scheduling
    -   Directory Scanning
    -   Transfer Change State
    -   XMS

Each sub-node represents a [Decision Rule / Rule Table category](../#Types_of_triggering_events).

1.  Right-click the sub-node that corresponds to the type of Rule Table and/or Decision Rule list you want to filter.

For example, to filter a Scheduling-type list of Rule Tables and Decision Rules, right-click the <span style="font-weight: bold;">Scheduling</span> sub-node.

Gateway displays a context menu.

1.  In the context menu, select<span style="font-weight: bold;"> Select...</span>.

Gateway displays the <span style="font-style: italic;">Select Rule Tables/Decision rules</span> window.

1.  In this window, enter values in the fields that you want to use as filtering criteria for a new display list. You can enter multiple criteria, and you can combine filtering of Rule Tables and Decision Rules. The following table lists the fields you can use to filter the display.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Rule tables selection</p>         </td>
      </tr>
      <tr>
         <td><p>Name</p>         </td>
         <td><p>Enter a Rule Table name to filter Rule Tables in the list display.</p>         </td>
      </tr>
      <tr>
         <td><p>Execution</p>         </td>
         <td><p>Select an execution type to filter Rule Tables in the list display.</p>         </td>
      </tr>
      <tr>
         <td><p>Decision rules selection</p>         </td>
      </tr>
      <tr>
         <td><p>Name</p>         </td>
         <td><p>Enter a Decision Rule name to filter Decision Rules in the list display.</p>         </td>
      </tr>
      <tr>
         <td><p>Comments</p>         </td>
         <td><p>Enter a comment to filter Decision Rules in the list display.</p>
<p>The comment must be the complete text of the comment field.</p>         </td>
      </tr>
      <tr>
         <td><p>Execution</p>         </td>
         <td><p>Select an execution type to filter Decision Rules in the list display.</p>         </td>
      </tr>
   </tbody>
</table>

1.  After completing the fields as required, click <span style="font-weight: bold;">OK</span>.

Gateway refreshes the list display in the right pane, filtering entries according to the specified criteria.

Related topics

[Rule Table: General tab](../rule_table_general_tab)

[Rule Table: Linked rules tab](../rule_table_general_tab/rule_table_linked_rules_tab)

[Rule Table: Schedule Event tab](../rule_table_general_tab/rule_table_scheduling_event_tab)

[Rule Table: File Event tab](../rule_table_general_tab/rule_table_file_event_tab)

[Rule Table: Event tab](../rule_table_general_tab/rule_table_event_tab)

[Rule Table: XMS Event tab](../rule_table_general_tab/rule_table_xms_event_tab)

 

[Defining Decision Rule conditions](../defining_decision_rule_conditions)

[Decision Rules and Rule Tables: Parameters List](../working_with_decision_rules_cli/decision_rules_rule_tables_parameter_list)

[Command syntax for Scheduling Event Models](../working_with_decision_rules_cli/scheduling_event_model_command_syntax) (date syntax)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
