{
    "title": "Working with XMS Models",
    "linkTitle": "Working with XMS Models",
    "weight": "190"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Transfers

[Creating an XMS Model](#Creating_an_XMS_model)

[Displaying a selected XMS Model](#Displaying_a_selected_XMS_Model)

[Modifying an XMS Model](#Modifying_an_XMS_Model)

[Deleting an XMS Model](#Deleting_an_XMS_Model)

[Displaying all XMS Models](#Displaying_all_XMS_Models)

For information about Property Lists, refer to [Working with Property Lists](../managing_property_lists).

Use XMS-type Model objects to create a link between Gateway and Axway Messaging via an Axway Messaging connector. XMS Models work exclusively with the Axway Messaging connector and do not function with other types of transfer.

Before creating an XMS Model you <span style="font-weight: bold;">must</span> create a Property List. The XMS Model then uses the attributes defined in the Property List.

<span id="Creating_an_XMS_model"></span>

## Creating an XMS Model

To transfer data between Axway Messaging and Gateway, you require an XMS-type Model.

To create a new XMS Model:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:

Transfer Management &gt; Parameters &gt; Model &gt; XMS Model &gt; Property list

In the Directory tree structure, Gateway displays the names of existing Property Lists.

<span style="font-weight: bold;">Note:</span> You may need to refresh the display by right-clicking <span style="font-weight: bold;">Property list</span> and selecting <span style="font-weight: bold;">Refresh</span>.

1.  Right-click a Property List name and select <span style="font-weight: bold;">New</span> from the context menu to display the first <span style="font-style: italic;">New XMS Model</span> window.
2.  In the <span style="font-weight: bold;">Name</span> field, enter a name for the new XMS Model.
3.  In the <span style="font-weight: bold;">Direction</span> field, select a server direction:
    -   <span style="font-weight: bold;">To Gateway</span>: for transmitting incoming file transfers to an Axway Messaging server message queue
    -   <span style="font-weight: bold;">From Gateway</span>: for transmitting the messages of an Axway Messaging server message queue to a file transfer application via a Gateway Transfer Request
4.  Click <span style="font-weight: bold;">OK</span> to confirm.  
    Gateway displays a second <span style="font-style: italic;">New XMS Model</span> window.
5.  Complete the second <span style="font-style: italic;">New XMS Model</span> window:
    -   In the <span style="font-weight: bold;">Comments</span> field, enter a comment (optional)
    -   Select an <span style="font-weight: bold;">Argument</span> from the drop-down list
    -   Use &lt;Ctrl + space> to list possible values and &lt;&> to list symbolic variables to define the argument
    -   Click <span style="font-weight: bold;">Add</span> to confirm this argument. Repeat until you have entered all arguments. You can use an existing transfer to aid you in deciding which arguments are useful for a given XMS Model.

    The Axway Messaging connector attributes table below lists and defines commonly used arguments.
6.  Click <span style="font-weight: bold;">OK</span> to confirm.

#### Axway Messaging connector attributes

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Argument</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>For outgoing messages, enter one of the following values:</p>
<ul>
<li><span style="font-weight: bold;">MSG</span> = Axway Messaging message handling</li>
<li><span style="font-weight: bold;">ERROR_ACK</span> = error and acknowledgment handling</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Directory Name</p>         </td>
         <td><p>For outgoing messages, enter the directory in which <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span> stores Axway Messaging data content to be sent.</p>         </td>
      </tr>
      <tr>
         <td><p>Max size</p>         </td>
         <td><p>Enter the maximum message size to be handled.</p>         </td>
      </tr>
      <tr>
         <td><p>Compression</p>         </td>
         <td><p>For incoming files transferred to Axway Messaging, enter one of the following values:</p>
<ul>
<li><span style="font-weight: bold;">Y</span> (yes)</li>
<li><span style="font-weight: bold;">N</span> (no)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Priority</p>         </td>
         <td><p>For incoming files, enter one of the following values to indicate the priority an application can use as a criteria for getting messages from a source:</p>
<ul>
<li><span style="font-weight: bold;">LOW</span> = The message has low priority</li>
<li><span style="font-weight: bold;">MEDIUM</span> = The message has intermediate priority</li>
<li><span style="font-weight: bold;">HIGH</span> = The message has high priority</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

<span id="Displaying_a_selected_XMS_Model"></span>

## Displaying a selected XMS Model

To view the attributes of a selected XMS Model

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:

Transfer Management &gt; Parameters &gt; Model &gt; XMS Model

1.  Right-click the <span style="font-weight: bold;">Property List</span> sub-node, then choose <span style="font-weight: bold;">Select</span>... from the context menu.

Gateway displays the <span style="font-style: italic;">Select Models</span> window.

1.  In the <span style="font-style: italic;">Select Models</span> window, use the <span style="font-weight: bold;">Name</span> field to enter criteria for the Model display selection.

<!-- -->

1.  Click <span style="font-weight: bold;">OK</span>.

Gateway regenerates the right window XMS Model display, taking into account your selection criteria.

<span id="Modifying_an_XMS_Model"></span>

## Modifying an XMS Model

To modify and update an XMS Model:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:

Transfer Management &gt; Parameters &gt; Model &gt; XMS Model &gt; Property list

In the Directory tree structure, Gateway displays the names of existing Property Lists.

1.  Click to select the Property List that contains the Model you want to modify.

In the display pane (right pane) Gateway displays the XMS Models contained in the selected Property List folder.

1.  Right-click the Model that you want to modify and select <span style="font-weight: bold;">Modify...</span> in the context menu. The corresponding Model window is displayed.
2.  Use the <span style="font-weight: bold;">Add</span>, <span style="font-weight: bold;">Update</span>, and <span style="font-weight: bold;">Delete</span> buttons to update the Model.
3.  Click <span style="font-weight: bold;">OK</span> to confirm these changes.

<span id="Deleting_an_XMS_Model"></span>

## Deleting an XMS Model

To delete an XMS Model:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:

Transfer Management &gt; Parameters &gt; Model &gt; XMS Model &gt; Property list

In the Directory tree structure, Gateway displays the names of existing Property Lists.

1.  Click to select the appropriate Property List that contains the Model you want to delete.

In the display pane (right pane) Gateway displays the XMS Models contained in the Property List folder you selected.

1.  Right-click the Model that you want to delete and select <span style="font-weight: bold;">Delete</span> in the context menu.
2.  Gateway displays a confirmation box. Click <span style="font-weight: bold;">Yes</span> to confirm.

Repeat for each XMS Model that you want to delete.

<span id="Displaying_all_XMS_Models"></span>

## Displaying all XMS Models

To display all XMS Models:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:

Transfer Management &gt; Parameters &gt; Model &gt; XMS Model &gt; Property list

In the Directory tree structure, Gateway displays the names of existing Property Lists.

1.  Click to select the Property List that contains the Model(s) you want to display.

In the display pane (right pane) Gateway displays the XMS Models contained in the Property List folder you selected.

Related topics

[Axway Messaging connector](../../../../connectors_about/messaging_connector)

[JMS connector](../../../../connectors_about/jms_about/jms_connector)

[Working with Property Lists](../managing_property_lists)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
