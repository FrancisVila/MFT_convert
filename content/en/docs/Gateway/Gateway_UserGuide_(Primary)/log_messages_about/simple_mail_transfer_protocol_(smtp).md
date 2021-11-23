{
    "title": "Simple Mail Transfer Protocol (SMTP)",
    "linkTitle": "Simple Mail Transfer Protocol (SMTP)",
    "weight": "450"
}{{< Gateway/componentlongname  >}}: Messages and codes

This topic lists SMTP log messages.

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SMTP101I"></span>101</p>         </td>
         <td><p><strong>SMTP I TRACE (%1) [%2] %3</strong></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>This message is used to log unexpected events</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connected Site Ident</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Message</p>         </td>
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
         <td><p><span id="SMTP102I"></span>102</p>         </td>
         <td><p><span style="font-weight: bold;">SMTP I TRACE (%1) [%2] %3: %4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>This message is used to trace received and sent data</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connected Site Ident</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Direction: R for received, S for sent</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Data</p>         </td>
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
         <td><p><span id="SMTP103E"></span>103</p>         </td>
         <td><p><span style="font-weight: bold;">SMTP E ERROR (%1) [%2] Received an Invalid SMTP response ['%3']</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An invalid SMTP response was received from the server</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connected Site Ident</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Server response received</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Make sure you are connecting to an SMTP server</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SMTP104E"></span>104</p>         </td>
         <td><p><span style="font-weight: bold;">SMTP E ERROR (%1) [%2] Received negative answer %3 '%4' for command '%5'</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>SMTP server returned an error indication.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connected Site Ident</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>SMTP code returned by server</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Explanation string returned by server</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Last SMTP command sent</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Server probably does not support a required option, or a parameter was incorrect (invalid email address...)</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SMTP105E"></span>105</p>         </td>
         <td><p><span style="font-weight: bold;">SMTP E ERROR (%1) [%2] Invalid auth. method '%3' (%4)</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>This message is displayed when the SASL mechanism set in the Remote Site configuration is invalid.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connected Site Ident</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>SASL mechanism used</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Value of the SMTP SASL mechanism used (number)</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check Remote Site configuration.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SMTP106E"></span>106</p>         </td>
         <td><p><span style="font-weight: bold;">SMTP E ERROR (%1) [%2] Authentication error (%3): %4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>This message is displayed when the SASL authentication process fails.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connected Site Ident</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>SASL mechanism used</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Error message</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the SMTP server configuration and adapt the Remote Site settings.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SMTP107E"></span>107</p>         </td>
         <td><p><span style="font-weight: bold;">SMTP E ERROR (%1) [%2] local site '%3' or transfer '%4': Invalid Mail From Address: '%5'</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Invalid originator email address is being used (From).</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connected Site Ident</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local Site Ident</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Transfer local identifier</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Invalid address used (may be empty if address was not defined)</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Explicitly add a From email address when creating the Transfer Request or configure the Local Site with an email address.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SMTP108E"></span>108</p>         </td>
         <td><p><span style="font-weight: bold;">SMTP E ERROR (%1) [%2] dest. site '%3' or transfer '%4': Invalid Mail Destination Address: '%5'</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Invalid or empty destination email address is being used (To).</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connected Site Ident</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local Site Ident</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Transfer local identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Invalid address used (may be empty if address was not defined)</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Explicitly add a To email address when creating the Transfer Request, or configure the Remote Site with an email address.</p>
<p>Correct the invalid address used.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SMTP110I"></span>110</p>         </td>
         <td><p><span style="font-weight: bold;">SMTP I SEND_BEG (%1) [%2] %3 Start sending file: %4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>File transmission has started.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connected Site Ident</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Transfer local identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Physical path of the file being sent</p>         </td>
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
         <td><p><span id="SMTP111I"></span>111</p>         </td>
         <td><p><span style="font-weight: bold;">SMTP I SEND_END (%1) [%2] %3 End sending file: %4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The complete file is sent.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connected Site Ident</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Transfer local identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Physical path of the file being sent</p>         </td>
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
         <td><p><span id="SMTP112E"></span>112</p>         </td>
         <td><p><span style="font-weight: bold;">SMTP E SEND_ERR (%1) [%2] %3 Error sending file: %4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An error occurred while sending the file.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connected Site Ident</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Transfer local identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Physical path of the file being sent</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check reason, error and protocol diagnostic (if available), subsequent log message or in transfer details.</p>         </td>
      </tr>
   </tbody>
</table>

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
