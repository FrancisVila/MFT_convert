{
    "title": "Server transfer rules",
    "linkTitle": "Server transfer rules",
    "weight": "340"
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
         <td>28         </td>
         <td>Secure-<br />
Transport<br />
Servers         </td>
         <td>Secure-<br />
Transport<br />
Edge         </td>
         <td>SOCKS         </td>
         <td>1080         </td>
         <td><img src="/Images/SecureTransport/RightArrow_14x11.png" /><br />
(out-<br />
bound)         </td>
         <td>SOCKS5 proxy for server-initiated transfers (out-<br />
bound)         </td>
      </tr>
   </tbody>
</table>

Do not define rule 28 for a deployment with no {{< SecureTransport/componentshortname  >}} Edge.

**Related topics:**

-   [Protocol rules](../r_st_protocol_rules)
-   [Authentication rules](../r_st_authentication_rules)
-   [Administration rules](../r_st_administration_rules)
-   [TM server communication rules](../r_st_tm_server_communication_rules)
-   [Standard Cluster rules](../r_st_standard_clustering_rules)
-   [Enterprise Cluster rules](../r_st_large_enterprise_clustering_rules)
-   [Protocol rules - outbound from SecureTransport Edge](../r_st_protocol_rules_outbound)
