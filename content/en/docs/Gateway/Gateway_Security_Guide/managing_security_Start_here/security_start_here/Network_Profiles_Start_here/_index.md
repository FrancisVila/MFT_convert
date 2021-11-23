{
    "title": "Network Profiles",
    "linkTitle": "Network Profiles",
    "weight": "170"
}{{< Gateway/componentlongname  >}}: Managing Security

Network Profiles associate an incoming network connection request with a Security Profile. If no Network Profile matches the incoming connection, or if the matched Profile does not refer to an existing Security Profile, the session is interrupted. If TLS or SSH is not enabled in the selected Network Profile, the connection does not use the Security server.

Matching an incoming connection with a Network Profile is based on:

-   Destination address and SAP (local)
-   Origin address and SAP (remote)

A Network Profile comprises:

-   Destination address pattern (address/SAP)
-   Origin address pattern (address/SAP)
-   Type option that indicates whether or not to use TLS or SSH security
-   Security Profile name (optional and only used if TLS or SSH option is activated)

All patterns can contain the following substitution characters:

-   \* matches any number of characters
-   ? matches a single character or no characters

You can define Network Profiles either via the GUI or via command line.

Related topics

[Managing Network Profiles](network_profiles_(gui))

[Managing Network Profiles (command line)](managing_network_profiles_cli)

 

Links to documentation set for Axway Gateway {{< Gateway/releasenumber  >}}:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
