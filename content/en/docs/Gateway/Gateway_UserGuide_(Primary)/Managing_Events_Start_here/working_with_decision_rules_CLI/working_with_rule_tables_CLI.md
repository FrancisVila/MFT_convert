{
    "title": "Working with Rule Tables (command line)",
    "linkTitle": "Working with Rule Tables",
    "weight": "200"
}{{< Gateway/componentlongname  >}}: Managing Events

`peladm create_ruletable`

`peladm update_ruletable`

`peladm delete_ruletable`

`peldsp display_ruletable`

`peldsp select_ruletable`

<span id="peladm_create_ruletable"></span>

## Creating a Rule Table: peladm create\_ruletable

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><code>peladm create_ruletable</code> [see parameters below]</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to create a new Rule Table.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>Mandatory parameter</p>
<p><code>-name (-n)</code></p>         </td>
         <td><p>Enter a unique name for the Rule Table you are creating.</p>         </td>
      </tr>
      <tr>
         <td><p>-status (-stat)</p>         </td>
         <td><p>Enter one of the following states:</p>
<ul>
<li>ACTIVE</li>
<li>INACTIVE</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-type_of_rules_table (-type)</p>         </td>
         <td><p>Enter one of the following Rule Table types:</p>
<ul>
<li>XFER_CHANGE_STATE</li>
<li>TEMPORAL</li>
<li>FILE_STORING</li>
<li>XMS</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-default_execution_type (-det)</p>         </td>
         <td><p>The type of process to be triggered if no process is triggered by an associated Decision Rule. Enter one of the following values:</p>
<ul>
<li><strong>MODEL</strong> = the default execution is defined by a Model. Specify the Model in the <code>default_model (-dm)</code> parameter below.</li>
<li><strong>AMTRIX</strong> = redirect the Transfer to AMTrix for processing</li>
<li><strong>PERL</strong></li>
<li><strong>COMMAND</strong> = the default execution is a command line or script specified in the <code>default_command_line</code> parameter. Refer to <a href="../decision_rules_executing_scripts">Executing scripts as command lines from Decision Rules</a>.</li>
<li><strong>TO_XMS</strong></li>
<li><strong>NONE</strong> (default)</li>
<li><strong>LOG_CLEANING</strong></li>
<li><strong>MAILBOX_CLEANING</strong></li>
<li><strong>STAT_CLEANING</strong></li>
<li><strong>XIB</strong> = redirect the Transfer to Integrator for processing. The payload file for a Transfer which was routed to Integrator is not deleted by the purge operation. For more information, refer to <a href="../../../connectors_about/integrator_about/integrator_connector#Purging">Purging for transfers routed from Gateway to Integrator</a>.</li>
<li><strong>DEFAULT</strong> = route the transfer using a Model inside an Application. This option is only available via online commands. The option exists for reasons of compatibility with earlier product versions.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-link_transfers (-lt)</p>         </td>
         <td><p>Use this parameter if you enter the value <em>MODEL</em> for the <code>default_execution_type</code> parameter.</p>
<p>Enter one of the following values:</p>
<ul>
<li><strong>Y</strong> (default) = Yes.<br />
Create a logical link between the incoming and the outgoing Transfers.</li>
<li><span style="font-weight: bold;">N</span> = No.<br />
No link between the incoming and the outgoing Transfers</li>
</ul>
<p>When you enter <span style="font-weight: bold;">Y:</span></p>
<ul>
<li>The input Transfer Request parameter <span class="code">route_to_xfer</span> is set to the output Transfer identifier</li>
<li>The output Transfer Request parameter <span class="code">route_from_xfer</span> is set to the input Transfer identifier</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-default_model (-dm)</p>         </td>
         <td><p>If you entered the value <span style="font-style: italic;">MODEL</span> for the <span class="code">default_execution_type</span> parameter, enter a Model name.</p>         </td>
      </tr>
      <tr>
         <td><p>-default_purge_model (-dpm)</p>         </td>
         <td><p>If you entered the value <span style="font-style: italic;">MAILBOX_CLEANING</span> for the <span class="code">default_execution_type</span> parameter, enter the name of an existing Purge Model to define the purge operation on the Mailbox.</p>         </td>
      </tr>
      <tr>
         <td><p>-default_perl_script (-dps)</p>         </td>
         <td><p>If you entered the value <span style="font-style: italic;">PERL</span> for the <span class="code">default_execution_type</span> parameter, enter the Perl script name and access path.</p>         </td>
      </tr>
      <tr>
         <td><p>-default_command_line (-dcl)</p>         </td>
         <td><p>If you entered the value <span style="font-style: italic;">COMMAND</span> for the <span class="code">default_execution_type</span> parameter, enter the execution command line, or alternatively, enter the path and file name to a script. Refer to <a href="../decision_rules_executing_scripts">Executing scripts as command lines from Decision Rules</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>-add_decisionrule (-a)</p>         </td>
         <td><p>Add one or more Decision Rules.</p>         </td>
      </tr>
      <tr>
         <td><p>-restrict_processing (-rp)</p>         </td>
         <td><p>Select whether or not to activate restriction criteria parameters for Decision Rules processing.</p>
