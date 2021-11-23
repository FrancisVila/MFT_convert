{
    "title": "Command line operations for Local Sites",
    "linkTitle": "Command line operations",
    "weight": "170"
}{{< Gateway/componentlongname  >}}: Managing Partners

`peladm create_loc_site`

`peladm delete_loc_site`

`peladm update_loc_site`

`peldsp display_loc_site`

`peldsp select_loc_site`

`peldsp status_loc_site`

<span id="peladm_create_loc_site"></span>

## Creating Local Sites: peladm create\_loc\_site

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p>peladm create_loc_site {-alias} [] [] [] [] [] []</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to create a Local Site.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>Mandatory</p>
<p><code>-alias (-a)</code>: Enter a Site alias for the Local Site you are creating.</p>         </td>
      </tr>
      <tr>
         <td><p>Not for FTP or SFTP Sites.</p>
<p><code>-proto_ident (-pi)</code>: Enter the Site protocol name for the Site.</p>         </td>
      </tr>
      <tr>
         <td><p><code>-comments (-cts)</code>: Enter a comment for user information.</p>         </td>
      </tr>
      <tr>
         <td><p><code>-dir_path (-dp)</code>: Enter the path to the directory of the local file management system where received files are stored.</p>         </td>
      </tr>
      <tr>
         <td><p>SMTP only</p>
<p><code>-mail_address (-email)</code>: Enter the default email address to use if no address is specified in the Transfer Request. By default, Gateway uses the default <em>From</em> address.</p>         </td>
      </tr>
      <tr>
         <td><p><code>-param1 (-p1)</code>: Enter a user parameter of up to 40 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><code>-param2 (-p2)</code>: Enter a user parameter of up to 40 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following command creates a Local Site with the alias SITE_LOC.</p>
<p>peladm create_loc_site  -a SITE_LOC</p>         </td>
      </tr>
   </tbody>
</table>

<span id="peladm_update_loc_site"></span>

## Modifying Local Sites: peladm update\_loc\_site

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p>peladm update_loc_site {-alias} [] [] [] [] [] []</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to modify and update the attributes of a Local Site that you identify by its alias.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>Mandatory</p>
<p><code>-alias (-a)</code>: Enter a Site alias for the Local Site you are modifying.</p>         </td>
      </tr>
      <tr>
         <td><p><em>Not for FTP or SFTP Sites.</em></p>
<p><code>-proto_ident (-pi)</code>: Enter the new Site protocol name for the Site.</p>         </td>
      </tr>
      <tr>
         <td><p><code>-comments (-cts)</code>: Enter a modified comment for user information.</p>         </td>
      </tr>
      <tr>
         <td><p><code>-dir_path (-dp)</code>: Enter a modified path to the directory of the local file management system where received files are stored.</p>         </td>
      </tr>
      <tr>
         <td><p>SMTP only</p>
<p><code>-mail_address (-email)</code>: Enter a modified default email address to use if no address is specified in the Transfer Request. By default Gateway uses the default From address.</p>         </td>
      </tr>
      <tr>
         <td><p><code>-param1 (-p1)</code>: Enter a user parameter of up to 40 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><code>-param2 (-p2)</code>: Enter a user parameter of up to 40 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following command resets the protocol identifier for the Local Site SITE.</p>
<p>peladm update_loc_site  -a SITE</p>
<p>   -pi SITE_PROTO_IDENT</p>         </td>
      </tr>
   </tbody>
</table>

<span id="peladm_delete_loc_site"></span>

## Deleting Local Sites: peladm delete\_loc\_site

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p>peladm delete_loc_site {-alias} [] [] [] [] [] []</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to delete a Local Site that you identify by its alias.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>Mandatory</p>
<p><code>-alias (-a)</code>: Enter the Site alias for the Local Site you are deleting.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following command deletes the Local Site whose alias is SITE:</p>
<p>peladm delete_loc_site  -a SITE</p>         </td>
      </tr>
   </tbody>
</table>

<span id="peldsp_select_loc_site"></span>

## Selecting Local Sites: peldsp select\_loc\_site

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p>peldsp select_loc_site [-] []</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to filter the display of Local Sites using the criteria entered as parameters.</p>
<p>To list all Local Sites, enter no parameters. You can then refine your selection using the optional parameters.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><code>-alias (-a)</code>: Enter a Site alias for the Local Site as selection criteria.</p>         </td>
      </tr>
      <tr>
         <td><p>Not for FTP or SFTP Sites.</p>
<p><code>-proto_ident (-pi)</code>: Enter a Site protocol name as selection criteria.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following command generates a filtered display of Local Sites. Gateway displays the aliases of the Local Sites that match the selection criteria.</p>
<p>peldsp select_loc_site  -a U</p>
<p>Each string parameter is seen as a truncated search key. The command returns a list of the Local Sites with aliases beginning with the letter U.</p>
<p>UXTPDX02</p>
<p>UXTPDT03</p>
<p>UXTPLX02</p>         </td>
      </tr>
   </tbody>
</table>

<span id="peldsp_display_loc_site"></span>

## Displaying Local Sites: peldsp display\_loc\_site

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p>peldsp display_loc_site {-alias}</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to display the attributes of a specific Local Site that you identify by its alias.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>Mandatory</p>
<p><code>-alias (-a)</code>: Enter a Site alias for the Local Site as selection criteria.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>When you use this command, Gateway displays each parameter on a separate line in the format:</p>
<p>name_of_field="value"</p>
<p>Each field name is prefixed by the string "<code>s_</code>", referring to the <strong>S</strong>ite object.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="peldsp_status_loc_site"></span>

## Displaying Local Site status: peldsp status\_loc\_site

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p>peldsp status_loc_site {-alias}</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to display the initial and dynamic status of a Local Site that you identify by its alias.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span style="font-style: italic;">Mandatory</span></p>
<p><span class="code">-alias (-a)</span>: Enter a Site alias for the Local Site as selection criteria.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>When you use this command, Gateway displays each parameter on a separate line in the format:</p>
<p>name_of_field="value"</p>
<p>Each field name is prefixed by the string "<span class="code" style="font-weight: bold;">s_</span>", referring to the <span style="font-weight: bold;">S</span>ite object.</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Site objects: Parameters List](sites_parameter_list)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
