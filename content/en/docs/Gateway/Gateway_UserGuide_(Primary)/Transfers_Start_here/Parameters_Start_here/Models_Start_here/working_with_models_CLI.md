{
    "title": " ",
    "linkTitle": "Command line operations",
    "weight": "220"
}{{< Gateway/componentlongname  >}}: Managing Transfers

# Command line operations

## Working with models (command line)

`peladm create_model`

`peladm update_model`

`peladm delete_model`

`peladm check_model`

`peldsp display_model`

`peldsp select_model`

<span id="peladm_create_model"></span>

### Creating a model: peladm create\_model

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p>peladm create_model {-model} [<em>optional parameters</em>]</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to create a Model.</p>
<p>Each Model is uniquely defined by the following two attributes:</p>
<ul>
<li>-model (-ml)</li>
<li>-protocol (-pr)</li>
</ul>
<p>For XMS-type Models:</p>
<p>To create an XMS-type Model for transfers <strong>to Gateway</strong> from an Axway Messaging server, use the following parameters:</p>
<ul>
<li>-model (-ml)</li>
<li><span class="code">-protocol (-pr)</span>: Enter the value <span style="font-weight: bold;">to_gtw</span></li>
<li>-prop_list_name (-pln)</li>
<li>-appli (-app)</li>
<li>one or more attributes necessary to enable Gateway to reroute the message to the destination application</li>
</ul>
<p>To create an XMS-type Model for transfers <span style="font-weight: bold;">from Gateway</span> to an Axway Messaging server, use only the following parameters:</p>
<ul>
<li>-model (-ml)</li>
<li><span class="code">-protocol (-pr)</span>: Enter the value <span style="font-weight: bold;">from_gtw</span></li>
<li>-prop_list_name (-pln)</li>
<li>-add_map (-am)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span class="code">-model (-ml)</span>: Enter the name of the Model.</p>
<p>(max 25 characters)</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-style: italic;">Optional parameters:</span> Refer to <a href="../model_object_parameter_list">Model objects: Parameters List</a></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example 1</strong></p>         </td>
         <td><p>The following example creates a General Model named MODELA.</p>
<p>   peladm create_model  -ml MODELA</p>
<p>   -pr GENERAL</p>
<p>   -dest_alias TPHSE</p>
<p>   -appli DEFAULT_B</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example 2</strong></p>         </td>
         <td><p>The following example creates an XMS-type Model for a transfer from an Axway Messaging server towards Gateway.</p>
<p>   peladm create_model  -ml XMStoGTW</p>
<p>   -pr to_gtw</p>
<p><span class="code" style="font-weight: bold;">   -pln plist</span></p>
<p>   -appli &amp;(application)</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example 3</strong></p>         </td>
         <td><p>The following example creates an XMS-type Model for a transfer from Gateway towards an Axway Messaging server. The <span class="code" style="font-weight: bold;">add_map</span> parameter directs Gateway to retrieve <span style="font-style: italic;">appli</span> and <span style="font-style: italic;">originator</span> values from the current transfer to use as <span style="font-style: italic;">application</span> and <span style="font-style: italic;">server</span> values of the proplist. The <span class="code" style="font-weight: bold;">add-map</span> parameter also sets the <span class="code">cost</span> parameter of the properties list to the value 2000.</p>
<p>   peladm create_model  -ml GTWtoXMS</p>
<p>   -pr from_gtw</p>
<p><span class="code" style="font-weight: bold;">   -pln plist</span></p>
<p>   -add_map "application=&amp;(appli);cost=2000;server=&amp;(originator)"</p>         </td>
      </tr>
   </tbody>
</table>

<span id="peladm_update_model"></span>

### Modifying a Model: peladm update\_model

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p>peladm update_model {-model} [<span style="font-weight: normal;font-style: italic;">optional parameters</span>]</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to modify an existing Model.</p>
<p>If you update a Model using a parameter without a value, the command deletes the last parameter value.</p>
<p>Enter the Model name and Model protocol as parameters, followed by all the fields you want to modify. The default Model protocol is GENERAL.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span class="code">-model (-ml)</span>: Enter the name of the existing model you want to modify.</p>         </td>
      </tr>
      <tr>
         <td><p>Optional parameters: <span style="font-style: normal;">Refer to <a href="../model_object_parameter_list">Model objects: Parameters List</a>.</span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following example modifies the Application object used by a General Model named MODELA.</p>
