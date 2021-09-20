{
    "title": "Standard clustering rules",
    "linkTitle": "Standard clustering rules",
    "weight": "360"
}The following rules are required for a Standard Cluster (SC).

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
         <td>29         </td>
         <td>Secure-<br/>Transport<br/>Servers         </td>
         <td>Secure-<br/>Transport<br/>Servers         </td>
         <td>Proprietary         </td>
         <td>44431         </td>
         <td>
<img data-mc-conditions="axway_conditions.ScreenOnly" src="RightArrow_14x11.png"/>
<img data-mc-conditions="axway_conditions.ScreenOnly" src="RightArrow_14x11.png"/>
<br/>(server-to-server)         </td>
         <td>Server synchronization and heartbeat         </td>
      </tr>
      <tr>
         <td>30         </td>
         <td>Secure-<br/>Transport<br/>Servers         </td>
         <td>Secure-<br/>Transport<br/>Servers         </td>
         <td>HTTPS         </td>
         <td>444         </td>
         <td>
<img data-mc-conditions="axway_conditions.ScreenOnly" src="RightArrow_14x11.png"/>
<img data-mc-conditions="axway_conditions.ScreenOnly" src="RightArrow_14x11.png"/>
<br/>(server-to-server)         </td>
         <td>Synchronization         </td>
      </tr>
   </tbody>
</table>

**Related topics:**

-   [Protocol rules](../r_st_protocol_rules)
-   [Authentication rules](../r_st_authentication_rules)
-   [Administration rules](../r_st_administration_rules)
-   [TM server communication rules](../r_st_tm_server_communication_rules)
-   [Server transfer rules](../r_st_server_transfer_rules)
-   [Enterprise Cluster rules](../r_st_large_enterprise_clustering_rules)
-   [Protocol rules - outbound from SecureTransport Edge](../r_st_protocol_rules_outbound)
