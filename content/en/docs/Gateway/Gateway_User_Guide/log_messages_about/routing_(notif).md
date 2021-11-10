{
    "title": "Routing (NOTIF)",
    "linkTitle": "Routing (NOTIF)",
    "weight": "410"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Messages and codes

This topic lists routing (NOTIF) log messages.

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="NOT402I"></span>402</p>         </td>
         <td><p><span style="font-weight: bold;">NOT I XEND_CF [%1] Final destination = %2 undefined</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The final destination does not exist.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Final destination name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Create the final destination corresponding object.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="NOT403I"></span>403</p>         </td>
         <td><p><span style="font-weight: bold;">NOT I XEND_CF [%1] %2 = %3 selected for routing</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A destination, towards which the received file will be transferred, has been selected.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Routing according to the selected object. The partner used for the routed transfer is chosen according to one of the following parameters:</p>
<ul>
<li><span class="code">dest_alias</span> associated with a Model</li>
<li><span class="code">route_remote_agent</span> associated with a CGATE</li>
<li><span class="code">route_remote_agent</span> associated with a directory file (VFD)</li>
<li><span class="code">route_remote_agent</span> associated with a Site</li>
<li>transfer destination</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Selected Remote Site alias</p>         </td>
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
         <td><p><span id="NOT404E"></span>404</p>         </td>
         <td><p><span style="font-weight: bold;">NOT E XEND_CF [%1] Routing failure: type = %2, protocol = %3</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Routing failure: the transfer type and the protocol are not compatible.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Transfer type</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Protocol</p>         </td>
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
         <td><p><span id="NOT405E"></span>405</p>         </td>
         <td><p><span style="font-weight: bold;">NOT E XEND_CF [%1] Routing failure: model = %2 not found</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Routing failure: the referenced Model was not found.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Model name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Create the referenced Model.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="NOT406E"></span>406</p>         </td>
         <td><p><span style="font-weight: bold;">NOT E XEND_CF [%1] Routing failure: no remote_agent selected</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Routing failure: no Remote Site has been selected.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Complete the routing definitions.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="NOT407E"></span>407</p>         </td>
         <td><p><span style="font-weight: bold;">NOT E XEND_CF [%1] Routing failure: % 2 is not defined</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Routing failure: the selected destination has not been defined.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Selected Site alias</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Create the corresponding Site.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="NOT408E"></span>408</p>         </td>
         <td><p><span style="font-weight: bold;">NOT E XEND_CF [%1] Routing failure: %2 is a local site</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Routing failure: the selected destination is a Local Site.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Selected Site alias</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Select a Remote Site to route to.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="NOT409E"></span>409</p>         </td>
         <td><p><span style="font-weight: bold;">NOT E XEND_CF routing failure: XferRequest error, ErrCod = %1, errno = %2</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Routing failure: the monitor failed during the new transfer request deposit.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Corresponding local error (if any)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>System specific return code</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Analyze why monitor failed during new transfer request deposit.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="NOT410S"></span>410</p>         </td>
         <td><p><span style="font-weight: bold;">NOT S XEND_CF [%1] Routing towards %2, ident %3, model %4, route_from_xfer %5</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Success</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Routing was successful towards the Site %2</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Routing Site name</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>New transfer identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Name of the Model used</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Transfer identifier that is linked to the new transfer</p>         </td>
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
         <td><p><span id="NOT420I"></span>420</p>         </td>
         <td><p><span style="font-weight: bold;">NOT I XEND_CF [%1] Decision rule [%2], condition (%3 %4 %5) = FALSE</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Condition %2 of the Decision Rule is not in agreement with the incoming transfer. Therefore this rule will not be selected.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Condition that the incoming transfer does not agree with</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Operator</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Value</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Analyze why the Decision Rule was not selected.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="NOT421I"></span>421</p>         </td>
         <td><p><span style="font-weight: bold;">NOT I XEND_CF [%1] Decision rule [%2] selected, execution type = %3</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Indicates the name and execution type of the Decision Rule selected.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Decision Rule name</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Type of processing that will be applied. One of the following execution types:</p>
<ul>
<li>Application of a Model</li>
<li>Execution of a Perl script or command line</li>
<li>Redirection to AMTrix/ Axway Integrator</li>
<li>None</li>
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
         <td><p><span id="NOT422I"></span>422</p>         </td>
         <td><p><span style="font-weight: bold;">NOT I XEND_CF [%1] Default Model %2 will be applied</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Indicates the name of the Model referenced at the table level that will be applied if the incoming transfer does not agree with any rule.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Name of the Model, defined at the table level, that will be applied</p>         </td>
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
         <td><p><span id="NOT423I"></span>423</p>         </td>
         <td><p><span style="font-weight: bold;">NOT I XEND_CF [%1] Model %2 will be applied</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Indicates the name of the Model that will be applied as referenced in the selected Decision Rule.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
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
         <td><p><span id="NOT424E"></span>424</p>         </td>
         <td><p><span style="font-weight: bold;">NOT E XEND_CF [%1] No model is referenced</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>No Model name is referenced at the Decision Rule level or the table level.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Analyze why the Model cannot be applied.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="NOT425I"></span>425</p>         </td>
         <td><p><span style="font-weight: bold;">NOT I XEND_NOT I XEND_CF [%1] Decision rule [%2]: after substituting symbolic variable in the condition (%3 %4 %5), incorrect type for the value</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The Decision Rule does not return the correct type of variable after substituting the symbolic variable.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Decision Rule name</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Argument</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Operator</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Value</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Analyze why the Decision Rule will not be selected.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="NOT426I"></span>426</p>         </td>
         <td><p><span style="font-weight: bold;">NOT I XEND_CF [%1] For Model %2, value %3 is not valid for the parameter %4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>At the level of the Model %2 that will be applied, the parameter and corresponding value are not compatible.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Model name</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Invalid value</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Parameter (the Model parameter that does not allow the defined value)</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Analyze why the Model cannot be applied.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="NOT427E"></span>427</p>         </td>
         <td><p><span style="font-weight: bold;">NOT E XEND_CF [%1] Not routed, %2 : %3</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Routing was not successful because a condition was not met.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Parameter whose condition was not met</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
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
         <td><p><span id="NOT428E"></span>428</p>         </td>
         <td><p><span style="font-weight: bold;">NOT E XEND_CF [%1] Not routed, local_ident and remote_agent</span><span style="font-weight: bold;">are the same</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The origin (source) and destination are the same.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Modify either the <span class="code">local_ident</span> or the <span class="code">remote_agent</span>.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="NOT429E"></span>429</p>         </td>
         <td><p><span style="font-weight: bold;">NOT E XEND_CF [%1] Not routed, %2 : %3 is a local site</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Routing failure: the selected destination is a Local Site.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Object and parameters:</p>
<ul>
<li>Model <span class="code">remote_agent</span></li>
<li>Model <span class="code">org_alias</span></li>
<li>Model <span class="code">dest_alias</span></li>
<li>CGate <span class="code">route_remote_agent</span></li>
<li>VFD <span class="code">route_remote_agent</span></li>
<li>Site <span class="code">route_remote_agent</span></li>
<li>Destination</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Selected Site alias</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Select Remote Site to route to.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="NOT430E"></span>430</p>         </td>
         <td><p><span style="font-weight: bold;">NOT E XEND_CF [%1] Not routed, %2 : site %3 is not defined</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Routing failure: the selected destination was not defined.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Object and parameters:</p>
<ul>
<li>Model <span class="code">remote_agent</span></li>
<li>Model <span class="code">org_alias</span></li>
<li>Model <span class="code">dest_alias</span></li>
<li>CGate <span class="code">route_remote_agent</span></li>
<li>VFD <span class="code">route_remote_agent</span></li>
<li>Site <span class="code">route_remote_agent</span></li>
<li>Destination</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Selected Site alias</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Create the corresponding Site.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="NOT431I"></span>431</p>         </td>
         <td><p><span style="font-weight: bold;">NOT I XEND_CF [%1] Perl script %2 will be executed</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Indicates the Perl script that will be executed.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Absolute path of the Perl script that will be executed</p>         </td>
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
         <td><p><span id="NOT432E"></span>432</p>         </td>
         <td><p><span style="font-weight: bold;">NOT E XEND_CF [%1] No perl script is referenced</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>No Perl script is referenced at the table level or the level of the Decision Rule selected.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Analyze why the Perl script cannot be executed.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="NOT433I"></span>433</p>         </td>
         <td><p><span style="font-weight: bold;">NOT I XEND_CF [%1] Default perl script %2 will be executed</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Indicates the default Perl script, referenced at the table level that will be executed.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Absolute path of the Perl script, referenced at the table level, that will be executed if no rules satisfy the incoming transfer</p>         </td>
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
         <td><p><span id="NOT434E"></span>434</p>         </td>
         <td><p><span style="font-weight: bold;">NOT E XEND_CF [%1] For General Model %2, %3 %4 is not defined</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Indicates that one of the parameters of a General Model is not valid.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Name of the General Model</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Model parameter that is not defined:</p>
<ul>
<li>remote_agent</li>
<li>org_alias</li>
<li>dest_alias</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Selected Site alias</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Analyze why the General Model is not correct.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="NOT435E"></span>435</p>         </td>
         <td><p><span style="font-weight: bold;">NOT E XEND_CF [%1] Perl script %2 doesn't exist</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Indicates that the Perl script does not exist.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Absolute path of the referenced Perl script</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Analyze why the Perl script cannot be executed.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="NOT436I"></span>436</p>         </td>
         <td><p><span style="font-weight: bold;">NOT I XEND_CF [%1] The command line %2 will be executed</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Indicates that the specified command will be executed.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Command line that will be executed. This command includes an executable program as well as its arguments.</p>         </td>
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
         <td><p><span id="NOT437E"></span>437</p>         </td>
         <td><p><span style="font-weight: bold;">NOT E XEND_CF [%1] No command line is referenced</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>No command line is referenced at the table level or in the Decision Rule selected.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Analyze why the execution of the command line cannot be executed.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="NOT438I"></span>438</p>         </td>
         <td><p><span style="font-weight: bold;">NOT I XEND_CF [%1] The default command line %2 will be executed</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Indicates the default command line, referenced at the table level that will be executed if no rules satisfy the incoming transfer.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Command line (referenced at the table level) that will be executed. This command includes an executable program as well as these arguments.</p>         </td>
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
         <td><p><span id="NOT439I"></span>439</p>         </td>
         <td><p><span style="font-weight: bold;">NOT I XEND_CF [%1] Default Execution type = %2</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Indicates that the default execution type will be activated.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Type of processing that will be applied. One of the following execution types:</p>
<ul>
<li>Application of a Model</li>
<li>Execution of a Perl script or shell</li>
<li>Redirection to AMTrix/Axway Integrator</li>
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
         <td><p><span id="NOT440I"></span>440</p>         </td>
         <td><p><span style="font-weight: bold;">NOT I XEND_CF [%1] Resulting %2 parameter = "%3" in the Model %4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Provides information on the resolved Model.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Parameter name</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Parameter value after substitution of the symbolic variable</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Name of the referenced Model in the selected Decision Rule</p>         </td>
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
         <td><p><span id="NOT442I"></span>442</p>         </td>
         <td><p>NOT I XEND_CF Examining rule table [%1]</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Indicates that the Rule Table is being examined.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Name of Rule Table</p>         </td>
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
         <td><p>443</p>         </td>
         <td><p>[%1] Rule table [%2] , condition (%3 %4 %5) = FALSE</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Displays the evaluations done when searching for a decision rule to match.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td>Identifier of the evaluated transfer         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td>The evaluated rule table         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td>Selection criteria         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td>Selection value         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td>Evaluation result         </td>
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
         <td><p>444</p>         </td>
         <td><p>Trading partner %1 not found when sending automatic receipt for transfer [%2]</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The trading partner needed for sending the receipt was not found</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Originating trading partner for incoming transfer</p>         </td>
      </tr>
      <tr>
         <td>          </td>
         <td><p>2</p>         </td>
         <td>Identifier of the incoming transfer         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check trading partner configuration</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p>445</p>         </td>
         <td><p>[%1] Routing to XIB not performed, no payload file</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A decision rule is trying to route to XIB a transfer that does not have payload</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Identifier of the transfer</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check decision rules and do not route to XIB transfers with no payload. They have no meaning for XIB</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="NOTE690E"></span>690</p>         </td>
         <td><p>NOTE  E TRINEX  Transfer to route %1 does not exist</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Transfer cannot be routed since routing encountered too many errors. The transfer has been purged or deleted before being routed.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Avoid purging or deleting transfers before they are routed.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="NOTE691E"></span>691</p>         </td>
         <td><p>NOTE  E TRLOCKED  Transfer to route %1 is currently locked</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Transfer cannot be routed since routing encountered too many errors. The transfer is currently in use.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the transfer state to avoid this problem.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="NOTE692E"></span>692</p>         </td>
         <td><p>NOTE  E TRACCERR  Transfer to route %1 access error: %2</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Transfer cannot be routed since routing encountered too many errors.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Access error message</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>The error message should give a hint regarding the routing problem.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="NOTE693E"></span>693</p>         </td>
         <td><p>NOTE  E TRPRMERR  Too many routing errors (%2), ignoring transfer %1</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Transfer cannot be routed since routing encountered too many errors.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Number of trials</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the routing rules.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="NOTE694E"></span>694</p>         </td>
         <td><p>NOTE  E XEND_CF  [%1] Error while executing the command line %2</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The command line referenced at the table level or in the selected Decision Rule cannot be executed properly.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Command line to be executed (this command includes an executable program as well as its arguments)</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the command line spelling, rights or content.</p>         </td>
      </tr>
   </tbody>
</table>

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
