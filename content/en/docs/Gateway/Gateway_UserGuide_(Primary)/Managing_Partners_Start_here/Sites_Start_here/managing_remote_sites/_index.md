{
    "title": "Remote Sites",
    "linkTitle": "Remote Sites",
    "weight": "160"
}{{< Gateway/componentlongname  >}}: Managing Partners

[About Remote Sites](#About)

[Creating a Remote Site](#Creating_a_new_Site)

[Displaying a list of Remote Sites](#Displaying_a_list_of_all_Remote_Site_objects)

[Displaying selected Remote Sites](#Displaying%20selected%20Remote%20Site%20objects)

[Viewing Remote Site attributes](#Viewing_Remote_Site_attributes)

[Modifying a Remote Site](#Modifying_a_Remote_Site)

[Deleting a Remote Site](#Deleting_a_Remote_Site)

<span id="About"></span>

## About Remote Sites

When you install Gateway, it creates a set of Remote Sites adapted for use with different protocols, and stores them in your database. The following sections describe how to add your own Sites and how to manage all of the available Sites.

<span id="Creating_a_new_Site"></span>

## Creating a Remote Site

To create a new Remote Site object:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:  
    Partner Management > Sites
2.  Right-click the **Remote Site** sub-node and select <span style="font-weight: bold;">New</span>  
    Gateway displays the <span id="New_Remote_Site_creation_window"></span><span style="font-style: italic;">New Remote Site</span> window.  
    The set of fields and tabs displayed for Remote Site objects depends on the protocol that you select. The initial screen displays three tabs:

-   <span style="font-weight: bold;">General</span>
-   <span style="font-weight: bold;">Options</span>
-   <span style="font-weight: bold;">Network address</span>

When you select the protocol on the <span style="font-weight: bold;">General</span> tab, the tabs displayed will change.

Complete the tabs of the <span style="font-style: italic;">New Remote Site</span> window according to your requirements.  
The following topics describe the fields in each tab and their possible values:

[<span style="font-weight: bold;">General</span> tab](remote_site_general_tab)

[<span style="font-weight: bold;">Options</span> tab](remote_site_options_tab)

[<span style="font-weight: bold;">Network address</span> tab](remote_site_network_address_tab)

Protocol-specific tabs:

-   [<span style="font-weight: bold;">PeSIT</span>](remote_site_pesit_tab) [tab](remote_site_pesit_tab)
-   [<span style="font-weight: bold;">OFTP</span> tab](remote_site_oftp_tab) (Odette)
-   [<span style="font-weight: bold;">FTP/HTTP</span> tab](remote_site_ftp_http_tab)
-   [<span style="font-weight: bold;">PEL</span> tab](remote_site_pel_tab)
-   [<span style="font-weight: bold;">POP3</span> tab](remote_site_pop3_tab)
-   [<span style="font-weight: bold;">SMTP</span> tab](remote_site_smtp_tab)
-   [<span style="font-weight: bold;">SFTP</span> tab](remote_site_sftp_tab)
-   [<span style="font-weight: bold;">SWIFTNet</span> tab](remote_site_swiftnet_tab)
-   [<span style="font-weight: bold;">JMS</span> tab](remote_site_jms_tab)
-   [<span style="font-weight: bold;">X.400</span> tab](remote_site_x400_tab)

[<span style="font-weight: bold;">Net security</span> tab](remote_site_net_security_tab)

After completing the fields, click <span style="font-weight: bold;">OK</span> to accept the values and close the window.

<span id="Displaying_a_list_of_all_Remote_Site_objects"></span>

## Displaying a list of Remote Sites

To display a list of all Remote Site objects stored in the database:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:  
    Partner Management > Sites
2.  Click the <span style="font-weight: bold;">Remote Site</span> sub-node.  
    In the right pane, Gateway displays a list of all Remote Sites.

<span id="Displaying selected Remote Site objects"></span>

## Displaying selected Remote Sites

If your Gateway configuration includes multiple Remote Site objects, you can limit the display by applying display selection criteria.

To limit the Remote Site object display:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:  
    Partner Management > Sites
2.  Click the <span style="font-weight: bold;">Remote Site</span> sub-node.  
    Gateway displays a list of all Remote Sites in the right pane.
3.  Right-click the <span style="font-weight: bold;">Remote Site</span> sub-node, then select <span style="font-weight: bold;">Select...</span> from the context menu.  
    Gateway displays the <span style="font-style: italic;">Select Remote Sites</span> window.
4.  In the <span style="font-style: italic;">Select Remote Sites</span> window, enter one or more of the following Remote Site attributes as selection criteria:

-   Remote Site Alias
-   Protocol
-   Network Type
-   Network address

Click <span style="font-weight: bold;">OK</span>.  
Gateway regenerates the right window display list, taking into account your selection criteria.

<span id="Viewing_Remote_Site_attributes"></span>

## Viewing Remote Site attributes

To view the attributes of a specific Remote Site:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:  
    Partner Management > Sites
2.  Click the <span style="font-weight: bold;">Remote Site</span> sub-node.  
    Gateway displays a list of all Remote Sites in the right pane.
3.  In the right pane, right-click the name of the Remote Site for which you want to view the Site attributes. Select <span style="font-weight: bold;">View...</span> from the context menu.  
    Gateway displays the <span style="font-style: italic;">Remote Sites (read only)</span> window. This window provides you with a view of all attributes for the selected Remote Site.
4.  When you have finished viewing the information, click <span style="font-weight: bold;">Close</span> to quit the window.

<span id="Modifying_a_Remote_Site"></span>

## Modifying a Remote Site

To modify the attributes of a Remote Site:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:  
    Partner Management > Sites
2.  Click the <span style="font-weight: bold;">Remote Site</span> sub-node.  
    Gateway displays a list of all Remote Sites in the right pane.
3.  In the right pane, right-click the name of the Remote Site for which you want to modify the Site attributes. Select <span style="font-weight: bold;">Modify...</span> from the context menu.  
    Gateway displays the <span style="font-style: italic;">Remote Site</span> editing window. This window has the same tabs and fields as the <span style="font-style: italic;">[New Remote Site](#New_Remote_Site_creation_window)</span> window above.
4.  Enter new values in the editing fields as required.
5.  When you have finished modifying the attributes, click <span style="font-weight: bold;">OK</span> to accept the new values and close the window.

<span id="Deleting_a_Remote_Site"></span>

## Deleting a Remote Site

To delete an existing Remote Site:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the nodes:  
    Partner Management > Sites
2.  Click the <span style="font-weight: bold;">Remote Site</span> sub-node.  
    Gateway displays a list of all Remote Sites in the right pane.
3.  In the right pane, right-click the name of the Remote Site you want to delete. Select <span style="font-weight: bold;">Delete...</span> from the context menu.  
    Gateway displays a confirmation dialog box.
4.  In the confirmation dialog box, click <span style="font-weight: bold;">Yes</span> to confirm the delete operation.  
    Alternatively, click <span style="font-weight: bold;">No</span> or <span style="font-weight: bold;">Cancel</span> to abandon the operation.  
    Gateway deletes the Remote Site from the database and removes the entry from the display window.

Related topics

[Site objects: Parameters List](../managing_local_sites_cli/sites_parameter_list)

[About Site objects](../)

[Working with Remote Sites (command line)](../managing_local_sites_cli/managing_remote_sites_cli)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
