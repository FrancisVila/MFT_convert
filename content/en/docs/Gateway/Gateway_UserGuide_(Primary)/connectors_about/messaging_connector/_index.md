{
    "title": "Axway Messaging connector",
    "linkTitle": "Axway Messaging",
    "weight": "180"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Connectors

[<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span> and Axway Messaging](#Gateway_and_Messaging)

[Operational overview](#Operational_overview)

[Axway Messaging connector](#Messaging_connector_concepts)

[Linking <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span> to Axway Messaging: Overview](#Linking_Gateway_Messaging)

<span id="Gateway_and_Messaging"></span>

## <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span> and Axway Messaging

This section introduces Axway Messaging (formerly XMS) and the Axway Messaging connector in Gateway.

Gateway and the components that support Messaging were originally designed to work in different environments.

-   <span style="font-weight: bold;">Gateway</span> operates in a file transfer environment, handling file exchanges via multiple standardized protocols across local networks, extranets and the Internet.
-   <span style="font-weight: bold;">Messaging</span> is Message-Oriented Middleware. The Messaging components (servers, clients and administrative tools) provide an environment in which applications can exchange messages without directly communicating with each other.

The <span style="font-weight: bold;">Axway Messaging connector</span> provides you with the means to link these two environments, enabling you to:

-   Transmit Messaging formatted application messages across your network (or across the Internet)
-   Redirect any file received at the Gateway to a Messaging client in the form of an Axway Messaging message

<img src="/Images/Gateway/XMSConnector2.png" class="maxWidth" />

 

<span id="Operational_overview"></span>

## Operational overview

### From Gateway to Messaging

When Gateway is operating in <span style="font-style: italic;">server/receiver</span> mode or <span style="font-style: italic;">client/receiver</span> mode, it can transform and route any incoming file to one or more Messaging servers.

To do this, Gateway processes the file and the associated technical (transfer) parameters and uses the information to generate a Messaging format envelope. Gateway then redirects the enveloped file to a Messaging Server message queue.

### From Messaging to Gateway

For Messaging formatted messages deposited to an Axway Messaging message queue, one or more Messaging servers can direct the messages to Gateway through the connector for routing via one of the protocols supported by Gateway.

To do this, Gateway:

-   Acts as an application that <span style="font-style: italic;">consumes</span> a message deposited to the Axway Messaging message queue
-   Extracts and writes the message content to disk, and extracts the information necessary for the message transfer
-   Forwards the reformatted message to the target application via a Gateway Transfer Request

<span id="Messaging_connector_concepts"></span>

## Axway Messaging connector

### Connectors

An <span style="font-style: italic;">Axway Messaging connector</span> is a group of technical components that enables Gateway and Messaging to exchange data. You define connectors using either the GUI or the command line interface. Each connector operates in a single direction either from the Gateway to a Messaging server queue or vice versa. For each Messaging server it is typical (but not mandatory) to create three connectors, one each for:

-   Messages from the Messaging server to Gateway
-   Messages from Gateway to the Messaging server message queue
-   Messages from Gateway to the Messaging server error message queue

### Property Lists

In the Axway Messaging environment, each message contains the following parts:

-   <span style="font-style: italic;">Body</span>: contains the information that the sending application sends to the receiving application
-   <span style="font-style: italic;">Header</span>: contains attributes that provide details about the message. Sending applications specify the values of these predefined attributes. Among the details in the header are the following:
    -   Names of the sending and receiving applications
    -   Names of the sending and receiving servers
-   <span style="font-style: italic;">Header extension</span>: contains properties that provide additional details about the message. Properties <span style="font-style: italic;">extend</span> a header with application-defined properties. Sending applications define both the names and the values of properties. Because properties are optional, header extensions can be empty

A Gateway <span style="font-weight: bold;">Property List</span> contains a description of the <span style="font-style: italic;">header extension</span> part of the Axway Messaging message. For each field of the <span style="font-style: italic;">header extension</span> the Property List contains a name and data type.

For files received at the Gateway, and routed to a Messaging queue, Gateway uses the Property List to provide information about the current transfer to the application that is the destination of the Axway Messaging message.

For files transferred from a Messaging server queue, and handled by the Gateway for routing via a standardized protocol, the Property List provides the technical parameters that enable Gateway to reroute the message contents.

Define Property Lists using either the GUI or the command line interface.

### XMS-type Decision Rules

Once you have created an Axway Messaging connector, Gateway provides a special category of <span style="font-weight: bold;">Decision Rules</span> that can link an Axway Messaging message reception event to a file transfer via the Gateway.

Define <span style="font-style: italic;">XMS-type Decision Rules</span> using either the GUI or the command line interface.

### XMS Models

After creating a Property List, you can create an <span style="font-weight: bold;">XMS-type Model</span> that uses attributes defined in the list. XMS Models can be one of two types:

-   From Gateway
-   To Gateway

To use the XMS Model, create a Decision Rule and specify the appropriate XMS-type Model in the rule.

<span id="Linking_Gateway_Messaging"></span>

## Linking <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span> to Axway Messaging: Overview

To link Gateway to Axway Messaging:

1.  In the configuration menu, [activate the Axway Messaging connector](../../configuration_start_here/config_connectors#olh_connectivity_xms).
2.  Create a Property List
3.  Create an XMS Model of the type <span style="font-style: italic;">To</span> or <span style="font-style: italic;">From</span> Gateway
4.  Create an IN or OUT type connector
5.  Create a Decision Rule: XMS-type for IN connectors and XFER\_CHANGE\_STATE for OUT connectors
6.  Create a Rule Table: XMS-type for IN connectors and XFER\_CHANGE\_STATE for OUT connectors
7.  Set the <span class="code">p\_libxmsrapi</span> environment variable to <span class="code">fullpath</span> in the <span class="code">xmsrapi</span> library. On UNIX it is called <span class="code">libxmsrapi.so</span> and on Windows<span class="code"> xmsrapi.dll</span>

Related topics

[Linking <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span> to Axway Messaging](messaging_working_with)

[Linking <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span> to Axway Messaging (command line)](messaging_working_with_cli)

[Working with Property Lists](../../transfers_start_here/parameters_start_here/models_start_here/managing_property_lists)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
