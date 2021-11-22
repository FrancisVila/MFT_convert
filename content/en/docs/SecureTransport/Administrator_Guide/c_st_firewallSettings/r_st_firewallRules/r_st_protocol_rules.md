{
    "title": "Protocol rules",
    "linkTitle": "Protocol rules",
    "weight": "300"
}<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">#         </th>
<th class="HeadE-Column1-Header1">Group<br />
source         </th>
<th class="HeadE-Column1-Header1">Group destination         </th>
<th class="HeadE-Column1-Header1">Protocol         </th>
<th class="HeadE-Column1-Header1">Destination port         </th>
<th class="HeadE-Column1-Header1">Direction         </th>
<th class="HeadD-Column1-Header1">Purpose         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>1         </td>
         <td>Internet         </td>
         <td>Secure-<br />
Transport<br />
Edge Virtual IP (load balancer)         </td>
         <td>FTP(S)         </td>
         <td>21         </td>
         <td><img src="/Images/SecureTransport/LeftArrow_14x11.png" /><br />
(in-<br />
bound)         </td>
         <td>Client FTP(S) control channel         </td>
      </tr>
      <tr>
         <td>2         </td>
         <td>Internet         </td>
         <td>Secure-<br />
Transport<br />
Edge Virtual IP (load balancer)         </td>
         <td>FTP(S)         </td>
         <td>1024 to 65535 (Actual port range is specified on the Remote Server.)         </td>
         <td><img src="/Images/SecureTransport/RightArrow_14x11.png" /><br />
(out-<br />
bound)         </td>
         <td>Client FTP(S) data channel, active mode         </td>
      </tr>
      <tr>
         <td>3         </td>
         <td>Internet         </td>
         <td>Secure-<br />
Transport<br />
Edge Virtual IP (load balancer)         </td>
         <td>FTP(S)         </td>
         <td>1024 to 65535 (Actual port range is specified on the Edge.)         </td>
         <td><img src="/Images/SecureTransport/LeftArrow_14x11.png" /><br />
(in-<br />
bound)         </td>
         <td>Client FTP(S) data channel, active mode         </td>
      </tr>
      <tr>
         <td>4         </td>
         <td>Internet         </td>
         <td>Secure-<br />
Transport<br />
Edge Virtual IP (load balancer)         </td>
         <td>HTTP         </td>
         <td>80         </td>
         <td><img src="/Images/SecureTransport/LeftArrow_14x11.png" /><br />
(in-<br />
bound)         </td>
         <td>Client web access<br />
(non-secure)         </td>
      </tr>
      <tr>
         <td>5         </td>
         <td>Internet         </td>
         <td>Secure-<br />
Transport<br />
Edge Virtual IP (load balancer)         </td>
         <td>HTTPS         </td>
         <td>443         </td>
         <td><img src="/Images/SecureTransport/LeftArrow_14x11.png" /><br />
(in-<br />
bound)         </td>
         <td>Client web access (secure)         </td>
      </tr>
      <tr>
         <td>6         </td>
         <td>Internet         </td>
         <td>Secure-<br />
Transport<br />
Edge Virtual IP (load balancer)         </td>
         <td>SSH         </td>
         <td>22         </td>
         <td><img src="/Images/SecureTransport/LeftArrow_14x11.png" /><br />
(in-<br />
bound)         </td>
         <td>Client SSH access         </td>
      </tr>
      <tr>
         <td>7         </td>
         <td>Internet         </td>
         <td>Secure-<br />
Transport<br />
Edge Virtual IP (load balancer)         </td>
         <td>AS2 (SSL)         </td>
         <td>10443         </td>
         <td><img src="/Images/SecureTransport/LeftArrow_14x11.png" /><br />
(in-<br />
bound)         </td>
         <td>Partner AS2 access (secure)         </td>
      </tr>
      <tr>
         <td>8         </td>
         <td>Internet         </td>
         <td>Secure-<br />
Transport<br />
Edge Virtual IP (load balancer)         </td>
         <td>AS2 (non-SSL)         </td>
         <td>10080         </td>
         <td><img src="/Images/SecureTransport/LeftArrow_14x11.png" /><br />
(in-<br />
bound)         </td>
         <td>Partner AS2 access<br />
(non-secure)         </td>
      </tr>
      <tr>
         <td>9         </td>
         <td>Internet         </td>
         <td>Secure-<br />
Transport<br />
Edge Virtual IP (load balancer)         </td>
         <td>PeSIT over plain socket         </td>
         <td>17617         </td>
         <td><img src="/Images/SecureTransport/LeftArrow_14x11.png" /><br />
(in-<br />
bound)         </td>
         <td>Partner PeSIT access<br />
(non-secure)         </td>
      </tr>
      <tr>
         <td>10         </td>
         <td>Internet         </td>
         <td>Secure-<br />
Transport<br />
Edge Virtual IP (load balancer)         </td>
         <td>PeSIT over secured socket
(non–Transfer CFT Compatible)         </td>
         <td>17627         </td>
         <td><img src="/Images/SecureTransport/LeftArrow_14x11.png" /><br />
(in-<br />
bound)         </td>
         <td>Partner PeSIT access<br />
(non-secure)         </td>
      </tr>
      <tr>
         <td>11         </td>
         <td>Internet         </td>
         <td>Secure-<br />
