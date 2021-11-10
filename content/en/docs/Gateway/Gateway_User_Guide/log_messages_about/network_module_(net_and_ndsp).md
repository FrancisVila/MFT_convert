{
    "title": "Network module (NET and NDSP)",
    "linkTitle": "Network module (NET and NDSP)",
    "weight": "320"
}This topic lists Network module log messages.

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="NET001E"></span>001</p>         </td>
         <td><p><span style="font-weight: bold;">NET E COMMER %1</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An error condition has been reported by the underlying network subsystem. This software, which is supported by the operating system and/or the communication card, is platform dependent.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Name of the communication service (API routine or system service) and an error number with additional text that usually describes the problem</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Refer to the documentation supplied with the communication interface for information on the error reported. You may also need to check the documentation for the OS.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="NET002I"></span>002</p>         </td>
         <td><p>NET I INITDONE comm_type=%1 - sap="%2" - incoming_max=%3 - device_name=%4 local_address=%5</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Successful initialization of the network interface. The parameters are those used for the initialization. They reflect the configuration selected during Gateway installation.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Type of network support. Possible values are:TCP, DSA, LU 62, PAD.</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Selection parameters for incoming calls whose formats depend on the underlying network type and OS platform:</p>
<ul>
<li>TCP/IP: port number for listening for incoming calls</li>
<li>PAD: protocol-id or an entry point in the routing table for incoming calls</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Maximum number of incoming connection calls. This parameter is used to limit the number of simultaneous incoming calls.</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Name referencing the communication hardware or software used by the network interface, depending on the type of network used.</p>
<p>Used for some platforms only. It is typically used to select an attachment point or a communication card.</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>References an access point to reach the local host from the network area</p>         </td>
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
         <td><p><span id="NDSP011I"></span>011</p>         </td>
         <td><p>NDSP I REQ outgoing connection request [prot="%1"/comm="%2"/src="%3"/dest="%4"/udata="%5"]</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The network connection requested by a protocol module has been routed to the corresponding network subsystem.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>File transfer protocol module that requested the network connection</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Network subsystem: TCP, DSA, LU 6.2, PAD</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Network address of the originator Site</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Network address of the destination Site</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>TCP/IP port number</p>         </td>
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
         <td><p><span id="NDSP012I"></span>012</p>         </td>
         <td><p>NDSP I IND incoming connection indication [net="%1"/comm="%3"/src="%4"/ dest="%5"/udata="%5" %6]</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An incoming network connection request has been intercepted and has been routed to the corresponding local protocol module.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>File transfer protocol module that requested the network connection</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Network subsystem: TCP, DSA, LU 6.2, PAD</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Calling network address</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Called network address</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>TCP/IP port number for the local destination</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Route name of the network description in the network security files</p>         </td>
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
         <td><p><span id="NDSP013I"></span>013</p>         </td>
         <td><p><span style="font-weight: bold;">NDSP I ROUT connection request routed to %1</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A network connection request has been routed to the selected network procedure.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>The network procedure to which the connection is forwarded</p>         </td>
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
         <td><p><span id="NDSP014W"></span>014</p>         </td>
         <td><p><span style="font-weight: bold;">NDSP W REFUSER connection request refused by the user</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A network connection request has been rejected by a user exit.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Verify the related exit.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="NDSP015E"></span>015</p>         </td>
         <td><p><span style="font-weight: bold;">NDSP E BADTP connection request rejected: TP procedure unknown</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An outgoing connection request has been rejected locally by Gateway. The Gateway configuration file is probably incorrect.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Possible causes:</p>
<ul>
<li>Gateway was not correctly started and initialized</li>
<li>The name of the file transfer module referenced in the request does not exist, or is different from that set up in the Gateway configuration file</li>
</ul>
<p>Correct the error. Contact Axway Support if the problem persists.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="NDSP016E"></span>016</p>         </td>
         <td><p><span style="font-weight: bold;">NDSP E BADNET connection request rejected: NET procedure unknown</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An incoming network connection request has been rejected by the monitor. The Gateway configuration file is probably incorrect.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Possible causes:</p>
