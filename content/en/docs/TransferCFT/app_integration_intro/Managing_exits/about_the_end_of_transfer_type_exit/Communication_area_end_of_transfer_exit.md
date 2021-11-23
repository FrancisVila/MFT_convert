{
    "title": "About  the communication area",
    "linkTitle": "About the communication area",
    "weight": "340"
}This topic describes the end-of-transfer exit communication area. The
communication area contains the fields which are described in the tables
below:

-   [General
    information](#General_information_fields)
-   [Local
    file information](#Local_file_information_fields)
-   [Network
    file information](#Network_file_information)
-   [Transfer
    information](#Transfer_information)
-   [Information
    returned by the user (in update mode)](#Information_returned_by_the_user)
-   [Information
    input/returned by the user](#Information_input_returned_by_the_user)
-   [Additional
    information](#Additional_information)

The following tables list all the fields of the communication structure.

<span id="General_information_fields"></span>

### General information fields

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Field</p>         </th>
<th class="HeadD-Column1-Header1"><p>Explanation</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>idt</p>         </td>
         <td><p>Transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>idf</p>         </td>
         <td><p>File identifier (if  TYPE = FILE)</p>         </td>
      </tr>
      <tr>
         <td><p>idm</p>         </td>
         <td><p>Message identifier (if TYPE= MESSAGE)</p>         </td>
      </tr>
      <tr>
         <td><p>ida</p>         </td>
         <td><p>Application identifier</p>         </td>
      </tr>
      <tr>
         <td><p>part</p>         </td>
         <td><p>Partner name</p>         </td>
      </tr>
      <tr>
         <td><p>direct</p>         </td>
         <td><p>Transfer direction (S/R)</p>         </td>
      </tr>
      <tr>
         <td><p>diagi</p>         </td>
         <td><p>Internal diagnostics code</p>         </td>
      </tr>
      <tr>
         <td><p>diagp</p>         </td>
         <td><p>Protocol diagnostics code</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Local_file_information_fields"></span>

### Local file information fields

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Field</p>         </th>
<th class="HeadD-Column1-Header1"><p>Explanation</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>fblksize</p>         </td>
         <td><p>File block size</p>         </td>
      </tr>
      <tr>
         <td><p>fcode</p>         </td>
         <td><p>Data code (A, E or B)</p>         </td>
      </tr>
      <tr>
         <td><p>fkeylen</p>         </td>
         <td><p>Key length (indexed file)</p>         </td>
      </tr>
      <tr>
         <td><p>fkeypos</p>         </td>
         <td><p>Key position (indexed file)</p>         </td>
      </tr>
      <tr>
         <td><p>flrecl</p>         </td>
         <td><p>Record length</p>         </td>
      </tr>
      <tr>
         <td><p>fname</p>         </td>
         <td><p>Name of transferred file</p>         </td>
      </tr>
      <tr>
         <td><p>forg</p>         </td>
         <td><p>File organization:</p>
<ul>
<li>C: contiguous</li>
<li>I: indexed</li>
<li>D: direct</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>ftype</p>         </td>
         <td><p>File type</p>         </td>
      </tr>
      <tr>
         <td><p>frecfm</p>         </td>
         <td><p>Record format:</p>
<ul>
<li>F: fixed</li>
<li>U: undefined</li>
<li>V: variable</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>fspace</p>         </td>
         <td><p>Space allocated (in kilobytes)</p>         </td>
      </tr>
      <tr>
         <td><p>ftime</p>         </td>
         <td><p>File creation time (HHMMSSCC)</p>         </td>
      </tr>
      <tr>
         <td><p>fdate</p>         </td>
         <td><p>File creation date (YYYYMMDD)</p>         </td>
      </tr>
      <tr>
         <td><p>fday</p>         </td>
         <td><p>File creation day</p>         </td>
      </tr>
      <tr>
         <td><p>fmonth</p>         </td>
         <td><p>File creation month</p>         </td>
      </tr>
      <tr>
         <td><p>fyear</p>         </td>
         <td><p>File creation year</p>         </td>
      </tr>
      <tr>
         <td><p>unit</p>         </td>
         <td><p>File medium name</p>         </td>
      </tr>
      <tr>
         <td><p>unitc</p>         </td>
         <td><p>File medium type</p>         </td>
      </tr>
      <tr>
         <td><p>nbchar</p>         </td>
         <td><p>Number of characters transferred</p>         </td>
      </tr>
      <tr>
         <td><p>nbr</p>         </td>
         <td><p>Number of records transferred</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Network_file_information"></span>

### Network file information

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Field</p>         </th>
<th class="HeadD-Column1-Header1"><p>Explanation</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>nidf</p>         </td>
         <td><p>Network identifier of the file</p>         </td>
      </tr>
      <tr>
         <td><p>npart</p>         </td>
         <td><p>Remote partner</p>         </td>
      </tr>
      <tr>
         <td><p>nfname</p>         </td>
         <td><p>Network name of the file</p>         </td>
      </tr>
      <tr>
         <td><p>nkeylen</p>         </td>
         <td><p>Network key length (indexed)</p>         </td>
      </tr>
      <tr>
         <td><p>nkeypos</p>         </td>
         <td><p>Network key position (indexed)</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Transfer_information"></span>

### Transfer information

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Field</p>         </th>
<th class="HeadD-Column1-Header1"><p>Explanation</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>diagc</p>         </td>
         <td><p>Additional diagnostics code</p>         </td>
      </tr>
      <tr>
         <td><p>diagx</p>         </td>
         <td><p>rfu ( complementary to diagp)</p>         </td>
      </tr>
      <tr>
         <td><p>msg</p>         </td>
         <td><p>Message text sent</p>         </td>
      </tr>
      <tr>
         <td><p>parm</p>         </td>
         <td><p>user-defined network parameter</p>         </td>
      </tr>
      <tr>
         <td><p>profil</p>         </td>
         <td><p>PeSIT only</p>
<p>Profile:</p>
<ul>
<li>D: PESIT
E (DMZ)</li>
<li>C: PESIT
D CFT</li>
<li>S: PESIT
D SIT</li>
<li>A: PESIT
E</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>prottyp</p>         </td>
         <td><p>Protocol type:</p>
<ul>
<li>P: PeSIT</li>
<li>O: ODETTE</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>rappl</p>         </td>
         <td><p>Receiving application</p>         </td>
      </tr>
      <tr>
         <td><p>rpart</p>         </td>
         <td><p>Receiving partner</p>         </td>
      </tr>
      <tr>
         <td><p>ruser</p>         </td>
         <td><p>Receiving user</p>         </td>
      </tr>
      <tr>
         <td><p>sappl</p>         </td>
         <td><p>Sending application</p>         </td>
      </tr>
      <tr>
         <td><p>spart</p>         </td>
         <td><p>Sending partner</p>         </td>
      </tr>
      <tr>
         <td><p>suser</p>         </td>
         <td><p>Sending user</p>         </td>
      </tr>
      <tr>
         <td><p>ipart</p>         </td>
         <td><p>Intermediate partner</p>         </td>
      </tr>
      <tr>
         <td><p>ctime</p>         </td>
         <td><p>Catalog deposit time (HHMMSSCC)</p>         </td>
      </tr>
      <tr>
         <td><p>cdate</p>         </td>
         <td><p>Catalog deposit date (YYYYMMDD)</p>         </td>
      </tr>
      <tr>
         <td><p>cday</p>         </td>
         <td><p>Catalog deposit day</p>         </td>
      </tr>
      <tr>
         <td><p>cmonth</p>         </td>
         <td><p>Catalog deposit month</p>         </td>
      </tr>
      <tr>
         <td><p>cyear</p>         </td>
         <td><p>Catalog deposit year</p>         </td>
      </tr>
      <tr>
         <td><p>btime</p>         </td>
         <td><p>Transfer start time (HHMMSSCC)</p>         </td>
      </tr>
      <tr>
         <td><p>bdate</p>         </td>
         <td><p>Transfer start date (YYYYMMDD)</p>         </td>
      </tr>
      <tr>
         <td><p>bday</p>         </td>
         <td><p>Transfer start day</p>         </td>
      </tr>
      <tr>
         <td><p>bmonth</p>         </td>
         <td><p>Transfer start month</p>         </td>
      </tr>
      <tr>
         <td><p>byear</p>         </td>
         <td><p>Transfer star year</p>         </td>
      </tr>
      <tr>
         <td><p>etime</p>         </td>
         <td><p>Transfer end time (HHMMSSCC)</p>         </td>
      </tr>
      <tr>
         <td><p>edate</p>         </td>
         <td><p>Transfer end date (YYYYMMDD)</p>         </td>
      </tr>
      <tr>
         <td><p>eday</p>         </td>
         <td><p>Transfer end day</p>         </td>
      </tr>
      <tr>
         <td><p>emonth</p>         </td>
         <td><p>Transfer end month</p>         </td>
      </tr>
      <tr>
         <td><p>eyear</p>         </td>
         <td><p>Transfer end year</p>         </td>
      </tr>
      <tr>
         <td><p>xlate</p>         </td>
         <td><p>Translation table identifier</p>         </td>
      </tr>
      <tr>
         <td><p>group</p>         </td>
         <td><p>Group</p>         </td>
      </tr>
      <tr>
         <td><p>userid</p>         </td>
         <td><p>User
identifier</p>         </td>
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
         <td><p>SSL profile Id.</p>         </td>
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

<span id="Information_input_returned_by_the_user"></span>

### Information input/returned by the user

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Field</p>         </th>
<th class="HeadD-Column1-Header1"><p>Explanation</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>version</p>         </td>
         <td><p>Exit version</p>
<p>The value of this parameter is used to identify the version
of the EXIT task supplied.</p>         </td>
      </tr>
      <tr>
         <td><p>comment</p>         </td>
         <td><p>Local comment</p>
<p>This field can be modified by the user program. Any modifications
are taken into account when the catalog is updated (if usraction
= UPDATE with or without change of state).</p>         </td>
      </tr>
      <tr>
         <td><p>state</p>         </td>
         <td><p>State requested on UPDATE (D, H, K, X). See <a href="../#Transfer_state">Transfer
states.</a></p>         </td>
      </tr>
   </tbody>
</table>

<span id="Information_returned_by_the_user"></span>

### Information returned by the user

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Field</p>         </th>
<th class="HeadD-Column1-Header1"><p>Explanation</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>usraction</p>         </td>
         <td><p>Action requested by the user:</p>
<ul>
<li>U: UPDATE</li>
<li>D: DELETE</li>
<li>N: NONE</li>
</ul>
<p>Note:
If the value of the parameter is N (NONE), any changes to parameters that
have been requested, for example, modifications made to the comment field,
are ignored.</p>         </td>
      </tr>
      <tr>
         <td><p>usrmsg</p>         </td>
         <td><p>User message, 80 characters, recorded in the {{< TransferCFT/componentshortname  >}}
LOG file (CFTS18I)</p>
<p>This message can contain the code returned by the user
function and other information.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Additional_information"></span>

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
         <td><p>recblkn</p>         </td>
         <td><p>Catalog block number</p>         </td>
      </tr>
      <tr>
         <td><p>typ</p>         </td>
         <td><p>Transfer type:</p>
<ul>
<li>1: FILE</li>
<li>2: MSG</li>
<li>3: REPLY</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>stated</p>         </td>
         <td><p>Transfer acknowledgement</p>         </td>
      </tr>
      <tr>
         <td><p>nspart</p>         </td>
         <td><p>Transfer origin</p>         </td>
      </tr>
      <tr>
         <td><p>nrpart</p>         </td>
         <td><p>Transfer destination</p>         </td>
      </tr>
      <tr>
         <td><p>idtp</p>         </td>
         <td><p>Protocol identifier</p>         </td>
      </tr>
      <tr>
         <td><p>idexit</p>         </td>
         <td><p>EXIT identifier</p>         </td>
      </tr>
      <tr>
         <td><p>parmexit</p>         </td>
         <td><p>User EXIT parameter (PARM parameter of the CFTEXIT command)</p>         </td>
      </tr>
      <tr>
         <td><p>language</p>         </td>
         <td><p>Language:</p>
<ul>
<li>C: C
language</li>
<li>O: COBOL</li>
</ul>         </td>
      </tr>
   </tbody>
</table>
