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

-   <a href="../r_st_protocol_rules" class="MCXref xref">Protocol rules</a>
-   <a href="../r_st_authentication_rules" class="MCXref xref">Authentication rules</a>
-   <a href="../r_st_administration_rules" class="MCXref xref">Administration rules</a>
-   <a href="../r_st_tm_server_communication_rules" class="MCXref xref">TM server communication rules</a>
-   <a href="../r_st_standard_clustering_rules" class="MCXref xref">Standard Cluster rules</a>
-   <a href="../r_st_large_enterprise_clustering_rules" class="MCXref xref">Enterprise Cluster rules</a>
-   <a href="../r_st_protocol_rules_outbound" class="MCXref xref">Protocol rules - outbound from SecureTransport Edge</a>