<p>Enter one of the following values:</p>
<ul>
<li><span style="font-weight: bold;">Y</span> = Yes</li>
<li><span style="font-weight: bold;">N</span> (default) = No</li>
</ul>
<p>If you enter the <strong>Y</strong> (yes) value, you must also enter at least one value for one of the following parameters:</p>
<ul>
<li>restrict_processing_on_state</li>
<li>restrict_processing_on_direction</li>
<li>restrict_processing_on_type</li>
<li>restrict_processing_on_mode</li>
<li>restrict_processing_on_protocol</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-restrict_processing_on_state (-rpos)</p>         </td>
         <td><p>You can enter one or more of the following values if you entered the value <strong>Y</strong> (yes) for the <span class="code">restrict_processing (-rp)</span> parameter:</p>
<ul>
<li>ENDED</li>
<li>CANCELED</li>
<li>ACKNOWLEDGED</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-restrict_processing_on_direction (-rpod)</p>         </td>
         <td><p>You can enter one or more of the following values if you entered the value <strong>Y</strong> (yes) for the <span class="code">restrict_processing (-rp)</span> parameter:</p>
<ul>
<li>IN</li>
<li>OUT</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-restrict_processing_on_type (-rpot)</p>         </td>
         <td><p>You can enter one or more of the following values if you entered the value <strong>Y</strong> (yes) for the <span class="code">restrict_processing (-rp)</span> parameter:</p>
<ul>
<li>TRANS</li>
<li>LOTS</li>
<li>POLL</li>
<li>LIST</li>
<li>EERP</li>
<li>SELECT</li>
<li>MSG</li>
<li>DIR</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-restrict_processing_on_mode (-rpom)</p>         </td>
         <td><p>You can enter one or more of the following values if you entered the value <strong>Y</strong> (yes) for the <span class="code">restrict_processing (-rp)</span> parameter:</p>
<ul>
<li>INITIATOR</li>
<li>RESPONDER</li>
</ul>         </td>
      </tr>
      <tr>
         <td><span class="code">-restrict_processing_on_protocol (-rpop)</span>         </td>
         <td><p>You can enter one or more of the following values if you entered the value Y (yes) for the <span class="code">restrict_processing (-rp)</span> parameter:</p>
<ul>
<li>PEL</li>
<li>ODETTE</li>
<li>PHSE</li>
<li>PHSD</li>
<li>FTP</li>
<li>HTTP</li>
<li>FTP_HTTP</li>
<li>POP3</li>
<li>SFTP</li>
<li>SMTP</li>
<li>AS2</li>
<li>AS3</li>
<li>AS1_POP3</li>
<li>AS1_SMTP</li>
<li>RN_HTTP</li>
<li>RN_POP3</li>
<li>RN_SMTP</li>
<li>SWIFTNET</li>
<li>JMS</li>
<li>X420</li>
<li>X400</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-log_level (-ll)</p>         </td>
         <td><p>To define the logging level, enter one of the following values:</p>
<ul>
<li><span style="font-weight: bold;">DEFAULT_LEVEL</span> (default)</li>
<li><span style="font-weight: bold;">0</span> = none</li>
<li><span style="font-weight: bold;">1</span> = short</li>
<li><span style="font-weight: bold;">2</span> = full</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-is_rules_table_exclusive (-excl)</p>         </td>
         <td><p>By default, Gateway analyzes the Decision Rules in a Rule Table in their listed order, stopping at the first Rule that matches a complete set of conditions.</p>
