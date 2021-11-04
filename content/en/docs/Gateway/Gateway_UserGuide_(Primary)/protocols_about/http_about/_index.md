{
    "title": "HTTP",
    "linkTitle": "HTTP",
    "weight": "160"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Protocols

## About HTTP

[HTTP](#http_intro)

[HTTP and Gateway](#HTTP_and_Gateway)

<span id="http_intro"></span>

### HTTP Introduction

The <span style="font-weight: bold;">H</span>yper<span style="font-weight: bold;">t</span>ext <span style="font-weight: bold;">T</span>ransfer <span style="font-weight: bold;">P</span>rotocol (HTTP) is an application-level protocol, used as a generic protocol for communication between users, proxies, or gateways and other Internet systems.

Gateway implements both HTTP/1.0 client and server specifications. Configuration of the relevant objects for HTTP depends on whether you are using Gateway in server mode or client mode.

#### How does HTTP work?

HTTP is a client/server protocol based on a simple request-response dialog. As a stateless protocol, HTTP requires that every request sent by a client contain all the information (for example, identification parameters) necessary for the server to execute it. A complete dialog, which is always initiated by the client, consists of one request and one response.

Sometimes one or more intermediaries, such as a proxy, firewall, or gateway, are present in the request/response chain.

To end an HTTP session the client takes no explicit action as the connection is closed after each request/response dialog pair.

<span id="HTTP_and_Gateway"></span>

### HTTP and Gateway

You can use HTTP in Gateway to:

-   Send and receive files in client and server mode
-   List available files or transfers
-   Customize error pages and PUT command results
-   Access virtual file directories via the Gateway GUI

Gateway enables you to implement routing and execute user exits when sending or receiving transfers.

Related topics

[Configuring the HTTP environment](http_config.htm)

[Using HTTP in server mode](http_using_in_server_mode.htm)

[Using HTTP in client mode](http_using_in_client_mode.htm)

[Using HTTP/HTTPS proxies](http_using_proxies.htm)

[Adding non-standard HTTP headers](http_client_non_std_headers.htm)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
