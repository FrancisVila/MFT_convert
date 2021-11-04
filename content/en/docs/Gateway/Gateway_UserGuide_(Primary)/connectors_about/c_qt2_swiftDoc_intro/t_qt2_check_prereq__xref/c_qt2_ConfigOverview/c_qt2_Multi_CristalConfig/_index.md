{
    "title": "Multiple CRISTAL configurations",
    "linkTitle": "Multiple CRISTAL configurations",
    "weight": "370"
}You can adapt the TARGET2 object configuration to support multiple JMS/CRISTAL back-end applications, each one working for a specific institution and using a specific BIC code and Local Trading Partner.

In this case, you use Decision Rules to filter incoming flows from TARGET2 depending on the Local Trading Partner alias. Decision Rules use Models to forward the messages to the respective Remote JMS Sites.

Requests coming from the different back-office JMS Sites can be forwarded to different SWIFTNet Remote Sites by duplicating the FROM\_BO\_TO\_SSP and TG2DIR\_GETFILE\_SSP Decision Rules and their associated Models.

Related topics

[Multiple CRISTAL configuration: example 1](c_qt2_multi_cristalfg_exmpl1)

[Multiple CRISTAL configuration: example 2](c_qt2_multi_cristalcfg_exmpl2)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
