{
    "title": "File Transfer Protocol (FTP)",
    "linkTitle": "File Transfer Protocol (FTP)",
    "weight": "210"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Messages and codes

This topic lists FTP log messages.

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="FTP100E"></span>100</p>         </td>
         <td><p>FTP E ERROR %1 (%2) %3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An error condition has been detected. This message is used to report system errors (Input/Output, memory, network) or errors that cannot be explained by the protocol diagnostic code set.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Error text</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Refer to your platform documentation for system errors. For other errors, check protocol or Application parameters.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="FTP101I"></span>101</p>         </td>
         <td><p>FTP I TRACE %1</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>This message is used to trace FTP commands or FTP result codes sent to, or received from, a Remote Site. Each FTP command is in hexadecimal and text format (ASCII or EBCDIC, depending on host language).</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>FTP command or FTP result code</p>         </td>
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
         <td><p><span id="FTP102I"></span>102</p>         </td>
         <td><p>FTP I TRC_DATA %1</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>This message is used to trace data file or data list exchange with a Remote Site.</p>
<p>All data is in hexadecimal and in text format (ASCII or EBCDIC, depending on host language if possible).</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Data exchanged</p>         </td>
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
         <td><p><span id="FTP103W"></span>103</p>         </td>
         <td><p><span style="font-weight: bold;">FTP W TIMEOUT %1 (%2)</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>This message appears if timeout occurred for a specific connection.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
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
         <td><p><span id="FTP104E"></span>104</p>         </td>
         <td><p>FTP E ERROR Ftp script file %1 doesnt exist or cannot be opened</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>This message appears if a user uses a script file to send specific <span class="code">SITE</span> or <span class="code">QUOTE</span> commands in Initiator mode.</p>
<p>For example: SCRIPT file in user message 1 from Transfer Request or Application.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Name of the script file</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Abort transfer, if needed, and re-send with a correct script file name. Alternatively, change read access on file.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="FTP105E"></span>105</p>         </td>
         <td><p><span style="font-weight: bold;">FTP E ERROR Command and %1 isnt correct, parsing of command line %2 canceled</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>This message appears if timeout occurred for a specific connection.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Command in error</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Full user message or line in script</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Abort transfer, if needed, and restart the transfer with a correct user message 1 or line in script file.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="FTP106I"></span>106</p>         </td>
         <td><p>FTP I INFO Command '%1' ignored, not allowed to user</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Received an unknown FTP command.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Command in error</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Do not use this command any more.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="FTP107E"></span>107</p>         </td>
         <td><p><span style="font-weight: bold;">FTP E ERROR %1: data length %2 exceed %3</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An encoding/decoding error occurred during transfer.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Type of FTP encoding/decoding processing</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Length in error</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Maximum length as described in Transfer Request (or in Application used)</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check data length in transfer or in Application.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="FTP108E"></span>108</p>         </td>
         <td><p>FTP E ERROR %1 parameter too long: '%2'</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Type of FTP encoding/decoding processing</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Length in error</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p> </p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="FTP109E"></span>109</p>         </td>
         <td><p>FTP E ERROR Received file name '%1' is too long</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p> </p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="FTP110E"></span>110</p>         </td>
         <td><p><span style="font-weight: bold;">FTP E ERROR %1(%2) Data connection forbidden: remote IP addresses are different for control and data sessions</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A bounce attack was detected. The data connection is restricted.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>If the requested transfer is not a bounce attack, enable the <span class="code">change_data_addr</span> option in the Remote Site or the Proxy object to allow the transfer.</p>         </td>
      </tr>
   </tbody>
</table>

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="FTP110E"></span>111</p>         </td>
         <td><p><span style="font-weight: bold;">FTP W TIMEOUT (%1) %2 Login deadline expired</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td>Warning         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td>Gateway has cut a connection from a partner, that was not followed by a completed login within a reasonable timeout. This mechanism avoids DOS-type attacks, that attempt to keep one connection slot occupied without proceeding to log in.         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td>Remote alias         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>Possible causes</p>         </td>
         <td><ul>
<li>DOS attack</li>
<li>Network delays</li>
</ul>         </td>
      </tr>
      <tr>
         <td>Actions         </td>
         <td><ul>
<li>Monitor calling addresses for the "login timed out" connections, check for repeated connection attempts not followed by login attempts.</li>
<li>Check network bandwidth.</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="FTP120W"></span>120</p>         </td>
         <td><p><span style="font-weight: bold;">FTP W SEC_FAIL %1(%2) Security negotiation failure: security is disabled for control session</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An AUTH command was received while security is restricted on the corresponding session.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the configuration of the FTP client that sent this command, or configure Gateway to allow security.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="FTP121W"></span>121</p>         </td>
         <td><p><span style="font-weight: bold;">FTP W SEC_FAIL %1(%2) Security negotiation failure: security is mandatory for control session</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The FTP client tried to connect in an unsecured way on a session where security is mandatory.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the configuration of the FTP client that sent this command, or configure Gateway to allow unsecured communication.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="FTP122W"></span>122</p>         </td>
         <td><p><span style="font-weight: bold;">FTP W SEC_FAIL %1(%2) Security negotiation failure: security is disabled for data session</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>In server mode, the FTP client tried to negotiate a secured data session while this is restricted by configuration.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the configuration of the FTP client that negotiated this feature, or configure Gateway to allow a secured transfer.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="FTP123W"></span>123</p>         </td>
         <td><p><span style="font-weight: bold;">FTP W SEC_FAIL %1(%2) Security negociation failure: security is mandatory for data session</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>In server mode, the FTP client tried to negotiate an unsecured data session while security is required by configuration.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the configuration of the FTP client that negotiated this feature, or configure Gateway to allow an unsecured transfer.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="FTP124W"></span>124</p>         </td>
         <td><p><span style="font-weight: bold;">FTP W SEC_FAIL %1(%2) Security negociation failure: server refused '%3'</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>In client mode, the FTP server rejected a PROT command sent by Gateway, thus restricting the corresponding level of security for the next transfers. If the data policy of the Security Profile used is set to OPTIONAL, another option may be negotiated with the server.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>The rejected command: PROT P (secured transfer) or PROT C (plain transfer)</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>If the negative server response is the last one of the negotiation, check the configuration of the FTP server that rejected the command, or configure Gateway to be compatible with its policy.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="FTP130W"></span>130</p>         </td>
         <td><p><span style="font-weight: bold;">FTP W VFD_ERR %1(%2) Could not move '%3' to '%4': '%5'</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>In server mode, an error occurred while trying to execute a requested move/rename sequence (RNFR-RNTO).</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Source path</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Destination path</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Error message</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>The action must be taken according to the error message.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="FTP131W"></span>131</p>         </td>
         <td><p><span style="font-weight: bold;">FTP W VFD_ERR %1(%2) Could not create directory '%3': '%4'</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>In server mode, an error occurred while trying to execute a requested directory creation command (MKD).</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Directory</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Error message</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>The action must be taken according to the error message.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="FTP132W"></span>132</p>         </td>
         <td><p><span style="font-weight: bold;">FTP W VFD_ERR %1(%2) Could not delete file '%3': '%4'</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>In server mode, an error occurred while trying to execute a requested file deletion command (DELE).</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Directory</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Error message</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>The action must be taken according to the error message.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="FTP133W"></span>133</p>         </td>
         <td><p><span style="font-weight: bold;">FTP W VFD_ERR %1(%2) Could not remove directory '%3': '%4'</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>In server mode, an error occurred while trying to execute a requested directory deletion command (RMD).</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Directory</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Error message</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>The action must be taken according to the error message.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="FTP134W"></span>134</p>         </td>
         <td><p>FTP W VFD_ERR  %1(%2) Write permission denied for file '%3'. Current directory is '%4'</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Gateway, in server mode, has refused the user, connected FTP client, or other, the right to receive the requested file in the defined directory.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>File name</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Directory</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check that the user, the connected FTP client, or other, is authorized to upload this file. If the user is authorized, check the VFD rights defined in the CGate for the user, the connected FTP client, or other.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="FTP135W"></span>135</p>         </td>
         <td><p>FTP W VFD_ERR  %1(%2) Read permission denied for file '%3'. Current directory is '%4'</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Gateway, in server mode, has refused the user, connected FTP client, or other, the right to send the requested file to the defined directory.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>File name</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Directory</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check that the user, the connected FTP client, or other is authorized to download this file. If the user is authorized, check the VFD rights defined in the CGate for this user, the connected FTP client, or other.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="FTP210I"></span>210</p>         </td>
         <td><p><span style="font-weight: bold;">FTP I SEND_BEG %1 (%2) [%3] Start sending ftp file: %4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Beginning of an FTP data file transfer in Initiator/Sender or Responder/Sender mode.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Xfer local ident</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Protocol file name</p>         </td>
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
         <td><p><span id="FTP211I"></span>211</p>         </td>
         <td><p><span style="font-weight: bold;">FTP I SEND_BEG %1 (%2) [%3] Start sending file: %4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Beginning of an FTP data file transfer in Initiator/Sender or Responder/Sender mode.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Real file name on file system</p>         </td>
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
         <td><p><span id="FTP212I"></span>212</p>         </td>
         <td><p><span style="font-weight: bold;">FTP I SEND_RST %1 (%2) [%3] Restart sending ftp file: %4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Restart of an FTP data file transfer in Initiator/Sender or Responder/Sender mode.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Protocol file name</p>         </td>
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
         <td><p><span id="FTP213I"></span>213</p>         </td>
         <td><p><span style="font-weight: bold;">FTP I SEND_RST %1 (%2) [%3] Restart sending file: %4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Restart of an FTP data file transfer in Initiator/Sender or Responder/Sender mode.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Real file name on file system</p>         </td>
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
         <td><p><span id="FTP214I"></span>214</p>         </td>
         <td><p><span style="font-weight: bold;">FTP I SEND_END %1 (%2) [%3] End sending ftp file: %4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>End of an FTP data file transfer in Initiator/Sender or Responder/Sender mode.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Protocol file name</p>         </td>
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
         <td><p><span id="FTP215I"></span>215</p>         </td>
         <td><p><span style="font-weight: bold;">FTP I SEND_END %1 (%2) [%3] End sending file: %4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>End of an FTP data file transfer in Initiator/Sender or Responder/Sender mode.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Real file name on file system</p>         </td>
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
         <td><p><span id="FTP216E"></span>216</p>         </td>
         <td><p><span style="font-weight: bold;">FTP E SEND_ERR %1 (%2) [%3] Error sending (state %4) ftp file: %5</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error on an FTP data file transfer in Initiator/Sender or Responder/Sender mode.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Transfer state</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Protocol file name</p>         </td>
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
         <td><p><span id="FTP217E"></span>217</p>         </td>
         <td><p><span style="font-weight: bold;">FTP E SEND_ERR %1 (%2) [%3] Error sending (state %4) file: %5</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error on an FTP data file transfer in Initiator/Sender or Responder/Sender mode.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Transfer state</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Real file name on file system</p>         </td>
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
         <td><p><span id="FTP218W"></span>218</p>         </td>
         <td><p><span style="font-weight: bold;">FTP W SEND_STP %1 (%2) [%3] Stop sending (state %4) ftp file: %5</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>End of an FTP data file transfer in Initiator/Sender or Responder/Sender mode.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Transfer state</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Protocol file name</p>         </td>
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
         <td><p><span id="FTP219W"></span>219</p>         </td>
         <td><p><span style="font-weight: bold;">FTP W SEND_STP %1 (%2) [%3] Stop sending (state %4) file: %5</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>End of an FTP data file transfer in Initiator/Sender or Responder/Sender mode.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Transfer state</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Protocol file name</p>         </td>
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
         <td><p><span id="FTP230I"></span>230</p>         </td>
         <td><p><span style="font-weight: bold;">FTP I RECV_BEG %1 (%2) [%3] Start receiving ftp file: %4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Beginning of an FTP data file transfer in Initiator/Receiver or Responder/Receiver mode.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Protocol file name</p>         </td>
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
         <td><p><span id="FTP231I"></span>231</p>         </td>
         <td><p><span style="font-weight: bold;">FTP I RECV_BEG %1 (%2) [%3] Start receiving file: %4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Beginning of an FTP data file transfer in Initiator/Receiver or Responder/Receiver mode.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Real file name on file system</p>         </td>
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
         <td><p><span id="FTP232I"></span>232</p>         </td>
         <td><p><span style="font-weight: bold;">FTP I RECV_RST %1 (%2) [%3] Restart receiving ftp file: %4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Restart of an FTP data file transfer in Initiator/Receiver or Responder/Receiver mode.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Protocol file name</p>         </td>
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
         <td><p><span id="FTP233I"></span>233</p>         </td>
         <td><p><span style="font-weight: bold;">FTP I RECV_RST %1 (%2) [%3] Restart receiving file: %4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Restart of an FTP data file transfer in Initiator/Receiver or Responder/Receiver mode.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Real file name on file system</p>         </td>
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
         <td><p><span id="FTP234I"></span>234</p>         </td>
         <td><p><span style="font-weight: bold;">FTP I RECV_RST %1 (%2) [%3] Restart receiving file: %4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>End of an FTP data file transfer in Initiator/Receiver or Responder/Receiver mode.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Protocol file name</p>         </td>
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
         <td><p><span id="FTP235I"></span>235</p>         </td>
         <td><p><span style="font-weight: bold;">FTP I RECV_END %1 (%2) [%3] End receiving file: %4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>End of an FTP data file transfer in Initiator/Receiver or Responder/Receiver mode.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Real file name on file system</p>         </td>
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
         <td><p><span id="FTP236E"></span>236</p>         </td>
         <td><p><span style="font-weight: bold;">FTP E RECV_ERR %1 (%2) [%3] Error receiving (state %4) ftp file: %5</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>End of an FTP data file transfer in Initiator/Receiver or Responder/Receiver mode.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Transfer state</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Protocol file name</p>         </td>
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
         <td><p><span id="FTP237E"></span>237</p>         </td>
         <td><p><span style="font-weight: bold;">FTP E RECV_ERR %1 (%2) [%3] Error receiving (state %4) file: %5</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error on an FTP data file transfer in Initiator/Receiver or Responder/Receiver mode.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Transfer state</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Real file name on file system</p>         </td>
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
         <td><p><span id="FTP238W"></span>238</p>         </td>
         <td><p><span style="font-weight: bold;">FTP W RECV_STP %1 (%2) [%3] Stop receiving (state %4) ftp file: %5</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>End of an FTP data file transfer in Initiator/Receiver or Responder/Receiver mode.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Transfer state</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Protocol file name</p>         </td>
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
         <td><p><span id="FTP239W"></span>239</p>         </td>
         <td><p><span style="font-weight: bold;">FTP W RECV_STP %1 (%2) [%3] Stop receiving (state %4) file: %5</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>End of an FTP data file transfer in Initiator/Receiver or Responder/Receiver mode.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Transfer state</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Protocol file name</p>         </td>
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
         <td><p><span id="FTP240I"></span>240</p>         </td>
         <td><p><span style="font-weight: bold;">FTP I XACK_REQ %1(%2) [%3] send file acknowledge, org:%4, dest:%5, protocol_file name:%6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An FTP acknowledgment was sent.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Protocol originator</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Protocol destination</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Protocol file name</p>         </td>
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
         <td><p><span id="FTP241I"></span>241</p>         </td>
         <td><p><span style="font-weight: bold;">FTP I XACK_IND %1(%2) [%3] receive file acknowledge, org:%4, dest:%5, protocol_file name:%6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An FTP acknowledgment was received.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Protocol originator</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Protocol destination</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Protocol file name</p>         </td>
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
         <td><p><span id="FTP242E"></span>242</p>         </td>
         <td><p><span style="font-weight: bold;">FTP E CMD_ERR %1(%2) [%3] %4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An error response (&gt; 400) was received</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>The last command sent, followed by ": ", and the error response received</p>         </td>
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
         <td><p><span id="FTP250E"></span>250</p>         </td>
         <td><p><span style="font-weight: bold;">FTP E VFD_ERR %1 (%2) VFD init error: %3 - %4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An error occurred in FTP while initializing a VFD session</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>VFD error code</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>VFD error message (refer to <a href="../vfd_errors">VFD Errors</a> for more information)</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Depends on the VFD message</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="FTP260I"></span>260</p>         </td>
         <td><p>FTP I LIST_BEG %1 (%2) [%3] Start receiving ftp listing: %4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Beginning of an FTP listing.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Protocol file name</p>         </td>
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
         <td><p><span id="FTP261I"></span>261</p>         </td>
         <td><p>FTP I LIST_BEG %1 (%2) [%3] Start receiving listing: %4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Beginning of an FTP listing.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Real file name on file system</p>         </td>
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
         <td><p><span id="FTP264I"></span>264</p>         </td>
         <td><p>FTP I LIST_END %1 (%2) [%3] End receiving ftp listing: %4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>End of an FTP listing.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Protocol file name</p>         </td>
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
         <td><p><span id="FTP265I"></span>265</p>         </td>
         <td><p>FTP I LIST_END %1 (%2) [%3] End receiving listing: %4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>End of an FTP listing.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Protocol file name</p>         </td>
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
         <td><p><span id="FTP266E"></span>266</p>         </td>
         <td><p>FTP E LIST_ERR %1 (%2) [%3] Error receiving (state %4) ftp listing: %5</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error on an FTP listing.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Transfer state</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Protocol file name</p>         </td>
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
         <td><p><span id="FTP267E"></span>267</p>         </td>
         <td><p>FTP E LIST_ERR %1 (%2) [%3] Error receiving (state %4) listing: %5</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error on an FTP listing.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Transfer state</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Real file name on file system</p>         </td>
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
         <td><p><span id="FTP268W"></span>268</p>         </td>
         <td><p>FTP W LIST_STP %1 (%2) [%3] Stop receiving (state %4) ftp listing: %5</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>End of an FTP listing</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Transfer state</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Protocol file name</p>         </td>
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
         <td><p><span id="FTP269W"></span>269</p>         </td>
         <td><p>FTP W LIST_STP %1 (%2) [%3] Stop receiving (state %4) listing: %5</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>End of an FTP listing</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Transfer state</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Protocol file name</p>         </td>
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
         <td><p><span id="FTP300I"></span>300</p>         </td>
         <td><p>FTP I PX_LOAD %1(%2) Proxy %3 successfully loaded</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Proxy object has been found and loaded.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Proxy name</p>         </td>
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
         <td><p><span id="FTP301I"></span>301</p>         </td>
         <td><p>FTP I PX_CNX  %1(%2) Successfully connected to proxy %3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A connection has been established between Gateway and proxy.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Proxy name</p>         </td>
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
         <td><p><span id="FTP310I"></span>310</p>         </td>
         <td><p>FTP E PX_ERR  %1(%2) Could not access proxy %3: error %4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An error occurred while reading proxy object configuration.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Proxy name</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Meaningless</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p> </p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="FTP311I"></span>311</p>         </td>
         <td><p>FTP E PX_ERR  %1(%2) Proxy %3 is not an FTP proxy</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The proxy object does not refer to FTP protocol.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Proxy name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Verify that the object used as proxy in the ftp site is defined with ftp protocol.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="FTP312E"></span>312</p>         </td>
         <td><p>FTP E PX_ERR  %1(%2) Parsing error in proxy %3 script</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An error occurred while interpreting the script.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Proxy name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Correct command lines in the script.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="FTP313E"></span>313</p>         </td>
         <td><p>FTP E PX_ERR  %1(%2) Protocol error while connecting to proxy %3: %4 %5</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Protocol error while connecting to proxy</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Proxy name</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Error code</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Error message</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Verify protocol configuration.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="FTP314E"></span>314</p>         </td>
         <td><p>FTP E PX_ERR  %1(%2) Proxy %3 script file %4 access error %5: %6</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Unable to access to script file name</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Proxy name</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Script file name</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Error code (errno)</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Error message (errno message)</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Verify name of script file.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="FTP320I"></span>320</p>         </td>
         <td><p>FTP I SEC_OK  %1(%2) Data sessions mode switched to 'secure'</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Data session has been switched to secure mode.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
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
         <td><p><span id="FTP321I"></span>321</p>         </td>
         <td><p>FTP I SEC_OK  %1(%2) Data sessions mode switched to 'clear'</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Data session has been switched to clear mode.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
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
         <td><p><span id="FTP330I"></span>330</p>         </td>
         <td><p>FTP I VFD_OK  %1(%2) '%3' moved to '%4'</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A file name has been successfully renamed.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Old file name</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>New file name</p>         </td>
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
         <td><p><span id="FTP331I"></span>331</p>         </td>
         <td><p>FTP I VFD_OK  %1(%2) Created directory '%3'</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A directory has been successfully created.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Created directory name</p>         </td>
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
         <td><p><span id="FTP332I"></span>332</p>         </td>
         <td><p>FTP I VFD_OK  %1(%2) Deleted file '%3'</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A file has been successfully deleted.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Deleted file name</p>         </td>
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
         <td><p><span id="FTP333I"></span>333</p>         </td>
         <td><p>FTP I VFD_OK  %1(%2) Removed directory '%3'</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A directory has been successfully deleted.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Deleted directory name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>None</p>         </td>
      </tr>
   </tbody>
</table>

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