<ul>
<li>Gateway was not correctly started and initialized</li>
<li>The name of the Gateway network module referenced in the request does not exist, or is different from that set up in the Gateway configuration file</li>
</ul>
<p>Correct the error. Contact Axway Support if the problem persists.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="NDSP017E"></span>017</p>         </td>
         <td><p><span style="font-weight: bold;">NDSP E FAIL connection request rejected: selection invalid</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An incoming network connection request has been rejected by the monitor. The selected protocol module is not reachable.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check that Gateway was correctly started with all processes running.</p>
<p>If the problem persists, contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="NDSP018E"></span>018</span></p>         </td>
         <td><p><span style="font-weight: bold;">NDSP E BADADDR connection request rejected: unknown calling address</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An incoming network connection request has been rejected by the monitor. The Gateway network security files are probably incorrect.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Possible causes:</p>
<ul>
<li>Connection is not allowed</li>
<li>Security files are not correctly set up</li>
</ul>
<p>Modify the security files and make sure that transfer is allowed. If the problem persists, contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="NDSP019E"></span>019</span></p>         </td>
         <td><p><span style="font-weight: bold;">NDSP E BADSITE connection request rejected: unknown physical site %1 name %2</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An incoming network connection request has been rejected by the monitor. The Gateway network security files or database are probably incorrect.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Type of Site name ("alias" or "proto ident")</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Site name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Possible causes:</p>
<ul>
<li>Security files are not correctly set up</li>
<li>Gateway database is not correctly set up</li>
</ul>
<p>Modify the security files and check the Gateway database. If the problem persists, contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="NDSP020E"></span>020</span></p>         </td>
         <td><p><span style="font-weight: bold;">NDSP E SECUSITE %1(%2) security error: returned site doesn't match expected site ["%3"/"%4"]</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An incoming transfer request has been rejected by the monitor. The protocol identifier returned by the remote node does not match the protocol identifier of the Site found in the security file.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Protocol identifier (sent by remote)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Protocol identifier (link to the Site alias name found in local network security file)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Route name (network security file record name)</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Possible causes:</p>
<ul>
<li>Connection is not allowed</li>
<li>Gateway database is not correctly set up</li>
</ul>
<p>Modify the security files or Gateway database. If the problem persists, contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="NDSP021E"></span>021</p>         </td>
         <td><p><span style="font-weight: bold;">NDSP E SECUX25 %1(%2) X25 security error: returned site doesn't match calling address [call ad="%3"/"%4"/"%5"] [wait ad="%6"/"%7"/"%8"]</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An incoming Transfer Request has been rejected by the monitor. When the incoming connection arrives, Gateway finds the related record in the security files. If the flag parameter does not contain the CTRL value, Gateway does not compare the protocol identifier returned by the remote node. However, it checks if there is a record in the network security file that corresponds to that protocol identifier. If it finds one, this message is logged.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name (alias)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Address related to the protocol identifier returned</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>User data related to the protocol identifier returned</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Route name related to the protocol identifier returned</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Address found in the incoming connection</p>         </td>
      </tr>
      <tr>
         <td><p>7</p>         </td>
         <td><p>User data found in the incoming connection</p>         </td>
      </tr>
      <tr>
         <td><p>8</p>         </td>
         <td><p>Route name related to the incoming connection (network security file record name)</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Possible causes:</p>
<ul>
<li>The connection is not allowed</li>
<li>The security files are not correctly set up</li>
<li>The Gateway database is not correctly set up</li>
</ul>
<p>Modify the security files or the Gateway database. Try to find out if that transfer is allowed. Contact Axway Support if some other cause is involved.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="NDSP022E"></span>022</p>         </td>
         <td><p><span style="font-weight: bold;">NDSP E SECUIP %1(%2) IP security error: returned site doesn't match calling address call ad="%3"/"%4"/"%5"] [wait ad="%6"/"%7"/"%8"]</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An incoming transfer request has been rejected by the monitor. When the incoming connection arrives, Gateway finds the related record in the security files. If the flag parameter does not contain CTRL value, Gateway does not compare the protocol identifier returned by the remote node. However, it checks if there is a record in the network security file that corresponds to that protocol identifier. If it finds one, this message is logged.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name (alias)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Connection identifier</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Address related to the protocol identifier returned</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>User data related to the protocol identifier returned</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Route name related to the protocol identifier returned</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Address found in the incoming connection</p>         </td>
      </tr>
      <tr>
         <td><p>7</p>         </td>
         <td><p>User data found in the incoming connection</p>         </td>
      </tr>
      <tr>
         <td><p>8</p>         </td>
         <td><p>Route name related to the incoming connection</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Possible causes:</p>
