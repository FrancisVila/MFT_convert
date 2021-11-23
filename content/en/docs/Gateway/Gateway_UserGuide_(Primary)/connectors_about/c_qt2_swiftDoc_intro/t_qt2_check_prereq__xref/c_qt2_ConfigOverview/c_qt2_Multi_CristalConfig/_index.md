{
    "title": "Multiple CRISTAL configurations",
    "linkTitle": "Multiple CRISTAL configurations",
    "weight": "380"
}You can adapt the TARGET2 object configuration to support multiple JMS/CRISTAL back-end applications, each one working for a specific institution and using a specific BIC code and Local Trading Partner.

In this case, you use Decision Rules to filter incoming flows from TARGET2 depending on the Local Trading Partner alias. Decision Rules use Models to forward the messages to the respective Remote JMS Sites.

Requests coming from the different back-office JMS Sites can be forwarded to different SWIFTNet Remote Sites by duplicating the FROM\_BO\_TO\_SSP and TG2DIR\_GETFILE\_SSP Decision Rules and their associated Models.

Related topics

[Multiple CRISTAL configuration: example 1](c_qt2_multi_cristalfg_exmpl1)

[Multiple CRISTAL configuration: example 2](c_qt2_multi_cristalcfg_exmpl2)

 

Links to documentation set for Axway Gateway {{< Gateway/releasenumber  >}}:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
