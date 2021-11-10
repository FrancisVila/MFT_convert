{
    "title": "Statistics and script resolution modules (SR STATS)",
    "linkTitle": "Statistics and Script Resolution Modules (SR STATS)",
    "weight": "470"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Messages and codes

This topic lists SR STATS log messages.

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SR001E"></span>001</p>         </td>
         <td><p><span style="font-weight: bold;">SR E SBUNDEF undefined symbol %1 in %2 line %3</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The symbol name is undefined.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Symbol name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>File name or parameter</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Line number in the file</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Correct the symbol name.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SR002E"></span>002</p>         </td>
         <td><p><span style="font-weight: bold;">SR E SBINVAL invalid symbol in %1 line %1</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The symbol name is undefined.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>File name or parameter</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Line number in the file</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check for an invalid syntax symbol and correct the syntax.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SR003E"></span>003</p>         </td>
         <td><p><span style="font-weight: bold;">SR E LNTLONG line %1 too long in %2 script file</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The line length is greater than 240 characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Line number</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Script file name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Reduce the line length to 240 characters.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SR004E"></span>004</p>         </td>
         <td><p><span style="font-weight: bold;">SR E OPENERR open error: %1 file</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error opening the file which either does not exist or is impossible to create.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>File name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check for the error and correct it.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SR005E"></span>005</p>         </td>
         <td><p><span style="font-weight: bold;">SR E READERR read error: %1 file line %2</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error reading the file.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>File name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Line number in the file</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check for the error and correct it.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SR006E"></span>006</p>         </td>
         <td><p><span style="font-weight: bold;">SR E SPINVAL resolved script path %1 is invalid</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The resolved script path either does not contain the <span class="code">x_local_ident</span> symbol or contains other symbols.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Resolved script path</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Correct the resolved script path that must contain the <span class="code">x_local_ident</span> symbol, and only this symbol.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SR007E"></span>007</p>         </td>
         <td><p><span style="font-weight: bold;">SR E ALLOCERR memory allocation failed: STAT record format %1</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Not enough memory to handle the STAT record format.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>STAT record format number</p>         </td>
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
         <td><p><span id="SR008E"></span>008</p>         </td>
         <td><p><span style="font-weight: bold;">SR E TOOFRMT too many STAT record formats defined: maximum %1</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The maximum number of STAT record format defined in the STAT data dictionary file has been exceeded.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Maximum number of STAT record formats</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Reduce the number of STAT record formats.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SR009E"></span>009</p>         </td>
         <td><p><span style="font-weight: bold;">SR E FRINVAL invalid or undefined STAT record format %</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The maximum number of STAT record format defined in the STAT data dictionary file has been exceeded.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>STAT record format number</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>If the STAT record format is invalid, a previous error message is logged describing the error. If it is undefined, check for the error in the data dictionary STAT file or in the exit function <span style="font-style: italic;">ExitStatMessage</span>, and correct it.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SR010E"></span>010</p>         </td>
         <td><p><span style="font-weight: bold;">SR E RCTSHRT STAT record length exceeds %1 characters: format %2</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The stat record length exceeds the maximum record length.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Maximum record length</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>STAT record format number</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Modify the stat record.</p>         </td>
      </tr>
   </tbody>
</table>

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
