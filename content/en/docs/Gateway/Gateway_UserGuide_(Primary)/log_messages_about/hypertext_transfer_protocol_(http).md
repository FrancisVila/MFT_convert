{
    "title": "Hypertext Transfer Protocol (HTTP)",
    "linkTitle": "Hypertext Transfer Protocol (HTTP)",
    "weight": "230"
}{{< Gateway/componentlongname  >}}: Messages and codes

This topic lists HTTP log messages.

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="HTTP101I"></span>101</p>         </td>
         <td><p>HTTP  I TRACE %1</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>This message is used to trace both received and sent data.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
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
         <td><p><span id="HTTP102I"></span>102</p>         </td>
         <td><p>HTTP  I TRACE %1(%2) %3 - %4 - %5 "%6" - length %7 - user-agent: %8</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An HTTP request has been received and is being processed. The request does not match a monitor transfer.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connected Site alias</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Local connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Request method used by the HTTP client (GET, PUT, POST)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Path requested (URI accessed)</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>HTTP return code</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Reason associated with the return code</p>         </td>
      </tr>
      <tr>
         <td><p>7</p>         </td>
         <td><p>Length of the data sent by the client</p>         </td>
      </tr>
      <tr>
         <td><p>8</p>         </td>
         <td><p>"User-Agent" field sent by the client. This field is typically used to recognize the kind of client connected.</p>         </td>
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
         <td><p><span id="HTTP103I"></span>103</p>         </td>
         <td><p><strong>HTTP  I TRACE %1(%2) [%9] %3 - %4 - %5 "%6" - length %7 - user-agent: %8</strong></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A Transfer Request has been received and is being processed.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connected Site alias</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Local connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Request method used by the HTTP client (GET, PUT, POST)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Path requested (URI accessed)</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>HTTP return code</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Reason associated with the return code</p>         </td>
      </tr>
      <tr>
         <td><p>7</p>         </td>
         <td><p>Length of the data sent by the client</p>         </td>
      </tr>
      <tr>
         <td><p>8</p>         </td>
         <td><p>"User-Agent" field sent by the client. This field is typically used to recognize the kind of client connected.</p>         </td>
      </tr>
      <tr>
         <td><p>9</p>         </td>
         <td><p>Local transfer number</p>         </td>
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
         <td><p><span id="HTTP104I"></span>104</p>         </td>
         <td><p><span style="font-weight: bold;">HTTP  I TRACE (%1) %2 %3</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>This message is used to trace received and sent HTTP headers.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Direction (<span style="font-weight: bold;">R</span> for read and <span style="font-weight: bold;">S</span> for sent)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Header field</p>         </td>
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
         <td><p><span id="HTTP105I"></span>105</p>         </td>
         <td><p><span style="font-weight: bold;">HTTP  I TRACE HTTP %1"server is using identification method: %2</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>This message is displayed when the server is started and each time the identification method is changed.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Server using the authentication method</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>New authentication method</p>         </td>
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
         <td><p><span id="HTTP110E"></span>110</p>         </td>
         <td><p><span style="font-weight: bold;">HTTP  E ERROR %1(%2) Can't load file %3</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A file could not be loaded (configuration file or directory listing template file).</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connected Site alias</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Local connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>File path</p>         </td>
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
         <td><p><span id="HTTP111E"></span>111</p>         </td>
         <td><p><span style="font-weight: bold;">HTTP  E ERROR  %1(%2) [%3] %4: error %5 (%6)</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An unexpected error occurred while manipulating a resource.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connected Site alias</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Local connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local number of the transfer (0 if not available)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Current operation being made or resource being manipulated</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Error number or string</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Description (if available)</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check configuration of the resource being used.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="HTTP112E"></span>112</p>         </td>
         <td><p><span style="font-weight: bold;">HTTP  E ERROR  %1(%2) No directory listing template available</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Directory could not be listed because no listing template is defined.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connected Site alias</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Local connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Fill in the list template field of the selected CGate or the default list template in the HTTP configuration</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="HTTP130W"></span>130</p>         </td>
         <td><p>HTTP  W VFD_ERR  %1(%2) Could not move '%3' to '%4': '%5'</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Directory could not be moved.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connected Site alias</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Local connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Old directory name</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>New directory name</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Error message</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Action depends on the error message.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="HTTP131W"></span>131</p>         </td>
         <td><p>HTTP  W VFD_ERR  %1(%2) Could not create directory '%3': '%4'</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Directory could not be created.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connected Site alias</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Local connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Directory name</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Error message</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Action depends on the error message.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="HTTP132W"></span>132</p>         </td>
         <td><p>HTTP  W VFD_ERR  %1(%2) Could not delete '%3': '%4'</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Directory could not be deleted.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connected Site alias</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Local connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p><span style="font-weight: normal;">Directory name</span></p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p><span style="font-weight: normal;">Error message</span></p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Action depends on the error message.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="HTTP131W"></span>133</p>         </td>
         <td><p><strong>HTTP W VFD_ERR %1(%2) Could not list '%3': '%4'</strong></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Directory could not be listed.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connected Site alias</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Local connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Directory name</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Error message</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Action depends on the error message.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="HTTP131W"></span>134</p>         </td>
         <td><p><strong>HTTP W VFD_ERR %1(%2) Could not read '%3': '%4'</strong></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Directory could not be read.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connected Site alias</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Local connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Directory name</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Error message</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Action depends on the error message.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="HTTP131W"></span>135</p>         </td>
         <td><p><strong>HTTP W VFD_ERR %1(%2) Write permission denied for file '%3'. Current directory is '%4'</strong></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>File could not be written.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connected Site alias</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Local connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>File name</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Directory message</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check VFD access rights.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="HTTP150I"></span>150</p>         </td>
         <td><p>HTTP  I VFD_OK  %1(%2) '%3' moved to '%4'</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Directory was moved.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p><span style="font-weight: normal;">Connected Site alias</span></p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Local connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p><span style="font-weight: normal;">Old directory name</span></p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>New directory name</p>         </td>
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
         <td><p><span id="HTTP151I"></span>151</p>         </td>
         <td><p>HTTP  I VFD_OK  %1(%2) Created directory '%3'</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Directory was created.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p><span style="font-weight: normal;">Connected Site alias</span></p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Local connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p><span style="font-weight: normal;">Directory name</span></p>         </td>
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
         <td><p><span id="HTTP152I"></span>152</p>         </td>
         <td><p>HTTP  I VFD_OK  %1(%2) Deleted file '%3'</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>File was deleted.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p><span style="font-weight: normal;">Connected Site alias</span></p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Local connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p><span style="font-weight: normal;">File name</span></p>         </td>
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
         <td><p><span id="HTTP153I"></span>153</p>         </td>
         <td><p>HTTP  I VFD_OK  %1(%2) Deleted directory '%3'</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Directory was deleted.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p><span style="font-weight: normal;">Connected Site alias</span></p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Local connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p><span style="font-weight: normal;">Directory name</span></p>         </td>
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
         <td><p><span id="HTTP211I"></span>211</p>         </td>
         <td><p><span style="font-weight: bold;">HTTP  I SEND_BEG %1(%2) [%3] %4 Start sending file: %5</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The file is starting to be sent.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connected Site alias</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Local connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local number of the transfer (0 if not available)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Protocol destination</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
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
         <td><p><span id="HTTP215I"></span>215</p>         </td>
         <td><p><span style="font-weight: bold;">HTTP  I SEND_END %1(%2) [%3] %4 End sending file: %5</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The file has been completely sent.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connected Site alias</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Local connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local number of the transfer (0 if not available)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Protocol destination</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Physical path of the file sent</p>         </td>
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
         <td><p><span id="HTTP217E"></span>217</p>         </td>
         <td><p><span style="font-weight: bold;">HTTP  E SEND_ERR %1(%2) [%3] %4 Error sending file: %5</span></p>         </td>
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
         <td><p>Connected Site alias</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Local connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local number of the transfer (0 if not available)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Protocol destination</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
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
         <td><p><span id="HTTP231I"></span>231</p>         </td>
         <td><p><span style="font-weight: bold;">HTTP  I RECV_BEG %1(%2) [%3] %4 Start receiving file: %5</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A  file starts to be received.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connected Site alias</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Local connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local number of the transfer (0 if not available)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Protocol destination</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Physical path of the file being received</p>         </td>
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
         <td><p><span id="HTTP235I"></span>235</p>         </td>
         <td><p><span style="font-weight: bold;">HTTP  I RECV_END %1(%2) [%3] %4 End receiving file: %5</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The file has been completely received.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connected Site alias</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Local connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local number of the transfer (0 if not available)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Protocol destination</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Physical path of the file received</p>         </td>
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
         <td><p><span id="HTTP237E"></span>237</p>         </td>
         <td><p><span style="font-weight: bold;">HTTP  E RECV_ERR %1(%2) [%3] %4 Error receiving file: %5</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An error occurred while receiving the file.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connected Site alias</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Local connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local number of the transfer (0 if not available)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Protocol destination</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Physical path of the file being received</p>         </td>
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
         <td><p><span id="HTTP240I"></span>240</p>         </td>
         <td><p>HTTP  I LIST_BEG %1(%2) [%3] %4 Start receiving listing: %5</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Start of file reception.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connected Site alias</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Local connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local number of the transfer (<span style="font-weight: bold;">0</span> if not available)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Protocol destination</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Physical path of the file being received</p>         </td>
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
         <td><p><span id="HTTP241I"></span>241</p>         </td>
         <td><p>HTTP  I LIST_END %1(%2) [%3] %4 End receiving listing: %5</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The file has been completely received.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connected Site alias</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Local connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local number of the transfer (<span style="font-weight: bold;">0</span> if not available)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Protocol destination</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Physical path of the file being received</p>         </td>
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
         <td><p><span id="HTTP242E"></span>242</p>         </td>
         <td><p>HTTP  E LIST_ERR %1(%2) [%3] %4 Error receiving listing: %5</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An error occurred while receiving the file.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connected Site alias</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Local connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local number of the transfer (<span style="font-weight: bold;">0</span> if not available)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Protocol destination</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Physical path of the file being received</p>         </td>
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
         <td><p><span id="HTTP300I"></span>300</p>         </td>
         <td><p><span style="font-weight: bold;">HTTP  I TRACE %1(%2) [%3] Sending request: %4 (length %5)</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A request is being sent to the server.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connected Site alias</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Local connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local number of the transfer (0 if not available)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Request sent (for example, GET / HTTP/1.0)</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Length of data to be sent</p>         </td>
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
         <td><p><span id="HTTP301E"></span>301</p>         </td>
         <td><p><span style="font-weight: bold;">HTTP  E RECV_ERR %1(%2) [%3] Request refused by server (%4 '%5')</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Request has been rejected by the server (returned code &gt;= 300).</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connected Site alias</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Local connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local number of the transfer (0 if not available)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Return code</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Returned description</p>         </td>
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
         <td><p><span id="HTTP302I"></span>302</p>         </td>
         <td><p><span style="font-weight: bold;">HTTP  I TRACE %1(%2) [%3] Receive response: %4 (length %5)</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A response has been received.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connected Site alias</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Local connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local number of the transfer (0 if not available)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Answer (for example, HTTP/1.0 200 OK)</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Length of the data to be received</p>         </td>
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
         <td><p><span id="HTTP303E"></span>303</p>         </td>
         <td><p><span style="font-weight: bold;">HTTP  E ERROR %1(%2) [%3] Invalid server response: %4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Some elements could not be recognized or accepted in the response from the server.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connected Site alias</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Local connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local number of the transfer (0 if not available)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Answer (for example, HTTP/1.0 200 OK)</p>         </td>
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
         <td><p><span id="HTTP304E"></span>304</p>         </td>
         <td><p><span style="font-weight: bold;">HTTP  E AUTH_ERR %1(%2) [%3] Auth rejected by server (%4 '%5')</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The server returned a negative answer to the first request used (identification).</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connected Site alias</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Local connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local number of the transfer (0 if not available)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Return code (&gt;= 300)</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Returned description</p>         </td>
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
         <td><p><span id="HTTP131W"></span>305</p>         </td>
         <td><p><strong>HTTP W REDIR_W %1(%2) [%3] Receive response: %4 (length %5); please check/update the configuration</strong></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A “HTTP 301 Moved Permanently” was received.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connected Site alias</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Local connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local number of the transfer (0 if not available)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Answer (for example, HTTP/1.0 301 Moved Permanently)</p>         </td>
      </tr>
      <tr>
         <td><strong>5</strong>         </td>
         <td>Length of the data to be received         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Update the configuration to reflect the new address.</p>         </td>
      </tr>
   </tbody>
