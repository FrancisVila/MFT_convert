{
    "title": "Using requester mode",
    "linkTitle": "Using requester mode",
    "weight": "390"
}The communication structure is defined by the interface before
the user function is called. You must provide, complete, or modify the
parameters that <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> needs to establish network and protocol connections.

The initialization function and the user function, if needed, are called
when connection requests are made, even for network and protocol connection
attempts (retries) or store and forward operations.

If the partner is:

-   Known to Transfer
    CFT: the communication structure fields indicate the values of the CFTPART
    and CFTTCP corresponding to the partner
-   Not known to Transfer
    CFT: the only fields containing valid data are the general information
    fields and the fields contained in the following table (partner information
    fields)

### Partner information fields

<table>
   <th>
      <tr>
<th><p>Field </p>         </th>
<th><p>Explanation </p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Field </p>         </td>
         <td><p>Explanation </p>         </td>
      </tr>
      <tr>
         <td><p>ptype </p>         </td>
         <td><p>Partner type </p>         </td>
      </tr>
      <tr>
         <td><p>part </p>         </td>
         <td><p>Partner local identifier </p>         </td>
      </tr>
      <tr>
         <td><p>idne </p>         </td>
         <td><p>Network resource identifier </p>         </td>
      </tr>
      <tr>
         <td><p>idprot </p>         </td>
         <td><p>Protocol identifier </p>         </td>
      </tr>
      <tr>
         <td><p>prof </p>         </td>
         <td><p>PeSIT only</p>
<p>Profile</p>         </td>
      </tr>
      <tr>
         <td><p>prot </p>         </td>
         <td><p>Protocol type </p>         </td>
      </tr>
      <tr>
         <td><p>commut </p>         </td>
         <td><p>Store and forward indicator (‘Y’) </p>         </td>
      </tr>
      <tr>
         <td><p>imaxtime </p>         </td>
         <td><p>Maximum incoming call time ("23595999") </p>         </td>
      </tr>
      <tr>
         <td><p>imintime </p>         </td>
         <td><p>Minimum incoming call time ("00000000") </p>         </td>
      </tr>
      <tr>
         <td><p>omaxtime </p>         </td>
         <td><p>Maximum outgoing call time ("23595999") </p>         </td>
      </tr>
      <tr>
         <td><p>omintime </p>         </td>
         <td><p>Minimum outgoing call time ("00000000") </p>         </td>
      </tr>
      <tr>
         <td><p>ntype </p>         </td>
         <td><p>Network type </p>         </td>
      </tr>
      <tr>
         <td><p>imaxt </p>         </td>
         <td><p>Maximum incoming call time on the network resource ("23595999") </p>         </td>
      </tr>
      <tr>
         <td><p>imint </p>         </td>
         <td><p>Minimum incoming call time on the network resource ("00000000") </p>         </td>
      </tr>
      <tr>
         <td><p>omaxt </p>         </td>
         <td><p>Maximum outgoing call time on the network resource ("23595999") </p>         </td>
      </tr>
      <tr>
         <td><p>omint </p>         </td>
         <td><p>Minimum outgoing call time on the network resource ("00000000") </p>         </td>
      </tr>
      <tr>
         <td><p>retryw </p>         </td>
         <td><p>Spacing of connection attempts (7 minutes) </p>         </td>
      </tr>
      <tr>
         <td><p>retryn </p>         </td>
         <td><p>Number of connection attempts spaced by retryw (6) </p>         </td>
      </tr>
      <tr>
         <td><p>retrym </p>         </td>
         <td><p>Maximum number of connection attempts (12) </p>         </td>
      </tr>
      <tr>
         <td><p>cnxin </p>         </td>
         <td><p>Maximum number of simultaneous incoming calls, for the
given network partner (2) </p>         </td>
      </tr>
      <tr>
         <td><p>cnxout </p>         </td>
         <td><p>Maximum number of simultaneous outgoing calls, for the
given network partner (2) </p>         </td>
      </tr>
      <tr>
         <td><p>cnxinout </p>         </td>
         <td><p>Maximum number of simultaneous communications, for the
given network partner (2) </p>         </td>
      </tr>
      <tr>
         <td><p>cMode</p>         </td>
         <td><p>SSL mode Client/Server</p>         </td>
      </tr>
      <tr>
         <td><p>cAuthPolicy</p>         </td>
         <td><p>SSL auth Anonymous/Simple/Double</p>         </td>
      </tr>
      <tr>
         <td><p>bCipher</p>         </td>
         <td><p>SSL cipher suite</p>         </td>
      </tr>
      <tr>
         <td><p>sParm</p>         </td>
         <td><p>SSL command free parameters</p>         </td>
      </tr>
      <tr>
         <td><p>sRemoteUserDn</p>         </td>
         <td><p>Remote User certificate Dn</p>         </td>
      </tr>
      <tr>
         <td><p>sRemoteIssuerDn</p>         </td>
         <td><p>Remote Issuer Dn</p>         </td>
      </tr>
      <tr>
         <td><p>sRemoteCaId</p>         </td>
         <td><p>Remote CA Alias</p>         </td>
      </tr>
      <tr>
         <td><p>sUserCId</p>         </td>
         <td><p>User Certificate Alias</p>         </td>
      </tr>
      <tr>
         <td><p>sCertFname</p>         </td>
         <td><p>File including Remote certificate</p>         </td>
      </tr>
      <tr>
         <td><p>sProf</p>         </td>
         <td><p>SSL profil Id.</p>         </td>
      </tr>
      <tr>
         <td><p>sRemoteSerial</p>         </td>
         <td><p>Serial Number</p>         </td>
      </tr>
      <tr>
         <td><p>ExitFree</p>         </td>
         <td><p>Free Area between all EXITs</p>         </td>
      </tr>
   </tbody>
