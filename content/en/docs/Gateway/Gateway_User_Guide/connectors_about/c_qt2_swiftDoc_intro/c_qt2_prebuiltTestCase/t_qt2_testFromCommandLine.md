{
    "title": "Launching tests via line commands",
    "linkTitle": "Launching tests via line commands",
    "weight": "310"
}To launch a test case via a Gateway line command, use a command in the format of the following example:

.../QT2> peltrans -ml FROM\_BO\_TO\_SSP -fc xml/InitialRequest.xml -param1 0000

Where:

-   <span class="bold_in_para">-ml</span> is the name of the Model called to execute the test case  
    For the current set of test cases you always use the Model FROM\_BO\_TO\_SSP.
-   <span class="bold_in_para">-fc </span>is the path to the XML file that Gateway uses to generate the initial request to SSP.  
    Gateway requires the file <span class="code">InitialRequest.xml</span> to generate the initial request for all test cases.
-   <span class="bold_in_para">-param1</span> is the test case number  
    Select a test case number from the table in [Pre-built test cases](../).

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
