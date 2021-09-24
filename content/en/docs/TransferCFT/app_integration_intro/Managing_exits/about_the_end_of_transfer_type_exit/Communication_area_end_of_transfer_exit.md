{
    "title": "About the communication area",
    "linkTitle": "About the communication area",
    "weight": "370"
}# <span id="Title"></span><span id="About_the_communication_area__End_of_transfer_exit"></span>About the communication area

This topic describes the end-of-transfer exit communication area. The
communication area contains the fields which are described in the tables
below:

-   [General
    information](#general_information_fields)
-   [Local
    file information](#local_file_information_fields)
-   [Network
    file information](#network_file_information)
-   [Transfer
    information](#transfer_information)
-   [Information
    returned by the user (in update mode)](#information_returned_by_the_user)
-   [Information
    input/returned by the user](#information_input_returned_by_the_user)
-   [Additional
    information](#additional_information)

The following tables list all the fields of the communication structure.

### <span id="General_information_fields"></span>General information fields

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p>Field</p>
</th>
         <th>
            <p>Explanation</p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td colspan="1" rowspan="1">
            <p>idt</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Transfer identifier</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>idf</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>File identifier (if  TYPE = FILE)</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>idm</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Message identifier (if TYPE= MESSAGE) </p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>ida</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Application identifier</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>part</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Partner name</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>direct</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Transfer direction (S/R)</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>diagi</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Internal diagnostics code</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>diagp</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Protocol diagnostics code</p>
         </td>
      </tr>
   </tbody>
</table>

### <span id="Local_file_information_fields"></span>Local file information fields

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p>Field</p>
</th>
         <th>
            <p>Explanation</p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td colspan="1" rowspan="1">
            <p>fblksize</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>File block size</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>fcode</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Data code (A, E or B)</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>fkeylen</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Key length (indexed file) </p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>fkeypos</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Key position (indexed file)</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>flrecl</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Record length</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>fname</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Name of transferred file</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>forg</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>File organization:</p>
            <ul>
               <li>C: contiguous               </li>
               <li>I: indexed               </li>
               <li>D: direct               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>ftype</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>File type</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>frecfm</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Record format:</p>
            <ul>
               <li>F: fixed               </li>
               <li>U: undefined               </li>
               <li>V: variable               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>fspace</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Space allocated (in kilobytes)</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>ftime</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>File creation time (HHMMSSCC)</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>fdate</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>File creation date (YYYYMMDD)</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>fday</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>File creation day</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>fmonth</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>File creation month</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>fyear</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>File creation year</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>unit</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>File medium name</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>unitc</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>File medium type</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>nbchar</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Number of characters transferred</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>nbr</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Number of records transferred</p>
         </td>
      </tr>
   </tbody>
</table>

### <span id="Network_file_information"></span>Network file information

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p>Field</p>
</th>
         <th>
            <p>Explanation</p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td colspan="1" rowspan="1">
            <p>nidf</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Network identifier of the file</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>npart</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Remote partner</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>nfname</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Network name of the file</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>nkeylen</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Network key length (indexed)</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>nkeypos</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Network key position (indexed)</p>
         </td>
      </tr>
   </tbody>
</table>

### <span id="Transfer_information"></span>Transfer information

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p>Field</p>
</th>
         <th>
            <p>Explanation</p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td colspan="1" rowspan="1">
            <p>diagc</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Additional diagnostics code</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>diagx</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>rfu ( complementary to diagp)</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>msg</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Message text sent</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>parm</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>user-defined network parameter</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>profil</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>PeSIT only</p>
            <p>Profile:</p>
            <ul>
               <li>D: PESIT 
 E (DMZ)               </li>
               <li>C: PESIT 
 D CFT               </li>
               <li>S: PESIT 
 D SIT               </li>
               <li>A: PESIT 
 E               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>prottyp</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Protocol type:</p>
            <ul>
               <li>P: PeSIT               </li>
               <li>O: ODETTE               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>rappl</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Receiving application</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>rpart</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Receiving partner</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>ruser</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Receiving user</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>sappl</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Sending application</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>spart</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Sending partner</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>suser</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Sending user</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>ipart</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Intermediate partner</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>ctime</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Catalog deposit time (HHMMSSCC)</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>cdate</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Catalog deposit date (YYYYMMDD)</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>cday</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Catalog deposit day</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>cmonth</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Catalog deposit month</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>cyear</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Catalog deposit year</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>btime</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Transfer start time (HHMMSSCC)</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>bdate</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Transfer start date (YYYYMMDD)</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>bday</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Transfer start day</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>bmonth</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Transfer start month</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>byear</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Transfer star year</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>etime</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Transfer end time (HHMMSSCC)</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>edate</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Transfer end date (YYYYMMDD)</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>eday</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Transfer end day</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>emonth</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Transfer end month</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>eyear</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Transfer end year</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>xlate</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Translation table identifier</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>group</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Group</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>userid</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>User 
 identifier</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>cMode</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>SSL mode Client/Server</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>cAuthPolicy</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>SSL auth Anonymous/Simple/Double</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>bCipher</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>SSL cipher suite</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>sParm</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>SSL command free parameters</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>sRemoteUserDn</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Remote User certificate Dn</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>sRemoteIssuerDn</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Remote Issuer Dn</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>sRemoteCaId</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Remote CA Alias</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>sUserCId</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>User Certificate Alias</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>sCertFname</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>File including Remote certificate</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>sProf</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>SSL profile Id.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>sRemoteSerial</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Serial Number</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>ExitFree</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Free Area between all EXITs</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>XferCycleId</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>CycleId for tracking occurrences </p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>XferObjectcId</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Name of the transfer tracking class </p>
         </td>
      </tr>
   </tbody>
</table>

### <span id="Information_input_returned_by_the_user"></span>Information input/returned by the user

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p>Field</p>
</th>
         <th>
            <p>Explanation</p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td colspan="1" rowspan="1">
            <p>version</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Exit version</p>
            <p>The value of this parameter is used to identify the version 
 of the EXIT task supplied.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>comment</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Local comment</p>
            <p>This field can be modified by the user program. Any modifications 
 are taken into account when the catalog is updated (if usraction 
 = UPDATE with or without change of state).</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>state</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>State requested on UPDATE (D, H, K, X). See <a href="..//transfercft/app_integration_intro/managing_exits/about_the_end_of_transfer_type_exit">Transfer 
 states.</a></p>
         </td>
      </tr>
   </tbody>
</table>

### <span id="Information_returned_by_the_user"></span>Information returned by the user

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p>Field</p>
</th>
         <th>
            <p>Explanation</p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td colspan="1" rowspan="1">
            <p>usraction</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Action requested by the user:</p>
            <ul>
               <li>U: UPDATE               </li>
               <li>D: DELETE               </li>
               <li>N: NONE               </li>
            </ul>
            <p>Note: 
 If the value of the parameter is N (NONE), any changes to parameters that 
 have been requested, for example, modifications made to the comment field, 
 are ignored.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>usrmsg</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>User message, 80 characters, recorded in the  <span>Transfer CFT</span> 
 LOG file (CFTS18I)</p>
            <p>This message can contain the code returned by the user 
 function and other information.</p>
         </td>
      </tr>
   </tbody>
</table>

### <span id="Additional_information"></span>Additional information

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p>Field</p>
</th>
         <th>
            <p>Explanation</p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td colspan="1" rowspan="1">
            <p>recblkn</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Catalog block number</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>typ</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Transfer type:</p>
            <ul>
               <li>1: FILE               </li>
               <li>2: MSG               </li>
               <li>3: REPLY               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>stated</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Transfer acknowledgement</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>nspart</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Transfer origin</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>nrpart</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Transfer destination</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>idtp</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Protocol identifier</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>idexit</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>EXIT identifier</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>parmexit</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>User EXIT parameter (PARM parameter of the CFTEXIT command)</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>language</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Language:</p>
            <ul>
               <li>C: C 
 language               </li>
               <li>O: COBOL               </li>
            </ul>
         </td>
      </tr>
   </tbody>
</table>
