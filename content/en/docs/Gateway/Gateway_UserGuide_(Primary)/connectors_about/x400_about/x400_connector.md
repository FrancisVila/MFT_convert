{
    "title": "X.400 connector",
    "linkTitle": "X.400 connector",
    "weight": "270"
}{{< Gateway/componentlongname  >}}: Connectors

[Introduction](#intro)

[This version](#this_version)

[X.400 and Gateway](#x400_and_gw)

[Required Gateway objects for X.400](#required_objects)

This topic introduces the X.400 connector in Gateway.

<span id="intro"></span>

## Introduction

The X.400 connector enables Gateway to function as an X.400 host. Gateway can connect simultaneously to any number of Message Transfer Agents (MTA) and Message Stores (MS).

You can use the X.420 protocol to send and receive EDI messages. The Gateway X.400 connector is a communication server that uses this protocol.

The user has access to a system that handles sending, receiving, and acknowledgment of messages.

<span id="this_version"></span>

## This version

This version of Gateway supports X.420 on TCP/IP.

This version has been designed to work with Axway Integrator.

### Limitations

Routing and Sentinel tracking do not include X.400-specific fields.

<span id="x400_and_gw"></span>

## X.400 and Gateway

The Gateway X.400 connector enables you to perform the following roles:

-   Transport and route X.400 messages between partners and platforms
-   Manage X.400 message transfers

You can also use Integrator in conjunction with Gateway for advanced message processing.

<span id="required_objects"></span>

## Required Gateway objects for X.400

You need to create the following Gateway objects to be able to exchange and/or route X.400 messages.

### Remote Site object

In the Remote Site object you specify the remote MTA and MS retrieve methods. You can create as many Remote Sites as required.

### Transfer Request object

In the Transfer Request object you describe how a message is sent or received using the X.420 protocol.

 

Related topics

[About X.400](../)

[Configuring Gateway for X.400](../x400_configuring)

[Managing X.400 partners](../x400_managing_partners)

[Working with X.400](../x400_working_with)

[X.400 log messages](../../../log_messages_about/x400_messages)

 

Links to documentation set for Axway Gateway {{< Gateway/releasenumber  >}}:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
