{
    "title": "User Request (USR)",
    "linkTitle": "User Request (USR)",
    "weight": "540"
}{{< Gateway/componentlongname  >}}: Messages and codes

This topic lists User Request log messages.

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="USR000S"></span>000</p>
<p><span id="USR001I"></span>001</p>
<p><span id="USR002W"></span>002</p>
<p><span id="USR003E"></span>003</p>
<p><span id="USR004F"></span>004</p>         </td>
         <td><p><strong>USR S SUCCESS %1</strong></p>
<p><span style="font-weight: bold;">USR I INFO %1</span></p>
<p><span style="font-weight: bold;">USR W WARNING %1</span></p>
<p><span style="font-weight: bold;">USR E ERROR %1</span></p>
<p><span style="font-weight: bold;">USR F FATAL %1</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><ul>
<li><span style="font-weight: bold;">000</span>: Success</li>
<li><span style="font-weight: bold;">001</span>: Information</li>
<li><span style="font-weight: bold;">002</span>: Warning</li>
<li><span style="font-weight: bold;">003</span>: Error</li>
<li><span style="font-weight: bold;">004</span>: Fatal</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>These messages are printed on a user exit request, using a log utility function that is supplied with the monitor (named <span style="font-weight: bold;">LogPrintf</span>). This function can be called from a user exit to print user messages in the log file. The message identification number (integer in the first column) is used by the utility function to select the user message type to print. This integer number is the first argument of the LogPrintf function:</p>
<ul>
<li><span style="font-weight: bold;">000</span>: successful operation in the user exit function</li>
<li><span style="font-weight: bold;">001</span>: information message</li>
<li><span style="font-weight: bold;">002</span>: warning condition detected in the user exit function</li>
<li><span style="font-weight: bold;">003</span>: error condition detected in the user exit function</li>
<li><span style="font-weight: bold;">004</span>: fatal error condition detected in the user exit function</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Test of the message whose content and format are defined by the user</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>None</p>         </td>
      </tr>
   </tbody>
</table>

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