<p>   peladm update_model  -ml MODELA</p>
<p>   -pr GENERAL</p>
<p>   -appli DEFAULT_A</p>         </td>
      </tr>
   </tbody>
</table>

<span id="peladm_delete_model"></span>

### Deleting a model: peladm delete\_model

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p>peladm delete_model {-model} [-protocol] [<span style="font-weight: normal;font-style: italic;">optional parameters</span>]</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to delete a Model. Since you can create a General Model and a protocol Model with the same name, you should specify both the name and protocol of the Model that you want to delete.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span class="code">-model (-ml)</span>: Enter the name of the existing Model that you want to delete.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-style: normal;font-family: monospace;">-protocol (-pr)</span>: Enter the name of the protocol of the Model that you want to delete. Enter one of the following values:</p>
<ul>
<li><span style="font-weight: bold;">GENERAL</span> (default)</li>
<li><span style="font-weight: bold;">PHSE</span> = PeSIT HS E</li>
<li><span style="font-weight: bold;">PHSD</span> = PeSIT HS D</li>
<li><span style="font-weight: bold;">PEL</span></li>
<li><span style="font-weight: bold;">FTP</span></li>
<li><span style="font-weight: bold;">HTTP</span></li>
<li><span style="font-weight: bold;">ODETTE</span> = OFTP</li>
<li><span style="font-weight: bold;">SFTP</span></li>
<li><span style="font-weight: bold;">SMTP</span></li>
<li><span style="font-weight: bold;">POP3</span></li>
<li>POP3</li>
<li>TO_GTW</li>
<li>FROM_GTW</li>
<li>AS2</li>
<li>AS3</li>
<li>AS1_POP3</li>
<li>AS1_SMTP</li>
<li>RN_POP3</li>
<li>RN_SMTP</li>
<li>RN_HTTP</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Optional parameters: <span style="font-style: normal;">Refer to <a href="../model_object_parameter_list">Model objects: Parameters List</a></span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>   peladm delete_model  -ml MODELA</p>
<p>   -pr GENERAL</p>         </td>
      </tr>
   </tbody>
</table>

<span id="peladm_check_model"></span>

### Checking Model properties: peladm check\_model

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p>peladm check_model {-model} [-protocol]</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to verify the coherence between the properties of a Model and the names of the properties used in the Model.</p>
<p>Since a General Model and a Protocol Model can share the same name, you should specify both the name and protocol of the Model that you want to check.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span class="code">-model (-ml)</span>: Enter the name of the existing Model that you want to check.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-protocol (-pr)</span>: Enter the name of the protocol of the Model that you want to check. Enter one of the following values:</p>
<ul>
<li><span style="font-weight: bold;">GENERAL</span> (default)</li>
<li><span style="font-weight: bold;">PHSE</span> = PeSIT HS E</li>
<li><span style="font-weight: bold;">PHSD</span> = PeSIT HS D</li>
<li><span style="font-weight: bold;">PEL</span></li>
<li><span style="font-weight: bold;">FTP</span></li>
<li><span style="font-weight: bold;">HTTP</span></li>
<li><span style="font-weight: bold;">ODETTE</span> = OFTP</li>
<li><span style="font-weight: bold;">SFTP</span></li>
<li><span style="font-weight: bold;">SMTP</span></li>
<li><span style="font-weight: bold;">POP3</span></li>
<li>POP3</li>
<li>TO_GTW</li>
<li>FROM_GTW</li>
<li>AS2</li>
<li>AS3</li>
<li>AS1_POP3</li>
<li>AS1_SMTP</li>
<li>RN_POP3</li>
<li>RN_SMTP</li>
<li>RN_HTTP</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>peladm check_model  -ml MODELA  -pr GENERAL</p>         </td>
      </tr>
   </tbody>
</table>

<span id="peldsp_select_model"></span>

