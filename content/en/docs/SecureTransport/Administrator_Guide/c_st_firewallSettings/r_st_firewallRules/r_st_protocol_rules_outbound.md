{
    "title": "Protocol rules - outbound from SecureTransport Edge",
    "linkTitle": "Protocol rules - outbound from SecureTransport Edge",
    "weight": "370"
}<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">#         </th>
<th class="HeadE-Column1-Header1">Group source         </th>
<th class="HeadE-Column1-Header1">Group destination         </th>
<th class="HeadE-Column1-Header1">Protocol         </th>
<th class="HeadE-Column1-Header1">Destination port         </th>
<th class="HeadE-Column1-Header1">Direction         </th>
<th class="HeadD-Column1-Header1">Purpose         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>32         </td>
         <td>Secure-<br />
Transport<br />
Edge         </td>
         <td>Internet         </td>
         <td>FTP(S)         </td>
         <td>1024 to 65535 port range specified on the Edge         </td>
         <td><img src="/Images/SecureTransport/LeftArrow_14x11.png" /><br />
(inbound)         </td>
         <td>Server FTP(S) data channel, active mode         </td>
      </tr>
      <tr>
         <td>33         </td>
         <td>Secure-<br />
Transport<br />
Edge         </td>
         <td>Internet         </td>
         <td>FTP(S)         </td>
         <td>1024 to 65535 port range specified on the client server         </td>
         <td><img src="/Images/SecureTransport/RightArrow_14x11.png" /><br />
(out-<br />
bound)         </td>
         <td>Server FTP(S) data channel, passive mode         </td>
      </tr>
      <tr>
         <td>34         </td>
         <td>Secure-<br />
Transport<br />
Edge         </td>
         <td>Internet         </td>
         <td>FTP(S)         </td>
         <td>21         </td>
         <td><img src="/Images/SecureTransport/RightArrow_14x11.png" /><br />
(out-<br />
bound)         </td>
         <td>Server FTP(S) data channel         </td>
      </tr>
      <tr>
         <td>35         </td>
         <td>Secure-<br />
Transport<br />
Edge         </td>
         <td>Internet         </td>
         <td>HTTP         </td>
         <td>80         </td>
         <td><img src="/Images/SecureTransport/RightArrow_14x11.png" /><br />
(out-<br />
bound)         </td>
         <td>Server HTTP data channel         </td>
      </tr>
      <tr>
         <td>36         </td>
         <td>Secure-<br />
Transport<br />
Edge         </td>
         <td>Internet         </td>
         <td>HTTPS         </td>
         <td>443         </td>
         <td><img src="/Images/SecureTransport/RightArrow_14x11.png" /><br />
(out-<br />
bound)         </td>
         <td>Server HTTPS data channel         </td>
      </tr>
      <tr>
         <td>37         </td>
         <td>Secure-<br />
Transport<br />
Edge         </td>
         <td>Internet         </td>
         <td>SSH         </td>
         <td>22         </td>
         <td><img src="/Images/SecureTransport/RightArrow_14x11.png" /><br />
(out-<br />
bound)         </td>
         <td>Server SSH data channel         </td>
      </tr>
      <tr>
         <td>38         </td>
         <td>Secure-<br />
Transport<br />
Edge         </td>
         <td>Internet         </td>
         <td>AS2         </td>
         <td>Specified in the transfer site         </td>
         <td><img src="/Images/SecureTransport/RightArrow_14x11.png" /><br />
(out-<br />
bound)         </td>
         <td>Server AS2 data channel         </td>
      </tr>
      <tr>
         <td>39         </td>
         <td>Secure-<br />
Transport<br />
Edge         </td>
         <td>Internet         </td>
         <td>PeSIT         </td>
         <td>Specified in the transfer site         </td>
         <td><img src="/Images/SecureTransport/RightArrow_14x11.png" /><br />
(out-<br />
bound)         </td>
         <td>Server PeSIT data channel         </td>
      </tr>
   </tbody>
</table>

If you disable the default HTTP port by not defining rule 4, do not define rule 35.

Define rules 39 and 40 for each port specified for the partnerships in the transfer sites.

**Related topics:**

-   [Protocol rules](../r_st_protocol_rules)
-   [Authentication rules](../r_st_authentication_rules)
-   [Administration rules](../r_st_administration_rules)
-   [TM server communication rules](../r_st_tm_server_communication_rules)
-   [Server transfer rules](../r_st_server_transfer_rules)
-   [Standard Cluster rules](../r_st_standard_clustering_rules)
-   [Enterprise Cluster rules](../r_st_large_enterprise_clustering_rules)
