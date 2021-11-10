{
    "title": "Monitor checking (CHK)",
    "linkTitle": "Monitor checking (CHK)",
    "weight": "310"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Messages and codes

This topic lists Monitor checking log messages.

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="CHK001S"></span>001</p>         </td>
         <td><p><span style="font-weight: bold;">CHK S CHKOK Monitor check ended successfully</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Success</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Monitor checked all resources successfully before starting.</p>         </td>
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
         <td><p><span id="CHK002I"></span>002</p>         </td>
         <td><p>CHK I CHKBEGIN Start Monitor checking</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Monitor starts resource checking procedure.</p>         </td>
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
         <td><p><span id="CHK050S"></span>050</p>         </td>
         <td><p><span style="font-weight: bold;">CHK S RCVXFOK Recovered mailbox successfully</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Success</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The recovery of master Mailbox was successful.</p>         </td>
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
         <td><p><span id="CHK051S"></span>051</p>         </td>
         <td><p><span style="font-weight: bold;">CHK S RCVBCKOK Recovered backup successfully</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Success</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The recovery of mirror Mailbox was successful.</p>         </td>
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
         <td><p><span id="CHK052W"></span>052</p>         </td>
         <td><p><span style="font-weight: bold;">CHK W E_RCVXF Mailbox recovery failed: %1</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The recovery of master Mailbox has failed.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>System error in string format</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check system error to correct it. Try manual recovery.</p>
<p>If recovery still fails, initialize Mailbox.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="CHK053W"></span>053</p>         </td>
         <td><p><span style="font-weight: bold;">CHK W E_RCVBCK Backup recovery failed: %1</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The recovery of mirror Mailbox has failed.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>System error in string format</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check system error to correct it. Try manual recovery.</p>
<p>If recovery still fails, initialize Mailbox or disable the <span style="font-weight: bold;"><a href="../../configuration_start_here/config_gateway_paras#Mirror_option">Mirror option</a></span>.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="CHK100E"></span>100</p>         </td>
         <td><p><span style="font-weight: bold;">CHK E XFERINIT Opening mailbox failed: %1</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Checking procedure cannot open Mailbox file.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>System error in string format</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check system error to correct it.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="CHK101E"></span>101</p>         </td>
         <td><p><span style="font-weight: bold;">CHK E XFERCREAT Creating mailbox failed: %1</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Monitor was unable to create Mailbox file.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>System error is in string format</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check system error to correct it.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="CHK102E"></span>102</p>         </td>
         <td><p><span style="font-weight: bold;">CHK E XFERSCAN Reading mailbox failed: %1</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An error occurred when checking Mailbox file structure.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>System error is in string format or monitor error</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check system error to correct it. Try manual recovery.</p>
<p>If recovery still fails, initialize Mailbox or disable the <span style="font-weight: bold;"><a href="../../configuration_start_here/config_gateway_paras#Mirror_option">Mirror option</a></span>.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="CHK103E"></span>103</p>         </td>
         <td><p><span style="font-weight: bold;">CHK E XFEREND Closing mailbox failed: %1</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An error occurred while closing Mailbox file.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>System error is in string format</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check system error to correct it. Try recovery.</p>
<p>If recovery still fails, initialize Mailbox or disable the <span style="font-weight: bold;"><a href="../../configuration_start_here/config_gateway_paras#Mirror_option">Mirror option</a></span>.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="K104E"></span>104</p>         </td>
         <td><p><span style="font-weight: bold;">CHK E SUPCTXR Error while loading context (%1): %2</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Checking procedure could not load context file.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>System error is in string format</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Normally, context file is recreated with a dirty status if loading it failed. So a call to database checking should correct the problem. If you still cannot load context file, check system error to correct it.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="CHK105E"></span>105</p>         </td>
         <td><p><span style="font-weight: bold;">CHK E SUPCTXW Error while saving context (%1): %2</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Checking procedure could not save context file.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>System error is in string format</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check system error. Try manual recovery.</p>
<p>If recovery still fails, initialize Mailbox or disable the <span style="font-weight: bold;"><a href="../../configuration_start_here/config_gateway_paras#Mirror_option">Mirror option</a></span>.</p>         </td>
      </tr>
   </tbody>
</table>

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
