{
    "title": "Monitoring Gateway",
    "linkTitle": "Monitoring Gateway",
    "weight": "180"
}{{< Gateway/componentlongname  >}}: Overview

The following features enable you to supervise and analyze Gateway transfer operations and processes.

## Mailbox

The *Mailbox* is a permanent file in which Gateway stores all data relating to Transfer Requests. During the transfer process, all Transfer Request statuses and data are updated in the Mailbox. This stored information enables Gateway to restart and complete transfers in the case of failure during the transfer process.

To view and manage the contents of the Mailbox, use either the GUI or online commands.

## Connections and Connected Users

To monitor the activities of the Gateway server, you supervise current connections. These are connections that are still open, whether they are active (transferring data) or not. To retrieve information about connections, use Connection and Connected User objects.

To view Connection and Connected User objects, use either the GUI or online commands.

## Logs

Gateway stores traces of all monitoring, protocol, and network events in a *Log* file. You can configure Gateway to write different levels of detail to the file.

To consult log contents, either use the GUI or open the Log file.

<span id="Traces"></span>

## 

## Audit

Gateway stores the actions performed by users relating to the Gateway configuration in a dedicated audit file, to provide traceability of changes done to the product's configuration. This concerns changes both to global and to object configuration.

This functionality cannot be disabled, and the audit file can only be written by the audit process inside Gateway.

For more information, see <a href="../../audit" class="MCXref xref">Managing Audit files</a>.

## Traces

Gateway lets you activate the traces of Gateway processes without restarting the product. Traces settings are displayed as dynamic parameters in the unified configuration and changing their values using the `peluconf` utility or Gateway Navigator does not require a product restart. The only difference is for Gatecontroller, whose trace level needs to be set using the new `pelmon` subcommand `traceset`. For Gatecontroller, the updates made with the command `pelmon traceset` are only active until restart. There is no link between trace set in Navigator and trace set from the command line. The Gatecontroller trace parameter set in Navigator requires restart.

The list of trace level parameters is available in the advanced parameter configuration Gateway Navigator or using the `pelmon` get command, filtering by trace.

Some processes (`ipelsock`) may take some time to be applied requiring up to 120s to acknowledge the configuration change.

For Secure Relay you can now activate the traces from Gateway :

-   Using the `peluconf` utility:
    -   Set `-s xsr log_level N`, where `N 0 <= N <= 3`. If N is numerical but other than 0, 1, 2 or 3, an error message is displayed.
-   In Gateway Navigator (**Log levels > Secure Relay**)

To verify that the trace level was set, look in the `log.properties` file in the xsr directory `(install_dir/run_time/xsr`). The line should appear as: `log4j.rootLogger=ERROR, XSR_ROLLINGFILE`.

### Enabling root cause analysis

If a process fails to send heartbeats to Gatecontroller for a number of 5 configured heartbeat periods and the process is considered "vital", then Gatecontroller will restart Gateway. After the 4th missed heartbeat for one vital process, Gatecontroller will automatically trigger two actions:

-   activate level 4 trace for the faulty process
-   if configured to do so, will launch a debugger attached to the faulty process.

The configuration of the debugger command to launch is made through the static parameter `[gatecontroller]gc_debugger_cmd`

If between the 4th and the 5th heartbeat period, the process unblocks and sends its heartbeat to Gatecontroller, the root cause analysis procedure is reversed:

-   trace is set back to level 0 on that process
-   the debugger process is stopped

### Limitation

For APIs used by Gateway to interoperate with other products (Sentinel API, Integrator API, X.400, X.420, Messaging), the dynamic trace level is not currently supported.

## Statistics

If you select the corresponding option in the Gateway configuration menu, each transfer termination (correct ending or cancellation) triggers the deposit of information to a *Statistics file*. You can use the information in your Statistics files to analyze transfer performance.

## Process monitoring

Gateway provides a centralized control of all its processes. GateController is a process that is always present. This process is responsible for starting, monitoring and stopping each permanent process within Gateway. It is able to give a reliable status of the product at any time. GateController is the only process you need to monitor in order to know the status of Gateway.

GateController starts and stops permanent processes. It is notified of starts and stops of any other process, and monitors every process of Gateway. Every permanent process sends heartbeats, so that GateController can detect crashes, loops, or any other loss of service. It can restart the entire Gateway application, or an individual process.

The `gatestatus` command enables you to monitor Gateway. It is a simple reference tool designed for the system administrator to check the functioning of Gateway. `gatestatus` messages don't necessarily indicate that there is problem, merely a condition that can only be cleared with user intervention.

## Sentinel

Sentinel is a Business Activity Monitoring (BAM) product of the {{< Gateway/platformorsuiteshortname  >}}.

If your Axway product package includes both Gateway and Sentinel, you can configure Sentinel to monitor Gateway transfer activities.

[Next topic](../ov_dmz_deployment)

Related topics

[Monitoring transfers](../../transfers_start_here/monitoring_transfers_start_here)

[Monitoring Connections](../../transfers_start_here/monitoring_transfers_start_here/monitoring_connections_gui)

[Monitoring Connected Users](../../transfers_start_here/monitoring_transfers_start_here/monitoring_connected_users_(gui))

[Log files](../../transfers_start_here/monitoring_transfers_start_here/log_files)

[Managing Statistics files (command line)](../../transfers_start_here/monitoring_transfers_start_here/viewing_and_managing_mailbox_contents_cli/managing_statistics_files)

[About gatestatus messages](../../starting_and_stopping_server/c_gatestatus_messages)

[About Axway Sentinel](../../connectors_about/sentinel_about)

<a href="../../configuration_start_here/config_gateway_paras" class="MCXref xref">Configuring Gateway parameters</a>

Links to documentation set for Axway Gateway {{< Gateway/releasenumber  >}}:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
