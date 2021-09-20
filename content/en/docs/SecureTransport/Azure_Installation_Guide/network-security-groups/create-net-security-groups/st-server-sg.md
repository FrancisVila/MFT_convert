{
    "title": "SecureTransport Server Security Group",
    "linkTitle": "SecureTransport Server Security Group",
    "weight": "110"
}Allow inbound traffic according to the *Firewall rules* section as described in the SecureTransport 5.5 *Administrator's Guide*.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Inbound traffic from 8088-8093 range should be allowed for both TCP and UDP protocols from one <span>SecureTransport</span> Server to another (<span>SecureTransport</span> Server Security Group).         </td>
      </tr>
</table>

-   The **Destination** is a comma separated list of SecureTransport Edge Private IPs.
-   The **Source** is comma separated list of SecureTransport Edge Private IPs.

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
         <td>SecureTransport Servers         </td>
         <td>TCP         </td>
         <td>80         </td>
         <td>SecureTransport Servers         </td>
         <td>SNMP         </td>
      </tr>
      <tr>
         <td>SecureTransport Servers         </td>
         <td>TCP         </td>
         <td>443         </td>
         <td>SecureTransport Servers         </td>
         <td>Cluster cache management         </td>
      </tr>
      <tr>
         <td>SecureTransport Servers         </td>
         <td>UDP         </td>
         <td>10022         </td>
         <td>SecureTransport Servers         </td>
         <td>Cluster cache management         </td>
      </tr>
      <tr>
         <td>SecureTransport Servers         </td>
         <td>TCP         </td>
         <td>444         </td>
         <td>Administration Host Private IP         </td>
         <td>Administration Tool (HTTPS)         </td>
      </tr>
      <tr>
         <td>SecureTransport Servers         </td>
         <td>TCP         </td>
         <td>44431         </td>
         <td>SecureTransport Servers         </td>
         <td>Cluster Listener         </td>
      </tr>
      <tr>
         <td>SecureTransport Servers         </td>
         <td>TCP         </td>
         <td>9999         </td>
         <td>SecureTransport Servers         </td>
         <td>TM JMX Port         </td>
      </tr>
      <tr>
         <td>SecureTransport Servers         </td>
         <td>SSH         </td>
         <td>22         </td>
         <td>SecureTransport Servers         </td>
         <td>SSH for Administration         </td>
      </tr>
      <tr>
         <td>SecureTransport Servers         </td>
         <td>TCP         </td>
         <td>8005         </td>
         <td>SecureTransport Servers         </td>
         <td>Tomcat shutdown port         </td>
      </tr>
      <tr>
         <td>SecureTransport Servers         </td>
         <td>TCP         </td>
         <td>8009         </td>
         <td>SecureTransport Servers         </td>
         <td>Tomcat JK connector         </td>
      </tr>
      <tr>
         <td>SecureTransport Servers         </td>
         <td>TCP         </td>
         <td>20444         </td>
         <td>SecureTransport Servers         </td>
         <td>Administration Tool         </td>
      </tr>
      <tr>
         <td>SecureTransport Servers         </td>
         <td>TCP         </td>
         <td>7         </td>
         <td>SecureTransport Servers         </td>
         <td>Coherence         </td>
      </tr>
      <tr>
         <td>SecureTransport Servers         </td>
         <td>TCP         </td>
         <td>7800-7802         </td>
         <td>SecureTransport Servers         </td>
         <td>Hibernate second-level cache         </td>
      </tr>
      <tr>
         <td>SecureTransport Servers         </td>
         <td>TCP         </td>
         <td>*         </td>
         <td>Any         </td>
         <td>Deny all TCP Traffic         </td>
      </tr>
      <tr>
         <td>SecureTransport Servers         </td>
         <td>UDP         </td>
         <td>*         </td>
         <td>Any         </td>
         <td>Deny all UDP traffic         </td>
      </tr>
      <tr>
         <td>SecureTransport Servers         </td>
         <td>Any         </td>
         <td>*         </td>
         <td>SecureTransport Servers         </td>
         <td>Allow all ICMP traffic for Cluster communication          </td>
      </tr>
   </tbody>
</table>

SecureTransport Server nodes communicate via ICMP protocol which is not available for selection as a separate Protocol. If we want to enable it, we must enable the traffic for all protocols which we do not prefer. So, we create two rules that deny all TCP and UDP traffic on all ports with lower priority than the above rules. The rule with the lowest priority allows traffic on all protocols and ports. This means that only the ICMP traffic will be allowed.