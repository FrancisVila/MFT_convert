{
    "title": "Working with Diffusion Lists (command line)",
    "linkTitle": "Command line operations",
    "weight": "180"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Partners

[<span class="code" style="font-weight: bold;">peladm create\_list</span>](#peladm_create_list)

[<span class="code" style="font-weight: bold;">peladm update\_list</span>](#peladm_update_list)

[<span class="code" style="font-weight: bold;">peladm delete\_list</span>](#peladm_delete_list)

[<span class="code" style="font-weight: bold;">peldsp select\_list</span>](#peldsp_select_list)

[<span class="code" style="font-weight: bold;">peldsp display\_list</span>](#peldsp_display_list)

<span id="peladm_create_list"></span>

## Creating a Diffusion List: peladm create\_list

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code"><strong>peladm create_list {-list_name}</strong> [-group] [-comments] [-model] [-site_file] [-sites] [-add_sites] [-del_sites] [-template_site]</span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to create a Diffusion List.</p>
<p>The <span style="font-style: italic;">string</span> syntax followed by the * character is used to search for all Sites that begin with this string.</p>
<p><span style="font-weight: bold;">Note:</span> Processing of <span class="code">-sites</span> and <span class="code">-add_sites</span> parameters is always performed before processing <span class="code">-del_site</span> (delete).</p>
<p>You can simplify List creation by pointing to a text file that comprises all the elements to include in the Diffusion List.</p>
<p>When you create a Diffusion List, the Sites or Lists you refer to must exist, unless you use a Template Site. In this case, the destination Sites are protocol-level destinations. No check is performed to determine whether they exist.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>Mandatory</p>
<p><span class="code">-list_name (-n)</span>: Enter a name for the Diffusion List object you are creating.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-group (-gr)</span>: Enter a name for the name of the Application group associated with the Diffusion List.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-comments (-cts)</span>: Enter a comment about the Diffusion List.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-model (-ml)</span>: Enter the name of a default Model that you want to associate with the Diffusion List.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-site_file (-sf)</span>: Enter the name of a text file that contains a set of Sites, protocol-level destinations and/or Diffusion Lists to use as targets for the Diffusion List.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-sites (-s)</span>: Enter names of Sites, protocol-level destinations or other Diffusion Lists to use as targets for the Diffusion List.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-add_sites (-a)</span>: Enter the names of additional Sites to add to the Diffusion List.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-del_sites (-d)</span>: Enter the names of Sites that you want to remove from the Diffusion List.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-template_site (-ts)</span>: Enter the name of a Template Site to associate with the Diffusion List.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following command creates a Diffusion List object named <span style="font-style: italic;">LIST1</span> with a default template (MODELA) and several target destinations.</p>
<p>peladm create_list</p>
<p>-list_name LIST1</p>
<p>–comments "First List"</p>
<p>–model MODELA</p>
<p>–sites "SITEA SITEB SITEC LIST11 ASITE* BSITE*"</p>
<p> </p>
<p>The destinations defined for this Diffusion are:</p>
<ul>
<li>SITEA, SITEB, SITEC</li>
<li>LIST11 and the ASITE* and BSITE* generic Sites</li>
</ul>
<p><span style="font-weight: bold;">Note:</span> The Sites and Diffusion List you select when creating a Diffusion List already exist.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="peladm_update_list"></span>

## Modifying a Diffusion List: peladm update\_list

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code"><strong>peladm update_list {-list_name}</strong> [-group] [-comments] [-model] [-site_file] [-sites] [-add_sites] [-del_sites] [-template_site]</span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to modify and update a Diffusion List.</p>
<p>The Diffusion List name (<span class="code">-list_name</span>) value identifies the Diffusion List to modify. Enter new values of optional the parameters you want to change.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>Mandatory</p>
<p><span class="code">-list_name (-n)</span>: Enter a name for the Diffusion List object you want to modify</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-group (-gr)</span>: Enter a name of the Application group associated with the Diffusion List</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-comments (-cts)</span>: Enter a comment about the Diffusion List</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-model (-ml)</span>: Enter the name of a default Model that you want to associate with the Diffusion List</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-site_file (-sf)</span>: Enter the name of a text file that contains a set of Sites, protocol-level destinations and/or Diffusion Lists to use as targets for the Diffusion List</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-sites (-s)</span>: Enter names of Sites, protocol-level destinations or other Diffusion Lists to use as targets for the Diffusion List</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-add_sites (-a)</span>: Enter the names of additional Sites to add to the Diffusion List</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-del_sites (-d)</span>: Enter the names of Sites that you want to remove from the Diffusion List</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-template_site (-ts)</span>: Enter the name of a Template Site to associate with the Diffusion List</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following command:</p>
<ul>
<li>updates LIST1 with a default template (MODELB)</li>
<li>replaces the existing elements in the Diffusion List with SITE1</li>
<li>adds SITE2 and LIST</li>
</ul>
<p>peladm update_list</p>
<p>–n LIST1</p>
<p>–ml MODELB</p>
<p>–s "SITE1"</p>
<p>–a "SITE2 LIST"</p>         </td>
      </tr>
   </tbody>
</table>

<span id="peladm_delete_list"></span>

## Deleting a Diffusion List: peladm delete\_list

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code">peladm delete_list {-list_name}</span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to delete a specified Diffusion List.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>Mandatory</p>
<p><span class="code">-list_name (-n)</span>: Enter a name for the Diffusion List object you want to delete.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following command deletes the Diffusion List <span style="font-style: italic;">LIST1</span>:</p>
<p>peladm delete_list  –list_name LIST1</p>         </td>
      </tr>
   </tbody>
</table>

<span id="peldsp_select_list"></span>

## Selecting a Diffusion List: peldsp select\_list

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code"><strong>peldsp select_list</strong> [-list_name]</span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to select for display the Diffusion List that corresponds to the list name criteria.</p>
<p>To list all Diffusion Lists, do not specify any parameters. Use the optional parameters to refine the selection.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span class="code">-list_name (-n)</span>: Enter the name of the Diffusion List you want to display.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following command returns the names of the Diffusion Lists that correspond to the selection criteria.</p>
<p>peldsp select_list  –n LI</p>
<p>Each parameter is considered to be a <span style="font-style: italic;">truncated</span> search key. This command returns the Diffusion Lists whose names begin with <span style="font-style: italic;">LI.</span> It could, for example, return:</p>
<p>peldsp select_list  –n LI</p>
<p>LIST1_DEFAULT</p>
<p>LIST2</p>
<p>LIST34</p>         </td>
      </tr>
   </tbody>
</table>

<span id="peldsp_display_list"></span>

## Displaying a Diffusion List: peldsp display\_list

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code"><strong>peldsp display_list</strong> [-list_name]</span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to display the parameters of a Diffusion List that you identify by its name.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span class="code">-list_name (-n)</span>: Enter the name of the Diffusion List for which you want to display the attributes.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>Gateway returns a display of each parameter associated with the specified Diffusion List object on one line in the form:</p>
<p>name_of_field(_optional counter)="value"</p>
<p>Each field name is prefixed with the <span class="code" style="font-weight: bold;">d_</span> string which points to a Diffusion List-type object.</p>
<p>For example when you enter the following command:</p>
<p>peldsp display_list  –n LIST2</p>
<p>Gateway might display the following fields and values (depending on your configuration):</p>
<p>d_list_name='LIST2'</p>
<p>d_group_name='GDEFAULT'</p>
<p>d_model_name='MODELA'</p>
<p>d_comment='used template site'</p>
<p>d_template_site='TPHSE'</p>
<p>d_site_1='DEST1'</p>
<p>d_site_2='DEST2'</p>
<p>d_site_3='SITE'</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Diffusion Lists: Parameters List](diffusion_lists_parameter_list)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
