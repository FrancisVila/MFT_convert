{
    "title": "Working with Diffusion Lists",
    "linkTitle": "Working with Diffusion Lists",
    "weight": "180"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Partners

[Creating a new Diffusion List object](#Creating_a_Diffusion_List)

[Displaying a list of all Diffusion List objects](#Displaying_all_Diffusion_List_objects)

[Displaying a list of selected Diffusion List objects](#Displaying_a_selected_list_of_Diffusion_List_objects)

[Displaying the attributes of a specified Diffusion List object](#Viewing_the_Attributes_of_a_Diffusion_List)

[Modifying a Diffusion List object](#Modifying_a_Diffusion_List_object)

[Deleting a Diffusion List object](#Deleting_a_Diffusion_List_object)

<span id="Creating_a_Diffusion_List"></span>

## Creating a new Diffusion List

To create a new Diffusion List object:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Partner Management</span> node.  
     
2.  Right-click the <span style="font-weight: bold;">Diffusion List</span> sub-node.  
    Gateway displays a context menu.  
      
3.  From the context menu, select <span style="font-weight: bold;">New</span>.  
    Gateway displays the <span style="font-style: italic;">New Diffusion List</span> dialog window. This window comprises two tabs.  
      
4.  Complete the fields of the <span style="font-weight: bold;">General</span> tab using the following table.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><span id="General_tab"></span>Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">Name</span></p>         </td>
         <td><p>Enter the Diffusion List name.<br />
Maximum: 31 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Model</span></p>         </td>
         <td><p>Enter the name of the default Model object attached to the List.<br />
Maximum: 26 alphanumeric characters.</p>
<p>Alternatively, select a Model from the drop-down list.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Group</span></p>         </td>
         <td><p>Enter the name of the Application group associated with the List.<br />
Maximum: 16 alphanumeric characters.<br />
The default Group name is <span style="font-weight: bold;">GDEFAULT</span>.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Template Site</span></p>         </td>
         <td><p>Select a Template Site to associate with the List.</p>
<p>If you select a template in this field, Gateway displays the <span style="font-weight: bold;">Destination list</span> tab.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Comments</span></p>         </td>
         <td><p>Enter a free-text description for the List.<br />
Maximum: 80 alphanumeric characters.</p>         </td>
      </tr>
   </tbody>
</table>

1.  If you did <span style="font-weight: bold;">not</span> select a Template Site in the <span style="font-weight: bold;">General</span> tab, the second tab of the <span style="font-style: italic;">New Diffusion List</span> window is the <span style="font-weight: bold;">List Selection</span> tab. Use the <span style="font-weight: bold;">List Selection</span> tab to select the Sites and/or Lists you want to include in your Diffusion List.  
      
    The <span style="font-weight: bold;">List Selection</span> tab has two panes:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><span id="List_Selection_tab"></span>Pane         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">Selected item</span></p>         </td>
         <td><p>The <span style="font-weight: bold;">Selected item</span> panel displays the lists and sites that you select in the <span style="font-weight: bold;">Available items</span> tab. These are the items that comprise your new Diffusion List.</p>
<p>To add an item to the <span style="font-weight: bold;">Selected item</span> pane, use the <span style="font-weight: bold;">Available items</span> pane below.</p>
<p>To remove an item from the <span style="font-weight: bold;">Selected item</span> pane, click the item to select it, then click the <span style="font-weight: bold;">Unselect</span> button.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Available items</span></p>         </td>
         <td><p>The <span style="font-weight: bold;">Available items</span> pane displays all existing Diffusion Lists and Sites that you can use to compose your new Diffusion List.</p>
<p>To add an item to the new Diffusion list, click to select the item in the <span style="font-weight: bold;">Available items</span> pane. Then click the <span style="font-weight: bold;">Select</span> button. Gateway adds the item to the list of the <span style="font-weight: bold;">Selected items</span> pane.</p>         </td>
      </tr>
   </tbody>
</table>

1.  If you selected a Template Site in the <span style="font-weight: bold;">General</span> tab, Gateway displays the <span style="font-weight: bold;">Destination list</span> tab in place of the <span style="font-weight: bold;">List Selection tab</span> described in the previous step.  
    You associate a Template Site with a Diffusion List only if you are using Gateway in Responder mode.  
      
    Use the <span style="font-weight: bold;">Destination list</span> tab to create one or more target destinations for the transfer of a single file responder-mode using a template. Remote clients can then retrieve files made available to them by connecting to the local Gateway using a name from the list.  
      
    The following table describes the components of the <span style="font-weight: bold;">Destination list</span> tab.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><span id="Destination_list_tab"></span>Pane         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">Add</span> (data field)</p>         </td>
         <td><p>Enter a remote user name to use to retrieve an available file from your local Gateway</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Add</span> (button)</p>         </td>
         <td><p>Click the <span style="font-weight: bold;">Add</span> button to add the name of the above data field to the list of remote users</p>         </td>
      </tr>
      <tr>
         <td><p>Result display pane</p>         </td>
         <td><p>This pane displays the list of remote users that exist for the selected template</p>         </td>
      </tr>
      <tr>
         <td><p>Delete<span style="font-weight: normal;"> (button)</span></p>         </td>
         <td><p>To delete an element from the list of users in the Result display pane, select the item in the pane and then click <span style="font-weight: bold;">Delete</span></p>         </td>
      </tr>
   </tbody>
</table>

1.  When you have finished composing your Diffusion List, click <span style="font-weight: bold;">OK</span> to validate and close the window.

<span id="Displaying_all_Diffusion_List_objects"></span>

## Displaying all Diffusion List objects

To display a list of all Diffusion List objects stored in the database:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Partner Management</span> node.  
     
2.  Click the <span style="font-weight: bold;">Diffusion List</span> sub-node.  
    Gateway displays a list of all existing Diffusion List objects in the right (display) pane.

<span id="Displaying_a_selected_list_of_Diffusion_List_objects"></span>

## Displaying a list of selected Diffusion List objects

You can reduce the number of Diffusion List objects listed in the display pane by applying selection criteria to the display.

To display a selected list of Diffusion List objects:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Partner Management</span> node.  
     
2.  Click the <span style="font-weight: bold;">Diffusion List</span> sub-node.  
    Gateway displays a list of all existing Diffusion List objects in the right pane.  
      
3.  Right-click the <span style="font-weight: bold;">Diffusion List</span> sub-node, then select <span style="font-weight: bold;">Select...</span> from the context menu.  
    Gateway displays the <span style="font-style: italic;">Select Diffusion Lists</span> window.  
      
4.  In the <span style="font-style: italic;">Select Diffusion Lists</span> window, use the data fields to enter criteria for Diffusion List display selection. You can use one or both of the following selection criteria:
    -   Maximum number of lists (default = 50)
    -   List Name  
         
5.  Click <span style="font-weight: bold;">OK</span> to accept the display selection criteria.  
    Gateway regenerates the right window Diffusion List display, taking into account your selection criteria.

<span id="Viewing_the_Attributes_of_a_Diffusion_List"></span>

## Viewing Diffusion List object attributes

To view the attributes of a specific Remote Site:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Partner Management</span> node.  
     
2.  Click the <span style="font-weight: bold;">Diffusion List</span> sub-node.  
    Gateway displays a list of all existing Diffusion List objects in the right (display) pane.  
      
3.  In the right pane, right-click the name of the Diffusion List object you want to view. Select <span style="font-weight: bold;">View...</span> from the context menu.  
    Gateway displays the <span style="font-style: italic;">Diffusion List (read only)</span> window. This window comprises two tabs that provide you with a view of all attributes for the selected Diffusion List.  
      
4.  When you have finished viewing the information, click <span style="font-weight: bold;">Close</span> to quit the window.

<span id="Modifying_a_Diffusion_List_object"></span>

## Modifying a Diffusion List object

To modify the attributes of an existing Diffusion List object:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Partner Management</span> node.  
     
2.  Click the <span style="font-weight: bold;">Diffusion List</span> sub-node.  
    Gateway displays a list of all existing Diffusion List objects in the right (display) pane.  
      
3.  In the display frame (right frame), right-click the Diffusion List object that you want to modify. Then in the context menu click <span style="font-weight: bold;">Modify...</span>.  
    Gateway opens the <span style="font-style: italic;">Diffusion List</span> editing window. This window comprises two tabs.  
      
4.  Modify the value fields of the tabs according to your requirements.  
     
5.  Click <span style="font-weight: bold;">OK</span> to confirm changes and complete the modification procedure.

<span id="Deleting_a_Diffusion_List_object"></span>

## Deleting a Diffusion List object

To delete an existing Diffusion List object:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Partner Management</span> node.  
     
2.  Click the <span style="font-weight: bold;">Diffusion List</span> sub-node.  
    Gateway displays a list of all existing Diffusion List objects in the right (display) pane.  
      
3.  In the right pane, right-click the name of the Diffusion List object you want to delete. Select <span style="font-weight: bold;">Delete...</span> from the context menu.  
    Gateway displays a confirmation dialog box.  
      
4.  In the confirmation dialog box, click <span style="font-weight: bold;">Yes</span> to confirm the delete operation.  
    Alternatively, click <span style="font-weight: bold;">No</span> or <span style="font-weight: bold;">Cancel</span> to abandon the operation.  
    Gateway deletes the Diffusion List object from the database and removes the entry from the display window.

Related topics

[Overview: Diffusion Lists](../../../ov_gateway/ov_diffusion_lists)

[Working with Diffusion Lists (command line)](../working_with_diffusion_lists_cli)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
