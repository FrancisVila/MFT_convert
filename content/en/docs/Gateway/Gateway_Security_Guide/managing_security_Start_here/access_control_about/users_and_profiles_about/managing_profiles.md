{
    "title": "Working with User Profiles ",
    "linkTitle": "Working with User Profiles",
    "weight": "170"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Security

[Creating a new User Profile object](#Creating_a_User_Profile_object)

[Displaying all User Profile objects](#Displaying_a_list_of_User_Profile_objects)

[Displaying a list of selected User Profile objects](#Displaying_a_list_of_selected_User_Profile_objects)

[Viewing User Profile object attributes](#Viewing_the_attributes_of_a_User_Profile_object)

[Modifying a User Profile object](#Modifying_a_User_Profile_object)

[Deleting a User Profile object](#Deleting_a_User_Profile_object)

<span id="Creating_a_User_Profile_object"></span>

## Creating a new User Profile object

To create a new User Profile object:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:  
    **Security Management > Access Control Management**
2.  Right-click the <span style="font-weight: bold;">Profile</span> sub-node, and then select <span style="font-weight: bold;">New</span> from the context menu.  
    Gateway displays the <span style="font-style: italic;">New Profile</span> window.
3.  In the <span style="font-style: italic;">New Profile</span> window:
    -   Enter a unique name for the Profile in the <span style="font-weight: bold;">Name</span> field. You can enter up to 31 alphanumeric characters.
    -   Optionally, enter a free-text description in the <span style="font-weight: bold;">Comments</span> field. You can enter up to 80 alphanumeric characters.
    -   Complete the object/access matrix. To grant complete access to all objects, click the <span style="font-weight: bold;">Select All</span> button. Alternatively, check individual boxes.
4.  Click <span style="font-weight: bold;">OK</span> to save the definition and close the window.

<span id="Displaying_a_list_of_User_Profile_objects"></span>

## Displaying all User Profile objects

To display a list of all User Profile objects stored in the database:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:  
    **Security Management > Access Control Management**
2.  Click the <span style="font-weight: bold;">Profile</span> sub-node.  
    Gateway displays a list of all existing User Profile objects in the right (display) pane.

<span id="Displaying_a_list_of_selected_User_Profile_objects"></span>

## Displaying a list of selected User Profile objects

You can reduce the number of User Profile objects listed in the display pane by applying selection criteria to the display.

To display a selected list of User Profile objects:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:  
    **Security Management > Access Control Management**
2.  Click the <span style="font-weight: bold;">Profile</span> sub-node.  
    Gateway displays a list of all existing User Profile objects in the right pane.
3.  Right-click the <span style="font-weight: bold;">Profile</span> sub-node, then select <span style="font-weight: bold;">Select...</span> from the context menu.  
    Gateway displays the <span style="font-style: italic;">Select Profile</span> window.
4.  In the <span style="font-style: italic;">Select Profile</span> window, use the data fields to enter criteria for User Profile display selection. You can use one or more of the following User Profile attributes as selection criteria:
    -   Maximum number of lists (default = 50)
    -   Profile user name
    -   Comments
    -   Active
5.  Click <span style="font-weight: bold;">OK</span> to accept the display selection criteria.  
    Gateway regenerates the right window User Profile list display, taking into account your selection criteria.

<span id="Viewing_the_attributes_of_a_User_Profile_object"></span>

## Viewing User Profile object attributes

To view the attributes of a specific User Profile object:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:  
    **Security Management > Access Control Management**
2.  Click the <span style="font-weight: bold;">Profile</span> sub-node.  
    Gateway displays a list of all existing User Profile objects in the right (display) pane.
3.  In the right pane, right-click the name of the User Profile object you want to view. Select <span style="font-weight: bold;">View...</span> from the context menu.  
    Gateway displays the <span style="font-style: italic;">User Profile (read only)</span> window. This window provides you with a view of all attributes for the selected User Profile object.
4.  When you have finished viewing the information, click <span style="font-weight: bold;">Close</span> to quit the window.

<span id="Modifying_a_User_Profile_object"></span>

## Modifying a User Profile object

To modify the attributes of an existing User Profile object:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:  
    **Security Management > Access Control Management**
2.  Click the <span style="font-weight: bold;">Profile</span> sub-node.  
    Gateway displays a list of all existing User Profile objects in the right (display) pane.
3.  In the display frame (right frame), right-click the User Profile object that you want to modify. Then in the context menu click <span style="font-weight: bold;">Modify...</span>  
    Gateway opens the <span style="font-style: italic;">User Profile</span> editing window.
4.  Modify the Profile rights according to your requirements.
5.  Click <span style="font-weight: bold;">OK</span> to confirm changes and complete the modification procedure.

<span id="Deleting_a_User_Profile_object"></span>

## Deleting a User Profile object

To delete an existing User Profile object:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Partner Management</span> node.
2.  Click the <span style="font-weight: bold;">Profile</span> sub-node.  
    Gateway displays a list of all existing User Profile objects in the right (display) pane.
3.  In the right pane, right-click the name of the User Profile object you want to delete. Select <span style="font-weight: bold;">Delete...</span> from the context menu.  
    Gateway displays a confirmation dialog box.
4.  In the confirmation dialog box, click <span style="font-weight: bold;">Yes</span> to confirm the delete operation.  
    Alternatively, click <span style="font-weight: bold;">No</span> or <span style="font-weight: bold;">Cancel</span> to abandon the operation.  
    Gateway deletes the User Profile object from the database and removes the entry from the display window.

Related topics

[About Access Control Management](../../)

[Configuration: Gateway parameters](../../../../../gateway_userguide_(primary)/configuration_start_here/config_gateway_paras)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
