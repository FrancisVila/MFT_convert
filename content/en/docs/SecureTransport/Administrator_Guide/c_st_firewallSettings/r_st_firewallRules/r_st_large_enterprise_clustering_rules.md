{
    "title": "Enterprise Cluster rules",
    "linkTitle": "Large enterprise clustering rules",
    "weight": "360"
}The following rule is required for a Enterprise Cluster (EC). The cluster cache manager uses the first free port starting at 8088.

<table>
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
         <td>31         </td>
         <td>Secure-<br />
Transport<br />
Servers         </td>
         <td>Secure-<br />
Transport<br />
Servers         </td>
         <td>TCP and UDP         </td>
         <td>8088 through 8093         </td>
         <td><img src="/Images/SecureTransport/LeftArrow_14x11.png" />
<img src="/Images/SecureTransport/RightArrow_14x11.png" /><br />
(server-to-server)         </td>
         <td>Cluster cache management         </td>
      </tr>
   </tbody>
</table>

**Related topics:**

-   [Protocol rules](../r_st_protocol_rules)
-   [Authentication rules](../r_st_authentication_rules)
-   [Administration rules](../r_st_administration_rules)
-   [TM server communication rules](../r_st_tm_server_communication_rules)
-   [Server transfer rules](../r_st_server_transfer_rules)
-   [Standard Cluster rules](../r_st_standard_clustering_rules)
-   [Protocol rules - outbound from SecureTransport Edge](../r_st_protocol_rules_outbound)
