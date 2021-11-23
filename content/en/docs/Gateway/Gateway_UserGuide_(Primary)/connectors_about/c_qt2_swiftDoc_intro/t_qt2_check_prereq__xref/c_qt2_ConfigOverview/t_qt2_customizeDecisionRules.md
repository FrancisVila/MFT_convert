{
    "title": "Customizing Gateway Decision Rules for TARGET2",
    "linkTitle": "Customizing Decision Rules",
    "weight": "360"
}After importing the TARGET2 object set, you must modify the configuration of the Decision Rule objects to correspond to your network environment.

After you import Decision Rules:

1.  In Gateway Navigator, right-click **Event Management\\Transfer Change State\\Default**.
2.  Click **Properties**.
3.  In the **General** tab:
    -   Select **Active**
    -   For Default execution type select **No action**
    -   Select **Link input and output transfers**
    -   For Log level select **Full**

      
    <img src="/Images/Gateway/0300001B.png" class="maxWidth" />
4.  In the **Linked rules** tab:
    -   Move Decision Rules from Available rules to Linked rules using the **Link** button.
    -   Click **OK**.

      
    <img src="/Images/Gateway/0300001C.png" class="maxWidth" />  
5.  Customize parameters according to your configuration requirements.  
     

Links to documentation set for Axway Gateway {{< Gateway/releasenumber  >}}:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