<ul>
<li>The connection is not allowed</li>
<li>The security files are not correctly set up</li>
<li>The Gateway database is not correctly set up</li>
</ul>
<p>Modify the security files or Gateway database. Try to find out if that transfer is allowed. Contact Axway Support if some other cause is involved.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="NDSP023E"></span>023</span></p>         </td>
         <td><p><span style="font-weight: bold;">NDSP E BADPROTO connection request rejected: physical site name %1 doesn't exist for protocol %2</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The Site found in the network security files contains a file transfer protocol that does not match the configuration found in the Gateway configuration file.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name (alias)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Type of file transfer protocol found in the Gateway configuration file</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Modify the port number (IP) in the Remote Site definition to match those found in the Gateway configuration file.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="NDSP024E"></span>024</span></p>         </td>
         <td><p><span style="font-weight: bold;">NDSP E BADTABLE loading %1 secu file problem: %2 (line %3)</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A syntax error was found while loading a network security file.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Type of network security file (IP )</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Problem identification message</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Line number where the problem was encountered</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Modify the security files to respect the correct syntax.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="NDSP025E"></span>025</p>         </td>
         <td><p><span style="font-weight: bold;">NDSP E REFMON connection request refused by the monitor</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A network connection request has been rejected by the Gateway monitor. This message is logged when a memory problem or a time-out occurs.</p>         </td>
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
         <td><p><span style="font-weight: bold;"><span id="NDSP026I"></span>026</span></p>         </td>
         <td><p><span style="font-weight: bold;">NDSP I REFRESH refresh %1 net secu file by %2: %3 records --&gt; %4 records</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Reload of the network security files was made by using <span class="code" style="font-weight: bold;">pelctl</span> command line to take into account the changes.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Type of network security file (IP)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>User name</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Previous number of records</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>New number of records</p>         </td>
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
         <td><p><span style="font-weight: bold;"><span id="NDSP027I"></span>027</span></p>         </td>
         <td><p><span style="font-weight: bold;">NDSP I LOADTAB loading %1 net secu file: %2 records</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>First load of the network security files when Gateway is starting.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Type of network security file (IP)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Number of records</p>         </td>
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
         <td><p><span id="NDSP028I"></span>028</p>         </td>
         <td><p><span style="font-weight: bold;">NDSP I ROUT connection indication routed to %1</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A network connection indication has been routed to the selected file transfer procedure.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>The file transfer procedure to which the connection is forwarded</p>         </td>
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
         <td><p><span id="NET050I"></span>050</p>         </td>
         <td><p><span style="font-weight: bold;">NET I TLSOK (%1) handshake success, version %2, cipher suite %3, secure renegotiation %4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Indicates that a TLS handshake was achieved. The connection is now secured.</p>
<p>The TLS parameters are negotiated according to the remote connection end requirements and the security profiles defined in SECS.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>TLS protocol version: 3.0 or 3.1</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local cipher suite in use</p>         </td>
      </tr>
      <tr>
         <td>          </td>
         <td><p>4</p>         </td>
         <td>Y or N         </td>
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
         <td><p><span id="NET051I"></span>051</p>         </td>
         <td><p>NET I TLSOKCAC (%1) cache success, cipher suite %2, version %3, secure renegotiation %4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The element was found in the cache.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Cipher suite used</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>TLS protocol version</p>         </td>
      </tr>
      <tr>
         <td>          </td>
         <td><p>4</p>         </td>
         <td>Y or N         </td>
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
         <td><p><span id="NET052I"></span>052</p>         </td>
         <td><p><span style="font-weight: bold;">NET I TLSCLNTF (%1) close notify exchanged</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Indicates that a TLS session closed correctly by exchanging close notify alert messages.</p>
