{
    "title": "Multiple CRISTAL configuration: example 2",
    "linkTitle": "Example 2",
    "weight": "400"
}## Remote Sites

-   SWIFT2 - SWIFTNet
-   CRISTAL\_IN2 - JMS
-   CRISTAL\_OUT2 - JMS
-   CRISTAL\_ERR2 - JMS
-   CRISTAL\_FILE2 – PeSIT E

## Trading Partner

-   QT2\_TP\_LOCAL2

## Models

-   FROM\_BO\_TO\_SSP2 - linked to the SWIFTNet Remote Site
-   TG2DIR\_GETFILE\_SSP2 - linked to the SWIFTNet Remote Site
-   TO\_BO\_QT2\_FILE\_OK2 - linked to CRISTAL\_FILE2 Remote site
-   TO\_BO\_QT2\_FILEMSG\_KO2 - linked to CRISTAL\_ERR2 Remote Site
-   TO\_BO\_QT2\_FILEMSG\_KO\_P2 - linked to CRISTAL\_ERR2 Remote Site
-   TO\_BO\_QT2\_GETFILE\_KO2 - linked to CRISTAL\_ERR2 Remote Site
-   TO\_BO\_QT2\_OK2 - linked to CRISTAL\_OUT2 Remote Site

## Decision Rules

-   FROM\_BO\_TO\_SSP2 - Model FROM\_BO\_TO\_SSP2
-   INCOMING\_GETFILE\_SSP2 - batch call: tg2file TO\_BO\_QT2\_FILE\_OK2 TO\_BO\_QT2\_FILEMSG\_KO\_P2 &(local\_copy\_directory2)
-   INCOMING\_GETFILE\_SSP\_KO2 - Model TO\_BO\_QT2\_GETFILE\_KO2
-   INCOMING\_SSP\_IA\_REQUEST – batch call: ssp\_pull\_s.sh
-   INCOMING\_SSP\_IA\_RESPONSE2 - batch call: tg2msg TO\_BO\_QT2\_OK2 TO\_BO\_QT2\_FILEMSG\_KO\_P2
-   OUTGOING\_SSP\_IA\_REQ\_KO2 - Model TO\_BO\_QT2\_FILEMSG\_KO2
-   TG2DIR\_GETFILE\_SSP2 - Model TG2DIR\_GETFILE\_SSP2

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
