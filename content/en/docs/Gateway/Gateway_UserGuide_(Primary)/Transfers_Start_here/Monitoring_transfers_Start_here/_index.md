{
    "title": "Monitoring Transfers ",
    "linkTitle": "Monitoring Transfers",
    "weight": "130"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Transfers

This topic introduces the features that enable you to supervise, analyze, and maintain Gateway transfer operations and processes.

-   [Mailbox](#mailbox)
-   [Connections and Connected Users](#connections_and_connected_users)
-   [Logs](#logs)
-   [Statistics](#stats)
-   [Automatic maintenance operations](#auto_maint_operations)
-   [Axway Sentinel](#sentinel)

<span id="mailbox"></span>

## Mailbox

To understand how to use the Mailbox in Gateway, it is important that you understand what it is.

The <span style="font-style: italic;">Mailbox</span> is a permanent file in which Gateway stores all data relating to Transfer Requests. During the transfer process, all Transfer Request statuses and data are updated in the Mailbox. This stored information enables Gateway to restart and complete transfers in the case of failure during the transfer process.

The Mailbox contains a complete description of the Transfers.

Each Transfer, successful or not, has its own record in the Mailbox. This record stores information such as:

-   Transfer origin and destination
-   Application used
-   Transfer status
-   Scheduling parameters:
    -   start
    -   date
    -   priority

To view the Mailbox via online commands, you must display details of Transfer Requests using the <span class="code" style="font-weight: bold;">[peldsp select\_trans](../submitting_transfer_requests_start_here/working_with_transfers_cli#peldsp_select_trans)</span> command.

### Backup Mailbox: Mirroring

The loss of an unduplicated Mailbox file can provoke the loss of all of the collected monitored information about Gateway. The Gateway <span style="font-style: italic;">Mirroring</span> feature creates a second version of the Mailbox for backup purposes. This protects the Gateway Mailbox from catastrophic failures such as disk crashes. Refer to [Managing the Mailbox (command line)](viewing_and_managing_mailbox_contents_cli/managing_mailbox_cli#Mailbox_mirroring).

<span id="connections_and_connected_users"></span>

## Connections and Connected Users

To monitor the activities of the Gateway server, you supervise current connections. These are connections that are still open, whether they are active (transferring data) or not.

Gateway can provide you with the following types of information about your current connections:

-   Identification
-   Localization
-   Resource consumption
-   Error ratio
-   Average transfer speed

To retrieve this information, use <span style="font-style: italic;">Connection</span> and <span style="font-style: italic;">Connected User objects</span>. Gateway creates these objects for connections and users that use Gateway. The life of the object is limited to the life span of the Connection or Connected User that the object describes. Unlike most other Gateway objects, you cannot create and store Connections and Connected Users. They only display current state information.

To select and display attributes of Connection and Connected User objects, use either the GUI or online commands.

### Connections

A Connection object contains information describing a protocol session. Monitored information for connections enables you to detect any exceptional activity (excessive resource consumption, low transfer performance, important error ratios, intrusions, and so on). Use either the GUI or online commands to list current connections, display connection attributes, or stop the progress of a connection (kill the connection).

### Connected Users

In the context of monitoring, a Connected User is an entity that is responsible for a set of connections. A Connected User is a virtual object that is identified with the Site used for these connections. All information that single connections carry is cumulated at the Connected User level. As for Connections, use either the GUI or online commands to list and display attributes, and disconnect Connected Users. A disconnection consists in killing all related connections with a single operation.

<span id="logs"></span>

## Logs

Gateway stores traces of all monitoring, protocol, and network events in a <span style="font-style: italic;">Log</span> file. You can configure Gateway to write different levels of detail to the file. You consult log contents either using the GUI or by opening the Log file.

<span id="stats"></span>

## Statistics

If you select the corresponding option for your Gateway configuration, each transfer termination (correct ending or cancellation) triggers the deposit of information to a <span style="font-style: italic;">Statistics file</span>. You can use the information in your Statistics files to analyze transfer performance.

<span id="auto_maint_operations"></span>

## Automatic maintenance operations

Automatic maintenance operations enable Gateway to run continuously, while at the same time:

-   Purging the Mailbox
-   Archiving the Log file
-   Archiving the Statistics file

Gateway executes automatic maintenance operations periodically according to the definition you set for the date/time cycle, and according to the volume of data that transits the Mailbox. Additionally, you can schedule batch jobs at the end of monitor maintenance processing.

<span id="sentinel"></span>

## Axway Sentinel

Sentinel is a Business Activity Monitoring (BAM) product, part of the <span class="mc-variable axway_variables.Platform_or_Suite_Short_Name variable">Axway Platform</span> platform.

If your Axway product package includes both Gateway and Sentinel, you can configure Sentinel to monitor Gateway transfer activities.

Related topics

[Overview: Monitoring <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>](../../ov_gateway/ov_monitoring_gateway)

[About Axway Sentinel](../../connectors_about/sentinel_about)

[Viewing and managing Mailbox contents](viewing_and_managing_mailbox_contents_(gui))

[Managing the Mailbox (command line)](viewing_and_managing_mailbox_contents_cli/managing_mailbox_cli)

[Maintaining the Mailbox (command line)](viewing_and_managing_mailbox_contents_cli/maintaining_mailbox)

[Monitoring Connections](monitoring_connections_gui)

[Monitoring Connected Users](monitoring_connected_users_(gui))

[Monitoring Connections (command line)](viewing_and_managing_mailbox_contents_cli/monitoring_connections_cli)

[Monitoring Connected Users (command line)](viewing_and_managing_mailbox_contents_cli/monitoring_connected_users_cli)

[Log files](log_files)

[Working with Logs](log_files/working_with_logs_(gui))

[Working with Logs (command line)](log_files/working_with_logs_cli)

[Managing Statistics files (command line)](viewing_and_managing_mailbox_contents_cli/managing_statistics_files)

[Automating maintenance operations](automating_maintenance)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
