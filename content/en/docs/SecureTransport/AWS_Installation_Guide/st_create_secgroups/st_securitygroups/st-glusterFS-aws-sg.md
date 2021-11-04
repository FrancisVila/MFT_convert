{
    "title": "GlusterFS Security Group",
    "linkTitle": "GlusterFS Security Group",
    "weight": "140"
}## GlusterFS Security Group

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
         <td><p>SSH</p>         </td>
         <td><p>SSH</p>         </td>
         <td><p>22</p>         </td>
         <td><p>Administration Host Security Group</p>         </td>
         <td><p>Administration Host Security Group</p>         </td>
      </tr>
      <tr>
         <td><p>Custom TCP Rule</p>         </td>
         <td><p>TCP</p>         </td>
         <td><p>24007</p>         </td>
         <td><p>GlusterFS Security Group</p>
<p>SecureTransport Server Security Group</p>         </td>
         <td><p>Gluster Daemon</p>         </td>
      </tr>
      <tr>
         <td><p>Custom TCP Rule</p>         </td>
         <td><p>TCP</p>         </td>
         <td><p>111</p>         </td>
         <td><p>GlusterFS Security Group</p>
<p>SecureTransport Server Security Group</p>         </td>
         <td><p>Portmapper</p>         </td>
      </tr>
      <tr>
         <td><p>Custom TCP Rule</p>         </td>
         <td><p>TCP</p>         </td>
         <td><p>49152-49251</p>         </td>
         <td><p>GlusterFS Security Group</p>
<p>SecureTransport Server Security Group</p>         </td>
         <td><p>Each brick for every volume on your host requires its own port</p>         </td>
      </tr>
      <tr>
         <td><p>Custom TCP Rule</p>         </td>
         <td><p>TCP</p>         </td>
         <td><p>2049</p>         </td>
         <td><p>GlusterFS Security Group</p>
<p>SecureTransport Server Security Group</p>         </td>
         <td><p>NFS</p>         </td>
      </tr>
   </tbody>
</table>
