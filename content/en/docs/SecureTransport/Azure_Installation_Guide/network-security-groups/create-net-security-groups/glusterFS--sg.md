{
    "title": "GlusterFS Security Group",
    "linkTitle": "GlusterFS Security Group",
    "weight": "130"
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
SecureTransport Servers
         </td>
         <td>Portmapper         </td>
      </tr>
      <tr>
         <td>GlusterFS Servers         </td>
         <td>TCP         </td>
         <td>49152-49251         </td>
         <td>GlusterFS Servers,
SecureTransport Servers 
         </td>
         <td>Each brick for every volume on your host requires its own port         </td>
      </tr>
      <tr>
         <td>GlusterFS Servers         </td>
         <td>TCP         </td>
         <td>2049         </td>
         <td>GlusterFS Servers,
SecureTransport Servers
         </td>
         <td>NFS         </td>
      </tr>
   </tbody>
</table>
