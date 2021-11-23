{
    "title": "New Rule Table: Event tab",
    "linkTitle": "Event tab",
    "weight": "220"
}{{< Gateway/componentlongname  >}}: Managing Events

When you create a Transfer Change State type Rule Table, Gateway displays the **Event** tab in the <span style="font-style: italic;">New Rule Table</span> window.

Use the <span style="font-weight: bold;">Event</span> tab to restrict processing to a limited set of Transfers, depending on conditions you specify.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Element         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Restrict processing</p>         </td>
         <td><p>Select this check box if you want to create restriction criteria for the application of transfer Decision Rules.</p>
<p>When you select this box, Gateway activates the criteria text boxes below.</p>         </td>
      </tr>
      <tr>
         <td><p>Transfer state</p>         </td>
         <td><p>Enter one or more transfer states for which you want to allow processing.</p>
<p>For example: <span style="font-weight: bold;">ENDED</span>, <span style="font-weight: bold;">ACKED</span>, ...</p>         </td>
      </tr>
      <tr>
         <td><p>Transfer mode</p>         </td>
         <td><p>Enter the mode for which you want to allow processing:</p>
<ul>
<li><span style="font-weight: bold;">Responder</span> or</li>
<li>Initiator</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Transfer direction</p>         </td>
         <td><p>Enter the Transfer direction for which you want to allow processing:</p>
<ul>
<li>IN<span style="font-weight: normal;"> or</span></li>
<li>OUT</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Transfer type</p>         </td>
         <td><p>Enter one or more transfer types for which you want to allow processing.</p>
<p>For example: <span style="font-weight: bold;">MSG</span>, <span style="font-weight: bold;">TRANS</span>, ...</p>         </td>
      </tr>
      <tr>
         <td><strong>Transfer protocol</strong>         </td>
         <td>Enter one or more transfer protocols for which you want to allow processing.
For example: <strong>PEL, ODETTE, PHSE...</strong>         </td>
      </tr>
   </tbody>
</table>

> **Note:**
>
> Multiple values for a condition must be separated by a comma with no space between them.

Related topics

[Working with Rule Tables and Decision Rules](../../working_with_rule_tables_and_decision_rules(gui))

[Defining Decision Rule conditions](../../defining_decision_rule_conditions)

[Decision Rules and Rule Tables: Parameters List](../../working_with_decision_rules_cli/decision_rules_rule_tables_parameter_list)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
