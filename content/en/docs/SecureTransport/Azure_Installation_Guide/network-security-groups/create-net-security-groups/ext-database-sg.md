{
    "title": "External Database Security Group",
    "linkTitle": "External Database Security Group",
    "weight": "120"
}Allow the following inbound traffic:

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Type</th>
         <th>Protocol</th>
         <th>Port / Port Range</th>
         <th>Source</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Database VM Private IP         </td>
         <td>Any         </td>
         <td>1433         </td>
         <td>Administration Host Private IP,
SecureTransport Servers 
         </td>
         <td>Access to the database         </td>
      </tr>
      <tr>
         <td>Database VM Private IP         </td>
         <td>Any         </td>
         <td>3389         </td>
         <td>Administration Host Private IP         </td>
         <td>RDP access to the database VM         </td>
      </tr>
   </tbody>
</table>
