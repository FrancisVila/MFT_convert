{
    "title": "Using HTTP/HTTPS proxies",
    "linkTitle": "Using HTTP/HTTPS proxies",
    "weight": "210"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Protocols

[Configuring proxies](#Configuring_Proxies)

[HTTP/HTTPS proxy details](#HTTP_HTTPS_proxy_details)

<span id="Configuring_Proxies"></span>

## Configuring proxies

The configuration of a Proxy object is defined in the file <span class="code">proxy.ini</span>.

To use a Proxy, add <span class="code">@proxy\_name</span>to the TCP address of the Remote Site.

The TCP address of Sites (<span class="code">IP@proxy/port</span>) must not exceed 63 characters.

### Configuring HTTP proxies

Configure HTTP proxies as follows:

\[proxy\_name\]

protocol = HTTP

address = proxy.domain/8080

user = login

password = pass

### Configuring HTTPS proxies

Configure HTTPS proxies as follows:

\[proxy\_name\]

protocol = HTTPS

address = proxy.domain/8080

user = login

password = pass

<span id="HTTP_HTTPS_proxy_details"></span>

## HTTP/HTTPS proxy details

<span id="HTTP_proxies"></span>

### HTTP proxies

To proxy HTTP through Web proxies, the basic procedure is as follows:

1.  Connect to the Web proxy.
2.  Send the HTTP requests formed with the full URL (http://) and the proxy identification parameters.
3.  Wait for the response from either the Web proxy or the remote Web server.

<span id="HTTPS_proxies"></span>

### HTTPS proxies

To proxy HTTPS through Web proxies, the basic procedure is as follows:

1.  Connect to the Web proxy.
2.  Send an HTTP connect request for the distant HTTPS server.
3.  Wait for the proxy response.
4.  Initiate the SSL connection with the remote server.
5.  Send the HTTP requests.

To connect to an HTTPS server through a web proxy, the HTTP protocol and the Remote Site representing the HTTPS server must be set to use TLS security.

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
