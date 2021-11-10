{
    "title": "New Rule Table: General tab",
    "linkTitle": "Rule Table tabs",
    "weight": "170"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Events

When you create a Rule Table, Gateway displays the <span style="font-weight: bold;">General</span> tab in the <span style="font-style: italic;">New Rule Table</span> window.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Element         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Name</p>         </td>
         <td><p>Enter a unique name for the new Rule Table.</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>You cannot modify this field.</p>
<p>This field displays the Rule Table type.</p>         </td>
      </tr>
      <tr>
         <td><p>Comments</p>         </td>
         <td><p>Optional</p>
<p>Enter a free-text description for the Rule Table.<br />
Maximum: 80 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Active</p>         </td>
         <td><p>Select this option to set the Rule Table to <span style="font-style: italic;">active</span> status.</p>         </td>
      </tr>
      <tr>
         <td><p>Exclusive table</p>         </td>
         <td><p><span style="font-style: italic;">Not for Transfer Change State Rule Tables</span>.</p>
<p>By default, Gateway analyzes the Decision Rules in a Rule Table in their listed order, stopping at the first Rule that matches a complete set of conditions.</p>
<ul>
<li><span style="font-weight: bold;">Select</span> this option, if you want Gateway to stop the analysis of the table list after processing the first Rule that matches a complete set of conditions (default).</li>
<li><span style="font-weight: bold;">Disable</span> this option if you want Gateway to continue analyzing the table list after processing a matching Rule. This enables you to execute more than one task on the occurrence of a single event.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Exit called</p>         </td>
         <td><p>Some Rule Tables are inherently associated with exit processes that are automatically called during Rule processing.</p>
<p>Select this option to disable all exits inherent in Rule processing.</p>         </td>
      </tr>
      <tr>
         <td><p><span id="Default_exec_type"></span>Default execution type</p>         </td>
         <td><p>The default execution type to apply to an event if no defined Decision Rule matches the current parameters.</p>
<p>Select one of the following:</p>
<ul>
<li><span style="font-weight: bold;">Model</span>: Redirect the Transfer to another transfer whose parameters are defined in a Transfer Model.<br />
If you select this option, you must complete the <span style="font-weight: bold;">Model name</span> field. Additionally, it is recommended that you select the <span style="font-weight: bold;">Link input and output transfers</span> option.</li>
<li><span style="font-weight: bold;">XIB</span> (<span style="font-style: italic;">only for Scheduling-type Rule Tables and Transfer Change State Rule Tables</span>): Redirect the Transfer to AMTrix/ Axway Integrator for processing. The payload file for a Transfer which was routed to Integrator is not deleted by the purge operation. For more information, refer to <a href="../../connectors_about/integrator_about/integrator_connector#Purging">Purging for transfers routed from Gateway to Integrator</a>.</li>
<li><span style="font-weight: bold;">To XMS</span>: Redirect the Transfer to an Axway Messaging server queue via an Axway Messaging connector.</li>
<li><span style="font-weight: bold;">Mailbox cleaning</span> (<span style="font-style: italic;">only for Scheduling-type Rule Tables</span>): Clean the Mailbox via an associated Purge Model.</li>
<li><span style="font-weight: bold;">Perl Script</span>: Apply a Perl script.</li>
<li><span style="font-weight: bold;">Batch command</span>: Execute a batch command or script.</li>
<li><span style="font-weight: bold;">No action</span>: Implement no routing.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Model name</p>         </td>
         <td><p>This field is displayed if you select <span style="font-style: italic;">Model or To XMS</span> in <span style="font-weight: bold;">Default execution type</span>.</p>
<p>Enter the name of the Model to apply or select a Model from the drop-down list. The Model name must correspond to a General Model.</p>         </td>
      </tr>
      <tr>
         <td><p>XMS connector out</p>         </td>
         <td><p>This field is displayed if you select <span style="font-style: italic;">To XMS</span> in <span style="font-weight: bold;">Default execution type</span>.</p>
<p>Enter the name of the Axway Messaging out connector that handles the Transfer.</p>         </td>
      </tr>
      <tr>
         <td><p>Link input and output transfers</p>         </td>
         <td><p>Not for all types of Rule Table.</p>
<p>This field is displayed if you select <span style="font-style: italic;">Model</span> in <span style="font-weight: bold;">Default execution type</span>.</p>
<p>Select this option to create a logical link between the incoming and the outgoing Transfers.</p>         </td>
      </tr>
      <tr>
         <td><p>Purge Model</p>         </td>
         <td><p>This field is displayed if you select <span style="font-style: italic;">Mailbox cleaning</span> in <span style="font-weight: bold;">Default execution type</span>.</p>
<p>Select the Purge Model you want to apply for the purge operation.</p>         </td>
      </tr>
      <tr>
         <td><p>Perl script</p>         </td>
         <td><p>This field is displayed if you select <span style="font-style: italic;">Perl Script</span> in <span style="font-weight: bold;">Default execution type</span>.</p>
<p>Enter the script to apply to the current Transfer.<br />
</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Batch command</span></p>         </td>
         <td><p>This field is displayed if you select <span style="font-style: italic;">Batch command</span> in <span style="font-weight: bold;">Default execution type</span>.</p>
<p>Enter the command to apply to the current Transfer.<br />
Alternatively, enter the path and file name of the script to execute.</p>
<p>Refer to <a href="../working_with_decision_rules_cli/decision_rules_executing_scripts">Executing scripts as command lines from Decision Rules</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>Log level</p>         </td>
         <td><p>Select one of the following:</p>
<ul>
<li><span style="font-weight: bold;">No log</span>: no log recording</li>
<li><span style="font-weight: bold;">Short</span>: normal log recording</li>
<li><span style="font-weight: bold;">Full</span>: detailed log recording</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Working with Rule Tables and Decision Rules](../working_with_rule_tables_and_decision_rules(gui))

[Defining Decision Rule conditions](../defining_decision_rule_conditions)

[Decision Rules and Rule Tables: Parameters List](../working_with_decision_rules_cli/decision_rules_rule_tables_parameter_list)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
