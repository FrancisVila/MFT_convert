{
    "title": "Working with Remote Sites (command line)",
    "linkTitle": "Working with Remote Sites",
    "weight": "180"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Partners

<span class="code" style="font-weight: bold;">[peladm create\_site](#peladm_create_site)</span>

<span class="code" style="font-weight: bold;">[peladm update\_site](#peladm_update_site)</span>

<span class="code" style="font-weight: bold;">[peladm delete\_site](#peladm_delete_site)</span>

<span class="code" style="font-weight: bold;">[peldsp select\_site](#peldsp_select_site)</span>

<span class="code" style="font-weight: bold;">[peldsp display\_site](#peldsp_display_site)</span>

<span class="code" style="font-weight: bold;">[peldsp status\_site](#peldsp_status_site)</span>

<span class="code" style="font-weight: bold;">[pelctl start\_site](#pelctl_start_site)</span>

<span class="code" style="font-weight: bold;">[pelctl stop\_site](#pelctl_stop_site)</span>

<span id="peladm_create_site"></span>

## Creating Remote Sites: peladm create\_site

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code">peladm create_site {-alias}</span> [<span style="font-weight: normal;">optional parameters</span>]</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to create a Remote Site. The command has one mandatory parameter and many optional parameters.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>Mandatory</p>
<p><span class="code">-alias (-a)</span>: Enter a Site alias for the Remote Site you are creating.</p>         </td>
      </tr>
      <tr>
         <td><p>Optional parameters</p>
<p>Refer to <a href="../sites_parameter_list">Site objects: Parameters List</a>.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example 1</strong></p>         </td>
         <td><p>The following command creates a Remote Site with the properties:</p>
<ul>
<li>alias: SITE</li>
<li>protocol: PeSIT HS E</li>
<li>network type: TCP/IP</li>
<li>called address: 1922575869</li>
<li>max data block size: 2500</li>
</ul>
<p>peladm create_site</p>
<p>   -a SITE</p>
<p>   -pr PHSE</p>
<p>   -ct TCPIP</p>
<p>   -dest_address 1922575869</p>
<p>   -ds 2500</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example 2</strong></p>         </td>
         <td><p>The following command creates a Remote Site with the properties:</p>
<ul>
<li>alias: SWIFT_AP_1</li>
<li>protocol: SWIFTNet</li>
</ul>
<p>peladm create_site</p>
<p>   -alias SWIFT_AP_1</p>
<p>   -protocol SWIFTNET</p>
<p>   -login_ident user1</p>
<p>   -login_password password1</p>
<p>   -init_conn_max 4</p>
<p>   -resp_conn_max 1</p>
<p>   -ra_instance Ra1</p>
<p>   -message_partner appli1</p>
<p>   -event_end_point appli1_ep</p>         </td>
      </tr>
   </tbody>
</table>

<span id="peladm_update_site"></span>

## Modifying Remote Sites: peladm update\_site

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code">peladm update_site {-alias}</span> [<span style="font-weight: normal;">optional parameters</span>]</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to modify the properties of a Remote Site that you identify by its alias. You can modify all values except the alias.</p>
<p>The syntax is the same as for the <span class="code" style="font-weight: bold;">peladm create_site</span> command.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>Mandatory</p>
<p><span class="code">-alias (-a)</span>: Enter a Site alias for the Remote Site you are modifying.</p>         </td>
      </tr>
      <tr>
         <td><p>Optional parameters</p>
<p>Refer to <a href="../sites_parameter_list">Site objects: Parameters List</a>.</p>
<p>Enter values for the parameters you want to modify.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following command resets the protocol for the Remote Site SITE to PeSIT HS E.</p>
<p>peladm update_site  -a SITE  <span style="font-weight: bold;">-pr PHSE</span></p>         </td>
      </tr>
   </tbody>
</table>

<span id="peladm_delete_site"></span>

## Deleting Remote Sites: peladm delete\_site

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code">peladm delete_site {-alias}</span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to delete a Remote Site that you identify by its alias.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>Mandatory</p>
<p><span class="code">-alias (-a)</span>: Enter a Site alias for the Remote Site you are deleting.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following command deletes the Remote Site SITE.</p>
<p>peladm delete_site  -a SITE</p>         </td>
      </tr>
   </tbody>
</table>

<span id="peldsp_select_site"></span>

## Selecting Remote Sites: peldsp select\_site

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code">peldsp select_site [-alias] [-proto_ident] [-group] [-protocol] [comm_type] [dest_address]</span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to select the Remote Sites that match the selection criteria entered as parameters.</p>
<p>All parameters are optional. To list all Remote Sites, enter no parameters. Enter the command again using the optional parameters to refine your selection.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span class="code">-alias (-a)</span>: Enter a Site alias for the Remote Site as selection criteria.</p>         </td>
      </tr>
      <tr>
         <td><p>Not for FTP or SFTP.</p>
<p><span class="code">-proto_ident (-pi)</span>: Enter a Site protocol name as selection criteria.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-group (-gr)</span>: Enter the Group name of the Site or Sites you want to display.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-protocol (-pr)</span>: Enter the protocol used by the Site or Sites you want to display. Enter one of the following values:</p>
<ul>
<li><span style="font-weight: bold;">PEL</span> (Default)</li>
<li><span style="font-weight: bold;">PHSE</span> = PeSIT HS E</li>
<li><span style="font-weight: bold;">PHSD</span> = PeSIT HS D</li>
<li><span style="font-weight: bold;">FTP</span></li>
<li>HTTP</li>
<li><span style="font-weight: bold;">FTP_HTTP</span></li>
<li><span style="font-weight: bold;">ODETTE</span> = OFTP</li>
<li><span style="font-weight: bold;">SFTP</span></li>
<li><span style="font-weight: bold;">SMTP</span></li>
<li><span style="font-weight: bold;">POP3</span></li>
<li>TO_GTW</li>
<li>FROM_GTW</li>
<li>AS2</li>
<li>AS3</li>
<li>AS1_POP3</li>
<li>AS1_SMTP</li>
<li>RN_POP3</li>
<li>RN_SMTP</li>
<li>RN_HTTP</li>
<li>SWIFTNet</li>
<li>JMS</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-comm_type (-ct)</span>: Enter the type of communications interface used by the Site or Sites you want to display. Enter one of the following values:</p>
<ul>
<li>PAD</li>
<li>TCPIP (default)</li>
<li>LU62</li>
<li>DSA</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-dest_address (-da)</span>: Enter the destination address of the Site or Sites you want to display.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example 1</strong></p>         </td>
         <td><p>The following command returns the list of Remote Sites that use PEL protocol and the TCP/IP network type.</p>
<p>peldsp select_site  -pr PEL  -ct TCPIP</p>
<p>Gateway lists the Remote Site aliases that match the selection criteria:</p>
<p>IMTPLX01</p>
<p>UXTPLX01</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example 2</strong></p>         </td>
         <td><p>Gateway handles each string parameter as a truncated search key. The following example returns the list of Remote Sites whose aliases begin with U and whose main destination address begins with 192.</p>
<p>peldsp select_site  -a U  -dest_address 192</p>
<p>Returns, for example:</p>
<p>UXTPDX01</p>
<p>UXTPDT02</p>
<p>UXTPLX01</p>
<p>Where the displayed results conform to the criteria.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="peldsp_display_site"></span>

## Displaying Remote Sites: peldsp display\_site

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code">peldsp display_site {-alias}</span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to display the properties of a specific Remote Site that you identify by its alias.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>Mandatory</p>
<p><span class="code">-alias (-a)</span>: Enter a Site alias for the Remote Site for which you want to display the properties.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>Gateway displays each parameter of the specified Site on a separate line, in the format:</p>
<p>name_of_field="value"</p>
<p>Each field name is prefixed by the string "<span class="code" style="font-weight: bold;">s_</span>", referring to the <span style="font-weight: bold;">S</span>ite object.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="peldsp_status_site"></span>

## Displaying Remote Site status: peldsp status\_site

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code">peldsp status_site {-alias}</span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to display the initial and dynamic status of a Remote Site that you identify by its alias.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>Mandatory</p>
<p><span class="code">-alias (-a)</span>: Enter a Site alias for the Remote Site for which you want to display the status.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>Gateway displays each status parameter of the specified Site on a separate line, in the format:</p>
<p>name_of_field="value"</p>
<p>Each field name is prefixed by the string "<span class="code" style="font-weight: bold;">s_</span>", referring to the <span style="font-weight: bold;">S</span>ite object.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="pelctl_start_site"></span>

## Starting Remote Sites: pelctl start\_site

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code">pelctl start_site {-alias} [-init_mode] [-resp_mode] [-commpath_used] [-trace_mode] [-poll_mode]</span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to dynamically activate a Site. When you start a Site, its state changes from <span style="font-weight: bold;">NO</span> to <span style="font-weight: bold;">YES</span> (for a specified connection mode).</p>
<p>Gateway initiates no connections, Transfers, or any other operations with inactive Sites.</p>
<p>If the Site is not already active, the start operation activates the Site and:</p>
<ul>
<li>resets counters and timers for the Site, in particular:
<ul>
<li>current number of unsuccessful connection attempts (<span class="code">Site retry_count</span> parameter)</li>
<li>current interval between connection attempts (<span class="code">Site retry_delay</span> parameter)</li>
</ul></li>
<li>immediately processes all Transfer Requests with <span style="font-weight: bold;">to begin</span> status</li>
</ul>
<p>If the Site is already active, the operation still resets Site counters and timers, and processes Transfer Requests with <span style="font-weight: bold;">to begin</span> status.</p>
<p>To change the initial state for a Site (that is, the default state that Gateway takes into account on startup), you must update the initial modes for that Site via the <span class="code" style="font-weight: bold;">peladm update_site</span> command. However, all modifications to the Site initialization modes take effect dynamically, and are lost when you restart Gateway.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>Mandatory</p>
<p><span class="code">-alias (-a)</span>: Enter a Site alias for the Remote Site that you want to start.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-init_mode (-im)</span>: Enter this parameter to start the Site in Initiator Site mode.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-resp_mode (-rm)</span>: Enter this parameter to start the Site in Responder Site mode.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-commpath_used (-cu)</span>: Enter the communications path used to connect the Site. Enter one of the values:</p>
<ul>
<li><span style="font-weight: bold;">MAIN</span> = Main communication address</li>
<li><span style="font-weight: bold;">ALT1</span> = First alternative communication address</li>
<li><span style="font-weight: bold;">ALT2</span> = Second alternative communication address</li>
<li><span style="font-weight: bold;">ALT3</span> = Third alternative communication address</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-trace_mode (-tm)</span>: Enter this parameter to activate the trace mode.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-poll_mode (-pm)</span>: Enter this parameter to activate the polling function.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following command starts the Site with the alias SITENAME in both Initiator mode and Responder mode.</p>
<p>pelctl start_site  -alias SITENAME</p>
<p>   -init_mode</p>
<p>   -resp_mode</p>         </td>
      </tr>
   </tbody>
</table>

<span id="pelctl_stop_site"></span>

## Stopping Remote Sites: pelctl stop\_site

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code">pelctl stop_site {-alias} [-init_mode] [-resp_mode] [-trace_mode] [-poll_mode]</span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to disable the Transfer or trace activity on a Remote Site.</p>
<p>Stopping a Site involves changing its state from <span style="font-weight: bold;">YES</span> to <span style="font-weight: bold;">NO</span> (for specified connection modes).</p>
<p>Transfers that are currently in progress continue until they are completed (on condition that no error stops their execution). Gateway initiates no connections, transfers, or any other operations with inactive Sites. Stopping an inactive Site has no effect.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>Mandatory</p>
<p><span class="code">-alias (-a)</span>: Enter a Site alias for the Remote Site that you want to start.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-init_mode (-im)</span>: Enter this parameter to disable Initiator mode for the selected Site.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-resp_mode (-rm)</span>: Enter this parameter to disable Responder mode for the selected Site.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-trace_mode (-tm)</span>: Enter this parameter to disable trace mode for the selected Site.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-poll_mode (-pm)</span>: Enter this parameter to disable polling for the selected Site.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following command disables Initiator mode and Responder mode for the Site SITENAME.</p>
<p>pelctl stop_site  -alias SITENAME</p>
<p>   -init_mode</p>
<p>   -resp_mode</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Site objects: Parameters List](../sites_parameter_list)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
