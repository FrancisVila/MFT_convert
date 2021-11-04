{
    "title": "SECS messages",
    "linkTitle": "SECS",
    "weight": "430"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Messages and codes

This topic lists Security server log messages.

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS010E"></span>010</p>         </td>
         <td><p><span style="font-weight: bold;">SECS E SES_INIT (%1) No Netprof matching [src_addr=%2] [dst_addr=%3]</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error while trying to retrieve Network Profile object from network parameters (incoming connection).</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Source address</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Destination address</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the Network Profile database configuration and make sure that there is one existing record that matches these network parameters.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS011I"></span>011</p>         </td>
         <td><p><span style="font-weight: bold;">SECS I SES_INIT (%1) Netprof : %2 selected [src_addr=%3] [dst_addr=%4]</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information indicating the Network Profile selected for the current connection (incoming connection).</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Netprof object name</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Source address</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
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
         <td><p><span id="SECS012E"></span>012</p>         </td>
         <td><p><span style="font-weight: bold;">SECS E SES_INIT (%1) %2 Security Profile Error : %3 not found</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error while trying to retrieve the Security Profile for the current connection.</p>
<p>The name of the profile is taken from the Site for outgoing connections or from the Network Profile object found for incoming connections.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Server or client mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Security profile name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check if the referenced Security Profile exists in the Security Profile database.</p>
<p>If it does not exist, create it or modify the Site or the Network Profile object attributes.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS013I"></span>013</p>         </td>
         <td><p><span style="font-weight: bold;">SECS I SES_INIT (%1) %2 Security Profile : %3 selected</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information indicating the Security Profile name selected for the current connection.</p>
<p>The name of the profile is taken from the Site for outgoing connections or from the Network Profile object found for incoming connections.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Server or client mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Security profile name</p>         </td>
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
         <td><p><span style="font-weight: bold;"><span id="SECS014I"></span>014</span></p>         </td>
         <td><p><span style="font-weight: bold;">SECS I CA_BUILD (%1) %2 Sending Accepted DN : %3</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p><span style="font-style: italic;">Server mode only</span></p>
<p>Information indicating the local name of the certification trusted authority subject name sent to the client.</p>
<p>Typically, several messages are sent consecutively, since more than one authority is accepted.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Server or client mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Security profile name</p>         </td>
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
         <td><p><span id="SECS015E"></span>015</p>         </td>
         <td><p><span style="font-weight: bold;">SECS E CA_BUILD (%1) %2 Accepted DN : %3 not found</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Server mode only</p>
<p>Error while trying to retrieve the certificate referenced by its name in the accepted authorities field of the current profile.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Server or client mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Certificate name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check that the desired authority is correctly referenced in the current profile, or that the certificate is still present in the local database.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="SECS016I"></span>016</span></p>         </td>
         <td><p><span style="font-weight: bold;">SECS I CA_BUILD (%1) %2 Sending Accepted DN : %3</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Server mode only</p>
<p>Information indicating the distinguished name of the certification trusted authority subject name sent to the client.</p>
<p>Typically, several messages are sent consecutively, since more than one authority is accepted.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Server or client mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Trusted authority distinguished name</p>         </td>
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
         <td><p><span id="SECS017E"></span>017</p>         </td>
         <td><p><span style="font-weight: bold;">SECS E CA_BUILD (%1) %2 Accepted DN : %3 not found</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Server mode only</p>
<p>Error while trying to retrieve the certificate referenced by its name in the accepted authorities field of the current profile.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Server or client mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Distinguished name of the trusted authority</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check that the desired authority is correctly referenced in the current profile, or that the certificate is still present in the local database.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="SECS018I"></span>018</span></p>         </td>
         <td><p><span style="font-weight: bold;">SECS I CA_RECV (%1) %2 Dn received : %3 found in base</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Client mode only</p>
<p>Information indicating the local name of the certification trusted authority subject name received from the server. This Distinguished Name corresponds to a certificate present in the local database.</p>
<p>Typically, several messages are sent consecutively, since more than one authority is received.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Server or client mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Distinguished Name of the trusted authority</p>         </td>
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
         <td><p><span style="font-weight: bold;"><span id="SECS019E"></span>019</span></p>         </td>
         <td><p><span style="font-weight: bold;">SECS E CA_RECV (%1) %2 Dn received : %3 not found in base</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Client mode only</p>
<p>Information indicating that no certificate corresponding to the trusted authority distinguished name received from the server was found in the local database. Therefore, it is impossible to send a certificate that matches such an authority.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Server or client mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Distinguished name of the trusted authority</p>         </td>
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
         <td><p><span style="font-weight: bold;"><span id="SECS020I"></span>020</span></p>         </td>
         <td><p><span style="font-weight: bold;">SECS I CA_RECV (%1) %2 Dn received : %3 found in base</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Client mode only</p>
<p>Information indicating the distinguished name of the certification trusted authority subject name received from the server. This distinguished name corresponds to a certificate present in the local database.</p>
<p>Typically, several messages are sent consecutively, since more than one authority is received.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Server or client mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Distinguished name of the trusted authority</p>         </td>
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
         <td><p><span style="font-weight: bold;"><span id="SECS030I"></span>030</span></p>         </td>
         <td><p><span style="font-weight: bold;">SECS I C_BUILD (%1) %2 Certificate sent: %3</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information indicating the local name of one of the certification path elements sent to the remote partner.</p>
<p>Typically, several messages are sent consecutively, since the certification path sent contains more than one element.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Server or client mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local name of the sent certificate</p>         </td>
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
         <td><p><span style="font-weight: bold;"><span id="SECS031E"></span>031</span></p>         </td>
         <td><p><span style="font-weight: bold;">SECS E C_BUILD (%1) %2 Certificate : %3 not found</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error while trying to send the corresponding certificate.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Server or client mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local name of the certificate to send</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check that the certificate is present in the local database, or change the current Security Profile attributes.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="SECS032I"></span>032</span></p>         </td>
         <td><p><span style="font-weight: bold;">SECS I C_BUILD (%1) %2 Certificate sent: %3</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information indicating the distinguished name of one of the certification path elements sent to the remote partner.</p>
<p>Typically, several messages are sent consecutively since the certification path sent contains more than one element.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Server or client mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local name of the sent certificate</p>         </td>
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
         <td><p><span id="SECS033E"></span>033</p>         </td>
         <td><p><span style="font-weight: bold;">SECS E C_BUILD (%1) %2 Certificate : %3 not found</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error while trying to send the corresponding certificate.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Server or client mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local name of the certificate to send</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check that the certificate is present in the local database, or change the current Security Profile attributes.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS034E"></span>034</p>         </td>
         <td><p><span style="font-weight: bold;">SECS E C_BUILD (%1) %2 Certificate Sending Error [reason= %3] :%4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error while trying to send the corresponding certificate.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Server or client mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Reason for the error, one of:</p>
<ul>
<li>User certificate key error: no private key is associated with user certificate</li>
<li>Certificate not found</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Local name of the certificate to send</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check for the reason code and modify the Security Profile settings if required.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS035E"></span>035</p>         </td>
         <td><p>SECS E SES_INIT (%1) %3 TLS Security Profile %2 has no XPP entity name, check configuration</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>PassPort PS entity name missing from TLS Security Profile.</p>
<p>This message can only occur if the PassPort connector is activated in the configuration menu.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>TLS Security profile identity</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Client or server</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check TLS Security Profile configuration.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS036E"></span>036</p>         </td>
         <td><p>SECS E SES_INIT (%1) %3 TLS Security Profile %2 has no XPP entity password, check configuration</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>PassPort PS entity password missing from TLS Security Profile.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>TLS Security profile identity</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Client or server</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check TLS Security Profile configuration.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS040I"></span>040</p>         </td>
         <td><p><span style="font-weight: bold;">SECS I C_RECV (%1) %2 Certificate : %3 received</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information indicating the local name of one of the certification path elements received from the remote partner.</p>
<p>Typically, several messages are sent consecutively since the certification path sent contains more than one element.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Server or client mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local name of the sent certificate</p>         </td>
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
         <td><p><span id="SECS041E"></span>041</p>         </td>
         <td><p><span style="font-weight: bold;">SECS E C_RECV (%1) %2 Certificate check error [reason=%3] : %4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information indicating that an error occurred while verifying the certification path received from the remote partner.</p>
<p>This indicates that the remote partner authentication has failed.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Server or client mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Reason code, one of:</p>
<ul>
<li><span style="font-style: italic;">Decoding error</span>: unable to decode the certificate content</li>
<li><span style="font-style: italic;">Template matching</span>: no template matching this certificate was found in the current profile</li>
<li><span style="font-style: italic;">Validity error</span>: the certificate validity is not correct (too early or too late)</li>
<li><span style="font-style: italic;">Signature error</span>: the certificate signature is not correct</li>
<li><span style="font-style: italic;">Root not found</span>: the root authority certificate was not sent within the certification path and was not found in the local database</li>
<li><span style="font-style: italic;">Invalid Root</span>: the certification path does not lead to a trusted authority</li>
<li><span style="font-style: italic;">Key usage not granted</span>: the certificate does not authorize the user to carry out this action</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Distinguished name of the received certificate</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the reason code for more information.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS042I"></span>042</p>         </td>
         <td><p>SECS I C_RECV (%1) %2 Certification Path Received Correct</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The correct Certification Path has been received.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Server or client mode</p>         </td>
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
         <td><p><span id="SECS043E"></span>043</p>         </td>
         <td><p><span style="font-weight: bold;">SECS E SECS (%1) %2 RSA computation error [operation=%3]</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Information indicating that an error occurred during the RSA encryption computation.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Server or client mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Name of failed operation</p>         </td>
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
         <td><p><span style="font-weight: bold;"><span id="SECS050E"></span>050</span></p>         </td>
         <td><p><span style="font-weight: bold;">SECS E SP_IN_CHK (%1) %2 Security Profile Check Error: %3 not found</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Server mode only</p>
<p>Error while checking Site input Security Profile.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Server or client mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Security profile name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>In the Security Profile object, verify the Remote Site/NET security tab settings for the incoming connection</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS051E"></span>051</p>         </td>
         <td><p>SECS E SP_IN_CHK (%1) %2 Security Profile %3 Check Error: parameter %4 doesn't match [reason=%5]</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Server mode only</p>
<p>A security parameter of the established connection does not match the input Site Security Profile.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Server or client mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Security profile name</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Parameter name or value</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Error code:</p>
<ul>
<li><span style="font-weight: bold;">10</span>: Incompatible type between the Site Security Profile type and the actual mode</li>
<li><span style="font-weight: bold;">11</span>: Client authentication is mandatory in the Security Profile for the Site, but the client failed to identify itself during the handshake phase</li>
<li><span style="font-weight: bold;">12</span>: Client authentication is imposed as anonymous in the Security Profile for the Site but the client identified itself during the handshake phase</li>
<li><span style="font-weight: bold;">13</span>: Server authentication is mandatory in the Security Profile for the Site but the server did not identify itself during the handshake phase</li>
<li><span style="font-weight: bold;">14</span>: Server authentication imposed as anonymous in the Security Profile for the Site but the server identified itself during the handshake phase</li>
<li><span style="font-weight: bold;">17</span>: The Security Profile for the Site has an incompatible exit scheduling value with the Security Profile used</li>
<li><span style="font-weight: bold;">18</span>: The Security Profile for the Site does not allow the cipher suite used</li>
<li><span style="font-weight: bold;">19</span>: The Security Profile for the Site does not allow the TLS version used</li>
<li><span style="font-weight: bold;">20</span>: Section "UserLocalCertificates" of the Security Profile for the Site does not contain the sent certificate (%4)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the error code for more information.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="SECS052E"></span>052</span></p>         </td>
         <td><p><span style="font-weight: bold;">SECS E SP_IN_CHK (%1) %2 Security Profile %3 Check Error [%4]: DN = %5</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Server mode only</p>
<p>The input Security Profile for the Site does not match the received certification chain.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Server or client mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Security profile name</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Reason code:</p>
<ul>
<li><span style="font-style: italic;">Decoding error</span>: unable to decode the certificate content</li>
<li><span style="font-style: italic;">Template matching</span>: no template matching this certificate was found in the current profile</li>
<li><span style="font-style: italic;">Validity error</span>: the certificate validity is not correct (too early or too late)</li>
<li><span style="font-style: italic;">Signature error</span>: the certificate signature is not correct</li>
<li><span style="font-style: italic;">Root not found</span>: the root authority certificate was not sent within the certification path and was not found in the local database</li>
<li><span style="font-style: italic;">Invalid Root</span>: the certification path does not lead to a trusted authority</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Distinguished Name of the certificate</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the reason code for more information.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS055I"></span>055</p>         </td>
         <td><p>SECS I SP_IN_CHK (%1) %2 Security Profile Check Success: %3 matches %4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Server mode only</p>
<p>The Security Profile for the Site matches the Security Profile already used.</p>
<p>This message only appears if <span class="code" style="font-weight: bold;">secs_log_level</span> is higher than 1 and if the input Security Profile for the Site is different from the one selected during the connection phase.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Server or client mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Security Profile name</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Name of the first Security Profile used</p>         </td>
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
         <td><p><span style="font-weight: bold;"><span id="SECS060E"></span>060</span></p>         </td>
         <td><p>SECS E THC (%1) %2 Unable to decode certificate</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Not possible to decode a certificate.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Server or client mode</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Contact your exchange partner.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="SECS061E"></span>061</span></p>         </td>
         <td><p>SECS E THC (%1) %2 Certificate is not enabled (%3)</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The certificate is not enabled.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Server or client mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Certificate name (alias)</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Enable the certificate.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="SECS062I"></span>062</span></p>         </td>
         <td><p>SECS I THC (%1) %2 Certificate is present and enabled (%3)</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The certificate is present and enabled</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Server or client mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Certificate name (alias)</p>         </td>
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
         <td><p><span id="SECS063E"></span>063</p>         </td>
         <td><p>SECS E THC (%1) %2 Certificate is not present in the base (%3)</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The certificate is not present in the database</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Server or client mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Certificate subject name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>In the Sprof (security profile), activate the option <span style="font-weight: bold;">Automatic import of partner certificates</span>.
See <em>Security Guide &gt; <a href="#">Managing SSH Security profiles</a></em> for further information (requires login).</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS064E"></span>064</p>         </td>
         <td><p>SECS E RCI (%1) %2 Unable to decode certificate</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Gateway cannot decode the certificate.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Server or client mode</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Contact your exchange partner.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS065E"></span>065</p>         </td>
         <td><p>SECS E RCI (%1) %2 Unable to put certificate in the base (%3)</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Gateway cannot write the certificate to the database.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Server or client mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Certificate name (alias)</p>         </td>
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
         <td><p><span id="SECS066I"></span>066</p>         </td>
         <td><p>SECS I RCI (%1) %2 Certificate successfully put in the base (%3)</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Gateway has written the certificate to the database. A newly registered certificate has the name format: Imported_Certificate_xxxxxx.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Server or client mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Certificate name (alias)</p>         </td>
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
         <td><p><span id="SECS067I"></span>067</p>         </td>
         <td><p>SECS I RCI (%1) %2 Certificate already in the base (%3)</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The certificate already exists in the database.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Server or client mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Certificate name (alias)</p>         </td>
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
         <td><p><span id="SECS090E"></span>090</p>         </td>
         <td><p>SECS E SECS (%1) Security Exit Severe Error: [status=%2] [reason=%3]</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A severe security exit error has occurred.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Status</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Reason</p>         </td>
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
         <td><p><span id="SECS099E"></span>099</p>         </td>
         <td><p>SECS E SECS unknown message (%1)</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Non identifiable message</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Connection identifier</p>         </td>
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
         <td><p><span id="SECS100E"></span>100</p>         </td>
         <td><p><span style="font-weight: bold;">SECS E %1(%2) Security exit severe error [status=%3] [reason=%4]</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A serious error has occurred during execution of a security exit.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Server or client mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Corresponding local error (if any)</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Action depends on the reason code and the exit implementation.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS101S"></span>101</p>         </td>
         <td><p><span style="font-weight: bold;">SECS S %1(%2) Session established with site %3, %4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Success</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A session has been established successfully with the named Site.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Server or client mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Name of the SFTP Site you are connected to</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>SSH parameters for the session: key exchange algorithm, public key algorithm, cipher algorithm, Mac algorithm.</p>         </td>
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
         <td><p><span id="SECS102S"></span>102</p>         </td>
         <td><p><span style="font-weight: bold;">SECS S %1(%2) Session established for user %3, %4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Success</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A session has been established successfully with the named user.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Name of the user connected to Gateway</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>SSH parameters for the session: key exchange algorithm, public key algorithm, cipher algorithm, Mac algorithm.</p>         </td>
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
         <td><p><span id="SECS103I"></span>103</p>         </td>
         <td><p><span style="font-weight: bold;">SECS I %1(%2) Session ended with site %3</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The session with the named Site has been ended.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Name of the SFTP Site for which the session is ended.</p>         </td>
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
         <td><p><span id="SECS104I"></span>104</p>         </td>
         <td><p><span style="font-weight: bold;">SECS I %1(%2) Session ended for user %3</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The session with the named user has been ended.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Name of the user for which the session is ended.</p>         </td>
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
         <td><p><span id="SECS105W"></span>105</p>         </td>
         <td><p><span style="font-weight: bold;">SECS W %1(%2) No net profile matching [src_add="%3"] [dest_add="%4"]</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>There is no Network profile matching the incoming connection.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Source address of the incoming connection</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Destination address of the incoming connection</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>To accept connections with these source and destination addresses, you must modify the net profile object accordingly.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS106I"></span>106</p>         </td>
         <td><p><span style="font-weight: bold;">SECS I %1(%2) Net profile %3 selected [src_add="%4"] [dest_add="%5"]</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A Network profile has been selected for the incoming connection.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Name of the Network profile selected</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Source address of the incoming connection</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Destination address of the incoming connection</p>         </td>
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
         <td><p><span id="SECS107W"></span>107</p>         </td>
         <td><p><span style="font-weight: bold;">SECS W %1(%2) Net profile %3 does not supply any security option</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>No security option is associated with the selected Network profile: the Network profile selected has its security option set to NONE.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Name of the net profile selected</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>If an SSH connection is required, set the security option to SSH.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS108E"></span>108</p>         </td>
         <td><p><span style="font-weight: bold;">SECS E %1(%2) SSH profile %3 not found, check configuration</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The Network profile selected is pointing to a SSH profile which does not exist in the database.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Name of the SSH profile referenced in the net profile</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check your configuration.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS109E"></span>109</p>         </td>
         <td><p><span style="font-weight: bold;">SECS E %1(%2) Selected SSH profile %3 is not usable in client mode, check configuration</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The SSH profile selected is of SERVER type and cannot be used to initiate a connection in client mode.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Name of the selected SSH profile</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check your configuration.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS110E"></span>110</p>         </td>
         <td><p><span style="font-weight: bold;">SECS E %1(%2) Selected SSH profile %3 is not usable in server mode, check configuration</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The SSH profile selected is of CLIENT type and cannot be used to initiate a connection in server mode.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Name of the SSH profile selected</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check your configuration.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS111I"></span>111</p>         </td>
         <td><p><span style="font-weight: bold;">SECS I %1(%2) SSH profile %3 selected</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The named SSH profile has been selected to initiate a new connection.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Name of the SSH profile selected</p>         </td>
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
         <td><p><span id="SECS112E"></span>112</p>         </td>
         <td><p><span style="font-weight: bold;">SECS E %1(%2) Signature request with an invalid algorithm identifier (%3)</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The algorithm identifier is displayed as a string if it is recognized (for example ssh-dss),<br />
otherwise it is in the form "(id) unknown" (for example "17 (unknown)").</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Requested algorithm identifier</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>This message is attached to a safety test and should not normally occur. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS113E"></span>113</p>         </td>
         <td><p><span style="font-weight: bold;">SECS E %1(%2) Signature verification request with an invalid algorithm identifier (%3)</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The algorithm identifier is displayed as a string if it is recognized (for example ssh-dss), otherwise it is in the form "(id) unknown" (for example "17 (unknown)").</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Requested algorithm identifier</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>This message is attached to a safety test and should not normally occur. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS114I"></span>114</p>         </td>
         <td><p><span style="font-weight: bold;">SECS I %1(%2) DSS signature achieved with private key %3</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A DSS signature is achieved with the named private key.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Name of the DSS private key</p>         </td>
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
         <td><p><span id="SECS115I"></span>115</p>         </td>
         <td><p><span style="font-weight: bold;">SECS I %1(%2) RSA signature achieved with private key %3</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A RSA signature is achieved with the named private key.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Name of the RSA private key</p>         </td>
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
         <td><p><span id="SECS116E"></span>116</p>         </td>
         <td><p><span style="font-weight: bold;">SECS E %1(%2) DSS signature failure with private key %3</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>DSS signature has failed with the named private key</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Name of the DSS private key</p>         </td>
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
         <td><p><span id="SECS117E"></span>117</p>         </td>
         <td><p><span style="font-weight: bold;">SECS E %1(%2) RSA signature failure with private key %3</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>RSA signature has failed with the named private key</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Name of the RSA private key</p>         </td>
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
         <td><p><span id="SECS118I"></span>118</p>         </td>
         <td><p><span style="font-weight: bold;">SECS I %1(%2) DSS signature verification achieved with public key %3</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The DSS signature verification was successful with the named public key.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Name of the DSS public key</p>         </td>
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
         <td><p><span id="SECS119I"></span>119</p>         </td>
         <td><p><span style="font-weight: bold;">SECS I %1(%2) RSA signature verification achieved with public key %3</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The RSA signature verification was successful with the named public key.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Name of the RSA public key</p>         </td>
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
         <td><p><span id="SECS120E"></span>120</p>         </td>
         <td><p><span style="font-weight: bold;">SECS E %1(%2) DSS signature verification failure with public key %3</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>This error occurs when the partner Mac hash obtained by signature verification is not the same as the Mac hash expected.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-style: italic;">Result</span></p>         </td>
         <td><p>The connection is closed immediately.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Name of the DSS public key</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Your partner is probably using a corrupted key or is does not hold the private key corresponding to the public key supplied. Contact your partner and compare the keys.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS121E"></span>121</p>         </td>
         <td><p><span style="font-weight: bold;">SECS E %1(%2) RSA signature verification failure with public key %3</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>This error occurs when the partner Mac hash obtained by signature verification is not the same as the Mac hash expected.</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-style: italic;">Result</span></p>         </td>
         <td><p>The connection is closed immediately.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Name of the RSA public key</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Your partner is probably using a corrupted key or is does not hold the private key corresponding to the public key supplied. Contact your partner and compare the keys.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS122E"></span>122</p>         </td>
         <td><p><span style="font-weight: bold;">SECS E %1(%2) Public parameters request with an algorithm identifier (%3) that is not set in the SSH profile (algorithm identifier (%3) is not set...)</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Algorithm identifier not set in SSH Profile</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Name of the algorithm identifier</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>This message is attached to a safety test and should not occur.<br />
Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS123E"></span>123</p>         </td>
         <td><p><span style="font-weight: bold;">SECS E %1(%2) Public parameters supplied with an algorithm identifier (%3) that is not set in the SSH profile</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Algorithm identifier not set in SSH Profile</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Name of the algorithm identifier</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>This message is attached to a safety test and should not occur.<br />
Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS124E"></span>124</p>         </td>
         <td><p><span style="font-weight: bold;">SECS E %1(%2) No private key alias is defined in the site or the SSH profile</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The name of the private key to use in the SSH connection is not supplied in the SFTP Site or the SSH profile configuration.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>On the client side the private key name may be omitted if your configuration specifies PASSWORD authentication only.<br />
Check your configuration.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS125E"></span>125</p>         </td>
         <td><p><span style="font-weight: bold;">SECS E %1(%2) No private key alias defined in the SSH profile</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The SSH profile configuration does not supply the name of the private key to be used in SSH connection setup.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>On the server side a private key name is mandatory in the SSH profile definition.<br />
Check your configuration.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS126E"></span>126</p>         </td>
         <td><p><span style="font-weight: bold;">SECS E %1(%2) Private key %3 not found, check configuration</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The SFTP Site or the SSH profile refers to a private key that does not exist in the database.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Name of the private key</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check your configuration.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS127E"></span>127</p>         </td>
         <td><p><span style="font-weight: bold;">SECS E %1(%2) Selected private key %3 has an algorithm identifier (%4) that is not compatible with the one requested (*moved) (%5), check configuration</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The private key selected has an algorithm identifier that does not match the negotiated algorithm identifier. The negotiated algorithm identifier is specified in the public key algorithm list of the SSH profile used.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Name of the private key</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Algorithm identifier of the private key</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Algorithm identifier requested by SSH</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check your configuration.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS128E"></span>128</p>         </td>
         <td><p><span style="font-weight: bold;">SECS E %1(%2) User %3 login refused (password method), [reason %4]</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A user attempting to login using the password method was rejected by Gateway.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>User name</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Reason for login refusal</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>The user is probably unknown or has supplied an invalid password. If this user should have access permission check your configuration.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS129E"></span>129</p>         </td>
         <td><p><span style="font-weight: bold;">SECS E %1(%2) User %3 login refused (public key method), [reason %4]</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A user attempting to login using public key method was rejected by Gateway</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>User name</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Reason for login refusal</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>The user is probably unknown. If this user should have access permission check your configuration.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS130E"></span>130</p>         </td>
         <td><p><span style="font-weight: bold;">SECS E %1(%2) Authentication control failed for site %3</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A SSH connection attempt with a partner server was unsuccessful. This is a general error message, which will be preceded in the log by a more specialized one.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Site name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check your configuration and contact your partner.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS131E"></span>131</p>         </td>
         <td><p><span style="font-weight: bold;">SECS E %1(%2) Authentication control failed for user %3</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A SSH connection attempt from a user partner was unsuccessful. This is general error message, which will be preceded in the log by a more specialized one.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>User name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check your configuration and contact your partner.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS132E"></span>132</p>         </td>
         <td><p><span style="font-weight: bold;">SECS E %1(%2) Authentication control failed for user %3</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A SSH connection attempt from a user partner was unsuccessful. This is general error message that may be related to implementation.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>User name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check your configuration and contact Axway Support if necessary.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS133E"></span>133</p>         </td>
         <td><p><span style="font-weight: bold;">SECS E %1(%2) Authentication control failed for user %3</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A SSH connection attempt from a user partner was unsuccessful.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>User name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>This is general error message that may be related to implementation. Check your configuration and contact Axway Support if necessary.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS134W"></span>134</p>         </td>
         <td><p><span style="font-weight: bold;">SECS W %1(%2) Key %3 (group %4) imported from site %5, waiting for validation</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A key has been imported from a server Site and has the state TO_CHECK.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Key name generated by Gateway</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Key group name</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Site that submitted the key</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the key fingerprint with your partner. You may then change its name, enable or disable it, change its group or comments, etc.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS135W"></span>135</p>         </td>
         <td><p><span style="font-weight: bold;">SECS W %1(%2) Key %3 (group %4) imported from user %5, waiting for validation</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A key has been imported from a client Site and has the state TO_CHECK.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Key name generated by Gateway</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Key group name</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>User that submitted the key</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the key fingerprint with your partner. You may then change its name, enable or disable it, change its group or comments, and so on.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS136W"></span>136</p>         </td>
         <td><p><span style="font-weight: bold;">SECS W %1(%2) Key import cancelled, key received from site %3, already exists as %4 (group %5) in state %6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A key has been submitted from a server Site and Gateway aborted the import operation because the key already exists in the product database.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Site that submitted the key</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Existing key name</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Existing key group</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Existing key state</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>The key may have not been validated yet or disabled for some reason. Check the existing key.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS137W"></span>137</p>         </td>
         <td><p><span style="font-weight: bold;">SECS W %1(%2) Key import cancelled, key received from site %3, already exist as %4 (group %5) in state %6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A key has been submitted from a client Site and Gateway aborted the import operation because the key already exists in the product database.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>User that submitted the key</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Existing key name</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Existing key group</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Existing key state</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>The key may have not been validated yet or disabled for some reason. Check the existing key or contact your partner.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS138E"></span>138</p>         </td>
         <td><p><span style="font-weight: bold;">SECS E %1(%2) Key access error</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>This is an internal error. Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS139W"></span>139</p>         </td>
         <td><p><span style="font-weight: bold;">SECS W %1(%2) Public keys (%3 and %4) with the same fingerprint were found, these keys may be duplicated</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Your database contains two public keys with the same fingerprint. This means the same key has been imported twice with two different names.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>First public key</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Second public key</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Delete one of the keys. This message can appear if the <span style="font-weight: bold;">trustHostedPublicKeys </span> option is used. (See the <em>Security guide &gt; <a href="#">SSH authentication</a></em> for further information).</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS140E"></span>140</p>         </td>
         <td><p><span style="font-weight: bold;">SECS E %1(%2) Specified public key (%3) and received key fingerprint do not match</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The key received from the partner does not match the public key specified for authentication control in the Site or the SSH profile.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Public key name specified for authentication control</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>The connection has been aborted. Check the key fingerprint with your partner.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS141E"></span>141</p>         </td>
         <td><p><span style="font-weight: bold;">SECS E %1(%2) Specified public key (%3) is not enabled</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The public key specified for authentication control in the Site or the SSH profile is not in the ENABLED state.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Public key name specified for authentication control</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>The key may have been intentionally disabled temporarily. Check your configuration.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS142E"></span>142</p>         </td>
         <td><p><span style="font-weight: bold;">SECS E %1(%2) Specified public key (%3) not found, check configuration</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The public key specified for authentication control in the Site or the SSH profile cannot be found.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Public key name specified for authentication control</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check your configuration.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS143E"></span>143</p>         </td>
         <td><p><span style="font-weight: bold;">SECS E %1(%2) Public key name (%3) specified in the site invalidates the key name in the SSH profile (%4), check configuration</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>There is a conflict between the public key name specified in the Site and the public key name specified in the SSH profile.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Public key name in the Site</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Public key name in the SSH profile</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check your configuration.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS144E"></span>144</p>         </td>
         <td><p><span style="font-weight: bold;">SECS E %1(%2) Received public key matches a hosted key (%3) in an other group (%4)</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A hosted key matches the key received from the partner but the authentication control has a public key group different from the received key group. This message can only appear if the <span style="font-weight: bold;">trustHostedPublicKeys </span> option is used.</p>
<p>(See the <em>Security guide &gt; <a href="#">SSH authentication</a></em> for further information).</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Matching hosted public key</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Group of hosted public key</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check your configuration. Compare the key group in the message and the "public_key_group" parameter in the authentication control structure.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS145E"></span>145</p>         </td>
         <td><p><span style="font-weight: bold;">SECS E %1(%2) Received public key matches a hosted key (%3) that is not enabled</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A hosted key matches the key received from the partner but is not ENABLED. This message can only appear if the <span style="font-weight: bold;">trustHostedPublicKeys </span> option is used. The connection is aborted.</p>
<p>(See the <em>Security guide &gt; <a href="#">SSH authentication</a></em> for further information).</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Matching hosted public key</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the key with your partner, and modify its state if necessary.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS146E"></span>146</p>         </td>
         <td><p><span style="font-weight: bold;">SECS E %1(%2) Public key received from site %3 does not match a hosted key</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The server Site has submitted a key that does not match any public key in the database. The connection has been aborted. The key may have been imported according to Gateway configuration.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Site name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>This message can appear if the <span style="font-weight: bold;">trustHostedPublicKeys </span> option is used.</p>
<p>(See the <em>Security guide &gt; <a href="#">SSH authentication</a></em> for further information).</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS147E"></span>147</p>         </td>
         <td><p><span style="font-weight: bold;">SECS E %1(%2) Public key received from user %3 rejected</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The client has submitted a key that does not match any public key in the database. The connection has been aborted. The key may have been imported according to the configuration.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>User name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>This message can appear if the <span style="font-weight: bold;">trustHostedPublicKeys </span> option is used.</p>
<p>(See the <em>Security guide &gt; <a href="#">SSH authentication</a></em> for further information).</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS148E"></span>148</p>         </td>
         <td><p><span style="font-weight: bold;">SECS E %1(%2) Public key received from site %3 rejected</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The server Site submitted a key that does not match any public key in the database. The connection has been aborted. The key may have been imported according to the configuration.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Site name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>This message can appear if the <span style="font-weight: bold;">trustHostedPublicKeys </span> option is not used.</p>
<p>(See the <em>Security guide &gt; <a href="#">SSH authentication</a></em> for further information).</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS149E"></span>149</p>         </td>
         <td><p><span style="font-weight: bold;">SECS E %1(%2) Public key received from user %3 does not match a hosted key</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The client Site submitted a key that does not match any public key in the database. The connection has been aborted. The key may have been imported according to the configuration.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>User name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>This message can appear if the <span style="font-weight: bold;">trustHostedPublicKeys </span> option is not used.</p>
<p>(See the <em>Security guide &gt; <a href="#">SSH authentication</a></em> for further information).</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS150E"></span>150</p>         </td>
         <td><p><span style="font-weight: bold;">SECS E %1(%2) RSA signature verification gets a different hash length</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>This error occurs when the partner Mac hash obtained by the signature verification does not have the same length as the Mac hash expected.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Contact your partner and compare the keys.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS151E"></span>151</p>         </td>
         <td><p><span style="font-weight: bold;">SECS E %1(%2) RSA signature verification gets a different hash value</span> </p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>This error occurs when the partner Mac hash obtained by signature verification is not the same as the Mac hash expected. The obvious reason for this is that your partner is using a corrupted key or does not own the private key corresponding to the public key supplied.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>The connection is closed immediately. Contact your partner and compare the keys.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS152E"></span>152</p>         </td>
         <td><p><span style="font-weight: bold;">SECS E KEY_ERR %1(%2) DH public key generation failure, session aborted</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Internal error occurred.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
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
         <td><p><span id="SECS153E"></span>153</p>         </td>
         <td><p>SECS E CRT_ERR %1(%2) No certificate alias defined in the site or the SSH profile</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>No certificate alias has been defined in the Site or in the SSH profile.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Define a certificate alias.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS154E"></span>154</p>         </td>
         <td><p>SECS E CRT_ERR %1(%2) No certificate alias defined in the SSH profile</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>No certificate alias has been defined in the SSH profile.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Define a certificate alias.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS155E"></span>155</p>         </td>
         <td><p>SECS E CRT_ERR %1(%2) Certificate %3 not found, check configuration</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>No certificate alias has been defined in the SSH profile.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Name of certificate</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check configuration for certificate name and location.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS156E"></span>156</p>         </td>
         <td><p>SECS E CRT_ERR %1(%2) Selected certificate %3 has an algorithm identifier (%4) that is not compatible with the requested one (%5), check configuration</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The selected certificate has an algorithm identifier that is not compatible with the requested one.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Name of certificate</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Certificate algorithm identifier</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Required algorithm identifier</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check configuration</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS157E"></span>157</p>         </td>
         <td><p>SECS E CRT_ERR %1(%2) Specified certificate (%3) and received certificate do not match</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The selected certificate has an algorithm identifier that is not compatible with the requested algorithm.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Specified certificate</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Contact your exchange partner.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS158E"></span>158</p>         </td>
         <td><p>SECS E CRT_ERR %1(%2) Specified certificate (%3) is not enabled</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The specified certificate (%3) is not enabled</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Specified certificate</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Enable the certificate or specify an enabled certificate</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS159E"></span>159</p>         </td>
         <td><p>SECS E CRT_ERR %1(%2) Specified certificate (%3) not found, check configuration</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The specified certificate was not found</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Specified certificate</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check configuration for available certificates</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS160E"></span>160</p>         </td>
         <td><p>SECS E CRT_ERR %1(%2) Received certificate matches a hosted certificate (%3) that is not enabled</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The received certificate matches an unenabled hosted certificate</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Unenabled hosted certificate</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Enable the certificate.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS161E"></span>161</p>         </td>
         <td><p>SECS E CRT_ERR %1(%2) Certificate received from site %3 does not match a hosted certificate</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The certificate received from the Site does not match a hosted certificate</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Partner Site</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check your security certificate configuration.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS162E"></span>162</p>         </td>
         <td><p>SECS E CRT_ERR %1(%2) Certificate received from user %3 does not match a hosted certificate</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The certificate received from user does not match a hosted certificate</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Certificate received from user</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check your security certificate configuration.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS163E"></span>163</p>         </td>
         <td><p>SECS E CRT_ERR %1(%2) Certificate received from site %3 rejected</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The certificate received from the site was rejected.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Certificate received from Site</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check your security certificate configuration.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS164E"></span>164</p>         </td>
         <td><p>SECS E CRT_ERR %1(%2) Certificate received from user %3 rejected</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Certificate received from the user was rejected.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Certificate received from user</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check your security certificate configuration</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS165E"></span>165</p>         </td>
         <td><p>SECS E CRT_IMP %1(%2) Certificate access error</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Certificate access error</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check your security certificate configuration.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS166W"></span>166</p>         </td>
         <td><p>SECS W CRT_IMP %1(%2) Certificates (%3 and %4) with the same subject name were found, these certificates may be duplicated</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Certificate access error.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Certificate sharing subject name (duplicate)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Certificate sharing subject name (duplicate)</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check your security certificate configuration.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS167I"></span>167</p>         </td>
         <td><p>SECS I SIGN_OK %1(%2) RSA signature verification achieved with certificate %3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Confirmation of signature verification with specified certificate.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Certificate used for signature verification</p>         </td>
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
         <td><p><span id="SECS168E"></span>168</p>         </td>
         <td><p>SECS E SIGN_ERR %1(%2) RSA signature verification failure with certificate %3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Verification failure with specified certificate.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Certificate used for signature verification</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Contact your exchange partner.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS169W"></span>169</p>         </td>
         <td><p>SECS W CRT_IMP %1(%2) Certificate import cancelled, certificate received from site %3, already exist as %4 in state %5</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Import canceled because certificate already exists.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Name of Site from which certificate was being imported</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Name of existing certificate</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>State of existing certificate</p>         </td>
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
         <td><p><span id="SECS170W"></span>170</p>         </td>
         <td><p>SECS W CRT_IMP %1(%2) Certificate import cancelled, certificate received from user %3, already exists as %4 in state %5</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Import canceled because certificate already exists.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Name of user from which certificate was being imported</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Name of existing certificate</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>State of existing certificate</p>         </td>
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
         <td><p><span id="SECS171W"></span>171</p>         </td>
         <td><p>SECS W CRT_IMP %1(%2) Certificate %3 imported from site %4, waiting for validation</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Imported certificate is waiting for validation.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Name of certificate imported</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Name of Site from which certificate was imported</p>         </td>
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
         <td><p><span id="SECS172W"></span>172</p>         </td>
         <td><p>SECS W CRT_IMP %1(%2) Certificate %3 imported from user %4, waiting for validation</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Imported certificate is waiting for validation.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Name of certificate imported</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Name of user from which certificate was imported</p>         </td>
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
         <td><p><span id="SECS173I"></span>173</p>         </td>
         <td><p>SECS I SIGN_OK %1(%2) RSA signature achieved with certificate %3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Verification of success of signature process.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Name of certificate used for signature</p>         </td>
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
         <td><p><span id="SECS174E"></span>174</p>         </td>
         <td><p>SECS E SIGN_ERR %1(%2) RSA signature failure with certificate %3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Failure of signature process with specified certificate.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Name of certificate used in signature failure</p>         </td>
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
         <td><p><span id="SECS175E"></span>175</p>         </td>
         <td><p>SECS E CRT_ERR %1(%2) Certificate received from site %3 can not be parsed</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Parsing failure of certificate from specified Site.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Name of originating Site of certificate that cannot be parsed</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Contact your exchange partner.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS176E"></span>176</p>         </td>
         <td><p>SECS E CRT_ERR %1(%2) Certificate received from user %3 can not be parsed</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Parsing failure of certificate from specified user.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Name of originating user of certificate that cannot be parsed</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Contact your exchange partner.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS177E"></span>177</p>         </td>
         <td><p>SECS E CRT_ERR %1(%2) Certificate received from site %3 is expired</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Expiration of certificate from the specified Site.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Name of Site from which the expired certificate was received</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Contact your exchange partner.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS178E"></span>178</p>         </td>
         <td><p>SECS E CRT_ERR %1(%2) Certificate received from user %3 is expired</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Expiration of certificate from the specified user.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Name of user from which the expired certificate was received</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Contact your exchange partner.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS179E"></span>179</p>         </td>
         <td><p>SECS E CRT_ERR %1(%2) DER parsing error for certificate %3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>DER parsing error of the specified certificate</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Name of the certificate object of DER parsing error</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Contact your exchange partner.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS180E"></span>180</p>         </td>
         <td><p>SECS E CRT_ERR %1(%2) DER decoding error for certificate %3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>DER coding error of the specified certificate</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Name of the certificate object of DER coding error</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Contact your exchange partner.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS181E"></span>181</p>         </td>
         <td><p>SECS E CRT_ERR %1(%2) Record to DER conversion error for certificate %3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Record to DER conversion error for the specified certificate</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Name of the certificate object of the record to DER conversion error</p>         </td>
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
         <td><p><span id="SECS182E"></span>182</p>         </td>
         <td><p>SECS E CRT_ERR %1(%2) Certificate received from site %3 is self signed</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Certificate received from specified Site is self signed.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Name of the originating Site of the self-signed certificate</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>The certificate is non-trusted. Contact your exchange partner.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS183E"></span>183</p>         </td>
         <td><p>SECS E CRT_ERR %1(%2) Certificate received from user %3 is self signed</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Certificate received from specified user is self signed.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Name (alias) of the originating user of the self-signed certificate</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>The certificate is non-trusted. Contact your exchange partner.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS184E"></span>184</p>         </td>
         <td><p>SECS E CRT_ERR %1(%2) Could not find an issuer certificate with name %3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Issuer certificate with specified name was not found.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Subject name of the unfound issuer certificate</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Contact your exchange partner.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS185E"></span>185</p>         </td>
         <td><p>SECS E CRT_ERR %1(%2) Issuer certificate %3 is not enabled</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Issuer certificate with specified name is not enabled.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Name of the un-enabled issuer certificate</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Enable the certificate.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS186E"></span>186</p>         </td>
         <td><p>SECS E CRT_ERR %1(%2) Issuer certificate %3 is expired</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Issuer certificate with specified name has expired.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Name (alias) of the expired issuer certificate</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Acquire new valid certificate.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS187E"></span>187</p>         </td>
         <td><p>SECS E CRT_ERR %1(%2) Intermediate certificate %3 signature invalid for issuer %4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Signature of intermediate certificate invalid for issuer.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Intermediate certificate name (alias)</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Issuer certificate name (alias)</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Contact your exchange partner.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS188E"></span>188</p>         </td>
         <td><p>SECS E CRT_ERR %1(%2) Certificate received from site %3 has an invalid signature for issuer %4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Signature of certificate from specified Site has invalid signature for specified issuer.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Site that submitted certificate</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Issuer certificate name (alias)</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Contact your exchange partner.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS189E"></span>189</p>         </td>
         <td><p>SECS E CRT_ERR %1(%2) Certificate received from user %3 has an invalid signature for issuer %4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Signature of certificate from specified Site has invalid signature.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>User of certificate with invalid signature</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Issuer certificate name (alias)</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Contact your exchange partner.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS190E"></span>190</p>         </td>
         <td><p>SECS E CRT_ERR %1(%2) Root certificate %3 self signature is invalid</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Self signature of root certificate is not valid.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Name (alias) of root certificate with invalid signature</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Verify the root certificate.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS191E"></span>191</p>         </td>
         <td><p>SECS E CRT_ERR %1(%2) Certificate %3 has an unknown type (%4)</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The last certificate of the validation chain is not a root-type certificate.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Name of certificate with unknown type</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Unknown certificate type</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Verify the certificates in the base.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS192E"></span>192</p>         </td>
         <td><p>SECS E CRT_ERR %1(%2) Certificate received from site %3 is hosted as %4 with same subject name but differs</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The certificate subject name field is correct but other certificate fields do not contain expected information.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Originating Site of certificate</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Name of certificate with same subject name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Contact your exchange partner.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS193E"></span>193</p>         </td>
         <td><p>SECS E CRT_ERR %1(%2) Certificate received from user %3 is hosted as %4 with same subject name but differs</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The certificate subject name field is correct but other certificate fields do not contain expected information</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Originating user of certificate</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Name of certificate with same subject name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Contact your exchange partner.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS194E"></span>194</p>         </td>
         <td><p>SECS E CRT_ERR %1(%2) Specified certificate (%3) has an invalid type (%4), USER type is expected</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Received certificate of another type when expecting USER.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Name of certificate with unexpected type</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Unexpected type</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Verify the certificates in the base.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS195E"></span>195</p>         </td>
         <td><p>SECS E CRT_ERR %1(%2) Specified certificate (%3) has an invalid type (%4), OTHER type is expected</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Received certificate of another type when expecting OTHER type.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Name of certificate with unexpected type</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Unexpected type</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Contact your exchange partner.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS196E"></span>196</p>         </td>
         <td><p>SECS E CRT_ERR %1(%2) Certificate received from user %3 does not match the subject name pattern in ssh profile</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Received certificate from user with mismatched SSH profile subject name.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Originating user of certificate with mismatched subject name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>If this is an error, check your SSH Security Profile.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS197E"></span>197</p>         </td>
         <td><p>SECS E CRT_ERR %1(%2) Certificate received from user %3 does not match the issuer name pattern in ssh profile</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Received certificate from user with mismatched SSH profile issuer name.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Originating user of certificate with mismatched issuer name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>If this is an error, check your SSH Security Profile.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS198E"></span>198</p>         </td>
         <td><p>SECS E CRT_ERR %1(%2) Certificate received from site %3 does not match the subject name pattern in ssh profile</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Received certificate from user with mismatched SSH profile subject name pattern.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Originating user of certificate with mismatched subject name pattern</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>If this is an error, check your SSH Security Profile.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS199E"></span>199</p>         </td>
         <td><p>SECS E CRT_ERR %1(%2) Certificate received from site %3 does not match the issuer name pattern in ssh profile</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Received certificate from user with mismatched SSH profile issuer name pattern.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Originating user of certificate with mismatched issuer name pattern</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>If this is an error, check your SSH Security Profile.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS200E"></span>200</p>         </td>
         <td><p>Certificate received from site %3 is signed by an issuer (%4) different from the expected one</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Received certificate from specified Site is signed by unexpected issuer.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Originating Site of certificate with unexpected issuer signature</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Unexpected issuer</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check your SSH Security Profile.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS201E"></span>201</p>         </td>
         <td><p>SECS E CRT_ERR %1(%2) Certificate received from user %3 is signed by an issuer (%4) different from the expected one</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Received certificate from specified User is signed by unexpected issuer.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Originating user of certificate with unexpected issuer signature</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Unexpected issuer</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check your SSH Security Profile.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS202I"></span>202</p>         </td>
         <td><p>SECS I SIGN_OK %1(%2) RSA signature verification with a certificate issued by %3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>RSA signature verification with a certificate form specified issuer.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Issuer of certificate with RSA signature</p>         </td>
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
         <td><p><span id="SECS203E"></span>203</p>         </td>
         <td><p>SECS E AUTHERR %1(%2) Invalid new password supplied by user %3, password unchanged</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Specified user submitted invalid new password.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>User who supplied invalid new password</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Ask your exchange partner to retry transfer.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS204I"></span>204</p>         </td>
         <td><p>SECS I AUTH_OK %1(%2) Password changed successfully by user %3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Change of password by specified user.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>User who changed password</p>         </td>
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
         <td><p><span id="SECS205E"></span>205</p>         </td>
         <td><p>SECS E SES_INIT %1(%2) Selected SSH profile %3 has no XPP entity name, check configuration</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Missing PassPort PS entity name in SSH profile.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Selected SSH profile</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check SSH profile object configuration.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS206E"></span>206</p>         </td>
         <td><p>SECS E SES_INIT %1(%2) Selected SSH profile %3 has no XPP entity password, check configuration</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Missing PassPort PS password in SSH profile.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Selected SSH profile</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check SSH profile object configuration.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS207E"></span>207</p>         </td>
         <td><p>SECS E CRT_ERR %1(%2) Certificate received from site %3 has insufficient key usage</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Insufficient key usage on received Site certificate.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Site originating message</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Contact your exchange partner</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS208E"></span>208</p>         </td>
         <td><p>SECS E CRT_ERR %1(%2) Certificate received from user %3 has insufficient key usage</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Insufficient key usage on received user certificate.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Certificate alias</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Contact your exchange partner</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS209E"></span>209</p>         </td>
         <td><p>SECS E CRT_ERR %1(%2) Certificate received from site %3 has insufficient extended key usage</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Insufficient extended key usage on received Site certificate.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Site that originated the certificate</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Contact your exchange partner</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS210E"></span>210</p>         </td>
         <td><p>SECS E CRT_ERR %1(%2) Certificate received from user %3 has insufficient extended key usage</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Insufficient extended key usage on received user certificate.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>User who originated the certificate</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Contact your exchange partner.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS211E"></span>211</p>         </td>
         <td><p>SECS E LOGNERR %1(%2) User %3 login refused (password method, public key %5 expected), [reason %4]</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>User login or password refused.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Security Server ID</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>User whose login is refused</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Reason for login refusal</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Expected public key</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Verify the CGate configuration.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS212E"></span>212</p>         </td>
         <td><p>SECS E LOGNERR %1(%2) User %3 login refused (password method, certificate %5 expected), [reason %4]</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>User login refused.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>User whose login is refused</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Reason for login refusal</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Expected certificate</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Verify that the CGate has a certificate listed in the Security tab.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS213E"></span>213</p>         </td>
         <td><p>SECS  E SES_INIT  %1(%2) Specified SSH profile (%3) is not enabled</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The SSH profile specified in the net profile or in the Site is not in the ENABLED state.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>SUP identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Client or server mode</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Name of the SSH profile referenced in the net profile or in the Site</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>The SSH profile may have been intentionally disabled temporarily. Check your configuration.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS300E"></span>300</p>         </td>
         <td><p><span style="font-weight: bold;">SECS E UEX %1</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error occurred on SECS PassPort PS exit.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>PassPort PS generated message</p>         </td>
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
         <td><p><span id="SECS301W"></span>301</p>         </td>
         <td><p><span style="font-weight: bold;">SECS W UEX %1</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error occurred on SECS PassPort PS exit.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>PassPort PS generated message</p>         </td>
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
         <td><p><span id="SECS302I"></span>302</p>         </td>
         <td><p><span style="font-weight: bold;">SECS I UEX %1</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error occurred on SECS PassPort PS exit</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>PassPort PS generated message</p>         </td>
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
         <td><p><span id="SECS303E"></span>303</p>         </td>
         <td><p>SECS E UEX %1</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>SSH error occurred on SECS PassPort PS exit</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>PassPort PS generated message</p>         </td>
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
         <td><p><span id="SECS304W"></span>304</p>         </td>
         <td><p>SECS W UEX %1</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>SSH error occurred on SECS PassPort PS exit</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>PassPort PS generated message</p>         </td>
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
         <td><p><span id="SECS305I"></span>305</p>         </td>
         <td><p>SECS I UEX %1</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>SSH error occurred on SECS PassPort PS exit</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>PassPort PS generated message</p>         </td>
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
         <td><p><span id="SECS310E"></span>310</p>         </td>
         <td><p>SECS E SECT %1</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Generic ASx-related error message</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Message text generated by the Security Server</p>         </td>
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
         <td><p><span id="SECS311W"></span>311</p>         </td>
         <td><p>SECS W SECT %1</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Generic ASx-related warning message</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Message text generated by the Security Server</p>         </td>
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
         <td><p><span id="SECS312I"></span>312</p>         </td>
         <td><p>SECS I SECT %1</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Generic ASx-related information message</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Message text generated by the Security Server</p>         </td>
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
         <td><p><span id="SECS313E"></span>313</p>         </td>
         <td><p>SECS E SECT Certificate alias expected</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Trading partner does not have certificate alias</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Verify the configuration of the Trading Partner.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS314E"></span>314</p>         </td>
         <td><p>SECS E SECT Certificate list build failed</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Certificate list build failed</p>         </td>
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
         <td><p><span id="SECS315E"></span>315</p>         </td>
         <td><p>SECS E SECT User certificate %1 not found</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Received certificate alias does not exist in database.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Name of user certificate</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Verify configuration of Trading Partner.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS316E"></span>316</p>         </td>
         <td><p>SECS E SECT Authority certificate %1 not found</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The specified certificate does not exist in the certificate list</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Name of authority certificate</p>         </td>
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
         <td><p><span id="SECS317E"></span>317</p>         </td>
         <td><p>SECS E SECT Authority certificate error: %2 for subject name %1</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An authority certificate with this name could not be found.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Subject name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Error message</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the certificate database or contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS318E"></span>318</p>         </td>
         <td><p>SECS E SECT Certificate %1 is not enabled</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>SECT certificate not enabled.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Certificate name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Enable the certificate.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS319E"></span>319</p>         </td>
         <td><p>SECS E SECT Certificate list length (%1) exceed maximum length (%3)</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The length of the certificate list exceeds the maximum limit (max = 16 000)</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Certificate list length</p>         </td>
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
         <td><p><span id="SECS320E"></span>320</p>         </td>
         <td><p>SECS E SECT User certificate %1 does not have a private key</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The specified user certificate does not have a private key.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>User certificate</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Verify the certificate.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS321I"></span>321</p>         </td>
         <td><p>SECS I SECT Certificate %1 sent</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The specified certificate has been sent.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Certificate name</p>         </td>
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
         <td><p><span id="SECS322I"></span>322</p>         </td>
         <td><p>SECS I SECT Certificate with subject name %1 sent</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The specified certificate has been sent.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Subject name of sent certificate</p>         </td>
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
         <td><p><span id="SECS323I"></span>323</p>         </td>
         <td><p>SECS I SECT Partner certificate with subject name %1 received</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The partner certificate with the specified subject name has been received.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Subject name of received partner certificate</p>         </td>
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
         <td><p><span id="SECS324E"></span>324</p>         </td>
         <td><p>SECS E SECT Partner certificate list check failed</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Checking of the partner certificate list failed.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Contact your exchange partner.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS325E"></span>325</p>         </td>
         <td><p>SECS E SECT Partner certificate list length is too small (%1)</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The length of the partner certificate list is too short.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Length of the partner certificate list</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Contact your exchange partner.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS326E"></span>326</p>         </td>
         <td><p>SECS E SECT Partner certificate operation error (%1)</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error in partner certificate operation.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Operation where error took place</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Contact your exchange partner.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS327E"></span>327</p>         </td>
         <td><p>SECS E SECT Partner certificate decoding error (subject name %1)</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error in partner certificate decoding.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Certificate subject name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Contact your exchange partner.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS328E"></span>328</p>         </td>
         <td><p>SECS E SECT Partner certificate expired (subject name %1)</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Partner certificate expired.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Certificate subject name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Contact your exchange partner.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS329E"></span>329</p>         </td>
         <td><p>SECS E SECT Partner certificate signature invalid (subject name %1 signed by issuer name %2)</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Invalid partner certificate signature.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Certificate subject name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>User name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Contact your exchange partner.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS330E"></span>330</p>         </td>
         <td><p>SECS E SECT Partner self signed certificate signature invalid (subject name %1)</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Invalid partner self signed certificate signature.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Certificate subject name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Contact your exchange partner.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS331E"></span>331</p>         </td>
         <td><p>SECS E SECT Partner certificate key decoding error</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error in partner certificate key decoding.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Contact your exchange partner.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS332E"></span>332</p>         </td>
         <td><p>SECS E SECT Root certificate not found in product store (subject name %1)</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Root certificate not found in product store.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Certificate subject name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Import the certificate to the product store.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS333E"></span>333</p>         </td>
         <td><p>SECS E SECT RSA computation error (%1)</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>RSA computation error.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Type of operation</p>         </td>
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
         <td><p><span id="SECS334E"></span>334</p>         </td>
         <td><p>SECS E SECT RSA computation aborted (no certificate alias supplied)</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Trading Partner object encryption certificate field is empty.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Verify Trading Partner object configuration.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS335E"></span>335</p>         </td>
         <td><p>SECS E SECT RSA computation aborted, no key for certificate alias %1</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Computation log was expected.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Certificate alias</p>         </td>
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
         <td><p><span id="SECS335E"></span>400</p>         </td>
         <td><strong>SECS E %1 (%2) Received public key provides insufficient security strength in FIPS mode.</strong>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td>FIPS validation error while attempting to import a public key received from the partner (the received key is not FIPS compliant).         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td>Client or server mode         </td>
      </tr>
      <tr>
         <td>          </td>
         <td><strong>2</strong>         </td>
         <td>SUP identifier         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td>Check the partner agreement regarding the key algorithms and lengths. Update the agreement in order to enforce the usage of FIPS compliant keys/certificates.         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="SECS335E"></span>401</p>         </td>
         <td><strong>SECS E %1 (%2) Selected key [name=%3/algo=%4] provides insufficient security in FIPS mode.</strong>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td>FIPS validation error while attempting to use a private key defined in Gateway objects (the key is not FIPS compliant).         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td>Client or server mode         </td>
      </tr>
      <tr>
         <td><strong>2</strong>         </td>
         <td>SUP identifier         </td>
      </tr>
      <tr>
         <td><strong>3</strong>         </td>
         <td>Name of the key         </td>
      </tr>
      <tr>
         <td><strong>4</strong>         </td>
         <td>Algorithm of the key         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td>Check the usage of the FIPS restricted key in the different configuration objects and update the configuration to remove the references to this key.         </td>
      </tr>
   </tbody>
</table>

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
