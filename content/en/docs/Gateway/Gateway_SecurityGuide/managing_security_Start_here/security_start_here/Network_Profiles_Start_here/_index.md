{
    "title": "Network Profiles",
    "linkTitle": "Network Profiles",
    "weight": "170"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Security

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

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
