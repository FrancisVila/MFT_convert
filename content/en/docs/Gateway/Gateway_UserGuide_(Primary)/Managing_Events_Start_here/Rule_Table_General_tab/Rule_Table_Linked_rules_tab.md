{
    "title": "New Rule Table: Linked rules tab",
    "linkTitle": "Linked rules tab",
    "weight": "180"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Events

When you create any of the four types of Rule Table, Gateway displays the <span style="font-weight: bold;">Linked rules</span> tab in the <span style="font-style: italic;">New Rule Table</span> window.

Use the <span style="font-weight: bold;">Linked rules</span> tab to add or remove [Decision Rules from the Rule Table](../../working_with_decision_rules_cli/decision_rules_rule_tables_parameter_list), and to manage the order in which Gateway analyzes the Decision Rules.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Element         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Linked Rules</p>         </td>
         <td><p>This frame contains the list of Decision Rules for inclusion in the Rule Table.</p>
<p>Select the Decision Rules you want to include from the <span style="font-style: italic;">Available Rules</span> frame.</p>         </td>
      </tr>
      <tr>
         <td><p>View rule</p>         </td>
         <td><p>This button appears when you select a Decision Rule in either the <span style="font-style: italic;">Available Rules</span> frame or the <span style="font-style: italic;">Linked Rules</span> frame.</p>
<p>Click this button to view information about the selected rule.</p>         </td>
      </tr>
      <tr>
         <td><p>Link</p>         </td>
         <td><p>Select a Decision Rule in the <span style="font-style: italic;">Available Rules</span> frame, then click the <span style="font-weight: bold;">Link</span> button.<br />
Gateway removes the Decision Rule from the <span style="font-style: italic;">Available Rules</span> frame (linking it to the Rule Table), and places it in the <span style="font-style: italic;">Linked Rules</span> frame.</p>         </td>
      </tr>
      <tr>
         <td><p>Unlink</p>         </td>
         <td><p>Select a Decision Rule in the <span style="font-style: italic;">Linked Rules</span> frame, then click the <span style="font-weight: bold;">Unlink</span> button.<br />
Gateway removes the Decision Rule from the <span style="font-style: italic;">Linked Rules</span> frame (unlinking it from the Rule Table), and places it in the <span style="font-style: italic;">Available Rules</span> frame.</p>         </td>
      </tr>
      <tr>
         <td><p>Up and down arrows</p>         </td>
         <td><p>These buttons are active when you select a Decision Rule in the <span style="font-style: italic;">Linked Rules</span> frame.</p>
<p>Use these buttons to modify the position of the selected Decision Rule in the list.</p>
<p>The list order determines the priority in which Gateway analyzes Decision Rules for conditional matching.</p>         </td>
      </tr>
      <tr>
         <td><p>Available Rules</p>         </td>
         <td><p>This frame displays all Decision Rules that are available for linking to the Rule Table.</p>
<p>Click any Decision Rule listed in this frame to select it. Then use the <span style="font-weight: bold;">View rule</span> and/or <span style="font-weight: bold;">Link</span> buttons as described above.</p>         </td>
      </tr>
      <tr>
         <td><p>Selected rule</p>         </td>
         <td><p>This display bar displays the name of the Decision Rule you select in the <span style="font-style: italic;">Linked Rules</span> or <span style="font-style: italic;">Available Rules</span> frame.</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Working with Rule Tables and Decision Rules](../../working_with_rule_tables_and_decision_rules(gui))

[Defining Decision Rule conditions](../../defining_decision_rule_conditions)

[Decision Rules and Rule Tables: Parameters List](../../working_with_decision_rules_cli/decision_rules_rule_tables_parameter_list)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
