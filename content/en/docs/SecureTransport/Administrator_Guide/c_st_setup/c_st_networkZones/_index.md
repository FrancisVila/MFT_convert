{
    "title": "Communication across Transaction Manager, protocol, and proxy servers",
    "linkTitle": "Transaction Manager protocol and proxy server communication",
    "weight": "280"
}{{< SecureTransport/componentshortname  >}} uses a streaming protocol for communication between the protocol servers running on {{< SecureTransport/componentshortname  >}} Edge and the Transaction Manager (TM) server running on {{< SecureTransport/componentshortname  >}} Server. The streaming protocol abstracts all file transfer protocols and unifies and secures this central communication. When you deploy one or more {{< SecureTransport/componentshortname  >}} Edge servers in a peripheral network (DMZ), the deployment is called *streaming* because no file transfer data is stored on the {{< SecureTransport/componentshortname  >}} Edge server. The protocol servers translate the protocol they are serving to the streaming protocol but do not read or write files.

With a streaming deployment, the TM Server connects to the protocol servers on the configured {{< SecureTransport/componentshortname  >}} Edge servers to establish the connections for the streaming protocol, so no process on a {{< SecureTransport/componentshortname  >}} Edge ever makes a connection from the DMZ into the internal secure network. For more information, see <a href="../../overview/c_st_securetransport_edge" class="MCXref xref">SecureTransport Edge</a>. (The TM server and protocol servers running on {{< SecureTransport/componentshortname  >}} Server also use the streaming protocol internally.)

> **Note:**
>
> Unless a number is specified via the corresponding system properties, the number of established streaming connections from Transaction Manager to a single protocol daemon (Admin, FTP, HTTP, and so forth) is calculated with the help of formula: min(20, 2\*CPUs)

{{< SecureTransport/securetransportname  >}}, when used as a client, can use a proxy server. With AS2 and HTTP/S protocols, any RFC 7231 compliant HTTP proxy is expected to work. With all other protocols, {{< SecureTransport/securetransportname  >}} can use the SOCKS5 proxy component of {{< SecureTransport/securetransportname  >}} Edge.

You configure the communication between the TM server and protocol servers and access to SOCKS5 and HTTP proxies by defining network zones. Each network zone on a {{< SecureTransport/componentshortname  >}} Server can have one or more network zone nodes that define access either within the {{< SecureTransport/componentshortname  >}} Server or between the {{< SecureTransport/componentshortname  >}} Server and one or more {{< SecureTransport/componentshortname  >}} Edge servers. This is also applicable when your implementation uses HTTP proxy servers or the SOCKS5 proxy components of the relevant {{< SecureTransport/securetransportname  >}} Edges. The TM Server connects to all protocol servers configured in all network zones. In the configuration of each transfer site, you can select a network zone to specify which proxy (HTTP or SOCKS5 on Edge) will be used for server-initiated transfers through that transfer site. {{< SecureTransport/componentshortname  >}} selects a node from the network zone using a load-balancing policy when a server-initiated transfer uses the network zone.

> **Note:**
>
> Remember that HTTP proxy is only supported with HTTP(S) and AS2 transfer sites. Proxying server-initiated transfers over the other supported protocols (SSH, FTP(S), PeSIT, etc.) requires the use of the SOCKS5 proxy on SecureTransport Edge.

Because you can specify multiple {{< SecureTransport/componentshortname  >}} Edge addresses in a node and multiple nodes in a network zone, you can implement any required many-to-many communication between TM servers (on {{< SecureTransport/componentshortname  >}} Server nodes) and protocol servers and / or SOCKS5 proxies (on {{< SecureTransport/componentshortname  >}} Edge servers).

On a {{< SecureTransport/componentshortname  >}} Server, a special network zone named `Private` defines the ports used for internal communication between the TM Server and the protocol servers and the Administration Tool server running on the {{< SecureTransport/componentshortname  >}} server.

On a {{< SecureTransport/componentshortname  >}} Edge server, there is only one network zone, a special one named `Private` that specifies the ports that the protocol servers listen on for connections from TM servers on {{< SecureTransport/componentshortname  >}} Servers. The port number must match the port number configured in the network zone on the {{< SecureTransport/componentshortname  >}} Servers that defines the connection to the {{< SecureTransport/componentshortname  >}} Edge server. You cannot define more network zones on a {{< SecureTransport/componentshortname  >}} Edge server.

The following topics describe the streaming deployment and describe managing the Transaction Manager (TM), protocol, and proxy server communication:

-   <a href="" class="MCXref xref">Streaming deployment</a> - Describes {{< SecureTransport/securetransportname >}} streaming deployment.
-   <a href="t_st_networkzones" class="MCXref xref">Manage the communication across Transaction Manager, protocol and proxy servers</a> - Describes managing the Transaction Manager (TM), protocol, and proxy server communication and provides how-to instructions for configuring the Transaction Manager (TM), protocol, and proxy server communication.
