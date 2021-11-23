{
    "title": "Adding an Integrator Gateway CommAdapter",
    "linkTitle": "Adding an Integrator Gateway CommAdapter",
    "weight": "110"
}[About the Integrator Gateway CommAdapter](#About)

[Prerequisites](#Prerequisites)

[Procedure](#Procedure)

<span id="About"></span>

## About the Integrator Gateway CommAdapter

The Integrator Gateway CommAdapter provides the services that enable Integrator to exchange messages with Gateway.

This CommAdapter uses a dedicated
processing task on the Integrator Server which we create as part of the procedure. This configuration step is optional, but it is recommended because it
improves the performance of the Gateway
connector by reserving dedicated processes.

<span id="Prerequisites"></span>

## Prerequisites

The Integrator Axway Server object and CommNetwork must exist in Composer.

<span id="Procedure"></span>

## Procedure

1.  In the Composer Topography workbench, open the Integrator Axway Server object.
2.  On the **Core Tasks** tab of the *Axway Server properties* window, create a processing task dedicated to Gateway.
    This step is not mandatory, but it is recommended, since it enables you to have
    separate processes and improves the performance of the Gateway connector.
3.  On the **Communication** tab, right-click the CommNetwork and select add a
    CommAdapter. Select **Gateway** for the CommAdapter type.
4.  Complete the
    **Configuration** sub-tab:
5.  Accept the default values for the other parameters on the **Advanced** sub-tab.
6.  On the **Task references** sub-tab, select the processing task created
    in step 2.
7.  Check, save and close the Axway Server object.
8.  Send the Axway Server object to the execution server via the **Send to
    Server** command. The status of the Axway Server is set to Committed.  
    **Note**: Since the Gateway CommAdapter is a client CommAdapter, there is no need to
    create a CommPoint.

Links to documentation set for Axway Gateway {{< Gateway/releasenumber  >}}:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
