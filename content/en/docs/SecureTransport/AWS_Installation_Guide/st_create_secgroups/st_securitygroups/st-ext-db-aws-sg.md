{
    "title": "External Database Security Group",
    "linkTitle": "External Database Security Group",
    "weight": "130"
}## External Database Security Group

Allow the following inbound traffic:

<table>
         
         
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Type         </th>
<th class="HeadE-Column1-Header1">Protocol         </th>
<th class="HeadE-Column1-Header1">Port or Port Range         </th>
<th class="HeadE-Column1-Header1">Source         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Oracle</p>         </td>
         <td><p>RDS</p>         </td>
         <td><p>1521</p>         </td>
         <td><p>Administration Host Security Group</p>
<p>SecureTransport Server Security Group</p>         </td>
         <td><p>Non-SSL access to the database</p>         </td>
      </tr>
      <tr>
         <td>PostgreSQL         </td>
         <td>RDS         </td>
         <td>5432         </td>
         <td>SecureTransport
Server Security
Group         </td>
         <td>Non-SSL access to the database         </td>
      </tr>
      <tr>
         <td><p>Custom TCP Rule</p>         </td>
         <td><p>TCP</p>         </td>
         <td><p>2484</p>         </td>
         <td><p>Administration Host Security Group</p>
<p>SecureTransport Server Security Group</p>         </td>
         <td><p>SSL access to the database</p>         </td>
      </tr>
   </tbody>
</table>