<p>Enter one of the following values:</p>
<ul>
<li><span style="font-weight: bold;">Y</span> = (default)</li>
<li><span style="font-weight: bold;">N</span> = No - enables Gateway to continue analyzing the table list after processing a matching Rule</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-is_user_exits_activated (-exit)</p>         </td>
         <td><p>Rule Tables are inherently associated with exit processes that are automatically called during Rule processing.</p>
<p>Enter one of the following values:</p>
<ul>
<li><span style="font-weight: bold;">Y</span> (default) = Yes - enable all inherent exits</li>
<li><span style="font-weight: bold;">N</span> = No - disable all inherent exits</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-temporal_event_model (-tem)</p>         </td>
         <td><p>If you are creating a Scheduling-type Rule Table (<span class="code">-type = TEMPORAL</span>), and you set the <code>default_execution_type</code> to <span style="font-style: italic;">MODEL</span>, use this parameter to specify the event Model.</p>
<p><span style="font-weight: bold;">Note:</span> This parameter requires a <a href="../scheduling_event_model_command_syntax">specific syntax</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>-execution_delay (-delay)</p>         </td>
         <td><p>Use this parameter if you are creating a Scheduling-type Rule Table.</p>
<p>If your Gateway server is out of service during a period when events are scheduled, this parameter enables you to specify the handling of the un-triggered events on server restoration.</p>
<ul>
<li><span style="font-weight: bold;">UNTIL_NEXT</span> (default) = when the Gateway server restarts, it executes the next scheduled action at the normal scheduled time, ignoring programmed actions that were not executed when the server was out of service.</li>
<li><span style="font-weight: bold;">INFINITE</span> = when the Gateway server restarts, it executes all actions that were scheduled but not executed due to server incapacity.</li>
<li><span style="font-weight: bold;">1 ... 2147483647</span> = enter a value to specify the maximum time within which a scheduled action can be executed on server restart. If this delay is exceeded, the programmed action is abandoned.<br />
<span style="font-weight: bold;">Example:</span> You schedule an action to be triggered at 12:30 p.m. Friday and enter a <span style="font-weight: bold;">Special value</span> delay of one hour. If the server is out of service from 12:00 p.m. to 1:00 p.m. Friday, the action is triggered on server restart because restart occurs within the specified delay. However, if the server is out of service from 12:00 p.m. to 2:00 p.m. Friday, the action is abandoned because the allowed delay value is exceeded.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-watched_directory (-watchdir)</p>         </td>
         <td><p>Use this parameter if you are creating a Directory Scanning type Rule Table.</p>
<p>Enter a string which defines the watched directory.</p>         </td>
      </tr>
      <tr>
         <td><p>-watch_period (-wp)</p>         </td>
         <td><p>Use this parameter if you are creating a Directory Scanning type Rule Table.</p>
<p>Enter a positive integer which defines the watch period {1 ... 2147483647 } in seconds.</p>
<p>Default = 10.</p>         </td>
      </tr>
      <tr>
         <td><p>-work_directory (-workdir)</p>         </td>
         <td><p>Use this parameter if you are creating a Directory Scanning type Rule Table.</p>
<p>Enter a string which defines the work directory.</p>         </td>
      </tr>
      <tr>
         <td><p>-is_optimized_cleaning (-optclean)</p>         </td>
         <td><p>Use this parameter if you are creating a Directory Scanning type Rule Table.</p>
<ul>
<li><span style="font-weight: bold;">Y</span> (default) = Yes - optimized cleaning is activated</li>
<li><span style="font-weight: bold;">N</span> = No - optimized cleaning is not activated</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-prop_list_name (-pln)</p>         </td>
         <td><p>Only for JMS or Axway Messaging</p>
<p>Enter a Property List name.</p>         </td>
      </tr>
      <tr>
         <td><p>-xms_connector_name (-xcn)</p>         </td>
         <td><p>Use this parameter if you are creating an XMS-type Rule Table.</p>
<p>Enter an Axway Messaging connector name.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Usage rules</strong></p>         </td>
         <td><p><span style="font-weight: bold;">Execution type parameters:</span></p>