<p>This message is a guarantee that both partners successfully closed the session. This is the last exchanged message, and the connection is closed immediately.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier</p>         </td>
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
         <td><p><span id="NET053W"></span>053</p>         </td>
         <td><p><span style="font-weight: bold;">NET W TLSALSND (%1) alert %2 sent (%3)</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Indicates that a TLS alert was sent.</p>
<p>An alert is sent when an error occurs. All these alerts (except "no renegotiation") are considered fatal and are followed by a disconnection.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Alert code:</p>
<ul>
<li><span style="font-weight: bold;">0:</span> Close notify</li>
<li><span style="font-weight: bold;">10:</span> Unexpected message</li>
<li><span style="font-weight: bold;">20:</span> Bad record mac</li>
<li><span style="font-weight: bold;">21:</span> Decryption failed</li>
<li><span style="font-weight: bold;">22:</span> Record overflow</li>
<li><span style="font-weight: bold;">30:</span> Decompression failure</li>
<li><span style="font-weight: bold;">40:</span> Handshake failure</li>
<li><span style="font-weight: bold;">41:</span> No certificate</li>
<li><span style="font-weight: bold;">42:</span> Bad certificate</li>
<li><span style="font-weight: bold;">43:</span> Unsupported certificate</li>
<li><span style="font-weight: bold;">44:</span> Certificate revoked</li>
<li><span style="font-weight: bold;">45:</span> Certificate expired</li>
<li><span style="font-weight: bold;">46:</span> Certificate unknown</li>
<li><span style="font-weight: bold;">47:</span> Illegal parameter</li>
<li><span style="font-weight: bold;">48:</span> Unknown ca</li>
<li><span style="font-weight: bold;">49:</span> Access denied</li>
<li><span style="font-weight: bold;">50:</span> Decode error</li>
<li><span style="font-weight: bold;">51:</span> Decrypt error</li>
<li><span style="font-weight: bold;">60:</span> Export restriction</li>
<li><span style="font-weight: bold;">70:</span> Protocol version</li>
<li><span style="font-weight: bold;">71:</span> Insufficient security (may occur if no cipher suite matches between client and server)</li>
<li><span style="font-weight: bold;">80:</span> Internal error</li>
<li><span style="font-weight: bold;">90:</span> User canceled</li>
<li><span style="font-weight: bold;">100:</span> No renegotiation</li>
<li><p><span style="font-weight: bold;">110:</span> Unsupported extension</p></li>
<li><span style="font-weight: bold;">111:</span>Certificate unobtainable</li>
<li><span style="font-weight: bold;">112:</span> Unrecognized name</li>
<li><span style="font-weight: bold;">113:</span> Bad certificate status response</li>
<li><span style="font-weight: bold;">114:</span> Bad certificate hash value</li>
<li><span style="font-weight: bold;">115:</span> Unknown psk identity</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Alert label</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the alert code for more information.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="NET054W"></span>054</p>         </td>
         <td><p><span style="font-weight: bold;">NET W TLSALRCV (%1) alert %2 received (%3)</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Indicates that a TLS alert was received.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Alert code (as for message <span style="font-weight: bold;">053</span> above)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Alert label</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the alert code for more information.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="NET055E"></span>055</p>         </td>
         <td><p><span style="font-weight: bold;">NET E TLSERROR (%1) handshake aborted, error %2/%3</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error during handshake.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Error code</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Error sub-code</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>If the error is related to SECS, check the netprof and sprof definitions in the security server.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="NET056E"></span>056</p>         </td>
         <td><p><span style="font-weight: bold;">NET E TLSINIT (%1) handshake can not be initiated, check configuration</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>SECS definitions do not contain a sprof or netprof item suitable for initiating this TLS connection.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>If the error is related to SECS, check the netprof and sprof definitions in the security server.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="NET060I"></span>060</p>         </td>
         <td><p><span style="font-weight: bold;">NET I SSHOK (%1) session success</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>SSH session established.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>NET context number</p>         </td>
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
         <td><p><span id="NET061I"></span>061</p>         </td>
         <td><p><span style="font-weight: bold;">NET I SSHEND (%1) session ended correctly</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Session ended correctly.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>NET context number</p>         </td>
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
         <td><p><span id="NET062E"></span>062</p>         </td>
         <td><p><span style="font-weight: bold;">NET E SSHINIT (%1) session can not be initiated, check configuration</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>SSH Profile error. The parameters defined in the SSH Profile are not compatible with those of the Remote Site.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>NET context number</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check SSH Profile configuration.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="NET063E"></span>063</p>         </td>
         <td><p><span style="font-weight: bold;">NET E SSHERROR (%1) session aborted on error, %2 (error %3/%4)</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>SSH protocol error (internal error).</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>NET context number</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Error code</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Sub-code</p>         </td>
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
         <td><p><span id="NET064E"></span>064</p>         </td>
         <td><p><span style="font-weight: bold;">NET E SSHEND (%1) session ended on error, %2 (error %3)</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>SSH protocol error.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>NET context number</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Error message</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Error code</p>         </td>
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
         <td><p><span id="NET065I"></span>065</p>         </td>
         <td><p>NET I SSHINFO (%1) %2</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>SSH negotiation message.</p>
