{
    "title": "About  the communication area",
    "linkTitle": "About the communication area",
    "weight": "320"
}This topic describes the communication area structure. The communication
area contains:

-   [General
    information fields](#General_information_fields)
-   [Return
    codes](#Return_codes___directory_exit)
-   [Partner
    information](#Partner_information___directory_exit)
-   [Partner
    network information](#Partner_network_information___directory_exit)
-   [Information
    per network type](#Partner_network_information___directory_exit) (not supported by all networks)

The next topic describes the communication area structure between the
interface and the user program.

The following tables list all the fields of the communication structure.

<span id="General_information_fields"></span>

### General information fields

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>Field</p>         </td>
         <td><p>Explanation</p>         </td>
      </tr>
      <tr>
         <td><p>version </p>         </td>
         <td><p>Interface
version number</p>
<p>The current version
number is "0130".</p>         </td>
      </tr>
      <tr>
         <td><p>idexit </p>         </td>
         <td><p>EXIT task
identifier</p>         </td>
      </tr>
      <tr>
         <td><p>exname</p>         </td>
         <td><p>User name</p>
<p>The user name is equal to the value of the exaref parameter
of the exaini function.</p>         </td>
      </tr>
      <tr>
         <td><p>parm</p>         </td>
         <td><p>User parameter</p>
<p>The user parameter
is equal to the value of the PARM parameter of the CFTEXIT object.</p>         </td>
      </tr>
      <tr>
         <td><p>exver</p>         </td>
         <td><p>Exit version V24 or higher</p>         </td>
      </tr>
      <tr>
         <td><p>language</p>         </td>
         <td><p>Language
of the user program:</p>
<ul>
<li>C: C
language</li>
<li>O: COBOL</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>etype</p>         </td>
         <td><p>EXIT task
type</p>
<p>A: directory Exit</p>         </td>
      </tr>
      <tr>
         <td><p>etrace</p>         </td>
         <td><p>Inoperative
parameter</p>         </td>
      </tr>
      <tr>
         <td><p>mode</p>         </td>
         <td><p>Call mode:</p>
<ul>
<li>R: Requester
mode</li>
<li>S: Server
mode</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>commutfl</p>         </td>
         <td><p>Switching
flag (intermediate partner):</p>
<ul>
<li>0: no
switching in process</li>
<li>1: switching
in process</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>curtime</p>         </td>
         <td><p>Current
time (HHMMSSCC)</p>         </td>
      </tr>
      <tr>
         <td><p>curdate</p>         </td>
         <td><p>Current date (YYYYMMDD)</p>         </td>
      </tr>
      <tr>
         <td><p>curreqc</p>         </td>
         <td><p>Current number of transfers in requester
mode for the given network partner</p>         </td>
      </tr>
      <tr>
         <td><p>cursrvc</p>         </td>
         <td><p>Current number of transfers in server
mode for the given network partner</p>         </td>
      </tr>
      <tr>
         <td><p>maxrty</p>         </td>
         <td><p>Requester mode only</p>
<p>Maximum number of network connection attempts</p>         </td>
      </tr>
      <tr>
         <td><p>currty</p>         </td>
         <td><p>Requester
mode only</p>
<p>Current number of network connection attempts</p>         </td>
      </tr>
      <tr>
         <td><p>maxrtyp </p>         </td>
         <td><p>Requester
mode only</p>
<p>Maximum
number of protocol connection attempts</p>         </td>
      </tr>
      <tr>
         <td><p>currtyp</p>         </td>
         <td><p>Requester
mode only</p>
<p>Current
number of protocol connection attempts</p>         </td>
      </tr>
      <tr>
         <td><p>protl </p>         </td>
         <td><p>Information about the protocols of the CFTPARM object:</p>
<ul>
<li>protocol
identifier</li>
<li>protocol
type</li>
<li>profile,
in the case of the PESIT protocol</li>
<li>associated
network type</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>idf </p>         </td>
         <td><p>Partner-related
file identifier</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Return_codes___directory_exit"></span>

### Return codes

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Field</p>         </th>
<th class="HeadD-Column1-Header1"><p>Explanation</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>ret1</p>         </td>
         <td><p>Return
code</p>
<ul>
<li>0: Processing
ok</li>
<li>1: Transfer
CFT must take charge of the call</li>
<li>2: Connection
refusal</li>
<li>9: Processing
error</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>ret2 </p>         </td>
         <td><p>Cause
of connection refusal if the return code value is 2</p>
<ul>
<li>1: Partner
not known</li>
<li>2: Password
not valid</li>
<li>3: Address
not known</li>
<li>4: Call
time not valid</li>
<li>5: Communication
protocol not valid</li>
<li>6: Maximum
number of virtual circuits reached</li>
<li>7: Maximum
number of transfers reached</li>
<li>8: Maximum
number of partners reached</li>
<li>9: Caller
taxation refusal</li>
<li>10: Network
problem</li>
<li>255:
Other cause of connection refusal</li>
</ul>
<p>These refusal codes are converted by {{< TransferCFT/componentshortname  >}} into
internal diagnostic codes.</p>
<p>In
server mode, the internal diagnostic codes are converted into
protocol diagnostic codes and sent to the calling partner.</p>
<p>In
requester mode, the internal diagnostic codes are saved in
the catalog.</p>         </td>
      </tr>
      <tr>
         <td><p>diag</p>         </td>
         <td><p>Diagnostic
code if the return code is not 0 and 1</p>
<p>The contents of this field are used in the EXIT related
error.</p>         </td>
      </tr>
      <tr>
         <td><p>msg </p>         </td>
         <td><p>User message</p>
<p>If this field is defined, the content is sent to the Transfer
CFT standard output.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Partner_information___directory_exit"></span>

### Partner information

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Field</p>         </th>
<th class="HeadD-Column1-Header1"><p>Explanation</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>ptype</p>         </td>
         <td><p>Partner
type:</p>
<ul>
<li>C: normal
{{< TransferCFT/componentshortname  >}} partner</li>
<li>D: dynamic
{{< TransferCFT/componentshortname  >}} partner</li>
<li>E: non
{{< TransferCFT/componentshortname  >}} partner</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>part</p>         </td>
         <td><p>Partner
local identifie</p>         </td>
      </tr>
      <tr>
         <td><p>ipart</p>         </td>
         <td><p>Intermediate partner local identifier</p>         </td>
      </tr>
      <tr>
         <td><p>cpart</p>         </td>
         <td><p>Associated store and forward partner identifier</p>         </td>
      </tr>
      <tr>
         <td><p>idnet</p>         </td>
         <td><p>Network resource identifier</p>         </td>
      </tr>
      <tr>
         <td><p>idprot</p>         </td>
         <td><p>Protocol identifier</p>         </td>
      </tr>
      <tr>
         <td><p>prot</p>         </td>
         <td><p>Protocol type:</p>
<ul>
<li>P: PeSIT
protocol</li>
<li>0: ODETTE
protocol</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>prof</p>         </td>
         <td><p>PeSIT
only</p>
<p>Profile:</p>
<ul>
<li>C : PeSIT
D, Cft</li>
<li>S: PeSIT
D, Sit</li>
<li>A: PeSIT
E</li>
<li>D: PeSIT
E (DMZ)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>syst</p>         </td>
         <td><p>Operating
system:</p>
<ul>
<li>4: OS400</li>
<li>7: GCOS7</li>
<li>8: GCOS8</li>
<li>M: MVS</li>
<li>S: UNIX</li>
<li>V: VMS</li>
<li>G: GUARD</li>
<li>B: BS2000</li>
<li>W: WINDOWS</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>code </p>         </td>
         <td><p>Code:</p>
<ul>
<li>A:  ASCII</li>
<li>E:  EBCDIC</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>open</p>         </td>
         <td><p>No longer supported</p>         </td>
      </tr>
      <tr>
         <td><p>commut</p>         </td>
         <td><p>Store
and forward indicator:</p>
<ul>
<li>N:  No
store and forward</li>
<li>Y: Immediate
store and forward</li>
<li>S: Deferred
store and forward</li>
<li>P: Forced
commutation</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>sap</p>         </td>
         <td><p>Remote
SAP (Service Access Point)</p>         </td>
      </tr>
      <tr>
         <td><p>imaxtime</p>         </td>
         <td><p>Maximum incoming call time (HHMMSSCC)</p>         </td>
      </tr>
      <tr>
         <td><p>imintime</p>         </td>
         <td><p>Minimum incoming call time (HHMMSSCC)</p>         </td>
      </tr>
      <tr>
         <td><p>omaxtime</p>         </td>
         <td><p>Maximum outgoing call time (HHMMSSCC)</p>         </td>
      </tr>
      <tr>
         <td><p>omintime</p>         </td>
         <td><p>Minimum outgoing call time (HHMMSSCC)</p>         </td>
      </tr>
      <tr>
         <td><p>nrpart</p>         </td>
         <td><p>Remote partner name</p>         </td>
      </tr>
      <tr>
         <td><p>nrpassw</p>         </td>
         <td><p>Remote partner password</p>         </td>
      </tr>
      <tr>
         <td><p>newnrpw</p>         </td>
         <td><p>PeSIT E only</p>
<p>Remote partner new password</p>         </td>
      </tr>
      <tr>
         <td><p>nspart</p>         </td>
         <td><p>Local name</p>         </td>
      </tr>
      <tr>
         <td><p>nspassw</p>         </td>
         <td><p>Local password</p>         </td>
      </tr>
      <tr>
         <td><p>newnspw</p>         </td>
         <td><p>PeSIT E only</p>
<p>New local password</p>         </td>
      </tr>
      <tr>
         <td><p>group</p>         </td>
         <td><p>Group identifier</p>         </td>
      </tr>
      <tr>
         <td><p>sauth</p>         </td>
         <td><p>File send authorization list identifier</p>         </td>
      </tr>
      <tr>
         <td><p>rauth</p>         </td>
         <td><p>File receive authorization list identifier</p>         </td>
      </tr>
      <tr>
         <td><p>xlate</p>         </td>
         <td><p>Transcoding table identifier</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Partner_network_information___directory_exit"></span>

### Partner network information

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Field</p>         </th>
<th class="HeadD-Column1-Header1"><p>Explanation</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>ntype</p>         </td>
         <td><p>Network
type:</p>
<ul>
<li>T: TCP</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>addr</p>         </td>
         <td><p>Remote
partner address</p>         </td>
      </tr>
      <tr>
         <td><p>imaxt</p>         </td>
         <td><p>Maximum incoming call time on the network
resource</p>         </td>
      </tr>
      <tr>
         <td><p>imint</p>         </td>
         <td><p>Minimum incoming call time on the network
resource</p>         </td>
      </tr>
      <tr>
         <td><p>omaxt </p>         </td>
         <td><p>Maximum outgoing call time on the network
resource</p>         </td>
      </tr>
      <tr>
         <td><p>omint</p>         </td>
         <td><p>Minimum outgoing call time on the network
resource</p>         </td>
      </tr>
      <tr>
         <td><p>retryw</p>         </td>
         <td><p>Spacing of connection attempts (in minutes)</p>         </td>
      </tr>
      <tr>
         <td><p>retryn</p>         </td>
         <td><p>Number of connection attempts spaced by
retryw</p>         </td>
      </tr>
      <tr>
         <td><p>retrym</p>         </td>
         <td><p>Maximum number of connection attempts</p>         </td>
      </tr>
      <tr>
         <td><p>cnxin</p>         </td>
         <td><p>Maximum number of simultaneous incoming
calls for the given network partner</p>         </td>
      </tr>
      <tr>
         <td><p>cnxout</p>         </td>
         <td><p>Maximum number of simultaneous outgoing
calls, for the given network partner</p>         </td>
      </tr>
      <tr>
         <td><p>cnxinout</p>         </td>
         <td><p>Maximum number of simultaneous communications,
for the given network partner</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Network_dependent_information___directory_exit"></span>

### Network dependent information

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Field</p>         </th>
<th class="HeadD-Column1-Header1"><p>Explanation</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>udata</p>         </td>
         <td><p>User data</p>         </td>
      </tr>
      <tr>
         <td><p>odata</p>         </td>
         <td><p>Other data.</p>         </td>
      </tr>
      <tr>
         <td><p>speedin</p>         </td>
         <td><p>Virtual
circuit input speed (in bits/second)</p>         </td>
      </tr>
      <tr>
         <td><p>speedout</p>         </td>
         <td><p>Virtual circuit output speed (in bits/second)</p>         </td>
      </tr>
      <tr>
         <td><p>pcvin</p>         </td>
         <td><p>Incoming reverse charge call:</p>
<ul>
<li>1: Yes</li>
<li>0: No</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>pcvout</p>         </td>
         <td><p>Outgoing
reverse charge call:</p>
<ul>
<li>1: Yes</li>
<li>0: No</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>gfa</p>         </td>
         <td><p>Closed
subscriber group number</p>         </td>
      </tr>
      <tr>
         <td><p>verify</p>         </td>
         <td><p>Number of characters (between 0 and 64)
to be checked in the caing partner address</p>         </td>
      </tr>
      <tr>
         <td><p>parity</p>         </td>
         <td><p>Obsolete parameter</p>         </td>
      </tr>
      <tr>
         <td><p>databit</p>         </td>
         <td><p>Obsolete parameter</p>         </td>
      </tr>
      <tr>
         <td><p>stopbit</p>         </td>
         <td><p>Obsolete parameter</p>         </td>
      </tr>
      <tr>
         <td><p>modout</p>         </td>
         <td><p>Obsolete parameter</p>         </td>
      </tr>
      <tr>
         <td><p>config</p>         </td>
         <td><p>Obsolete parameter</p>         </td>
      </tr>
      <tr>
         <td><p>padno</p>         </td>
         <td><p>Obsolete parameter</p>         </td>
      </tr>
      <tr>
         <td><p>padset</p>         </td>
         <td><p>Obsolete parameter</p>         </td>
      </tr>
   </tbody>
</table>

### Additional information

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Field</p>         </th>
<th class="HeadD-Column1-Header1"><p>Explanation</p>         </th>
      </tr>
   </thead>
   <tbody>
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
         <td><p>SSL profile ID</p>         </td>
      </tr>
      <tr>
         <td><p>sRemoteSerial</p>         </td>
         <td><p>Serial Number</p>         </td>
      </tr>
      <tr>
         <td><p>ExitFree</p>         </td>
         <td><p>Free Area between all EXITs</p>         </td>
      </tr>
      <tr>
         <td><p>XferCycleId</p>         </td>
         <td><p>CycleId for tracking occurrences</p>         </td>
      </tr>
      <tr>
         <td><p>XferObjectcId</p>         </td>
         <td><p>Name of the transfer tracking class</p>         </td>
      </tr>
   </tbody>
</table>