<p>If you set <span class="code">default_execution_type</span> to:</p>
<ul>
<li><em>COMMAND</em>, then enter a value for the <span class="code">default_command_line</span> parameter.</li>
<li><em>MODEL</em>, then enter a value for the <span class="code">default_model</span> parameter.</li>
<li><em>PERL</em>, then enter a value for the <span class="code">default_perl_script</span> parameter.</li>
</ul>
<p>Restricted processing parameters</p>
<p>To limit XFER_CHANGE_STATE Decision Rule processing to a limited set of Transfers, you must set the parameter <span class="code">restrict_processing</span> to <span style="font-weight: bold;">Y</span> (yes). Gateway then restricts processing based one or more conditions that you set for the following parameters:</p>
<ul>
<li><span class="code">restrict_processing_on_direction</span>: restrict processing to either <span style="font-weight: bold;">Input</span> or <span style="font-weight: bold;">Output</span> Transfers</li>
<li><span class="code">restrict_processing_on_mode</span>: restrict processing to either <span style="font-weight: bold;">Initiator</span> or <span style="font-weight: bold;">Responder</span> mode Transfers</li>
<li><span class="code">restrict_processing_on_state</span>: restrict processing to either <span style="font-weight: bold;">Ended</span>, <span style="font-weight: bold;">Canceled</span> or <span style="font-weight: bold;">Acknowledged</span> Transfers</li>
<li><span class="code">restrict_processing_on_type</span>: restrict processing to Transfers of the specified type (TRANS, POLL, LOT,...)</li>
<li><p><span class="code">restrict_processing_on_protocol</span>: restrict processing to Transfers of the specified protocol (PEL, ODETTE, PHSE,…)</p></li>
</ul>
<p>If multiple values are specified for a parameter, these must be separated by a comma with no extra spaces.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="peladm_update_ruletable"></span>

## Modifying a Rule Table: peladm update\_ruletable

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code" style="font-weight: bold;">peladm update_ruletable</span> [see parameters below]</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to set or modify the parameters of an existing Rule Table.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>Mandatory parameter</p>
<p><span class="code">-name (-n)</span></p>         </td>
         <td><p>Enter the name of the Rule Table you want to update.</p>         </td>
      </tr>
      <tr>
         <td><p>-status (-stat)</p>         </td>
         <td><p>Enter one of the following states:</p>
<ul>
<li>ACTIVE<span style="font-weight: normal;"> (default)</span></li>
<li>INACTIVE</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-type_of_rules_table (-type)</p>         </td>
         <td><p>Enter one of the following Rule Table types:</p>
<ul>
<li>XFER_CHANGE_STATE<span style="font-weight: normal;"> (default)</span></li>
<li>TEMPORAL</li>
<li>FILE_STORING</li>
<li>XMS</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-default_execution_type (-det)</p>         </td>
         <td><p>Enter the type of process to be triggered if no process is triggered by an associated Decision Rule. Enter one of the following values:</p>
<ul>
<li><strong>MODEL</strong> = the default execution is defined by a Model. Specify the Model in the <span class="code">default_model (-dm)</span> parameter below.</li>
<li><strong>AMTRIX</strong> = redirect the Transfer to AMTrix for processing</li>
<li><strong>PERL</strong></li>
<li><strong>COMMAND</strong> = the default execution is a command line or script specified in the <span class="code">default_command_line</span> parameter. Refer to <a href="../decision_rules_executing_scripts">Executing scripts as command lines from Decision Rules</a>.</li>
<li><strong>TO_XMS</strong></li>
<li><strong>NONE</strong> (default)</li>
<li><strong>LOG_CLEANING</strong></li>
<li><strong>MAILBOX_CLEANING</strong></li>
<li><strong>STAT_CLEANING</strong></li>
<li><strong>XIB</strong> = redirect the Transfer to Integrator for processing. The payload file for a Transfer which was routed to Integrator is not deleted by the purge operation. For more information, refer to <a href="../../../connectors_about/integrator_about/integrator_connector#Purging">Purging for transfers routed from Gateway to Integrator</a>.</li>
<li><strong>DEFAULT</strong> = route the transfer using a Model inside an Application. This option is only available via online commands. The option exists for reasons of compatibility with earlier product versions.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-link_transfers (-lt)</p>         </td>
         <td><p>Use this parameter if you enter the value <span style="font-style: italic;">MODEL</span> for the <span class="code">default_execution_type</span> parameter.</p>
