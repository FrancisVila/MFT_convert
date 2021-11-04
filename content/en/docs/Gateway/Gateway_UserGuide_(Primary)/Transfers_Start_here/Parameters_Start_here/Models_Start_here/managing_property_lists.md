{
    "title": "Working with Property Lists",
    "linkTitle": "Working with Property Lists",
    "weight": "190"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Transfers

[Displaying all Property Lists](#Displaying_all_Property_Lists)

[Creating a Property List](#Creating_a_Property_List)

[Viewing the attributes of a Property List](#Viewing_attributes_of_a_Property_List)

[Modifying a Property List](#Modifying_a_Property_List)

[Deleting a Property List](#Deleting_a_Property_List)

In Gateway, Property Lists are used for both Axway Messaging and JMS.

<span style="font-weight: bold;">For Axway Messaging</span>, you must create a Property List before you create an XMS Model. The XMS Model then uses the attributes you defined in the Property List.

<span style="font-weight: bold;">For JMS</span>, the use of Property Lists is optional. A Property List makes it easier to add properties in a Model or Decision Rule.

Gateway uses the elements in a Property List to:

-   associate Transfer Request parameters with incoming Axway Messaging or JMS messages
-   provide information to Axway Messaging or JMS message destination applications about the contents of messages sent via Gateway

<span id="Displaying_all_Property_Lists"></span>

## Displaying all Property Lists

Before you can create an XMS Model, you must have at least one Property List.

To display all existing Property Lists, in the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:

Transfer Management &gt; Parameters &gt; Model &gt; XMS Model &gt; Property list

In the Directory tree structure, Gateway displays all existing Property Lists.

<span style="font-weight: bold;">Note:</span> You may need to refresh the display by right-clicking <span style="font-weight: bold;">Property list</span> and selecting <span style="font-weight: bold;">Refresh</span>.

<span id="Creating_a_Property_List"></span>

## Creating a Property List

If no Property List exists, or if you require a new list, create a list as follows:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:

Transfer Management &gt; Parameters &gt; Model &gt; XMS Model &gt; Property list

1.  Right-click the <span style="font-weight: bold;">Property list</span> sub-node and select <span style="font-weight: bold;">New</span> from the context menu.

Gateway displays the <span style="font-style: italic;">New Property List</span> window.

1.  Complete the fields of the <span style="font-style: italic;">New Property List</span> window as follows:

### <span style="font-style: italic;"><span id="New_Property_List_window"></span></span>New Property List window

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>Field</p>         </td>
         <td><p>Description</p>         </td>
      </tr>
      <tr>
         <td><p>Name</p>         </td>
         <td><p>Enter the name of the Property List.<br />
Maximum: 25 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Comments</p>         </td>
         <td><p>Enter a free-text description for the Property List.<br />
Maximum: 80 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Property</p>
<p>For each property you add, enter the <span style="font-weight: bold;">Name</span> and <span style="font-weight: bold;">Type</span>. Then click <span style="font-weight: bold;">Add</span> to include this property in the Property List.</p>         </td>
      </tr>
      <tr>
         <td><p>Name</p>         </td>
         <td><p>Enter the property name.</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Select the property type:</p>
<ul>
<li>Boolean</li>
<li>Char</li>
<li>Double</li>
<li>Float</li>
<li>Int</li>
<li>Long</li>
<li>Short</li>
<li>String</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

1.  Click <span style="font-weight: bold;">OK</span> to confirm and create the new Property List.

<span id="Viewing_attributes_of_a_Property_List"></span>

## Viewing the attributes of a Property List

To view the attributes of a specific Property List:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:

Transfer Management &gt; Parameters &gt; Model &gt; XMS Model &gt; Property list

In the Directory tree structure, Gateway displays the names of existing Property Lists.

1.  In the Directory tree structure, right-click the Property List that you want to view, and select <span style="font-weight: bold;">View...</span> from the context menu.

Gateway displays the<span style="font-style: italic;"> Property List (read only)</span> window. This window provides you with a view of all attributes for the selected Application.

1.  After viewing the information, click <span style="font-weight: bold;">Close</span> to quit the window.

<span id="Modifying_a_Property_List"></span>

## Modifying a Property List

To modify and update an existing Property List:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:

Transfer Management &gt; Parameters &gt; Model &gt; XMS Model &gt; Property list

In the Directory tree structure, Gateway displays the names of existing Property Lists.

1.  Right-click the <span style="font-weight: bold;">Property list</span> node and select <span style="font-weight: bold;">New </span>from the context menu.

Gateway displays the <span style="font-style: italic;">New Property List</span> window.

1.  Make the modifications in the Property List and click <span style="font-weight: bold;">Update</span> to take into account the new parameters. For details about the parameters of the Property List, refer to [New Property List window](#New_Property_List_window) (above).
2.  Click <span style="font-weight: bold;">OK</span> to confirm.

Repeat the procedure for each Property List you want to update.

<span id="Deleting_a_Property_List"></span>

## Deleting a Property List

To delete an existing Property List:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:

Transfer Management &gt; Parameters &gt; Model &gt; XMS Model &gt; Property list

In the Directory tree structure, Gateway displays the names of existing Property Lists.

1.  In the Directory tree structure, right-click the Property List that you want to delete, and select <span style="font-weight: bold;">Delete...</span> from the context menu.

<span style="font-weight: bold;">Note:</span> You cannot delete a Property List that contains any Model objects. If the <span style="font-weight: bold;">Delete</span> command is not active in the context menu, check the display pane to see if it contains any Model objects for the Property List. Delete any Model objects, then you can delete the Property List.

1.  Click <span style="font-weight: bold;">OK</span> to confirm.

Repeat the procedure for each Property List you want to delete.

 

Related topics

[Axway Messaging connector](../../../../connectors_about/messaging_connector)

[JMS connector](../../../../connectors_about/jms_about/jms_connector)

[Working with Transfer Models](../working_with_models_(gui))

[Working with XMS Models](../managing_xms_models)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
