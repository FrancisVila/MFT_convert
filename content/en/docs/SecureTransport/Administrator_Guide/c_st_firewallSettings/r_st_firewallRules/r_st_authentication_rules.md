{
    "title": "Authentication rules",
    "linkTitle": "Authentication rules",
    "weight": "320"
}<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <col/>
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>#</th>
         <th>Group source</th>
         <th>Group destination</th>
         <th>Protocol</th>
         <th>Destination port</th>
         <th>Direction</th>
         <th>Purpose</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>17         </td>
         <td>Secure-<br/>Transport<br/>Server         </td>
         <td>Trusted (secure network)         </td>
         <td>SiteMinder         </td>
         <td>44441         </td>
         <td>
<img data-mc-conditions="axway_conditions.ScreenOnly" src="RightArrow_14x11.png"/>
<br/>(out-<br/>bound)         </td>
         <td>SiteMinder Accounting         </td>
      </tr>
      <tr>
         <td>18         </td>
         <td>Secure-<br/>Transport<br/>Server         </td>
         <td>Trusted (secure network)         </td>
         <td>SiteMinder         </td>
         <td>44442         </td>
         <td>
<img data-mc-conditions="axway_conditions.ScreenOnly" src="RightArrow_14x11.png"/>
<br/>(out-<br/>bound)         </td>
         <td>SiteMinder Authentication         </td>
      </tr>
      <tr>
         <td>19         </td>
         <td>Secure-<br/>Transport<br/>Server         </td>
         <td>Trusted (secure network)         </td>
         <td>SiteMinder         </td>
         <td>44443         </td>
         <td>
<img data-mc-conditions="axway_conditions.ScreenOnly" src="RightArrow_14x11.png"/>
<br/>(out-<br/>bound)         </td>
         <td>SiteMinder Authorization         </td>
      </tr>
      <tr>
         <td>20         </td>
         <td>Secure-<br/>Transport<br/>Server         </td>
         <td>Trusted (secure network)         </td>
         <td>LDAP         </td>
         <td>389 or 3268         </td>
         <td>
<img data-mc-conditions="axway_conditions.ScreenOnly" src="RightArrow_14x11.png"/>
<br/>(out-<br/>bound)         </td>
         <td>LDAP user lookup and authentication         </td>
      </tr>
   </tbody>
</table>

**Related topics:**

-   [Protocol rules](../r_st_protocol_rules)
-   [Administration rules](../r_st_administration_rules)
-   [TM server communication rules](../r_st_tm_server_communication_rules)
-   [Server transfer rules](../r_st_server_transfer_rules)
-   [Standard Cluster rules](../r_st_standard_clustering_rules)
-   [Enterprise Cluster rules](../r_st_large_enterprise_clustering_rules)
-   [Protocol rules - outbound from SecureTransport Edge](../r_st_protocol_rules_outbound)
