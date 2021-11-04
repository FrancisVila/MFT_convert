{
    "title": "SecureTransport Edge checklists",
    "linkTitle": "SecureTransport Edge checklists",
    "weight": "70"
}This section provides the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge checklists for root and non-root installations.

## <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge root installation checklist

The following items are needed for the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge root installation configuration:

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Items         </th>
<th colspan="2" class="HeadD-Column1-Header1">Your installation         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge IP address         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server IP address or host name         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Core server license for <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Server feature license for <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>CA and certificate attributes         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Initial password for the root CA         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><strong>Port Settings</strong>         </td>
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
         <td>PeSIT over Secured Socket
port         </td>
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
         <td>Database port         </td>
         <td>33060         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Proxy server port         </td>
         <td>1080         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><strong>Streaming Port Settings:</strong>         </td>
         <td><strong>Default</strong>         </td>
         <td><strong>Your installation</strong>         </td>
      </tr>
      <tr>
         <td>FTP         </td>
         <td>20021         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>HTTP         </td>
         <td>20080         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>AS2         </td>
         <td>21080         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>SSH         </td>
         <td>20022         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>PeSIT         </td>
         <td>27617         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>ADMIN         </td>
         <td>20444         </td>
         <td>          </td>
      </tr>
   </tbody>
</table>

> **Note:**
>
> If port 22 is the default port for the operating system SSH service on your platform, to avoid conflicts change the port or disable the operating system service or choose a different port for SecureTransport SSH service. The default operating system SSH port for Axway appliances is 10022.

## <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge non-root installation checklist

The following items are needed for the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge non-root installation configuration:

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Items         </th>
<th colspan="2" class="HeadD-Column1-Header1">Your installation         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge IP address         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server IP address or host name         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Core server license for <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Server feature license for <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>CA and certificate attributes         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Initial password for the root CA         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><strong>Port Settings</strong>         </td>
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
         <td>PeSIT over Secured Socket
port         </td>
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
         <td>Database port         </td>
         <td>33060         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Proxy server port         </td>
         <td>1080         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><strong>Streaming Port Settings:</strong>         </td>
         <td><strong>Default</strong>         </td>
         <td><strong>Your installation</strong>         </td>
      </tr>
      <tr>
         <td>FTP         </td>
         <td>20021         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>HTTP         </td>
         <td>20080         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>AS2         </td>
         <td>21080         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>SSH         </td>
         <td>20022         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>PeSIT         </td>
         <td>27617         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>ADMIN         </td>
         <td>20444         </td>
         <td>          </td>
      </tr>
   </tbody>
</table>

> **Note:**
>
> If port 8022 is the default port for the operating system SSH service on your platform, to avoid conflicts change the port or disable the operating system service or choose a different port for SecureTransport SSH service. The default operating system SSH port for Axway appliances is 10022.
