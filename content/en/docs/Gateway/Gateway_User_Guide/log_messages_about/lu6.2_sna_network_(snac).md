{
    "title": "LU 6.2 SNA network (SNAC)",
    "linkTitle": "LU 6.2 SNA network (SNAC)",
    "weight": "280"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Messages and codes

This topic lists LU 6.2 SNA network log messages.

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNAC003I"></span>003</p>         </td>
         <td><p><span style="font-weight: bold;">SNAC I CONN_RP- allocation request refused: conversation in progress</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>CPI-C is a single conversation process. Another conversation cannot begin until the current one is ended.</p>         </td>
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
         <td><p><span id="SNAC004I"></span>004</p>         </td>
         <td><p><span style="font-weight: bold;">SNAC I ALLOC_RQ allocation request: dest=%1 %2 %3 %4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Beginning of an LU 6.2 conversation. The "dest" parameter indicates the CPI-C symbolic destination.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Conversation ID assigned</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Remote LU name</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Transaction program name</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Name of the conversation mode</p>         </td>
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
         <td><p><span id="SNAC005I"></span>005</p>         </td>
         <td><p><span style="font-weight: bold;">SNAC I ALLOC_AK allocation accepted: RLU=%1 MODE=%2 CID=%3</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The requested conversation is accepted.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote LU name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Name of the conversation mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Conversation ID assigned</p>         </td>
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
         <td><p><span id="SNAC006I"></span>006</p>         </td>
         <td><p><span style="font-weight: bold;">SNAC I ALLOC_NK allocation refused: RLU=%1 FONC=%2, ORIGINE=%3, RCODE=%4, ERRNO=%5</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An unexpected error occurred during conversation allocation. The name of the CPI-C function concerned and its return code are displayed. ORIGINE indicates whether the refusal is from the Local or Remote Site.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote LU name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>CPI-C function concerned</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Origin of the error</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>CPI-C function return code</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>System-specific return code</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>If the function is <span style="font-weight: bold;">cminit</span>, check that the symbolic destination is defined in the SNA setup. If not, check the appropriate CPI-C manual delivered with the product to determine why the function failed.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SNAC007I"></span>007</p>         </td>
         <td><p><span style="font-weight: bold;">SNAC I ALLOC_ID allocation requested: RLU=%1 MODE=%2 CID=%3</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The remote system has requested a conversation allocation.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote LU name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Name of the conversation mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Conversation ID assigned</p>         </td>
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
         <td><p><span id="SNAC008I"></span>008</p>         </td>
         <td><p><span style="font-weight: bold;">SNAC I DEALL_RQ deallocation request: RLU=%1 OPTION=%2</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The local system has requested termination of the conversation.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote LU name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>De-allocation option</p>         </td>
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
         <td><p><span id="SNAC009I"></span>009</p>         </td>
         <td><p><span style="font-weight: bold;">SNAC I DEALL_ID deallocation request: RLU=%1 OPTION=%2</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The local system has requested termination of the conversation.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote LU name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>De-allocation option</p>         </td>
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
         <td><p><span id="SNAC010I"></span>010</p>         </td>
         <td><p><span style="font-weight: bold;">SNAC I CONV_END end of conversation: RLU=%1 RCODE=%2, ERRNO=%3</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Reason for the termination of the conversation (normal or abnormal). If an error has occurred, refer to <a href="#SNAC020E">SNA message number 20</a> for details.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote LU name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>CPI-C error</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>System specific error</p>         </td>
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
         <td><p><span id="SNAC020E"></span>020</p>         </td>
         <td><p><span style="font-weight: bold;">SNAC E ERROR RLU=%1 FONC=%2 ORIGINE=%3, RCODE=%4, ERRNO=%5</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An unexpected error occurred during conversation.</p>
<p>The name of the CPI-C function concerned and its return code are displayed.</p>
<p>ORIGINE indicates whether the refusal is from the Local or Remote Site.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote LU name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>CPI-C function concerned</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Origin of the error</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>CPI-C function return code</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>System-specific return code</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>If the function is <span style="font-weight: bold;">cminit</span>, check that the symbolic destination is defined in the SNA setup. If not, check the CPI-C manual delivered with the product to determine why the function failed.</p>         </td>
      </tr>
   </tbody>
</table>

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