Transport<br />
Edge Virtual IP (load balancer)         </td>
         <td>PeSIT over secured socket
(Transfer CFT Compatible)         </td>
         <td>17637         </td>
         <td><img src="/Images/SecureTransport/LeftArrow_14x11.png" /><br />
(in-<br />
bound)         </td>
         <td>Partner PeSIT access<br />
(non-secure)         </td>
      </tr>
      <tr>
         <td>12         </td>
         <td>Internet         </td>
         <td>Secure-<br />
Transport<br />
Edge Virtual IP (load balancer)         </td>
         <td>PeSIT over pTCP plain socket         </td>
         <td>19617         </td>
         <td><img src="/Images/SecureTransport/LeftArrow_14x11.png" /><br />
(in-<br />
bound)         </td>
         <td>Partner PeSIT access<br />
(non-secure)         </td>
      </tr>
      <tr>
         <td>13         </td>
         <td>Internet         </td>
         <td>Secure-<br />
Transport<br />
Edge Virtual IP (load balancer)         </td>
         <td>PeSIT over pTCP secured socket         </td>
         <td>19627         </td>
         <td><img src="/Images/SecureTransport/LeftArrow_14x11.png" /><br />
(in-<br />
bound)         </td>
         <td>Partner PeSIT access<br />
(non-secure)         </td>
      </tr>
      <tr>
         <td>14         </td>
         <td>Trusted<br />
(secure<br />
network)         </td>
         <td>Secure-<br />
Transport<br />
Edge         </td>
         <td>HTTPS         </td>
         <td>444         </td>
         <td><img src="/Images/SecureTransport/LeftArrow_14x11.png" /><br />
(in-<br />
bound)         </td>
         <td>{{< SecureTransport/componentshortname  >}} Administration Tool (if access is required through the firewall)         </td>
      </tr>
      <tr>
         <td>15         </td>
         <td>Secure-<br />
Transport<br />
Server         </td>
         <td>Mail server for outgoing mail         </td>
         <td>SMTP (TCP)         </td>
         <td>25         </td>
         <td><img src="/Images/SecureTransport/RightArrow_14x11.png" /><br />
(out-<br />
bound)         </td>
         <td>Ad hoc file transfer email notifications from ST Web Client         </td>
      </tr>
      <tr>
         <td>16         </td>
         <td>Secure-<br />
Transport<br />
Server         </td>
         <td>SNMP Masters         </td>
         <td>SNMP (UDP)         </td>
         <td>162         </td>
         <td><img src="/Images/SecureTransport/RightArrow_14x11.png" /><br />
(out-<br />
bound)         </td>
         <td>SNMP monitoring         </td>
      </tr>
   </tbody>
</table>

For a streaming deployment with one {{< SecureTransport/componentshortname  >}} Edge and one {{< SecureTransport/componentshortname  >}} Server there is no load balancer, so substitute the real IP address of the {{< SecureTransport/componentshortname  >}} Edge for the IP address of the load balancer in the Group Destination column for rules 1 through 13.

For outbound AS2 transfers or asynchronous MDN receipts for inbound AS2 transfers, define outbound rules for ports 10080 and 10443. If the AS2 listener is on the {{< SecureTransport/componentshortname  >}} Server and an SOCKS5 proxy is on the {{< SecureTransport/componentshortname  >}} Edge, define these rules on the firewall between the {{< SecureTransport/componentshortname  >}} Edge and the {{< SecureTransport/componentshortname  >}} Server. Otherwise, define these rules on the firewall between the {{< SecureTransport/componentshortname  >}} Edge and the Internet.

For internal users to upload or download files to {{< SecureTransport/componentshortname  >}}, they must log into the {{< SecureTransport/componentshortname  >}} Server directly using HTTP(S) or FTP(S). So those ports from the secure network to the {{< SecureTransport/componentshortname  >}} Server must be open. In some installations, access is only through a proxy. In this case secure network requires access to the Proxy server.

Both FTP and FTPS use port 20 for the data channel in active mode. If preferred, you can define a passive-port range instead, and set up a similar rule for that range of ports. Both FTP and FTPS use port 21 for the control channel. For more details, see <a href="../../../c_st_troubleshootcommonproblems/t_st_ftpdoesnotworkthroughfirewall/c_st_passive_port_range_is_not_defined_in_firewall#Appendix_Troubleshooting_4259246568_1028083" class="MCXref xref">Passive port range is not defined in the firewall</a>.

HTTP access is optional. To disable HTTP, do not define rule 4.

If the SMTP server that handles ad hoc file transfer email notifications from ST Web Client is in the secure network, do not define rule 15.

**Related topics:**

-   <a href="../r_st_authentication_rules" class="MCXref xref">Authentication rules</a>
-   <a href="../r_st_administration_rules" class="MCXref xref">Administration rules</a>
-   <a href="../r_st_tm_server_communication_rules" class="MCXref xref">TM server communication rules</a>
-   <a href="../r_st_server_transfer_rules" class="MCXref xref">Server transfer rules</a>
-   <a href="../r_st_standard_clustering_rules" class="MCXref xref">Standard Cluster rules</a>
-   <a href="../r_st_large_enterprise_clustering_rules" class="MCXref xref">Enterprise Cluster rules</a>
-   <a href="../r_st_protocol_rules_outbound" class="MCXref xref">Protocol rules - outbound from SecureTransport Edge</a>
