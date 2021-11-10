{
    "title": "Importing an Integrator Server object set",
    "linkTitle": "Importing an object set from an Integrator Server",
    "weight": "130"
}[About importing the object set](#about_import_obj_set)

[Prerequisites](#prereqs_import_obj_set)

[Procedure](#procedure_import_obj_set)

[After importing the object set](#after_import_obj_set)

<span id="about_import_obj_set"></span>

## About importing the object set

To populate the Axway Server object that represents the Integrator Server in
Composer, you must import a set of objects from that Integrator Server instance.

<span id="prereqs_import_obj_set"></span>

## Prerequisites

Before you can import an object set you must:

-   Install an Integrator Server instance
-   Start the Integrator Server instance, or if the Server is already running, restart the Integrator Server.
-   In Composer, create an Axway Server object to represent the Integrator Server instance.  
    [View procedure](../t_cmpsr_create_syncserv_intgr)

<span id="procedure_import_obj_set"></span>

## Procedure

1.  In the Composer Topography workbench, right-click the Integrator Axway Server object in the navigator pane and select
    **Advanced actions > Import Object-Set** from the context menu.  
    Composer imports Integrator Server Core Tasks from the Server instance to the Axway Server
    that you created.
    After you import the Object-Set, the Axway Server has the
    Composer life cycle status "Committed" .
2.  Right-click the Axway Server object in the navigator pane and select
    **Advanced actions > Back to design** from the context menu.
    The object status changes to Checked.

<span id="after_import_obj_set"></span>

## After you import the object set

You can now add a CommAdapter to the Integrator Axway Server object.

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
