{
    "title": "Network Architecture",
    "linkTitle": "Network Architecture",
    "weight": "50"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Overview

As described in the previous topic, Gateway enables you to transfer different types of file between different applications, both within a local network and over the Internet.

You can integrate Gateway into a large variety of network architectures. The architecture you select depends on the Gateway functions you want to use.

## Local Area Networks

### Inter-platform file transfers

You can deploy Gateway in your local corporate network, to make use of its capacity to transfer variously-formatted files between different platforms using a variety of different protocols.

<img src="/Images/Gateway/Archi2_Sentinel_756x613.png" class="maxWidth" />

### Sentinel monitoring

You can enhance your ability to track the activities of your Axway network applications by adding Sentinel monitoring.

## Linking your local network to the Internet

### <span class="mc-variable axway_variables.Company_Name variable">Axway</span> <span class="mc-variable suite_variables.SecureRelayName variable">Secure Relay</span> option

You can use your Gateway as an Internet gateway. The Gateway product includes <span class="mc-variable suite_variables.SecureRelayName variable">Secure Relay</span> components that enable you to deploy Gateway in a secured DMZ configuration.

Secure operation is assured by:

-   A Secure Relay Master Agent that you install and run natively on the Gateway
-   One or more Secure Relay Router Agents, delivered as part of the Gateway package, that you install in the DMZ

Together, these two components:

-   Manage connections to the outside world for file exchanges, preventing external partners from directly accessing Gateway
-   Handle streaming of data flows, to and from the Internet

<img src="/Images/Gateway/Archi4_Internet_756x586.png" class="maxWidth" />

### Gateway-to-Gateway DMZ option

Alternatively, you can deploy two Gateways in a bridged private/public DMZ configuration.

<img src="/Images/Gateway/Archi_DMZ_2GTW_756x567.png" class="maxWidth" />

## Using EDIINT protocols

You can deploy Gateway as an EDIINT file transfer tool, creating links to your business trading partners via the Internet.

<img src="/Images/Gateway/Archi_EDIINT_756x578.png" class="maxWidth" />

## Linking your local network to a WAN

You can use Gateway to link a local network to an external corporate network.

<img src="/Images/Gateway/Archi_WAN_756x587.png" class="maxWidth" />

## Interconnecting applications over multiple local and remote networks

You can make use of the multiple protocol handling capacities of Gateway to deploy the product for exchanges over multiple networks.

<img src="/Images/Gateway/Archi_Multi_4_756x866.png" class="maxWidth" />

[Next topic](../ov_file_transfers)

Related topics

[DMZ deployment](../ov_dmz_deployment)

[About Axway Sentinel](../../connectors_about/sentinel_about)

[About EDIINT](../../protocols_about/ediint_about)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