<p>Enter one of the following values:</p>
<ul>
<li><span style="font-weight: bold;">Y</span> (default) = Yes - create a logical link between the incoming and the outgoing Transfers</li>
<li><span style="font-weight: bold;">N</span> = No - no link between the incoming and the outgoing Transfers</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-default_model (-dm)</p>         </td>
         <td><p>If you entered the value <span style="font-style: italic;">MODEL</span> for the <span class="code">default_execution_type</span> parameter, enter a Model name.</p>         </td>
      </tr>
      <tr>
         <td><p>-default_perl_script (-dps)</p>         </td>
         <td><p>If you entered the value <span style="font-style: italic;">PERL</span> for the <span class="code">default_execution_type</span> parameter, enter the Perl script name and path.</p>         </td>
      </tr>
      <tr>
         <td><p>-default_command_line (-dcl)</p>         </td>
         <td><p>If you entered the value <span style="font-style: italic;">COMMAND</span> for the <span class="code">default_execution_type</span> parameter, enter the execution command line.</p>         </td>
      </tr>
      <tr>
         <td><p>-add_decisionrule (-a)</p>         </td>
         <td><p>Enter the name(s) of the Decision Rule(s) you want to add.</p>         </td>
      </tr>
      <tr>
         <td><p>-delete_decisionrule (-d)</p>         </td>
         <td><p>Enter the name(s) of the Decision Rule(s) you want to delete.</p>         </td>
      </tr>
      <tr>
         <td><p>-delete_all_decisionrules (-dad)</p>         </td>
         <td><p>Delete all Decision Rules.</p>
<p>Enter one of the following values:</p>
<ul>
<li><span style="font-weight: bold;">Y</span> = Yes</li>
<li><span style="font-weight: bold;">N</span> = No</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-move_up (-mu)</p>         </td>
         <td><p>Enter the name(s) of the Decision Rule(s) you want to move upwards in the evaluation order list.</p>         </td>
      </tr>
      <tr>
         <td><p>-move_down (-md)</p>         </td>
         <td><p>Enter the name(s) of the Decision Rule(s) you want to move downwards in the evaluation order list.</p>         </td>
      </tr>
      <tr>
         <td><p>-restrict_processing (-rp)</p>         </td>
         <td><p>Select whether or not to activate restriction criteria parameters for Decision Rules processing.</p>
<p>Enter one of the following values:</p>
<ul>
<li><span style="font-weight: bold;">Y</span> = Yes</li>
<li><span style="font-weight: bold;">N</span> (default) = No</li>
</ul>
<p>If you enter the <strong>Y</strong> (yes) value, you must also enter at least one value for one of the following parameters:</p>
<ul>
<li>restrict_processing_on_state</li>
<li>restrict_processing_on_direction</li>
<li>restrict_processing_on_type</li>
<li>restrict_processing_on_mode</li>
<li>restrict_processing_on_protocol</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-restrict_processing_on_state (-rpos)</p>         </td>
         <td><p>You can enter one or more or the following values if you entered the value <strong>Y</strong> (yes) for the <span class="code">restrict_processing (-rp)</span> parameter:</p>
<ul>
<li>ENDED</li>
<li>CANCELED</li>
<li>ACKNOWLEDGED</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-restrict_processing_on_direction (-rpod)</p>         </td>
         <td><p>You can enter one or more or the following values if you entered the value <strong>Y</strong> (yes) for the <span class="code">restrict_processing (-rp)</span> parameter:</p>
<ul>
<li>IN</li>
<li>OUT</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-restrict_processing_on_type (-rpot)</p>         </td>
         <td><p>You can enter one or more or the following values if you entered the value <strong>Y</strong> (yes) for the <span class="code">restrict_processing (-rp)</span> parameter:</p>
<ul>
<li>TRANS</li>
<li>LOTS</li>
<li>POLL</li>
<li>LIST</li>
<li>EERP</li>
<li>SELECT</li>
<li>MSG</li>
<li>DIR</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-restrict_processing_on_mode (-rpom)</p>         </td>
         <td><p>You can enter one or more or the following values if you entered the value <strong>Y</strong> (yes) for the <span class="code">restrict_processing (-rp)</span> parameter:</p>
<ul>
<li>INITIATOR</li>
<li>RESPONDER</li>
</ul>         </td>
      </tr>
      <tr>
         <td><span class="code">-restrict_processing_on_protocol (-rpop)</span>         </td>
         <td><p>You can enter one or more of the following values if you entered the value Y (yes) for the <span class="code">restrict_processing (-rp)</span> parameter:</p>
