{
    "title": "Launching tests from the Gateway GUI",
    "linkTitle": "Launching tests from the Gateway GUI",
    "weight": "320"
}To launch a test case from the Gateway GUI you complete the following *New Transfer Request* screens:

## General tab

<img src="/Images/Gateway/0300001E.png" class="maxWidth" />

In the **Model** field, enter the name of the model called by Gateway to execute the test case. For the current set of test cases you always use the Model FROM\_BO\_TO\_SSP.

## Attributes tab

<img src="/Images/Gateway/0300001F.png" class="maxWidth" />

In the **File component** field, enter the path to the `InitialRequest.xml` file. By default, this file is located at: `C:\Axway\qt2\xml`

## Details tab

<img src="/Images/Gateway/03000020.png" class="maxWidth" />

In the **Param 1** field, enter the number of the test case you want to run. Select a test case from the table provided in [Pre-built test cases](../).

## SWIFTNet tab

<img src="/Images/Gateway/03000021.png" class="maxWidth" />

In the **Destination partner** and **Originator partner** fields, enter the names of the appropriate Remote Sites.

Links to documentation set for Axway Gateway {{< Gateway/releasenumber  >}}:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
