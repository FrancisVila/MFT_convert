{
    "title": "Transaction Manager protocol and proxy server communication",
    "linkTitle": "Transaction Manager protocol and proxy server communication",
    "weight": "290"
}SecureTransport uses a streaming protocol for communication between the protocol servers running on SecureTransport Edge and the Transaction Manager (TM) server running on SecureTransport Server. The streaming protocol abstracts all file transfer protocols and unifies and secures this central communication. When you deploy one or more SecureTransport Edge servers in a peripheral network (DMZ), the deployment is called *streaming* because no file transfer data is stored on the SecureTransport Edge server. The protocol servers translate the protocol they are serving to the streaming protocol but do not read or write files.

With a streaming deployment, the TM Server connects to the protocol servers on the configured SecureTransport Edge servers to establish the connections for the streaming protocol, so no process on a SecureTransport Edge ever makes a connection from the DMZ into the internal secure network. For more information, see [SecureTransport Edge](../../overview5/c_st_securetransport_edge). (The TM server and protocol servers running on SecureTransport Server also use the streaming protocol internally.)

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Unless a number is specified via the corresponding system properties, the number of established streaming connections from Transaction Manager to a single protocol daemon (Admin, FTP, HTTP, and so forth) is calculated with the help of formula: min(20, 2*CPUs)         </td>
      </tr>
</table>

SecureTransport, when used as a client, can use a proxy server. With AS2 and HTTP/S protocols, any RFC 7231 compliant HTTP proxy is expected to work. With all other protocols, SecureTransport can use the SOCKS5 proxy component of SecureTransport Edge.

You configure the communication between the TM server and protocol servers and access to SOCKS5 and HTTP proxies by defining network zones. Each network zone on a SecureTransport Server can have one or more network zone nodes that define access either within the SecureTransport Server or between the SecureTransport Server and one or more SecureTransport Edge servers. This is also applicable when your implementation uses HTTP proxy servers or the SOCKS5 proxy components of the relevant SecureTransport Edges. The TM Server connects to all protocol servers configured in all network zones. In the configuration of each transfer site, you can select a network zone to specify which proxy (HTTP or SOCKS5 on Edge) will be used for server-initiated transfers through that transfer site. SecureTransport selects a node from the network zone using a load-balancing policy when a server-initiated transfer uses the network zone.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Remember that HTTP proxy is only supported with HTTP(S) and AS2 transfer sites. Proxying server-initiated transfers over the other supported protocols (SSH, FTP(S), PeSIT, etc.) requires the use of the SOCKS5 proxy on SecureTransport Edge.         </td>
      </tr>
</table>

Because you can specify multiple SecureTransport Edge addresses in a node and multiple nodes in a network zone, you can implement any required many-to-many communication between TM servers (on SecureTransport Server nodes) and protocol servers and / or SOCKS5 proxies (on SecureTransport Edge servers).

On a SecureTransport Server, a special network zone named `Private` defines the ports used for internal communication between the TM Server and the protocol servers and the Administration Tool server running on the SecureTransport server.

On a SecureTransport Edge server, there is only one network zone, a special one named `Private` that specifies the ports that the protocol servers listen on for connections from TM servers on SecureTransport Servers. The port number must match the port number configured in the network zone on the SecureTransport Servers that defines the connection to the SecureTransport Edge server. You cannot define more network zones on a SecureTransport Edge server.

The following topics describe the streaming deployment and describe managing the Transaction Manager (TM), protocol, and proxy server communication:

-   [Streaming deployment](c_st_streaming_deployment) - Describes SecureTransport streaming deployment.
-   [Manage the communication across Transaction Manager, protocol and proxy servers](t_st_networkzones) - Describes managing the Transaction Manager (TM), protocol, and proxy server communication and provides how-to instructions for configuring the Transaction Manager (TM), protocol, and proxy server communication.