<ul>
<li>PEL</li>
<li>ODETTE</li>
<li>PHSE</li>
<li>PHSD</li>
<li>FTP</li>
<li>HTTP</li>
<li>FTP_HTTP</li>
<li>POP3</li>
<li>SFTP</li>
<li>SMTP</li>
<li>AS2</li>
<li>AS3</li>
<li>AS1_POP3</li>
<li>AS1_SMTP</li>
<li>RN_HTTP</li>
<li>RN_POP3</li>
<li>RN_SMTP</li>
<li>SWIFTNET</li>
<li>JMS</li>
<li>X420</li>
<li>X400</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-log_level (-ll)</p>         </td>
         <td><p>To define the logging level, enter one of the following values:</p>
<ul>
<li>DEFAULT_LEVEL<span style="font-weight: normal;"> (default)</span></li>
<li>0 ... 2</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-is_rules_table_exclusive (-excl)</p>         </td>
         <td><p>By default, Gateway analyzes the Decision Rules in a Rule Table in their listed order, stopping at the first Rule that matches a complete set of conditions.</p>
<p>Enter one of the following values:</p>
<ul>
<li><span style="font-weight: bold;">Y</span> = (default)</li>
<li><span style="font-weight: bold;">N</span> = No - enables Gateway to continue analyzing the table list after processing a matching Rule</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-is_user_exits_activated (-exit)</p>         </td>
         <td><p>Rule Tables are inherently associated with exit processes that are automatically called during Rule processing.</p>
<p>Enter one of the following values:</p>
<ul>
<li><span style="font-weight: bold;">Y</span> (default) = Yes - enable all inherent exits</li>
<li><span style="font-weight: bold;">N</span> = No - disable all inherent exits</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-temporal_event_model (-tem)</p>         </td>
         <td><p>If you are creating a Scheduling-type Rule Table (<span class="code">-type = TEMPORAL</span>), and you set the <code>default execution type</code> to <span style="font-style: italic;">MODEL</span>, use this parameter to specify the event Model.</p>
<p><span style="font-weight: bold;">Note:</span> This parameter requires a <a href="../scheduling_event_model_command_syntax">specific syntax</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>-execution_delay (-delay)</p>         </td>
         <td><p>Use this parameter if you are creating a Scheduling-type Rule Table.</p>
<p>If your Gateway server is out of service during a period when events are scheduled, this parameter enables you to specify the handling of the un-triggered events on server restoration.</p>
<ul>
<li><span style="font-weight: bold;">UNTIL_NEXT</span> (default) = when the Gateway server restarts, it executes the next scheduled action at the normal scheduled time, ignoring programmed actions that were not executed when the server was out of service.</li>
<li><span style="font-weight: bold;">INFINITE</span> = when the Gateway server restarts, it executes all actions that were scheduled but not executed due to server incapacity.</li>
<li><span style="font-weight: bold;">1 ... 2147483647</span> = enter a value to specify the maximum time within which a scheduled action can be executed on server restart. If this delay is exceeded, the programmed action is abandoned.<br />
<strong>Example:</strong> You schedule an action to be triggered at 12:30 p.m. on Friday and enter a <span style="font-weight: bold;">Special value</span> delay of one hour. If the server is out of service from 12:00 p.m. to 1:00 p.m. on Friday, the action is triggered on server restart because restart occurs within the specified delay.<br />
However, if the server is out of service from 12:00 p.m. to 2:00 p.m. on Friday, the action is abandoned because the allowed delay value is exceeded.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-watched_directory (-watchdir)</p>         </td>
         <td><p>Use this parameter if you are creating a Directory Scanning type Rule Table.</p>
<p>Enter a string which defines the watched directory.</p>         </td>
      </tr>
      <tr>
         <td><p>-watch_period (-wp)</p>         </td>
         <td><p>Use this parameter if you are creating a Directory Scanning type Rule Table.</p>
<p>Enter a positive integer which defines the watch period { 1 ... 2147483647 } in seconds.</p>
<p>Default = 10.</p>         </td>
      </tr>
      <tr>
         <td><p>-work_directory (-workdir)</p>         </td>
         <td><p>Use this parameter if you are creating a Directory Scanning type Rule Table.</p>
