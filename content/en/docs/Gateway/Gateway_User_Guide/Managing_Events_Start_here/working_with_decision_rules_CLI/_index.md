{
    "title": "Working with Decision Rules (command line)",
    "linkTitle": "Command line operations",
    "weight": "180"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Events

<span class="code" style="font-weight: bold;">[peladm create\_decisionrule](#peladm_create_decisionrule)</span>

<span class="code" style="font-weight: bold;">[peladm update\_decisionrule](#peladm_update_decisionrule)</span>

<span class="code" style="font-weight: bold;">[peladm delete\_decisionrule](#peladm_delete_decisionrule)</span>

<span class="code" style="font-weight: bold;">[peldsp display\_decisionrule](#peldsp_display_decisionrule)</span>

<span class="code" style="font-weight: bold;">[peldsp select\_decisionrule](#peldsp_select_decisionrule)</span>

<span id="peladm_create_decisionrule"></span>

## Creating a Decision Rule: peladm create\_decisionrule

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code" style="font-weight: bold;">peladm create_decisionrule</span> [see parameters below]</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to create a new Decision Rule. Specify at least one condition for the Decision Rule. You can specify conditions in two ways:</p>
<ul>
<li>Use the parameter <span class="code">cond_arg (-ca)</span> to list a set of conditions separated by the semi-colon character.</li>
<li>Use the parameter <span class="code">-import_cond (-ic)</span> to specify a file to import, that contains a list of conditions. Each line in the file contains an argument name, an operator and a value.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span class="code">name (-n)</span><br />
<span style="font-style: italic;">(Mandatory)</span></p>         </td>
         <td><p>Enter a unique name for the Decision Rule.</p>         </td>
      </tr>
      <tr>
         <td><p>type_of_decisionrules (-type)</p>         </td>
         <td><p>Enter one of the following Decision Rule types:</p>
<ul>
<li>XFER_CHANGE_STATE<span style="font-weight: normal;"> (default)</span></li>
<li>TEMPORAL</li>
<li>FILE_STORING</li>
<li>XMS</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>comments (-cts)</p>         </td>
         <td><p>Enter a free text description of the Decision Rule you are creating.</p>         </td>
      </tr>
      <tr>
         <td><p>execution_type (-et)</p>         </td>
         <td><p>The type of process to be triggered by a Decision Rule. Enter one of the following values:</p>
<ul>
<li><strong>MODEL</strong> = the execution is defined by a Model. Specify the Model in the <span class="code">model (-ml)</span> parameter below.</li>
<li><strong>AMTRIX</strong> = redirect the Transfer to AMTrix for processing</li>
<li><strong>PERL</strong> Refer to the readme in the following folder:
<ul>
<li>On UNIX
<code>&lt;Gateway installation directory&gt;/run_time/scripts/perl/</code></li>
<li>On Windows
<code>&lt;Gateway installation directory&gt;\run_time\scripts\perl\</code></li>
</ul></li>
<li><strong>COMMAND</strong> = the execution type is a command line or script specified in the <span class="code">command_line</span> parameter. Refer to <a href="decision_rules_executing_scripts">Executing scripts as command lines from Decision Rules</a>.</li>
<li><strong>TO_XMS</strong></li>
<li><strong>NONE</strong> (default)</li>
<li><strong>LOG_CLEANING</strong></li>
<li><strong>MAILBOX_CLEANING</strong></li>
<li><strong>STAT_CLEANING</strong></li>
<li><strong>XIB</strong> = redirect the Transfer to Integrator for processing. The payload file for a Transfer which was routed to Integrator is not deleted by the purge operation. For more information, refer to <a href="../../connectors_about/integrator_about/integrator_connector#Purging">Purging for transfers routed from Gateway to Integrator</a>.</li>
<li><strong>DEFAULT</strong> = route the transfer using a Model inside an Application. This option is only available via online commands. The option exists for reasons of compatibility with earlier product versions.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>link_transfers (-lt)</p>         </td>
         <td><p>Use this parameter if you enter the value <span style="font-style: italic;">MODEL</span> for the <span class="code">execution_type</span> parameter.</p>
<p>Enter one of the following values:</p>
<ul>
<li><span style="font-weight: bold;">Y</span> (default) = Yes - create a logical link between the incoming and the outgoing Transfers</li>
<li><span style="font-weight: bold;">N</span> = No - no link between the incoming and the outgoing Transfers</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>model (-ml)</p>         </td>
         <td><p>If you entered the value <span style="font-style: italic;">MODEL</span> or <span style="font-style: italic;">TO_XMS</span> for the <span class="code">execution_type</span> parameter, enter a Model name.</p>         </td>
      </tr>
      <tr>
         <td><p>purge_model (-pm)</p>         </td>
         <td><p>If you entered the value <span style="font-style: italic;">MAILBOX_CLEANING</span> for the <span class="code">execution_type</span> parameter, enter the name of an existing Purge Model to define the purge operation on the Mailbox.</p>         </td>
      </tr>
      <tr>
         <td><p>perl_script (-ps)</p>         </td>
         <td><p>If you entered the value <span style="font-style: italic;">PERL</span> for the <span class="code">execution_type</span> parameter, enter the Perl script name and access path.</p>         </td>
      </tr>
      <tr>
         <td><p>command_line (-cl)</p>         </td>
         <td><p>If you entered the value <span style="font-style: italic;">COMMAND</span> for the <span class="code">execution_type</span> parameter, enter the execution command line. The command line can include symbolic variables. Alternatively, you can enter the path and file name of a script to execute. Refer to <a href="decision_rules_executing_scripts">Executing scripts as command lines from Decision Rules</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>cond_arg (-ca)</p>         </td>
         <td><p>Enter one or more conditional arguments in the format <span style="font-style: italic;">condition1;condition2</span></p>
<p>For example:</p>
<p><span class="code">cond "destination = FTPC; direction = I, protocol&lt;&gt;PHSE,FTP; appli = &amp;(file_name)"</span></p>         </td>
      </tr>
      <tr>
         <td><p>prop_list_name (-pln)</p>         </td>
         <td><p>Only for JMS or Axway Messaging</p>
<p>Enter a Property List name.</p>         </td>
      </tr>
      <tr>
         <td><p>xms_connector_out_name (-xcn)</p>         </td>
         <td><p>Use this parameter if you are creating an XMS-type Decision Rule.</p>
<p>Enter an Axway Messaging connector name.</p>         </td>
      </tr>
      <tr>
         <td><p>import_cond (-ic)</p>         </td>
         <td><p>Enter the name of the file that contains the execution conditions.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Usage rules</strong></p>         </td>
         <td><p><span style="font-weight: bold;">Execution type parameters:</span></p>
<p>If you set <span class="code">execution_type</span> to:</p>
<ul>
<li><em>COMMAND</em>, then enter a value for the <span class="code">command_line</span> parameter. You can enter a command or the path and file name of a script. Refer to <a href="decision_rules_executing_scripts">Executing scripts as command lines from Decision Rules</a>.</li>
<li><em>MODEL</em>, then enter a value for the <span class="code">model</span> parameter.</li>
<li><em>PERL</em>, then enter a value for the <span class="code">perl_script</span> parameter.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><strong>Example 1</strong></p>         </td>
         <td><p>The following example creates a Decision Rule to handle incoming files from the FTP client FTPC.</p>
<p>peladm create_decisionrule</p>
<p>   -name TABFTP</p>
<p>   -type XFER_CHANGE_STATE</p>
<p>   -execution_type Model</p>
<p>   -ml MODELFTP</p>
<p>   -cond_arg "destination = FTPC; direction = I"</p>
<p>   -protocol&lt;&gt;PHSE,FTP; appli = &amp;(file_name)"</p>
<p>Gateway checks the following conditions:</p>
<ul>
<li>Destination = FTPC</li>
<li>Direction = Input</li>
<li>Protocol = either PeSIT HS E or FTP</li>
<li>Application = file name of the current Transfer</li>
</ul>
<p>If all conditions correspond to the current Transfer parameters, Gateway submits a new Transfer Request and applies the Model MODELFTP. This Model contains the parameters required to route the Transfer.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example 2</strong></p>         </td>
         <td><p>The following example creates a Decision Rule for routing to a PeSIT client:</p>
<p>peladm create_decisionrule</p>
<p>   -name TABPHSE</p>
<p>   -type XFER_CHANGE_STATE</p>
<p>   -execution_type DEFAULT</p>
<p>   -cond_arg "destination = *PHSE; rec_len&gt;=1200; originator #FTPC"</p>
<p>Gateway checks the following conditions:</p>
<ul>
<li>Destination = *PHSE (a destination Site whose name ends with PHSE)</li>
<li>Record length = greater than or equal to 1200</li>
<li>Originator = any originator Site that is not FTPC</li>
</ul>
<p>If all the conditions correspond to the current Transfer parameters, Gateway submits a new Transfer Request by using the execution type <em>DEFAULT</em>.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="peladm_update_decisionrule"></span>

## Updating Decision Rules: peladm update\_decisionrule

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code" style="font-weight: bold;">peladm update_decisionrule</span> [see parameters below]</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to modify an existing Decision Rule.</p>
<p>You can:</p>
<ul>
<li>Add a new condition to a Decision Rule</li>
<li>Modify an existing condition</li>
<li>Delete an existing condition</li>
<li>Modify the name of the condition import file</li>
<li>Modify the rule type</li>
<li>Link or un-link Transfers incoming and outgoing Transfers</li>
<li>Modify the routing behavior for this Rule</li>
<li>Modify the Model referenced in this Rule</li>
<li>Modify the Perl script referenced in this Rule</li>
<li>Modify the command line referenced in this Rule</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>name (-n)</p>
<p>(Mandatory)</p>         </td>
         <td><p>Enter a unique name for the Decision Rule.</p>         </td>
      </tr>
      <tr>
         <td><p>type_of_decisionrules (-type)</p>         </td>
         <td><p>Enter one of the following Decision Rule types:</p>
<ul>
<li>XFER_CHANGE_STATE<span style="font-weight: normal;"> (default)</span></li>
<li>TEMPORAL</li>
<li>FILE_STORING</li>
<li>XMS</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>comments (-cts)</p>         </td>
         <td><p>Edit the free text description of the Decision Rule.</p>         </td>
      </tr>
      <tr>
         <td><p>execution_type (-et)</p>         </td>
         <td><p>The type of process to be triggered by a Decision Rule. Enter one of the following values:</p>
<ul>
<li><strong>MODEL</strong> = the execution is defined by a Model. Specify the Model in the <span class="code">model (-ml)</span> parameter below.</li>
<li><strong>AMTRIX</strong> = redirect the Transfer to AMTrix for processing</li>
<li><strong>PERL</strong></li>
<li><strong>COMMAND</strong> = the execution type is a command line or script specified in the <span class="code">command_line</span> parameter. Refer to <a href="decision_rules_executing_scripts">Executing scripts as command lines from Decision Rules</a>.</li>
<li><strong>TO_XMS</strong></li>
<li><strong>NONE</strong> (default)</li>
<li><strong>LOG_CLEANING</strong></li>
<li><strong>MAILBOX_CLEANING</strong></li>
<li><strong>STAT_CLEANING</strong></li>
<li><strong>XIB</strong> = redirect the Transfer to Integrator for processing. The payload file for a Transfer which was routed to Integrator is not deleted by the purge operation. For more information, refer to <a href="../../connectors_about/integrator_about/integrator_connector#Purging">Purging for transfers routed from Gateway to Integrator</a>.</li>
<li><strong>DEFAULT</strong> = route the transfer using a Model inside an Application. This option is only available via online commands. The option exists for reasons of compatibility with earlier product versions.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>link_transfers (-lt)</p>         </td>
         <td><p>Use this parameter if you enter the value <span style="font-style: italic;">MODEL</span> for the <span class="code">execution_type</span> parameter.</p>
<p>Enter one of the following values:</p>
<ul>
<li><span style="font-weight: bold;">Y</span> (default) = Yes - create a logical link between the incoming and the outgoing Transfers</li>
<li><span style="font-weight: bold;">N</span> = No - no link between the incoming and the outgoing Transfers</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>model (-ml)</p>         </td>
         <td><p>If you entered the value <span style="font-style: italic;">MODEL</span> or <span style="font-style: italic;">TO_XMS</span> for the <span class="code">execution_type</span> parameter, enter a Model name.</p>         </td>
      </tr>
      <tr>
         <td><p>purge_model (-pm)</p>         </td>
         <td><p>If you entered the value <span style="font-style: italic;">MAILBOX_CLEANING</span> for the <span class="code">execution_type</span> parameter, enter the name of an existing Purge Model to define the purge operation on the Mailbox.</p>         </td>
      </tr>
      <tr>
         <td><p>perl_script (-ps)</p>         </td>
         <td><p>If you entered the value <span style="font-style: italic;">PERL</span> for the <span class="code">execution_type</span> parameter, enter the Perl script name and access path.</p>         </td>
      </tr>
      <tr>
         <td><p>command_line (-cl)</p>         </td>
         <td><p>If you entered the value <span style="font-style: italic;">COMMAND</span> for the <span class="code">execution_type</span> parameter, enter the execution command line.</p>         </td>
      </tr>
      <tr>
         <td><p>prop_list_name (-pln)</p>         </td>
         <td><p>Only for JMS or Axway Messaging</p>
<p>Enter a Property List name.</p>         </td>
      </tr>
      <tr>
         <td><p>xms_connector_out_name (-xcn)</p>         </td>
         <td><p>Use this parameter if you are creating an XMS-type Decision Rule.</p>
<p>Enter an Axway Messaging connector name.</p>         </td>
      </tr>
      <tr>
         <td><p>add_cond (-a)</p>         </td>
         <td><p>Add one or more conditions.</p>         </td>
      </tr>
      <tr>
         <td><p>update_cond (-u)</p>         </td>
         <td><p>Update on or more existing conditions.</p>         </td>
      </tr>
      <tr>
         <td><p>delete_cond (-d)</p>         </td>
         <td><p>Specify a condition to delete.</p>         </td>
      </tr>
      <tr>
         <td><p>import_cond (-ic)</p>         </td>
         <td><p>Specify a file the file to import that contains the execution conditions.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Usage rules</strong></p>         </td>
         <td><p><span style="font-weight: bold;">Execution type parameters:</span></p>
<p>If you set <span class="code">execution_type</span> to:</p>
<ul>
<li><em>COMMAND</em>, then enter a value for the <span class="code">command_line</span> parameter.</li>
<li><em>MODEL</em>, then enter a value for the <span class="code">model</span> parameter.</li>
<li><em>PERL</em>, then enter a value for the <span class="code">perl_script</span> parameter.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><strong>Syntax Examples</strong></p>         </td>
         <td><p>Adding a condition:</p>
<p>   peladm update_decisionrule</p>
<p>      {-name &lt;Decision rule name&gt;}</p>
<p>      [-add_cond ['"'argument_name operator value'"';';']*]</p>
<p>Modifying a condition:</p>
<p>   peladm update_decisionrule</p>
<p>      {-name &lt;Decision rule name&gt;}</p>
<p>      [-update_cond ['"'argument_name operator value'"'';']*]</p>
<p>Deleting a condition:</p>
<p>   peladm update_decisionrule</p>
<p>      {-name &lt;Decision rule name&gt;}</p>
<p>      [-update_cond ['"'argument_name operator value'"'';']*]</p>
<p>Modifying routing behavior:</p>
<p>   peladm update_decisionrule</p>
<p>      {-name &lt;Decision rule name&gt;}</p>
<p>      [-execution_type { MODEL | AMTRIX | PERL | COMMAND |<br />
      TO_XMS | DEFAULT | NONE | LOG_CLEANING |<br />
      MAILBOX_CLEANING | STAT_CLEANING | XIB }]</p>
<p>Modifying the Model:</p>
<p>   peladm update_decisionrule</p>
<p>      {-name &lt;Decision rule name&gt;}</p>
<p>      [-model model name]</p>
<p>Modifying the Perl script:</p>
<p>   peladm update_decisionrule</p>
<p>      {-name &lt;Decision rule name&gt;}</p>
<p>      [-perl_script script access path]</p>
<p>Modifying the online command:</p>
<p>   peladm update_decisionrule</p>
<p>      {-name &lt;Decision rule name&gt;}</p>
<p>      [-command_line online command]</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following example updates the Decision Rule <span style="font-style: italic;">MyRule</span> and sets the processing type to use the Model <span style="font-style: italic;">MyModel</span>:</p>
<p>peladm update_decisionrule</p>
<p>   -name MyRule</p>
<p>   -execution_type Model</p>
<p>   -model MyModel</p>         </td>
      </tr>
   </tbody>
</table>

<span id="peladm_delete_decisionrule"></span>

## Deleting a Decision Rule: peladm delete\_decisionrule

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code"><strong>peladm delete_decisionrule</strong> [-name] [-type_of_decisionrules]</span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to delete an existing Decision Rule.</p>
<p>Repeat the command for each Decision Rule you want to delete.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>-name (-n)</p>         </td>
         <td><p>Enter the name of the Decision Rule you want to delete.</p>         </td>
      </tr>
      <tr>
         <td><p>-type_of_decisionrules (-type)</p>         </td>
         <td><p>Enter the type of Decision Rule you want to delete. Enter one of the following values:</p>
<ul>
<li>XFER_CHANGE_STATE</li>
<li>TEMPORAL</li>
<li>FILE_STORING</li>
<li>XMS</li>
</ul>         </td>
      </tr>
      <tr>
         <td><strong>Notes</strong>         </td>
         <td><p>If the <code>peladm delete_decisionrule </code>command produces an error with a message like this:</p>
<p><em>The decision rule that wants to be deleted (peladm delete_decisionrule -n</em> MY_DECISION_RULE <em>-type</em> MY_TYPE<em>) is linked to a Rule Table (</em>MY_RULETABLE<em>), therefore it cannot be deleted.</em></p>
<p>In this case, the solution is to first unlink the decision rule from the MY_RULETABLE table:</p>
<p><code>peladm update_ruletable -n MY_RULETABLE -type MY_TYPE -d MY_DECISION_RULE</code></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>Enter the command:</p>
<p><span class="code" style="font-weight: bold;">   peladm delete_decisionrule  -n MyDecisionRule</span></p>
<p>Gateway deletes the Decision Rule with the name <span style="font-style: italic;">MyDecisionRule</span>.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="peldsp_display_decisionrule"></span>

## Displaying Decision Rule properties: peldsp display\_decisionrule

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code"><strong>peldsp display_decisionrule</strong> [-name] [-type_of_decisionrules]</span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to display the properties of a specified Decision Rule.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span class="code">-name (-n)</span>: Enter the name of the Decision Rule whose properties you want to display</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-type_of_decision_rules (-t)</span>: Enter the type of Decision Rule whose properties you want to display. Enter one of the following values:</p>
<ul>
<li>XFER_CHANGE_STATE</li>
<li>TEMPORAL</li>
<li>FILE_STORING</li>
<li>XMS</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>Enter the command:</p>
<p><span class="code" style="font-weight: bold;">   peldsp display_decisionrule  -n MyDecisionRule</span></p>
<p>Gateway returns the properties of the Decision Rule with the name <span style="font-style: italic;">MyDecisionRule</span>:</p>
<p>   rd_name MyDecisionRule</p>
<p>   rd_type 'XFER_CHANGE_STATE'</p>
<p>   rd_comments ""</p>
<p>   rd_execution_type = MODEL</p>
<p>   rd_link_transfers = Y</p>
<p>   rd_perl_script =</p>
<p>   rd_cond_1 = protocol&lt;&gt; FTP, PHSE</p>         </td>
      </tr>
   </tbody>
</table>

<span id="peldsp_select_decisionrule"></span>

## Displaying all Decision Rule names: peldsp select\_decisionrule

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code"><strong>peldsp select_decisionrule</strong></span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to display the names of all Decision Rules.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>Enter the command with no parameters to display the names of all Decision Rules.</p>
<p>To list Decision Rules according to a given parameter, enter the command followed by the parameter, for example <span class="code">-name</span> or <span class="code">-type TEMPORAL</span>.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>Enter the command:</p>
<p><span class="code" style="font-weight: bold;">   peldsp select_decisionrule</span></p>
<p>Gateway returns the names of all Decision Rules existing on the server.</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Decision Rules and Rule Tables: Parameters List](decision_rules_rule_tables_parameter_list)

[Command syntax for Scheduling Event Models](scheduling_event_model_command_syntax) (date syntax)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
