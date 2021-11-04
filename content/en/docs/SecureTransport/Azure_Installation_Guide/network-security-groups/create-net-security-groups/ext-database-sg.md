{
    "title": "External Database Security Group",
    "linkTitle": "External Database Security Group",
    "weight": "120"
}Allow the following inbound traffic:

<table>
         
         
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Type         </th>
<th style="text-align: left;" class="HeadE-Column1-Header1">Protocol         </th>
<th class="HeadE-Column1-Header1">Port / Port Range         </th>
<th class="HeadE-Column1-Header1">Source         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Database VM Private IP         </td>
         <td>Any         </td>
         <td>1433         </td>
         <td>Administration Host Private IP,
SecureTransport Servers         </td>
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
