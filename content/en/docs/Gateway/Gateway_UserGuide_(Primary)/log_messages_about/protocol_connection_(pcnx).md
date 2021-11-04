{
    "title": "Protocol Connection (PCNX)",
    "linkTitle": "Protocol Connection (PCNX)",
    "weight": "380"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Messages and codes

This topic lists Protocol Connection log messages.

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PCNX001I"></span>001</p>         </td>
         <td><p>PCNX I SEL (%1) CGate %2 selected</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A CGate object matching the incoming connection has been found and selected. Several verifications are to be processed according to this CGate definition.</p>
<p><span style="font-weight: bold;">Note:</span> This message is only displayed if the value of the configuration variable <span class="code">cgate_log_level</span> is greater than or equal to <span style="font-weight: bold;">1</span>.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Selected CGate object name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>None</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PCNX002E"></span>002</p>         </td>
         <td><p><span style="font-weight: bold;">PCNX E CF (%1) Connection Failure, reason: %2</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The protocol connection through the CGate object has failed and the connection is rejected.</p>
<p><span style="font-weight: bold;">Note:</span> This message is displayed whatever the value of the configuration variable <span class="code">cgate_log_level</span>.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection failure reason (string) which can take one of the following values:</p>
<ul>
<li>No CGate matching the connection</li>
<li>Invalid FTP login password</li>
<li>Password expired</li>
<li>Password change forbidden</li>
<li>Password syntax invalid</li>
<li>New and old passwords are the same</li>
<li>Invalid HTTP login password</li>
<li>Invalid PHSE pre-connection login</li>
<li>Invalid PHSE pre-connection password</li>
<li>Invalid PHSE pre-connection client password</li>
<li>Invalid ODT client password</li>
<li>Invalid PEL client password</li>
<li>Invalid TLS security profile</li>
<li>Invalid TLS security user parameter</li>
<li>Insufficient TLS client authentication</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Refer to <a href="../../managing_partners_start_here/cgates_start_here/cgates_protocol_connection_phase">CGates: Protocol connection phase</a> for more details about the protocol connection mechanisms and check your configuration.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PCNX103I"></span>003</p>         </td>
         <td><p><span style="font-weight: bold;">PCNX I CONN (%1) %2 Connection Request Received</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An incoming connection request has been received.</p>
<p><span style="font-weight: bold;">Note:</span> This message is only displayed if the value of the configuration variable <span class="code">cgate_log_level</span> is greater than or equal to <span style="font-weight: bold;">2</span>.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection protocol type which can be either FTP, HTTP, PEL, ODT, or PHSE</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>None</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PCNX104I"></span>004</p>         </td>
         <td><p><span style="font-weight: bold;">PCNX I CONN (%1) %2</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An incoming connection request has been received. This message gives the details of what parameters have been received from the network. This message can be displayed on several lines. Its content is protocol dependent.</p>
<p><span style="font-weight: bold;">Note:</span> This message is only displayed if the value of the configuration variable <span class="code">cgate_log_level</span> is greater than or equal to <span style="font-weight: bold;">2</span>.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Protocol dependent message content:</p>
<ul>
<li>Common (FTP, HTTP and PHSE)
<ul>
<li>calling address, calling SAP, called address, called SAP</li>
<li>login user, login password</li>
</ul></li>
<li>HTTP specific parameters: HTTP host name</li>
<li>PHSE specific parameters: client ident, server ident</li>
<li>ODT and PEL: client ident</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>None</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PCNX105I"></span>005</p>         </td>
         <td><p><span style="font-weight: bold;">PCNX I CONN (%1) %2</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The protocol connection through the CGate object is successful. This message gives information about the output parameters obtained from the selected CGate hierarchy. This message can be displayed on several lines.</p>
<p><span style="font-weight: bold;">Note:</span> This message is only displayed if the value of the configuration variable <span class="code">cgate_log_level</span> is greater than or equal to <span style="font-weight: bold;">2</span>.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Protocol dependent message content:</p>
<ul>
<li>Common (FTP, HTTP, ODT, PEL, and PHSE)</li>
<li>Template Site</li>
<li>Route remote agent, route local agent, route destination ident, route originator ident</li>
<li>HTTP and FTP shared parameters</li>
<li>VFD root directory</li>
<li>VFD home directory</li>
<li>HTTP specific parameters</li>
<li>Home page</li>
<li>List template</li>
<li>PHSE specific parameters</li>
<li>Server password</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>None</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PCNX020I"></span>020</p>         </td>
         <td><p>020 PCNX I TPM (%1) Entry found in trading partner database for user %2</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Entry found in trading partner database for user</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>User name found in database</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>None</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="PCNX021E"></span>021</p>         </td>
         <td><p>021 PCNX E TPM_CF (%1) Connection Failure for user %2 reason : %3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Connection refused for user specified in parameter 2</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>User name found in database</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Reason for connection failure</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the reason displayed in parameter 3 and correct the error.</p>         </td>
      </tr>
   </tbody>
</table>

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
