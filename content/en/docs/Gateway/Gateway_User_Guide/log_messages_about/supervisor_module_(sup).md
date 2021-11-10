{
    "title": "Supervisor module (SUP)",
    "linkTitle": "Supervisor Module (SUP)",
    "weight": "480"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Messages and codes

This topic lists Supervisor module log messages.

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP001I"></span>001</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I INIT_RQ %1(%2) connection request, requester mode</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The Local Site is requesting a connection to a Remote Site (Initiator mode connection for the Local Site).</p>         </td>
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
         <td><p><span id="SUP002I"></span>002</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I INIT_ID %1(%2) connection indication, server mode</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The Local Site is requesting a connection to a Remote Site (requester mode connection for the Local Site).</p>         </td>
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
         <td><p><span id="SUP003I"></span>003</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I INIT_RP+ %1(%2) connection in server mode accepted</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The Local Site has accepted the incoming connection request (Responder mode connection for the Local Site).</p>         </td>
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
         <td><p><span id="SUP004I"></span>004</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I INIT_RP- %1(%2) connection in server mode refused: reason=%3</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The Local Site has rejected the incoming connection request (Responder mode connection for the Local Site).</p>         </td>
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
         <td><p>Rejection reason (monitor diagnostic)</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the settings of the Remote Site. If necessary, also verify the correct initialization and startup of the underlying communication interface to reach the Remote Site.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP005I"></span>005</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I INIT_CF+ %1(%2) connection in requester mode accepted</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The Remote Site has accepted the incoming connection request (Initiator mode connection for the Local Site).</p>         </td>
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
         <td><p><span id="SUP006W"></span>006</p>         </td>
         <td><p>SUP W INIT_CF- %1(%2) connection in requester mode refused: reason=%3 / prot.diag=%4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The Remote Site or the file transfer module has rejected the incoming connection request (Initiator mode connection for the Local Site).</p>         </td>
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
         <td><p>Rejection reason (monitor diagnostic)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Protocol diagnostic code (if any)</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the settings of the Remote Site. If necessary, also verify the correct initialization and start of the underlying communication interface to reach the Remote Site.</p>
<p>Check the settings of the Transfer Request for a refusal by the transfer module.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP007I"></span>007</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I TERM_RQ %1(%2) end connection request: reason=%3</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The Local Site has requested the release of the connection with the Remote Site.</p>         </td>
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
         <td><p>Release reason (monitor diagnostic)</p>         </td>
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
         <td><p><span id="SUP008I"></span>008</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I TERM_ID %1(%2) end of connection indication: reason=%3 / prot.diag=%4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The Local Site has received a connection release indication from the Remote Site. The connection is considered ended when this indication is received. The monitor does not reply to this indication.</p>         </td>
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
         <td><p>Release reason (monitor diagnostic)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Release reason (protocol diagnostic)</p>         </td>
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
         <td><p><span id="SUP009I"></span>009</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I TERM_CF %1(%2) end of connection confirmation</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The end of connection requested by the monitor has been confirmed.</p>         </td>
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
         <td><p><span id="SUP010W"></span>010</p>         </td>
         <td><p><span style="font-weight: bold;">SUP W ABORT_RQ %1(%2) connection abort request: reason=%3</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The Local Site has requested the abort of the connection with the Remote Site.</p>         </td>
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
         <td><p>Abort reason (monitor diagnostic)</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Analyze the diagnostic for the monitor to determine the reason for the unexpected end of connection.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP011W"></span>011</p>         </td>
         <td><p><span style="font-weight: bold;">SUP W ABORT_ID %1(%2) connection abort indication: reason=%3 /prot.diag=%4 / error=%5</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The Local Site has received a connection abort indication from the Remote Site or from the file transfer module.</p>         </td>
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
         <td><p>Abort reason (monitor diagnostic)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Abort reason (protocol diagnostic)</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Abort reason (other diagnostics: system error, transfer process error, ...)</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Analyze the diagnostics supplied to understand the reason for the unexpected end of connection.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP012I"></span>012</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I XSND_RQ %1(%2) [%3] transfer request, transmit file %4/%5, srce %6, dest %7</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The Local Site has requested the start of the file emission procedure.</p>         </td>
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
         <td><p>Local transfer identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Access path to the file</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>File name</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Origin Site</p>         </td>
      </tr>
      <tr>
         <td><p>7</p>         </td>
         <td><p>Destination Site</p>         </td>
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
         <td><p><span id="SUP013I"></span>013</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I XRCV_RQ %1(%2) [%3] transfer request, receive file %4/%5, srce %6 dest %7</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The Local Site has requested the start of the file reception procedure.</p>         </td>
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
         <td><p>Local transfer identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Access path to the file</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>File name</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Origin Site</p>         </td>
      </tr>
      <tr>
         <td><p>7</p>         </td>
         <td><p>Destination Site</p>         </td>
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
         <td><p><span id="SUP014I"></span>014</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I XSND_ID %1(%2) transfer indication, transmit file, srce %3 dest %4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The Remote Site has requested the start of the file emission procedure (file transmission to the Local Site).</p>         </td>
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
         <td><p>Origin Site</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Destination Site</p>         </td>
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
         <td><p><span id="SUP015I"></span>015</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I XRCV_ID %1(%2) transfer indication, receive file, srce %3 dest %</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The Remote Site has requested the start of the file reception procedure (file transmission from the Local Site).</p>         </td>
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
         <td><p>Origin Site</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Destination Site</p>         </td>
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
         <td><p><span id="SUP016I"></span>016</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I XBEG_CF+ %1(%2) [%3] transfer in requester mode accepted</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The Remote Site has accepted the file transfer.</p>         </td>
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
         <td><p>Local transfer identifier (number)</p>         </td>
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
         <td><p><span id="SUP017E"></span>017</p>         </td>
         <td><p><span style="font-weight: bold;">SUP E XBEG_CF- %1(%2) [%3] transfer in requester mode refused: reason=%4 / prot.diag=%5 / error=%6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The Remote Site or the file transfer module has refused the file transfer.</p>         </td>
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
         <td><p>Local transfer identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Abort reason (monitor diagnostic)</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Abort reason (protocol diagnostic)</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Abort reason (other diagnostics: system error, transfer process error, ...)</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Analyze the diagnostics supplied to understand the refusal reason.</p>
<p>Check the settings of the Remote Site. If necessary, verify the correct initialization and startup of the underlying communication interface to reach the Remote Site.</p>
<p>Check the settings of the Transfer Request for a refusal by the transfer module.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP018I"></span>018</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I XBEG_RP+ %1(%2) [%3] transfer in server mode accepted</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The Local Site has accepted the incoming Transfer Request.</p>         </td>
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
         <td><p>Local transfer identifier (number)</p>         </td>
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
         <td><p><span id="SUP019I"></span>019</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I XBEG_RP- %1(%2) [%3] transfer in server mode refused: reason=%4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The Local Site has rejected the incoming Transfer Request.</p>         </td>
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
         <td><p>Local transfer identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Rejection reason (monitor diagnostic)</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Analyze the diagnostic supplied to understand the rejection reason.</p>
<p>Check the settings of the Remote Site. If necessary, also verify the correct initialization and start of the underlying communication interface to reach the Remote Site.</p>
<p>Check the settings of the Transfer Request for a refusal by the transfer module.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP020I"></span>020</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I XEND_RQ %1(%2) end transfer request %3: reason=%4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The Local Site has requested a premature end of transfer (transfer abort or suspension).</p>         </td>
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
         <td><p>Ending reason (monitor diagnostic)</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>A suspended transfer will be automatically restarted later.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP021I"></span>021</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I XEND_ID %1(%2) [%3] end of transfer indication: reason=%4 / prot.diag=%5 / errror=%6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The Local Site has received from the Remote Site an indication for the end of transfer</p>         </td>
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
         <td><p>Local transfer identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Abort reason (monitor diagnostic)</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Abort reason (protocol diagnostic)</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Abort reason (other diagnostics: system error, transfer process error, ...)</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>In case one of the diagnostics indicates an error, do the following:</p>
<ul>
<li>Check the settings of the Remote Site. If necessary, also verify the correct initialization and startup of the underlying communication interface to reach the Remote Site.</li>
<li>Check the settings of the Transfer Request for a refusal by the transfer module.</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP022I"></span>022</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I XEND_RP %1(%2) [%3] effective end of transfer</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The response to an end of transfer indication has been made</p>         </td>
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
         <td><p>Local transfer identifier (number)</p>         </td>
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
         <td><p><span id="SUP023I"></span>023</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I XEND_CF %1(%2) [%3] end of transfer confirmation</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The response to an end-of-transfer indication has been made.</p>         </td>
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
         <td><p>Local transfer identifier (number)</p>         </td>
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
         <td><p><span id="SUP024E"></span>024</p>         </td>
         <td><p><span style="font-weight: bold;">SUP E XEND_CF %1(%2) [%3] routing failure: %4 , ErrCod=%5</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The monitor has failed to create a Transfer Request to forward the received file.</p>
<p>The reason for the failure indicated by %4 and % 5 gives the corresponding system error if any.</p>         </td>
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
         <td><p>Local transfer identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Failure reason (monitor diagnostic)</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Corresponding local error (if any)</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Analyze the diagnostics supplied to correct the problem.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP025I"></span>025</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I SITE warning! local site does not correspond to the configuration</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The existing Local Site does not correspond to the default Local Site identifier defined during the monitor installation procedure.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Verify that you have created the default Local Site for the monitor (with the name defined by the <span class="code">local_proto_ident</span> parameter in the monitor installation file).</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP026I"></span>026</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I SITE warning! no local site defined</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The default Local Site identifier for the monitor is not created. It corresponds to the Local Site identifier, defined during the monitor installation procedure.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Create the monitor default Local Site.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP027E"></span>027</p>         </td>
         <td><p><span style="font-weight: bold;">SUP E XEND_CF %1(%2) [%3] routing failure towards %4: %5 %6, ErrCod=%7</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The monitor was not able to route the Transfer Request.</p>         </td>
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
         <td><p>Local transfer identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Routing Site name</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Failure reason (monitor diagnostic)</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Object name link to the failure reason</p>         </td>
      </tr>
      <tr>
         <td><p>7</p>         </td>
         <td><p>Corresponding local error (if any)</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Analyze the diagnostics supplied to correct the problem.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP028I"></span>028</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I XEND_CF %1(%2) [%3] routing towards %4 ident:%5 model:%6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The monitor routes the transfer to the Site %4.</p>         </td>
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
         <td><p>Local transfer identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Routing Site name</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Transfer ident</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Model name</p>         </td>
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
         <td><p><span style="font-weight: bold;"><span id="SUP030E"></span>030</span></p>         </td>
         <td><p><span style="font-weight: bold;">SUP E BADAPPLI %1: Receive application "%2" doesn't exist</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The monitor was not able to find the Application (FTP protocol).</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Application name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Create a Gateway Application with this name.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP031E"></span>031</p>         </td>
         <td><p><span style="font-weight: bold;">SUP E BADACK no transfer record found for ACK msg (%1)</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The monitor was not able to find the Transfer Request associated with the acknowledgement request</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the acknowledgement request parameters</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP032E"></span>032</p>         </td>
         <td><p><span style="font-weight: bold;">SUP E ACKFAIL transfer (%1) acknowledgment update fails</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The monitor was not able to update the Transfer Request associated with the acknowledgement request</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the acknowledgement request parameters.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP033W"></span>033</p>         </td>
         <td><p>SUP W ACKIGN  transfer (%1) acknowledgment ignored</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The Site acknowledgement option was set to "NOT_TO_ACK". The transfer associated with the acknowledgement request is not modified.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer identifier</p>         </td>
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
         <td><p><span id="SUP034E"></span>034</p>         </td>
         <td><p><span style="font-weight: bold;">SUP E ACKFAIL transfer (%1) couldn't send acknowledgment ('%2')</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Gateway was unable to send acknowledgement</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Context specific message</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Action depends on parameter 2 message content. Check partner configuration.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP036I"></span>036</p>         </td>
         <td><p>SUP I CONNHOLD connection held for upcoming transfers. wait interval: %1</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The Site acknowledgement option was set to "NOT_TO_ACK". The transfer associated with the acknowledgement request is not modified.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Wait interval in seconds</p>         </td>
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
         <td><p><span id="SUP040E"></span>040</p>         </td>
         <td><p><span style="font-weight: bold;">SUP E KEY Invalid product key: %1</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The software protection key defined during the monitor installation procedure is not valid</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Key value used</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the software protection key supplied by the software delivery team. If it is the same as the one contained in the message, contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP041E"></span>041</p>         </td>
         <td><p><span style="font-weight: bold;">SUP E KEY Product code or site name invalid. rc=%1</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The software protection key is not valid.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Error code returned by the key checking routine</p>         </td>
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
         <td><p><span id="SUP042E"></span>042</p>         </td>
         <td><p><span style="font-weight: bold;">SUP E KEY Product code or site name invalid. rc=%1</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The software protection key is not valid</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Error code returned by the key checking routine</p>         </td>
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
         <td><p><span id="SUP043E"></span>043</p>         </td>
         <td><p>SUP E KEY Retention date expired</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The software protection key is not valid, because the retention date has expired</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
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
         <td><p><span id="SUP044W"></span>044</p>         </td>
         <td><p><span style="font-weight: bold;">SUP W KEY Retention date about to expire. credit=%1 days</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Warning message indicating that the retention date expires in %1 days. After this delay, the software protection key becomes invalid.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Number of days remaining for the validity of the protection key</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Contact Axway Support</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP045E"></span>045</p>         </td>
         <td><p><span style="font-weight: bold;">SUP E KEY Number of authorized connections exceeded. max=%1</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The number of simultaneous connections has exceeded the maximum value defined in the software protection key. Above the maximum, further connection requests are rejected.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Maximum number of simultaneous connections authorized</p>         </td>
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
         <td><p><span id="SUP046E"></span>046</p>         </td>
         <td><p><span style="font-weight: bold;">SUP E KEY Number of authorized sites exceeded. max=%1</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The number of simultaneous connections has exceeded the maximum value defined in the software protection key. Above the maximum, further connection requests are rejected.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Maximum number of simultaneous connections authorized</p>         </td>
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
         <td><p><span id="SUP047E"></span>047</p>         </td>
         <td><p><span style="font-weight: bold;">SUP E KEY Protocol not allowed or invalid</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The requested protocol is not allowed in the software protection key</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
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
         <td><p><span id="SUP048I"></span>048</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I KEY key=%1, site=%2</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message printed after a successful verification of the software protection key</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Protection key</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Default Local Site defined during the installation</p>         </td>
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
         <td><p><span id="SUP049I"></span>049</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I KEY protocol option: %1</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>List of the file transfer protocols authorized by the software protection key</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>List of file transfer protocols</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Default Local Site defined during the installation</p>         </td>
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
         <td><p><span id="SUP050I"></span>050</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I KEY retention date=%1 %2</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Retention date defined in the software protection key</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Two digits specifying the year (ex. <span style="font-weight: bold;">97</span> for <span style="font-style: italic;">1997</span>)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Three digits specifying the Julian day of the year (<span style="font-weight: bold;">001</span> to <span style="font-weight: bold;">365</span>)</p>         </td>
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
         <td><p><span id="SUP051I"></span>051</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I KEY connection limits: connection=%1, site=%2</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Maximum number of active connections and Sites allowed. They are defined in the software protection key.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Maximum number of simultaneous connections</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Maximum number of Sites</p>         </td>
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
         <td><p><span id="SUP054I"></span>054</p>         </td>
         <td><p><span style="font-weight: bold;">SUP E KEY Protocol %1 not allowed, canceling transfer %2</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The requested protocol is not allowed in the software protection key, therefore the transfer was canceled.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Which protocol is not allowed</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Number of transfer that was canceled</p>         </td>
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
         <td><p><span id="SUP060I"></span>060</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I INI-CTOR Initializing connector '%1'</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Initializing specified connector. A connector manages a queue associated with a file.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>One of the following:</p>
<ul>
<li>Sentinel</li>
<li>Router (connector responsible for routing)</li>
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
         <td><p><span id="SUP061I"></span>061</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I ST-CPROC Starting '%1' connector process number %2</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Starting connector associated with specified process</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Name of connector: either Sentinel or Router</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Process number (a single process is allowed per queue)</p>         </td>
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
         <td><p><span id="SUP062I"></span>062</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I CPROCUP '%1' connector process number %2 now UP (pid=%3)</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Specified connector is ready</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Name of connector: either Sentinel or Router</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Process number (a single process is allowed per queue)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Process system identifier</p>         </td>
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
         <td><p><span id="SUP063I"></span>063</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I CPROCDOWN '%1' connector process number %2 now DOWN</span> <span style="font-weight: bold;">(pid=%3)</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Specified connector is stopped</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Name of connector: either Sentinel or Router</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Process number (a single process is allowed per queue)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Process system identifier</p>         </td>
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
         <td><p><span id="SUP064W"></span>064</p>         </td>
         <td><p><span style="font-weight: bold;">SUP W SUSSCHED '%1' %2 %% full, transfer scheduling suspended</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The specified queue has reached a critical threshold. To avoid congestion, transfer scheduling is suspended.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Path to the queue</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Percentage of queue filled</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>If queue congestion is temporary, transfer scheduling will restart when the queue is no longer full.</p>
<p>If the queue corresponds to a Sentinel connector, check that Sentinel is active.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP065I"></span>065</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I SUSSCHED Transfer scheduling resumed</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Queue level below critical threshold: transfer scheduling resumed.</p>         </td>
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
         <td><p><span id="SUP066W"></span>066</p>         </td>
         <td><p><span style="font-weight: bold;">SUP W REFUCONN '%1' %2 %% full, new connections will be refused</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The specified queue has reached a critical threshold. All new connections are refused.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Path to the queue</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Percentage of queue filled</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>If queue congestion is temporary, connections will be accepted when the queue is no longer full.</p>
<p>If the queue corresponds to a Sentinel connector, check that Sentinel is active.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP067I"></span>067</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I ACCPCONN New connections will be accepted again</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Queue level below critical threshold: new connections accepted again.</p>         </td>
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
         <td><p><span id="SUP068W"></span>068</p>         </td>
         <td><p><span style="font-weight: bold;">SUP W REFUXFER '%1' %2 %% full, new transfers will be refused</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The specified queue has reached a critical threshold. All new transfers are refused.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Path to the queue</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Percentage of queue filled</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>If queue congestion is temporary, transfers will be accepted when the queue is no longer full.</p>
<p>If the queue corresponds to a Sentinel connector, check that Sentinel is active.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP069I"></span>069</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I ACCPXFER New transfers will be accepted again</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Queue level below critical threshold: new transfers accepted again.</p>         </td>
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
         <td><p><span id="SUP070W"></span>070</p>         </td>
         <td><p><span style="font-weight: bold;">SUP W REFUUSER '%1' %2 %% full, new users will be refused</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The specified queue has reached a critical threshold. All new user logins are refused.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Path to the queue</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Percentage of queue filled</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>If queue congestion is temporary, user logins will be accepted when the queue is no longer full.</p>
<p>If the queue corresponds to a Sentinel connector, check that Sentinel is active.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP071I"></span>071</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I ACCPUSER New users will be accepted again</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Queue level below critical threshold: new users accepted again</p>         </td>
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
         <td><p><span id="SUP072E"></span>072</p>         </td>
         <td><p>SUP E PMQWRERR Write to file '%1' failed (ErrCod=%2)</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>File write error</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>File name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Error code number &amp; message</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check that the file is not full</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP073I"></span>073</p>         </td>
         <td><p>SUP I RE-CPROC Restarting '%1' connector process number %2</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Restarting a process</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connector name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Process number</p>         </td>
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
         <td><p><span id="SUP080I"></span>080</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I INI-HP Initializing helper pool '%1'</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The SUP process is initializing the helper pool</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Name of process</p>         </td>
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
         <td><p><span id="SUP081I"></span>081</p>         </td>
         <td><p>SUP I ST-HPROC Starting '%1' helper process number %2</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Helper process is starting up</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Helper process name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Helper process number</p>         </td>
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
         <td><p><span id="SUP082I"></span>082</p>         </td>
         <td><p>SUP I HPROCUP '%1' helper process number %2 now UP (pid=%3)</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Helper process is starting operating</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Helper process name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Helper process number</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Helper process identification</p>         </td>
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
         <td><p><span id="SUP083I"></span>083</p>         </td>
         <td><p>SUP I HPROCDOWN '%1' helper process number %2 now DOWN (pid=%3)</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Helper process is not operating</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Helper process name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Helper process number</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Helper process identification</p>         </td>
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
         <td><p><span id="SUP084E"></span>084</p>         </td>
         <td><p>SUP E EDIPRERR [%1] EDI processing error: reason=%2 ErrCod=%3 errno=%4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error on processing EDI protocol</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer Id</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Reason for error (string)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Error code</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Error number</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>The solution for the error depends on the returned message. In most cases this error indicates a problem in the Transfer partner security configuration.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP085I"></span>085</p>         </td>
         <td><p>SUP I RE-HPROC Recycling '%1' helper process number %2</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A process is stopped and then restarted after a certain number of operations to free up memory.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connector name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Process number</p>         </td>
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
         <td><p><span id="SUP101W"></span>101</p>         </td>
         <td><p><span style="font-weight: bold;">SUP W SITE-DOWN Site %1 disabled due to maximum retry count (%2) reached</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The monitor has disabled the Remote Site because the maximum number of consecutive connection attempts to that site has been reached. The monitor does not attempt further connection to that Site.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Maximum number of connection retries</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>The user must enable that Site using online commands or a graphical user interface, so the monitor can again schedule file transfer on the Site.</p>
<p>Enabling a Site resets its connection counters (retry count and retry delays).</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP102I"></span>102</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I U-LOGIN User %1 (%2) pid %3 has logged in</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td>A remote user has logged in.         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td>User         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td>IP of the user         </td>
      </tr>
      <tr>
         <td><strong>3</strong>         </td>
         <td>Process id         </td>
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
         <td><p><span id="SUP103I"></span>103</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I U-LOGOUT User %1 (%2) pid %3 logged out</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td>A remote user has logged out         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td>User         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td>IP of the user         </td>
      </tr>
      <tr>
         <td><strong>3</strong>         </td>
         <td>Process id         </td>
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
         <td><p><span id="SUP104W"></span>104</p>         </td>
         <td><p><span style="font-weight: bold;">SUP W U-EXITED User %1 pid %2 abnormally exited</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A user process exited without properly closing its resources. This message typically appears when a user Application program does not call ItpCloseSession() before exiting, or when such a program or a Gateway tool is killed.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>No meaning (typically "unknown")</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Process id</p>         </td>
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
         <td><p><span id="SUP105W"></span>105</p>         </td>
         <td><p><span style="font-weight: bold;">SUP W U-FAIL login refused to %1: unauthorized access</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The user name and/or password is invalid</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>User name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Use a correct user name and a correct password.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP106I"></span>106</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I ALT_COMM Using alternate communication path Nb: %1 to site %2</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>All the connection attempts to the Site have failed with the last communication path. So the monitor tries to reach the Site by using the next communication path numbered %1 available.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Path number (<span style="font-weight: bold;">1</span>, <span style="font-weight: bold;">2</span>, or <span style="font-weight: bold;">3</span>)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Alias Site identifier</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Solve the communication error on the other communication paths</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP107I"></span>107</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I MAIN_COMM Using main communication path to site %2</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The communication path has been changed by a user action. It is the main one that is used to reach the Remote Site.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Alias Site identifier</p>         </td>
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
         <td><p><span id="SUP108I"></span>108</p>         </td>
         <td><p>SUP I SITE-RTRY Site %1 [%2] retry connection (%3/%4) in %5 seconds</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Indicates a connection retry event in <span style="font-style: italic;">n</span> seconds</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Site alias</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Transfer ID</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Retry count</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Maximum allowable retry attempts</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Seconds before next retry</p>         </td>
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
         <td><p><span id="SUP109I"></span>109</p>         </td>
         <td><p>SUP I TO_ALTER Site %1 [%2] maximum retry(%3) reached. Switch to alternate communication path Nb: %4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Indicates a switch to connection attempts on a new communication path</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Site alias</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Transfer ID</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Maximum allowable retry attempts</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>New communication path number</p>         </td>
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
         <td><p><span id="SUP110I"></span>110</p>         </td>
         <td><p>SUP I TP_MAIN Site %1 [%2] maximum retry(%3) reached. Switch to main communication path</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Indicates a switch to connection attempts on the main communication path</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Site alias</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Transfer ID</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Maximum allowable retry attempts</p>         </td>
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
         <td><p><span id="SUP111I"></span>111</p>         </td>
         <td><p>SUP I N-ATTACH Notification script attached to user %1 pid %2</p>         </td>
      </tr>
      <tr>
         <td><p><span id="SUP112I"></span>112</p>         </td>
         <td><p>SUP I N-DETACH Notification script detached from user %1 pid %2</p>         </td>
      </tr>
      <tr>
         <td><p><span id="SUP113I"></span>113</p>         </td>
         <td><p>SUP I N-STARTED User notification process %1 started</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A user process dedicated to an external user exit routine has been started.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Path name of the program to execute</p>         </td>
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
         <td><p><span id="SUP114W"></span>114</p>         </td>
         <td><p><span style="font-weight: bold;">SUP W N-HIGH-WM Notif high water mark reached(%1)</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>This message indicates that user processes executing external exits are not able to dispatch execution of exit frames at the speed of incoming events. It means that the number of awaiting exit frames queued by Gateway has reached a maximum value defined in the configuration file ("high water mark").</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Actual number of awaiting exit frames queued by Gateway</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Gateway normally recovers from this warning automatically. It may have to reject incoming connections in order to decrease the amount of its resources actually used. You can try to decrease the average response time of the user exit routines.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP115I"></span>115</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I N-LOW-WM Notif low water mark reached(%1</span>)</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>This message indicates that user processes executing external exits have dispatched enough awaiting exit frames queued by Gateway to decrease their number under a minimal value defined in the configuration file ("low water mark").</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Actual number of awaiting exit frames queued by Gateway</p>         </td>
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
         <td><p><span id="SUP116I"></span>116</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I N-NO-PROC No user process available for notifications</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>This message indicates that all process context resources are used, and that Gateway is not allowed to create additional user processes</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Gateway normally recovers from this warning automatically. It may have to reject incoming connections in order to decrease the amount of its resources actually used.</p>
<p>You can allow Gateway to start more user processes by increasing the configuration parameter <span class="code">notif_process_started_max</span>.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP117I"></span>117</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I N-CONFIG Origin set enabled=(%1), processes to start=%2, max processes=%3</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message written by the external user exit manager at Gateway startup</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Exit families allowed</p>
<p>Default families are (ft, xfer)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Number of user exit processes to create with Gateway startup</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Maximum number of user exit processes Gateway is allowed to manage simultaneously</p>         </td>
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
         <td><p><span id="SUP118I"></span>118</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I N-OPENSET NotifOpenSet, type set=(%1), script max=(%2</span>)</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message written once a user exit process has been restarted successfully</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Exit families allowed</p>
<p>Default families are (ft, xfer)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Maximum number of transfer contexts (active transfers) this process can manage simultaneously</p>         </td>
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
         <td><p><span id="SUP119I"></span>119</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I N-CLOSESET NotifCloseSet, type set=(%1), script max=(%2)</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information message written when a user exit process has freed its resources before exiting</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Exit families allowed</p>
<p>Default families are (ft, xfer)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Maximum number of transfer contexts (active transfers) this process can manage simultaneously</p>         </td>
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
         <td><p><span id="SUP120W"></span>120</p>         </td>
         <td><p><span style="font-weight: bold;">SUP W N-BUGGY User notification process problem, type set=(%1), required=(%3), script max=(%2)</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Gateway has detected abnormal user exit process</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Exit families allowed</p>
<p>Default families are (ft, xfer)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Exit families this process is able to handle</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Maximum number of transfer contexts (active transfers) the process can manage simultaneously</p>         </td>
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
         <td><p><span id="SUP121I"></span>121</p>         </td>
         <td><p>SUP I UN-INIT NotifInit by user %1 pid %2 max scripts %3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Message reserved for Gateway Support debug mode.</p>
<p>A user exit process has exited before performing its initialization.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Command line used to start the process</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the command line and the output of the corresponding process.</p>
<p>If you cannot correct the problem, contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP122I"></span>122</p>         </td>
         <td><p>SUP I UN-END NotifEnd by user %1 pid %2</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Message reserved for Gateway Support debug mode.</p>
<p>A user exit process has exited before performing its initialization.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Command line used to start the process</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the command line and the output of the corresponding process.</p>
<p>If you cannot correct the problem, contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP123I"></span>123</p>         </td>
         <td><p>SUP I UN-GETIND NotifGetInd ident=%3 context=%4 get by user %1 pid %2</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Message reserved for Gateway Support debug mode.</p>
<p>A user exit process has exited before performing its initialization.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Command line used to start the process</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the command line and the output of the corresponding process.</p>
<p>If you cannot correct the problem, contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP124I"></span>124</p>         </td>
         <td><p>SUP I UN-PUTREP NotifPutResp ident=%3 context=%4 put by user %1 pid %2</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Message reserved for Gateway Support debug mode.</p>
<p>A user exit process has exited before performing its initialization.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Command line used to start the process</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the command line and the output of the corresponding process.</p>
<p>If you cannot correct the problem, contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP125I"></span>125</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I UN-GETPEN NotifGet pending for user %1 pid %2</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Message reserved for Gateway Support debug mode.</p>
<p>A user exit process has exited before performing its initialization.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Command line used to start the process</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the command line and the output of the corresponding process.</p>
<p>If you cannot correct the problem, contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP126I"></span>126</p>         </td>
         <td><p>SUP I N-FAILURE User notif process start failure %1</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A user exit process has exited before performing its initialization</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Command line used to start the process</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the command line and the output of the corresponding process.</p>
<p>If you cannot correct the problem, contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP127I"></span>127</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I N-EXITED Abnormal exiting of a user exit process %1 pid %2</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Gateway has detected an abnormal exiting of a user exit process</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Exit families allowed. Default families are (ft, xfer)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Exit process id</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the output of the corresponding process.</p>
<p>If you cannot correct the problem, contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP151E"></span>151</p>         </td>
         <td><p>SUP E FN-XFERER Notif=%1, Ident=%2, ERROR=%7, Site=%3, Appli=%4, Yday=%5,Nth=%6</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>This message is provided for user external exit debugging. This message is written when the configuration parameter <span class="code">notif_log_level</span> is set to a value of 3 or greater.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Name of the user exit notification frame.</p>
<p>Other parameters correspond to different fields of the parameter area passed to the exit routine.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>No special action</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP150I"></span>150</p>         </td>
         <td><p>SUP I FN-XFEROK Notif=%1, Ident=%2, Site=%3, Appli=%4, Yday=%5, Nth=%6</p>         </td>
      </tr>
      <tr>
         <td><p><span id="SUP152I"></span>152</p>         </td>
         <td><p>SUP I FN-XFERUN Notif=%1, Ident=%2, NO CHANGED Todo=%3, Reason=%4,Reason lib=%5</p>         </td>
      </tr>
      <tr>
         <td><p><span id="SUP154I"></span>154</p>         </td>
         <td><p>SUP I XN-XFEROK Notif=%1, Ident=%2, State=%7, Site=%3, Appli=%4, Yday=%5, Nth=%6</p>         </td>
      </tr>
      <tr>
         <td><p><span id="SUP157I"></span>157</p>         </td>
         <td><p>SUP I FN-INITUN Notif=%1, %2 &lt;-&gt; %3, Todo=%4, Reason=%5, Reason lib=%6</p>         </td>
      </tr>
      <tr>
         <td><p><span id="SUP160I"></span>160</p>         </td>
         <td><p>SUP I IN-INITOK Notif=%1, org=%3, dest=%4</p>         </td>
      </tr>
      <tr>
         <td><p><span id="SUP161I"></span>161</p>         </td>
         <td><p>SUP I IN-INITER Notif=%1, INIT FAILED org=%3, dest=%4</p>         </td>
      </tr>
      <tr>
         <td><p><span id="SUP162I"></span>162</p>         </td>
         <td><p>SUP I FN-TERABOK Notif=%1, site %2</p>         </td>
      </tr>
      <tr>
         <td><p><span id="SUP163I"></span>163</p>         </td>
         <td><p>SUP I FN-TERABER Notif=%1, FAILED site %2</p>         </td>
      </tr>
      <tr>
         <td><p><span id="SUP164I"></span>164</p>         </td>
         <td><p>SUP I FN-PCNXUN Type=%1, Protocol=%2, User=%3, NOT CHANGED</p>         </td>
      </tr>
      <tr>
         <td><p><span id="SUP165I"></span>165</p>         </td>
         <td><p>SUP I FN-PCNXCH Type=%1, Protocol=%2, User=%3, CHANGED Todo=%4, Reason=%5, Reason lib=%6</p>         </td>
      </tr>
      <tr>
         <td><p><span id="SUP167I"></span>167</p>         </td>
         <td><p>SUP I FN-PCNXOK Type=%1, Protocol=%2, User=%3, NO RESPONSE</p>         </td>
      </tr>
      <tr>
         <td><p><span id="SUP169I"></span>169</p>         </td>
         <td><p>SUP I N-RECYCL Recycling user notification process (ops_count=%1)</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>This message set is provided for user external exit debugging. These messages are written when the configuration parameter <span class="code">notif_log_level</span> is set to a value of 3 or greater.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Name of the user exit notification frame.</p>
<p>Other parameters correspond to different fields of the parameter area passed to the exit routine.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>No special action</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP153W"></span>153</p>         </td>
         <td><p>SUP W FN-XFERCH Notif=%1, Ident=%2, CHANGED Todo=%3, Reason=%4, Reason lib=%5</p>         </td>
      </tr>
      <tr>
         <td><p><span id="SUP155W"></span>155</p>         </td>
         <td><p>SUP W XN-XFERER Notif=%1, Ident=%2, State=%7, ERROR=%8, Site=%3, Yday=%5, Nth=%6</p>         </td>
      </tr>
      <tr>
         <td><p><span id="SUP156W"></span>156</p>         </td>
         <td><p>SUP W FN-XFERCN Notif=%1, Ident=%2, XFER CANCELED Todo=%3, Reason=%4, Reason lib=%5</p>         </td>
      </tr>
      <tr>
         <td><p><span id="SUP158W"></span>158</p>         </td>
         <td><p>SUP W FN-INITCH Notif=%1, %2, CHANGED Todo=%3, Reason=%4, Reason lib=%5</p>         </td>
      </tr>
      <tr>
         <td><p><span id="SUP159W"></span>159</p>         </td>
         <td><p>SUP W FN-INITCN Notif=%1, %2, INIT DELETED Todo=%3, Reason=%4, Reason lib=%5</p>         </td>
      </tr>
      <tr>
         <td><p><span id="SUP166W"></span>166</p>         </td>
         <td><p>SUP W FN-PCNXCN Type=%1, Protocol=%2, User=%3, REJECTED Todo=%4, Reason=%5, Reason lib=%6</p>         </td>
      </tr>
      <tr>
         <td><p><span id="SUP168W"></span>168</p>         </td>
         <td><p>SUP W FN-PCNXER Type=%1, Protocol=%2, User=%3, FAILURE</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>This message set is provided for user external exit debugging. These messages are written when the configuration parameter <span class="code">notif_log_level</span> is set to a value of 3 or greater.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Name of the user exit notification frame.</p>
<p>Other parameters correspond to different fields of the parameter area passed to the exit routine.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>No special action</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP218I"></span>218</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I USER-SECU User:%1 %2:%3 <span style="font-style: italic;">Action</span>:%4 Allowed</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A user action on Gateway objects has been allowed.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>User name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Object type</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Object name</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Action type</p>         </td>
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
         <td><p><span id="SUP219I"></span>219</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I USER-SECU User:%1 %2:%3 <span style="font-style: italic;">Action</span>:%4 Denied</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A user action on Gateway objects has been denied.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>User name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Object type</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Object name</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Action type</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the user profile.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP220W"></span>220</p>         </td>
         <td><p>SUP W BEFNTF Before Call %1, State FT %2, type Notif %3</p>         </td>
      </tr>
      <tr>
         <td><p><span id="SUP221W"></span>221</p>         </td>
         <td><p>SUP W AFTNTF State: %1, status: %2, After Call: %3</p>         </td>
      </tr>
      <tr>
         <td><p><span id="SUP222W"></span>222</p>         </td>
         <td><p>SUP W NTFRESP Response of %1, User todo %2, reason lib %3, reason %4</p>         </td>
      </tr>
      <tr>
         <td><p><span id="SUP223W"></span>223</p>         </td>
         <td><p>SUP W NTFNORESP After %1 without response</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>This message set is provided for user external exit debugging. These messages are written when the configuration parameter <span class="code">notif_log_level</span> is set to a value of 3 or greater.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Name of the user exit notification frame.</p>
<p>Other parameters correspond to different fields of the parameter area passed to the exit routine.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>No special action</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP224W"></span>224</p>         </td>
         <td><p><span style="font-weight: bold;">SUP W SITE-DOWN Site %1 disabled due to protocol error: %2</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The Site is disabled due to protocol error.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Alias Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Error code</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Analyze protocol trace and modify some definitions.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP225I"></span>225</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I XFERDELAY Transfer from %1 to %2, filename=%3, will start at %4in order to keep unicity of time</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>This message occurs when several transfers in Odette protocol are submitted at the same second. The monitor defers the transfer to keep the Odette key identifier.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Alias name of the originator Site</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Alias name of the destination Site</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Protocol-level file name</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Beginning date</p>         </td>
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
         <td><p><span id="SUP226W"></span>226</p>         </td>
         <td><p><span style="font-weight: bold;">SUP W SDISABLIC Site %1 disabled due to a missing option in the product license</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The Site exists but the user does not have the right to use it.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Site name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check option and license.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP227E"></span>227</p>         </td>
         <td><p><span style="font-weight: bold;">SUP E NOSITE (%1) Site %2 not found for protocol %3</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Template not found on incoming connection.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>internal reference</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Site name</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Protocol</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check or create Site.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP256W"></span>256</p>         </td>
         <td><p><span style="font-weight: bold;">SUP W MIR-DOWN Mirroring of transfer database disabled due to file error</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The Mirror Mailbox cannot be used anymore.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Stop Gateway and try to recover the Mailbox.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP257W"></span>257</p>         </td>
         <td><p><span style="font-weight: bold;">SUP W MIR-ERR Error on transfer mirror database ignored</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An error occurred but the <span class="code">mirror_action_on_err</span> configuration parameter value is different from 0 (stop the monitor) and 1 (stop the mirroring)</p>         </td>
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
         <td><p><span id="SUP258I"></span>258</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I PUR-BEG Begin of transfer purge session</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>This message occurs either when a cyclic purge starts, or when a user submits a purge request.</p>         </td>
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
         <td><p><span id="SUP259I"></span>259</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I PUR-END End of transfer purge session</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>This message occurs when all purge requests of the session are completed</p>         </td>
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
         <td><p><span id="SUP260I"></span>260</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I PUR-STAT %1 transfers purged for '%2' request</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>This message occurs when a purge request is ended</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Number of transfers purged</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Name of purged request</p>         </td>
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
         <td><p><span id="SUP261E"></span>261</p>         </td>
         <td><p><span style="font-weight: bold;">SUP E PUR-ERR Error while purging transfer, skipping request '%1' (%2 transfers purged</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An error occurs in a purge request. This purge request is skipped.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Name of purged request</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Number of transfers purged before error</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>The error may be a Mailbox integrity error. Stop monitor and check Mailbox integrity (refer to the <span class="code">pelmon</span> online command).</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP262I"></span>262</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I PUR-LOAD Adding periodic purge request '%1'</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>This message occurs at the startup of monitor if periodic purge parameter file is supplied</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Name of purged request</p>         </td>
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
         <td><p><span id="SUP263I"></span>263</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I PUR-ERR Error loading periodic purge request file '%1': %2</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>This message occurs at the startup of monitor if periodic purge parameter file is supplied</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>File path of purge parameter file</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>System error code</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check purge parameter file (access rights,...)</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP270I"></span>270</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I XEND_CF %1(%2) [%3] EERP routed towards %4 ident:%5</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The acknowledgement request has been routed successfully</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote agent name</p>         </td>
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
         <td><p>Remote agent of the routed acknowledgement request</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Local identifier of the routed acknowledgement request</p>         </td>
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
         <td><p><span id="SUP271W"></span>271</p>         </td>
         <td><p><span style="font-weight: bold;">SUP W NEERP_NR [%2] Negative EERP not routed due to negative acknowledgement option not set on site %1</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Corresponding option not set for this Site.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Transfer reference number</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check license. Check/create option.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP280I"></span>280</p>         </td>
         <td><p>SUP  I XSR_LINOK SecureRelay login accepted for user %1</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A login request from Secure Relay has been accepted.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>User name</p>         </td>
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
         <td><p><span id="SUP281I"></span>281</p>         </td>
         <td><p>SUP  I XSR_LINKO SecureRelay login refused for user %1 (reason %2)</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A login request from Secure Relay has been refused.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>User name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Reason code</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check previous message logs for further explanation.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP300E"></span>300</p>         </td>
         <td><p><span style="font-weight: bold;">SUP E TLS_ERR %1(%2) Site sprof checkfailed (%3)</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error while verifying matching between the used incoming security profile and the security profile in the connection Site field. The matching process takes place just after the protocol connection.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connected Site protocol identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Reason</p>
<p>Reason codes:</p>
<ul>
<li><strong>1</strong>: Security context not found. Disconnection happens (and security context is deleted) before the supervisor tries to check the security profile used in the connection.</li>
<li><span style="font-weight: bold;">10</span>: Incompatible type between the Site Security Profile type and the actual mode</li>
<li><span style="font-weight: bold;">11</span>: Client authentication is mandatory in the Security Profile for the Site, but the client failed to identify itself during the handshake phase</li>
<li><span style="font-weight: bold;">12</span>: Client authentication is imposed as anonymous in the Security Profile for the Site but the client identified itself during the handshake phase</li>
<li><span style="font-weight: bold;">13</span>: Server authentication is mandatory in the Security Profile for the Site but the server did not identify itself during the handshake phase</li>
<li><span style="font-weight: bold;">14</span>: Server authentication imposed as anonymous in the Security Profile for the Site but the server identified itself during the handshake phase</li>
<li><span style="font-weight: bold;">17</span>: The Security Profile for the Site has an incompatible exit scheduling value with the Security Profile used</li>
<li><span style="font-weight: bold;">18</span>: The Security Profile for the Site does not allow the cipher suite used</li>
<li><span style="font-weight: bold;">19</span>: The Security Profile for the Site does not allow the TLS version used</li>
<li><span style="font-weight: bold;">20</span>: Section "UserLocalCertificates" of the Security Profile for the Site does not contain the sent certificate (%4)</li>
<li><span style="font-weight: bold;">21</span>: Templates of new Security Profile do not match received certification chain</li>
<li><span style="font-weight: bold;">30</span>: The common name of the certificate received does not match the one set in the <span style="font-weight: bold;">Subject certificate alias</span> field of the Site</li>
<li><span style="font-weight: bold;">31</span>: The common name of the issuer certificate received does not match the one set in the <span style="font-weight: bold;">Issuer certificate alias</span> field of the Site</li>
<li><span style="font-weight: bold;">32</span>: The distinguished name of the certificate received does not match the pattern set in the <span style="font-weight: bold;">Subject name pattern</span> field of the Site</li>
<li><span style="font-weight: bold;">33</span>: The distinguished name of the issuer certificate received does not match the pattern set in the <span style="font-weight: bold;">Issuer name pattern</span> field of the Site</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the security profile defined in the <span class="code">tls_sprof_in</span> attribute of the Site and the Security Profile used to establish the session.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP371W"></span>371</p>         </td>
         <td><p>SUP W DUPFILE Could not create transfer: transfer [%1] with duplicate file already exists</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A transfer could not be created as the VFD record exists.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Identifier of the new transfer</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Identifier of the old transfer</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the VFD configuration.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP372W"></span>372</p>         </td>
         <td><p>372 SUP W DUPFILE Could not create transfer: transfer [%1] with duplicate file is in use</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A transfer could not be created as the VFD record is in use.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Identifier of the new transfer</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Identifier of the old transfer</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the VFD configuration.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP373W"></span>373</p>         </td>
         <td><p>SUP E DUPFILE [%1] transfer update failed: transfer [%2] with duplicate file already exists</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A transfer could not be updated as the VFD record exists.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Identifier of the new transfer</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Identifier of the old transfer</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the VFD configuration.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP374W"></span>374</p>         </td>
         <td><p>SUP E DUPFILE [%1] transfer update failed: transfer [%2] with duplicate file is in use</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A transfer could not be updated as a duplicate VFD record is in use.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Identifier of the new transfer</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Identifier of the old transfer</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the VFD configuration.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP375W"></span>375</p>         </td>
         <td><p>SUP W DUPFILE [%1] transfer request canceled by transfer request [%2]</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Supervisor canceled a transfer as duplicate record exists in VFD.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Identifier of the new transfer</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Identifier of the old transfer</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the VFD configuration.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP376W"></span>376</p>         </td>
         <td><p>SUP E DUPFILE [%1] transfer request could not be canceled by transfer request [%2]</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Supervisor tried to cancel a transfer due to a VFD duplicate record but the transfer was locked.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Identifier of the new transfer</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Identifier of the old transfer</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the VFD configuration.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP377W"></span>377</p>         </td>
         <td><p>SUP W XCOMSCR %1 [%3] transfer request canceled on max site connection retry</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The transfer is canceled as the maximum number of retries on the outgoing site has been reached.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Site alias that has reached maximum number of retries</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Identifier of the cancelled transfer</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the site configuration.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP378W"></span>378</p>         </td>
         <td><p>SUP W XRSINUSE [%1] Transfer IN USE on RESEND (refcount=%2)</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Warning that the transfer is in use on a RESEND.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer ID</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>EDI reference count (technical message for diagnostic)</p>         </td>
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
         <td><p><span id="SUP379W"></span>379</p>         </td>
         <td><p>SUP W XRSLOCKED [%1] Transfer LOCKED on RESEND</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Warning that the transfer is in locked on a RESEND.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer ID</p>         </td>
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
         <td><p><span id="SUP380W"></span>380</p>         </td>
         <td><p>SUP W XRSUPDERR [%1] Transfer UPDATE FAILURE on RESEND: %2</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Warning that the transfer update failed on a RESEND.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer IS</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Text message</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Diagnose according to text message (parameter 2).</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP381W"></span>381</p>         </td>
         <td><p>SUP W XRSGETERR [%1] Transfer GET FAILURE on RESEND: %2</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Warning that the transfer GET failed on a RESEND.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer ID</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Text message</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Diagnose according to text message (parameter 2).</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP382I"></span>382</p>         </td>
         <td><p>SUP I XRSRSTOK [%1] Transfer successfully restarted for RESEND</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information (trace message)</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The transfer successfully restarted on a RESEND.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer ID</p>         </td>
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
         <td><p><span id="SUP383I"></span>383</p>         </td>
         <td><p>SUP I XRSCANOK [%1] Transfer successfully canceled for RESEND</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information (trace message)</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The transfer successfully cancelled on a RESEND</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer ID</p>         </td>
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
         <td><p><span id="SUP384W"></span>384</p>         </td>
         <td><p>SUP W XTBINUSE [%1] Transfer IN USE on DATE TO BEGIN reached (refcount=%2)</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Warning that the transfer is already in use on the <span style="font-style: italic;">date to begin</span> trigger</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer ID</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Reference count (for diagnostic)</p>         </td>
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
         <td><p><span id="SUP385W"></span>385</p>         </td>
         <td><p>SUP W XTBLOCKED [%1] Transfer LOCKED on DATE TO BEGIN reached</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Warning that the transfer is locked, when reaching the <span style="font-style: italic;">date to begin</span> trigger</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer ID</p>         </td>
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
         <td><p><span id="SUP386W"></span>386</p>         </td>
         <td><p>SUP W XTBUPDERR [%1] Transfer UPDATE FAILURE on DATE TO BEGIN reached: %2</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Warning that the transfer has had an <span style="font-style: italic;">update failure</span>, before reaching the <span style="font-style: italic;">date to begin</span> trigger</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer ID</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Text message indicating error context</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Action depends on text message content.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP387W"></span>387</p>         </td>
         <td><p>SUP W XTBGETERR [%1] Transfer GET FAILURE on DATE TO BEGIN reached: %2</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Warning that the transfer has registered a <span style="font-style: italic;">get failure</span>, when reaching the <span style="font-style: italic;">date to begin</span> trigger</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer ID</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Text message indicating error context</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Action depends on text message content</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP388E"></span>388</p>         </td>
         <td><p>SUP E XTBGIVEUP [%1] Transfer NOT UPDATED on DATE TO BEGIN reached due to unrecoverable error</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The transfer has not been updated when reaching the <span style="font-style: italic;">date to begin</span> trigger</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer ID</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Analyze the log messages that immediately precede this message to understand the failure context. This message is always preceded in the log by one of the SUP warning messages: <span style="font-weight: bold;">384</span>,<span style="font-weight: bold;"> 385</span>,<span style="font-weight: bold;"> 386</span>,<span style="font-weight: bold;"> 387</span>.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP389I"></span>389</p>         </td>
         <td><p>SUP I XTBUPDOK [%1] Transfer state successfully changed on date to begin reached</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>This message only occurs when the File Transfer log level is &gt;3.</p>
<p>The transfer state has been changed when reaching the <span style="font-style: italic;">date to begin</span> trigger.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer ID</p>         </td>
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
         <td><p><span id="SUP394W"></span>394</p>         </td>
         <td><p>SUP W XTEINUSE [%1] Transfer IN USE on DATE TO END reached (refcount=%2)</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Warning that the transfer was in use when the <span style="font-style: italic;">date to end</span> trigger was reached.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer ID</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Reference counter number</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>No user action. Gateway initiates an automatic retry after 30 seconds</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP395W"></span>395</p>         </td>
         <td><p>SUP W XTELOCKED [%1] Transfer LOCKED on DATE TO END reached</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Warning that the transfer was locked when the <span style="font-style: italic;">date to end</span> trigger was reached.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer ID</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>No user action. Gateway initiates an automatic retry after 30 seconds.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP396W"></span>396</p>         </td>
         <td><p>SUP W XTEUPDERR [%1] Transfer UPDATE FAILURE on DATE TO END reached: %2</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Warning that the transfer update failed when the <span style="font-style: italic;">date to end</span> trigger was reached.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer ID</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Text message describing failure context, for diagnosis</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Analyze failure context.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP397W"></span>397</p>         </td>
         <td><p>SUP W XTEGETERR [%1] Transfer GET FAILURE on DATE TO END reached: %2</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Warning that there was a transfer <span style="font-style: italic;">get</span> failure when the <span style="font-style: italic;">date to end</span> trigger was reached.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer ID</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Text message describing failure context, for diagnosis</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Analyze failure context.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP398E"></span>398</p>         </td>
         <td><p>SUP E XTEGIVEUP [%1] Transfer NOT CANCELLED on DATE TO END reached due to unrecoverable error</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The transfer was not cancelled, due to an unrecoverable error, when the <span style="font-style: italic;">date to end</span> trigger was reached.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer ID</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Analyze the log messages that immediately precede this message to understand the failure context. This message is always preceded in the log by one of the SUP warning messages: <span style="font-weight: bold;">394</span>,<span style="font-weight: bold;"> 395</span>,<span style="font-weight: bold;"> 396</span>,<span style="font-weight: bold;"> 397</span>.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP399I"></span>399</p>         </td>
         <td><p>SUP I XTECANOK  [%1] Transfer successfully cancelled on date to end reached</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information (trace message)</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The transfer was successfully canceled when the <span style="font-style: italic;">date to end</span> trigger was reached.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer ID</p>         </td>
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
         <td><p><span id="SUP400I"></span>400</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I XEND_CF %1(%2) [%3] Not routed, %4: %5</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Routing was not successful because a condition was not met.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote agent name</p>         </td>
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
         <td><p>Parameter whose condition was not met</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Value of the parameter</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Analyze why the routing was not successful.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP401I"></span>401</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I XEND_CF %1(%2) [%3] Not routed, local_ident and remote_agent are not different</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Routing was not successful because the transfer destination Site (<span class="code">remote_agent</span>) is not different from the Local Site (<span class="code">local_agent</span>).</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote agent name</p>         </td>
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
         <td><p>Action</p>         </td>
         <td><p>None</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP411I"></span>411</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I XEND_CF %1(%2) [%3] Not Routed, %4 : %5 is a local site</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The selected destination is a Local Site.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote agent name</p>         </td>
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
         <td><p>Object and parameters:</p>
<ul>
<li>Model remote_agent</li>
<li>Model org_alias</li>
<li>Model dest_alias</li>
<li>CGate route_remote_agent</li>
<li>VFD route_remote_agent</li>
<li>Site route_remote_agent</li>
<li>Destination</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Selected Site alias</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Analyze why routing was not successful.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP412I"></span>412</p>         </td>
         <td><p><span style="font-weight: bold;">SUP I XEND_CF %1(%2) [%3] Not Routed, %4 : site %5 is not defined</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The selected destination is not defined.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote agent name</p>         </td>
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
         <td><p>Object and parameters:</p>
<ul>
<li>Model remote_agent</li>
<li>Model org_alias</li>
<li>Model dest_alias</li>
<li>CGate route_remote_agent</li>
<li>VFD route_remote_agent</li>
<li>Site route_remote_agent</li>
<li>Destination</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Selected Site alias</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Analyze why the routing was not successful.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP470W"></span>470</p>         </td>
         <td><p><span style="font-weight: bold;">SUP W COUS User %1: max upload rate exceeded, aborting transfers</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The given user exceeded upload rate quota. All current transfers are aborted and new upload transfers are not allowed for this user until the user's total upload use decreases.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>User name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>An attack was detected according to the quotas given. Either increase the quota for this user, reset the Connected User, or, forbid access to this user.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP471W"></span>471</p>         </td>
         <td><p>SUP W COUS User %1: max download rate exceeded, aborting transfers</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The given user exceeded the download rate quota. All current transfers are aborted and new download transfers are not allowed for this user until the user's total download use decreases.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>User name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>An attack was detected according to the quotas given. Either increase the quota for this user, reset the Connected User, or forbid access to this user.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SUP472W"></span>472</p>         </td>
         <td><p><span style="font-weight: bold;">SUP W COUS User %1: max command rate exceeded, aborting connections</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The given user exceeded the command sensitivity quota. All this user's connections are closed, and no new connections are allowed for this user until the user's total command use decreases.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>User name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>An attack was detected according to the quotas given. Either increase the quota for this user, reset the connected user, or forbid access to this user.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="AMT520I"></span>520</p>         </td>
         <td><p><span style="font-weight: bold;">AMT I AMTS_ROUT %1[%2] transfer routed to AMTRIX/XIB. file=%3</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Indicates that the transfer was routed to the Axway Integrator connector.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Transfer ID</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>File name</p>         </td>
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
         <td><p><span id="AMT521E"></span>521</p>         </td>
         <td><p><span style="font-weight: bold;">AMT E AMTS_ROUT %1[%2] AMTRIX/XIB route failed. file=%3</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error message indicating that the transfer intended for the Axway Integrator connector cannot be routed.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Transfer ID</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>File name</p>         </td>
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
         <td><p><span id="AMT522E"></span>522</p>         </td>
         <td><p><span style="font-weight: bold;">AMT E AMTS_API %1[%2] XFBCONN connector error. Verb=%3. Reason=%4 [%5]</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error message indicating that the transfer intended for the Axway Integrator connector cannot be routed.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Transfer ID</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>XFBCONN API provoking the error</p>         </td>
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
         <td><p><span id="AMT523I"></span>900</p>         </td>
         <td><strong>SUP E INTHP [%1] Unable to read transfer %2</strong>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td>Transfer not found in database         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td>Transfer local identifier         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td>Error code (number)         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="AMT523I"></span>901</p>         </td>
         <td><strong>SUP E INTHP [%1] Unable to write signature data %2</strong>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td>Can't attach signature information to the transfer         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer local identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Error code (number)</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="AMT523I"></span>903</p>         </td>
         <td><p><strong>SUP E INTHP [%1] Unable to write transfer %2</strong></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Can't update transfer</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer local identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Error code (number)</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="AMT523I"></span>904</p>         </td>
         <td><p><strong>SUP E INTHP Internal error (%1) %2</strong></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Unexpected error</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Error code (number)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Error description</p>         </td>
      </tr>
   </tbody>
</table>

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="AMT523I"></span>906</p>         </td>
         <td><strong>SUP W INTHP [%1] No payload, skip integrity processing</strong>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td>Warning         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td>Transfer doesn't have a payload, no integrity operation is performed         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td>Transfer local identifier         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="AMT523I"></span>907</p>         </td>
         <td><strong>SUP I INTHP [%1] Signature %2 successfuly</strong>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td>Information         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td>Signature was either generated or verified succcessfuly         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td>integrity operation performed         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="AMT523I"></span>908</p>         </td>
         <td><strong>SUP E INTHP [%1] Signature %2 failed</strong>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td>Error         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td>Signature generation or verification failed         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td>integrity operation performed         </td>
      </tr>
   </tbody>
</table>

 

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