<p>Enter a string which defines the work directory.</p>         </td>
      </tr>
      <tr>
         <td><p>-is_optimized_cleaning (-optclean)</p>         </td>
         <td><p>Use this parameter if you are creating a Directory Scanning type Rule Table.</p>
<ul>
<li><span style="font-weight: bold;">Y</span> (default)= Yes - optimized cleaning is activated</li>
<li><span style="font-weight: bold;">N</span> = No - optimized cleaning is not activated</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-prop_list_name (-pln)</p>         </td>
         <td><p>Only for JMS or Axway Messaging</p>
<p>Enter a Property List name.</p>         </td>
      </tr>
      <tr>
         <td><p>-restrict_processing_on_mode (-rpom)</p>         </td>
         <td><p>Enter one of the following:</p>
<ul>
<li><strong>INITIATOR</strong></li>
<li><strong>RESPONDER</strong></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-xms_connector_name (-xcn)</p>         </td>
         <td><p>Use this parameter if you are creating an XMS-type Rule Table.</p>
<p>Enter an Axway Messaging connector name.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Usage rules</strong></p>         </td>
         <td><p>Execution type parameters:</p>
<p>If you set <span class="code">default_execution_type</span> to:</p>
<ul>
<li><em>COMMAND</em>, then enter a value for the <span class="code">default_command_line</span> parameter.</li>
<li><em>MODEL</em>, then enter a value for the <span class="code">default_model</span> parameter.</li>
<li><em>PERL</em>, then enter a value for the <span class="code">default_perl_script</span> parameter.</li>
</ul>
<p>Restricted processing parameters:</p>
<p>To limit Decision Rule processing to a limited set of Transfers, you must set the parameter <span class="code">restrict_processing</span> to <span style="font-weight: bold;">Y</span> (yes). Gateway then restricts processing based one or more conditions that you set for the following parameters:</p>
<ul>
<li><span class="code">restrict_processing_on_direction</span>: restrict processing to either <span style="font-weight: bold;">Input</span> or <span style="font-weight: bold;">Output</span> Transfers</li>
<li><span class="code">restrict_processing_on_mode</span>: restrict processing to either <span style="font-weight: bold;">Initiator</span> or <span style="font-weight: bold;">Responder</span> mode Transfers</li>
<li><span class="code">restrict_processing_on_state</span>: restrict processing to either <span style="font-weight: bold;">Ended</span>,<span style="font-weight: bold;"> Canceled</span> or <span style="font-weight: bold;">Acknowledged</span> Transfers</li>
<li><span class="code">restrict_processing_on_type</span>: restrict processing to Transfers of the specified type (TRANS, POLL, LOT,...)</li>
<li><span class="code">restrict_processing_on_protocol</span>: restrict processing to Transfers of the specified protocol (PEL, ODETTE, PHSE,…)</li>
</ul>
<p>If multiple values are specified for a parameter, these must be separated by a comma with no extra spaces.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example 1</strong></p>         </td>
         <td><p>The following example defines the order of Decision Rules in the list.</p>
<p>   peladm update_ruletable  -a TABFTP</p>
<p>   peladm update_ruletable  -a "TABPHSE, TABHTTP"</p>
<p>Gateway adds the Decision Rule TABFTP to the list, followed by TABPHSE and TABHTTP. Gateway evaluates the list of Decision Rules in this order: TABFTP &gt; TABPHSE &gt; TABHTTP.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example 2</strong></p>         </td>
         <td><p>Use the parameters <span class="code">move_up</span> and <span class="code">move_down</span> to modify the order of Decision Rules in the list. For example, the command:</p>
<p>   peladm update_ruletable  -move_up TABPHSE</p>
<p>moves Decision Rule TABPHSE up one position in the list.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example 3</strong></p>         </td>
         <td><p>The following example sets the default execution type for the whole Rule Table. In addition it uses the <span class="code">restrict_processing</span> parameter to restrict processing to Transfers with Ended state and of the type TRANS.</p>
<p>peladm update_ruletable  -default_execution_type Default</p>
<p>   -restrict_processing Y</p>
<p>   -restrict_processing_on_state E</p>
<p>   -restrict_processing_on_type TRANS</p>         </td>
      </tr>
   </tbody>
</table>

<span id="peladm_delete_ruletable"></span>

