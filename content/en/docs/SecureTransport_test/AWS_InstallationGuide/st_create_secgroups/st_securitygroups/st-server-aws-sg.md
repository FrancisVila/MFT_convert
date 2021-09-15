{
    "title": "SecureTransport Server Security Group",
    "linkTitle": "SecureTransport Server Security Group",
    "weight": "120"
}## SecureTransport Server Security Group

Allow inbound traffic according to the *Firewall rules* section as described in the SecureTransport 5.5 *Administrator's Guide*.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Inbound traffic from 8088-8093 range should be allowed for both TCP and UDP protocols from one SecureTransport Server to another (SecureTransport Server Security Group).         </td>
      </tr>
</table>

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
            <p>Custom TCP Rule</p>
         </td>
         <td>
            <p>TCP</p>
         </td>
         <td>
            <p>162</p>
         </td>
         <td>
            <p>SecureTransport Server Security Group</p>
         </td>
         <td>
            <p>SNMP</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Custom UDP Rule</p>
         </td>
         <td>
            <p>TCP</p>
         </td>
         <td>
            <p>8088-8093</p>
         </td>
         <td>
            <p>SecureTransport Server Security Group</p>
         </td>
         <td>
            <p>Cluster cache management</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Custom UDP Rule</p>
         </td>
         <td>
            <p>UDP</p>
         </td>
         <td>
            <p>8088-8093</p>
         </td>
         <td>
            <p>SecureTransport Server Security Group</p>
         </td>
         <td>
            <p>Cluster cache management</p>
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
            <p>444</p>
         </td>
         <td>
            <p>Administration Host Security Group</p>
         </td>
         <td>
            <p>Administration Tool (HTTPS)</p>
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
            <p>44431</p>
         </td>
         <td>
            <p>SecureTransport Server Security Group</p>
         </td>
         <td>
            <p>Cluster Listener</p>
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
            <p>9999</p>
         </td>
         <td>
            <p>SecureTransport Server Security Group</p>
         </td>
         <td>
            <p>TM JMX Port</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Custom ICMP Rule</p>
         </td>
         <td>
            <p>IPv4</p>
         </td>
         <td>
            <p>Echo Reply</p>
         </td>
         <td>
            <p>SecureTransport Server Security Group</p>
         </td>
         <td>
            <p>Echo Reply</p>
         </td>
      </tr>
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
            <p>SSH for Administration</p>
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
            <p>8005</p>
         </td>
         <td>
            <p>SecureTransport Server Security Group</p>
         </td>
         <td>
            <p>Tomcat shutdown port</p>
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
            <p>8009</p>
         </td>
         <td>
            <p>SecureTransport Server Security Group</p>
         </td>
         <td>
            <p>Tomcat JK connector</p>
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
            <p>20444</p>
         </td>
         <td>
            <p>SecureTransport Server Security Group</p>
         </td>
         <td>
            <p>Administration Tool</p>
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
            <p>7</p>
         </td>
         <td>
            <p>SecureTransport Server Security Group</p>
         </td>
         <td>
            <p>Coherence</p>
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
            <p>7800-7802</p>
         </td>
         <td>
            <p>SecureTransport Server Security Group</p>
         </td>
         <td>
            <p>Hibernate second-level cache</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Custom ICMP Rule</p>
         </td>
         <td>
            <p>IPv4</p>
         </td>
         <td>
            <p>Echo Request</p>
         </td>
         <td>
            <p>SecureTransport Server Security Group</p>
         </td>
         <td>
            <p>Echo Request</p>
         </td>
      </tr>
   </tbody>
</table>
