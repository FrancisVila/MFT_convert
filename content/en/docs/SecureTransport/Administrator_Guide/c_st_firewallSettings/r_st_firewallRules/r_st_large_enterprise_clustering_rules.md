{
    "title": "Large enterprise clustering rules",
    "linkTitle": "Large enterprise clustering rules",
    "weight": "370"
}The following rule is required for a Enterprise Cluster (EC). The cluster cache manager uses the first free port starting at 8088.

<table cellspacing="0">
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
         <td>31         </td>
         <td>Secure-<br/>Transport<br/>Servers         </td>
         <td>Secure-<br/>Transport<br/>Servers         </td>
         <td>TCP and UDP         </td>
         <td>8088 through 8093         </td>
         <td>
<img data-mc-conditions="axway_conditions.ScreenOnly" src="RightArrow_14x11.png"/>
<img data-mc-conditions="axway_conditions.ScreenOnly" src="RightArrow_14x11.png"/>
<br/>(server-to-server)         </td>
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
