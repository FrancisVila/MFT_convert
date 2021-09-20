{
    "title": "SecureTransport Edge checklists",
    "linkTitle": "SecureTransport Edge checklists",
    "weight": "70"
}This section provides the SecureTransport Edge checklists for root and non-root installations.

## SecureTransport Edge root installation checklist

The following items are needed for the SecureTransport Edge root installation configuration:

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Items</th>
<th colspan="2">Your installation</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><span>SecureTransport</span> Edge IP address         </td>
         <td colspan="2">          </td>
      </tr>
      <tr>
         <td><span>SecureTransport</span> Server IP address or host name         </td>
         <td colspan="2">          </td>
      </tr>
      <tr>
         <td>Core server license for <span>SecureTransport</span> Edge         </td>
         <td colspan="2">          </td>
      </tr>
      <tr>
         <td>Server feature license for <span>SecureTransport</span> Edge         </td>
         <td colspan="2">          </td>
      </tr>
      <tr>
         <td>CA and certificate attributes         </td>
         <td colspan="2">          </td>
      </tr>
      <tr>
         <td>Initial password for the root CA         </td>
         <td colspan="2">          </td>
      </tr>
      <tr>
         <td><strong>Port Settings</strong>
         </td>
         <td><strong>Default</strong>
         </td>
         <td><strong>Your installation</strong>
         </td>
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
         <td><strong>Streaming Port Settings:</strong>
         </td>
         <td><strong>Default</strong>
         </td>
         <td><strong>Your installation</strong>
         </td>
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

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">If port 22 is the default port for the operating system SSH service on your platform, to avoid conflicts change the port or disable the operating system service or choose a different port for <span>SecureTransport</span> SSH service. The default operating system SSH port for <span>Axway</span> appliances is 10022.         </td>
      </tr>
</table>

## SecureTransport Edge non-root installation checklist

The following items are needed for the SecureTransport Edge non-root installation configuration:

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Items</th>
<th colspan="2">Your installation</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><span>SecureTransport</span> Edge IP address         </td>
         <td colspan="2">          </td>
      </tr>
      <tr>
         <td><span>SecureTransport</span> Server IP address or host name         </td>
         <td colspan="2">          </td>
      </tr>
      <tr>
         <td>Core server license for <span>SecureTransport</span> Edge         </td>
         <td colspan="2">          </td>
      </tr>
      <tr>
         <td>Server feature license for <span>SecureTransport</span> Edge         </td>
         <td colspan="2">          </td>
      </tr>
      <tr>
         <td>CA and certificate attributes         </td>
         <td colspan="2">          </td>
      </tr>
      <tr>
         <td>Initial password for the root CA         </td>
         <td colspan="2">          </td>
      </tr>
      <tr>
         <td><strong>Port Settings</strong>
         </td>
         <td><strong>Default</strong>
         </td>
         <td><strong>Your installation</strong>
         </td>
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
         <td><strong>Streaming Port Settings:</strong>
         </td>
         <td><strong>Default</strong>
         </td>
         <td><strong>Your installation</strong>
         </td>
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

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">If port 8022 is the default port for the operating system SSH service on your platform, to avoid conflicts change the port or disable the operating system service or choose a different port for <span>SecureTransport</span> SSH service. The default operating system SSH port for <span>Axway</span> appliances is 10022.         </td>
      </tr>
</table>
