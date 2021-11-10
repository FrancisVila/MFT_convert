{
    "title": "SWIFTNet connector",
    "linkTitle": "SWIFTNet connector",
    "weight": "250"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Connectors

[SWIFTNet and Gateway](#SWIFTNet_and_Gateway)

[Required Gateway objects for SWIFTNet](#Required_objects)

<span id="SWIFTNet_and_Gateway"></span>

## SWIFTNet and Gateway

The Gateway SWIFTNet connector enables you to perform the following roles:

-   Transport and route SWIFTNet messages between partners and platforms
-   Manage SWIFTNet file/message transfers

### Functionality

The Gateway SWIFTNet connector offers the following functions:

-   SWIFTNet data exchange, with full support of:
    -   FileAct/InterAct services
    -   Real Time/Store-and-Forward delivery modes
-   Transfer management:
    -   Parallel processing (inbound/outbound)
    -   Priority handling
    -   Reliability (if a transfer is not successful, Gateway retries)
-   Routing:
    -   Automated transfer routing
-   Monitoring:
    -   Retry, restart on failure
    -   Event cycle linking between applications

<span id="Required_objects"></span>

## Required Gateway objects for SWIFTNet

You need to create the following Gateway objects to be able to exchange and/or route SWIFTNet files and messages.

### Remote Site object

In the Remote Site object you specify the characteristics of the SWIFTNet access point. If you have several access points, create a Remote Site object for each one.

### Local Trading Partner object

In the Local Trading Partner object you specify your local SWIFTNet identification information.

### Remote Trading Partner object

In the Remote Trading Partner object you specify your business partner's SWIFTNet identification information. In addition, you specify SWIFTNet services and delivery mode.

### Transfer Request object

In the Transfer Request object you describe how a file is sent or received (using SWIFTNet FileAct) or how a message is sent or received (using SWIFTNet InterAct). Amongst other parameters, it specifies:

-   The SWIFTNet Remote Site
-   The SWIFTNet Local Trading Partner object
-   The SWIFTNet Remote Trading Partner object
-   ...

### Acknowledgment Message object

In the Acknowledgement Message object you specify information concerning receipts using SWIFTNet FileAct in Real Time.

### Decision Rule object and Model object

If you want to route SWIFTNet files and/or messages to another business partner, use the Decision Rule object and Model object.

Related topics

[About SWIFTNet](../)

[Configuring the <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>/SWIFTNet environment](swiftnet_configuring)

[Working with <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>/SWIFTNet](swiftnet_working_with)

[SWIFTNet state transitions](../swiftnet_backup_sites/swiftnet_state_transitions)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
