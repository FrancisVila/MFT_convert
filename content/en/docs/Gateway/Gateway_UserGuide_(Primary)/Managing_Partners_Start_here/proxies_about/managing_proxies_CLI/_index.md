{
    "title": "Working with Proxies (command line)",
    "linkTitle": "Command line operations",
    "weight": "160"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Partners

<span class="code" style="font-weight: bold;">[peladm create\_proxy](#peladm_create_proxy)</span>

<span class="code" style="font-weight: bold;">[peladm update\_proxy](#peladm_update_proxy)</span>

<span class="code" style="font-weight: bold;">[peladm delete\_proxy](#peladm_delete_proxy)</span>

<span class="code" style="font-weight: bold;">[peldsp display\_proxy](#peldsp_display_proxy)</span>

<span class="code" style="font-weight: bold;">[peldsp select\_proxy](#peldsp_select_proxy)</span>

<span id="peladm_create_proxy"></span>

## Creating a Proxy: peladm create\_proxy

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code"><strong>peladm create_proxy [-name (-n)]</strong> [optional parameters]</span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to create a new Proxy.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span class="code">-name (-n)</span>: Enter the name of the Proxy you are creating.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-style: italic;">optional parameters:</span> Refer to <a href="proxies_parameter_list">Proxies: Parameters List</a>.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following command creates an FTP Proxy:</p>
<p>peladm create_proxy  -name FProxy</p>
<p>-protocol FTP</p>
<p>-comments "FTP proxy"</p>
<p>-login_user Shepherd</p>
<p>-login_password</p>
<p>-type USER_AT_SITE</p>
<p>-change_data_addr N</p>         </td>
      </tr>
   </tbody>
</table>

<span id="peladm_update_proxy"></span>

## Modifying a Proxy: peladm update\_proxy

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code"><strong>peladm update_proxy [-name (-n)]</strong> [optional parameters]</span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to modify a Proxy definition.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span class="code">-name (-n)</span>: Enter the name of the Proxy.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-style: italic;">optional parameters:</span> Refer to <a href="proxies_parameter_list">Proxies: Parameters List</a>.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following command modifies the properties of the Proxy named <span style="font-style: italic;">Proxy1.</span></p>
<p>peladm update_proxy  -name Proxy1</p>
<p>-protocol FTP</p>
<p>-change_data_addr Y</p>         </td>
      </tr>
   </tbody>
</table>

<span id="peladm_delete_proxy"></span>

## Deleting a Proxy: peladm delete\_proxy

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code"><strong>peladm delete_proxy [-name (-n)]</strong></span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to delete an existing Proxy.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span class="code">-name (-n)</span>: Enter the name of the Proxy.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following command deletes the Proxy named <span style="font-style: italic;">Proxy1.</span></p>
<p>peladm delete_proxy  -name Proxy1</p>         </td>
      </tr>
   </tbody>
</table>

<span id="peldsp_display_proxy"></span>

## Displaying a Proxy: peldsp display\_proxy

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code"><strong>peladm display_proxy [-name (-n)]</strong></span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>This command displays the full definition of the Proxy that you specify.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span class="code">-name (-n)</span>: Enter the name of the Proxy.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following example displays all attributes of Proxy <span style="font-style: italic;">Proxy1</span>.</p>
<p>Enter the command:</p>
<p>peldsp display_proxy  -name Prosy</p>
<p>Gateway returns:</p>
<p>pr_name='Proxy1'</p>
<p>pr_protocol=FTP</p>
<p>pr_address='proxy/21'</p>
<p>pr_comments=''</p>         </td>
      </tr>
   </tbody>
</table>

<span id="peldsp_select_proxy"></span>

## Selecting Proxies: peldsp select\_proxy

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code"><strong>peldsp select_proxy [-name (-n)] [-protocol (-pr)]</strong></span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to display a subset of proxies that matches the defined selection criteria.</p>
<p>To list all Proxies, enter the command without any selection parameters.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span class="code">-name (-n)</span>: Enter the name of the Proxy.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-protocol (-pr)</span>: Name of the network layer protocol of the proxy you want to display. Enter one of the values:</p>
<ul>
<li>SOCKS4</li>
<li>FTP</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following command selects all FTP Proxies.</p>
<p>peldsp select_proxy  -protocol FTP</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Proxies: Parameters List](proxies_parameter_list)

[Using an FTP proxy](../../../protocols_about/ftp_about/ftp_using_proxy)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
