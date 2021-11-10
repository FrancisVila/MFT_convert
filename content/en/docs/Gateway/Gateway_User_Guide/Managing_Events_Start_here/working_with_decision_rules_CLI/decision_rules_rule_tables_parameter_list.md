{
    "title": "Decision Rules and Rule Tables: Parameters List",
    "linkTitle": "Decision Rules & Rule Tables: Parameters List",
    "weight": "210"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Events

The following table lists all Decision Rule and Rule Table command parameters in alphabetical order. The corresponding field name in the Gateway GUI is displayed in <span style="font-style: italic;font-weight: bold;">italics</span>

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Parameter         </th>
<th class="HeadE-Column1-Header1">Meaning         </th>
<th class="HeadD-Column1-Header1">Values         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>add_cond (-a)</p>
<p><span style="font-style: italic;font-weight: bold;">(None)</span></p>         </td>
         <td><p>Modifying Decision Rule</p>
<p>Add one or more conditions to an existing Decision Rule</p>         </td>
         <td><p>Condition expression that comprises:</p>
<ul>
<li>argument name</li>
<li>operator</li>
<li>value</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>add_decisionrule (-a)</p>
<p><span style="font-style: italic;font-weight: bold;">(None)</span></p>         </td>
         <td><p>Rule Tables</p>
<p>Add a Decision Rule to the list</p>         </td>
         <td><p>Decision Rule name</p>         </td>
      </tr>
      <tr>
         <td><p>cond_arg (-ca)</p>
<p><span style="font-style: italic;font-weight: bold;">Argument</span></p>         </td>
         <td><p>Creating Decision Rule</p>
<p>Define one or more conditions for the Decision Rule</p>         </td>
         <td><p>Condition expression that comprises:</p>
<ul>
<li>argument name</li>
<li>operator</li>
<li>value</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>command_line (-cl)</p>
<p><span style="font-style: italic;font-weight: bold;">Batch command</span></p>         </td>
         <td><p>Command line to execute. Can include symbolic variables.</p>         </td>
         <td><p>Path of the command. For example:</p>
<p>/bin/ksh/p_home_dir /run_time/ftpconf.sh</p>         </td>
      </tr>
      <tr>
         <td><p>comments (-cts)</p>
<p><span style="font-style: italic;font-weight: bold;">Comments</span></p>         </td>
         <td><p>Free-text description</p>         </td>
         <td><p>Maximum: 80 alphanumeric characters</p>         </td>
      </tr>
      <tr>
         <td><p>default_command_line (-dcl)</p>
<p><span style="font-style: italic;font-weight: bold;">Batch command</span></p>         </td>
         <td><p>Rule Tables</p>
<p>Define default command to execute if no Decision Rule matches the Transfer parameters.</p>
<p>Set this parameter if you set the <span class="code">default_execution_type</span> to <span style="font-style: italic;">Command.</span></p>         </td>
         <td><p>Path of the command</p>         </td>
      </tr>
      <tr>
         <td><p>default_execution_type (-det)</p>
<p><span style="font-style: italic;font-weight: bold;">Default execution type</span></p>         </td>
         <td><p>Rule Tables</p>
<p>Define default processing to use if no Decision Rule matches the current Transfer parameters.</p>         </td>
         <td><p>One of the following values:</p>
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
<li><strong>DEFAULT</strong> (<em>only via command line</em>) = route the transfer using a Model inside an Application. This option exists for reasons of compatibility with earlier product versions.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>default_model (-dm)</p>
<p><span style="font-style: italic;font-weight: bold;">Model</span></p>         </td>
         <td><p>Rule Tables</p>
<p>Define default Model to use if no Decision Rule matches the current Transfer parameters.</p>
<p>Set this parameter if you set <span class="code">default_execution_type</span> to <span style="font-style: italic;">Model</span>.</p>         </td>
         <td><p>Name of a General Model</p>         </td>
      </tr>
      <tr>
         <td><p>default_perl_script (-ds)</p>
<p><span style="font-style: italic;font-weight: bold;">Perl script</span></p>         </td>
         <td><p>Rule Tables</p>
<p>Define default Perl script to use if no Decision Rule matches the current Transfer parameters.</p>
<p>Set this parameter if you set <span class="code">default_execution_type</span> to <span style="font-style: italic;">Perl</span>.</p>         </td>
         <td><p>Path of the Perl script</p>         </td>
      </tr>
      <tr>
         <td><p>delete_cond (-d)</p>
<p><span style="font-style: italic;font-weight: bold;">(None)</span></p>         </td>
         <td><p>Modifying Decision Rule</p>
<p>Delete Decision Rule condition</p>         </td>
         <td><p>Condition expression that comprises:</p>
<ul>
<li>argument name</li>
<li>operator</li>
<li>value</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>delete_all_decisionrules (-dad)</p>         </td>
         <td><p> </p>         </td>
         <td><p>One of the following values:</p>
<ul>
<li><strong>Y</strong> (yes) (default)</li>
<li><strong>N</strong> (no)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>delete_decisionrule (-d)</p>
<p><span style="font-style: italic;font-weight: bold;">(None)</span></p>         </td>
         <td><p>Rule Tables</p>
<p>Disable Decision Rule in the list</p>         </td>
         <td><p>Decision Rule name</p>         </td>
      </tr>
      <tr>
         <td><p>execution_delay (-delay)</p>         </td>
         <td><p>A positive integer which defines the execution delay</p>         </td>
         <td><p>One of the following values:</p>
<ul>
<li>UNTIL_NEXT (default)</li>
<li>INFINITE</li>
<li>1 ... 2147483647</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>execution_type (-et)</p>
<p><span style="font-style: italic;font-weight: bold;">Execution type</span></p>         </td>
         <td><p>Decision Rule</p>
<p>The type of process to be triggered by a Decision Rule.</p>         </td>
         <td><p>One of the following values:</p>
<ul>
<li><strong>MODEL</strong></li>
<li><strong>AMTRIX</strong></li>
<li><strong>PERL</strong></li>
<li><strong>COMMAND</strong></li>
<li><strong>TO_XMS</strong></li>
<li><strong>NONE</strong></li>
<li><strong>LOG_CLEANING</strong></li>
<li><strong>MAILBOX_CLEANING</strong></li>
<li><strong>STAT_CLEANING</strong></li>
<li><strong>XIB</strong> (for Integrator)</li>
<li><strong>DEFAULT</strong> (<em>only via command line</em>) = route the transfer using a Model inside an Application. This option exists for reasons of compatibility with earlier product versions.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>import_cond (ic)</p>
<p><span style="font-style: italic;font-weight: bold;">(None)</span></p>         </td>
         <td><p>Creating Decision Rule</p>
<p>Import a text file that defines list of conditions to apply in this Decision Rule</p>         </td>
         <td><p>Full file name and path that contains set of conditions to import.</p>         </td>
      </tr>
      <tr>
         <td><p>is_optimized_cleaning (-optclean)</p>
<p>Optimized cleaning</p>         </td>
         <td><p>If this boolean is set, the Optimized cleaning function is activated</p>         </td>
         <td><p>One of the following values:</p>
<ul>
<li><strong>Y</strong> (yes) (default)</li>
<li><strong>N</strong> (no)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>is_rules_table_exclusive (-excl)</p>         </td>
         <td><p>If this boolean is set, the Rule Table is exclusive</p>         </td>
         <td><p>One of the following values:</p>
<ul>
<li><strong>Y</strong> (yes) (default)</li>
<li><strong>N</strong> (no)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>is_user_exits_activated (-exit)</p>         </td>
         <td><p>If this boolean is set, the user exits are called</p>         </td>
         <td><p>One of the following values:</p>
<ul>
<li><strong>Y</strong> (yes) (default)</li>
<li><strong>N</strong> (no)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>link_transfers (-lt)</p>
<p><span style="font-style: italic;font-weight: bold;">Link input and output transfers</span></p>         </td>
         <td><p>Decision Rule</p>
<p>Link output Transfer Request to input Transfer. If you set this value to <span style="font-weight: bold;">Yes</span>:</p>
<ul>
<li>the input Transfer Request parameter <span class="code">route_to_xfer</span> is set to the output Transfer identifier</li>
<li>the output Transfer Request parameter <span class="code">route_from_xfer</span> is set to the input Transfer identifier</li>
</ul>         </td>
         <td><p>One of the following values:</p>
<ul>
<li><strong>Y</strong> (yes) (default)</li>
<li><strong>N</strong> (no)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>log_level (-ll)</p>
<p><span style="font-style: italic;font-weight: bold;">(None)</span></p>         </td>
         <td><p>Rule Tables</p>
<p>Defines the log level for error messages</p>         </td>
         <td><p>One of the following values:</p>
<ul>
<li><span style="font-weight: bold;">0</span> = minimum log level</li>
<li><span style="font-weight: bold;">1</span> = medium (reports errors regarding Decision Rule failures and so on)</li>
<li><span style="font-weight: bold;">2</span> = detailed (includes information regarding symbolic variables)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>model (-ml)</p>
<p><span style="font-style: italic;font-weight: bold;">Model</span></p>         </td>
         <td><p>Creating Decision Rule</p>
<p>General Model to use for routing definition</p>         </td>
         <td><p>General Model name.</p>
<p>Maximum: 26 alphanumeric characters.</p>
<p>The Model name that you specify must have a corresponding General Model that includes the <span class="code" style="font-weight: bold;">dest_alias</span> definition.</p>
<p>Either the General Model or the associated Protocol Model must include the following parameters:</p>
<ul>
<li>file_component</li>
<li>appli</li>
</ul>
<p>You can use symbolic variables if you want to retrieve the value for these parameters from the incoming Transfer.</p>         </td>
      </tr>
      <tr>
         <td><p>move_down (-md)</p>
<p><span style="font-style: italic;font-weight: bold;">(None)</span></p>         </td>
         <td><p>Updating Rule Table</p>
<p>Move Decision Rule down one place in the list</p>         </td>
         <td><p>Decision Rule name</p>         </td>
      </tr>
      <tr>
         <td><p>move_up (-mu)</p>
<p><span style="font-style: italic;font-weight: bold;">(None)</span></p>         </td>
         <td><p>Updating Rule Table</p>
<p>Move Decision Rule up one place in the list</p>         </td>
         <td><p>Decision Rule name</p>         </td>
      </tr>
      <tr>
         <td><p>name (-n)</p>
<p><span style="font-style: italic;font-weight: bold;">Name</span></p>         </td>
         <td><p>Decision Rule or Rule Table</p>
<p>Decision Rule or Rule Table name</p>         </td>
         <td><p>Decision Rule or Rule Table name.</p>
<p>Maximum: 26 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>perl_script (-ps)</p>
<p><span style="font-style: italic;font-weight: bold;">Perl script</span></p>         </td>
         <td><p>Decision Rule</p>
<p>Perl script to use to define routing</p>         </td>
         <td><p>Path of Perl script.</p>
<p>Maximum: 128 characters.</p>
<p>For example, in UNIX:</p>
<p>/home/users/utill/scripts /my_script.pl</p>         </td>
      </tr>
      <tr>
         <td><p>prop_list_name (-pln)</p>         </td>
         <td><p>Name of Property List</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>restrict_processing (-rp)</p>
<p><span style="font-style: italic;font-weight: bold;">Restrict processing</span></p>         </td>
         <td><p>Rule Tables</p>
<p>Restricts processing to Transfers that conform to the conditions that you define for the following parameters:</p>
<ul>
<li>restrict_processing_on_state</li>
<li>restrict_processing_on_direction</li>
<li>restrict_processing_on_type</li>
<li>restrict_processing_on_mode</li>
<li><p>restrict_processing_on_protocol</p></li>
</ul>         </td>
         <td><p>One of the following values:</p>
<ul>
<li><strong>Y</strong> (yes)</li>
<li><strong>N</strong> (no)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>restrict_processing_on_direction (-rpod)</p>
<p><span style="font-style: italic;font-weight: bold;">Transfer direction</span></p>         </td>
         <td><p>Rule Tables</p>
<p>Restricts processing to either incoming or outgoing Transfers</p>         </td>
         <td><p>One of the following values:</p>
<ul>
<li><span style="font-weight: bold;">I</span> (In)</li>
<li><span style="font-weight: bold;">O</span> (Out)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>restrict_processing_on_mode (-rpom)</p>
<p><span style="font-style: italic;font-weight: bold;">Transfer mode</span></p>         </td>
         <td><p>Rule Tables</p>
<p>Restricts processing to Transfer in either Initiator or Responder mode</p>         </td>
         <td><p>One of the following values:</p>
<ul>
<li><span style="font-weight: bold;">I</span> (Initiator)</li>
<li><span style="font-weight: bold;">R</span> (Responder)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>restrict_processing_on_state (-rpos)</p>
<p><span style="font-style: italic;font-weight: bold;">Transfer state</span></p>         </td>
         <td><p>Rule Tables</p>
<p>Restricts processing to Transfers of the specified state</p>         </td>
         <td><p>One of the following values:</p>
<ul>
<li><span style="font-weight: bold;">E</span> (Ended)</li>
<li><span style="font-weight: bold;">C</span> (Canceled)</li>
<li><span style="font-weight: bold;">A</span> (Acknowledged)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>restrict_processing_on_type (-rpot)</p>
<p><span style="font-style: italic;font-weight: bold;">Transfer type</span></p>         </td>
         <td><p>Rule Tables</p>
<p>Restricts processing to Transfers of the specified type</p>         </td>
         <td><p>One of the following values:</p>
<ul>
<li><strong>TRANS</strong></li>
<li><strong>POLL</strong></li>
<li><strong>LOTS</strong></li>
<li><strong>LIST</strong></li>
<li><strong>EERP</strong></li>
<li><strong>DIR</strong></li>
<li><strong>SELECT</strong></li>
<li><strong>MSG</strong></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>restrict_processing_on_protocol (-rpot)</p>
<p><span style="font-style: italic;font-weight: bold;">Transfer protocol</span></p>         </td>
         <td><p>Rule Tables</p>
<p>Restricts processing to Transfers of the specified protocol(s)</p>         </td>
         <td><p>One of the following values:</p>
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
<li><p>AS1_SMTP</p></li>
<li><p>RN_HTTP</p></li>
<li><p>RN_POP3</p></li>
<li><p>RN_SMTP</p></li>
<li><p>SWIFTNET</p></li>
<li><p>JMS</p></li>
<li><p>X420</p></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>temporal_event_model (-tem)</p>         </td>
         <td><p>Temporal event model with the specific syntax</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>type_of_decisionrules (-type)</p>         </td>
         <td><p>Selects type of Decision Rules</p>         </td>
         <td><p>One of the following values:</p>
<ul>
<li><strong>XFER_CHANGE_STATE</strong></li>
<li><strong>TEMPORAL</strong></li>
<li><strong>FILE_STORING</strong></li>
<li><strong>XMS</strong></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>type_of_rules_table (-type)</p>         </td>
         <td><p>Selects type of Rule Table</p>         </td>
         <td><p>One of the following values:</p>
<ul>
<li><strong>XFER_CHANGE_STATE</strong></li>
<li><strong>TEMPORAL</strong></li>
<li><strong>FILE_STORING</strong></li>
<li><strong>XMS</strong></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>update_cond (-u)</p>         </td>
         <td><p>Update one or more conditions for the Decision Rule</p>         </td>
         <td><p>Condition expression that comprises:</p>
<ul>
<li>argument name</li>
<li>operator</li>
<li>value</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>watched_directory (-watchdir)</p>
<p>Watch directory</p>         </td>
         <td><p>Defines the watched directory</p>         </td>
         <td><p>String</p>         </td>
      </tr>
      <tr>
         <td><p>watch_period (-wp)</p>
<p>Watch period</p>         </td>
         <td><p>Defines the watch period</p>         </td>
         <td><p>Positive integer</p>         </td>
      </tr>
      <tr>
         <td><p>work_directory (-workdir)</p>
<p>Work directory</p>         </td>
         <td><p>Defines the work directory</p>         </td>
         <td><p>String</p>         </td>
      </tr>
      <tr>
         <td><p>xms_connector_name (-xcn)</p>         </td>
         <td><p>Name of Axway Messaging connector</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>mail_xpriority<br />
(-mailxprio)</p>         </td>
         <td><p>SMTP protocol only (with or without S/MIME) - the value for X-Priority mail header (SEPAmail standard)</p>         </td>
         <td><p>Integer, between <span style="font-weight: bold;">1</span> and <span style="font-weight: bold;">5</span></p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Command syntax for Scheduling Event Models](../scheduling_event_model_command_syntax) (date syntax)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
