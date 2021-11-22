{
    "title": "SecureTransport Edge Security Group",
    "linkTitle": "SecureTransport Edge Security Group",
    "weight": "100"
}Allow inbound traffic according to the *Firewall rules* section as described in the .

**Inbound traffic** - this setup refers to traffic from the load balancer to the Edge serves.

-   The **Destination** is a comma separated list of {{< SecureTransport/componentshortname >}} Edge Private IPs.

> **Note:**
>
> Specifying Any for Source and the fact that the SecureTransport Edge VMs do not have a public IPs means that only the Load Balancer and VMs from the Virtual Network can access the Edges on the specified ports.

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
         <td>ST Edges         </td>
         <td>TCP         </td>
         <td>80         </td>
         <td>Any         </td>
         <td>HTTP         </td>
      </tr>
      <tr>
         <td>ST Edges         </td>
         <td>TCP         </td>
         <td>443         </td>
         <td>Any         </td>
         <td>HTTPS         </td>
      </tr>
      <tr>
         <td>ST Edges         </td>
         <td>TCP         </td>
         <td>10022         </td>
         <td>Any         </td>
         <td>SSH (SFTP and SCP)         </td>
      </tr>
      <tr>
         <td>ST Edges         </td>
         <td>TCP         </td>
         <td>21         </td>
         <td>Any         </td>
         <td>FTP (secure and non-secure) control channel (For secure connections: the firewall must allow bidirectional communication)         </td>
      </tr>
      <tr>
         <td>ST Edges         </td>
         <td>TCP         </td>
         <td>20         </td>
         <td>Any         </td>
         <td>FTP (secure and non-secure) active-mode data channel         </td>
      </tr>
      <tr>
         <td>ST Edges         </td>
         <td>TCP         </td>
         <td>User-defined range         </td>
         <td>Any         </td>
         <td>FTP (secure and non-secure) passive-mode data channel         </td>
      </tr>
      <tr>
         <td>ST Edges         </td>
         <td>TCP         </td>
         <td>10080         </td>
         <td>Any         </td>
         <td>AS2 (non-SSL)         </td>
      </tr>
      <tr>
         <td>ST Edges         </td>
         <td>TCP         </td>
         <td>10443         </td>
         <td>Any         </td>
         <td>AS2 (SSL)         </td>
      </tr>
      <tr>
         <td>ST Edges         </td>
         <td>TCP         </td>
         <td>17617         </td>
         <td>Any         </td>
         <td>PeSIT (non-SSL)         </td>
      </tr>
      <tr>
         <td>ST Edges         </td>
         <td>TCP         </td>
         <td>17627         </td>
         <td>Any         </td>
         <td>PeSIT over secure socket (Transfer CFT compatible)         </td>
      </tr>
      <tr>
         <td>ST Edges         </td>
         <td>TCP         </td>
         <td>17637         </td>
         <td>Any         </td>
         <td>PeSIT over secure socket (CFT compatible)         </td>
      </tr>
      <tr>
         <td>ST Edges         </td>
         <td>TCP         </td>
         <td>19617         </td>
         <td>Any         </td>
         <td>PeSIT over pTCP plain socket         </td>
      </tr>
      <tr>
         <td>ST Edges         </td>
         <td>TCP         </td>
         <td>19627         </td>
         <td>Any         </td>
         <td>PeSIT over pTCP Secured Socket         </td>
      </tr>
   </tbody>
</table>

**Streaming** – refers to traffic from the ST servers to the Edge serves.

-   The **Destination** is a comma separated list of {{< SecureTransport/componentshortname >}} Edge Private IP addresses.
-   The **Source** is comma separated list of {{< SecureTransport/componentshortname >}} Server Private IP addresses.

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
         <td>ST Edges         </td>
         <td>TCP         </td>
         <td>20080         </td>
         <td>SecureTransport Servers         </td>
         <td>Streaming HTTP Server         </td>
      </tr>
      <tr>
         <td>ST Edges         </td>
         <td>TCP         </td>
         <td>20022         </td>
         <td>SecureTransport Servers         </td>
         <td>Streaming SSH Server         </td>
      </tr>
      <tr>
         <td>ST Edges         </td>
         <td>TCP         </td>
         <td>20021         </td>
         <td>SecureTransport Servers         </td>
         <td>Streaming FTP Server         </td>
      </tr>
      <tr>
         <td>ST Edges         </td>
         <td>TCP         </td>
         <td>21080         </td>
         <td>SecureTransport Servers         </td>
         <td>Streaming AS2 Server         </td>
      </tr>
      <tr>
         <td>ST Edges         </td>
         <td>TCP         </td>
         <td>20444         </td>
         <td>SecureTransport Servers         </td>
         <td>Streaming Administration Tool Server         </td>
      </tr>
      <tr>
         <td>ST Edges         </td>
         <td>TCP         </td>
         <td>27617         </td>
         <td>SecureTransport Servers         </td>
         <td>Streaming PeSIT Server         </td>
      </tr>
   </tbody>
</table>

**Internal communication** – refers to traffic between the Edge serves and traffic from the Administration host.

-   The **Destination** is a comma separated list of {{< SecureTransport/componentshortname >}} Edge Private IP addresses.

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
         <td>ST Edges         </td>
         <td>TCP         </td>
         <td>33060         </td>
         <td>Administration Host Private IP         </td>
         <td>Database Administration         </td>
      </tr>
      <tr>
         <td>ST Edges         </td>
         <td>TCP         </td>
         <td>33060         </td>
         <td>SecureTransport Edges         </td>
         <td>MariaDB or MySQL communication         </td>
      </tr>
      <tr>
         <td>ST Edges         </td>
         <td>TCP         </td>
         <td>22         </td>
         <td>Administration Host Private IP         </td>
         <td>SSH for Administration         </td>
      </tr>
      <tr>
         <td>ST Edges         </td>
         <td>TCP         </td>
         <td>444         </td>
         <td>Administration Host Private IP         </td>
         <td>Administration Tool (HTTPS)         </td>
      </tr>
      <tr>
         <td>ST Edges         </td>
         <td>TCP         </td>
         <td>444         </td>
         <td>SecureTransport Edges         </td>
         <td>Cluster Synchronization         </td>
      </tr>
      <tr>
         <td>ST Edges         </td>
         <td>TCP         </td>
         <td>8005         </td>
         <td>SecureTransport Edges         </td>
         <td>Tomcat shutdown         </td>
      </tr>
      <tr>
         <td>ST Edges         </td>
         <td>TCP         </td>
         <td>8006         </td>
         <td>SecureTransport Edges         </td>
         <td>AS2 shutdown         </td>
      </tr>
      <tr>
         <td>ST Edges         </td>
         <td>TCP         </td>
         <td>7800-7802         </td>
         <td>SecureTransport Edges         </td>
         <td>Hibernate second level cache         </td>
      </tr>
   </tbody>
</table>

 