<p>This message is used at the start of an SSH negotiation to identify the Initiator (remote or host, client or server).</p>
<p>The message is also used at the end of an SSH negotiation to indicate that negotiation was successful (otherwise an error message is generated).</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SSH session number</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message</p>         </td>
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
         <td><p><span id="NET066W"></span>066</p>         </td>
         <td><p>NET W SSHWARN (%1) %2</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Warning message containing disconnection reason code from client authentication phase.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>NET context number</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Message</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Possible causes:</p>
<ul>
<li>Incorrect authentication parameters (for example, username or password)</li>
<li>The connection is not allowed by remote machine</li>
</ul>
<p>Correct the authentication parameters or, in case of connection not permitted, check remote machine configuration and log.</p>         </td>
      </tr>
   </tbody>
</table>

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="NET066W"></span>069</p>         </td>
         <td><strong>NET W SSHWARN (%1) %2 Login deadline expired</strong>         </td>
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
         <td>SSH version string         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td>Connection identifier         </td>
      </tr>
      <tr>
         <td>Possible causes         </td>
         <td><ul>
<li><p>Possible DOS attack</p></li>
<li><p>Network delays</p></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><ul>
<li>Monitor calling addresses for the "login timed out" connections. Check for repeated connection attempts not followed by login attempts.</li>
<li>Check network bandwidth.</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="NET070I"></span>070</p>         </td>
         <td><p><span style="font-weight: bold;">NET I NSRINF %1(%2) %3</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Generic <span class="mc-variable axway_variables.Company_Name variable">Axway</span> <span class="mc-variable suite_variables.SecureRelayName variable">Secure Relay</span> networking information display.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Mode:</p>
<ul>
<li>Transfer phase:
<ul>
<li>Client</li>
<li>Server</li>
</ul></li>
<li>Initialization phase</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>NET context number</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Explanatory text message</p>         </td>
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
         <td><p><span id="NET071W"></span>071</p>         </td>
         <td><p><span style="font-weight: bold;">NET W NSRWRN %1(%2) %3</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Generic <span class="mc-variable axway_variables.Company_Name variable">Axway</span> <span class="mc-variable suite_variables.SecureRelayName variable">Secure Relay</span> networking warning display.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Mode:</p>
<ul>
<li>Transfer phase:
<ul>
<li>Client</li>
<li>Server</li>
</ul></li>
<li>Initialization phase</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>NET context number</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Explanatory text message</p>         </td>
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
         <td><p><span id="NET072E"></span>072</p>         </td>
         <td><p><span style="font-weight: bold;">NET E NSRERR %1(%2) %3</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Generic <span class="mc-variable axway_variables.Company_Name variable">Axway</span> <span class="mc-variable suite_variables.SecureRelayName variable">Secure Relay</span> networking error display.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Mode:</p>
