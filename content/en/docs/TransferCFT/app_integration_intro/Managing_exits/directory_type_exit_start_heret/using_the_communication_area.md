{
    "title": "Using server mode",
    "linkTitle": "Using server mode",
    "weight": "410"
}# <span id="Title"></span>Using server mode



This topic describes how to use the communication area for a directory

exit in server mode. The [next topic](using_requester_mode.htm)

explains a directory exit in the requester mode.



## <span id="Server_Mode"></span>Server mode



The entire communication structure is defined by the interface before

the user function is called. You must perform checks concerning the characteristics

of the calling partner.



### Partner information fields



<table data-cellspacing="0">
<thead>
<tr>
<th><p>Field </p></th>
<th><p>Explanation </p></th>
</tr>
</thead>
<tbody>
<tr>
<td data-valign="top"><p>ptype </p></td>
<td data-valign="top" width="84%"><p>Partner type </p></td>
</tr>
<tr>
<td data-valign="top"><p>nrpart </p></td>
<td data-valign="top" width="84%"><p>Remote partner name </p></td>
</tr>
<tr>
<td data-valign="top"><p>nrpassw </p></td>
<td data-valign="top" width="84%"><p>Remote partner password </p></td>
</tr>
<tr>
<td data-valign="top"><p>newnrpw </p></td>
<td data-valign="top" width="84%"><p>Remote partner new password </p></td>
</tr>
<tr>
<td data-valign="top"><p>nspart </p></td>
<td data-valign="top" width="84%"><p>Local name </p></td>
</tr>
<tr>
<td data-valign="top"><p>nspassw </p></td>
<td data-valign="top" width="84%"><p>Local password </p></td>
</tr>
<tr>
<td data-valign="top"><p>prot </p></td>
<td data-valign="top" width="84%"><p>Protocol type </p></td>
</tr>
<tr>
<td data-valign="top"><p>prof </p></td>
<td data-valign="top" width="84%"><p>Profile if PESIT protocol </p></td>
</tr>
<tr>
<td data-valign="top"><p>sap </p></td>
<td data-valign="top" width="84%"><p>Remote Sap (Service Access Point) </p></td>
</tr>
<tr>
<td data-valign="top"><p>imaxtime </p></td>
<td data-valign="top" width="84%"><p>Maximum incoming call time (HHMMSSCC)</p></td>
</tr>
<tr>
<td data-valign="top"><p>imintime </p></td>
<td data-valign="top" width="84%"><p>Minimum incoming call time (HHMMSSCC)</p></td>
</tr>
<tr>
<td data-valign="top"><p>ntype </p></td>
<td data-valign="top" width="84%"><p>Network type </p></td>
</tr>
<tr>
<td data-valign="top"><p>addr </p></td>
<td data-valign="top" width="84%"><p>Remote partner address </p></td>
</tr>
<tr>
<td data-valign="top"><p>udata </p></td>
<td data-valign="top" width="84%"><p>User data </p></td>
</tr>
<tr>
<td data-valign="top"><p>pcvin </p></td>
<td data-valign="top" width="84%"><p>Incoming reverse charge call</p></td>
</tr>
<tr>
<td data-valign="top"><p>gfa </p></td>
<td data-valign="top" width="84%"><p>Closed subscriber group number </p></td>
</tr>
</tbody>
</table>



When the user function is called, if the partner name <span>part</span>

is empty, so that the partner local identifier is unknown to Transfer

CFT, the only fields that contain valid data (imintime and imintime are

initialized to "23595999" and "00000000" respectively)

are the above fields in addition to the general information fields.  

The <span>ret1</span> return code field must

be defined when the user function is returned.  

If there is a connection refusal, return code value of 2, the <span>ret2</span>

field may be defined to inform the calling partner of the cause of the

refusal.  

The content of the diag field appears with the appropriate error message

if the return code is not 0 and 1.  

If the msg field is defined, its content is sent to the <span>Transfer CFT</span> standard

output.



If the return code value is 0 or 1, the user can modify the fields indicated

in the following System information field table.



### System information fields



<table data-cellspacing="0">
<thead>
<tr>
<th><p>Field </p></th>
<th><p>Explanation </p></th>
</tr>
</thead>
<tbody>
<tr>
<td data-valign="top" width="16%"><p>syst </p></td>
<td data-valign="top" width="84%"><p>System </p></td>
</tr>
<tr>
<td data-valign="top" width="16%"><p>code </p></td>
<td data-valign="top" width="84%"><p>Code:</p>
<ul>
<li>A: ASCII</li>
<li>E: EBCDIC</li>
</ul></td>
</tr>
<tr>
<td data-valign="top" width="16%"><p>open </p></td>
<td data-valign="top" width="84%"><p>Obsolete parameter</p></td>
</tr>
<tr>
<td data-valign="top" width="16%"><p>commut </p></td>
<td data-valign="top" width="84%"><p>Store and forward indicator </p></td>
</tr>
<tr>
<td data-valign="top" width="16%"><p>nspart </p></td>
<td data-valign="top" width="84%"><p>Local name </p></td>
</tr>
<tr>
<td data-valign="top" width="16%"><p>nspassw </p></td>
<td data-valign="top" width="84%"><p>Local password </p></td>
</tr>
<tr>
<td data-valign="top" width="16%"><p>part </p></td>
<td data-valign="top" width="84%"><p>Partner local identifier </p></td>
</tr>
<tr>
<td data-valign="top" width="16%"><p>group </p></td>
<td data-valign="top" width="84%"><p>Group identifier </p></td>
</tr>
<tr>
<td data-valign="top" width="16%"><p>sauth </p></td>
<td data-valign="top" width="84%"><p>File send authorization list identifier </p></td>
</tr>
<tr>
<td data-valign="top" width="16%"><p>rauth </p></td>
<td data-valign="top" width="84%"><p>File receive authorization list identifier </p></td>
</tr>
<tr>
<td data-valign="top" width="16%"><p>xlate </p></td>
<td data-valign="top" width="84%"><p>Transcoding table identifier </p></td>
</tr>
<tr>
<td data-valign="top" width="16%"><p>idf </p></td>
<td data-valign="top" width="84%"><p>Partner file identifier </p></td>
</tr>
</tbody>
</table>



If the part field of the communication

structure is empty on return from the user function, the partner local

identifier UNDEFPTN appears in

the catalog and on the <span>Transfer CFT</span> standard output.  

If the part field has been modified

and if the new identifier is located in the <span>Transfer CFT</span> partner base,

<span>Transfer CFT</span> sets the ret1 field to 9 (processing error) and the diag

field to "PTNEXIST".

