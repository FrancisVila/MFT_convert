{
    "title": "Parameter equivalents in Central Governance",
    "linkTitle": "Parameter equivalents in Central Governance",
    "weight": "300"
}<table>
   <th>
      <tr>
<th>CG field         </th>
<th>CG values         </th>
<th><p>CFTUTIL </p>
<p>parameter</p>         </th>
<th>Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Maximum simultaneous transfers         </td>
         <td><p>Linux and Windows: 2-1000 (<u>128</u>)</p>
<p>z/OS and IBM i: 2-990 (<u>128</u>)</p>         </td>
         <td>MAXTRANS         </td>
         <td>The maximum number of simultaneous connections that <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> accepts to establish for a network resource.         </td>
      </tr>
      <tr>
         <td>Connections         </td>
         <td>1-2000
(128)         </td>
         <td>MAXCNX         </td>
         <td>The maximum number of simultaneous connections that
Transfer CFT accepts to establish on a given network
resource.         </td>
      </tr>
      <tr>
         <td>Disconnect timeout         </td>
         <td>0-3600 (60)         </td>
         <td>DISCTR, DISCTC         </td>
         <td>The wait timeout for either a response to the protocol connection request or to the partner in the connection, before disconnecting.         </td>
      </tr>
   </tbody>
</table>

Related topics

-   [About parallel transfers](../)
-   [FAQ and troubleshooting](../faq)