### Selecting models: peldsp select\_model

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p>peldsp select_model {-model} [-<span style="font-weight: normal;">protocol</span>] [-<span style="font-weight: normal;">prop_list_name</span>]</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to select the Models that match the criteria entered as parameters.</p>
<p>To list all Models, enter no parameters. You can refine your search using the optional parameters.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span class="code">-model (-ml)</span>: Enter the name of the existing Model that you want to select.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-protocol (-pr)</span> : Enter the name of the protocol of the Model that you want to select. Enter one of the following values:</p>
<ul>
<li><span style="font-weight: bold;">GENERAL</span> (default)</li>
<li><span style="font-weight: bold;">PHSE</span> = PeSIT HS E</li>
<li><span style="font-weight: bold;">PHSD</span> = PeSIT HS D</li>
<li><span style="font-weight: bold;">PEL</span></li>
<li><span style="font-weight: bold;">FTP</span></li>
<li><span style="font-weight: bold;">HTTP</span></li>
<li><span style="font-weight: bold;">ODETTE</span> = OFTP</li>
<li><span style="font-weight: bold;">SFTP</span></li>
<li><span style="font-weight: bold;">SMTP</span></li>
<li><span style="font-weight: bold;">POP3</span></li>
<li>POP3</li>
<li>TO_GTW</li>
<li>FROM_GTW</li>
<li>AS2</li>
<li>AS3</li>
<li>AS1_POP3</li>
<li>AS1_SMTP</li>
<li>RN_POP3</li>
<li>RN_SMTP</li>
<li>RN_HTTP</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-prop_list_name (-pln)</span>: Enter the name of the properties list that you want to select.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>When you enter the command, Model names and protocols that match the selection criteria are listed on screen. The following command returns all Models with the FTP protocol.</p>
<p>peldsp select_model  pr FTP</p>
<p>returns (for example):</p>
<p>MODELB</p>
<p>MODEL_FTP</p>         </td>
      </tr>
   </tbody>
</table>

<span id="peldsp_display_model"></span>

### Displaying a model: peldsp display\_model

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p>peldsp display_model {-model} [-protocol]</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to display the details of a Model identified by its name and protocol. The Transfer parameters are displayed by return.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span class="code">-model (-ml)</span>: Enter the name of the existing Model that you want to display.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-protocol (-pr)</span>: Enter the name of the protocol of the Model that you want to display. Enter one of the following values:</p>
<ul>
<li><span style="font-weight: bold;">GENERAL</span> (default)</li>
<li><span style="font-weight: bold;">PHSE</span> = PeSIT HS E</li>
<li><span style="font-weight: bold;">PHSD</span> = PeSIT HS D</li>
<li><span style="font-weight: bold;">PEL</span></li>
<li><span style="font-weight: bold;">FTP</span></li>
<li><span style="font-weight: bold;">HTTP</span></li>
<li><span style="font-weight: bold;">ODETTE</span> = OFTP</li>
<li><span style="font-weight: bold;">SFTP</span></li>
<li><span style="font-weight: bold;">SMTP</span></li>
<li><span style="font-weight: bold;">POP3</span></li>
<li>POP3</li>
<li>TO_GTW</li>
<li>FROM_GTW</li>
<li>AS2</li>
<li>AS3</li>
<li>AS1_POP3</li>
<li>AS1_SMTP</li>
<li>RN_POP3</li>
<li>RN_SMTP</li>
<li>RN_HTTP</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>Each parameter is displayed on a separate line:</p>
<p>   name_of_field="value"</p>
<p>Each field name is prefixed with the string "<span class="code" style="font-weight: bold;">m_</span>", relating to the <span style="font-weight: bold;">M</span>odel object.</p>
<p>Only supplied fields are displayed.</p>
<p>   peldsp display_model  -ml MODELA  -pr GENERAL</p>
<p>   m_model='MODELA'</p>
<p>   m_protocol='GENERAL'</p>
<p>   m_comments=''</p>
<p>   m_dest_alias='TPHSE'</p>
<p>   m_appli='DEFAULT_A'</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Model objects: Parameters List](../model_object_parameter_list)

[Working with purge models](../working_with_purge_models_cli)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