</table>

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="HTTP131W"></span>306</p>         </td>
         <td><strong>HTTP I NTLM_1 %1(%2) [%3] %4 NTLM%5 Authentication %6</strong>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An NTLM authentication operation was performed.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connected Site alias</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Local connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local number of the transfer (0 if not available)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Direction (Receiving or Sending an NTLM authentication message)</p>         </td>
      </tr>
      <tr>
         <td><strong>5</strong>         </td>
         <td>NTLM protocol version (NTLM or NTLM2)         </td>
      </tr>
      <tr>
         <td><strong>6</strong>         </td>
         <td>Type of the NTLM authentication message         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>None.</p>         </td>
      </tr>
   </tbody>
</table>

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="HTTP131W"></span>400</p>         </td>
         <td><strong>HTTP W TIMEOUT %1(%2) Login deadline expired</strong>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td>Gateway has cut a connection from a partner, that was not followed by a completed login within a reasonable timeout. This mechanism avoids DOS-type attacks, that attempt to keep one connection slot occupied without proceeding to log in.         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td>Remote protocol identifier         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td>Connection identifier         </td>
      </tr>
      <tr>
         <td><p>Actions</p>         </td>
         <td><ul>
<li>Monitor calling addresses for the "login timed out" connections. Check for repeated connection attempts not followed by login attempts</li>
<li>Check network bandwidth</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

 

 

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
