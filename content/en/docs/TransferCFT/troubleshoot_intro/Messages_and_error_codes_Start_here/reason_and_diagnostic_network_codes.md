{
    "title": "Reason  and diagnostic network codes",
    "linkTitle": "Reason and diagnostic network codes",
    "weight": "500"
}<span id="Reason_codes"></span>Reason codes: REASON codes provide a general explanation of the error detected, or
the refusal.

<span id="Diagnostic_codes"></span>Diagnostic codes: DIAGNOSTIC (diag) codes provide a detailed explanation of the source
of the error detected or the refusal.

<span id="TCP_IP_Network_codes"></span>

## TCP/IP network codes

<span id="REASON___TCP_IP_Reason_Codes"></span>

### TCP/IP reason codes

REASON corresponds to the reason code returned by the TCP/IP communication
system.

The codes are expressed in hexadecimal.

TCP/IP Reason codes

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Code         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>00</p>         </td>
         <td><p>Connection request rejected by the network or break caused
by the remote partner</p>         </td>
      </tr>
      <tr>
         <td><p>01</p>         </td>
         <td><p>Time-out for a connection request. The called party is
probably not connected to the network.</p>         </td>
      </tr>
      <tr>
         <td><p>02</p>         </td>
         <td><p>Insufficient resources (other than memory)</p>         </td>
      </tr>
      <tr>
         <td><p>03</p>         </td>
         <td><p>Insufficient memory</p>         </td>
      </tr>
      <tr>
         <td><p>04</p>         </td>
         <td><p>The network access point reference passed to the connection
is not valid</p>         </td>
      </tr>
      <tr>
         <td><p>08</p>         </td>
         <td><p>Invalid parameter in TCP request sent</p>         </td>
      </tr>
      <tr>
         <td><p>09</p>         </td>
         <td><p>Other cause of rejection</p>         </td>
      </tr>
      <tr>
         <td><p>43</p>         </td>
         <td><p>Invalid local or remote address</p>         </td>
      </tr>
   </tbody>
</table>

<span id="DIAGN___TCP_IIP_Diagnostic_Codes"></span>

### TCP/IP diagnostic codes

DIAGN (TCP/IP diagnostic codes) corresponds to the diagnostic code returned
by the TCP/IP communication system.

The value of this code corresponds to the "errno" variable
provided by the TCP/IP resource. In this case, refer to the manufacturer's
documentation for the meaning of this code.
