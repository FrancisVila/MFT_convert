{
    "title": "TCP port availability ",
    "linkTitle": "TCP port availability",
    "weight": "290"
}This page lists the various <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> ports used for communication between processes, for both single and multi-node installations, which can be used for health checks or transfer-related operations.

## Single node deployment

<table>
   <th>
      <tr>
<th>Usage         </th>
<th>Process         </th>
<th>Configurable         </th>
<th>Configuration Parameter         </th>
<th>Network Interface         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Listening port for file transfer protocol         </td>
         <td>CFTTCPS         </td>
         <td>Yes         </td>
         <td>CFTPROT:SAP         </td>
         <td>See CFTNET:HOST         </td>
      </tr>
      <tr>
         <td>Listening port for Synchronous Communication Media         </td>
         <td>CFTTCOMS         </td>
         <td>Yes         </td>
         <td>CFTCOM:PORT         </td>
         <td>See CFTCOM:HOST         </td>
      </tr>
      <tr>
         <td>Inter-process communication         </td>
         <td>CFTPRX         </td>
         <td>No         </td>
         <td>N/A: port provided by the operating system         </td>
         <td>127.0.0.1         </td>
      </tr>
      <tr>
         <td>Copilot inter-process communication         </td>
         <td>copsmng         </td>
         <td>No         </td>
         <td>N/A: port provided by the operating system         </td>
         <td>127.0.0.1         </td>
      </tr>
      <tr>
         <td>Copilot Web server         </td>
         <td>copui         </td>
         <td>Yes         </td>
         <td>copilot.general.serverport          </td>
         <td>copilot.general.serverhost         </td>
      </tr>
      <tr>
         <td>Copilot Web server for Central Governance / Flow Manager         </td>
         <td>copui         </td>
         <td>Yes         </td>
         <td>copilot.general.ssl_serverport          </td>
         <td>copilot.general.serverhost         </td>
      </tr>
      <tr>
         <td>Copilot Web server inter-process communication         </td>
         <td>copsproc         </td>
         <td>No         </td>
         <td>N/A: port provided by the operating system         </td>
         <td>127.0.0.1         </td>
      </tr>
      <tr>
         <td>Copilot REST API Web server         </td>
         <td>coprests         </td>
         <td>Yes         </td>
         <td>copilot.restapi.serverport         </td>
         <td>copilot.general.serverhost         </td>
      </tr>
      <tr>
         <td>Secure Relay Master Agent         </td>
         <td>masteragent.jar         </td>
         <td>Yes         </td>
         <td>secure_relay.ma.comm_port         </td>
         <td>secure_relay.ma.host         </td>
      </tr>
      <tr>
         <td>Secure Relay heartbeat service         </td>
         <td>CFTPRX         </td>
         <td>Yes         </td>
         <td>secure_relay.ma.heartbeat_service.port         </td>
         <td>secure_relay.ma.heartbeat_service.host         </td>
      </tr>
   </tbody>
</table>

## Multi-node deployment

<table>
   <th>
      <tr>
<th>Usage         </th>
<th>Process         </th>
<th>Configurable         </th>
<th>Configuration Parameter         </th>
<th>Network Interface         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Listening port for Synchronous Communication Media         </td>
         <td>copcoms         </td>
         <td>Yes         </td>
         <td>CFTCOM:PORT         </td>
         <td>See CFTCOM:HOST         </td>
      </tr>
      <tr>
         <td>Listening port for Synchronous Communication Media         </td>
         <td>CFTTCOMS         </td>
         <td>Yes         </td>
         <td>cft.multi_node.listen_port_range         </td>
         <td>0.0.0.0         </td>
      </tr>
      <tr>
         <td>Inter-node communication for transfer recovery         </td>
         <td>CFTPRX         </td>
         <td>Yes         </td>
         <td>cft.multi_node.listen_port_range         </td>
         <td>0.0.0.0         </td>
      </tr>
      <tr>
         <td>Copilot inter-process communication         </td>
         <td>copsmng         </td>
         <td>No         </td>
         <td>N/A: port provided by the operating system         </td>
         <td>127.0.0.1         </td>
      </tr>
      <tr>
         <td>Copilot Web server         </td>
         <td>copui         </td>
         <td>Yes         </td>
         <td>copilot.general.serverport          </td>
         <td>copilot.general.serverhost         </td>
      </tr>
      <tr>
         <td>Copilot Web server for Central Governance / Flow Manager         </td>
         <td>copui         </td>
         <td>Yes         </td>
         <td>copilot.general.ssl_serverport          </td>
         <td>copilot.general.serverhost         </td>
      </tr>
      <tr>
         <td>Copilot Web server inter-process communication         </td>
         <td>copsproc         </td>
         <td>No         </td>
         <td>N/A: port provided by the operating system         </td>
         <td>127.0.0.1         </td>
      </tr>
      <tr>
         <td>Copilot REST API Web server         </td>
         <td>coprests         </td>
         <td>Yes         </td>
         <td>copilot.restapi.serverport         </td>
         <td>copilot.general.serverhost         </td>
      </tr>
      <tr>
         <td>Node manager inter-process communication         </td>
         <td>copnman         </td>
         <td>Yes         </td>
         <td>cft.multi_node.listen_port_range         </td>
         <td>0.0.0.0         </td>
      </tr>
      <tr>
         <td>Connection Dispatcher local port (Windows, z/OS only)         </td>
         <td>copcod         </td>
         <td>Yes         </td>
         <td>copilot.connection_dispatcher.local_port         </td>
         <td>127.0.0.1         </td>
      </tr>
      <tr>
         <td>Secure Relay Master Agent         </td>
         <td>masteragent.jar         </td>
         <td>Yes         </td>
         <td>secure_relay.ma.comm_port + node_number         </td>
         <td>secure_relay.ma.host         </td>
      </tr>
      <tr>
         <td>Secure Relay heartbeat service         </td>
         <td>CFTPRX         </td>
         <td>Yes         </td>
         <td>secure_relay.ma.heartbeat_service.port         </td>
         <td>secure_relay.ma.heartbeat_service.host         </td>
      </tr>
   </tbody>
</table>
