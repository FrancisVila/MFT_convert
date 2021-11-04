{
    "title": "Proxy objects",
    "linkTitle": "Managing Proxy objects",
    "weight": "130"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Partners

[Proxies](#overview)

[Proxies and Gateway](#Proxies_and_Gateway)

<span id="overview"></span>

## Proxy objects introduction

A proxy server is a machine that plays the role of buffer between the file sender and the file receiver, or between the local area network and the external network. The proxy itself controls and implements connections with the outside world. When an internal application tries to connect to the external network, the application must first connect to the proxy. The application transmits the information necessary to establish an outgoing connection (including the target network address, port number, and so on).

The proxy receives data and forwards it via a different port. This eliminates the direct path between two networks and prevents unauthorized users from obtaining internal addresses and details of a private network.

Proxy servers are available for common Internet services. For example, an HTTP proxy can provide Web access, and an SMTP proxy can provide email services access.

<span id="Proxies_and_Gateway"></span>

## Proxies and Gateway

Gateway is proxy compliant and integrates functions to inter-operate with proxies.

In Gateway, you use the Proxy object exclusively in client mode for contacting a proxy server. The protocol settings of a Proxy object define the TCP address and access port for the connection server and the set of connection parameters (for example, the user name and corresponding password).

Gateway supports the following types of proxy:

-   <span style="font-weight: bold;">FT proxies</span>
    -   FTP
    -   HTTP
-   <span style="font-weight: bold;">NET proxies</span>
    -   SOCKS 4
    -   HTTPS

### SOCKS 4 proxies

SOCKS Protocol version 4 sends a network frame that contains the final destination address, the port number, and an identifier that makes authentication to the proxy possible.

### FTP proxies

You use the FTP proxy object exclusively in client mode. The protocol settings of a proxy must contain the TCP address type and address details for the connection server. This address must include the set of parameters that allow connection (for example, the user name and corresponding password).

### HTTP/HTTPS proxies

To connect to an HTTPS server through a web proxy, you set the HTTP protocol and the Remote Site representing the HTTPS server to use TLS/SSL security.

#### HTTPS proxies:

-   connect to the web proxy
-   send an HTTP connect request to the remote HTTPS server
-   wait for the proxy response
-   initiate the TLS/SSL connection with the remote server
-   send the HTTP requests

#### HTTP proxies:

-   connect to the web proxy
-   send the HTTP request formed with the complete URL (http://…) and the proxy identification parameters
-   wait for the response that can come from either the web proxy or the remote web server

It is possible to configure Gateway to do tunneling for various protocols over HTTP. To do this, a proxy object of type HTTPS needs to be created and configured with the address of the remote proxy. The type needs to be HTTPS even if the connection to the proxy is not secure (HTTP). In the remote site, the field "Network Proxy" needs to point to the previously defined proxy. In this configuration, Gateway uses the "CONNECT" method to authenticate the specified proxy.

Related topics

[Working with Proxies](managing_proxies)

[Working with Proxies (command line)](managing_proxies_cli)

[Proxies: Parameters List](managing_proxies_cli/proxies_parameter_list)

[Using an FTP proxy](../../protocols_about/ftp_about/ftp_using_proxy)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
