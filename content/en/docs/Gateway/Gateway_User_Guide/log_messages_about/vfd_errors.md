{
    "title": "VFD errors",
    "linkTitle": "VFD Errors",
    "weight": "550"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Messages and codes

The error messages in this topic are not logged directly, but are used as parts of other log messages.

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD100"></span>100</span></p>         </td>
         <td><p><span style="font-weight: bold;">memory allocation error</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered a system error while allocating memory.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the operating system configuration and memory usage.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD101"></span>101</span></p>         </td>
         <td><p><span style="font-weight: bold;">memory allocation error</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered a system error while reallocating memory.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the operating system configuration and memory usage.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="VFD102"></span>102</p>         </td>
         <td><p>configuration parameter name %1 is invalid</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD received an invalid configuration parameter</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Name of the unrecognized parameter</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD103"></span>103</span></p>         </td>
         <td><p><span style="font-weight: bold;">invalid session id</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD has been called with an invalid session identifier</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="VFD104"></span>104</p>         </td>
         <td><p>invalid root directory %1</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A VFD session has been initiated with an invalid root directory</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Root directory that caused the error</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the root directory parameter of the selected CGate and of its CGateGroup ancestors.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="VFD105"></span>105</p>         </td>
         <td><p>invalid home directory %1</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A VFD session has been initiated with an invalid home directory</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Home directory that caused the error</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the home directory parameter of the selected CGate and of its CGateGroup ancestors.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD106"></span>106</span></p>         </td>
         <td><p><span style="font-weight: bold;">cd up error, directory %1 position %2</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an error while going one level up in a directory (cd ..)</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Directory being moved up</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Parsing position when the error occurred</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="VFD107"></span>107</p>         </td>
         <td><p>parsing error, directory head type invalid</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an error while parsing a directory name</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD108"></span>108</span></p>         </td>
         <td><p><span style="font-weight: bold;">get path name error, directory %1 should be absolute</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an error while parsing a directory name.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Directory that caused the error</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD109"></span>109</span></p>         </td>
         <td><p><span style="font-weight: bold;">get last name error</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an error while parsing a directory name</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Directory that caused the error</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD110"></span>110</span></p>         </td>
         <td><p><span style="font-weight: bold;">node ident generation error</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an error when generating a new node ident</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD111"></span>111</span></p>         </td>
         <td><p><span style="font-weight: bold;">index record not found</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an error while reading in its database</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD112"></span>112</span></p>         </td>
         <td><p><span style="font-weight: bold;">index record not found</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an error while adding a new index entry</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD113"></span>113</span></p>         </td>
         <td><p><span style="font-weight: bold;">absolute directory expected</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an error while parsing a directory name.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="VFD114"></span>114</p>         </td>
         <td><p>home directory %1 is not under root directory</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A VFD session has been initiated with inconsistent root and home directories.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Home directory that caused the error</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the root and home directories parameters of the selected CGate and of its CGateGroup ancestors. The home directory must be under or of the same level as equal to the root directory.</p>
<p><span style="font-weight: bold;">Example:</span> If <code>/public/users</code> is the root directory, the home directory can be <code>/public/users/donald</code> but it cannot be <code>/public/our private stuff</code>.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD115"></span>115</span></p>         </td>
         <td><p><span style="font-weight: bold;">invalid option %d</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an invalid option</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD116"></span>116</span></p>         </td>
         <td><p><span style="font-weight: bold;">root directory overstep</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD failed to change current directory to an invalid location. This may happen when a command like "cd .." is supplied in the "/" directory.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="VFD117"></span>117</p>         </td>
         <td><p>invalid directory %1</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an error while parsing a directory.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Directory that caused the error</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="VFD118"></span>118</p>         </td>
         <td><p>current directory invalid %1</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an error while parsing a directory</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Directory that caused the error</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="VFD119"></span>119</p>         </td>
         <td><p>directory %1 already exists</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD could not create a directory because it already exists</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Directory that could not be created</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Use existing directory or choose another name for the new directory</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="VFD120"></span>120</p>         </td>
         <td><p>directory %1 creation error, parent bad type</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an error while creating a directory</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Directory that could not be created</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>A directory can be created only if its parent is a virtual directory. It is not possible to create a subdirectory in a mounted or real directory.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD121"></span>121</span></p>         </td>
         <td><p><span style="font-weight: bold;">this type of directory can't be mounted</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an error while mounting a directory</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>A directory can be mounted only if it is of the type virtual and is empty</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD122"></span>122</span></p>         </td>
         <td><p><span style="font-weight: bold;">mount directory %1 does not exist</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an error while mounting a directory</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>Directory that was not found on the file system</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>An attempt was made to mount a virtual directory on a real directory (file system) that does not exist. Check the directory to be mounted.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD123"></span>123</span></p>         </td>
         <td><p><span style="font-weight: bold;">only an empty directory can be mounted</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an error while mounting a directory</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>An attempt was made to mount a virtual directory that is not empty. This operation is forbidden.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD124"></span>124</span></p>         </td>
         <td><p><span style="font-weight: bold;">real entry name %1 is too long</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD found an entry (file or directory) whose name exceeds 127 characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>File or directory name that exceeds the limit</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>This may happen in real directories. The current limit is 127 characters for a file or directory name and 255 characters for a complete path name. This error prevents you from seeing the long file name but does not damage the VFD integrity.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD125"></span>125</span></p>         </td>
         <td><p><span style="font-weight: bold;">unknown entry type (st_mode=%1)</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered a real entry whose type is unknown</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Numerical value of the unrecognized entry type</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>st_mode is part of the system data type struct stat. Normally, entries have the type S_ISDIR or S_ISREG on UNIX and _S_IFDIR or _S_IFDIR on Windows.</p>
<p>Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD126"></span>126</span></p>         </td>
         <td><p><span style="font-weight: bold;">directory bad type, can not be unmounted</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an error while deleting a directory</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>An attempt was made to unmount a directory that is not a mounted directory.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD127"></span>127</span></p>         </td>
         <td><p><span style="font-weight: bold;">directory bad type, can not be deleted</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an error while unmounting a directory.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Only a virtual empty directory can be deleted. A real directory can not be deleted. A mounted directory has to be unmounted (so that it becomes virtual) before deletion.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD128"></span>128</span></p>         </td>
         <td><p><span style="font-weight: bold;">directory deletion not allowed</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an error while deleting a directory. </p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>This may happen if you try to delete the VFD root directory. The root directory must always exist and there should never be any need to delete it.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD129"></span>129</span></p>         </td>
         <td><p><span style="font-weight: bold;">only an empty directory can be deleted</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An attempt was made to delete a directory that is not empty. This operation is not allowed.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Empty the directory and try again</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD130"></span>130</span></p>         </td>
         <td><p><span style="font-weight: bold;">max number of directories has been reached</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an error while creating a directory. The maximum number of directories in the VFD is presently limited to 8192 (this includes virtual and mounted directories only, not real ones).</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Delete any unused directories and try again.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD131"></span>131</span></p>         </td>
         <td><p><span style="font-weight: bold;">directory motion not allowed</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an error while moving a directory.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Make sure that you are not trying to move:</p>
<ul>
<li>The root directory</li>
<li>The directory to a location that already contains a directory with the same name</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD132"></span>132</span></p>         </td>
         <td><p><span style="font-weight: bold;">directory bad type, can not be moved</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an error while moving a real directory. You can only move virtual and mounted directories (not real directories).</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check that the directory is not a real directory and that the target location is not a virtual directory.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="VFD133"></span>133</p>         </td>
         <td><p><span style="font-weight: bold;">directory already exists</span> </p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an error while creating a directory. The directory already exists.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>This is rather an internal message and error number 119 (see above) is most likely to be reported.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD134"></span>134</span></p>         </td>
         <td><p><span style="font-weight: bold;">directory bad type %1, can not register item</span> </p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an error while recording an item in a directory that is not virtual. Only virtual directories can contain items.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Type of directory that caused the error </p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD135"></span>135</span></p>         </td>
         <td><p><span style="font-weight: bold;">item already exists</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an error while recording an item. The item already exists in the selected directory.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD136"></span>136</span></p>         </td>
         <td><p><span style="font-weight: bold;">item not found</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an error while reading an item.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD137"></span>137</span></p>         </td>
         <td><p><span style="font-weight: bold;">directory resolution error, bad input parameter</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an error while reading an item.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD138"></span>138</span></p>         </td>
         <td><p><span style="font-weight: bold;">directory resolution error, not found</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an error while resolving a directory node ident.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD139"></span>139</span></p>         </td>
         <td><p><span style="font-weight: bold;">not implemented</span> </p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD was requested for a non-implemented service.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD140"></span>140</span></p>         </td>
         <td><p><span style="font-weight: bold;">initialization option invalid</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD was initialized with an unrecognized parameter.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD142"></span>142</span></p>         </td>
         <td><p><span style="font-weight: bold;">initialization error, shared index is down</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an error while accessing its index table.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD143"></span>143</span></p>         </td>
         <td><p><span style="font-weight: bold;">directory bad type, attributes cannot be set</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an error while setting directory attributes. You can only set attributes for virtual and mounted directories, not real directories.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check that the directory is not a real directory.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD144"></span>144</span></p>         </td>
         <td><p><span style="font-weight: bold;">translate name bad type %1</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an error while translating a name to the file system.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Type of directory that caused the error</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD145"></span>145</span></p>         </td>
         <td><p><span style="font-weight: bold;">data record already exists</span> </p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an error while writing in its database. The data record already exists.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD146"></span>146</span></p>         </td>
         <td><p><span style="font-weight: bold;">data record not found</span> </p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an error while reading in its database. Cannot find the data record.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD147"></span>147</span></p>         </td>
         <td><p><span style="font-weight: bold;">directory alias %1 is duplicated</span> </p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an error while setting a directory alias. The directory alias already exists in the VFD.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Alias that is duplicated</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Aliases must be unique in the VFD. Set a different alias for the directory.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD148"></span>148</span></p>         </td>
         <td><p><span style="font-weight: bold;">directory name %1 is reserved</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an error while creating a directory. Directory names beginning with "_item_" are reserved for internal needs (for item storage).</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>The reserved name that caused the error</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Do not use "_item" at the beginning of the directory name.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD149"></span>149</span></p>         </td>
         <td><p><span style="font-weight: bold;">mounted directory %1 is missing</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an error while accessing a mounted directory.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>File system directory that caused the error</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>A VFD directory has been mounted on a file system directory that is no longer present or reachable. Check the directory on your file system or unmount the VFD directory that points to it.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD150"></span>150</span></p>         </td>
         <td><p><span style="font-weight: bold;">root directory %1 should be absolute</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A VFD session was initiated with an invalid root directory.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Root directory that caused the error</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>The root directory must be absolute (that is, beginning with a slash). Check the root directory parameter of the selected CGate and of its parent CGateGroup.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD151"></span>151</span></p>         </td>
         <td><p><span style="font-weight: bold;">home directory %1 should be absolute</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A VFD session was initiated with an invalid home directory.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Home directory that caused the error</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>The home directory must be absolute (that is, beginning with a slash). Check the home directory parameter of the selected CGate and of its parentCGateGroup.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="VFD152"></span>152</p>         </td>
         <td><p><span style="font-weight: bold;">file deletion is impossible in a virtual directory</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>You cannot delete a file from a virtual directory.</p>         </td>
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
         <td><p><span id="VFD153"></span>153</p>         </td>
         <td><p>invalid file %s</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The file you selected is not valid.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Select a valid file</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="VFD154"></span>154</p>         </td>
         <td><p>permission denied</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>You do not have permission for this action.</p>         </td>
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
         <td><p><span id="VFD155"></span>155</p>         </td>
         <td><p>directory name too long (%s)</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The directory name you entered is too long.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>The maximum length of the directory name cannot exceed 128 characters.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="VFD156"></span>156</p>         </td>
         <td><p>directory path too long</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The directory path you entered is too long.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>The maximum length of the directory path cannot exceed 255 characters.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="VFD157"></span>157</p>         </td>
         <td><p>drives list overflow</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>If you use a Gateway GUI client, either remotely, or on the same machine as the Gateway server, when you mount a VFD, you select the real file directory to which you link the VFD from a <span style="font-style: italic;">Browse</span> window. The number of drives that Gateway can display in the <span style="font-style: italic;">Browse</span> window cannot exceed 255.</p>
<p>Refer to <a href="../../transfers_start_here/virtual_file_directory_start_here/working_with_virtual_file_directories_(gui)">Working with Virtual File Directories</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Reduce the number of devices accessible from your supporting machine.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="VFD158"></span>158</p>         </td>
         <td><p>no space left on device</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>No remaining disk space.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Reconfigure drive space.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD200"></span>200</span></p>         </td>
         <td><p><span style="font-weight: bold;">system error not implemented</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an error while using system services.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD201"></span>201</span></p>         </td>
         <td><p><span style="font-weight: bold;">system error mkdir %1, errno=%2</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an error in <span class="code">mkdir</span> system call.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Directory to be created</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>System errno value</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD202"></span>202</span></p>         </td>
         <td><p><span style="font-weight: bold;">system error creat %1, errno=%2</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an error in creat system call.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Path name to be created</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>System errno value</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD203"></span>203</span></p>         </td>
         <td><p><span style="font-weight: bold;">system error open %1, errno=%2</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an error in open system call.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>File to be opened</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>System errno value</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD204"></span>204</span></p>         </td>
         <td><p><span style="font-weight: bold;">system error close, errno=%1</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an error in close system call.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>System errno value</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD205"></span>205</span></p>         </td>
         <td><p><span style="font-weight: bold;">system error stat %1, errno=%2</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an error in stat system call.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>File to be stated</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>System errno value</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD206"></span>206</span></p>         </td>
         <td><p><span style="font-weight: bold;">system error read, errno=%1</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an error in read system call.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>System errno value</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD207"></span>207</span></p>         </td>
         <td><p><span style="font-weight: bold;">system error read count, %1 out of %2</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an error in read system call.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Number of bytes already read</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Number of bytes expected</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD208"></span>208</span></p>         </td>
         <td><p><span style="font-weight: bold;">system error write, errno=%1</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an error in write system call.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>System errno value</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD209"></span>209</span></p>         </td>
         <td><p><span style="font-weight: bold;">system error write count, %1 out of %2</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an error in write system call.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Number of bytes already written</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Number of bytes expected</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD210"></span>210</span></p>         </td>
         <td><p><span style="font-weight: bold;">system error lseek set, errno=%1</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an error in lseek system call</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>System errno value</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD211"></span>211</span></p>         </td>
         <td><p><span style="font-weight: bold;">system error lseek end, errno=%1</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an error in lseek system call.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>System errno value</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD212"></span>212</span></p>         </td>
         <td><p><span style="font-weight: bold;">system error lseek cur, errno=%1</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an error in lseek system call.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>System errno value</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD213"></span>213</span></p>         </td>
         <td><p><span style="font-weight: bold;">system error opendir %1, errno=%2</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an error in opendir system call.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Directory to be opened</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>System errno value</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD214"></span>214</span></p>         </td>
         <td><p><span style="font-weight: bold;">system error readdir, errno=%1</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an error in readdir system call.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>System errno value</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD215"></span>215</span></p>         </td>
         <td><p><span style="font-weight: bold;">system error closedir, errno=%1</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an error in closedir system call.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>System errno value</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD216"></span>216</span></p>         </td>
         <td><p><span style="font-weight: bold;">system error unlink %1, errno=%2</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an error in unlink system call.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>File to be unlinked</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>System errno value</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD217"></span>217</span></p>         </td>
         <td><p><span style="font-weight: bold;">system error shmget, errno=%1</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an error in shmget system call.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>System errno value</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="VFD218"></span>218</p>         </td>
         <td><p><span style="font-weight: bold;">system error shmat, errno=%1</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an error in shmat system call</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>System errno value</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="VFD219"></span>219</p>         </td>
         <td><p><span style="font-weight: bold;">system error shmdt, errno=%1</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an error in shmdt system call</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>System errno value</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD220"></span>220</span></p>         </td>
         <td><p><span style="font-weight: bold;">system error shmdt, errno=%1</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an error in shmctl system call</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>System errno value</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD221"></span>221</span></p>         </td>
         <td><p><span style="font-weight: bold;">system error ftok, errno=%1</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The VFD encountered an error in ftok system call</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>System errno value</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD222"></span>222</span></p>         </td>
         <td><p>system error rmdir %1, errno=%2</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error on removing directory</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Directory name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>System error number</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD223"></span>223</span></p>         </td>
         <td><p>system error rename %1 to %2, errno=%3</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error on renaming directory</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Old directory name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>New directory name</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>System error number</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD224"></span>224</span></p>         </td>
         <td><p>system error fsync, errno=%1</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>System error</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>System error number</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD225"></span>225</span></p>         </td>
         <td><p>system error getDrives, errno=%1</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>On Windows platforms only, error in getting list of drive devices</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>System error number</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD301"></span>301</span></p>         </td>
         <td><p><span style="font-weight: bold;">internal error 001</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An internal error occurred in the VFD</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD302"></span>302</span></p>         </td>
         <td><p><span style="font-weight: bold;">internal error 002</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An internal error occurred in the VFD</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD303"></span>303</span></p>         </td>
         <td><p><span style="font-weight: bold;">internal error 003</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An internal error occurred in the VFD</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD304"></span>304</span></p>         </td>
         <td><p><span style="font-weight: bold;">internal error 004</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An internal error occurred in the VFD</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD305"></span>305</span></p>         </td>
         <td><p><span style="font-weight: bold;">internal error 005</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An internal error occurred in the VFD</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="VFD306"></span>306</span></p>         </td>
         <td><p><span style="font-weight: bold;">internal error 006</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An internal error occurred in the VFD</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
