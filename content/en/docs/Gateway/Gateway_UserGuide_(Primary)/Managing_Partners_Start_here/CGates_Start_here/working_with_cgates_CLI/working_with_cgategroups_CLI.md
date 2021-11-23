{
    "title": "Working with CGateGroups (command line)",
    "linkTitle": "Working with CGateGroups",
    "weight": "240"
}{{< Gateway/componentlongname  >}}: Managing Partners

[`peladm create_cgategroup`](#peladm_create_cgategroup)

[`peladm delete_cgategroup`](#peladm_delete_cgategroup)

[`peladm update_cgategroup`](#peladm_update_cgategroup)

[`peldsp select_cgategroup`](#peldsp_select_cgategroup)

[`peldsp display_cgategroup`](#peldsp_display_cgategroup)

<span id="peladm_create_cgategroup"></span>

## Creating a CGateGroup: peladm create\_cgategroup

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p>peladm create_cgategroup {-name} [<em>optional parameters</em>]</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to create a new CGateGroup object and set its attributes. A CGateGroup is optionally linked as a child object to an existing CGateGroup object. Otherwise, it is considered to be the root CGateGroup.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>Mandatory</p>
<p><code>-name (-n)</code>: Enter a unique identifying name for the CGateGroup you are creating.</p>         </td>
      </tr>
      <tr>
         <td><p>Optional parameters:</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following command creates a new FTP CGateGroup object named <em>TEST</em>. Since the new CGateGroup has no parent group, it is a root CGateGroup.</p>
<p>peladm create_cgategroup</p>
<p>-n GR_TEST</p>
<p>-protocol FTP</p>
<p>-template_site TFTP</p>
<p>-sap "*"</p>
<p>-user_param1 "g1, g2, g3"</p>
<p>-vfd_right "/::RW:LC:N ;/ftp:*.*:RW:L:Y"</p>
<p>The created CGateGroup is valid regardless of the called SAP (sap = "*"). It has a user parameter 1 with three values ("g1", "g2", "g3") and the following two VFD rights definitions:</p>
<p>vfd_dir_path = "/"</p>
<p>file_pattern = ""</p>
<p>file_rights = "RW" (Read, Write)</p>
<p>directory_rights = "LC" (List, Create)</p>
<p>subdirectory_inheritence = "N" (No)</p>
<p>vfd_dir_path = "/ftp"</p>
<p>file_pattern = "*.*"</p>
<p>file_rights = "RW" (Read, Write)</p>
<p>directory_rights = "L" (List)</p>
<p>subdirectory_inheritence = "Y" (Yes)</p>         </td>
      </tr>
   </tbody>
</table>

<span id="peladm_update_cgategroup"></span>

## Modifying a CGateGroup: peladm update\_cgategroup

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p>peladm update_cgategroup {-name} [<em>optional parameters</em>]</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to modify and update a CGateGroup object.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>Mandatory</p>
<p><code>-name (-n)</code>: Enter a unique identifying name for the CGateGroup you are modifying.</p>         </td>
      </tr>
      <tr>
         <td><p>Optional parameters:</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following command updates the CGateGroup object <em>GR_TEST</em>, assigning <code>root_dir</code> and <code>home_dir</code> parameters.</p>
<p>peladm update_cgategroup</p>
<p>-n GR_TEST</p>
<p>-home_dir "/upload/"</p>
<p>-root_dir "/upload"</p>         </td>
      </tr>
   </tbody>
</table>

<span id="peladm_delete_cgategroup"></span>

## Deleting a CGateGroup: peladm delete\_cgategroup

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p>peladm delete_cgate {-name} [<em>optional parameters</em>]</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to delete a CGateGroup object that you specify by name. Note that the CGateGroup must be empty, (contain no CGates or child CGateGroups), before you can delete it.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><em>Mandatory</em></p>
<p><code>-name (-n)</code>: Enter a unique identifying name for the CGateGroup you are deleting.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following command deletes the CGateGroup object "GR_TEST".</p>
<p>peladm delete_cgategroup</p>
<p>-n GR_TEST</p>         </td>
      </tr>
   </tbody>
</table>

<span id="peldsp_select_cgategroup"></span>

## Selecting CGateGroups: peldsp select\_cgategroup

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p>peldsp select_cgategroup [] [] []</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to select CGateGroup objects that match the criteria entered as parameters.</p>
<p>To list all CGateGroups, run the command with no parameters. You can then use the optional parameters to refine the search.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><code>-name (-n)</code>: Enter a name as selection criteria for the display of CGatesGroups.</p>
<p>This parameter can contain wildcard characters ("?" or "*").</p>         </td>
      </tr>
      <tr>
         <td><p>Mandatory</p>
<p><code>-parent_group (-pg)</code>: Enter the name of the CGateGroup in which the new CGate is to be included.</p>         </td>
      </tr>
      <tr>
         <td><p><code>-recursive mode (-rm)</code>: Flag indicating whether to apply the selection only to the CGateGroup objects directly linked to the provided CGateGroup, or recursively to the whole hierarchy under the provided CGateGroup.</p>
<p>Enter one of the values:</p>
<ul>
<li><strong>Y</strong> (yes)</li>
<li><span style="font-weight: bold;">N</span> (no)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following command selects and displays CGatesGroups whose names begin with <span style="font-style: italic;">G</span> and that belong to the parent CGateGroup <span style="font-style: italic;">GR_TEST</span>. Recursive mode is set to Yes to apply the selection recursively to the CGateGroup sub-tree behind the CGateGroup GR_TEST.</p>
<p>peldsp select_cgateGroup</p>
<p>-name G?_TEST</p>
<p>-parent_group GR_TEST</p>
<p>-recursive_mode Y</p>
<p>G1_TEST</p>
<p>G2_TEST</p>
<p>G3_TEST</p>         </td>
      </tr>
   </tbody>
</table>

<span id="peldsp_display_cgategroup"></span>

## Displaying a CGateGroup: peldsp display\_cgategroup

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p>peldsp display_cgategroup {-name}</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to display the properties of a CGateGroup that you specify by name.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span style="font-style: italic;">Mandatory</span></p>
<p><span class="code">-name (-n)</span>: Enter a name as selection criteria for the display of CGatesGroups.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>Gateway returns a display of each parameter associated with the specified CGateGroup object. Gateway displays the results on the user screen in the format displayed on one line in the form.</p>
<p>name_of_field(_optional counter)="value"</p>
<p>For example:</p>
<p>cgg_file_rights_1='RW'</p>
<p>Each field name is prefixed with the string <span class="code">cgg_</span>, related to the CGate object.</p>
<p>Gateway displays an optional counter field when you display fields that have multiple instances within a single CGateGroup object. This property applies to VFD Rights, User Parameter 1 and 2 and the Calling Address Control.</p>
<p>When, for example you enter the command:</p>
<p>peldsp display_cgategroup -n GR_B</p>
<p>Gateway returns information similar to the following:</p>
<p>peldsp display_cgategroup -n GR_B</p>
<p>cgg_name='GR_B'</p>
<p>cgg_comments='10'</p>
<p>cgg_state='U'</p>
<p>cgg_parent_group='GR_A'</p>
<p>cgg_protocol='*'</p>
<p>cgg_sap=''</p>
<p>cgg_called_addr=''</p>
<p>cgg_http_host_name=''</p>
<p>cgg_root_dir=''</p>
<p>cgg_home_dir=''</p>
<p>cgg_http_home_page=''</p>
<p>cgg_http_list_template=''</p>
<p>cgg_template_site=''</p>
<p>cgg_rights_nb='0'</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[CGates and CGateGroups: Parameters List](../cgates_parameter_list)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
