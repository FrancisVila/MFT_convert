{
    "title": "Monitoring Connections (command line)",
    "linkTitle": "Monitoring Connections",
    "weight": "240"
}{{< Gateway/componentlongname  >}}: Managing Transfers

[`peldsp select_connection`](#peldsp_select_connction)

[`peldsp status_connection`](#peldsp_status_connection)

[`peldsp display_connection`](#peldsp_display_connection)

[`pelctl kill_connection`](#pelctl_kill_connection)

<span id="peldsp_select_connction"></span>

## Displaying list of Connections: peldsp select\_connection

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><code>peldsp select_connection [(-ci) (-ca) (-cb) (-s) (-m)]</code></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to display the list of Connections that match the parameters that you specify. The Connections may be in a transfer phase (Transferring) or not (Still).</p>
<p>To display the list of all Connections, enter the command with no parameter. Alternatively, specify the connection via the Connection identifier parameter. Use the optional parameters to further refine the search.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><code>-connection_id (-ci)</code>: Enter an integer that uniquely identifies the connection.</p>         </td>
      </tr>
      <tr>
         <td><p><code>-connected_after (-ca)</code>: Enter a time and date in the format <em>YYMMDD HHMMSS</em>.</p>         </td>
      </tr>
      <tr>
         <td><p><code>-connected_before (-cb)</code>: Enter a time and date in the format <em>YYMMDD HHMMSS</em>.</p>         </td>
      </tr>
      <tr>
         <td><p><code>-state (-s)</code>: Enter one of the following values:</p>
<ul>
<li><strong>S</strong> = Still (no activity)</li>
<li><span style="font-weight: bold;">T</span> = Transferring</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-mode (-m)</span>: Enter one of the following values:</p>
<ul>
<li><span style="font-weight: bold;">I</span> = Initiator</li>
<li><span style="font-weight: bold;">R</span> = Responder</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>peldsp select_connection  -ca '070803 150000'</p>
<p>This command selects the connections that occurred after 3 p.m. (<span style="font-weight: bold;">150000</span>) on 3 August 2007 (<span style="font-weight: bold;">070803</span>).</p>         </td>
      </tr>
   </tbody>
</table>

<span id="peldsp_status_connection"></span>

## Displaying Connection status: peldsp status\_connection

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code" style="font-weight: bold;">peldsp status_connection [(-ci) (-ca) (-cb) (-s) (-m)]</span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to display status information for a list of active Connections that match the parameters that you specify. Each element of this list comprises a Connection identifier followed by status attributes.</p>
<p>The Connections are either in a transfer phase (Transferring) or not (Still).</p>
<p>To list all Connections, use the command with no parameters. Alternatively, refine the search using optional parameters.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span class="code">-connection_id (-ci)</span>: Enter an integer that uniquely identifies the connection.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-connected_after (-ca)</span>: Enter a time and date in the format <span style="font-style: italic;">YYMMDD HHMMSS</span>.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-connected_before (-cb)</span>: Enter a time and date in the format <span style="font-style: italic;">YYMMDD HHMMSS</span>.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-state (-s)</span>: Enter one of the following values:</p>
<ul>
<li><span style="font-weight: bold;">S</span> = Still (no activity)</li>
<li><span style="font-weight: bold;">T</span> = Transferring</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-mode (-m)</span>: Enter one of the following values:</p>
<ul>
<li><span style="font-weight: bold;">I</span> = Initiator</li>
<li><span style="font-weight: bold;">R</span> = Responder</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>peldsp status_connection  -m I</p>
<p>This command selects Initiator mode connections.</p>
<p>Ident  Sta       Address       Connected At    Cuser   ECount   ASpeed    XBytes</p>
<p>  5     S   188.221.3.95/4096  070803 160124   RSK23     0     2154364   4308728</p>         </td>
      </tr>
   </tbody>
</table>

<span id="peldsp_display_connection"></span>

## Displaying Connection attributes: peldsp display\_connection

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code" style="font-weight: bold;">peldsp display_connection [(-ci)]</span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to display the supervision-oriented attributes of a Connection. The screen displays attributes for the Connection.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span class="code">-connection_id (-ci)</span>: Enter an integer that uniquely identifies the connection.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>peldsp display_connection  –ci 5</p>
<p>   c_connection_id = '5'</p>
<p>   c_connection_state = 'S'</p>
<p>   c_remote_address = '188.221.3.95/4096'</p>
<p>   c_date_connected = '070803 160124'</p>
<p>   c_protocol = 'FTP'</p>
<p>   c_mode = 'I'</p>
<p>   c_connected_user = 'RSK23'</p>
<p>   c_current_transfer_ident = '25468'</p>
<p>   c_transfer_date = '070803 163024'</p>
<p>   c_downloads_count = '3'</p>
<p>   c_uploads_count = '0'</p>
<p>   c_errors_count = '0'</p>
<p>   c_average_speed = '4308728'</p>
<p>   c_x_bytes = '2154364'</p>
<p> </p>
<p>For details of return parameters, refer to <a href="../connections_parameter_list#return_paras">Connections: Parameters list</a>.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="pelctl_kill_connection"></span>

## Aborting a Connection: pelctl kill\_connection

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code" style="font-weight: bold;">pelctl kill_connection [(-ci)]</span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to abort a specific Connection.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span class="code">-connection_id (-ci)</span>: Enter an integer that uniquely identifies the connection.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>First, check the status with <span class="code">peldsp select_connection</span>:</p>
<p>peldsp select_connection  -ca '070803 150000'</p>
<p>Then abort the required connection:</p>
<p>pelctl kill_connection  –ci 5</p>
<p>Finally, recheck the status with <span class="code">peldsp select_connection</span>:</p>
<p>peldsp select_connection  -ca '070803 150000'</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Connections: Parameters list](../connections_parameter_list)

[Monitoring Transfers](../../)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