## Deleting a Rule Table: peladm delete\_ruletable

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><strong>peladm delete_ruletable</strong> [-name]</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to delete a Rule Table.</p>
<p>Repeat the command for each Rule Table you want to delete.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameter</strong></p>         </td>
         <td><p>-name (-n)</p>         </td>
         <td><p>Enter the name of the Rule Table you want to delete.</p>         </td>
      </tr>
      <tr>
         <td><p>-type_of_rules_table (-type)</p>         </td>
         <td><p>Enter the type of Rule Table you want to delete. Enter one of:</p>
<ul>
<li><strong>XFER_CHANGE_STATE</strong></li>
<li><strong>TEMPORAL</strong></li>
<li><strong>FILE_STORING</strong></li>
<li><strong>XMS</strong></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>Enter the command:</p>
<p>   peladm delete_ruletable  -n MyRuleTable</p>
<p>Gateway deletes the Rule Table with the name <span style="font-style: italic;">MyRuleTable</span>.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="peldsp_display_ruletable"></span>

## Displaying Rule Table properties: peldsp display\_ruletable

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><strong>peldsp display_ruletable</strong> [-name] [-type_of_rules_table]</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to display the properties of a specified Rule Table.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span class="code">-name (-n)</span>: Enter the name of the Rule Table whose properties you want to display.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-type_of_rules_table (-type)</span>: Enter the type of Rule Table for which you want to display the properties.</p>
<p>Enter one of:</p>
<ul>
<li>XFER_CHANGE_STATE<span style="font-weight: normal;"> (default)</span></li>
<li>TEMPORAL</li>
<li>FILE_STORING</li>
<li>XMS</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>Enter the command:</p>
<p>   peldsp display_ruletable  -n MyRuleTable</p>
<p>Gateway returns the properties of the Rule Table with the name <span style="font-style: italic;">MyRuleTable</span>.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="peldsp_select_ruletable"></span>

## Displaying all Rule Table names: peldsp select\_ruletable

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><strong>peldsp select_ruletable</strong> [-name] [-default_execution_type] [-default_model] [-default_perl_script] [-type_of_rules_table] [-xms_connector_name]</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command without parameters to display the names of all Rule Tables.</p>
<p>Alternatively, add parameters as filtering criteria to restrict the return results.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>-name (-n)</p>         </td>
         <td><p>Rule Table name.</p>         </td>
      </tr>
      <tr>
         <td><p>-default_execution_type (-det)</p>         </td>
         <td><p>Type of process to be triggered if no process is triggered by an associated Decision Rule. Enter one of:</p>
<ul>
<li><strong>MODEL</strong></li>
<li><strong>AMTRIX</strong></li>
<li><strong>PERL</strong></li>
<li><strong>COMMAND</strong></li>
<li><strong>TO_XMS</strong></li>
<li><strong>NONE</strong> (default)</li>
<li><strong>LOG_CLEANING</strong></li>
<li><strong>MAILBOX_CLEANING</strong></li>
<li><strong>STAT_CLEANING</strong></li>
<li><strong>XIB</strong></li>
<li><strong>DEFAULT</strong></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-default_model (-dm)</p>         </td>
         <td><p>If you entered the value <span style="font-style: italic;">MODEL</span> for the <span class="code">default_execution_type</span> parameter, you can add a Model name.</p>         </td>
      </tr>
      <tr>
         <td><p>-default_perl_script (-dps)</p>         </td>
         <td><p>If you entered the value <span style="font-style: italic;">PERL</span> for the <span class="code">default_execution_type</span> parameter, you can enter the Perl script name and path.</p>         </td>
      </tr>
      <tr>
         <td><p>-type_of_rules_table (-type)</p>         </td>
         <td><p>Enter one of the following types:</p>
<ul>
<li>XFER_CHANGE_STATE<span style="font-weight: normal;"> (default)</span></li>
<li>TEMPORAL</li>
<li>FILE_STORING</li>
<li>XMS</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-xms_connector_name (-xcn)</p>         </td>
         <td><p>Use this parameter if you are displaying an XMS-type Rule Table.</p>
<p>Enter an Axway Messaging connector name.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>Enter the command:</p>
<p>   peldsp select_ruletable</p>
<p>Gateway returns the names of all Rule Tables existing on the server.</p>         </td>
      </tr>
   </tbody>
</table>

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
