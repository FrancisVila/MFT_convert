{
    "title": "Configure SiteMinder for SecureTransport integration",
    "linkTitle": "Configure SiteMinder for SecureTransport integration",
    "weight": "140"
}To successfully integrate <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> with SiteMinder, SiteMinder must be configured appropriately using the SiteMinder administration system. This topic provides general guidelines for configuring SiteMinder 4.X and 5.X. For more information, refer to the SiteMinder documentation.

1.  Create a SiteMinder agent that <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> is to use to connect to the SiteMinder Policy Server.  
    When creating the agent, either select the **4.X** compatibility option and fill in the **IP address** of the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server (not the SiteMinder Policy server) and **Shared secret** or select the **5.X** compatibility option and fill in the name of the agent only.
2.  Create an authentication scheme by selecting one of the following types:
    -   **Basic Template** – password authentication
    -   **X509 Client Cert Template** – certificate authentication
    -   **X509 Client Cert or Basic Template** – certificate *or* password authentication
    -   **X509 Client Cert and Basic Template** – certificate *and* password authentication
3.  Create a Realm, selecting the agent and authentication scheme that have been created for <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>.
4.  Create new rules under the Realm.
5.  Create a Response that returns the attributes required by the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> SiteMinder settings. For details, see <a href="../../c_st_authentication/t_st_siteminderintegrationconfiguration#SetupMenu_1217491348_1151043" class="MCXref xref">SiteMinder integration configuration</a>.
6.  Apply the new rules to the necessary SiteMinder Policy.