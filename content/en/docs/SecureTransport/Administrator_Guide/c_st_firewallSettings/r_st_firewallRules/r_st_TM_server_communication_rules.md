{
    "title": "TM server communication rules",
    "linkTitle": "TM server communication rules",
    "weight": "340"
}Network zones define the server ports that the TM Servers running on SecureTransport Servers in the secure network connect to on the SecureTransport Edge servers running in the peripheral network (DMZ). See [Communication across Transaction Manager, protocol, and proxy servers](../../../c_st_setup/c_st_networkzones).

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
         <td>22         </td>
         <td>Secure-<br/>Transport<br/>Servers         </td>
         <td>Secure-<br/>Transport<br/>Edge (FTP Server)         </td>
         <td>TCP over SSL         </td>
         <td>20021         </td>
         <td>
<img data-mc-conditions="axway_conditions.ScreenOnly" src="RightArrow_14x11.png"/>
<br/>(out-<br/>bound)         </td>
         <td>Transaction Manager streaming protocol         </td>
      </tr>
      <tr>
         <td>23         </td>
         <td>Secure-<br/>Transport<br/>Servers         </td>
         <td>Secure-<br/>Transport<br/>Edge (HTTP Server)         </td>
         <td>TCP over SSL         </td>
         <td>20080         </td>
         <td>
<img data-mc-conditions="axway_conditions.ScreenOnly" src="RightArrow_14x11.png"/>
<br/>(out-<br/>bound)         </td>
         <td>Transaction Manager streaming protocol         </td>
      </tr>
      <tr>
         <td>24         </td>
         <td>Secure-<br/>Transport<br/>Servers         </td>
         <td>Secure-<br/>Transport<br/>Edge (AS2 Server)         </td>
         <td>TCP over SSL         </td>
         <td>21080         </td>
         <td>
<img data-mc-conditions="axway_conditions.ScreenOnly" src="RightArrow_14x11.png"/>
<br/>(out-<br/>bound)         </td>
         <td>Transaction Manager streaming protocol         </td>
      </tr>
      <tr>
         <td>25         </td>
         <td>Secure-<br/>Transport<br/>Servers         </td>
         <td>Secure-<br/>Transport<br/>Edge (SSH Server)         </td>
         <td>TCP over SSL         </td>
         <td>20022         </td>
         <td>
<img data-mc-conditions="axway_conditions.ScreenOnly" src="RightArrow_14x11.png"/>
<br/>(out-<br/>bound)         </td>
         <td>Transaction Manager streaming protocol         </td>
      </tr>
      <tr>
         <td>26         </td>
         <td>Secure-<br/>Transport<br/>Servers         </td>
         <td>Secure-<br/>Transport<br/>Edge (PeSIT Server)         </td>
         <td>TCP over SSL         </td>
         <td>27617         </td>
         <td>
<img data-mc-conditions="axway_conditions.ScreenOnly" src="RightArrow_14x11.png"/>
<br/>(out-<br/>bound)         </td>
         <td>Transaction Manager streaming protocol         </td>
      </tr>
      <tr>
         <td>27         </td>
         <td>Secure-<br/>Transport<br/>Servers         </td>
         <td>Administration Tool server         </td>
         <td>TCP over SSL         </td>
         <td>20444         </td>
         <td>
<img data-mc-conditions="axway_conditions.ScreenOnly" src="RightArrow_14x11.png"/>
<br/>(out-<br/>bound)         </td>
         <td>Transaction Manager streaming protocol         </td>
      </tr>
   </tbody>
</table>

Do not define these rules in a deployment with no SecureTransport Edge. Define only the rules for the protocols you are using.

Note that in SecureTransport Edge deployment, port 20444 (used by the Administration Tool server) must always be open.

**Related topics:**

-   [Protocol rules](../r_st_protocol_rules)
-   [Authentication rules](../r_st_authentication_rules)
-   [Administration rules](../r_st_administration_rules)
-   [Server transfer rules](../r_st_server_transfer_rules)
-   [Standard Cluster rules](../r_st_standard_clustering_rules)
-   [Enterprise Cluster rules](../r_st_large_enterprise_clustering_rules)
-   [Protocol rules - outbound from SecureTransport Edge](../r_st_protocol_rules_outbound)
