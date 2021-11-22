{
    "title": "SecureTransport Edge Security Group",
    "linkTitle": "SecureTransport Edge Security Group",
    "weight": "110"
}## SecureTransport Edge Security Group

Allow inbound traffic according to the *Firewall rules* section as described in the .

-   **Inbound traffic** – this setup refers to traffic from the load balancer to the Edge serves.  

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
         <td>HTTP         </td>
         <td>TCP         </td>
         <td>80         </td>
         <td>Load Balancer Security Group         </td>
         <td>HTTP         </td>
      </tr>
      <tr>
         <td>HTTPS         </td>
         <td>TCP         </td>
         <td>443         </td>
         <td>Load Balancer Security Group         </td>
         <td>HTTPS         </td>
      </tr>
      <tr>
         <td>Custom TCP Rule         </td>
         <td>TCP         </td>
         <td>10022         </td>
         <td>Load Balancer Security Group         </td>
         <td>SSH (SFTP and SCP)         </td>
      </tr>
      <tr>
         <td>Custom TCP Rule         </td>
         <td>TCP         </td>
         <td>21         </td>
         <td>Load Balancer Security Group         </td>
         <td>FTP (secure and non-secure) control channel (For secure connections: the firewall mustallow bidirectional communication)         </td>
      </tr>
      <tr>
         <td>Custom TCP Rule         </td>
         <td>TCP         </td>
         <td>20         </td>
         <td>Load Balancer Security Group         </td>
         <td>FTP (secure and non-secure) active-mode data channel         </td>
      </tr>
      <tr>
         <td>Custom TCP Rule         </td>
         <td>TCP         </td>
         <td>User-defined range         </td>
         <td>Load Balancer Security Group         </td>
         <td>FTP (secure and non-secure) passive-mode data channel         </td>
      </tr>
      <tr>
         <td>Custom TCP Rule         </td>
         <td>TCP         </td>
         <td>10080         </td>
         <td>Load Balancer Security Group         </td>
         <td>AS2(non-SSL)         </td>
      </tr>
      <tr>
         <td>Custom TCP Rule         </td>
         <td>TCP         </td>
         <td>10443         </td>
         <td>Load Balancer Security Group         </td>
         <td>AS2 (SSL)         </td>
      </tr>
      <tr>
         <td>Custom TCP Rule         </td>
         <td>TCP         </td>
         <td>17617         </td>
         <td>Load Balancer Security Group         </td>
         <td>PeSIT (non-SSL)         </td>
      </tr>
      <tr>
         <td>Custom TCP Rule         </td>
         <td>TCP         </td>
         <td>17627         </td>
         <td>Load Balancer Security Group         </td>
         <td>PeSIT over secure socket (non-Transfer CFT compatible)         </td>
      </tr>
      <tr>
         <td>Custom TCP Rule         </td>
         <td>TCP         </td>
         <td>17637         </td>
         <td>Load Balancer Security Group         </td>
         <td>PeSIT over secure socket (CFT compatible)         </td>
      </tr>
      <tr>
         <td>Custom TCP Rule         </td>
         <td>TCP         </td>
         <td>19617         </td>
         <td>Load Balancer Security Group         </td>
         <td>PeSIT over pTCP plain socket         </td>
      </tr>
      <tr>
         <td>Custom TCP Rule         </td>
         <td>TCP         </td>
         <td>19627         </td>
         <td>Load Balancer Security Group         </td>
         <td>PeSIT over pTCP Secured Socket         </td>
      </tr>
   </tbody>
</table>

-   **Streaming** – this setup refers to traffic from the ST servers to the Edge serves.

<table>
         
         
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Type         </th>
<th class="HeadE-Column1-Header1">Protocol         </th>
<th class="HeadE-Column1-Header1">Port / Range         </th>
<th class="HeadE-Column1-Header1">Source         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Custom TCP Rule         </td>
         <td>TCP         </td>
         <td>20080         </td>
         <td>SecureTransport Server Security Group         </td>
         <td>Streaming HTTP Server         </td>
      </tr>
      <tr>
         <td>Custom TCP Rule         </td>
         <td>TCP         </td>
         <td>20022         </td>
         <td>SecureTransport Server Security Group         </td>
         <td>Streaming SSH Server         </td>
      </tr>
      <tr>
         <td>Custom TCP Rule         </td>
         <td>TCP         </td>
         <td>20021         </td>
         <td>SecureTransport Server Security Group         </td>
         <td>Streaming FTP Server         </td>
      </tr>
      <tr>
         <td>Custom TCP Rule         </td>
         <td>TCP         </td>
         <td>21080         </td>
         <td>SecureTransport Server Security Group         </td>
         <td>Streaming AS2 Server         </td>
      </tr>
      <tr>
         <td>Custom TCP Rule         </td>
         <td>TCP         </td>
         <td>20444         </td>
         <td>SecureTransport Server Security Group         </td>
         <td>Streaming Administration Tool Server         </td>
      </tr>
      <tr>
         <td>Custom TCP Rule         </td>
         <td>TCP         </td>
         <td>27617         </td>
         <td>SecureTransport Server Security Group         </td>
         <td>Streaming PeSIT Server         </td>
      </tr>
   </tbody>
</table>

-   **Internal communication** – refers to traffic between the Edge serves and traffic from the Administration host.

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
         <td><p>Custom TCP Rule</p>         </td>
         <td><p>TCP</p>         </td>
         <td><p>33060</p>         </td>
         <td><p>Administration Host SG</p>         </td>
         <td><p>Database Administration</p>         </td>
      </tr>
      <tr>
         <td><p>Custom TCP Rule</p>         </td>
         <td><p>TCP</p>         </td>
         <td><p>33060</p>         </td>
         <td><p>SecureTransport Edge SG</p>         </td>
         <td><p>MariaDB or MySQL communication</p>         </td>
      </tr>
      <tr>
         <td><p>Custom TCP Rule</p>         </td>
         <td><p>TCP</p>         </td>
         <td><p>22</p>         </td>
         <td><p>Administration Host Security Group</p>         </td>
         <td><p>SSH for Administration</p>         </td>
      </tr>
      <tr>
         <td><p>Custom TCP Rule</p>         </td>
         <td><p>TCP</p>         </td>
         <td><p>444</p>         </td>
         <td><p>Administration Host Security Group</p>         </td>
         <td><p>Administration Tool (HTTPS)</p>         </td>
      </tr>
      <tr>
         <td><p>Custom TCP Rule</p>         </td>
         <td><p>TCP</p>         </td>
         <td><p>444</p>         </td>
         <td><p>SecureTransport Edge Security Group</p>         </td>
         <td><p>Cluster Synchronization</p>         </td>
      </tr>
      <tr>
         <td><p>Custom TCP Rule</p>         </td>
         <td><p>TCP</p>         </td>
         <td><p>8005</p>         </td>
         <td><p>SecureTransport Edge Security Group</p>         </td>
         <td><p>Tomcat shutdown</p>         </td>
      </tr>
      <tr>
         <td><p>Custom TCP Rule</p>         </td>
         <td><p>TCP</p>         </td>
         <td><p>8006</p>         </td>
         <td><p>SecureTransport Edge Security Group</p>         </td>
         <td><p>AS2 shutdown</p>         </td>
      </tr>
      <tr>
         <td><p>Custom TCP Rule</p>         </td>
         <td><p>TCP</p>         </td>
         <td><p>7800-7802</p>         </td>
         <td><p>SecureTransport Edge SG</p>         </td>
         <td><p>Hibernate second level cache</p>         </td>
      </tr>
   </tbody>
</table>
