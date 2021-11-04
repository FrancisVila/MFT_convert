{
    "title": "Monitoring Connected Users (command line)",
    "linkTitle": "Monitoring Connected Users",
    "weight": "240"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Transfers

[<span class="code" style="font-weight: bold;">peldsp select\_connected\_user</span>](#peldsp_select_connected_user)

[<span class="code" style="font-weight: bold;">peldsp status\_connected\_user</span>](#peldsp_status_connected_user)

[<span class="code" style="font-weight: bold;">peldsp display\_connected\_user</span>](#peldsp%20display%20connected%20user)

[<span class="code" style="font-weight: bold;">pelctl disconnect\_user</span>](#pelctl_dixonnect_user)

[<span class="code" style="font-weight: bold;">pelctl reset\_connected\_user</span>](#pelctl_reset_connected_user)

<span id="peldsp_select_connected_user"></span>

## Displaying list of Connected Users: peldsp select\_connected\_user

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code"><strong>peldsp select_connected_user</strong> [(-cui)(-ca)(-cb)]</span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to display a list of the active Connected Users (via their identifiers) that match the parameters that you specify.</p>
<p>To list all Connected Users, enter the command with no parameter. Alternatively, identify the Connected User to select using the<span class="code"> -connected_user_id</span> parameter. Use the optional parameters to further refine the search.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span class="code">-connected_user_id (-cui)</span>: Enter an integer that uniquely identifies the Connected User.<br />
Max 31 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-connected_after (-ca)</span>: Enter a time and date in the format YYMMDD HHMMSS.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-connected_before (-cb)</span>: Enter a time and date In the format YYMMDD HHMMSS.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>peldsp select_connected_user  -ca '070803 150000'</p>
<p>RSK23</p>
<p>WNT002</p>
<p>This command selects Connected Users whose first connection occurred after 3 p.m. (<span style="font-weight: bold;">150000</span>) on 3 August 2007 (<span style="font-weight: bold;">070803</span>).</p>         </td>
      </tr>
   </tbody>
</table>

<span id="peldsp_status_connected_user"></span>

## Displaying Connected User status: peldsp status\_connected\_user

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code"><strong>peldsp status_connected_user</strong> [(-cui)(-ca)(-cb)]</span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to display status information for the active Connected Users that match the parameters that you specify. Each element of this list comprises a Connected User identifier followed by status attributes.</p>
<p>To list all Connected Users, enter the command with no parameter. Alternatively, refine the search using optional parameters.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span class="code">-connected_user_id (-cui)</span>: Enter an integer that uniquely identifies the connected user.<br />
Max 31 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-connected_after (-ca)</span>: Enter a time and date in the format <span style="font-style: italic;">YYMMDD HHMMSS</span>.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-connected_before (-cb)</span>: Enter a time and date In the format <span style="font-style: italic;">YYMMDD HHMMSS</span>.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>peldsp status_connected_user</p>
<p>Ident Last Address Connected At Max ACount DCount Ucount ECount ASpeed XBytes</p>
<p>RSK23 188.221.3.95/4096 070803 160124  10   124  102  22  0   2154364  4308728</p>
<p>WNT02 193.220.17.5/4096 070803 121107  10   14    8    6  0   1432864  2865728</p>         </td>
      </tr>
   </tbody>
</table>

<span id="peldsp display connected user"></span>

## Displaying Connected User attributes: peldsp display\_connected\_user

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code"><strong>peldsp display_connected_user</strong> [(-cui)]</span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to display the attributes of a specific Connected User. The screen displays attributes for the Connected User.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span class="code">-connected_user_id (-cui)</span>: Enter an integer that uniquely identifies the connected user.<br />
Max 31 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>peldsp display_connected_user  –cui RSK23</p>
<p>c_connected_user_id = 'RSK23'</p>
<p>c_last_remote_address = '188.221.3.95/4096'</p>
<p>c_last_connection_date = '070803 160124'</p>
<p>c_conn_max = '10'</p>
<p>c_connection_date = '070803 163024'</p>
<p>c_downloads_count = '3'</p>
<p>c_uploads_count = '0'</p>
<p>c_errors_count = '0'</p>
<p>c_average_speed = '4308728'</p>
<p>c_x_bytes = '2154364'</p>
<p> </p>
<p>For details of return parameters, refer to <a href="../connected_users_parameter_list#return_paras">Connected Users: Parameters list</a>.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="pelctl_dixonnect_user"></span>

## Disconnecting a Connected User: pelctl disconnect\_user

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code"><strong>pelctl disconnect_user</strong> [(-cui)]</span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to disconnect a specific Connected User.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span class="code">-connected_user_id (-cui)</span>: Enter an integer that uniquely identifies the Connected User.<br />
Max 31 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>peldsp select_connected_user</p>
<p>RSK23</p>
<p>WNT002</p>
<p>pelctl disconnect_user  –cui WNT002</p>
<p>peldsp select_connected_user</p>
<p>RSK23</p>         </td>
      </tr>
   </tbody>
</table>

<span id="pelctl_reset_connected_user"></span>

## Resetting a Connected User: pelctl reset\_connected\_user

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code"><strong>pelctl reset_connected_user</strong> [(-cui)]</span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to reset the Connected User quota to zero. This command is particularly useful when you are configuring the FTP<span class="code"> command_sensitivity</span> parameter. When a Connected User exceeds the command sensitivity quota, Gateway interrupts all current connections and forbids any further connections for this User.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span class="code">-connected_user_id (-cui)</span>: Enter an integer that uniquely identifies the Connected User.<br />
Max 31 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p><span style="font-weight: bold;">peldsp select_connected_user</span></p>
<p>RSK23</p>
<p>WNT002</p>
<p>pelctl reset_connected_user  –cui WNT002</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Connected Users: Parameters list](../connected_users_parameter_list)

[Monitoring Transfers](../../)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
