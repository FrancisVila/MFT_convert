{
    "title": "Working with Local Sites",
    "linkTitle": "Working with Local Sites",
    "weight": "150"
}{{< Gateway/componentlongname  >}}: Managing Partners

[Creating a Local Site object](#Creating_Local_Site)

[Displaying a list of Local Site objects](#Displaying_list_of_all_Local_Sites)

[Displaying selected Local Site objects](#Displaying_list_of_selected_Local_Sites)

[Viewing Local Site attributes](#Viewing_Local_Site_attributes)

[Modifying Local Site attributes](#Modifying_Local_Site_attributes)

[Deleting a Local Site](#Deleting_a_Local_Site)

<span id="Creating_Local_Site"></span>

## Creating a Local Site object

Gateway always contains at least one Local Site object that it generates from the configuration parameters you entered during the installation. You cannot remove this default Local Site object. You can, however, modify its parameters.

You can create as many additional Local Sites as you require.

To create a new Local Site object:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:  
    Partner Management > Sites
2.  Right-click the **Local Site** sub-node, then select <span style="font-weight: bold;">New</span> from the context menu to display the <span style="font-style: italic;">New Local Site</span> window.
3.  In this window, define the characteristics of the Site object by entering values in the fields, as described in the table below.
4.  After completing the fields, click <span style="font-weight: bold;">OK</span> to accept the values and close the window.  
    Gateway creates the new Local Site object and enters a new line representing the object in the display pane.

<span id="New_Local_Site_creation_window"></span>

### New Local Site window

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Field</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>General information</p>         </td>
      </tr>
      <tr>
         <td><p>Alias</p>         </td>
         <td><p>Enter the Local Site alias.<br />
Maximum: 31 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Protocol identifier</p>         </td>
         <td><p>Enter the Site protocol name.<br />
Maximum: 25 alphanumeric characters.<br />
By default, this value is the same as the Site alias name.</p>         </td>
      </tr>
      <tr>
         <td><p>OFTP</p>         </td>
         <td><p>Select this option if the protocol type is OFTP (Odette).</p>         </td>
      </tr>
      <tr>
         <td><p>Comments</p>         </td>
         <td><p>Optional</p>
<p>Enter a free-text description for the object.<br />
Maximum: 80 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>Default email address</p>         </td>
         <td><p>SMTP only</p>
<p>Enter the default email address (<span style="font-weight: bold;">From</span>) for the Local Site.<br />
Maximum: 128 characters.</p>
<p>When Gateway is acting as an SMTP client, it must indicate the <span style="font-weight: bold;">From</span> address of the email sender. If you do not specify the <span style="font-weight: bold;">From</span> address in the Transfer Request, Gateway searches for the address in the Local Site associated with the Remote Site that sends the Request.</p>
<p>A Remote Site and a Local Site are always associated with a Request that you send. Gateway identifies the Local Site either via the Remote Site parameter <span style="font-weight: bold;">Partner local alias</span><span style="font-style: italic;">,</span> or via the <span style="font-weight: bold;">Local site name</span> defined in the Gateway configuration menu.</p>         </td>
      </tr>
      <tr>
         <td><p>Directory for received files</p>         </td>
         <td><p>Enter the name of the directory used to store received files.<br />
Maximum: 127 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>User parameters</p>         </td>
      </tr>
      <tr>
         <td><p>Param 1</p>         </td>
         <td><p>User parameter.<br />
Maximum: 40 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Param 2</p>         </td>
         <td><p>User parameter.<br />
Maximum: 40 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Authentication certificate <span style="font-style: italic;font-weight: normal;">(OFTP R2.0 only)</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Specify the type of authentication certificate to use:</p>
<ul>
<li>SEC_ALIAS</li>
<li>Passport PS entity</li>
<li>Passport PS certificate</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Name</p>         </td>
         <td><p>Specify the authentication certificate to use.</p>         </td>
      </tr>
      <tr>
         <td><p>Password</p>         </td>
         <td><p><span style="font-style: italic;">Optional</span></p>
<p>Enter the connection password to send (from the Initiator) and the connection password to check (received from the Responder).</p>         </td>
      </tr>
   </tbody>
</table>

 

<span id="Displaying_list_of_all_Local_Sites"></span>

## Displaying a list of Local Site objects

To display a list of all Local Site objects stored in the database:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:  
    Partner Management > Sites
2.  Click the <span style="font-weight: bold;">Local Site</span> sub-node.  
    In the right pane, Gateway displays a list of all Local Sites.

<span id="Displaying_list_of_selected_Local_Sites"></span>

## Displaying selected Local Site objects

If your Gateway configuration includes multiple Local Site objects, you can limit the display by applying display selection criteria.

To limit the Local Site object display:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:  
    Partner Management > Sites
2.  Click the Local Site sub-node.  
    Gateway displays a list of all Local Sites in the right pane.
3.  Right-click the <span style="font-weight: bold;">Local Site</span> sub-node, then select <span style="font-weight: bold;">Select...</span> from the context menu.  
    Gateway displays the <span style="font-style: italic;">Select Local Sites</span> window.
4.  Enter either the name of a Local Site and/or a Local Site protocol identifier as selection criteria. Then click <span style="font-weight: bold;">OK</span>.  
    Gateway regenerates the right window display list, taking into account your selection criteria.

<span id="Viewing_Local_Site_attributes"></span>

## Viewing Local Site attributes

To view the attributes of a specific Local Site:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:  
    Partner Management > Sites
2.  Click the <span style="font-weight: bold;">Local Site</span> sub-node.  
    Gateway displays a list of all Local Sites in the right pane.
3.  In the right pane, right-click the name of the Local Site for which you want to view the Site attributes. Select <span style="font-weight: bold;">View...</span> from the context menu.  
    Gateway displays the<span style="font-style: italic;"> Local Sites (Read only)</span> window. This window provides you with a view of all attributes for the selected Local Site.
4.  When you have finished viewing the information, click <span style="font-weight: bold;">Close</span> to quit the window.

<span id="Modifying_Local_Site_attributes"></span>

## Modifying Local Site attributes

To modify the attributes of a Local Site:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:  
    Partner Management > Sites
2.  Click the <span style="font-weight: bold;">Local Site</span> sub-node.  
    Gateway displays a list of all Local Sites in the right pane.
3.  In the right pane, right-click the name of the Local Site for which you want to modify the Site attributes. Select <span style="font-weight: bold;">Modify...</span> from the context menu.  
    Gateway displays the<span style="font-style: italic;"> Local Site</span> editing window. This window comprises the same fields as the <span style="font-style: italic;">[New Local Site](#New_Local_Site_creation_window)</span> window above.
4.  Enter new values as required.
5.  After modifying the attributes, click <span style="font-weight: bold;">Close</span> to accept the new values and close the window.

<span id="Deleting_a_Local_Site"></span>

## Deleting a Local Site

To delete an existing Local Site:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:  
    Partner Management > Sites
2.  Click the <span style="font-weight: bold;">Local Site</span> sub-node.  
    Gateway displays a list of all Local Sites in the right pane.
3.  In the right pane, right-click the name of the Local Site you want to delete. Select <span style="font-weight: bold;">Delete...</span> from the context menu.  
    Gateway displays a confirmation dialog box.
4.  In the confirmation dialog box, click <span style="font-weight: bold;">Yes</span> to confirm the delete operation.  
    Alternatively, click <span style="font-weight: bold;">No</span> or <span style="font-weight: bold;">Cancel</span> to abandon the operation.  
    Gateway deletes the Local Site from the database and removes the entry from the display window.

Related topics

[Site objects: Parameters List](../managing_local_sites_cli/sites_parameter_list)

[About Site objects](../)

[Working with Local Sites (command line)](../managing_local_sites_cli)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