<ul>
<li>Transfer phase:
<ul>
<li>Client</li>
<li>Server</li>
</ul></li>
<li>Initialization phase</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>NET context number</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Explanatory text message</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Analyze the text message to determine action.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="NET073E"></span>073</p>         </td>
         <td><p>NET E NSRXSR %1(%2) %3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>[Message not currently used]</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="NET101I"></span>101</p>         </td>
         <td><p><span style="font-weight: bold;">NET I CONN_REQ (%1) outgoing connection request [src_add="%2",dest_add="%3"]</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The primitive for outgoing connection requests has been called up.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Network source address (calling)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Network destination address (called)</p>         </td>
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
         <td><p><span id="NET102I"></span>102</p>         </td>
         <td><p><span style="font-weight: bold;">NET I CONN_IND (%1) incoming connection indication [src_add="%2", dest_add="%3"]</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The primitive that processes incoming connection requests has been called up.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Network source address (calling)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Network destination address (called)</p>         </td>
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
         <td><p><span id="NET103I"></span>103</p>         </td>
         <td><p><span style="font-weight: bold;">NET I CONN_RESP (%1) incoming connection response [resp_add="%2"]</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The primitive for responding to incoming connection requests has been called up.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Network address of the responder</p>         </td>
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
         <td><p><span id="NET104I"></span>104</p>         </td>
         <td><p>NET I CONN_CONF (%1) outgoing connection confirmation [resp_add="%2"]</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The primitive that processes the confirmation of connection requests has been called up.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Network address of the responder</p>         </td>
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
         <td><p><span id="NET105I"></span>105</p>         </td>
         <td><p><span style="font-weight: bold;">NET I DISC_REQ (%1) disconnection request [reason="%2"]</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The primitive to send a connection disconnection has been called up.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Disconnection reason</p>         </td>
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
         <td><p><span id="NET106I"></span>106</p>         </td>
         <td><p><span style="font-weight: bold;">NET I DISC_IND (%1) disconnection indication [reason="%2"][origin="%3"]</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A disconnect indication has been received and the corresponding primitive called up.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Disconnection reason</p>         </td>
      </tr>
      <tr>
         <td>          </td>
         <td><p>3</p>         </td>
         <td><p>Origin</p>
