{
    "title": "Catalog of online commands",
    "linkTitle": "Catalog of online commands",
    "weight": "130"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: User Interfaces

This topic lists all <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span> online commands and related subcommands.

For each command, this topic provides:

-   A brief description of the use of the command
-   The command syntax
-   A list of subcommands
-   Links to topics that provide more detailed information

## Online commands

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><ul>
<li><a href="#peladm">peladm</a></li>
<li><a href="#pelbase">pelbase</a></li>
<li><a href="#pelctl">pelctl</a></li>
<li><a href="#peldconf">peldconf</a></li>
<li><a href="#peldsp">peldsp</a></li>
<li><a href="#pelexport">pelexport</a></li>
</ul>         </td>
         <td><ul>
<li><a href="#pelimport">pelimport</a></li>
<li><a href="#pelinst">pelinst</a></li>
<li><a href="#pelmig">pelmig</a></li>
<li><a href="#pelmon">pelmon</a></li>
<li><a href="#pelpur">pelpur</a></li>
<li><a href="#peltrans">peltrans</a></li>
</ul>         </td>
         <td><ul>
<li><a href="#secadm">secadm</a></li>
<li><a href="#secdsp">secdsp</a></li>
<li><a href="#vfdadm">vfdadm</a></li>
<li><a href="#vfddsp">vfddsp</a></li>
</ul>         </td>
      </tr>
   </tbody>
</table>

## Locating the appropriate command

To locate a command from a list of command task descriptions, refer to [Index of tasks](../online_commands_task_index).

For an overview of online command use, syntax and help sources, refer to [About online commands](../).

> **Note:**
>
> If you follow links to the Security guide on the Axway documentation portal, you will be required to be logged in.

<span id="peladm"></span>

## peladm

### Purpose

Use the <span class="code" style="font-weight: bold;">peladm</span> command to create, modify, and delete the following objects in the Gateway database:

-   Sites
-   Applications
-   Models
-   Diffusion Lists
-   CGates
-   CGateGroups
-   Users and Profiles
-   Decision Rules
-   Rule Table
-   Proxies

The <span class="code" style="font-weight: bold;">peladm</span> subcommands identify the object and the type of action to perform. For example, <span class="code" style="font-weight: bold;">peladm</span><span class="code"> delete\_site</span> identifies the object as a Remote Site and specifies deletion as the action to perform.

Each subcommand is associated with a set of parameters that define object properties.

### Syntax

peladm \[<span style="font-weight: normal;">subcommand</span>\] \[<span style="font-weight: normal;">parameters</span>\]

### Subcommands

This table lists the subcommands of the <span class="code" style="font-weight: bold;">peladm</span> command.

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Subcommand         </th>
<th class="HeadE-Column1-Header1">Use to...         </th>
<th class="HeadD-Column1-Header1">Additional information         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><span id="peladm_create_site"></span>peladm create_site</p>         </td>
         <td><p>create Remote Sites</p>         </td>
         <td><p><a href="../../../managing_partners_start_here/sites_start_here/managing_local_sites_cli/managing_remote_sites_cli">Working with Remote Sites (command line)</a></p>         </td>
      </tr>
      <tr>
         <td><p><span id="peladm_update_site"></span>peladm update_site</p>         </td>
         <td><p>update Remote Sites</p>         </td>
      </tr>
      <tr>
         <td><p><span id="peladm_delete_site"></span>peladm delete_site</p>         </td>
         <td><p>delete Remote Sites</p>         </td>
      </tr>
      <tr>
         <td><p><span id="peladm_create_loc_site"></span>peladm create_loc_site</p>         </td>
         <td><p>create Local Sites</p>         </td>
         <td><p><a href="../../../managing_partners_start_here/sites_start_here/managing_local_sites_cli">Working with Local Sites (command line)</a></p>         </td>
      </tr>
      <tr>
         <td><p><span id="peladm_update_loc_site"></span>peladm update_loc_site</p>         </td>
         <td><p>update Local Sites</p>         </td>
      </tr>
      <tr>
         <td><p><span id="peladm_delete_loc_site"></span>peladm delete_loc_site</p>         </td>
         <td><p>delete Local Sites</p>         </td>
      </tr>
      <tr>
         <td><p><span id="peladm_create_appli"></span>peladm create_appli</p>         </td>
         <td><p>create Applications</p>         </td>
         <td><p><a href="../../../transfers_start_here/parameters_start_here/applications_start_here/working_with_applications_cli">Working with Applications (command line)</a></p>         </td>
      </tr>
      <tr>
         <td><p><span id="peladm_update_appli"></span>peladm update_appli</p>         </td>
         <td><p>update Applications</p>         </td>
      </tr>
      <tr>
         <td><p><span id="peladm_delete_appli"></span>peladm delete_appli</p>         </td>
         <td><p>delete Applications</p>         </td>
      </tr>
      <tr>
         <td><p><span id="peladm_create_list"></span>peladm create_list</p>         </td>
         <td><p>create Diffusion List</p>         </td>
         <td><p><a href="../../../managing_partners_start_here/diffusion_lists_start_here/working_with_diffusion_lists_cli">Working with Diffusion Lists (command line)</a></p>         </td>
      </tr>
      <tr>
         <td><p><span id="peladm_update_list"></span>peladm update_list</p>         </td>
         <td><p>update Diffusion List</p>         </td>
      </tr>
      <tr>
         <td><p><span id="peladm_delete_list"></span>peladm delete_list</p>         </td>
         <td><p>delete Diffusion List</p>         </td>
      </tr>
      <tr>
         <td><p><span id="peladm_create_model"></span>peladm create_model</p>         </td>
         <td><p>create Models</p>         </td>
         <td><p><a href="../../../transfers_start_here/parameters_start_here/models_start_here/working_with_models_cli">Working with Models (command line)</a></p>         </td>
      </tr>
      <tr>
         <td><p><span id="peladm_update_model"></span>peladm update_model</p>         </td>
         <td><p>update Models</p>         </td>
      </tr>
      <tr>
         <td><p><span id="peladm_delete_model"></span>peladm delete_model</p>         </td>
         <td><p>delete Models</p>         </td>
      </tr>
      <tr>
         <td><p><span id="peladm_create_user"></span>peladm create_user</p>         </td>
         <td><p>create Users</p>         </td>
         <td><p>See the <em>Security Guide &gt; <a href="/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/Managing_Security/access_control/managing_users_CLI.htm">Working with Users (command line)</a></em> for further information.</p>         </td>
      </tr>
      <tr>
         <td><p><span id="peladm_update_user"></span>peladm update_user</p>         </td>
         <td><p>update Users</p>         </td>
      </tr>
      <tr>
         <td><p><span id="peladm_delete_user"></span>peladm delete_user</p>         </td>
         <td><p>delete Users</p>         </td>
      </tr>
      <tr>
         <td><p><span id="peladm_create_profile"></span>peladm create_profile</p>         </td>
         <td><p>create Profiles</p>         </td>
         <td><p>See the <em>Security Guide &gt; <a href="/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/Managing_Security/access_control/managing_profiles_CLI.htm">Working with Profiles (command line)</a></em> for further information.</p>         </td>
      </tr>
      <tr>
         <td><p><span id="peladm_update_profile"></span>peladm update_profile</p>         </td>
         <td><p>update Profiles</p>         </td>
      </tr>
      <tr>
         <td><p><span id="peladm_delete_profile"></span>peladm delete_profile</p>         </td>
         <td><p>delete Profiles</p>         </td>
      </tr>
      <tr>
         <td><p>peladm create_purge_model</p>         </td>
         <td><p>create Purge Model</p>         </td>
         <td><p><a href="../../../transfers_start_here/parameters_start_here/models_start_here/working_with_purge_models_cli">Working with Purge Models (command line)</a></p>         </td>
      </tr>
      <tr>
         <td><p>peladm update_purge_model</p>         </td>
         <td><p>update Purge Model</p>         </td>
      </tr>
      <tr>
         <td><p>peladm delete_purge_model</p>         </td>
         <td><p>delete Purge Model</p>         </td>
      </tr>
      <tr>
         <td><p><span id="peladm_update_trans"></span>peladm update_trans</p>         </td>
         <td><p>update Transfers</p>         </td>
         <td><p><a href="../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_cli">Working with Transfers (command line)</a></p>         </td>
      </tr>
      <tr>
         <td><p><span id="peladm_create_cgate"></span>peladm create_cgate</p>         </td>
         <td><p>create CGates</p>         </td>
         <td><p><a href="../../../managing_partners_start_here/cgates_start_here/working_with_cgates_cli">Working with CGates (command line)</a></p>         </td>
      </tr>
      <tr>
         <td><p><span id="peladm_update_cgate"></span>peladm update_cgate</p>         </td>
         <td><p>update CGates</p>         </td>
      </tr>
      <tr>
         <td><p><span id="peladm_delete_cgate"></span>peladm delete_cgate</p>         </td>
         <td><p>delete CGates</p>         </td>
      </tr>
      <tr>
         <td><p><span id="peladm_create_cgategroup"></span>peladm create_cgategroup</p>         </td>
         <td><p>create CGateGroups</p>         </td>
         <td><p><a href="../../../managing_partners_start_here/cgates_start_here/working_with_cgates_cli/working_with_cgategroups_cli">Working with CGateGroups (command line)</a></p>         </td>
      </tr>
      <tr>
         <td><p><span id="peladm_update_cgategroup"></span>peladm update_cgategroup</p>         </td>
         <td><p>update CGateGroups</p>         </td>
      </tr>
      <tr>
         <td><p><span id="peladm_delete_cgategroup"></span>peladm delete_cgategroup</p>         </td>
         <td><p>delete CGateGroups</p>         </td>
      </tr>
      <tr>
         <td><p><span id="peladm_create_ruletable"></span>peladm create_ruletable</p>         </td>
         <td><p>create Rule Tables</p>         </td>
         <td><p><a href="../../../managing_events_start_here/working_with_decision_rules_cli/working_with_rule_tables_cli">Working with Rule Tables (command line)</a></p>         </td>
      </tr>
      <tr>
         <td><p><span id="peladm_update_rule_table"></span>peladm update_ruletable</p>         </td>
         <td><p>set or modify the properties of the Rule Table</p>         </td>
      </tr>
      <tr>
         <td><p><span id="peladm_delete_ruletable"></span>peladm delete_ruletable</p>         </td>
         <td><p>delete Rule Tables</p>         </td>
      </tr>
      <tr>
         <td><p><span id="peladm_create_decisionrule"></span>peladm create_decisionrule</p>         </td>
         <td><p>create Decision Rules</p>         </td>
         <td><p><a href="../../../managing_events_start_here/working_with_decision_rules_cli">Working with Decision Rules (command line)</a></p>         </td>
      </tr>
      <tr>
         <td><p><span id="peladm_update_decisionrule"></span>peladm update_decisionrule</p>         </td>
         <td><p>update Decision Rules</p>         </td>
      </tr>
      <tr>
         <td><p><span id="peladm_delete_decisionrule"></span>peladm delete_decisionrule</p>         </td>
         <td><p>delete Decision Rules</p>         </td>
      </tr>
      <tr>
         <td><p><span id="peladm_create_prop_list"></span>peladm create_proplist</p>         </td>
         <td><p>create Axway Messaging connector Properties List</p>         </td>
         <td><p><a href="../../../connectors_about/messaging_connector/messaging_working_with_cli">Working with the Axway Messaging connector (command line)</a></p>         </td>
      </tr>
      <tr>
         <td><p><span id="peladm_update_prop_list"></span>peladm update_proplist</p>         </td>
         <td><p>update Axway Messaging connector Properties List</p>         </td>
      </tr>
      <tr>
         <td><p><span id="peladm_delete_prop_list"></span>peladm delete_proplist</p>         </td>
         <td><p>delete Axway Messaging connector Properties List</p>         </td>
      </tr>
      <tr>
         <td><p><span id="peladm_create_proxy"></span>peladm create_proxy</p>         </td>
         <td><p>create Proxies</p>         </td>
         <td><p><a href="../../../managing_partners_start_here/proxies_about/managing_proxies_cli">Working with Proxies (command line)</a></p>         </td>
      </tr>
      <tr>
         <td><p><span id="peladm_update_proxy"></span>peladm update_proxy</p>         </td>
         <td><p>update Proxies</p>         </td>
      </tr>
      <tr>
         <td><p><span id="peladm_delete_proxy"></span>peladm delete_proxy</p>         </td>
         <td><p>delete Proxies</p>         </td>
      </tr>
      <tr>
         <td><p>peladm create_tradepart</p>         </td>
         <td>create Trading Partners         </td>
         <td><a href="../../../managing_partners_start_here/trading_partners_start_here/working_with_trading_partners_cli">Working with Trading Partner objects (command line)</a>         </td>
      </tr>
      <tr>
         <td><p>peladm update_tradepart</p>         </td>
         <td>update Trading Partners         </td>
      </tr>
      <tr>
         <td><p>peladm delete_tradepart</p>         </td>
         <td>delete Trading Partners         </td>
      </tr>
   </tbody>
</table>

<span id="pelbase"></span>

## pelbase

### Purpose

Use the <span class="code" style="font-weight: bold;">pelbase</span> command to export Gateway objects from the database to an ASCII file or import objects from an ASCII file to the database.

You can export records in different formats depending on your requirements, so that you can adapt the records to your operating system (for example, you can complete the fields with environment variables).

### Syntax

pelbase \[<span style="font-weight: normal;">subcommand</span>\] \[<span style="font-weight: normal;">parameters</span>\]

### Subcommands

This table lists the subcommands of the <span class="code" style="font-weight: bold;">pelbase</span> command.

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Subcommand         </th>
<th class="HeadE-Column1-Header1">Use to...         </th>
<th class="HeadD-Column1-Header1">Additional information         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><span id="pelbase_export_site"></span>pelbase export_site</p>         </td>
         <td><p>export a Remote Site</p>         </td>
         <td><p><a href="../../../starting_and_stopping_server/importing_and_exporting_objects">Importing and exporting objects</a></p>         </td>
      </tr>
      <tr>
         <td><p><span id="pelbase_export_appli"></span>pelbase export_appli</p>         </td>
         <td><p>export an Application</p>         </td>
      </tr>
      <tr>
         <td><p><span id="pelbase_export_model"></span>pelbase export_model</p>         </td>
         <td><p>export a Model</p>         </td>
      </tr>
      <tr>
         <td><p><span id="pelbase_export_purge_model"></span>pelbase export_purge_model</p>         </td>
         <td><p>export a Purge Model</p>         </td>
      </tr>
      <tr>
         <td><p><span id="pelbase_export_list"></span>pelbase export_list</p>         </td>
         <td><p>export a Diffusion List</p>         </td>
      </tr>
      <tr>
         <td><p><span id="pelbase_export_user"></span>pelbase export_user</p>         </td>
         <td><p>export a User</p>         </td>
      </tr>
      <tr>
         <td><p><span id="pelbase_export_profile"></span>pelbase export_profile</p>         </td>
         <td><p>export a Profile</p>         </td>
      </tr>
      <tr>
         <td><p><span id="pelbase_export_cgate"></span>pelbase export_cgate</p>         </td>
         <td><p>export a CGate</p>         </td>
      </tr>
      <tr>
         <td><p><span id="pelbase_export_cgategroup"></span>pelbase export_cgategroup</p>         </td>
         <td><p>export a CGateGroup</p>         </td>
      </tr>
      <tr>
         <td><p><span id="pelbase_export_sgate"></span>pelbase export_sgate</p>         </td>
         <td><p>export an SGate</p>         </td>
      </tr>
      <tr>
         <td><p><span id="pelbase_export_sgategroup"></span>pelbase export_sgategroup</p>         </td>
         <td><p>export an SGateGroup</p>         </td>
      </tr>
      <tr>
         <td><p><span id="pelbase_export_proxy"></span>pelbase export_proxy</p>         </td>
         <td><p>export a Proxy</p>         </td>
      </tr>
      <tr>
         <td><p><span id="pelbase_export_decisionrule"></span>pelbase export_decisionrule</p>         </td>
         <td><p>export a Decision Rule</p>         </td>
      </tr>
      <tr>
         <td><p><span id="pelbase_export_rule_table"></span>pelbase export_ruletable</p>         </td>
         <td><p>export a Rule Table</p>         </td>
      </tr>
      <tr>
         <td><p><span id="pelbase_import"></span>pelbase import</p>         </td>
         <td><p>import an object</p>         </td>
      </tr>
   </tbody>
</table>

<span id="pelctl"></span>

## pelctl

### Purpose

Use the <span class="code" style="font-weight: bold;">pelctl</span> command to:

-   Start and stop the activity on a Site
-   Start, stop and cancel actions relating to Transfer states
-   Suspend or resume Log file recording and archiving
-   Suspend or resume Stat file recording and archiving
-   Manage tracing processes

The related subcommands identify the object you want to select. The subcommands are associated with a set of selection parameters.

### Syntax

**pelctl** \[subcommand\] \[parameters\]

### Subcommands

This table lists the subcommands of the <span class="code" style="font-weight: bold;">pelctl</span> command.

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Subcommand         </th>
<th class="HeadE-Column1-Header1">Use to...         </th>
<th class="HeadD-Column1-Header1">Additional information         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><span id="pelctl_start_site"></span>pelctl start_site</p>         </td>
         <td><p>Start a Site</p>         </td>
         <td><p><a href="../../../managing_partners_start_here/sites_start_here/managing_local_sites_cli/managing_remote_sites_cli">Working with Remote Sites (command line)</a></p>         </td>
      </tr>
      <tr>
         <td><p><span id="pelctl_stop_site"></span>pelctl stop_site</p>         </td>
         <td><p>Stop a Site</p>         </td>
      </tr>
      <tr>
         <td><p><span id="pelctl_control_trans"></span>pelctl control_trans</p>         </td>
         <td><p>Control a Transfer</p>         </td>
         <td><p><a href="../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_cli">Working with Transfers (command line)</a></p>         </td>
      </tr>
      <tr>
         <td><p><span id="pelctl_archive_log"></span>pelctl archive_log</p>         </td>
         <td><p>Archive the Log</p>         </td>
         <td><p><a href="../../../transfers_start_here/monitoring_transfers_start_here/log_files/working_with_logs_cli#pelctl_archive_log">pelctl archive_log</a></p>         </td>
      </tr>
      <tr>
         <td><p><span id="pelctl_suspend_log"></span>pelctl suspend_log</p>         </td>
         <td><p>Suspend Log recording</p>         </td>
         <td><p><a href="../../../transfers_start_here/monitoring_transfers_start_here/log_files/working_with_logs_cli#pelctl_suspend_log">pelctl suspend_log</a></p>         </td>
      </tr>
      <tr>
         <td><p><span id="pelctl_resume_log"></span>pelctl resume_log</p>         </td>
         <td><p>Resume Log recording</p>         </td>
         <td><p><a href="../../../transfers_start_here/monitoring_transfers_start_here/log_files/working_with_logs_cli#pelctl_resume_log">pelctl resume_log</a></p>         </td>
      </tr>
      <tr>
         <td><p><span id="pelctl_archive_stat"></span>pelctl archive_stat</p>         </td>
         <td><p>Archive Statistics file</p>         </td>
         <td><p><a href="../../../transfers_start_here/monitoring_transfers_start_here/viewing_and_managing_mailbox_contents_cli/managing_statistics_files#pelctl_archive_stat">pelctl archive_stat</a></p>         </td>
      </tr>
      <tr>
         <td><p><span id="pelctl_suspend_stat"></span>pelctl suspend_stat</p>         </td>
         <td><p>Suspend Statistics recording</p>         </td>
         <td><p><a href="../../../transfers_start_here/monitoring_transfers_start_here/viewing_and_managing_mailbox_contents_cli/managing_statistics_files#pelctl_suspend_stat">pelctl suspend_stat</a></p>         </td>
      </tr>
      <tr>
         <td><p><span id="pelctl_resume_stat"></span>pelctl resume_stat</p>         </td>
         <td><p>Resume Statistics recording</p>         </td>
         <td><p><a href="../../../transfers_start_here/monitoring_transfers_start_here/viewing_and_managing_mailbox_contents_cli/managing_statistics_files#pelctl_resume_stat">pelctl resume_stat</a></p>         </td>
      </tr>
      <tr>
         <td><p>pelctl load_net_security</p>         </td>
         <td><p>This command is present for compatibility purposes only and should no longer be used. It has been replaced by Network Profile.</p>
<p>Reload the content of the <span class="code">tablex25.adr</span> and <span class="code">tableip.adr</span> files.</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>pelctl load_tcp_org_port</p>         </td>
         <td><p>This command is present for compatibility purposes only and should no longer be used.</p>
<p>Reload the content of the file <span class="code">tcpoport.ini</span> after it has been modified.</p>
<p>The file <span class="code">tcpoport.ini</span> is used to assign the origin TCP port number for outgoing connections.</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p><span id="pelctl_trace_process"></span>pelctl trace_process</p>         </td>
         <td><p>Obtain trace data for Gateway processing</p>         </td>
         <td><p><a href="../../../starting_and_stopping_server/server_traces#pelctl_trace_process">pelctl trace_process</a></p>         </td>
      </tr>
      <tr>
         <td><p><span id="pelctl_trace_entitiy"></span>pelctl trace_entity</p>         </td>
         <td><p>Obtain trace data for a Gateway entity (sub-task of a process)</p>         </td>
         <td><p><a href="../../../starting_and_stopping_server/server_traces#pelctl_trace_entity">pelctl trace_entity</a></p>         </td>
      </tr>
      <tr>
         <td><p>pelctl trace_rotate</p>         </td>
         <td><p>Trigger the trace rotation</p>         </td>
         <td><p><a href="../../../starting_and_stopping_server/trace_rotate">Managing rotation and archiving of trace files</a></p>         </td>
      </tr>
      <tr>
         <td><p><span id="pelctl_kill_connection"></span>pelctl kill_connection</p>         </td>
         <td><p>Kill a Connection</p>         </td>
         <td><p><a href="../../../transfers_start_here/monitoring_transfers_start_here/viewing_and_managing_mailbox_contents_cli/monitoring_connections_cli">Monitoring Connections (command line)</a></p>         </td>
      </tr>
      <tr>
         <td><p><span id="pelctl_disconnect_user"></span>pelctl disconnect_user</p>         </td>
         <td><p>Disconnect a User</p>         </td>
         <td><p><a href="../../../transfers_start_here/monitoring_transfers_start_here/viewing_and_managing_mailbox_contents_cli/monitoring_connected_users_cli">Monitoring Connected Users (command line)</a></p>         </td>
      </tr>
      <tr>
         <td><p><span id="pelctl_reset_connected_user"></span>pelctl reset_connected_user</p>         </td>
         <td><p>Resets user quota to zero. An administrator can use this command to reassign access to users who have exceeded their quotas.</p>         </td>
      </tr>
      <tr>
         <td><p><span id="pelctl_detect"></span>pelctl detect_swift_recovery</p>         </td>
         <td>Initiates a manual system recovery detection procedure         </td>
         <td><a href="../../../connectors_about/swiftnet_about/swiftnet_sig_list/swiftnet_system_recovery#manual">SWIFTNet system recovery</a>         </td>
      </tr>
      <tr>
         <td><p><span id="pelctl_acquire_swqueue"></span>pelctl acquire_swqueue</p>         </td>
         <td><p>Acquire a SWIFTNet queue.</p>         </td>
         <td><p><a href="../../../connectors_about/swiftnet_about/swiftnet_connector/swiftnet_configuring#pelctl_acquire_swqueue">Configuring the <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>/SWIFTNet environment</a></p>         </td>
      </tr>
      <tr>
         <td><p><span id="pelctl_release_swqueue"></span>pelctl release_swqueue</p>         </td>
         <td><p>Release a SWIFTNet queue.</p>         </td>
      </tr>
      <tr>
         <td><p>pelctl open_output_channel</p>         </td>
         <td><p>Open a SWIFTNet output channel.</p>         </td>
         <td><p><a href="../../../connectors_about/swiftnet_about/swiftnet_input_channels/swiftnet_output_channels#control_op">SWIFTNet queues and output channels</a></p>         </td>
      </tr>
      <tr>
         <td><p>pelctl close_output_channel</p>         </td>
         <td><p>Close a SWIFTNet output channel.</p>         </td>
      </tr>
      <tr>
         <td><p><span id="pelctl_reload_asp_profiles"></span>pelctl reload_asp_profiles</p>         </td>
         <td>Reload SWIFTNet ASP profiles.         </td>
         <td><p><a href="../../../connectors_about/swiftnet_about/swiftnet_asp_check_commands/swiftnet_asp_check">SWIFTNet ASP check</a></p>         </td>
      </tr>
      <tr>
         <td><p><span id="pelctl_check_asp_status"></span>pelctl check_asp_status</p>         </td>
         <td>Check SWIFTNet ASP profiles status.         </td>
      </tr>
      <tr>
         <td><p>pelctl open_input_channel</p>         </td>
         <td><p>Open a SWIFTNet input channel.</p>         </td>
         <td><p><a href="../../../connectors_about/swiftnet_about/swiftnet_input_channels">SWIFTNet input channels</a></p>         </td>
      </tr>
      <tr>
         <td><p>pelctl close_input_channel</p>         </td>
         <td><p>Close a SWIFTNet input channel.</p>         </td>
      </tr>
      <tr>
         <td><p>pelctl delete_input_channel</p>         </td>
         <td><p>Delete a SWIFTNet input channel.</p>         </td>
      </tr>
      <tr>
         <td><p>pelctl create_output_channel</p>         </td>
         <td><p>Create a SWIFTNet output channel.</p>         </td>
         <td><p><a href="../../../connectors_about/swiftnet_about/swiftnet_input_channels/swiftnet_output_channels">SWIFTNet queues and output channels</a></p>         </td>
      </tr>
      <tr>
         <td><p>pelctl delete_output_channel</p>         </td>
         <td><p>Delete a SWIFTNet output channel.</p>         </td>
      </tr>
      <tr>
         <td><span class="code" style="font-weight: bold;">pelctl reload_xsr_ipfilter_file</span>         </td>
         <td>Reload the blacklist (black list) file dynamically, without restarting <span class="mc-variable suite_variables.GatewayName variable">Gateway</span>.         </td>
         <td>          </td>
      </tr>
   </tbody>
</table>

<span id="peldconf"></span>

## peldconf

### Purpose

This command is now deprecated.

The <span class="code" style="font-weight: bold;">peldconf</span> command was previously used to dynamically modify the Gateway configuration.

<span id="peldsp"></span>

## peldsp

### Purpose

Use the <span class="code" style="font-weight: bold;">peldsp</span> command to select the following objects defined in the administration database and display their parameters:

-   Sites
-   Applications
-   Models
-   Diffusion Lists
-   Users and Profiles
-   CGates and CGateGroups
-   Connections and Connected Users
-   Diffusion List and Transfer Requests
-   Decision Rules
-   Rule Tables
-   Properties lists
-   Proxies
-   Axway Messaging connectors

Use subcommands with <span class="code" style="font-weight: bold;">peldsp</span> to identify the type of object you want to select. The subcommands are associated with selection parameters.

### Syntax

peldsp \[<span style="font-weight: normal;">subcommand</span>\] \[<span style="font-weight: normal;">parameters</span>\]

### Subcommands

This table lists the subcommands of the <span class="code" style="font-weight: bold;">peldsp</span> command.

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Subcommand         </th>
<th class="HeadE-Column1-Header1">Use to...         </th>
<th class="HeadD-Column1-Header1">Additional information         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><span id="peldsp_select_site"></span>peldsp select_site</p>         </td>
         <td><p>display a selected list of Remote Sites</p>         </td>
         <td><p><a href="../../../managing_partners_start_here/sites_start_here/managing_local_sites_cli/managing_remote_sites_cli">Working with Remote Sites (command line)</a></p>         </td>
      </tr>
      <tr>
         <td><p><span id="peldsp_display_site"></span>peldsp display_site</p>         </td>
         <td><p>display the attributes of a Remote Site</p>         </td>
      </tr>
      <tr>
         <td><p><span id="peldsp_status_site"></span>peldsp status_site</p>         </td>
         <td><p>display the initial and dynamic states of a Remote Site</p>         </td>
      </tr>
      <tr>
         <td><p><span id="peldsp_select_loc_site"></span>peldsp select_loc_site</p>         </td>
         <td><p>display a selected list of Local  Sites</p>         </td>
         <td><p><a href="../../../managing_partners_start_here/sites_start_here/managing_local_sites_cli">Working with Local Sites (command line)</a></p>         </td>
      </tr>
      <tr>
         <td><p><span id="peldsp_diplay_loc_site"></span>peldsp display_loc_site</p>         </td>
         <td><p>display the parameters of a Local Site</p>         </td>
      </tr>
      <tr>
         <td><p><span id="peldsp_status_loc_site"></span>peldsp status_loc_site</p>         </td>
         <td><p>display the initial and dynamic states of a Local Site</p>         </td>
      </tr>
      <tr>
         <td><p><span id="peldsp_select_appli"></span>peldsp select_appli</p>         </td>
         <td><p>display a selected list of Applications</p>         </td>
         <td><p><a href="../../../transfers_start_here/parameters_start_here/applications_start_here/working_with_applications_cli">Working with Applications (command line)</a></p>         </td>
      </tr>
      <tr>
         <td><p><span id="peldsp_display_appli"></span>peldsp display_appli</p>         </td>
         <td><p>display the parameters of an Application</p>         </td>
      </tr>
      <tr>
         <td><p><span id="peldsp_select_model"></span>peldsp select_model</p>         </td>
         <td><p>display a selected list of Models</p>         </td>
         <td><p><a href="../../../transfers_start_here/parameters_start_here/models_start_here/working_with_models_cli">Working with Models (command line)</a></p>         </td>
      </tr>
      <tr>
         <td><p><span id="peldsp_display_model"></span>peldsp display_model</p>         </td>
         <td><p>display the parameters of a Model</p>         </td>
      </tr>
      <tr>
         <td><p><span id="peldsp_select_list"></span>peldsp select_list</p>         </td>
         <td><p>display a selected list of Diffusion Lists</p>         </td>
         <td><p><a href="../../../managing_partners_start_here/diffusion_lists_start_here/working_with_diffusion_lists_cli">Working with Diffusion Lists (command line)</a></p>         </td>
      </tr>
      <tr>
         <td><p><span id="peldsp_display_list"></span>peldsp display_list</p>         </td>
         <td><p>display the parameters of a Diffusion List</p>         </td>
      </tr>
      <tr>
         <td><p><span id="peldsp_select_user"></span>peldsp select_user</p>         </td>
         <td><p>display a selected list of Users</p>         </td>
         <td><p>See the <em>Security Guide &gt;</em> <a href="/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/Managing_Security/access_control/managing_users_CLI.htm">Working with users (command line)</a> for further information.</p>         </td>
      </tr>
      <tr>
         <td><p><span id="peldsp_display_user"></span>peldsp display_user</p>         </td>
         <td><p>display the parameters of Users</p>         </td>
      </tr>
      <tr>
         <td><p><span id="peldsp_select_profile"></span>peldsp select_profile</p>         </td>
         <td><p>display a selected list of Profiles</p>         </td>
         <td><p>See the <em>Security Guide &gt; <a href="/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/Managing_Security/access_control/managing_profiles_CLI.htm">Working with Profiles (command line)</a></em> for further information.</p>         </td>
      </tr>
      <tr>
         <td><p><span id="peldsp_display_profile"></span>peldsp display_profile</p>         </td>
         <td><p>display the parameters of Profiles</p>         </td>
      </tr>
      <tr>
         <td><p><span id="peldsp_select_trans"></span>peldsp select_trans</p>         </td>
         <td><p>display a selected list of Transfer Requests</p>         </td>
         <td><p><a href="../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_cli">Working with Transfers (command line)</a></p>         </td>
      </tr>
      <tr>
         <td><p><span id="peldsp_display_trans"></span>peldsp display_trans</p>         </td>
         <td><p>display the parameters of a Transfer Request</p>         </td>
      </tr>
      <tr>
         <td><p><span id="peldsp_status_trans"></span>peldsp status_trans</p>         </td>
         <td><p>display a selected list of Transfer Request with a subset of information for each selected Request</p>         </td>
      </tr>
      <tr>
         <td><p><span id="peldsp_select_cgate"></span>peldsp select_cgate</p>         </td>
         <td><p>display a selected list of CGates</p>         </td>
         <td><p><a href="../../../managing_partners_start_here/cgates_start_here/working_with_cgates_cli">Working with CGates (command line)</a></p>         </td>
      </tr>
      <tr>
         <td><p><span id="peldsp_display_cgate"></span>peldsp display_cgate</p>         </td>
         <td><p>display the parameters of CGates</p>         </td>
      </tr>
      <tr>
         <td><p><span id="peldsp_select_cgate_group"></span>peldsp select_cgategroup</p>         </td>
         <td><p>display a selected list of CGateGroups</p>         </td>
         <td><p><a href="../../../managing_partners_start_here/cgates_start_here/working_with_cgates_cli/working_with_cgategroups_cli">Working with CGateGroups (command line)</a></p>         </td>
      </tr>
      <tr>
         <td><p><span id="peldsp_display_cgategroup"></span>peldsp display_cgategroup</p>         </td>
         <td><p>display the parameters of CGateGroups</p>         </td>
      </tr>
      <tr>
         <td><p><span id="peldsp_select_connection"></span>peldsp select_connection</p>         </td>
         <td><p>display a selected list of Connections</p>         </td>
         <td><p><a href="../../../transfers_start_here/monitoring_transfers_start_here/viewing_and_managing_mailbox_contents_cli/monitoring_connections_cli">Monitoring Connections (command line)</a></p>         </td>
      </tr>
      <tr>
         <td><p><span id="peldsp_display_connection"></span>peldsp display_connection</p>         </td>
         <td><p>display the parameters of a Connection</p>         </td>
      </tr>
      <tr>
         <td><p><span id="peldsp_status_connection"></span>peldsp status_connection</p>         </td>
         <td><p>display the initial and dynamic states of a Connection</p>         </td>
      </tr>
      <tr>
         <td><p><span id="peldsp_select _connected user"></span>peldsp select_connected_user</p>         </td>
         <td><p>display a selected list of Connected Users</p>         </td>
         <td><p><a href="../../../transfers_start_here/monitoring_transfers_start_here/viewing_and_managing_mailbox_contents_cli/monitoring_connected_users_cli">Monitoring Connected Users (command line)</a></p>         </td>
      </tr>
      <tr>
         <td><p><span id="peldsp_display_connected_user"></span>peldsp display_connected_user</p>         </td>
         <td><p>display the parameters of a Connected User</p>         </td>
      </tr>
      <tr>
         <td><p><span id="peldsp_status_connected_user"></span>peldsp status_connected_user</p>         </td>
         <td><p>display the initial and dynamic states of a Connected User</p>         </td>
      </tr>
      <tr>
         <td><p><span id="peldsp_select_decisionrule"></span>peldsp select_decisionrule</p>         </td>
         <td><p>display a list of Decision Rules</p>         </td>
         <td><p><a href="../../../managing_events_start_here/working_with_decision_rules_cli">Working with Decision Rules (command line)</a></p>         </td>
      </tr>
      <tr>
         <td><p><span id="peldsp_display_decision_rule"></span>peldsp display_decisionrule</p>         </td>
         <td><p>display Decision Rule parameters</p>         </td>
      </tr>
      <tr>
         <td><p><span id="peldsp_select_ruletable"></span>peldsp select_ruletable</p>         </td>
         <td><p>display a list of Rule Tables</p>         </td>
         <td><p><a href="../../../managing_events_start_here/working_with_decision_rules_cli/working_with_rule_tables_cli">Working with Rule Tables (command line)</a></p>         </td>
      </tr>
      <tr>
         <td><p><span id="peldsp_display_ruletable"></span>peldsp display_ruletable</p>         </td>
         <td><p>display Rule Table parameters</p>         </td>
      </tr>
      <tr>
         <td><p><span id="peldsp_status_swoutputsession"></span>peldsp status_swoutputsession</p>         </td>
         <td><p>display the status of a SWIFTNet output session</p>         </td>
         <td><p><a href="../../../connectors_about/swiftnet_about/swiftnet_input_channels/swiftnet_output_channels">SWIFTNet queues and output channels</a></p>         </td>
      </tr>
   </tbody>
</table>

<span id="pelinst"></span>

## pelinst

### Purpose

Use the <span class="code" style="font-weight: bold;">pelinst</span> command to install or remove a Windows service.

### Syntax

**pelinst** \[parameters\]

#### To install a Windows service:

`pelinst <service name> <base directory> <account> <password> <description>`

#### To remove a Windows service:

`pelinst <service name> REMOVE`

### Subcommands

The <span class="code" style="font-weight: bold;">pelinst</span> command has no subcommands.

<span id="pelexport"></span>

## pelexport

### Purpose

Use the <span class="code" style="font-weight: bold;">pelexport</span> command to export a configuration <span class="code">.dat file, </span>to be reimported later using the <span class="code" style="font-weight: bold;">pelimport</span> command. This is relevant in the context of a migration, from 32-bit AIX to 64-bit AIX for example.

### Syntax

**pelexport** \[parameters\]

#### To export a **.dat** file

pelimport -infile &lt;nameOfFileToExport> -io &lt;prefixOfConfigurationFile>

The default value of <span class="code">&lt;prefixOfConfigurationFile></span> is <span class="code">xfer</span>.

**Example**: this imports the exported file `exportedxferbfile.dat `into `xferb.dat:`

`pelimport -infile xferbaix32.dat -io xferb`

### Subcommands

The <span class="code" style="font-weight: bold;">pelexport</span> command has no subcommands.

<span id="pelimport"></span>

## pelimport

### Purpose

Use the <span class="code" style="font-weight: bold;">pelimport</span> command to import a configuration <span class="code">.dat </span>into a configuration, from a file previously exported with the <span class="code" style="font-weight: bold;">pelexport</span> command . This is relevant in the context of a migration, from 32-bit AIX to 64-bit AIX for example.

### Syntax

**pelimport** \[parameters\]

#### To import a **.dat** file

`pelimport -infile <nameOfFileToImport> -io <prefixOfConfigurationFile>`

The default value of <span class="code">&lt;prefixOfConfigurationFile></span> is <span class="code">xfer</span>.

Example: this imports the exported file `exportedxferbfile.dat `into `xferb.dat:`

`pelimport -infile exportedxferbfile.dat -io xferb`

### Subcommands

The <span class="code" style="font-weight: bold;">pelimport</span> command has no subcommands.

<span id="pelmig"></span>

## pelmig

### Purpose

Use the [<span class="code" style="font-weight: bold;">pelmig</span>](../../../starting_and_stopping_server/migrating_mailbox#pelmig) command to upgrade the Mailbox file between different versions of Gateway, for example, when upgrading from the previous version of Gateway to the current version.

### Syntax

**pelmig** \[parameters\]

### Subcommands

The <span class="code" style="font-weight: bold;">pelmig</span> command has no subcommands.

<span id="pelmon"></span>

## pelmon

### Purpose

Use the <span class="code" style="font-weight: bold;">pelmon</span> command to:

-   Check Mailbox integrity
-   Restart Gateway
-   Initialize the Mailbox
-   Recover the Mailbox (if <span style="font-weight: bold;">[Mirror option](../../../configuration_start_here/config_gateway_paras#Mirror_option)</span> is activated)
-   Change the encryption passphrase file
-   Repair the Virtual File Directory
-   Reset the status prompted by the <a href="../../../starting_and_stopping_server#after_starting_gw_server" class="code">gatestatus</a> command

### Syntax

**pelmon \[subcommand\]** \[parameters\]

### Subcommands

This table lists the subcommands of the <span class="code" style="font-weight: bold;">pelmon</span> command.

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Subcommand         </th>
<th class="HeadE-Column1-Header1">Use to...         </th>
<th class="HeadD-Column1-Header1">Additional information         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><span id="pelmon_restart"></span><span class="code" style="font-weight: bold;">pelmon restart</span>         </td>
         <td>restart Gateway         </td>
         <td>Managing the Mailbox: <a href="../../../transfers_start_here/monitoring_transfers_start_here/viewing_and_managing_mailbox_contents_cli/managing_mailbox_cli#pelmon_restart" class="code">pelmon restart</a>         </td>
      </tr>
      <tr>
         <td><span id="pelmon_reset"></span><span class="code" style="font-weight: bold;">pelmon reset</span>         </td>
         <td>reset the status prompted by the <a href="../../../starting_and_stopping_server#after_starting_gw_server" class="code">gatestatus</a> command to the default value         </td>
         <td>Managing the Mailbox: <a href="../../../transfers_start_here/monitoring_transfers_start_here/viewing_and_managing_mailbox_contents_cli/managing_mailbox_cli#pelmon_reset" class="code">pelmon reset</a>         </td>
      </tr>
      <tr>
         <td><span id="pelmon_init_base"></span><span class="code" style="font-weight: bold;">pelmon init_base</span>         </td>
         <td>initialize Gateway Mailbox         </td>
         <td>Managing the Mailbox: <a href="../../../transfers_start_here/monitoring_transfers_start_here/viewing_and_managing_mailbox_contents_cli/managing_mailbox_cli#pelmon_init_base" class="code">pelmon init_base</a>         </td>
      </tr>
      <tr>
         <td><span id="pelmon_check_base"></span><span class="code" style="font-weight: bold;">pelmon check_base</span>         </td>
         <td>check Gateway Mailbox integrity         </td>
         <td>Managing the Mailbox: <a href="../../../transfers_start_here/monitoring_transfers_start_here/viewing_and_managing_mailbox_contents_cli/managing_mailbox_cli#pelmon_check_base" class="code">pelmon check_base</a>         </td>
      </tr>
      <tr>
         <td><span id="pelmon_recover_base"></span><span class="code" style="font-weight: bold;">pelmon recover_base</span>         </td>
         <td>recover Gateway Mailbox         </td>
         <td>Managing the Mailbox: <a href="../../../transfers_start_here/monitoring_transfers_start_here/viewing_and_managing_mailbox_contents_cli/managing_mailbox_cli#pelmon_recover_base" class="code">pelmon recover_base</a>         </td>
      </tr>
      <tr>
         <td><span id="pelmon_rebuild_vfd"></span><span class="code" style="font-weight: bold;">pelmon rebuild_vfd</span>         </td>
         <td>repair the Virtual File Directory         </td>
         <td>Managing the Mailbox: <a href="../../../transfers_start_here/monitoring_transfers_start_here/viewing_and_managing_mailbox_contents_cli/managing_mailbox_cli#pelmon_rebuild_vfd" class="code">pelmon rebuild_vfd</a>         </td>
      </tr>
      <tr>
         <td><span id="pelmon_change_pass_phrase"></span><span class="code" style="font-weight: bold;">pelmon change_pass_phrase</span>         </td>
         <td>change the encryption passphrase file         </td>
         <td>Managing the Mailbox: <a href="../../../transfers_start_here/monitoring_transfers_start_here/viewing_and_managing_mailbox_contents_cli/managing_mailbox_cli#pelmon_change_pass_phrase" class="code">pelmon change_pass_phrase</a>         </td>
      </tr>
   </tbody>
</table>

#### Deprecated subcommands

The following <span class="code" style="font-weight: bold;">pelmon</span> subcommands are now deprecated. You should not use these commands with this version of Gateway.

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Subcommand         </th>
<th class="HeadE-Column1-Header1">Previously used to...         </th>
<th class="HeadD-Column1-Header1">Command replaced by...         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><span class="code" style="font-weight: bold;">pelmon start</span>         </td>
         <td>start Gateway         </td>
         <td>the <span style="font-weight: bold;"><a href="../../../starting_and_stopping_server#starting_and_stopping_gw_server" class="code">gatestart</a></span> command         </td>
      </tr>
      <tr>
         <td><span class="code" style="font-weight: bold;">pelmon stop</span>         </td>
         <td>stop Gateway         </td>
         <td>the <span style="font-weight: bold;"><a href="../../../starting_and_stopping_server#starting_and_stopping_gw_server" class="code">gatestop</a></span> command         </td>
      </tr>
      <tr>
         <td><span class="code" style="font-weight: bold;">pelmon status</span>         </td>
         <td>test Gateway status         </td>
         <td>the <span style="font-weight: bold;"><a href="../../../starting_and_stopping_server#after_starting_gw_server" class="code">gatestatus</a></span> command         </td>
      </tr>
   </tbody>
</table>

<span id="pelpur"></span>

## pelpur

### Purpose

Use the <a href="../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_cli#pelpur" class="code">pelpur</a> command to purge the Mailbox of all Transfer Requests that match the specified criteria. The purged Transfers are stored in an archive file (unless you set the optional parameter <span class="code">-no\_arc</span>).

You can also use the <span class="code">pelpur</span> command to purge the transfer entries that match the specified criteria from the HA database used by SWIFTNet High Availability. To purge a transfer, the SWIFTNet High Availability feature has to be activated and connectivity with the HA database must be functional.

### Syntax

**pelpur** \[subcommand\]\[parameters\]

**pelpur** \[parameters\]

### Subcommands

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Subcommand         </th>
<th class="HeadE-Column1-Header1">Use to...         </th>
<th class="HeadD-Column1-Header1">Additional information         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><span class="code">pelpur xferPurge</span>         </td>
         <td>Purge the mailbox of all Transfer Requests that match the specified criteria.
This subcommand has the same effect as only running <span class="code">pelpur [parameters]</span>.         </td>
         <td>Works with transfers (command line) – table with <span class="code">pelpur xferPurge</span>         </td>
      </tr>
      <tr>
         <td><span class="code">pelpur clean_swha_db</span>         </td>
         <td>Purge the transfers from the HA database (used by SWIFTNet High Availability) that match the specified criteria.         </td>
         <td>Works with transfers (command line) – table with <span class="code">pelpur clean_swha_db</span>         </td>
      </tr>
   </tbody>
</table>

> **Note:**
>
> pelpur \[parameters\] is similar to pelpur xferPurge \[parameters\]. Both formats can be used.

<span id="peltrans"></span>

## peltrans

### Purpose

Use the <a href="../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_cli#peltrans" class="code">peltrans</a> command to submit a Transfer Request, a message Request, or a Diffusion List Request.

The request is a Diffusion List Request if the<span class="code"> dest\_alias</span> parameter is a Diffusion List.

### Syntax

**peltrans** \[parameters\]

### Subcommands

The peltrans command has no subcommands.

<span id="secadm"></span>

## secadm

### Purpose

Use the <span class="code" style="font-weight: bold;">secadm</span> command to manage Gateway security elements.

### Syntax

**secadm** \[subcommand\] \[parameters\]

### Subcommands

This table lists the subcommands of the <span class="code" style="font-weight: bold;">secadm</span> command.

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Subcommand         </th>
<th class="HeadE-Column1-Header1">Use to...         </th>
<th class="HeadD-Column1-Header1">Additional information         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><span id="secadm_import_cert"></span>secadm import_cert</p>         </td>
         <td><p>import a certificate from a file into the local database</p>         </td>
         <td><p>See the <em>Security Guide &gt; <a href="/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/Managing_Security/Certificates_and_keys/managing_certificates_CLI.htm">Managing certificates (command line)</a></em> for further information.</p>         </td>
      </tr>
      <tr>
         <td><p><span id="secadm_export_cert"></span>secadm export_cert</p>         </td>
         <td><p>export a certificate to a remote database</p>         </td>
      </tr>
      <tr>
         <td><p><span id="secadm_update_cert"></span>secadm update_cert</p>         </td>
         <td><p>modify a certificate</p>         </td>
      </tr>
      <tr>
         <td><p><span id="secadm_delete_cert"></span>secadm delete_cert</p>         </td>
         <td><p>delete a certificate from the database</p>         </td>
      </tr>
      <tr>
         <td><p><span id="secadm_import_key"></span>secadm import_key</p>         </td>
         <td><p>import a key into the local database</p>         </td>
         <td><p>See the <em>Security Guide &gt; <a href="/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/Managing_Security/Certificates_and_keys/managing_keys_CLI.htm">Managing keys (command line)</a></em> for further information.</p>         </td>
      </tr>
      <tr>
         <td><p><span id="secadm_update_key"></span>secadm update_key</p>         </td>
         <td><p>modify a key</p>         </td>
      </tr>
      <tr>
         <td><p><span id="secadm_delete_key"></span>secadm delete_key</p>         </td>
         <td><p>delete a key from the database</p>         </td>
      </tr>
      <tr>
         <td><p><span id="secadm_import_sprof"></span>secadm import sprof</p>         </td>
         <td><p>import a TLS Profile from a file into the local database</p>         </td>
         <td><p>See the <em>Security Guide &gt; <a href="/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/Managing_Security/TLS/managing_tls_security_profiles_CLI.htm">Managing TLS Security profiles (command line)</a></em> for further information.</p>         </td>
      </tr>
      <tr>
         <td><p><span id="secadm_delete_sprof"></span>secadm delete_sprof</p>         </td>
         <td><p>delete a TLS Security Profile from the database</p>         </td>
      </tr>
      <tr>
         <td><p><span id="secadm_import_sshprof"></span>secadm import_sshprof</p>         </td>
         <td><p>import an SSH Security Profile from a text file into the local database</p>         </td>
         <td><p>See the <em>Security Guide &gt; <a href="/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/Managing_Security/SSH/managing_ssh_security_profiles_CLI.htm">Managing SSH Security profiles (command line)</a></em> for further information.</p>         </td>
      </tr>
      <tr>
         <td><p><span id="secadm_delete_sshprof"></span>secadm delete_sshprof</p>         </td>
         <td><p>delete an SSH Security Profile from the database</p>         </td>
      </tr>
      <tr>
         <td><p><span id="secadm_create_netprof"></span>secadm create_netprof</p>         </td>
         <td><p>create a Network Profile</p>         </td>
         <td><p>See the <em>Security Guide &gt; <a href="/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/Managing_Security/Network_Profiles/managing_network_profiles_CLI.htm">Managing Network Profiles (command line)</a></em> for further information.</p>         </td>
      </tr>
      <tr>
         <td><p><span id="secadm_update_netprof"></span>secadm update_netprof</p>         </td>
         <td><p>modify a Network Profile</p>         </td>
      </tr>
      <tr>
         <td><p><span id="secadm_delete_netprof"></span>secadm delete_netprof</p>         </td>
         <td><p>delete a Network Profile</p>         </td>
      </tr>
   </tbody>
</table>

<span id="secdsp"></span>

## secdsp

### Purpose

Use the <span class="code" style="font-weight: bold;">secdsp</span> command to select security elements and to view their parameters.

### Syntax

secdsp \[<span style="font-weight: normal;">subcommand</span>\] \[<span style="font-weight: normal;">parameters</span>\]

### Subcommands

This table lists the subcommands of the <span class="code" style="font-weight: bold;">secdsp</span> command.

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Subcommand         </th>
<th class="HeadE-Column1-Header1">Use to...         </th>
<th class="HeadD-Column1-Header1">Additional information         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><span id="secdsp display cert"></span>secdsp display_cert</p>         </td>
         <td><p>display security certificate attributes</p>         </td>
         <td><p>See the <em>Security Guide &gt; <a href="/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/Managing_Security/Certificates_and_keys/managing_certificates_CLI.htm">Managing certificates (command line)</a></em> for further information.</p>         </td>
      </tr>
      <tr>
         <td><p><span id="secdsp select cert"></span>secdsp select_cert</p>         </td>
         <td><p>display a selected list of certificates</p>         </td>
      </tr>
      <tr>
         <td><p><span id="secdsp status cert"></span>secdsp status_cert</p>         </td>
         <td><p>display the state of a certificate</p>         </td>
      </tr>
      <tr>
         <td><p><span id="secdsp_display_sprof"></span>secdsp display_sprof</p>         </td>
         <td><p>display security profile attributes</p>         </td>
         <td><p>See the <em>Security Guide &gt;</em> <a href="/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/Managing_Security/TLS/managing_tls_security_profiles_CLI.htm">Managing TLS Security Profiles (command line)</a> for further information.</p>         </td>
      </tr>
      <tr>
         <td><p><span id="secdsp_select_sprof"></span>secdsp select_sprof</p>         </td>
         <td><p>display a selected list of security profile attributes</p>         </td>
      </tr>
      <tr>
         <td><p><span id="secdsp status sprof"></span>secdsp status_sprof</p>         </td>
         <td><p>display the state of a security profile</p>         </td>
      </tr>
      <tr>
         <td><p><span id="secdsp display sshprof"></span>secdsp display_sshprof</p>         </td>
         <td><p>display SSH profile attributes</p>         </td>
         <td><p>See the Security Guide &gt; <a href="/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/Managing_Security/SSH/managing_ssh_security_profiles_CLI.htm">Managing SSH Security Profiles (command line)</a> for further information.</p>         </td>
      </tr>
      <tr>
         <td><p><span id="secdsp select sshprof"></span>secdsp select_sshprof</p>         </td>
         <td><p>display a selected list of SSH profile attributes</p>         </td>
      </tr>
      <tr>
         <td><p><span id="secdsp status sshprof"></span>secdsp status_sshprof</p>         </td>
         <td><p>display the status if an SSH profile</p>         </td>
      </tr>
      <tr>
         <td><p><span id="secdsp display netprof"></span>secdsp display_netprof</p>         </td>
         <td><p>display Network Profile attributes</p>         </td>
         <td><p>See the <em>Security Guide &gt; <a href="/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/Managing_Security/Network_Profiles/managing_network_profiles_CLI.htm"><em>Managing Network Profiles (command line)</em></a></em> for further information.</p>         </td>
      </tr>
      <tr>
         <td><p><span id="secdsp select netprof"></span>secdsp select_netprof</p>         </td>
         <td><p>display a selected set of Network Profile attributes</p>         </td>
      </tr>
      <tr>
         <td><p><span id="secdsp status netprof"></span>secdsp status_netprof</p>         </td>
         <td><p>display the status of a Network Profile</p>         </td>
      </tr>
      <tr>
         <td><p><span id="secdsp display key"></span>secdsp display_key</p>         </td>
         <td><p>display security key attributes</p>         </td>
         <td><p>See the <em>Security Guide &gt; <a href="/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/Managing_Security/Certificates_and_keys/managing_keys_CLI.htm">Managing keys (command line)</a></em> for further information.</p>         </td>
      </tr>
      <tr>
         <td><p><span id="secdsp select key"></span>secdsp select_key</p>         </td>
         <td><p>display a selected list of security key attributes</p>         </td>
      </tr>
      <tr>
         <td><p><span id="secdsp status key"></span>secdsp status_key</p>         </td>
         <td><p>display the status of a security key</p>         </td>
      </tr>
   </tbody>
</table>

<span id="vfdadm"></span>

## vfdadm

### Purpose

Use the <span class="code" style="font-weight: bold;">vfdadm</span> command to manage the Virtual File Directory.

### Syntax

vfdadm \[<span style="font-weight: normal;">subcommand</span>\] \[<span style="font-weight: normal;">parameters</span>\]

### Subcommands

This table lists the subcommands of the <span class="code" style="font-weight: bold;">vfdadm</span> command.

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Subcommand         </th>
<th class="HeadE-Column1-Header1">Use to...         </th>
<th class="HeadD-Column1-Header1">Additional information         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><span id="vfdadm create dir"></span>vfdadm create_dir</p>         </td>
         <td><p>Create a new Virtual File Directory and set its attributes</p>         </td>
         <td><p><a href="../../../transfers_start_here/virtual_file_directory_start_here/working_with_vfds_cli">Working with VFDs (command line)</a></p>         </td>
      </tr>
      <tr>
         <td><p><span id="vfdadm_update_dir"></span>vfdadm update_dir</p>         </td>
         <td><p>Update the attributes (including the optional mount point attributes) of an existing Virtual File Directory</p>         </td>
      </tr>
      <tr>
         <td><p><span id="vfdadm_move_dir"></span>vfdadm move_dir</p>         </td>
         <td><ul>
<li>Move a VFD directory (or mounted directory), from its current location in the VFD to a new location</li>
<li>Rename a VFD directory</li>
<li>Move and rename a VFD directory</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span id="vfdadm_delete_dir"></span>vfdadm delete_dir</p>         </td>
         <td><p>Delete a Virtual File Directory</p>         </td>
      </tr>
   </tbody>
</table>

<span id="vfddsp"></span>

## vfddsp

### Purpose

Use the <span class="code" style="font-weight: bold;">vfddsp</span> command to select and display Virtual File Directory attributes.

### Syntax

vfddsp \[<span style="font-weight: normal;">subcommand</span>\] \[<span style="font-weight: normal;">parameters</span>\]

### Subcommands

This table lists the subcommands of the <span class="code" style="font-weight: bold;">vfddsp</span> command.

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Subcommand         </th>
<th class="HeadE-Column1-Header1">Use to...         </th>
<th class="HeadD-Column1-Header1">Additional information         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><span id="vfddsp display dir"></span>vfddsp display_dir</p>         </td>
         <td><p>display the details, or attributes, of a VFD logical directory</p>         </td>
         <td><p><a href="../../../transfers_start_here/virtual_file_directory_start_here/working_with_vfds_cli">Working with VFDs (command line)</a></p>         </td>
      </tr>
      <tr>
         <td><p><span id="vfddsp display file"></span>vfddsp display_file</p>         </td>
         <td><p>display the details of a VFD logical file identified by its VFD parent directory absolute path (or its alias) and its name</p>         </td>
      </tr>
      <tr>
         <td><p><span id="vfddsp_list_dir"></span>vfddsp list_dir</p>         </td>
         <td><p>list the contents of a specified Virtual File Directory</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Index of online commands](../online_commands_index)

[Index of tasks](../online_commands_task_index)

[About online commands](../)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
