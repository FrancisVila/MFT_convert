{
    "title": "Multiple CRISTAL configuration: example 1",
    "linkTitle": "Example 1",
    "weight": "400"
}## Remote Sites

-   SWIFT1 - SWIFTNet
-   CRISTAL\_IN1  - JMS
-   CRISTAL\_OUT1 - JMS
-   CRISTAL\_ERR1 - JMS
-   CRISTAL\_FILE1 – PeSIT E

## Trading Partner

-   QT2\_TP\_LOCAL1

## Models

-   FROM\_BO\_TO\_SSP1 - linked to the SWIFTNet Remote Site
-   TG2DIR\_GETFILE\_SSP1 - linked to the SWIFTNet Remote Site
-   TO\_BO\_QT2\_FILE\_OK1 - linked to CRISTAL\_FILE1 Remote Site
-   TO\_BO\_QT2\_FILEMSG\_KO1 - linked to CRISTAL\_ERR1 Remote Site
-   TO\_BO\_QT2\_FILEMSG\_KO\_P1 - linked to CRISTAL\_ERR1 Remote Site
-   TO\_BO\_QT2\_GETFILE\_KO1 - linked to CRISTAL\_ERR1 Remote Site
-   TO\_BO\_QT2\_OK1 - linked to CRISTAL\_OUT1 Remote Site

## Decision Rules

-   FROM\_BO\_TO\_SSP1 - Model FROM\_BO\_TO\_SSP1
-   INCOMING\_GETFILE\_SSP1 - batch call: tg2file TO\_BO\_QT2\_FILE\_OK1 TO\_BO\_QT2\_FILEMSG\_KO\_P1 &(local\_copy\_directory1)
-   INCOMING\_GETFILE\_SSP\_KO1 - Model TO\_BO\_QT2\_GETFILE\_KO1
-   INCOMING\_SSP\_IA\_REQUEST – batch call: ssp\_pull\_s.sh
-   INCOMING\_SSP\_IA\_RESPONSE1 -  batch call: tg2msg TO\_BO\_QT2\_OK1 TO\_BO\_QT2\_FILEMSG\_KO\_P1
-   OUTGOING\_SSP\_IA\_REQ\_KO1 - Model TO\_BO\_QT2\_FILEMSG\_KO1
-   TG2DIR\_GETFILE\_SSP1 - Model TG2DIR\_GETFILE\_SSP1

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
