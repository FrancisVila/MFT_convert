{
    "title": "Advanced Routing",
    "linkTitle": "Advanced Routing",
    "weight": "160"
}This chapter provides detailed information about the {{< SecureTransport/advancedrouting  >}} concepts and procedures. You will learn various instruction on how to create Advanced Routes, subscribe user accounts to {{< SecureTransport/advancedrouting  >}} applications and assign route package templates to user accounts.

In addition to configuration descriptions, you will be able to observe some example basic and advanced use cases.

The final topics of this chapter also contain instructions for {{< SecureTransport/advancedrouting  >}} best practices and troubleshooting.

## {{< SecureTransport/advancedrouting  >}} overview

Advanced Routing (AR) provides a mechanism for multiple routing and transformation iterations over one or more files. As the name suggests, it allows the {{< SecureTransport/componentshortname  >}} administrator to create diverse patterns for file transformations and movement (routing) across different partner systems and internal entities. UI-wise, Advanced Routing is a standard SecureTransport *application*: in order to use it, either an account or account template must subscribe to it.

Advanced Routing (AR) is the most complex application, both in terms of configuration and possible use cases. Using it involves concepts and terminology that are entirely AR-specific. In order to take advantage of these concepts, you must first understand the aspects of AR and the great multitude of file transfer scenarios it covers.

### What can Advanced Routing do?

AR allows you to configure complex sets of actions (called *route steps*) to apply on one or more files during a transfer process. Route steps are divided into two categories: *transformation* (modification) and *routing* (transferring) of files.

-   *Transformation* of files – this includes several predefined file modifications: you configure in what way you to modify (transform) a file. For example, you can apply PGP encryption/decryption, compression/decompression, character replacement or renaming of filenames, etc.
-   *Routing* of files – this is a definition of the AR file transfer: you configure where you want to send your file.

Each transformation or routing is defined as a *step* in a *route*. For example, if you want to 1)encrypt a file, 2)send it to the subscription folder of a selected account and then 3)decrypt it, you must perform one step per each action, three in total. These three steps form the route.

**Summary:** Route steps are *definitions for actions* you apply to one or more files in a specific order. A set of route steps forms a route.

{{< SecureTransport/advancedrouting  >}} allows you to add more routes if you need to. You decide how many steps you’ll have in each of your routes. Theoretically, your route package can include as many steps as you want; however, it is not recommended to have too many as it might adversely affect performance.

For best UI experience, it is recommended that you understand the terminology introduced with AR.

### {{< SecureTransport/advancedrouting  >}} glossary of terms

The following terms and concepts are introduced with {{< SecureTransport/advancedrouting  >}}:

-   **Route and route steps**  
    Advanced Routing provides advanced transformation and routing capabilities to file transfers. Each transformation and movement of files is performed in a *route*. A route is a set of (route) steps which are consecutively executed. The order of step execution is defined in the routes and the eventual processing of steps is triggered by predefined conditions. Only AR file transfers use steps. You can have multiple steps defined in a route. Each step performs either of the two possible actions: file *transformation* or file *routing*.  
    Note that both Transformation and route execution can be based on file path/name patterns or other environment variables
-   **Step conditions**  
    Each step you define has a triggering condition associated with it. You can trigger step execution either by using EL or always (unconditionally).
-   **Route package**  
    A collection of routes defines a route package. The routes in a package process the file in parallel: this means that no order in route execution is defined. Route package is performed on the Account level and is an instance of the Route Package Template.
-   **Route Package Template**  
    The Route Package Template is used for adding a route package per account. You can define the Business units a package template will be available to: only accounts part of the specified Business units will be able to use route packages as defined in the Route Package Template.

Now that you know some basic AR-specific terms, you can learn more about triggering conditions that launch a file transfer through the route steps.

### Triggering conditions and events

When specific predefined conditions are met, the route kicks off and its steps are performed in the predefined order. These conditions are triggered by specified events. As with routing steps, conditions are wrapped in routes as part of a *Route Package Template* or *Route Package*.

As an administrator, you define the conditions which will trigger transformation and routing processing or both over one or more files. Those conditions or steps are stored in a Route Package or Route Package Template. In order to reuse already defined steps, you must add them to a *Route Package Template*. In contrast, one or more steps which are specific for a particular user can be defined in a *Route Package*.

{{< SecureTransport/advancedrouting  >}} processing can be triggered by the following events:

-   Successful client upload
-   Failed client upload
-   Successful client download
-   Failed client download
-   Successful server pull
-   Temporarily failure of a server pull
-   Failed server pull - Also applies to failed wildcard and individual file pulls

## {{< SecureTransport/advancedrouting  >}} setup overview

The following list represents the setup stages that a SecureTransport administrator must go through in order to configure an AR instance.

-   Create a route package template
-   Create AR application
-   Create a route package instance from the route package template
-   Subscribe account to AR application to trigger the route

As noted above, you must have an account (or an account template) in order to create a subscription to the AR application. You can have multiple AR applications that cover different use cases for different groups of users. Additionally, you can create and AR delegated administrator to administer all AR configurations and file transfers.

As you can see, setup itself introduces some AR-specific concepts. The route package template, the route package instance and the route itself are all different forms of the same concept: a reusable configuration that is easily upgradable when necessary. You will better understand their purpose when you learn a bit more about the logic incorporated into each AR flow.

## {{< SecureTransport/advancedrouting  >}} features

{{< SecureTransport/advancedrouting  >}} offers the following features:

-   Conditioning
    -   Transformation and route execution can be based on file path/name patterns or other environment variables
-   Transformations
    -   PGP Encryption, PGP Decryption, Compress, Decompress, Line Ending, External Script, Encoding Conversion, Characters Replace, Line Padding, Line Truncating, Line Folding, and Rename transformations
    -   Multiple transformation execution (for example, Decompress > PGP Decryption > Compress)
    -   Renaming
-   Routings
    -   File routing to transfer sites, accounts (including virtual and LDAP ones), and file system through Publish To Account and Send To Partner
    -   Renaming and deleting
    -   Overwrite upload folder - optional setting for the new upload folder name which overwrites the one configured in Transfer site settings
-   Tracking and notifications
    -   File Tracking integration
    -   Sentinel integration
    -   Email notifications on routing and transformation successes, failures, and triggering
-   Extensive Expression Language support
-   Post routing, post transformation, and post processing actions 
-   Ability to specify and overwrite transformation and routing steps on an account basis
-   Distributed execution of the routes in a Standard Cluster or Enterprise Cluster

The following topics provide detailed info about different aspects of {{< SecureTransport/advancedrouting  >}} :

-   [Order of configuration](c_st_order_of_configuration)
-   [Configuration](c_st_configuration)
-   [Transformations](c_st_route_step_transformations)
-   [Route steps](c_st_route_steps)
-   [Operation](c_st_operation)
-   [Advanced Routing best practices](c_st_advanced_routing_best_practices)
-   [Custom Expression Language functions and variables](r_st_custom_el_functions_variables)
-   [Troubleshoot Advanced Routing](c_st_troubleshooting)
