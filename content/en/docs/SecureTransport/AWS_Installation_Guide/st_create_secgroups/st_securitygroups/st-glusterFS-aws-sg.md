{
    "title": "GlusterFS Security Group",
    "linkTitle": "GlusterFS Security Group",
    "weight": "140"
}## GlusterFS Security Group

Allow the following inbound traffic:

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
         <th>Port or Port Range</th>
         <th>Source</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p>SSH</p>
         </td>
         <td>
            <p>SSH</p>
         </td>
         <td>
            <p>22</p>
         </td>
         <td>
            <p>Administration Host Security Group</p>
         </td>
         <td>
            <p>Administration Host Security Group</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Custom TCP Rule</p>
         </td>
         <td>
            <p>TCP</p>
         </td>
         <td>
            <p>24007</p>
         </td>
         <td>
            <p>GlusterFS Security Group</p>
            <p>SecureTransport Server Security Group</p>
         </td>
         <td>
            <p>Gluster Daemon</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Custom TCP Rule</p>
         </td>
         <td>
            <p>TCP</p>
         </td>
         <td>
            <p>111</p>
         </td>
         <td>
            <p>GlusterFS Security Group</p>
            <p>SecureTransport Server Security Group</p>
         </td>
         <td>
            <p>Portmapper</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Custom TCP Rule</p>
         </td>
         <td>
            <p>TCP</p>
         </td>
         <td>
            <p>49152-49251</p>
         </td>
         <td>
            <p>GlusterFS Security Group</p>
            <p>SecureTransport Server Security Group</p>
         </td>
         <td>
            <p>Each brick for every volume on your host requires its own port</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Custom TCP Rule</p>
         </td>
         <td>
            <p>TCP</p>
         </td>
         <td>
            <p>2049</p>
         </td>
         <td>
            <p>GlusterFS Security Group</p>
            <p>SecureTransport Server Security Group</p>
         </td>
         <td>
            <p>NFS</p>
         </td>
      </tr>
   </tbody>
</table>
