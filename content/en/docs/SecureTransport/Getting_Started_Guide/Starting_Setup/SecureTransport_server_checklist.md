{
    "title": "SecureTransport Server checklists",
    "linkTitle": "SecureTransport Server checklists",
    "weight": "60"
}This section provides the {{< SecureTransport/componentshortname  >}} Server checklists for root and non-root installations.

## {{< SecureTransport/componentshortname  >}} Server root installation checklist

The following items are needed for the {{< SecureTransport/componentshortname  >}} Server root installation configuration:

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Items         </th>
<th colspan="2" class="HeadD-Column1-Header1">Your installation         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>{{< SecureTransport/componentshortname  >}} Server IP address         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Core server license for {{< SecureTransport/componentshortname  >}} Server         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Server feature license for {{< SecureTransport/componentshortname  >}} Server         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Certificate Authority (CA) and certificate attributes         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Initial password for the root CA         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><strong>Port settings</strong>         </td>
         <td><strong>Default</strong>         </td>
         <td><strong>Your installation</strong>         </td>
      </tr>
      <tr>
         <td>HTTP port         </td>
         <td>80         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>HTTPS port         </td>
         <td>443         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>HTTPS admin port         </td>
         <td>444         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>HTTPS admin shutdown port         </td>
         <td>8005         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>FTP/S port         </td>
         <td>21         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>AS2 port for HTTP         </td>
         <td>10080         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>AS2 port for HTTPS         </td>
         <td>10443         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>AS2 shutdown port         </td>
         <td>8006         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>SSH port         </td>
         <td>22         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>PeSIT over Plain Socket port         </td>
         <td>17617         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>PeSIT over Secured Socket port         </td>
         <td>17627         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>PeSIT over Secured Socket
(legacy) port         </td>
         <td>17637         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>PeSIT over Secured Socket (legacy § comp) port         </td>
         <td>17657         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>PeSIT over pTCP Plain Socket port         </td>
         <td>19617         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>PeSIT over pTCP Secured Socket port         </td>
         <td>19627         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>MariaDB / MySQL database port         </td>
         <td>33060         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><strong>Oracle database settings</strong>         </td>
         <td><strong>Default</strong>         </td>
         <td><strong>Your installation</strong>         </td>
      </tr>
      <tr>
         <td>Host         </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Port         </td>
         <td>1521         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>User Name         </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Password         </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Service Name         </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Use existing database schema         </td>
         <td>False         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Use secure connection         </td>
         <td>True         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Server Certificate DN         </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Certificate Path         </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td><strong>PostgreSQL database settings</strong>         </td>
         <td><strong>Default</strong>         </td>
         <td><strong>Your installation</strong>         </td>
      </tr>
      <tr>
         <td>Host         </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Port         </td>
         <td>5432         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>User Name         </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Password         </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Database Name         </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Use existing database schema         </td>
         <td>False         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Use secure connection         </td>
         <td>True         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Server Certificate DN         </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Certificate File         </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td><strong>Microsoft SQL Server database settings</strong>         </td>
         <td><strong>Default</strong>         </td>
         <td><strong>Your installation</strong>         </td>
      </tr>
      <tr>
         <td>Host         </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Port         </td>
         <td>1433         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Login Name         </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Password         </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Database Name         </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Use existing database schema         </td>
         <td>False         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Use secure connection         </td>
         <td>True         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Server Certificate CN         </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Certificate Path         </td>
         <td>          </td>
         <td>          </td>
      </tr>
   </tbody>
</table>

> **Note:**
>
> If port 22 is the default port for the operating system SSH service on your platform, to avoid conflicts change the port or disable the operating system service or choose a different port for SecureTransport SSH service. The default operating system SSH port for Axway appliances is 10022.

## {{< SecureTransport/componentshortname  >}} Server non-root installation checklist

The following items are needed for the {{< SecureTransport/componentshortname  >}} Server non-root installation configuration:

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Items         </th>
<th colspan="2" class="HeadD-Column1-Header1">Your installation         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>{{< SecureTransport/componentshortname  >}} Server IP address         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Core server license for {{< SecureTransport/componentshortname  >}} Server         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Server feature license for {{< SecureTransport/componentshortname  >}} Server         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Certificate Authority (CA) and certificate attributes         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Initial password for the root CA         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><strong>Port settings</strong>         </td>
         <td><strong>Default</strong>         </td>
         <td><strong>Your installation</strong>         </td>
      </tr>
      <tr>
         <td>HTTP port         </td>
         <td>8080         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>HTTPS port         </td>
         <td>8443         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>HTTPS admin port         </td>
         <td>8444         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>HTTPS admin shutdown port         </td>
         <td>8005         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>FTP/S port         </td>
         <td>8021         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>AS2 port for HTTP         </td>
         <td>10080         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>AS2 port for HTTPS         </td>
         <td>10443         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>AS2 shutdown port         </td>
         <td>8006         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>SSH port         </td>
         <td>8022         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>PeSIT over Plain Socket port         </td>
         <td>17617         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>PeSIT over Secured Socket port         </td>
         <td>17627         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>PeSIT over Secured Socket
(legacy) port         </td>
         <td>17637         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>PeSIT over Secured Socket (legacy § comp) port         </td>
         <td>17657         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>PeSIT over pTCP Plain Socket port         </td>
         <td>19617         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>PeSIT over pTCP Secured Socket port         </td>
         <td>19627         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>MariaDB / MySQL database port         </td>
         <td>33060         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><strong>Oracle database settings</strong>         </td>
         <td><strong>Default</strong>         </td>
         <td><strong>Your installation</strong>         </td>
      </tr>
      <tr>
         <td>Host         </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Port         </td>
         <td>1521         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>User Name         </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Password         </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Service Name         </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Use existing database schema         </td>
         <td>False         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Use secure connection         </td>
         <td>True         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Server Certificate DN         </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Certificate Path         </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td><strong>PostgreSQL database settings</strong>         </td>
         <td><strong>Default</strong>         </td>
         <td><strong>Your installation</strong>         </td>
      </tr>
      <tr>
         <td>Host         </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Port         </td>
         <td>5432         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>User Name         </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Password         </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Database Name         </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Use existing database schema         </td>
         <td>False         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Use secure connection         </td>
         <td>True         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Server Certificate DN         </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Certificate Path         </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td><strong>Microsoft SQL Server database settings</strong>         </td>
         <td><strong>Default</strong>         </td>
         <td><strong>Your installation</strong>         </td>
      </tr>
      <tr>
         <td>Host         </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Port         </td>
         <td>1433         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Login Name         </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Password         </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Database Name         </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Use existing database schema         </td>
         <td>False         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Use secure connection         </td>
         <td>True         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Server Certificate CN         </td>
         <td>          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Certificate Path         </td>
         <td>          </td>
         <td>          </td>
      </tr>
   </tbody>
</table>

> **Note:**
>
> If port 8022 is the default port for the operating system SSH service on your platform, to avoid conflicts change the port or disable the operating system service or choose a different port for SecureTransport SSH service. The default operating system SSH port for Axway appliances is 10022.
