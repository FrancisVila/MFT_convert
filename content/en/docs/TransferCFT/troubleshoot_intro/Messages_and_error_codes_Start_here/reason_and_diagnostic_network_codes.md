{
    "title": "Reason and diagnostic network codes",
    "linkTitle": "Reason and diagnostic network codes",
    "weight": "520"
}# <span id="Reason_and_diagnostic_network_codes"></span>Reason and diagnostic network codes

<span id="Reason_codes"></span>Reason codes: REASON codes provide a general explanation of the error detected, or
the refusal.

<span id="Diagnostic_codes"></span>Diagnostic codes: DIAGNOSTIC (diag) codes provide a detailed explanation of the source
of the error detected or the refusal.

## <span id="TCP_IP_Network_codes"></span>TCP/IP network codes

### <span id="REASON___TCP_IP_Reason_Codes"></span>TCP/IP reason codes

REASON corresponds to the reason code returned by the TCP/IP communication
system.

The codes are expressed in hexadecimal.

TCP/IP Reason codes

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Code</th>
         <th>Description</th>
      </tr>
   </thead>
      <tr valign="top">
         <td width="21.869%">
            <p>00</p>
         </td>
         <td width="78.131%">
            <p>Connection request rejected by the network or break caused 
 by the remote partner</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="21.869%">
            <p>01</p>
         </td>
         <td width="78.131%">
            <p>Time-out for a connection request. The called party is 
 probably not connected to the network.</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="21.869%">
            <p>02</p>
         </td>
         <td width="78.131%">
            <p>Insufficient resources (other than memory)</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="21.869%">
            <p>03</p>
         </td>
         <td width="78.131%">
            <p>Insufficient memory</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="21.869%">
            <p>04</p>
         </td>
         <td width="78.131%">
            <p>The network access point reference passed to the connection 
 is not valid</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="21.869%">
            <p>08</p>
         </td>
         <td width="78.131%">
            <p>Invalid parameter in TCP request sent</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="21.869%">
            <p>09</p>
         </td>
         <td width="78.131%">
            <p>Other cause of rejection</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="21.869%">
            <p>43</p>
         </td>
         <td width="78.131%">
            <p>Invalid local or remote address</p>
         </td>
      </tr>
</table>

### <span id="DIAGN___TCP_IIP_Diagnostic_Codes"></span>TCP/IP diagnostic codes

DIAGN (TCP/IP diagnostic codes) corresponds to the diagnostic code returned
by the TCP/IP communication system.

The value of this code corresponds to the "errno" variable
provided by the TCP/IP resource. In this case, refer to the manufacturer's
documentation for the meaning of this code.
