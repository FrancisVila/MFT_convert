{
    "title": "Working with Purge Models",
    "linkTitle": "Working with Purge Models",
    "weight": "200"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Transfers

[Overview](#Overview)

[Creating a Purge Model](#Create_purge_model)

[Display a list of all Purge Models](#Displaying_all_purge_models)

[Display a list of selected Purge Models](#Display_selected_list_of_purge_models)

[View details of a Purge Model](#Viewing_purge_model_details)

<a href="#" class="selected">Modify a Purge Model</a>

[Delete a Purge Model](#Deleting_a_purge_model)

<span id="Overview"></span>

## Overview

The <span style="font-style: italic;">Purge Model</span> is a special category of Model object that you can use for selective purge operations. When you have created one or more Purge Models, you can associate the Purge Models with the <span style="font-style: italic;">default execution results</span> of a Scheduling-type Decision Rule event. Refer to [Rule Table: General tab](../../../../managing_events_start_here/rule_table_general_tab).

### Example

-   You create a Purge Model named <span style="font-style: italic;">PurgeNonLocal</span> in which you associate the attributes of the originators of transfers to the values of your foreign agencies.
-   You create a Scheduling-type Decision Rule in which:
    -   You define a daily scheduled event at 6 p.m.
    -   You set the Default execution type to <span style="font-style: italic;">Mailbox cleaning</span>
    -   You indicate the <span style="font-style: italic;">PurgeNonLocal</span> Purge Model as the associated Model

Result: Each day at 6 p.m., Gateway purges all records of transfers in the Mailbox with originating addresses from your foreign offices.

<span id="Create_purge_model"></span>

## Creating a new Purge Model

To create a new Purge Model:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:

Transfer Management &gt; Parameters &gt; Model &gt; Purge Model

1.  Right-click <span style="font-weight: bold;">Purge Model</span>, then select <span style="font-weight: bold;">New</span> from the context menu to display the <span style="font-style: italic;">New Purge Model</span> window.
2.  Complete the fields of this window as described in the following table.
3.  After completing the fields in this window, click <span style="font-weight: bold;">OK</span>.

### New Purge Model window

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>Field</p>         </td>
         <td><p>Description</p>         </td>
      </tr>
      <tr>
         <td><p>Name</p>         </td>
         <td><p>Enter the Purge Model name.<br />
Maximum: 31 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Comments</p>         </td>
         <td><p>Optional</p>
<p>Enter a free-text description of the Purge Model object.<br />
Maximum: 80 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Argument</p>         </td>
         <td><p>Value</p>         </td>
      </tr>
      <tr>
         <td><p>All arguments that you add to the Purge Model object are listed in this pane.</p>         </td>
      </tr>
      <tr>
         <td><p>Model attributes</p>
<p>Use the <span style="font-weight: bold;">Argument</span> and <span style="font-weight: bold;">Value</span> fields in this section, in combination with the <span style="font-weight: bold;">Add</span>, <span style="font-weight: bold;">Update</span>, <span style="font-weight: bold;">Delete</span> and <span style="font-weight: bold;">Clear</span> buttons, to create your list of arguments for the Purge Model.</p>         </td>
      </tr>
      <tr>
         <td><p>Argument</p>         </td>
         <td><p>Select an argument from the list and then complete the <span style="font-weight: bold;">Value</span> field.</p>         </td>
      </tr>
      <tr>
         <td><p>Value</p>         </td>
         <td><p>Press &lt;Ctrl + space&gt; to display the list of values you can enter for the selected argument. Alternatively, enter <span style="font-weight: bold;">&amp;</span> to access the list of symbolic variables directly. (Be sure to first select the <span style="font-weight: bold;">Argument</span>.)</p>
<p>This list comprises existing Gateway objects, symbolic variables and specific values appropriate to the selected argument.</p>
<p>Click <span style="font-weight: bold;">Add</span> to add the argument to the list.</p>
<p>The combination of an argument and associated value defines the filtering criteria for the purge operation. When you initiate a purge using this Model, Gateway purges all records from the Mailbox that contain this Argument/Value pair and any other pairs defined for this Model.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Displaying_all_purge_models"></span>

## Displaying all Purge Models

To display all existing Purge Models, in the left pane of the GUI main window click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:

Transfer Management &gt; Parameters &gt; Model &gt; Purge Model

Gateway displays any existing Purge Models in the display frame (right frame).

<span id="Display_selected_list_of_purge_models"></span>

## Displaying a selected Purge Model

You can display a single Purge Model listed in the display pane by applying selection criteria to the display.

To display a selected Purge Model:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:

Transfer Management &gt; Parameters

1.  Right-click the <span style="font-weight: bold;">Purge Model</span> sub-node, then choose <span style="font-weight: bold;">Select</span>... from the context menu.

Gateway displays the <span style="font-style: italic;">Select Models</span> window.

1.  In the <span style="font-style: italic;">Select Models</span> window, use the <span style="font-weight: bold;">Name</span> data field to enter criteria for Purge Model display.

<!-- -->

1.  Click <span style="font-weight: bold;">OK</span>.

Gateway regenerates the right window display list, taking into account your selection criteria.

<span id="Viewing_purge_model_details"></span>

## Viewing Purge Model details

To view the details of a specific existing Purge Model:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:

Transfer Management &gt; Parameters &gt; Model &gt; Purge Model

Gateway displays any existing Purge Models in the display frame (right frame).

1.  In the display frame (right frame), right-click the Purge Model whose characteristics you want to view. Then from the context menu, select <span style="font-weight: bold;">View</span>.

Gateway opens the <span style="font-style: italic;">Purge Model (Read only)</span> window, displaying details of the Purge Model.

<span id="Modifying_a_purge_model"></span>

## Modifying a Purge Model

To modify the parameter contents of an existing Purge Model:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:

Transfer Management &gt; Parameters &gt; Model &gt; Purge Model

Gateway displays any existing Purge Models in the display frame (right frame).

1.  In the display frame (right frame), right-click the Purge Model that you want to update. Then in the context menu click <span style="font-weight: bold;">Modify...</span> to display the<span style="font-style: italic;"> Purge Model</span> window.
2.  Select the [Argument](../model_object_parameter_list) that you want to modify. You can also add or delete Arguments.
3.  Complete the <span style="font-weight: bold;">Argument</span> and <span style="font-weight: bold;">Value</span> fields. Click <span style="font-weight: bold;">Update</span> to confirm these changes.
4.  Click <span style="font-weight: bold;">OK</span> to confirm and complete the update procedure.

<span id="Deleting_a_purge_model"></span>

## Deleting a Purge Model

To delete an existing Purge Model:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:

Transfer Management &gt; Parameters &gt; Model &gt; Purge Model

Gateway displays any existing Purge Models in the display frame (right frame).

1.  In the display frame (right frame), right-click the Purge Model that you want to delete. Then from the context menu, select <span style="font-weight: bold;">Delete</span> to remove the Purge Model.

<!-- -->

1.  Click <span style="font-weight: bold;">OK</span> to confirm and complete the delete procedure.

Related topics

[Working with Purge Models (command line)](../working_with_purge_models_cli)

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
