{
    "title": "Upgrade SecureTransport on Windows",
    "linkTitle": "Upgrade SecureTransport on Windows",
    "weight": "90"
}If you are using an external database, it must be upgraded to a [supported version](https://docs.axway.com/bundle/SecureTransport_55_AdministratorGuide_allOS_en_HTML5/page/Content/AdministratorsGuide/introduction/r_st_Axway_and_third-party_software_support.htm#Database) prior to upgrading {{< SecureTransport/componentshortname  >}} to version {{< SecureTransport/componentversion  >}} or a new instance of the respective database should be deployed and you should migrate the existing {{< SecureTransport/componentshortname  >}} data to the new instance. Refer to the documentation for your database for the upgrade or migration procedure. If additional information is needed, contact your database vendor’s support.

Oracle users whose system privileges were granted through a role can update {{< SecureTransport/securetransportname  >}} to version {{< SecureTransport/componentversion  >}} only using the console.

The following topics provide instructions for upgrading an existing {{< SecureTransport/securetransportname  >}} installation:

-   <a href="upgrading_from_st_5.4_win_console" class="MCXref xref">Upgrade from SecureTransport 5.4 using the console</a> - Provides how-to instructions for upgrading from {{< SecureTransport/componentshortname >}} 5.4 using the console.
-   <a href="upgrade-from-st-5.4-win-gui" class="MCXref xref">Upgrade from SecureTransport 5.4 using the GUI</a> - Provides how-to instructions for upgrading from {{< SecureTransport/componentshortname >}} 5.4 using the GUI.
-   <a href="../../recover-previous-installation-win" class="MCXref xref">Recover your previous SecureTransport installation on Windows</a> - Provides how-to instructions for recovering your previous {{< SecureTransport/componentshortname >}} installation.
