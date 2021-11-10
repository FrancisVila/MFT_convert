{
    "title": "Creating a Host",
    "linkTitle": "Creating a Host",
    "weight": "120"
}## About the Host object

A Host object specifies the machine where you have installed the component server instance(s).

Before you create the Host object, you must create at least one CommNetwork object.

## Procedure

1.  In the Composer Topography workbench, select **File > New > Topography > Host** or right-click the **Host** folder in the navigator pane and select **Host**.  
    Composer displays the "Host properties" screen.
2.  In the **General** tab:
    -   **Name** – Enter a name for the Host.
    -   **HostGroup**: – Optionally, from the drop-down list, select a HostGroup that the Host machine belongs to.
    -   **OS type** – From the drop-down list, select the operating system that supports the Host.
3.  In the **Communication** tab:
    -   Click the **Create a CommNetwork** icon.
    -   Composer adds a CommNetwork node to the tree in the left pane, and opens the CommNetwork properties window in the right pane.
    -   In the **CommNetwork** field of the right pane, select a CommNetwork from the drop-down list.
    -   On the **TCP** sub-tab, enter the host name or IP address of the host where this CommNetwork runs.
4.  From the **File** menu select:
    -   **Check** to verify that all mandatory object definitions are correct.
    -   **Save** to save the object definition in the Composer database.

    <!-- -->

    -   **Close** to close the object properties window.

## After you create the Host object

After you create the Host, it is saved to the Composer database and is available for use.

You can now create an Axway Server objects that represent the Axway Server instances that are located on this Host.

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
