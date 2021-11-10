{
    "title": "Working with Transfer Models",
    "linkTitle": "Working with Transfer Models",
    "weight": "180"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Transfers

[Creating a new Transfer Model](#Creating_new_Transfer_Model)

[Creating a new General Model](#Creating_new_General_Model)

[Creating a new Protocol Model](#Creating_new_Protocol_Model)

[Displaying a list of all Transfer Models](#Displaying_all_Transfer_Models)

[Displaying a list of selected Transfer Models](#Displaying_selected_Transfer_Model)

[Viewing details of a Transfer Model](#Displaying_Transfer_Model)

[Modifying a Transfer Model](#Modifying_Transfer_Model)

[Deleting a Transfer Model](#Deleting_Transfer_Model)

<span id="Creating_new_Transfer_Model"></span>

## Creating a new Transfer Model

As described in [About Models](../), there are two types of Transfer Model:

-   General Model
-   Protocol Model

When you create a new Transfer Model, first [create a General Model](#Creating_new_General_Model). You can then optionally [create a Protocol Model](#Creating_new_Protocol_Model) with the same name.

<span id="Creating_new_General_Model"></span>

## Creating a new General Model

To create a new General Model:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:

Transfer Management &gt; Parameters &gt; Model &gt; Transfer Model

1.  Right-click <span style="font-weight: bold;">Transfer Model</span>, then select <span style="font-weight: bold;">New</span> from the context menu.

Gateway displays the <span style="font-style: italic;">New General Model</span> window.

1.  Complete the fields of this window as described in the table below.
2.  Click <span style="font-weight: bold;">OK</span>.

<span id="New_General_Model_window"></span>

### New General Model window (also for Protocol Models)

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Field</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Name</p>         </td>
         <td><p>Only for the General Model (this field is grayed out for the Protocol Model)</p>
<p>Enter the Transfer Model name.<br />
Maximum: 31 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Property List</p>
<p>(optional)</p>         </td>
         <td><p>Only for JMS</p>
<p>Select a <a href="../managing_property_lists">Property List</a> to use with this Model from the drop-down list.</p>
<p>The Property List you select in this field determines the contents of the <span style="font-weight: bold;">Name</span> selection box below.</p>
<p><span style="font-weight: bold;">Note:</span> If you create a Model and later modify it, it is not possible to modify this field (grayed out).</p>         </td>
      </tr>
      <tr>
         <td><p>Comments</p>
<p>(optional)</p>         </td>
         <td><p>Enter a free-text description of the Model object.<br />
Maximum: 80 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Protocol</p>         </td>
         <td><p>Only for the Protocol Model (this field is grayed out for the General Model)</p>
<p>Select the protocol:</p>
<ul>
<li>PEL</li>
<li>PeSIT E</li>
<li>PeSIT D</li>
<li>FTP</li>
<li>HTTP</li>
<li>OFTP<span style="font-weight: normal;"> (Odette)</span></li>
<li>SFTP</li>
<li>SMTP</li>
<li>POP3</li>
<li>EDIINT</li>
<li>AS1_POP3</li>
<li>AS1_SMTP</li>
<li>AS2</li>
<li>AS3</li>
<li>RN_POP3</li>
<li>RN_SMTP</li>
<li>RN_HTTP</li>
<li>SWIFTNet</li>
<li>JMS</li>
</ul>         </td>
      </tr>
      <tr>
         <td>Argument         </td>
         <td>Value         </td>
      </tr>
      <tr>
         <td><p>This table displays all attributes that you add to the Model object.</p>
<p>All JMS properties are preceded by <span class="code">property_</span>.</p>         </td>
      </tr>
      <tr>
         <td><p>Model attributes</p>
<p>Complete the <span style="font-weight: bold;">Argument</span>, <span style="font-weight: bold;">Name</span> (<span style="font-style: italic;">JMS only</span>) and<span style="font-weight: bold;"> Value</span> fields as described below, then click <span style="font-weight: bold;">Add</span> for each new attribute.</p>         </td>
      </tr>
      <tr>
         <td><p>Argument</p>         </td>
         <td><p>Select an argument from the list. The arguments displayed depend on the protocol.</p>
<p>For a complete list of parameters, refer to <a href="../model_object_parameter_list">Model Objects: Parameters List</a>.</p>
<p><span style="font-weight: bold;">For JMS:</span> select <span style="font-weight: bold;">jms property</span>, then complete the <span style="font-weight: bold;">Name</span> field.</p>         </td>
      </tr>
      <tr>
         <td><p>Name</p>         </td>
         <td><p><span style="font-style: italic;">Only for JMS</span></p>
<p>Enter a JMS property name.<br />
If you have completed the <span style="font-weight: bold;">Property List</span> field above, select a property from the drop-down list.</p>         </td>
      </tr>
      <tr>
         <td><p>Value</p>         </td>
         <td><p>Press &lt;Ctrl + space&gt; to display the list of values you can enter for the selected argument. Alternatively, enter <span style="font-weight: bold;">&amp;</span> to access the list of symbolic variables directly. (Make sure you first select the <span style="font-weight: bold;">Argument</span>.)</p>
<p>This list comprises existing Gateway objects, symbolic variables and specific values appropriate to the selected argument.</p>
<p>Alternatively, you can enter property values directly.</p>
<p><span style="font-weight: bold;">Note:</span> You can also use <a href="../../../../managing_events_start_here/defining_decision_rule_conditions#Using_user_functions">User functions</a>, such as <span class="code" style="font-weight: bold;">uppercase()</span> or <span class="code" style="font-weight: bold;">substring()</span> when defining a Model. However these user functions are only applicable when the Model is triggered by a routing function. User functions are not applied when the Model is used for a simple (non-routed) transfer.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Creating_new_Protocol_Model"></span>

## Creating a new Protocol Model

After creating a General Model, you can optionally create a Protocol Model with the same name.

To create a new Protocol Model:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:

Transfer Management &gt; Parameters &gt; Model &gt; Transfer Model

1.  Right-click the General Model for which you want to create a Protocol Model. Then select <span style="font-weight: bold;">New</span> from the context menu.

Gateway displays the <span style="font-style: italic;">New General Model</span> window.

<span style="font-weight: bold;">Note:</span> If you can only see the name of your General Model in the right pane of the GUI, and not in the left pane, you need to refresh the screen. Alternatively, close the <span style="font-weight: bold;">Transfer Model</span> node and then expand it once more.

1.  Complete the fields of this window as described in the [table](#New_General_Model_window) above.
2.  Click <span style="font-weight: bold;">OK</span>.

<span id="Displaying_all_Transfer_Models"></span>

## Displaying all Transfer Models

To display all existing Transfer Models:

In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:

Transfer Management &gt; Parameters &gt; Model &gt; Transfer Model

Gateway displays all existing General Models in the display frame (right frame).

#### Protocol Models

If you have created one or more Protocol Models for a General Model, a <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> appears next to the Model name.

Click the <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to display the Protocol Models for that General Model.

<span id="Displaying_selected_Transfer_Model"></span>

## Displaying a selected Transfer Model

You can display a single Transfer Model listed in the display pane by applying selection criteria to the display.

To display a selected Transfer Model:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:

Transfer Management &gt; Parameters

1.  Right-click the <span style="font-weight: bold;">Transfer Model</span> sub-node, then choose <span style="font-weight: bold;">Select</span>... from the context menu.

Gateway displays the <span style="font-style: italic;">Select Models</span> window.

1.  In the <span style="font-style: italic;">Select Models</span> window, use the <span style="font-weight: bold;">Name</span> data field to enter criteria for Transfer Model display.

<!-- -->

1.  Click <span style="font-weight: bold;">OK</span>.

Gateway regenerates the right window display list, taking into account your selection criteria.

<span id="Displaying_Transfer_Model"></span>

## Viewing Transfer Model details

#### General Model

To view the details of a General Model:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:

Transfer Management &gt; Parameters &gt; Model &gt; Transfer Model

Gateway displays all existing General Models in the display frame (right frame).

1.  In the display frame (right frame), right-click the General Model that you want to view. Then from the context menu, select <span style="font-weight: bold;">View</span>.

Gateway opens the <span style="font-style: italic;">General Model (Read only)</span> window, displaying details of the Model.

#### Protocol Model

To view the details of a Protocol Model:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:

Transfer Management &gt; Parameters &gt; Model &gt; Transfer Model

Gateway displays all existing General Models in the display frame (right frame).

1.  Click the <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> next to the name of the General Model in the left frame.

Gateway displays all existing Protocol Models for that General Model in the display frame (right frame).

1.  In the display frame (right frame), right-click the Protocol Model that you want to view. Then from the context menu, select <span style="font-weight: bold;">View</span>.

Gateway opens the <span style="font-style: italic;">General Model (Read only)</span> window, displaying details of the Model.

<span id="Modifying_Transfer_Model"></span>

## Modifying a Transfer Model

To modify the attributes of an existing Model:  
For a complete list of parameters and possible values, refer to [Model Objects: Parameters List](../model_object_parameter_list).

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:

Transfer Management &gt; Parameters &gt; Model &gt; Transfer Model

Gateway displays all existing Transfer Models in the display frame (right frame).

1.  In the display frame (right frame), right-click the Transfer Model that you want to modify. Then in the context menu click <span style="font-weight: bold;">Modify...</span> to display the<span style="font-style: italic;"> General Model</span> window.
2.  In the list of attributes, select the Argument that you want to modify.
3.  Complete the <span style="font-weight: bold;">Argument</span>, <span style="font-weight: bold;">Name</span> (<span style="font-style: italic;">JMS only</span>) and <span style="font-weight: bold;">Value</span> fields
4.  Click <span style="font-weight: bold;">Update</span> to confirm the changes.

Alternatively, you can add or remove attributes.

1.  Click <span style="font-weight: bold;">OK</span> to confirm and complete the update procedure.

<span id="Deleting_Transfer_Model"></span>

## Deleting a Transfer Model

To delete an existing Model:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:

Transfer Management &gt; Parameters &gt; Model &gt; Transfer Model

Gateway displays all existing Transfer Models in the display frame (right frame).

1.  In the display frame (right frame), right-click the Transfer Model that you want to delete. Then from the context menu, select <span style="font-weight: bold;">Delete</span>.

<!-- -->

1.  Click <span style="font-weight: bold;">OK</span> to confirm.

The Transfer Model is deleted.

Related topics

[Model objects: Parameters List](../model_object_parameter_list)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
