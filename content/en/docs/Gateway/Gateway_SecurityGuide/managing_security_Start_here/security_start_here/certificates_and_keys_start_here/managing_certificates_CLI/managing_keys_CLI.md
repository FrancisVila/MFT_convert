{
    "title": "Managing keys (command line)",
    "linkTitle": "Managing keys",
    "weight": "230"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Security

[<span class="code" style="font-weight: bold;">secadm import\_key</span>](#secadm_import_key)

[<span class="code" style="font-weight: bold;">secadm update\_key</span>](#secadm_update_key)

[<span class="code" style="font-weight: bold;">secadm delete\_key</span>](#secadm_delete_key)

[<span class="code" style="font-weight: bold;">secdsp select\_key</span>](#secdsp_select_key)

[<span class="code" style="font-weight: bold;">secdsp display\_key</span>](#secdsp_display_key)

[<span class="code" style="font-weight: bold;">secdsp status\_key</span>](#secdsp_status_key)

<span id="secadm_import_key"></span>

## Importing a key: secadm import\_key

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code" style="font-weight: bold;">secadm import_key {-name} {-file_name} {-file_format}</span> [-algorithm] [-type] [-group] [-state] [-comments]</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to import a key into the local database.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>Mandatory</p>
<p><span class="code">-name (-n)</span>: Enter the name of the key you are importing. The name of the key must be unique. (max 31 characters).</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-style: italic;">Mandatory</span></p>
<p><span class="code">-file_name (-fn)</span>: Enter the name of the file that contains the key to import.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-style: italic;">Mandatory</span></p>
<p><span class="code">-file_format (-ff)</span>: Enter the Key file encoding.</p>
<p>Possible values:</p>
<ul>
<li>DER</li>
<li>PEM (default)</li>
<li>TXT</li>
<li>OPENSSH</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-algorithm (-algo)</span>: Enter the Key file algorithm.</p>
<p>Possible values:</p>
<ul>
<li>RSA</li>
<li>DSS</li>
<li>ECDSA_NISTP256</li>
<li>ECDSA_NISTP384</li>
<li>ECDSA_NISTP521</li>
<li>ED25519</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-type (-t)</span>: Enter the key type.</p>
<p>Possible values:</p>
<ul>
<li>PRIVATE</li>
<li>PUBLIC</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-group (-g)</span>: Enter the group of the Key.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-state (-s)</span>: Enter the operational status of the Key:</p>
<ul>
<li><span style="font-weight: bold;">E</span> = Enabled</li>
<li><span style="font-weight: bold;">D</span> = Disabled</li>
<li><span style="font-weight: bold;">C</span> = To check</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-comments (-cts)</span>: Enter free text comments about the key.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following command imports the key contained in the file <span class="code">rsaprv1024.pem</span> into the database and names it rsaprv1024. The file type is the default value (PEM).</p>
<p>secadm import_key  –name "rsaprv1024"</p>
<p>–filename "rsaprv1024.pem"</p>         </td>
      </tr>
   </tbody>
</table>

<span id="secadm_update_key"></span>

## Updating a key: secadm update\_key

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code" style="font-weight: bold;">secadm update_key {-name}</span> [-state] [-group] [-new_name] [-comments]</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to modify a key.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span style="font-style: italic;">Mandatory</span></p>
<p><span class="code">-name (-n)</span>: Enter the name of the key you are modifying.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-state (-s)</span>: Enter the operational status of the Key:</p>
<ul>
<li><span style="font-weight: bold;">E</span> = Enabled</li>
<li><span style="font-weight: bold;">D</span> = Disabled</li>
<li><span style="font-weight: bold;">C</span> = To check</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-group (-g)</span>: Enter the group of the Key.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-new_name (-nn)</span>: Enter a new name for the Key.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-comments (-cts)</span>: Enter free text comments about the Key.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following command disables the use of the key rsaprv1024:</p>
<p>secadm update_key  –name "rsaprv1024"</p>
<p>–status DISABLED</p>         </td>
      </tr>
   </tbody>
</table>

<span id="secadm_delete_key"></span>

## Deleting a key: secadm delete\_key

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p>secadm delete_key {-name}</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to remove a Key from the database.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span style="font-style: italic;">Mandatory</span></p>
<p><span class="code">-name (-n)</span>: Enter the name of the Key you want to delete.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following command removes the key named rsaprv1024:</p>
<p>secadm delete_key  –name "rsaprv1024"</p>         </td>
      </tr>
   </tbody>
</table>

<span id="secdsp_display_key"></span>

## Displaying a key: secdsp display\_key

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p>secdsp display_key {-name}</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to display the attributes of a Key.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span style="font-style: italic;">Mandatory</span></p>
<p><span class="code">-name (-n)</span>: Enter the name of the Key for which you want to display the attributes.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following command displays attributes of the key named rsaprv1024:</p>
<p>secdsp display_key  –name "rsaprv1024"</p>         </td>
      </tr>
   </tbody>
</table>

<span id="secdsp_select_key"></span>

## Listing key names: secdsp select\_key

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p>secdsp select_key</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to display the names of the keys in the database.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><code>-name</code> (<code>-n</code>): Enter the name of the Key for which you want to display the attributes.</p>         </td>
      </tr>
      <tr>
         <td><code>-group</code> (<code>-g</code>): Enter the group of the Key.         </td>
      </tr>
      <tr>
         <td><p><code>-state</code> (<code>-s</code>): Enter the operational status of the Key:</p>
<ul>
<li>E = Enabled</li>
<li>D = Disabled</li>
<li>C = To check</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><code>-algorithm</code> (<code>-algo</code>): Enter the Key file algorithm.
Possible values:</p>
<ul>
<li>RSA</li>
<li>DSS</li>
<li>ECDSA_NISTP256</li>
<li>ECDSA_NISTP384</li>
<li>ECDSA_NISTP521</li>
<li>ED25519</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><code>-type</code> (<code>-t</code>): Enter the key type.
Possible values:</p>
<ul>
<li>PRIVATE</li>
<li>PUBLIC</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following command displays a list of the names of all enabled keys in the database:</p>
<p><code style="font-weight: bold;">secdsp select_key -state ENABLED</code></p>         </td>
      </tr>
   </tbody>
</table>

<span id="secdsp_status_key"></span>

## Listing key status: secdsp status\_key

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p>secdsp status_key</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to display the status (Enabled/Disabled/To_check) of the Keys in the database.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><code>-name</code> (<code>-n</code>): Enter the name of the Key for which you want to display the attributes.</p>         </td>
      </tr>
      <tr>
         <td><code>-group</code> (<code>-g</code>): Enter the group of the Key.         </td>
      </tr>
      <tr>
         <td><p><code>-state</code> (<code>-s</code>): Enter the operational status of the Key:</p>
<ul>
<li>E = Enabled</li>
<li>D = Disabled</li>
<li>C = To check</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><code>-algorithm</code> (<code>-algo</code>): Enter the Key file algorithm.
Possible values:</p>
<ul>
<li>RSA</li>
<li>DSS</li>
<li>ECDSA_NISTP256</li>
<li>ECDSA_NISTP384</li>
<li>ECDSA_NISTP521</li>
<li>ED25519</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><code>-type</code> (<code>-t</code>): Enter the key type.
Possible values:</p>
<ul>
<li>PRIVATE</li>
<li>PUBLIC</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following command displays a list of the names of all enabled keys in the database:</p>
<p><code style="font-weight: bold;">secdsp select_key -state ENABLED</code></p>         </td>
      </tr>
   </tbody>
</table>

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
