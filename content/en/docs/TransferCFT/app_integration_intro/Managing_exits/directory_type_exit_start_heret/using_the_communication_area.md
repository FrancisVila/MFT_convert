{
    "title": "Using  server mode",
    "linkTitle": "Using server mode",
    "weight": "380"
}This topic describes how to use the communication area for a directory
exit in server mode. The [next topic](../using_requester_mode)
explains a directory exit in the requester mode.

<span id="Server_Mode"></span>

## Server mode

The entire communication structure is defined by the interface before
the user function is called. You must perform checks concerning the characteristics
of the calling partner.

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
         <td><p>ptype </p>         </td>
         <td><p>Partner type </p>         </td>
      </tr>
      <tr>
         <td><p>nrpart </p>         </td>
         <td><p>Remote partner name </p>         </td>
      </tr>
      <tr>
         <td><p>nrpassw </p>         </td>
         <td><p>Remote partner password </p>         </td>
      </tr>
      <tr>
         <td><p>newnrpw </p>         </td>
         <td><p>Remote partner new password </p>         </td>
      </tr>
      <tr>
         <td><p>nspart </p>         </td>
         <td><p>Local name </p>         </td>
      </tr>
      <tr>
         <td><p>nspassw </p>         </td>
         <td><p>Local password </p>         </td>
      </tr>
      <tr>
         <td><p>prot </p>         </td>
         <td><p>Protocol type </p>         </td>
      </tr>
      <tr>
         <td><p>prof </p>         </td>
         <td><p>Profile if PESIT protocol </p>         </td>
      </tr>
      <tr>
         <td><p>sap </p>         </td>
         <td><p>Remote Sap (Service Access Point) </p>         </td>
      </tr>
      <tr>
         <td><p>imaxtime </p>         </td>
         <td><p>Maximum incoming call time (HHMMSSCC)</p>         </td>
      </tr>
      <tr>
         <td><p>imintime </p>         </td>
         <td><p>Minimum incoming call time (HHMMSSCC)</p>         </td>
      </tr>
      <tr>
         <td><p>ntype </p>         </td>
         <td><p>Network type </p>         </td>
      </tr>
      <tr>
         <td><p>addr </p>         </td>
         <td><p>Remote partner address </p>         </td>
      </tr>
      <tr>
         <td><p>udata </p>         </td>
         <td><p>User data </p>         </td>
      </tr>
      <tr>
         <td><p>pcvin </p>         </td>
         <td><p>Incoming reverse charge call</p>         </td>
      </tr>
      <tr>
         <td><p>gfa </p>         </td>
         <td><p>Closed subscriber group number </p>         </td>
      </tr>
   </tbody>
</table>

When the user function is called, if the partner name <span style="font-weight: bold;">part</span>
is empty, so that the partner local identifier is unknown to Transfer
CFT, the only fields that contain valid data (imintime and imintime are
initialized to "23595999" and "00000000" respectively)
are the above fields in addition to the general information fields.  
The <span style="font-weight: bold;">ret1</span> return code field must
be defined when the user function is returned.  
If there is a connection refusal, return code value of 2, the <span style="font-weight: bold;">ret2</span>
field may be defined to inform the calling partner of the cause of the
refusal.  
The content of the diag field appears with the appropriate error message
if the return code is not 0 and 1.  
If the msg field is defined, its content is sent to the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> standard
output.

If the return code value is 0 or 1, the user can modify the fields indicated
in the following System information field table.

### System information fields

<table>
   <th>
      <tr>
<th><p>Field </p>         </th>
<th><p>Explanation </p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>syst </p>         </td>
         <td><p>System </p>         </td>
      </tr>
      <tr>
         <td><p>code </p>         </td>
         <td><p>Code:</p>
<ul>
<li>A: ASCII</li>
<li>E: EBCDIC</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>open </p>         </td>
         <td><p>Obsolete parameter</p>         </td>
      </tr>
      <tr>
         <td><p>commut </p>         </td>
         <td><p>Store and forward indicator </p>         </td>
      </tr>
      <tr>
         <td><p>nspart </p>         </td>
         <td><p>Local name </p>         </td>
      </tr>
      <tr>
         <td><p>nspassw </p>         </td>
         <td><p>Local password </p>         </td>
      </tr>
      <tr>
         <td><p>part </p>         </td>
         <td><p>Partner local identifier </p>         </td>
      </tr>
      <tr>
         <td><p>group </p>         </td>
         <td><p>Group identifier </p>         </td>
      </tr>
      <tr>
         <td><p>sauth </p>         </td>
         <td><p>File send authorization list identifier </p>         </td>
      </tr>
      <tr>
         <td><p>rauth </p>         </td>
         <td><p>File receive authorization list identifier </p>         </td>
      </tr>
      <tr>
         <td><p>xlate </p>         </td>
         <td><p>Transcoding table identifier </p>         </td>
      </tr>
      <tr>
         <td><p>idf </p>         </td>
         <td><p>Partner file identifier </p>         </td>
      </tr>
   </tbody>
</table>

If the part field of the communication
structure is empty on return from the user function, the partner local
identifier UNDEFPTN appears in
the catalog and on the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> standard output.  
If the part field has been modified
and if the new identifier is located in the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> partner base,
<span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> sets the ret1 field to 9 (processing error) and the diag
field to "PTNEXIST".
