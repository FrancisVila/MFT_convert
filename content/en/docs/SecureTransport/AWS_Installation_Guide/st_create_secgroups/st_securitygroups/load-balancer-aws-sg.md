{
    "title": "Load Balancer Security Group",
    "linkTitle": "Load Balancer Security Group",
    "weight": "150"
}## Load Balancer Security Group

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
            <p>HTTP</p>
         </td>
         <td>
            <p>TCP</p>
         </td>
         <td>
            <p>80</p>
         </td>
         <td>
            <p>0.0.0.0/0</p>
         </td>
         <td>
            <p>HTTP</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>HTTPS</p>
         </td>
         <td>
            <p>TCP</p>
         </td>
         <td>
            <p>443</p>
         </td>
         <td>
            <p>0.0.0.0/0</p>
         </td>
         <td>
            <p>HTTPS</p>
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
            <p>10022</p>
         </td>
         <td>
            <p>0.0.0.0/0</p>
         </td>
         <td>
            <p>SSH (SFTP and SCP)</p>
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
            <p>21</p>
         </td>
         <td>
            <p>0.0.0.0/0</p>
         </td>
         <td>
            <p>FTP (secure and non-secure) control channel (For secure connections: the firewall must allow bidirectional communication)</p>
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
            <p>20</p>
         </td>
         <td>
            <p>0.0.0.0/0</p>
         </td>
         <td>
            <p>FTP (secure and non-secure) active-mode data channel</p>
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
            <p>User-defined range</p>
         </td>
         <td>
            <p>0.0.0.0/0</p>
         </td>
         <td>
            <p>FTP (secure and non-secure) passive-mode data channel</p>
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
            <p>10080</p>
         </td>
         <td>
            <p>0.0.0.0/0</p>
         </td>
         <td>
            <p>AS2(non-SSL)</p>
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
            <p>10443</p>
         </td>
         <td>
            <p>0.0.0.0/0</p>
         </td>
         <td>
            <p>AS2 (SSL)</p>
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
            <p>17617</p>
         </td>
         <td>
            <p>0.0.0.0/0</p>
         </td>
         <td>
            <p>PeSIT (non-SSL)</p>
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
            <p>17627</p>
         </td>
         <td>
            <p>0.0.0.0/0</p>
         </td>
         <td>
            <p>PeSIT over secure socket (Transfer CFT compatible)</p>
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
            <p>17637</p>
         </td>
         <td>
            <p>0.0.0.0/0</p>
         </td>
         <td>
            <p>PeSIT over secure socket (CFT compatible)</p>
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
            <p>19617</p>
         </td>
         <td>
            <p>0.0.0.0/0</p>
         </td>
         <td>
            <p>PeSIT over pTCP plain socket</p>
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
            <p>19627</p>
         </td>
         <td>
            <p>0.0.0.0/0</p>
         </td>
         <td>
            <p>PeSIT over pTCP Secured Socket</p>
         </td>
      </tr>
   </tbody>
</table>
