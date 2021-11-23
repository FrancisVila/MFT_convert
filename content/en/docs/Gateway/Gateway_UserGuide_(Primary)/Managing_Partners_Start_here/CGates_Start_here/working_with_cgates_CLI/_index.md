{
    "title": "Command line operations",
    "linkTitle": "Command line operations",
    "weight": "220"
}{{< Gateway/componentlongname  >}}: Managing Partners

## Working with CGates (command line)

[`peladm create_cgate`](#peladm_create_cgate)

[`peladm delete_cgate`](#peladm_delete_cgate)

[`peladm update_cgate`](#peladm_update_cgate)

[`peldsp select_cgate`](#peldsp_select_cgate)

[`peldsp display_cgate`](#peldsp_display_cgate)

<span id="peladm_create_cgate"></span>

### Creating a CGate: peladm create\_cgate

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p>peladm create_cgate {-name} {-parent_group} [<em>optional parameters</em>]</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to create a new CGate object and set its attributes. A CGate object must be linked to an existing CGateGroup object. Otherwise, the CGate object creation fails.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><em>Mandatory</em></p>
<p><code>-name (-n)</code>: Enter a unique identifying name for the CGate you are creating.</p>         </td>
      </tr>
      <tr>
         <td><p><em>Mandatory</em></p>
<p><code>-parent_group (-pg)</code>: Enter the name of the CGateGroup in which the new CGate is to be included.</p>         </td>
      </tr>
      <tr>
         <td><p>Optional parameters:</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following  command creates a new CGate called <em>TEST</em> that belongs to CGateGroup <em>GROUP</em>. It has a user parameter with three values: g1, g2 and g3 and two VFD rights definitions:</p>
<p>peladm create_cgate</p>
<p>-n TEST</p>
<p>-pg GROUP</p>
<p>-user_param1 "g1, g2, g3"</p>
<p>-vfd_right "/::RW:LC:N ;/ftp:*.*:RW:L:Y"</p>
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

<span id="peladm_update_cgate"></span>

### Modifying a CGate: peladm update\_cgate

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p>peladm update_cgate {-name} [<em>optional parameters</em>]</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to modify and update the attributes of a CGate object.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><em>Mandatory</em></p>
<p><code>-name (-n)</code>: Enter a unique identifying name for the CGate you are modifying.</p>         </td>
      </tr>
      <tr>
         <td><p>Optional parameters:</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following command updates the CGate <em>TEST</em>. The home directory is <code>/upload/</code> and the root directory is <code>/upload</code>. The command removes the first and second VFD rights definitions and adds the following new VFD rights definitions:</p>
<ul>
<li>VFD directory path: /upload/</li>
<li>file pattern: ""</li>
<li>file rights: Read and Write</li>
<li>directory rights: List</li>
<li>sub-directory inheritance: Yes</li>
</ul>
<p>peladm update_cgate</p>
<p>-n TEST</p>
<p>-del_vfd_right "1; 2"</p>
<p>-add_vfd_right "/upload/::RW:L:Y"</p>
<p>-home_dir "/upload/"</p>
<p>-root_dir "/upload"</p>         </td>
      </tr>
   </tbody>
</table>

<span id="peladm_delete_cgate"></span>

### Deleting a CGate: peladm delete\_cgate

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p>peladm delete_cgate {-name} [<em>optional parameters</em>]</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to delete a CGate object.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><em>Mandatory</em></p>
<p><code>-name (-n)</code>: Enter a unique identifying name for the CGate you are deleting.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following  command deletes the CGate <em>TEST</em>.</p>
<p>peladm delete_cgate</p>
<p>-n TEST</p>         </td>
      </tr>
   </tbody>
</table>

<span id="peldsp_select_cgate"></span>

### Selecting CGates: peldsp select\_cgate

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><code style="font-weight: bold;">peldsp select_cgate [-name] [-parent_group] [-protocol] [-state] [-calling_addr] [-recursive_mode]</code></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to select and display all CGate objects that match the criteria that you specify as parameters.</p>
<p>To list all CGate objects, run the command with no parameters. You can then use the optional parameters to refine the search.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><code>-name (-n)</code>: Enter  a name as selection criteria for the display of CGates.</p>         </td>
      </tr>
      <tr>
         <td><p><code>-parent_group (-pg)</code>: Enter the name of the CGateGroup in which the new CGate is to be included.</p>         </td>
      </tr>
      <tr>
         <td><p><code>-recursive mode (-rm)</code>: Flag indicating whether to apply the selection only to the CGate objects directly linked to the provided CGateGroup, or recursively to the whole hierarchy under the provided CGateGroup.</p>
<p>Enter one of the values:</p>
<ul>
<li><strong>Y</strong> (yes)</li>
<li><span style="font-weight: bold;">N</span> (no)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><code>protocol</code> (<code>-pr</code>): one of the following values:</p>
<ul>
<li><span style="font-weight: bold;">FTP</span> = FTP</li>
<li><span style="font-weight: bold;">HTTP</span> = HTTP</li>
<li><span style="font-weight: bold;">FTP_HTTP</span> = FTP+HTTP</li>
<li><span style="font-weight: bold;">PHSE</span> = PeSIT HS E</li>
<li><span style="font-weight: bold;">PHSD</span> = PeSIT HS D</li>
<li><span style="font-weight: bold;">ODETTE</span> = OFTP</li>
<li><span style="font-weight: bold;">PEL</span> = PEL</li>
<li><span style="font-weight: bold;">AS2</span></li>
<li><span style="font-weight: bold;">AS3</span></li>
<li><span style="font-weight: bold;">SFTP</span></li>
<li>RN_HTTP</li>
<li><span style="font-weight: bold;">*</span> = undefined</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><code>state </code>(<code>-s</code>) : Enter the state,
possible values:</p>
<ul>
<li><strong>E</strong> = Enabled</li>
<li><strong>D</strong> = Disabled</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><code>calling_addr </code>(<code>-cinga</code>): Enter a Calling Address Control definition.
A Calling Address definition follows the syntax:</p>
<p>“calling_address_pattern”:”authorization”</p>
<ul>
<li><em>calling_address_pattern</em>: Up to 31 alphanumeric characters, including wildcards</li>
<li><em>authorization</em>: enumerated [ A (allowed) | D (denied) ]</li>
</ul>
<p>Only one Calling Address Control definition can be specified.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following command selects and displays CGates whose names begin with F and that belong to the parent CGateGroup GR_TEST. Recursive mode is set to Yes to apply the selection recursively to the CGate sub-tree behind the CGateGroup GR_TEST.</p>
<p>peldsp select_cgate</p>
<p>-name F*</p>
<p>-parent_group GR_TEST</p>
<p>-recursive_mode Y</p>         </td>
      </tr>
   </tbody>
</table>

<span id="peldsp_display_cgate"></span>

### Displaying a CGate: peldsp display\_cgate

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p>peldsp display_cgate {-name}</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to display the attributes of a CGate that you identify by its name.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span style="font-style: italic;">Mandatory</span></p>
<p><span class="code">-name (-n)</span>: Enter a name as selection criteria for the display of CGates.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>Gateway returns a display of each parameter associated with the specified CGate object on one line in the form:</p>
<p>name_of_field(_optional counter)="value"</p>
<p>For example:</p>
<p>cg_file_rights_1='RW'</p>
<p>Each field name is prefixed with the string "<span class="code" style="font-weight: bold;">cg_</span>", related to the <span style="font-weight: bold;">CG</span>ate object.</p>
<p>Gateway displays an optional counter field when you display fields that have multiple instances within a single CGate object. This property applies to VFD Rights, User Parameter 1 and 2 and the Calling Address Control.</p>
<p>When, for example you enter the command:</p>
<p>peldsp display_cgate  -n TEST</p>
<p>Gateway may return information similar to the following:</p>
<p>cg_name='TEST'</p>
<p>cg_comments=''</p>
<p>cg_state='E'</p>
<p>cg_parent_group='GROUP'</p>
<p>cg_login_user='*'</p>
<p>cg_login_password=''</p>
<p>cg_change_password_option='N'</p>
<p>cg_client_ident='*'</p>
<p>cg_client_password=''</p>
<p>cg_server_ident='*'</p>
<p>cg_tls_sprof=''</p>
<p>cg_tls_client_auth='N'</p>
<p>cg_tls_sprof_user_param=''</p>
<p>cg_root_dir=''</p>
<p>cg_home_dir=''</p>
<p>cg_http_home_page=''</p>
<p>cg_http_list_template=''</p>
<p>cg_server_password=''</p>
<p>cg_user_param1_1='g1'</p>
<p>cg_user_param1_2='g2'</p>
<p>cg_user_param1_3='g3'</p>
<p>cg_rights_nb='2'</p>
<p>cg_path_1='/'</p>
<p>cg_file_pattern_1=''</p>
<p>cg_subdir_inheritance_1='N'</p>
<p>cg_file_rights_1='RW'</p>
<p>cg_dir_rights_1='LC'</p>
<p>cg_path_2='/ftp'</p>
<p>cg_file_pattern_2='*.*'</p>
<p>cg_subdir_inheritance_2='Y'</p>
<p>cg_file_rights_2='RW'</p>
<p>cg_dir_rights_2='L'</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[CGates and CGateGroups: Parameters List](cgates_parameter_list)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
