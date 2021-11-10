{
    "title": "Trading Partner Management (TPM)",
    "linkTitle": "Trading Partner Management (TPM)",
    "weight": "530"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Messages and codes

This topic lists PassPort (Trading Partner) log messages.

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TPM101E"></span>101</p>         </td>
         <td><p>TPM E INITERR Connector initialisation error %1</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error on PassPort connector initialization.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Externally generated error message</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Correct configuration according to displayed message.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TPM102W"></span>102</p>         </td>
         <td><p>TPM W IRESERR Initiator resolution error - dea_id=%2 protocol=%3 msg="%1"</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error resolving DEA ID (Gateway in Initiator mode).</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Externally generated error message</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>PassPort DEA ID</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Protocol</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Correct configuration according to displayed message.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TPM103W"></span>103</p>         </td>
         <td><p>TPM W RRESERR Responder resolution error - user_name=%2 protocol=%3 msg="%1"</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error resolving DEA ID (Gateway in Responder mode).</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Externally generated error message</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Remote partner user name</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Protocol</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Correct configuration according to displayed message.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TPM104W"></span>104</p>         </td>
         <td><p>TPM W PMISMAT Protocol mismatch - dea_id=%1 expecting protocol %2 got %3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Protocol mismatch prevents connection.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>PassPort DEA ID</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Protocol expected</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Protocol received</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Correct the remote Site protocol ID.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TPM105W"></span>105</p>         </td>
         <td><p>TPM W DMISMAT Direction mismatch - dea_id=%1 expecting direction %2 got %3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Transfer direction mismatch prevents connection.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>PassPort DEA ID</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Direction expected</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Direction received</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Correct Transfer Request direction attribute and resubmit Transfer Request, or use an alternate DEA ID via the <span class="code" style="font-weight: bold;">peltrans tpm_dea_id</span> command.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TPM106E"></span>106</p>         </td>
         <td><p>TPM E APIERR %1 error - retcod=%2 errcode=%4 errmsg="%3"</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>PassPort related API error.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>One of the following API actions:</p>
<ul>
<li>TpmConnect</li>
<li>TPMGetDeaById</li>
<li>TpmGetDeaByAttr</li>
<li>TpmDisconnect</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>TPM Error code - generated externally to Gateway</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>TPM Return code - generated externally Gateway</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>TPM Message string - generated externally to Gateway</p>         </td>
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
         <td><p><span id="TPM107E"></span>107</p>         </td>
         <td><p>TPM E NOPARAMF No parameters file configured</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The PassPort parameter file name is not indicated in the Gateway configuration file.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Use the configuration menu to set the correct PassPort configuration parameters.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TPM108I"></span>108</p>         </td>
         <td><p>TPM I INITDONE Initialisations done - paramfile="%1"</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Initialization is completed. Parameters are loaded to memory.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>PassPort parameter file name</p>         </td>
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
         <td><p><span id="TPM300E"></span>300</p>         </td>
         <td><p>TPM E TPM entry not found</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The requested PassPort entry cannot be found.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Verify PassPort database definition.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TPM301E"></span>301</p>         </td>
         <td><p>TPM E TPM initialization error</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Gateway cannot initialize the PassPort connector, because it has encountered an initialization error.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Verify that PassPort is installed on the platform and all prerequisites are met.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TPM302E"></span>302</p>         </td>
         <td><p>TPM E TPM access error</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>[message currently not used]</p>         </td>
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
         <td><p><span id="TPM303E"></span>303</p>         </td>
         <td><p>TPM E Invalid request to TPM</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A mandatory parameter is missing, for example DEA_ID.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Correct the Transfer Request and re-submit.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TPM304E"></span>304</p>         </td>
         <td><p>TPM E TPM data mismatches request</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The data retrieved from PassPort has an unexpected value.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the data definition for the relevant PassPort entry.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TPM305E"></span>305</p>         </td>
         <td><p>TPM E TPM API error</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>PassPort API returns an error.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Refer to the Gateway log file for more detailed information.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TPM306E"></span>306</p>         </td>
         <td><p>TPM E Invalid response from TPM</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The data retrieved from PassPort has an invalid or missing value, for example no DEA_ID, MODE or DIRECTION.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the data definition for the relevant PassPort entry.</p>         </td>
      </tr>
   </tbody>
</table>

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
