{
    "title": "GlusterFS Security Group",
    "linkTitle": "GlusterFS Security Group",
    "weight": "130"
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
         <td>GlusterFS Servers         </td>
         <td>SSH         </td>
         <td>22         </td>
         <td>Administration Host Private IP         </td>
         <td>Administration Host Security Group         </td>
      </tr>
      <tr>
         <td>GlusterFS Servers         </td>
         <td>TCP         </td>
         <td>24007         </td>
         <td>GlusterFS Servers, SecureTransport Servers         </td>
         <td>Gluster Daemon         </td>
      </tr>
      <tr>
         <td>GlusterFS Servers         </td>
         <td>TCP         </td>
         <td>111         </td>
         <td>GlusterFS Servers,
SecureTransport Servers         </td>
         <td>Portmapper         </td>
      </tr>
      <tr>
         <td>GlusterFS Servers         </td>
         <td>TCP         </td>
         <td>49152-49251         </td>
         <td>GlusterFS Servers,
SecureTransport Servers         </td>
         <td>Each brick for every volume on your host requires its own port         </td>
      </tr>
      <tr>
         <td>GlusterFS Servers         </td>
         <td>TCP         </td>
         <td>2049         </td>
         <td>GlusterFS Servers,
SecureTransport Servers         </td>
         <td>NFS         </td>
      </tr>
   </tbody>
</table>
