{
    "title": "Configuring security for SMTP",
    "linkTitle": "Configuring security for SMTP",
    "weight": "250"
}{{< Gateway/componentlongname  >}}: Protocols

[Establishing a secure link with SSL/TLS](#Establishing_a_secure_link_with_SSL_TLS)

[Defining an authentication method](#Defining_an_authentication_method)

<span id="Establishing_a_secure_link_with_SSL_TLS"></span>

## Establishing a secure link with SSL/TLS

You can configure Gateway to use SSL or TLS security for SMTP:

1.  In the configuration menu, select **Connectivity > Internet protocols > MAIL > SMTP**.
2.  Click <span style="font-weight: bold;">Advanced...</span>.
3.  Check <span style="font-weight: bold;">Use SSL/TLS</span>.
4.  Click <span style="font-weight: bold;">OK</span>.

You can configure Gateway to use TLS in implicit and explicit mode for an SMTP connection. Although most SMTP servers are secured explicitly, some accept implicit TLS connections, and SMTP servers of a proxy mailer may impose TLS in implicit mode.

<span id="Defining_an_authentication_method"></span>

## Defining an authentication method

The authentication methods supported by Gateway for the SMTP protocol (all of which are standard SASL mechanisms) are:

-   LOGIN
-   ANONYMOUS
-   PLAIN

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
