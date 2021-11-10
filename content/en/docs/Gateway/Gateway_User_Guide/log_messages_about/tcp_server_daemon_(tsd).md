{
    "title": "TCP Server Daemon (TSD)",
    "linkTitle": "TCP Server Daemon (TSD)",
    "weight": "500"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Messages and codes

This topic lists TCP Server Daemon log messages.

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TSD001I"></span>001</p>         </td>
         <td><p>TSD I CPORT_UP Control port %1 successfully attached</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Indicates that the TSD is ready to communicate with its dynamic servers.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Port name comprised of its local address and port number</p>         </td>
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
         <td><p><span id="TSD002I"></span>002</p>         </td>
         <td><p><span style="font-weight: bold;">TSD I SPORT_UP Port %2 for service %1 successfully attached</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Indicates that the TSD now listens to incoming connections on port %2 for the service %1.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Service name (HTTP, FTP, PEL, ODT or PHSE)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Port name comprised of its local address and port number</p>         </td>
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
         <td><p><span id="TSD003I"></span>003</p>         </td>
         <td><p><span style="font-weight: bold;">TSD I PROCS_UP Process %1 successfully launched for service %2</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A new dynamic process has been launched and is ready to accept connections for the service %2.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Process name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Service name (HTTP, FTP, PEL, ODT or PHSE)</p>         </td>
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
         <td><p><span id="TSD004I"></span>004</p>         </td>
         <td><p><span style="font-weight: bold;">TSD I PROCS_DN Process %1 successfully ended for service %2</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A dynamic process ended as planned and can be launched again later on.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Process name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Service name (HTTP, FTP, PEL, ODT or PHSE)</p>         </td>
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
         <td><p><span id="TSD005I"></span>005</p>         </td>
         <td><p><span style="font-weight: bold;">TSD I ICONX_UP Incoming connection port %2 for service %1 accepted</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A dynamic process of the service %2 accepted the incoming connection.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Service name (HTTP, FTP, PEL, ODT or PHSE)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Port name comprised of its local address and port number</p>         </td>
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
         <td><p><span id="TSD006I"></span>006</p>         </td>
         <td><p><span style="font-weight: bold;">TSD I ICONX_DN Incoming connection for service %1 closed</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A dynamic process for the service %1 closed a connection normally.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Service name (HTTP, FTP, PEL, ODT or PHSE)</p>         </td>
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
         <td><p><span id="TSD007E"></span>007</p>         </td>
         <td><p><span style="font-weight: bold;">TSD E CPORT_ER Can't attach control port %1</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The TSD is not able to communicate with its dynamic servers and cannot go on.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Port name comprised of its local address and port number</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check that the port is not already occupied. If other ports where specified, the TSD is able to find them. If there is no remaining free port, the TSD stops.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TSD008W"></span>008</p>         </td>
         <td><p><span style="font-weight: bold;">TSD W SPORT_ER Can't attach port %2 for service %1</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A listen point was not created for the service %1.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Service name (HTTP, FTP, PEL, ODT or PHSE)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Port name comprised of its local address and port number</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check that the port is not already occupied.</p>
<p>If the service has other ports, it still may be able to receive incoming connections.</p>
<p>Check the TCP/IP settings in the Gateway configuration menu.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TSD009E"></span>009</p>         </td>
         <td><p><span style="font-weight: bold;">TSD E PROCS_NO Process launch failed for service %1</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A dynamic process was not launched for the service %1.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Service name (HTTP, FTP, PEL, ODT or PHSE)</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check that no binary file has been deleted, renamed or moved away. Restart Gateway when the problem is fixed.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TSD010E"></span>010</p>         </td>
         <td><p><span style="font-weight: bold;">TSD E PROCS_ER Process %1 abnormally ended for service %2</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A dynamic process of the service %2 unexpectedly stopped.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Process name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Service name (HTTP, FTP, PEL, ODT or PHSE)</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>The process will be automatically restarted if necessary.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TSD011E"></span>011</p>         </td>
         <td><p><span style="font-weight: bold;">TSD E ICONX_NO Incoming connection port %2 for service %1 refused</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The service %2 is not currently able to handle more connections.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Service name (HTTP, FTP, PEL, ODT or PHSE)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Port name comprised of its local address and port number</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the service for the reason.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TSD012W"></span>012</p>         </td>
         <td><p><span style="font-weight: bold;">TSD W SPORT_CO Conflicting port %1 between services %2 and %3</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Two services are using the same port.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Port name comprised of its local address and port number</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Service name (HTTP, FTP, PEL, ODT or PHSE)</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the TCP/IP settings in the Gateway configuration menu.</p>
<p>Change conflicting ports.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TSD014I"></span>014</p>         </td>
         <td><p>TSD I MAXC_LOW Maximum connections for service %1 lowered to %2 due to process resource limit</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The number of maximum possible connections has been reduced due to resource limits.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Service name (HTTP, FTP, PEL, ODT or PHSE)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>New maximum connections limit</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Manage connections according to resource limits.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TSD020I"></span>020</p>         </td>
         <td><p>TSD I XSR_CTING [%1] Connecting to XSR agent</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Connecting to the Secure Relay Router Agent.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>IP address/TCP port</p>         </td>
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
         <td><p><span id="TSD021I"></span>021</p>         </td>
         <td><p>I XSR_CTED [%1] Connection with XSR agent established</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A connection with the Secure Relay Router Agent has been established.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>IP address/TCP port</p>         </td>
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
         <td><p><span id="TSD022W"></span>022</p>         </td>
         <td><p>TSD W XSR_CREFU [%1] Connection refused by XSR agent</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A connection with the Secure Relay Router Agent has been refused.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>IP address/TCP port</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the configuration of the connection.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TSD023W"></span>023</p>         </td>
         <td><p>TSD W XSR_CDOWN [%1] Connection with XSR agent broken</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The connection with the Secure Relay Router Agent is broken.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>IP address/TCP port</p>         </td>
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
         <td><p><span id="TSD024I"></span>024</p>         </td>
         <td><p>TSD I XSR_SAPOK [%1] Sap %2 successfully routed to %3 by XSR agent</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The SAP indicated in the message has been successfully routed by the Secure Relay Router Agent to the address indicated in the message.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>IP address/TCP port</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Local SAP address and access port</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Routing destination address and access port</p>         </td>
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
         <td><p><span id="TSD025E"></span>025</p>         </td>
         <td><p>TSD E XSR_SAPKO [%1] Sap %2 not routed to %3 by XSR agent: error=%4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The SAP indicated in the message has not been routed by the Secure Relay Router Agent to the address indicated in the message. The error code is included in the message.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>IP address/TCP port</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Local SAP address and access port</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Routing destination address and access port</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Secure Relay error code:</p>
<ul>
<li><span style="font-weight: bold;">2</span> = Secure Relay Router Agent could not establish SAP, either because the port number is non-valid or the port is occupied</li>
<li><span style="font-weight: bold;">4</span> = The Secure Relay Router Agent is not started</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Interpret the message depending on the error code.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TSD026E"></span>026</p>         </td>
         <td><p>TSD E XSR_UNERR [%1] Unexpected error: %2</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Unexpected error.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>IP address/TCP port</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Secure Relay error text message</p>         </td>
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
         <td><p><span id="TSD027E"></span>027</p>         </td>
         <td><p>TSD E XSR_VMISM [%1] XSR version mismatch, expecting %2-%3 received %4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Secure Relay version out of range.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>IP address/TCP port</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Minimum version</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Current version</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Received version</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check version prerequisites between Secure Relay Master Agent and Router Agent.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TSD028E"></span>028</p>         </td>
         <td><p>TSD E XSR_HELKO [%1] Error %2 received in HELLO RESP</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Secure Relay error.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>IP address/TCP port</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Error ID</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check version prerequisites between Secure Relay Master Agent and Router Agent.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TSD029E"></span>029</p>         </td>
         <td><p>TSD E XSR_UNRSP [%1] Unexpected response code=%2 received</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Possible protocol error.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>IP address/TCP port</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Response code</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Make sure you are using the right version of Secure Relay.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TSD030I"></span>030</p>         </td>
         <td><p>TSD I XSR_HELOK [%1] Handshake XSR OK, will use XSR protocol version %2</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The protocol handshake completed successfully and the common protocol version was established.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>IP Address and port</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Protocol version</p>         </td>
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
         <td><p><span id="TSD031I"></span>031</p>         </td>
         <td><p>TSD I XSR_CFINI [%1] Connection with XSR agent finished</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Connection terminated correctly</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>IP address/TCP port</p>         </td>
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
         <td><p><span id="TSD032I"></span>032</p>         </td>
         <td><p>TSD I XSR_VLOWR [%1] HELLO RESP received, lower XFBRELAY version required</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Server version problem (too high for client)</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>IP address/TCP port</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check Secure Relay Router Agent version.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TSD033I"></span>033</p>         </td>
         <td><p>TSD I XSR_LG_OK XSR-MA successfully establishes the log channel</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Secure Relay Master Agent has successfully established the log channel.</p>         </td>
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
         <td><p><span id="TSD034E"></span>034</p>         </td>
         <td><p>TSD E XSR_LG_KO XSR-MA is unable to establish the log channel. Cause: %1</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Secure Relay Master Agent cannot establish the log channel.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Error cause</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check Secure Relay Router Agent version.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TSD035E"></span>035</p>         </td>
         <td><p>TSD E XSR_NOSPR A security profile should be set for service %1 port %2</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>No security profile has been set for the reported service.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Service name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Service port</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Create a security profile for the reported service.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TSD036E"></span>036</p>         </td>
         <td><p>TSD E XSR_NOSPR Security params encoding error for service %1 port %2 security profile %3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>There was an en encoding error for the parameters for the given service, port and security profile.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Service name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Service port</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Service security profile</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check that the service name, port and security profile are correctly set.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TSD037E"></span>037</p>         </td>
         <td><p>TSD E XSR_GENER %1</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An error has occurred. This log message is used for miscellaneous errors.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Error description</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Depends on the error description.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TSD038W"></span>038</p>         </td>
         <td><p>TSD W XSR_VERMI SecureRelay protocol version is %1, it should be %2</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The Secure Relay protocol version is different from the one used by Gateway.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Secure Relay protocol version</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Gateway protocol version</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Make sure you have the right version of Secure Relay.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TSD039E"></span>039</p>         </td>
         <td><p>TSD E XSR_UNREQ Invalid SecureRelay request %1 received, expected a LOGIN_IND request</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An invalid request was received from Secure Relay instead of a LOGIN_IND request.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Request ID</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Make sure you are using the right version of Secure Relay.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TSD040I"></span>040</p>         </td>
         <td><p>TSD I XSR_LINRD SecureRelay login service ready on %1/%2</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The Secure Relay login service is ready on the given address and port.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Host address</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Port number</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>None</p>         </td>
      </tr>
   </tbody>
</table>

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
