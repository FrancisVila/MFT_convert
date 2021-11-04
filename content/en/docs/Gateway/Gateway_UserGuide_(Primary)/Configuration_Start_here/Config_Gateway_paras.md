{
    "title": "Configuring Gateway parameters",
    "linkTitle": "Gateway parameters",
    "weight": "80"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Configuration

The <span style="font-weight: bold;">Gateway</span> parameters of the configuration menu condition the Gateway supervision services. For example: product and Local Site information, database options, user access control and log levels.

[Gateway product and local Site information](#olh_gateway)

[Advanced parameters](#Advanced_parameters)

[Trace levels](#Advanced_parameters)

[Log levels](#Log_levels)

[Route transfer states](#Route_transfer_states)

[Gateway database information](#olh_gateway_database)

[Automatic archiving of Mailbox records, log and statistics files](#olh_gateway_database_archive)

[Database protection options](#olh_gateway_database_protection)

[User access control](#olh_gateway_connection_control)

[Trace file archiving parameters](#Trace_file_archiving_parameters)

<span id="olh_gateway"></span>

## Gateway parameters

Use the following parameters to set up Gateway product and Local Site information.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Parameter         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Local site alias</p>         </td>
         <td><p>Enter the default Local Site alias.<br />
Maximum: 20 alphanumeric characters with no spaces.<br />
You can use the same value as the <span style="font-weight: bold;">Local site name</span> if desired.</p>         </td>
      </tr>
      <tr>
         <td><p>Local site name</p>         </td>
         <td><p>Enter the default Local Site name.<br />
Maximum: 20 alphanumeric characters with no spaces.<br />
You can use the same value as the <span style="font-weight: bold;">Local site alias</span> if desired.</p>         </td>
      </tr>
      <tr>
         <td><p>License Key 1 - 4</p>         </td>
         <td><p>The license keys that control your rights to use Gateway. A license key is linked to the hostname of your machine, or to the Key label below.</p>
<p>You can enter up to four license keys. Only one key is mandatory.</p>
<p>The key is validated every time Gateway is started. If the key is invalid, a diagnostic message is logged and the activation process aborted.</p>         </td>
      </tr>
      <tr>
         <td><p>Key label</p>         </td>
         <td><p>Optional</p>
<p>The key label that controls your rights to use Gateway. A key label is not linked to the hostname of your machine.</p>
<p>If you have a Key label, enter it in this field.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Advanced_parameters"></span>

### Advanced parameters and Trace levels

Normally, you do not need to modify any of the Advanced parameters.

You may need to use Advanced parameters if, for example, you need to [Customize Trading Partner parameters](../customizing_trading_partner_paras) for certain trading file management situations.

To modify Advanced parameters or Trace levels:

1.  Click <span style="font-weight: bold;">Advanced options...</span>.
2.  In the <span style="font-style: italic;">Parameter</span> column, select the required item.
3.  In the <span style="font-style: italic;">Value</span> column, type the new value.
4.  Click OK to save the new settings.

<span id="Examples"></span>

#### Examples of Advanced parameters

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Parameter         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><span class="code">cancel_transfer_on_max_site_retry_reached</span></p>         </td>
         <td><p>Cancels the transfer when the maximum number of connection retries to a given Remote physical Site has been reached.</p>
<p>Set value to 1 to activate this parameter, set to 0 to deactivate this parameter.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">job_max</span></p>         </td>
         <td><p>Specifies the maximum number of simultaneous activated scripts (for routed commands). This parameter is only taken into account by Gateway if the <span class="code">started_command_user_control</span> parameter is set to <span style="font-weight: bold;">yes</span>.</p>
<p>Use this parameter in conjunction with the <span class="code">started_command_user_control</span> parameter.</p>         </td>
      </tr>
      <tr>
         <td><code>gc_debugger_cmd</code>         </td>
         <td><p>Configuration of the debugger command to launch after the 4th missed heartbeat for one vital process, to enable root cause analysis of non-responding processes. If the <code>gc_debugger_cmd </code>parameter is not set, no debugger is launched.</p>
<p>There are four place-holders that can be used inside the definition of the debug command:</p>
<ul>
<li>&lt;PID&gt; - it will be replaced with the process ID of the faulty process</li>
<li>&lt;PWD&gt; - the current working directory</li>
<li>&lt;PNAME&gt; - the name of the faulty process as it is known by Gatecontroller</li>
<li>&lt;DATETIME&gt; - the current timestamp</li>
</ul>
<p>For example, on Linux, the debugger command can be:</p>
<p>[gatecontroller]gc_debugger_cmd="strace -t -p &lt;PID&gt; -o &lt;PWD&gt;/&lt;PNAME&gt;_&lt;DATETIME&gt;.straceout"</p>
<p>Note: the debugger command can be used to launch any command and should be used with care, as the command will be ran with Gateway's user privileges</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">gc_proc_max_retries</span></p>         </td>
         <td><p>Specifies the maximum number of restarts for certain non-vital Gateway processes that are controlled by the GateController if these processes stop abnormally. For example, <span class="code">ipelapid</span> (the Gateway GUI daemon) or <span class="code">xfbapid</span>.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">gc_stop_mon_maxretries</span></p>         </td>
         <td><p>Specifies the maximum number of retries to send a stop request to the supervisor process.</p>
<p>You may need to modify this value if for example there were many requests to the supervisor just before the stop request. In this case the supervisor takes longer to handle the stop request as it first has to handle all other requests received earlier. If the supervisor has not handled the stop request within the number of retries defined by this parameter, GateController stops Gateway in a more abrupt manner.</p>         </td>
      </tr>
      <tr>
         <td><p><code> [monitor] ack_rcmax</code></p>         </td>
         <td><p>Specifies the maximum number of retries Gateway will attempt for an outgoing RECEIPT or EERP ack transfer. For manually initiated ACK transfers, if the <code>rc_max </code>parameter is specified for the transfer
the maximum number of retries is establied by the value of the rc_max parameter specified in the <span class="code">peltrans </span>command.
Example:</p>
<p><code> peltrans -type RECEIPT -rtx 123 -rc_max 3</code></p>
<p>If no value is set for the <code>[monitor] ack_rcmax</code> parameter, and <code>rc_max </code>is not specified in the <code>peltrans </code>command, the default fallback value is 5 (not configurable).</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">gc_gw_max_loop_restart</span></p>         </td>
         <td><p>Specifies the maximum number of GateController restarts allowed.</p>
<p>Use this parameter in conjunction with the <span class="code">gc_gw_max_loop_restart_period</span> parameter.</p>
<p><span style="font-weight: bold;">Example:</span> If the GateController restarts every X seconds and you do not want more than Y restarts in X*Y seconds, you can modify the values of these parameters as follows:</p>
<p><span class="code">gc_gw_max_loop_restart_period = X</span></p>
<p><span class="code">gc_gw_max_loop_restart = Y</span></p>
<p>The GateController will then be deactivated after the Yth following restart.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">gc_gw_max_loop_restart_period</span></p>         </td>
         <td><p>Specifies the period between two GateController restarts.</p>
<p>Use this parameter in conjunction with the <span class="code">gc_gw_max_loop_restart</span> parameter.</p>
<p>Refer to the example provided in the <span class="code">gc_gw_max_loop_restart</span> parameter section.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">started_command_user_control</span></p>         </td>
         <td><p>Set this parameter to <span style="font-weight: bold;">yes</span> if you want to control the maximum number of simultaneous activated scripts (for routed commands). Default = <span style="font-weight: bold;">no</span>.</p>
<p>Use this parameter in conjunction with the <span class="code">job_max</span> parameter that specifies the maximum number of simultaneous activated scripts.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">stop_site_on_max_retry_reached</span></p>         </td>
         <td><p>Deactivates the Remote physical Site when the maximum number of connection retries to this Site has been reached.</p>
<p>Set value to 1 to activate this parameter, set to 0 to deactivate this parameter.</p>         </td>
      </tr>
      <tr>
         <td><span class="code">ftp_vfd_fifo</span>         </td>
         <td><p>This parameter determines the FIFO behavior for the <span class="code" style="font-weight: bold;">RETR</span>, <span class="code" style="font-weight: bold;">STOR</span>, <span class="code" style="font-weight: bold;">MDTM</span> and <span class="code" style="font-weight: bold;">SIZE</span> FTP commands when they are used in combination with file name duplication (if the VFD allows it).</p>
<p>Possible values:</p>
<p><strong>0</strong> = use the current LIFO behavior using the file modification time</p>
<p><strong>1</strong> = use the old Interpel FIFO behavior using the file modification time</p>
<p>You must restart Gateway after modifying this parameter.</p>         </td>
      </tr>
      <tr>
         <td><span class="code">vsite_age_max</span>         </td>
         <td><p>When using PassPort PM, Gateway saves the results of queries in specific Site objects called <span style="font-style: italic;">Virtual Sites</span>. These Virtual Sites save PassPort from being queried all the time by Gateway.</p>
<p>Virtual Sites have a tunable lifetime set by the <span class="code">vsite_age_max</span> parameter. Setting a long lifetime reduces the number of queries to PassPort, resulting in shorter processing times. However, during that time any change made in the related PassPort entry is not refreshed. On the other hand, having a short <span class="code">vsite_age_max</span> value allows quicker updates of PassPort modifications within Gateway, but with poorer performance.</p>
<p>Possible values: 0 - 65 000 seconds. Default = 300.</p>         </td>
      </tr>
      <tr>
         <td><span class="code">cancel_transfer_on_connection_refusal</span>         </td>
         <td><p><em>PeSIT</em> <em>only</em></p>
<p>Cancel transfers on protocol connection phase failure.</p>
<p>Set this parameter to <strong>1</strong> to activate this parameter (cancel transfers on connection refusal).</p>
<p>Set this parameter to <strong>0</strong> to deactivate this parameter (do not cancel transfers on connection refusal).</p>         </td>
      </tr>
      <tr>
         <td><span class="code">sid_limit</span>         </td>
         <td><p><em>HTTP only</em></p>
<p>Use this parameter to limit the number of sessions a user can have on the server.</p>
<p>Each time a user logs in, the value of this parameter is compared with the number of sessions registered for that user. If the number of registered sessions is lower than the value of this parameter, the user is allowed to login. Otherwise the login is refused.</p>
<p>This parameter is only taken into account if you have set the HTTP server identification <strong>Method</strong> to <em>Cookie session id</em> or <em>CGI session id</em> in the configuration menu.</p>         </td>
      </tr>
      <tr>
         <td><span class="code">select_transfer_by_pathname</span>         </td>
         <td><p>Use this parameter to enable resuming interrupted transfers when working with monitored RFD (real file directory). This parameter only affects protocols that support resuming interrupted file transfers, like FTP.</p>
<p>Possible values:</p>
<ul>
<li>0 (default) = resuming interrupted transfers disabled</li>
<li>1 = allow resuming interrupted transfers</li>
</ul>         </td>
      </tr>
      <tr>
         <td><code>select_with_regexp</code>         </td>
         <td><p>Use this parameter to enable regex searching with select commands. Possible values:</p>
<ul>
<li>0 (default - means no)</li>
<li>1</li>
</ul>
<p>regex characters:</p>
<ul>
<li><code style="font-weight: bold;">*</code> match zero to any number of characters (any printable character)</li>
<li><code style="font-weight: bold;">?</code> match exactly one character (any printable character)</li>
<li><code style="font-weight: bold;">[</code> marks the start of a character group</li>
<li><strong>]</strong> marks the end of a character group</li>
<li><code style="font-weight: bold;">-</code> inside a character group, defines a range of characters.<br />
example: <code>a[b-d]c</code> will match abc, acc and adc.</li>
<li><code style="font-weight: bold;">^</code> or <code style="font-weight: bold;">!</code>used inside a character group, negates the entire group of characters.<br />
Example: <code>a[!abc]c</code> will not match <code>aac</code>, <code>abc </code>or <code>acc</code>, but will match <code>adc</code>, <code>aec</code>, <code>afc</code>, <code>agc</code>, etc.,</li>
<li><code style="font-weight: bold;">\</code> escape character. Search for special characters.<br />
Example: <code style="font-weight: bold;">\*</code> if you want to find a <code>*</code> (star) in the text.</li>
</ul>
<p>The search is case sensitive.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="trace_level_examples"></span>

#### Examples of Trace levels

The higher the specified trace level, the more information is dumped to the trace file.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Parameter         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><span class="code">x420.trace_level</span></p>         </td>
         <td><p>Trace level for X.420.</p>
<p>Possible values: 0 – 4 (default = 1).</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">ft_sftp.trace</span></p>         </td>
         <td><p>Trace level for SFTP generic code.</p>
<p>Possible values: 0 – 4 (default = 0).</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">ft_sftp.trace.tcp</span></p>         </td>
         <td><p>Trace level for low-level TCP code related to SFTP.</p>
<p>Possible values: 0 – 4 (default = 0).</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">ft_sftp.trace.ssh</span></p>         </td>
         <td><p>Trace level for SSH code related to SFTP.</p>
<p>Possible values: 0 – 4 (default = 0).</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Dynamic"></span>

#### Dynamic traces in Gateway

You can now activate the traces of Gateway processes<span class="italic_in_para"> without restarting the product</span>. Trace settings now appear as dynamic parameters in the unified configuration and changing their value is done either:

-   using the <span class="code">peluconf</span> utility  
    Set <span class="code">-s xsr log\_level N</span>, where <span class="code">N 0 &lt;= N &lt;= 3</span>. If <span class="code">N</span> is numerical but other than 0, 1, 2 or 3, an error message is displayed.
-   in Gateway Navigator (<span class="bold_in_para">Log levels > Secure Relay</span>)

The only difference is for Gatecontroller, whose trace level needs to be set using the new <span class="code">pelmon</span> subcommand <span class="code">traceset</span>. For Gatecontroller, the updates made with the command <span class="code">pelmon trace\_set</span> are only active until restart. There is no link between trace set in Navigator and trace set from the command line. The Gatecontroller trace parameter set in Navigator requires restart.

The list of trace level parameters is available in the advanced parameter configuration Gateway Navigator or using the <span class="code">pelmon</span> get command, filtering by trace.

Some processes (<span class="code">ipelsock</span>) may take some time to be applied requiring up to 120s to acknowledge the configuration change.

To verify that the trace level was set, look in the <span class="code">log.properties</span> file in the xsr directory (<span class="code">install\_dir/run\_time/xsr</span>).The line should appear as: <span class="code">log4j.rootLogger=ERROR, XSR\_ROLLINGFILE</span>.

##### Limitation

For APIs used by Gateway to interoperate with other products (Sentinel API, Integrator API, X.400, X.420, Messaging), the dynamic trace level is not supported.

 

<span id="Log_levels"></span>

### Log levels

You can set the level of detail for log files for various components independently in Gateway.

To set the log level:

Click the <span style="font-weight: bold;">Log levels...</span> button.

Set the log level for the required component:

CGate

-   Minimum: errors only (For example: "No CGate matching the connection")
-   Short: name of selected CGate only
-   Full: name of CGate and its details (settings)

SecureRelay

-   Minimum: error messages (around 90), warnings (6 in total), 2 informational messages ("SecureRelay router agent is now available again" and initial listen point establishment)
-   Short: Dynamic listening ports for FTP data channel
-   Full: Incoming connections (with source and destination address)

FTP control session

-   Minimum & Short: control connection init/disconnect/error, start/end sending file, user authentication (220 welcome message, user/pass -- gtw as server only)
-   Full: (all from Minimum/Short), extra server commands

FTP data session

-   Minimum, Short & Full: data connection init/disconnect/error

AS3 control session (same as FTP control sessions)

AS3 data session (same as FTP data sessions)

MGet/MPut

-   Minimum: errors only
-   Short: info on whether it was an MPut or MGet, and the transfer ID for the master transfer
-   Full: details of which directory was listed and which files were requested or sent

GateController (for process monitoring)

-   Minimum & Short: gcontroller errors only
-   Full: details on each Gateway process heartbeat and gcontroller listening port

AS2 (Same as HTTP)

Security server (for SSL/TLS and SSH)

TSD (TCP Server Daemon)

-   Minimum & Short: TSD server listen ports for all active protocols
-   Full: (all from Minimum/Short), incoming connections for each active protocol

Trade (EDIINT Trading partner)

-   Minimum: errors only
-   Short: (all from Minimum), originator/destination information
-   Full: (all from Short), encode/decode start/stop

SFTP

-   Minimum, Short & Full: control connection init/disconnect/error, start/end sending file

SWIFTNet

-   Minimum: transfer start/end, SWIFT sites started/stopped, SWIFT processes start/stop
-   Short: (all from Minimum), output channels and queues acquisition/release
-   Full: (all from Short), system recovery

JMS

-   Minimum: errors, transfer stated/ended/failed
-   Short: (all from Minimum), warnings: queue read/write went down
-   Full: (all from Short), queue read/write opened/closed

HTTP

-   Minimum: errors only, connection init/disconnect
-   Short: (all from Minimum), transfer start/end, HTTP primitive summary related to transfers
    Medium - (all from Short), HTTP primitive summary for all pages
-   Full: (all from Medium), HTTP primitive summary for all files (including images on Gateway web page)

RosettaNet HTTP (Same as HTTP)

X.400 (X.400 support will be discontinued)

For each component, you can choose from the following options:

-   <span style="font-weight: bold;">Minimum</span>
-   <span style="font-weight: bold;">Short</span>
-   <span style="font-weight: bold;">Medium</span> (only for AS2, HTTP, RosettaNet HTTP and X.400)
-   <span style="font-weight: bold;">Long</span> (only for X.400)
-   <span style="font-weight: bold;">Full</span>

<span style="font-weight: bold;"><span id="olh_x400_log_settings"></span>X.400 log settings:</span> You can set log levels for the various elements of the X.400 sub-system. These log messages do not appear in the Gateway log file. They are written to separate log files. Set the <span style="font-weight: bold;">Log size</span> (in Bytes), <span style="font-weight: bold;">Log full action</span> and <span style="font-weight: bold;">Log level</span> for each of the:

-   MTA
-   MTC
-   MS
-   UA X.420

where:

<span style="font-weight: bold;">Log size</span> represents the maximum size of the log entries specified in bytes.

In <span style="font-weight: bold;">Log level</span>, select what kind of information should be logged. The higher the log level is, the more information is logged:

-   0: Log Errors
-   1: Log level 0 + transport events
-   2: Log level 0-1 + transport PDUs
-   3: Log level 0-2 + internal messages
-   4: Log level 0-3 + configuration data

1.  Click <span style="font-weight: bold;">OK</span> to confirm the new log level settings.

For more information about log files in Gateway, refer to [Log files](../../transfers_start_here/monitoring_transfers_start_here/log_files).

<span id="Route_transfer_states"></span>

### Route transfer states

The Route transfer states configuration menu allows you to select the transfer states to trigger the routing mechanism and the Transfer Change State Decision Rule Table scanning in Gateway. The default values select the most important and common transitions and should be enough for most cases.

<span style="font-weight: bold;">Note:</span> Do not change the default values unless Axway Support or any specific Gateway documentation advises you to do this.

Click the <span style="font-weight: bold;">Route transfer states...</span> button.

Select the states to send to the router:

-   Frozen (F)
-   Delayed (D)
-   To begin (B)
-   To restart (R)
-   Processing (P)
-   Processing (V) (resp. side)
-   Suspended (S)
-   Interrupted (I)
-   Cancelled (C)
-   Ended (E)
-   Created (T)
-   To sign (G)
-   Acknowledged (A)
-   To ack (W)
-   nack by USER (U)
-   nack by XFB (X)
-   Ended routing (1)
-   Canceled routing (2)
-   To pack (3)
-   Packing (4)
-   To unpack (5)
-   Unpacking (6)

Click <span style="font-weight: bold;">OK</span>.

<span id="olh_gateway_database"></span>

## Gateway &gt; Database

Use the following parameters to set up Gateway database information.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Parameter         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Default directory for received files</p>         </td>
         <td><p>Enter the default directory used to store received files. The directory that you specify here must exist.</p>
<p>You can set this value in several Gateway objects. Gateway takes the value from object definitions in the following order of precedence:</p>
<ul>
<li>Application</li>
<li>Remote Site</li>
<li>Local Site</li>
<li>Default directory defined here</li>
</ul>
<p>Click the browse button to locate and select the directory.</p>         </td>
      </tr>
      <tr>
         <td><p><span id="Mirror_option"></span>Mirror option</p>         </td>
         <td><p>Gateway mirroring is a transparent software mirroring service that requires no specific hardware. When activated, it duplicates the Gateway Mailbox on a backup copy so that if the main Mailbox is damaged for any reason, it can be repaired from the mirroring Mailbox.</p>
<p>Select one of the following options:</p>
<ul>
<li><span style="font-weight: bold;">No mirroring</span>: Mirroring is deactivated</li>
<li><span style="font-weight: bold;">Stop on error</span>: Gateway stops if an error occurs during mirroring</li>
<li><span style="font-weight: bold;">Disable on error</span>: Mirroring is disabled if an error occurs during mirroring</li>
<li><span style="font-weight: bold;">Ignore error</span>: Mirroring continues and errors are ignored</li>
</ul>
<p>Refer to <a href="../../transfers_start_here/monitoring_transfers_start_here/viewing_and_managing_mailbox_contents_cli/managing_mailbox_cli#Mailbox_mirroring">Managing the Mailbox (command line)</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>Mirror DB directory</p>         </td>
         <td><p>Enter the directory path name where the backup copy of the Mailbox is stored. You should store the backup copy on a different disk drive from that used by the main Mailbox. The main Mailbox is located in the directory <span class="code">&lt;Gateway installation directory&gt;\run_time\data\</span>.</p>
<p>Click the browse button to locate and select the directory.</p>         </td>
      </tr>
      <tr>
         <td><p>File IO ordering</p>         </td>
         <td><p>Use this option to enable flushing in case of system crash.</p>
<p>Select one of the following values:</p>
<ul>
<li><span style="font-weight: bold;">Cache</span>: No IO write ordering or flushing is performed (default). This option renders maximum performance</li>
<li><span style="font-weight: bold;">Order</span>: The product forces flushing of write operations in order to preserve metadata consistencies in case of a system crash</li>
<li><span style="font-weight: bold;">Flush</span>: The product forces flushing of write operations after each change in the data files</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Purge transferred files after routing</p>         </td>
         <td><p>Check this option if you want Gateway to automatically delete files during the Mailbox purge which were deposited to the Gateway and then routed to another machine.</p>         </td>
      </tr>
      <tr>
         <td><p><span id="statistics_option"></span>Statistics option</p>         </td>
         <td><p>Check this option to record statistics on completed transfers.</p>         </td>
      </tr>
      <tr>
         <td><p>File name display option</p>         </td>
         <td><p>FTP and SFTP only</p>
<p>Set the default way in which VFD file names are displayed.</p>
<p>Select one of the following values:</p>
<ul>
<li><span style="font-weight: bold;">Gateway specific</span> = including sXferIdent (default)</li>
<li><span style="font-weight: bold;">Standard</span> = file name only</li>
</ul>
<p>Refer to <a href="../../transfers_start_here/virtual_file_directory_start_here#VFD_file_name_display_option">VFD file name display option</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>File name duplication policy</p>         </td>
         <td><p>FTP, HTTP and SFTP only</p>
<p>This option is only available if you select <span style="font-weight: bold;">Standard</span> in <span style="font-weight: bold;">File name display option</span>.</p>
<p>Set the default way in which duplicate file names are handled.</p>
<p>Select one of the following values:</p>
<ul>
<li><span style="font-weight: bold;">Duplicate</span> = duplicate names allowed (default)</li>
<li><span style="font-weight: bold;">Forbid</span> = duplicate names not allowed</li>
<li><span style="font-weight: bold;">Override</span> = if a duplicate file name is encountered, the new file replaces the old file with the same name</li>
</ul>
<p>Refer to <a href="../../transfers_start_here/virtual_file_directory_start_here#VFD_file_name_duplication_policy">VFD file name duplication policy</a>.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="olh_gateway_database_archive"></span>

### Gateway &gt; Database &gt; Archive

Use the following parameters to set up automatic archiving of Mailbox records, log and statistics files on a periodic basis.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Parameter         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">Mailbox cleanup</span>:</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Log and statistics archive</span>:</p>         </td>
      </tr>
      <tr>
         <td><p>Active</p>         </td>
         <td><p>Select this option to enable automatic archiving of the log file and statistics file.</p>
<p>Then enter one of the following:</p>
<ul>
<li><span style="font-weight: bold;">Start date</span> and <span style="font-weight: bold;">Period</span>, or</li>
<li><span style="font-weight: bold;">Threshold size</span></li>
</ul>
<p>If you specify both the <span style="font-weight: bold;">Start date</span>/<span style="font-weight: bold;">Period</span> and the <span style="font-weight: bold;">Threshold size</span>, the <span style="font-weight: bold;">Start date</span>/<span style="font-weight: bold;">Period</span> is ignored and the <span style="font-weight: bold;">Threshold size</span> is used.</p>
<p>Refer to <a href="../../transfers_start_here/monitoring_transfers_start_here/automating_maintenance#auto_log_file_archiving">Automating maintenance operations</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>Start date</p>         </td>
         <td><p>Start date and time in the format: MM<span style="font-weight: bold;">:</span>DD hh<span style="font-weight: bold;">:</span>mm<span style="font-weight: bold;">:</span>ss, where:</p>
<ul>
<li><span style="font-weight: bold;">MM</span> = month (01 - 12)</li>
<li><span style="font-weight: bold;">DD</span> = day in the month (01 - 31)</li>
<li><span style="font-weight: bold;">hh</span> = hour in the day (00 - 23)</li>
<li><span style="font-weight: bold;">mm</span> = minutes in the hour (00 - 59)</li>
<li><span style="font-weight: bold;">ss</span> = seconds in the minute (00 - 59)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Period</p>         </td>
         <td><p>The period in the format: MM<span style="font-weight: bold;">:</span>DD hh<span style="font-weight: bold;">:</span>mm<span style="font-weight: bold;">:</span>ss where:</p>
<ul>
<li><span style="font-weight: bold;">MM</span> = number of months</li>
<li><span style="font-weight: bold;">DD</span> = number of days</li>
<li><span style="font-weight: bold;">hh</span> = number of hours</li>
<li><span style="font-weight: bold;">mm</span> = number of minutes</li>
<li><span style="font-weight: bold;">ss</span> = number of seconds</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Threshold size</p>         </td>
         <td><p>Threshold size (in KB)</p>         </td>
      </tr>
   </tbody>
</table>

<span id="olh_gateway_database_protection"></span>

### Gateway &gt; Database &gt; Protection

You can configure database protection to encrypt Gateway database files using a 128-bit AES key. Database protection guarantees the confidentiality of security elements.

If activated, all Network Profile objects, Security Profile objects, Private keys and certificates (plus keys) are stored in separate encrypted files. This database protection option also applies to administration objects (Sites, Applications, and so on) and Transfer Request objects.

You can enable the payload integrity check to assure that payload haven’t changed between the moment is has been received by Gateway and further actions: routing to Integrator or routing to a third party. If activated, Gateway generates the signature for the incoming transfer’s payload, using Gateway private key and validates the signature for the routed transfers. The signature for the routed transfers can be generated either by Gateway or by Integrator. The protocols for which the signature is computed in Gateway, for incoming transfers are: SWIFTNet, PeSIT and JMS.

Use the following parameters to set up database protection options.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Parameter         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Database protection option</p>         </td>
         <td><p>To encrypt the Gateway administration files and/or the Mailbox, select one of the following values:</p>
<ul>
<li><span style="font-weight: bold;">None</span>: No database file encryption</li>
<li><span style="font-weight: bold;">Database files only</span>: Encrypt administration files only</li>
<li><span style="font-weight: bold;">Database files and transfer mailbox</span>: Encrypt administration files and the Mailbox</li>
</ul>
<p>When you use TLS and/or SSH with the Security server, you must set the encryption option to <em>Database files only</em> or <em>Database files and transfer mailbox</em>. This prevents eavesdropping and keeps critical information, such as RSA or DSA private keys, unreadable and unusable by unauthorized people.</p>
<p><strong>Important:</strong> After setting the required encryption level, you <strong>must</strong> perform the following steps:</p>
<ol>
<li><a href="../../starting_and_stopping_server/t_reloading_profile">Reload the profile</a> to set the environment variables.</li>
<li>Stop Gateway.</li>
<li>Encrypt (or unencrypt) the database files using the <span class="code" style="font-weight: bold;"><a href="../../transfers_start_here/monitoring_transfers_start_here/viewing_and_managing_mailbox_contents_cli/managing_mailbox_cli#pelmon_change_pass_phrase">pelmon change_pass_phrase</a></span> command.</li>
<li>Restart Gateway.</li>
</ol>
<p>If you do not perform these steps, the encryption level is not changed.</p>         </td>
      </tr>
      <tr>
         <td><strong>Password derived key file</strong>         </td>
         <td><p>Enter the full path and file name where the derived key for encrypting your password is stored. Gateway uses this file (and the encrypted password file) to recover the password used to encrypt and protect your administration database files and the Mailbox.</p>
<p>Click the <strong>browse</strong> button to locate and select the file.</p>         </td>
      </tr>
      <tr>
         <td><strong>Password encrypted file</strong>         </td>
         <td><p>Enter the full path and file name where the encrypted password is stored. Gateway uses this file (and the derived key file) to recover the password used to encrypt and protect your administration database files and the Mailbox.</p>
<p>Click the <strong>browse</strong> button to locate and select the file.</p>         </td>
      </tr>
      <tr>
         <td><p>Encrypt temporary received files</p>         </td>
         <td><p>Select this option to encrypt received files.</p>         </td>
      </tr>
      <tr>
         <td>Enable payload integrity check         </td>
         <td>Enable the payload signature generation for the incoming transfers and payload signature validation for the routed transfers.         </td>
      </tr>
      <tr>
         <td>RSA private key         </td>
         <td>Path to Gateway private key in PEM format         </td>
      </tr>
      <tr>
         <td>Password dk file         </td>
         <td>[Optional] path to the private key’s password derived key file. The file must be generated with the <span class="code">pelencpass </span>utility         </td>
      </tr>
      <tr>
         <td>Password enc file         </td>
         <td>[Optional] path to the private key’s password file. The file must be generated with the <span class="code">pelencpass </span>utility         </td>
      </tr>
   </tbody>
</table>

<span id="olh_gateway_connection_control"></span>

## Gateway &gt; Connection control

Use the following parameters to set up user access control.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Parameter         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">Administration control</span>:</p>         </td>
      </tr>
      <tr>
         <td><p>User access control</p>         </td>
         <td><p>This parameter controls user access to Gateway.</p>
<p>Select one of the following values:</p>
<ul>
<li><span style="font-weight: bold;">None</span>: No access control. User credentials in the login request are ignored.</li>
<li><span style="font-weight: bold;">By object type</span>: Users must provide their authentication (user ID and password) in their login request. Access control is based on object type. A user with authorized access to a type of object has the same access to all instances of that object type. Validation is carried out by Gateway or by customizable user exit routines. See Security guide &gt; <a href="#">Access control using exits</a> (requires login).</li>
<li><span style="font-weight: bold;">By object instance</span>: Users must supply their authentication (user ID and password) in their login request. Access control is based on individual object instances. Validation can only be carried out by customizable user exit routines.</li>
<li><span style="font-weight: bold;">By PassPort AM</span>: Access control is managed centrally for the <span class="mc-variable axway_variables.Platform_or_Suite_Short_Name variable">Axway Platform</span> platform by PassPort AM. See the Security Guide &gt; <a href="#">Passport AM </a></li>
</ul>
<p>See Security Guide &gt; <a href="#">Access Control Management</a>  for further information (requires login).</p>         </td>
      </tr>
      <tr>
         <td><p>Default user name</p>         </td>
         <td><p>Optional</p>
<p>Enter the default user name. The name you enter here is assigned to files that Gateway receives.</p>         </td>
      </tr>
      <tr>
         <td><p>Maximum number of simultaneous users</p>         </td>
         <td><p>Enter the maximum number of concurrent users allowed in Gateway (<span style="font-weight: bold;">1</span> - <span style="font-weight: bold;">200</span>).</p>
<p>When the upper threshold is reached, all subsequent login requests are denied.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Protocol control</span>:</p>         </td>
      </tr>
      <tr>
         <td><p><span id="connection_control_method"></span>Connection control method</p>         </td>
         <td><p>Select one of the following connection control methods:</p>
<ul>
<li><span style="font-weight: bold;">Monitor</span>: Applies no identification via CGate or exit (implements identification via static Site object)</li>
<li><span style="font-weight: bold;">CGate</span>: Applies default identification via CGates</li>
<li><span style="font-weight: bold;">Exit</span>: Executes protocol connection exit</li>
<li><span style="font-weight: bold;">CGate &amp; Exit</span>: Applies CGate identification and then executes protocol connection exit</li>
<li><span style="font-weight: bold;">Exit &amp; CGate</span>: Executes exit and then applies CGate identification. Use this option to force the use of a particular CGate.</li>
<li><span style="font-weight: bold;">Exit &amp; SGate</span>: Executes exit and then applies SGate identification. Use this option to force the use of a particular SGate.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span id="Connection_Ctrl_Meth_Per_Protocol"></span>Set option per protocol...</p>         </td>
         <td><p>Click this button to display the <span style="font-style: italic;">Gateway Connection Control Method</span> window.</p>
<p>Then, for each protocol you use, select one of the following connection control methods:</p>
<ul>
<li><span style="font-weight: bold;">Use global:</span> Applies the identification method that is specified in the global configuration parameter <span style="font-weight: bold;">Connection control method</span>.</li>
<li><span style="font-weight: bold;">Monitor:</span> *</li>
<li><span style="font-weight: bold;">CGate:</span> *</li>
<li><span style="font-weight: bold;">Exit:</span> *</li>
<li><span style="font-weight: bold;">CGate &amp; Exit:</span> *</li>
<li><span style="font-weight: bold;">Exit &amp; CGate:</span> *</li>
<li><span style="font-weight: bold;">Exit &amp; SGate:</span> *</li>
</ul>
<p>* Refer to the descriptions for <span style="font-weight: bold;">Connection control method</span> (above).</p>         </td>
      </tr>
      <tr>
         <td><p>Disable password pattern matching</p>         </td>
         <td><p>For CGate connection control methods</p>
<p>Select this option if, during user login, you want to disable the interpretation of wildcard characters in the login password (as defined in the CGate).</p>
<p>In this case, during login, Gateway analyzes the password for plain text characters only. The field content is compared "as is" with the password. The only exception is when the password field contains a single *. Then it will match a null password as well as a single *.</p>
<p>Do not select this option if you want the password field to contain any wildcard characters (as well as other printable characters).</p>
<p>Wildcard characters:</p>
<ul>
<li><span style="font-weight: bold;">*</span> = matches any character, as many occurrences as possible</li>
<li><span style="font-weight: bold;">?</span> = matches any character, only once, at the specified position in the pattern</li>
<li><span style="font-weight: bold;">[  ]</span> = specifies a set of allowed characters contained between the brackets. The user-specified password must match any one of the characters in this set, at the specified position in the pattern.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Hashed password</p>         </td>
         <td><p>Only if you have selected <span style="font-weight: bold;">Disable password pattern matching</span>.</p>
<p>Select this option if, for improved security, you want to store the user password in hashed format.</p>         </td>
      </tr>
      <tr>
         <td><p>CGate blocking</p>         </td>
         <td><p>Select this option to enable connection blocking at the CGate level.</p>
<p>If you use this option, check the values of the <span style="font-weight: bold;">Maximum login attempts before blocking</span> and <span style="font-weight: bold;">Blocking duration</span> parameters.</p>         </td>
      </tr>
      <tr>
         <td><p>Maximum login attempts before blocking</p>         </td>
         <td><p>Enter the maximum number of login attempts before temporarily blocking the connection at CGate level.</p>         </td>
      </tr>
      <tr>
         <td><p>Blocking duration</p>         </td>
         <td><p>Enter the blocking duration (in seconds) before allowing a new connection attempt at CGate level.</p>         </td>
      </tr>
      <tr>
         <td><p>Maximum number of initiated connections</p>         </td>
         <td><p>Enter the maximum number of simultaneous initiated connections allowed.</p>
<p><span style="font-weight: bold;">1</span> - <span style="font-weight: bold;">999</span> (default: <span style="font-weight: bold;">100</span>).</p>         </td>
      </tr>
      <tr>
         <td><p>Maximum number of responded connections</p>         </td>
         <td><p>Enter the maximum number of simultaneous responded connections allowed.</p>
<p><span style="font-weight: bold;">1</span> - <span style="font-weight: bold;">999</span> (default: <span style="font-weight: bold;">100</span>).</p>         </td>
      </tr>
      <tr>
         <td><p><strong>User inactivity timeout (minutes)</strong></p>         </td>
         <td><p>Enter the user inactivity timeout for users connected in Gateway, representing the number of minutes after which the user is timed out and disconnected from Gateway. If set to <strong>0</strong>, the user inactivity timer will be infinite and the user will never be automatically logged out. The value can also be set using a line command:<br />
<span class="code">peluconf set -s monitor user_idle_timeout 10 </span></p>
<p><strong>0 – 65000</strong> (default: <strong>15</strong>).</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Trace_file_archiving_parameters"></span>

## Trace file archiving parameters

The following table provides details of the trace file archiving (collecting) parameters accessible through the peluconf command. You can find these parameters (or add them) in the collector configuration section.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Parameter         </th>
<th class="HeadE-Column1-Header1">Description         </th>
<th class="HeadD-Column1-Header1">Default value         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><span class="code">max_files_to_move</span>         </td>
         <td>Specifies the maximum number of files to be moved per iteration during a trace files collect operation. This should be fraction of the <code>max_files_to_collect </code>parameter.         </td>
         <td>10         </td>
      </tr>
      <tr>
         <td><span class="code">max_files_to_collect</span>         </td>
         <td>Specifies the maximum number of trace files to be considered for a collection per iteration during preparation of the archive operation.         </td>
         <td>100         </td>
      </tr>
      <tr>
         <td><span class="code">collect_interval</span>         </td>
         <td>Specifies the interval (in minutes) between two successive trace file collector runs.         </td>
         <td>10         </td>
      </tr>
      <tr>
         <td><code>collect_delay</code>         </td>
         <td>Specifies the interval (in minutes) from the Gateway start until the trace collector is first activated.         </td>
         <td>0         </td>
      </tr>
      <tr>
         <td><span class="code">archive_path</span>         </td>
         <td>Specifies the directory where the archived traces are to be moved.         </td>
         <td><span class="code">%p_home_dir%\run_time\tmp\archive</span>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Configuration: Procedure](../config_procedure)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
