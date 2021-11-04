{
    "title": "Authentication rules",
    "linkTitle": "Authentication rules",
    "weight": "310"
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
         <td>17         </td>
         <td>Secure-<br />
Transport<br />
Server         </td>
         <td>Trusted (secure network)         </td>
         <td>SiteMinder         </td>
         <td>44441         </td>
         <td><img src="/Images/SecureTransport/RightArrow_14x11.png" /><br />
(out-<br />
bound)         </td>
         <td>SiteMinder Accounting         </td>
      </tr>
      <tr>
         <td>18         </td>
         <td>Secure-<br />
Transport<br />
Server         </td>
         <td>Trusted (secure network)         </td>
         <td>SiteMinder         </td>
         <td>44442         </td>
         <td><img src="/Images/SecureTransport/RightArrow_14x11.png" /><br />
(out-<br />
bound)         </td>
         <td>SiteMinder Authentication         </td>
      </tr>
      <tr>
         <td>19         </td>
         <td>Secure-<br />
Transport<br />
Server         </td>
         <td>Trusted (secure network)         </td>
         <td>SiteMinder         </td>
         <td>44443         </td>
         <td><img src="/Images/SecureTransport/RightArrow_14x11.png" /><br />
(out-<br />
bound)         </td>
         <td>SiteMinder Authorization         </td>
      </tr>
      <tr>
         <td>20         </td>
         <td>Secure-<br />
Transport<br />
Server         </td>
         <td>Trusted (secure network)         </td>
         <td>LDAP         </td>
         <td>389 or 3268         </td>
         <td><img src="/Images/SecureTransport/RightArrow_14x11.png" /><br />
(out-<br />
bound)         </td>
         <td>LDAP user lookup and authentication         </td>
      </tr>
   </tbody>
</table>

**Related topics:**

-   <a href="../r_st_protocol_rules" class="MCXref xref">Protocol rules</a>
-   <a href="../r_st_administration_rules" class="MCXref xref">Administration rules</a>
-   <a href="../r_st_tm_server_communication_rules" class="MCXref xref">TM server communication rules</a>
-   <a href="../r_st_server_transfer_rules" class="MCXref xref">Server transfer rules</a>
-   <a href="../r_st_standard_clustering_rules" class="MCXref xref">Standard Cluster rules</a>
-   <a href="../r_st_large_enterprise_clustering_rules" class="MCXref xref">Enterprise Cluster rules</a>
-   <a href="../r_st_protocol_rules_outbound" class="MCXref xref">Protocol rules - outbound from SecureTransport Edge</a>
