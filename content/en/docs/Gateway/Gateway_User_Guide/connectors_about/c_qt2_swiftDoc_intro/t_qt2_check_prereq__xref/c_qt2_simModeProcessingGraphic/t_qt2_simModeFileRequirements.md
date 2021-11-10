{
    "title": "Transfers and message type",
    "linkTitle": "Transfers and message type",
    "weight": "350"
}To run the TARGET2 module in simulation mode, a SWIFT loop configuration must be possible in which you send messages/files to yourself. Users must have access to a SWIFT InterAct service and a SWIFT identity that allows them to send InterAct to themselves.

The file sent to the simulation (InitialRequest.xml in the example) can have any content. The only requirements are:

-   The file must be embedded:
    -   File content must be contained between the tags <span class="code">&lt;SwInt:RequestPayload></span> and <span class="code">&lt;/SwInt:RequestPayload></span>
    -   File content must not conflict with XML parsing
-   The file must be an XML file. For example, you could use the <span class="code">InitialRequest.xml</span> file provided in the QT2 directory

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