</table>

 

When <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> does not know the partner, the following fields are
empty:

-   ipart: intermediate
    partner local identifier
-   sap: remote Sap
    (Service Access Point)
-   addr: remote partner
    address

The <span style="font-weight: bold;">ret1</span> return code field must
be defined when the user function is returned from.

If there is a connection refusal (return code value of 2), the ret2
field may be defined to make the cause of the refusal appear in the DIAGI
field of the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> catalog.

The content of the diag field appears with the appropriate error message
if the return code is not 0 and 1.

If the msg field is defined, its content is sent to the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>
standard output.

If the return code value is 0 or 1, you can modify all the fields
except the general information fields or the ptype and ntype fields.

Field descriptions

<table>
   <th>
      <tr>
<th><p>Field </p>         </th>
<th><p>Explanation </p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>part </p>         </td>
         <td><p>If this field:</p>
<ul>
<li>is empty
when the user function is returned from, the partner local identifier
"UNDEFPTN" appears in the catalog and on the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> standard
output.</li>
<li>has been
modified and if the new identifier is located in the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> partner
base, <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> sets the ret1 field to 9 (processing error) and the
diag field to "PTNEXIST"</li>
<li>has been
modified, during any network or protocol connection attempts that may
have been made, the system behaves as if the partner is not known to Transfer
CFT</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>ipart </p>         </td>
         <td><p>If the ipart field is defined, a voluntary store and forward
or backup mechanism<br />
(omintime = omaxtime) is possible.<br />
The user function is called to provide complete information or modify the
intermediate partner information<br />
In the store and forward case, the commutfl field is set to 1.</p>         </td>
      </tr>
      <tr>
         <td><p>idprot, idnet, prot and prof </p>         </td>
         <td><p>The idnet, prot and prof fields are connected to the CFTPROT
command identifier (idprot). If the idprot field is modified, the new
value must correspond to a CFTPROT command ( <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> updates the fields
that are associated with it)<br />
If not, <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> sets the ret1 field to 9 (processing error) and the
diag field to "NOPROT".<br />
 </p>
<p>The protl field indicates the list of <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> parameter
setting protocols. </p>         </td>
      </tr>
      <tr>
         <td><p>nspart, nspassw, sap and addr </p>         </td>
         <td><p>If the nspart (and nspassw as applicable), sap and addr
fields are not defined when the user function is returned from, the network
and protocol connections will not be able to be established<br />
<br />
The maximum length taken into account for the remote partner address depends
on the network type.</p>
<table>
   <th>
      <tr>
<th><p>Network type</p>         </th>
<th><p>Length</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>TCP</p>         </td>
         <td><p>64</p>         </td>
      </tr>
   </tbody>
</table>
<p> </p>         </td>
      </tr>
      <tr>
         <td><p>nrpart </p>         </td>
         <td><p>If the field nrpart is empty when the user function is
returned from, it is set to the value of the part field.</p>
<p>A network partner is identified by a network name (nrpart).</p>
<p>If the user establishes simultaneous connections with several
network partners using the same name, the values of the counters below
will be the sum of these connections and will be the same for each partner:</p>
<ul>
<li>curreqc:
current number of transfers in requester
mode, for the given network partner</li>
<li>cursrvc: current
number of transfers in server mode,
for the given network<br />
partner</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>maxrty<br />
and currty </p>         </td>
         <td><p>During network connection attempts, the currty value may
be used to assign a new address to the remote partner<br />
This counter is reset to zero each time the remote partner address is changed.</p>
<p>If the currty value reaches the maxrty value, Transfer
CFT attempts to go on to the next backup address.<br />
If there are no further backup addresses, <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> attempts to go on
to the next backup protocol. If there are no further backup protocols,
<span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> attempts to perform a backup store and forward</p>
<p>With the directory type EXIT task in requester mode, and
one and only one protocol and a single address associated with a partner,
<span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> attempts the backup store and forward. If the intermediate
partner does not exist, the transfer changes to the K state.</p>         </td>
      </tr>
      <tr>
         <td><p>maxrtyp and currtyp </p>         </td>
         <td><p>During protocol connection attempts, the currtyp value
may be used to assign a new protocol to the remote partner<br />
The counter is reset to zero each time the protocol is changed</p>
<p>If the currtyp value reaches the maxrtp value, Transfer
CFT attempts to go on to the next backup protocol<br />
If there are no further backup protocol, the transfer changes to the K
state</p>
<p>With the directory type EXIT in requester mode, and a single
protocol associated with the partner, the transfer changes to the K state </p>         </td>
      </tr>
   </tbody>
</table>

During network and protocol connection attempts, the fields that can
be modified and whose values are kept relative to the last call of the
user function are:

-   part: partner local
    identifier
-   idprot: protocol
    identifier
-   nrpart: remote
    partner name

Users can query an electronic directory (X500, DNS, ...) or their own
bases to locate their information (network name, password, remote sap,
remote partner address, and so on).
