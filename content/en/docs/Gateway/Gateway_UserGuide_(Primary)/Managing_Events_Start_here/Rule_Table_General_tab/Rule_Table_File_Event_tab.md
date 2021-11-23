{
    "title": "New Rule Table: File Event tab",
    "linkTitle": "File Event tab",
    "weight": "210"
}{{< Gateway/componentlongname  >}}: Managing Events

When you create a Directory Scanning type Rule Table, Gateway displays the **File Event** tab in the <span style="font-style: italic;">New Rule Table</span> window.

Use the <span style="font-weight: bold;">File Event</span> tab to specify the file that Gateway supervises for file triggering events.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Element         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><span id="Watch_directory"></span>Watch directory</p>         </td>
         <td><p>Enter the path to the directory you want Gateway to supervise (or poll) to determine the presence of a file.</p>         </td>
      </tr>
      <tr>
         <td><p>Watch period</p>         </td>
         <td><p>Enter the time cycle (in seconds) in which you want polling to reoccur.</p>         </td>
      </tr>
      <tr>
         <td><p><span id="Work directory"></span>Work directory</p>         </td>
         <td><p>Enter the path to the work directory.</p>
<p>When Gateway polls the <span style="font-weight: bold;">Watch Directory</span> and locates a file, it transfers the file to the Work directory before beginning file processing.</p>         </td>
      </tr>
      <tr>
         <td><p>Optimized cleaning</p>         </td>
         <td><p>Select this option to enable Gateway to periodically delete a part of the contents of the <span style="font-weight: bold;">Work Directory</span> contents.</p>
<p>The Optimized cleaning function includes security controls to avoid deletion of critical files. However, in cases of extremely sensitive files, it is prudent to avoid activating this option.</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Working with Rule Tables and Decision Rules](../../working_with_rule_tables_and_decision_rules(gui))

[Defining Decision Rule conditions](../../defining_decision_rule_conditions)

[Decision Rules and Rule Tables: Parameters List](../../working_with_decision_rules_cli/decision_rules_rule_tables_parameter_list)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
