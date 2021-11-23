{
    "title": "JMS",
    "linkTitle": "JMS",
    "weight": "240"
}{{< Gateway/componentlongname  >}}: Connectors

## About Java Message Service (JMS)

The Java Message Service™ (JMS) is a Java API for exchanging messages between two or more clients through a Message-Oriented Middleware (MOM). The JMS API defines a common set of interfaces and associated semantics that allow programs written in the Java programming language to communicate with any JMS-compatible MOM implementation. The JMS API is part of the Java 2 Platform, Enterprise Edition (J2EE). It is provided in the Java package `javax.jms`.

### JMS messages

JMS messages are the objects that communicate information between JMS clients. The messages are asynchronous requests, reports, or events that are consumed by enterprise applications, not humans. They contain precisely-formatted data that describes specific business actions. Through the exchange of these messages, each application tracks the progress of the enterprise.

### JMS message structure

A JMS message has three main parts:

-   **Message header** (required): Contains operational settings to identify and route messages
-   <span style="font-weight: bold;">Message properties</span> (optional): Contains additional properties to support compatibility with other providers or users. These properties can be used to create custom fields or filters.
-   <span style="font-weight: bold;">Message body</span> (optional): Allows users to create different types of message (text message, bytes message, and so on).

The message interface is extremely flexible and provides many ways to customize the contents of a message.

### JMS messaging models

The JMS API supports two types of messaging model:

-   Queuing model
-   Topic model

#### Queuing model (point-to-point)

In the <span style="font-style: italic;">queuing model</span>, a producer posts messages to a specific message queue and a consumer reads messages from the queue(s) established to hold their messages. Here, the producer knows the destination of the message and posts the message directly to the consumer's queue.

In this model:

-   Only one consumer receives the message
-   The producer does not have to be running when the receiver consumes the message, nor does the receiver need to be running when the message is sent
-   Queues retain all messages sent to them until the messages are consumed or until the messages expire
-   Every message successfully processed is acknowledged by the receiver

#### Topic model (publish and subscribe)

The <span style="font-style: italic;">topic model</span> supports publishing messages to a particular message topic. Zero or more subscribers may register interest in receiving messages on a particular message topic. In this model, neither the publisher nor the subscriber know about each other.

In this model:

-   Multiple consumers can receive the message
-   There is a timing dependency between publishers and subscribers. The publisher has to create a subscription in order for clients to be able to subscribe. The subscriber has to remain continuously active to receive messages, unless it has established a durable subscription. In that case, messages published while the subscriber is not connected will be redistributed whenever it reconnects.

### JMS API Architecture

JMS consists of several elements:

-   <span style="font-weight: bold;">JMS provider:</span> An implementation of the JMS interface for a Message-Oriented Middleware (MOM). Providers are implemented as either a Java JMS implementation or an adapter to a non-Java MOM.
-   <span style="font-weight: bold;">JMS client:</span> A Java-based application or object that produces and/or consumes messages.
-   <span style="font-weight: bold;">JMS producer:</span> A JMS client that creates and sends messages.
-   <span style="font-weight: bold;">JMS consumer:</span> A JMS client that receives messages.
-   <span style="font-weight: bold;">JMS message:</span> An object that contains the data being transferred between JMS clients.
-   <span style="font-weight: bold;">JMS queue:</span> A staging area that contains messages that have been sent and are waiting to be read. The messages are delivered in the order sent. A message is removed from the queue once it has been read.
-   <span style="font-weight: bold;">JMS topic:</span> A distribution mechanism for publishing messages that are delivered to multiple subscribers.

### Java Naming and Directory Interface (JNDI)

The JMS API, like all other Java Enterprise APIs, uses the <span style="font-style: italic;">Java Naming and Directory Interface</span> (JNDI) API for administration. The JMS API defines <span style="font-style: italic;">ConnectionFactories</span> and <span style="font-style: italic;">Destinations</span> as administered objects that are configured and placed in a JNDI naming context. JMS clients then look up and use these preconfigured objects. This ensures that JMS applications are easy to deploy and administer.

### JMS Providers

In order to use JMS, you must have a JMS provider that can manage the sessions and queues.

Examples of JMS providers:

-   Axway Messaging (XMS)
-   TIBCO EMS
-   IBM WebSphere MQ (formerly MQSeries)
-   Oracle Enterprise Messaging Services (OEMS)
-   Sun Java System Message Queue
-   Open Message Queue (Sun Microsystems)

Related topics

[JMS connector](jms_connector)

[Configuring the <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>/JMS environment](jms_configuring)

[Working with <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>/JMS](jms_working_with)

 

More information

Refer to the Oracle website: <http://www.oracle.com/technetwork/java/jms/index.html>

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