<ul>
<li>0: not set</li>
<li>1: not used</li>
<li>2: socket error or cannot connect to proxy</li>
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
         <td><p><span id="NET107I"></span>107</p>         </td>
         <td><p><span style="font-weight: bold;">NET I RES_REQ (%1) reset request [reason="%2"]</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A connection reset has been initiated and the corresponding primitive called up.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Reason for the connection reset</p>         </td>
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
         <td><p><span id="NET108I"></span>108</p>         </td>
         <td><p><span style="font-weight: bold;">NET I RES_IND (%1) reset indication [reason="%2"]</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A connection reset has been received.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Reason for the connection reset</p>         </td>
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
         <td><p><span id="NET109I"></span>109</p>         </td>
         <td><p><span style="font-weight: bold;">NET I RES_RESP (%1) reset response</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A connection reset response has been sent and the corresponding primitive called up.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
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
         <td><p><span id="NET110I"></span>110</p>         </td>
         <td><p><span style="font-weight: bold;">NET I RES_CONF (%1) reset confirmation</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The confirmation of the connection reset has been received and the corresponding primitive called up.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
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
         <td><p><span id="NET111S"></span>111</p>         </td>
         <td><p><span style="font-weight: bold;">NET S DATA_REQ (%1) data transmission request [size="%2"]</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Success</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A data transmission primitive has been called up.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Size of the buffer transmitted</p>         </td>
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
         <td><p><span id="NET112S"></span>112</p>         </td>
         <td><p><span style="font-weight: bold;">NET S DATA_IND (%1) incoming data indication [size="%2"]</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Success</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A data reception primitive has been called up.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Buffer size received</p>         </td>
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
         <td><p><span id="NET113S"></span>113</p>         </td>
         <td><p><span style="font-weight: bold;">NET S EXP_REQ (%1) urgent data request [size="%2"]</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Success</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Indicates that urgent data transmission primitive has been called up.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Buffer size transmitted</p>         </td>
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
         <td><p><span id="NET114S"></span>114</p>         </td>
         <td><p><span style="font-weight: bold;">NET S EXP_IND (%1) urgent data indication [size="%2"]</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Success</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Indicates that urgent data reception primitive has been called up.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Buffer size received</p>         </td>
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
         <td><p><span id="NET115I"></span>115</p>         </td>
         <td><p><span style="font-weight: bold;">NET I CONN_ROUTE outgoing connection request routed: host=%1 address=%2</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An outgoing connection request has been routed to a destination address.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Destination host</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Destination address</p>         </td>
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
         <td><p><span id="NET116I"></span>116</p>         </td>
         <td><p><span style="font-weight: bold;">NET I LIST_REQ (%1) listen connection request [dest_add="%2"]</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A dynamic listening connection is asked for FTP data transfer (for list or file data).</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>TCP/IP waiting address without port number</p>         </td>
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
         <td><p><span id="NET117I"></span>117</p>         </td>
         <td><p><span style="font-weight: bold;">NET I LIST_CONF (%1) listen connection confirmation (%4) [dest_address=<span style="font-weight: bold;">"</span></span><span style="font-weight: bold;">%2/%3"]</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A dynamic listening connection is set for FTP data transfer (for list or file data).</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>TCP/IP waiting address without port number</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Listen port number</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Listen connection identifier for data</p>         </td>
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
         <td><p><span id="NET118I"></span>118</p>         </td>
         <td><p><span style="font-weight: bold;">NET I TLS_REQ (%1) TLS handshake request</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The primitive to start the underlying TLS layer is called.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
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
         <td><p><span id="NET119I"></span>119</p>         </td>
         <td><p><span style="font-weight: bold;">NET I TLS_RESP (%1) TLS handshake response</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The primitive for responding to incoming TLS start indication is called.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
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
         <td><p><span id="NET120I"></span>120</p>         </td>
         <td><p><span style="font-weight: bold;">NET I TLS_IND (%1) TLS handshake indication</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A TLS start indication was received and the corresponding primitive called.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
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
         <td><p><span id="NET121I"></span>121</p>         </td>
         <td><p><span style="font-weight: bold;">NET I TLS_CONF (%1) TLS handshake confirmation</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The primitive that processes the confirmation of TLS start request was called.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
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
         <td><p><span id="NET300I"></span>300</p>         </td>
         <td><p><span style="font-weight: bold;">NET I PX_LOAD Proxy %1 successfully loaded</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The requested proxy was found and loaded.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Proxy name</p>         </td>
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
         <td><p><span id="NET301I"></span>301</p>         </td>
         <td><p><span style="font-weight: bold;">NET I PX_CNX (%1) Successfully connected to proxy %2</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The connection to the requested proxy was successful.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Proxy name</p>         </td>
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
         <td><p><span id="NET310E"></span>310</p>         </td>
         <td><p><span style="font-weight: bold;">NET E PX_ERR Could not access proxy %1: error %2</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An error occurred while loading the requested proxy.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Proxy name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Error message</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the NET proxy field in the Remote Site, and the proxy database, according to the error message.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="NET311E"></span>311</p>         </td>
         <td><p><span style="font-weight: bold;">NET E PX_ERR Proxy %1 is not a NET proxy</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The proxy required in the NET proxy field of the Remote Site is not a NET proxy.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Proxy name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the NET proxy field in the Remote Site, and the proxy database. The proxy required in the field may be an FT proxy.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="NET312E"></span>312</p>         </td>
         <td><p><span style="font-weight: bold;">NET E PX_ERR (%1) Protocol error while connecting to proxy %2: %3</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A protocol error occurred while negotiating the connection with the proxy.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier (number)</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Proxy name</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Error message</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the proxy configuration according to the error message.</p>         </td>
      </tr>
   </tbody>
</table>

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
