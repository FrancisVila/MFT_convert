{
    "title": "JMS connector",
    "linkTitle": "JMS connector",
    "weight": "260"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Connectors

[JMS and Gateway](#JMS_and_Gateway)

[Required Gateway objects for JMS](#Required_objects)

<span id="JMS_and_Gateway"></span>

## JMS and Gateway

The Gateway JMS connector enables Gateway to communicate with other applications using JMS messages. This enables you to interface with JMS-compatible Message-Oriented Middleware (MOM) such as Axway Messaging or IBM WebSphere MQ.

You can:

-   Route messages received by a JMS MOM to Gateway
-   Route files received by Gateway to a JMS MOM

The Gateway JMS connector calls the JMS API. You need to have a JMS provider and [configure the connector](../jms_configuring) for this provider.

### Supported versions

This version of Gateway supports JMS V1.1 and all earlier versions.

### Supported message types

The Gateway JMS connector supports the following JMS message types:

-   <span style="font-weight: bold;">TextMessage</span>: contains a character string
-   <span style="font-weight: bold;">BytesMessage</span>: contains an array of bytes
-   <span style="font-weight: bold;">Message</span>: no data content (contains header and properties only)

Gateway rejects all other JMS message types.

### Commit and Rollback

For each message transfer, the JMS connector within Gateway decides at a certain moment in time whether to <span style="font-style: italic;">commit</span> (validate) the transfer or to carry out a <span style="font-style: italic;">rollback</span> (cancel). Gateway carries out a commit only when all internal operations have been completed successfully. If an error occurs during a transfer, Gateway carries out an automatic rollback.

### Overview of JMS message transfer using Gateway

#### From Gateway to JMS

Gateway can convert any file to JMS message format and send it to a JMS MOM. For example, you can route files received by Gateway (using PeSIT or any other supported protocol) to a JMS MOM.

#### From JMS to Gateway

Gateway detects the arrival of a JMS message on the message queue in the JMS MOM. If a message arrives, Gateway automatically receives it.

<span id="Required_objects"></span>

## Required Gateway objects for JMS

You need to create the following Gateway objects to be able to exchange and/or route JMS messages.

### Remote Site object

Here you define how to communicate with your JMS provider, for example:

-   Direction: send and/or receive
-   Mode: queue (point-to-point) or topic (publish and subscribe)
-   Queue manager/JMS provider
-   Initialization properties

You can create several Remote Sites, depending on your requirements.

### Transfer Request object

A Transfer Request is the object that describes how a message is sent or received through JMS. Amongst other parameters, it specifies:

-   The JMS Remote Site
-   The JMS properties
-   The payload location (<span style="font-weight: bold;">File component</span>)

There are various ways to create a Transfer Request, for example:

-   Through a request issued by an application using the Gateway Application interface (API, command line)
-   By a user using the <span style="font-style: italic;">New Transfer Request</span> window of the Gateway GUI
-   Through the automated routing service provided by Gateway

### Decision Rule object and Model object

Here you specify the criteria that will activate the linked routing Model. Through the routing Model you define the parameters of the outgoing transfer. These parameters can be set with the value of the JMS incoming transfer parameters, such as the JMS properties.

Via the Decision Rule object you define the selection criteria for the routing Model:

-   For <span style="font-style: italic;">incoming</span> JMS messages:
    -   <span style="font-weight: bold;">Decision Rule</span>: selection criteria, such as property name = property value
    -   <span style="font-weight: bold;">Model</span>: Transfer parameter = property value
-   For <span style="font-style: italic;">outgoing</span> JMS messages:
    -   <span style="font-weight: bold;">Decision Rule</span>: Transfer parameters (for example, PeSIT protocol, application, file name)
    -   <span style="font-weight: bold;">Model</span>: parameter = property value (incoming transfer parameters)

Implementation Note

The <span class="code">DateFormat</span> class is instantiated locally in each thread. Thus it is used as described in the Java documentation: "Date formats are not synchronized. It is recommended to create separate format instances for each thread." Each thread of Jms Connector has a specific and unique <span class="code">DateFormat</span> instance.

Gateway uses:

-   <span class="code">JmsConnector</span> which is threadable.
-   <span class="code">JmsConnector</span> which instantiates a LogWriter.
-   <span class="code">LogWriter</span> which instantiates a DateFormat.

 

From the <span class="code">MessageFormat</span> class, Gateway uses <span class="code">MessageFormat.format()</span>, which for Java 1.6 is thread safe: <span class="code">http://docs.oracle.com/javase/6/docs/api/java/text/MessageFormat.html#format(java.lang.String,%20java.lang.Object...).</span>

Related topics

[About JMS](../)

[Configuring the <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>/JMS environment](../jms_configuring)

[Working with <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>/JMS](../jms_working_with)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
