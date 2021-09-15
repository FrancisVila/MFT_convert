{
    "title": "Manage Transaction Manager protocol and proxy server communication",
    "linkTitle": "Manage Transaction Manager protocol and proxy server communication",
    "weight": "320"
}This topic describes managing the Transaction Manager (TM), protocol, and proxy server communication.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">If the IP address in a Host of a network zone is changed, the corresponding <span>SecureTransport</span> Server or <span>SecureTransport</span> Edge must be restarted using the <code>&lt;FILEDRIVEHOME&gt;/stop_all</code> and <code>&lt;FILEDRIVEHOME&gt;/start_all</code> scripts. If the IP address in a Host of a non-private zone  in a cluster environment is changed, all nodes in the cluster need to be restarted.         </td>
      </tr>
</table>

**Related topic:**

-   [Streaming deployment](../c_st_streaming_deployment)

## Specify ports for internal TM server communications

Use the `Private` network zone to specify the ports and certificates used for communication between the TM Server and the protocol servers and the Administration Tool server running on the SecureTransport Server. The `Private` network zone defines one node named `Host` with one address, `localhost`. For the `Private` network zone and internal Transaction Manager server communications to work correctly, `localhost` must resolve to the IP address of the system loopback device.

1.  Select **Setup > Network Zones**.  
    The *Network Zone List* page is displayed.
2.  In the list, click `Private`.  
    The *Edit Network Zone entry* page is displayed.
3.  In the *Node List*, click `Host`.  
    The *Edit Network Zone node* page is displayed.
4.  Under *Streaming Configuration*, enter ports for the TM Server to connect to for each enabled protocol server and for the Administration Tool server.  
    In the special `Private` network zone on SecureTransport Server, these settings define both the ports that the TM Server connects to and the ports that the protocol servers and the Administration Tool server listen on for connections from the TM Server.
5.  (Optional) Under *Streaming Configuration*, select SSL key aliases to secure the SSL communication between the TM Server and the other servers. Do not select any of the SSL key aliases selected to secure protocol communications on the *Server Control* page. Also, add to the value of the `Streaming.TrustedAliases` server configuration parameter the aliases of the CAs that issued the certificates. For details, see the description of the `Streaming.TrustedAliases` server configuration parameter on the *Server Configuration* page.
6.  Click **Save** to save your changes.

## <span id="Create"></span>Create a network zone to define communications with SecureTransport Edge servers

Each network zone can define the communications between the TM Server on a SecureTransport Server and one or more SecureTransport Edge servers. If different protocol servers run on different SecureTransport Edge servers, you can control which protocol servers on which SecureTransport Edge servers the TM Server connects to by specifying different protocol servers and different SecureTransport Edge servers in different nodes.

1.  Select **Setup > Network Zones**.  
    The *Network Zone List* page is displayed.

2.  Click **New Network Zone**.  
    The *New Network Zone entry* page is displayed.

3.  In the **Name** field, enter a name for the network zone. This name is only used in the *Network Zone List* page.

4.  In the **Description** field, enter a description of the network zone to help you understand it purpose and use.

5.  In the **Public URL Prefix** field, enter a prefix for the URLs displayed in notification emails send to ad hoc file transfer recipients.  
    If a user is assigned to a business unit that references a network zone, emails to that user use the prefix specified in that network zone. If a user is not assigned to a business unit, emails to that user use the prefix specified in the default network zone. See [Set a default network zone](#set).

6.  In the **SSO Service Provider Entity ID** field, enter the Single Sign-On (SSO) service provider entity ID. If an entity ID is not provided, SecureTransport uses the entity ID under the `<ServiceProvider>` element from the `sso-enduser.xml` file.  
    
    When Single Sign-On is enabled and a user is successfully signed on to an Identity Provider (IdP), the IdP uses the specified entity ID to identify what network zone to redirect the user to.  
    

    <table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The title of a <code>Private</code> network zone node cannot be changed.          </td>
      </tr>
</table>

7.  If the SOCKS5 proxy is enabled in this network zone and DNS is not available on this SecureTransport Server, select **Use the Edge DNS configuration** to resolve transfer site host names and FQDNs using the DNS on the SecureTransport Edge so that SecureTransport can route transfers correctly.

8.  Click **New Node**.  
    The *New Network Zone Node* page is displayed.

9.  In the **Title** field, enter a title for the node.

10. If this server is part of a DR deployment, select the value for **Deployment Site**. For more information, see [Set up a disaster recovery cluster](../../../c_st_largeenterpriseclustering/t_st_largeenterprisecluster/t_st_setup_disaster_recovery_cluster).

11. In the **Notes** field, enter information to help you understand the purpose and use of the node.

12. Under *Streaming Configuration*, select the protocol servers that the TM Server connects to using this node of this network zone.

13. For each enabled protocol server, enter the port for the TM Servers to connect to.  
    For each SecureTransport Edge server configured under *Addresses*, for a connection to be successful, the SecureTransport Edge server must allow connection from this SecureTransport Server, the `Private` network zone must specify the same port for the protocol server, and the certificate must be trusted. See [Specify allowed SecureTransport Servers on SecureTransport Edge](#specify) and [Specify TM Server communication ports and IP address for protocol servers on SecureTransport Edge](#specify2).

14. Under *Addresses*, click **Add Address**.

15. In the **Address** field, enter the IP address of a SecureTransport Edge server that runs the protocol servers configured for this network zone node.

16. Repeat step 10 and 11 for each SecureTransport Edge server in this network zone node.

17. Click **OK** to save this node or **OK & New** to save this node and add another using steps 7 though 12.

18. Click **Save** to save the network zone.  
    SecureTransport save the network zone in the database.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">After restarting Transaction Manager if you specify a SSO Service Provider Entity ID value, <span>SecureTransport</span> will clone the <code>sso-enduser.xml</code> file (if any), and will make a transformation changing the <code>entityId</code> attribute in the <em>&lt;ServiceProvider&gt;</em> element, which will be used by the corresponding <span>SecureTransport</span> Edges on this Network Zone when the user is trying to authenticate via this Network Zone.         </td>
      </tr>
</table>

## <span id="Specify3"></span>Specify proxy settings in a network zone

Use network zones to specify how SecureTransport connects to the SecureTransport Edge SOCKS5 proxy (or a HTTP proxy, where relevant) for server-initiated file transfers. You can use the same network zone node to define streaming and proxy configuration or you can define only streaming or only proxy configuration in a node or network zone.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Streaming must be configured for each <span>SecureTransport Edge</span> zone in order for some functions to behave properly.
		         </td>
      </tr>
</table>

When you define an AS2, FTP(S), HTTP(S), PeSIT, or SSH transfer site, you can select a network zone to specify the proxy servers for transfer through that transfer site.

1.  Select **Setup > Network Zones**.  
    The *Network Zone List* page is displayed.
2.  Click a name in the list or click **New Network Zone**.  
    The *Edit Network Zone entry* page or the *New Network Zone entry* page is displayed.
3.  For a new network node, enter values in the **Name**, **Description**, and **Public URL Prefix** fields as needed.
4.  Click a title in the *Node List* or click **New Node**.  
    The **Edit Network Zone node* or the New Network Zone node* page is displayed.
5.  For a new node, enter values in the **Title** and **Notes** fields as needed.
6.  Under *Proxy*, select **Enable Proxy**.
7.  Select the proxies, **SOCKS5** or **HTTP**, to configure in the node.
8.  For each selected proxy:
    1.  Enter the **Port**. The proxy server must listen for connections on this port. For the SOCKS5 proxy on SecureTransport Edge, configure the port for the proxy server on the *Server Control* page. See [Manage the Proxy server on SecureTransport Edge](ext_s_proxyserver_edge.htm). If you use a third-party proxy server, refer to its documentation to configure the port.
    2.  (Optional) If required by the proxy server, enter a **Username** and, if also required, select **User Password** and enter a **Password**. The SOCKS5 proxy on SecureTransport Edge does not use this authentication.
9.  For a new node, add the address of the SecureTransport Edge servers that run the SOCKS5 proxies or the addresses of the other proxy servers. If you selected **SOCKS5**, you must use IPv4 addresses. SecureTransport Server selects the servers at these address sequentially (round-robin) when it uses this node for server-initialed transfer.
10. If DNS is not available on this SecureTransport Server, select **Use the Edge DNS configuration** to resolve transfer site host names and FQDNs using the DNS on the SecureTransport Edge so that SecureTransport can route transfers correctly.
11. Click **OK** to save the new node or the changes to the node.
12. Click **Save** to save the network zone.

## <span id="Set"></span>Set a default network zone

Business units can specify a network zone that defines the public URL for users in that business unit. For details, see [Create or edit a business unit](t_st_businessunits.htm#create). AS2, FTP(S), HTTP(S), PeSIT, and SSH transfer sites can specify a network zone that defines the proxy for that site. For details, see [Transfer sites](../../../accounts/transfersites). In all cases, you can select **Default** in the business unit or transfer site.

The default network zone defines the public URL for users in business units where you selected **Default** and for users who are not in a business unit. The default network zone also defines the proxy for transfer sites where you selected **Default**. If a transfer site selects the default network zone and no default is defined, transfers from that site fail.

1.  Select **Setup > Network Zones**.  
    The *Network Zone List* page is displayed.
2.  Select one network zone in the list.
3.  Click **Change Default**.  
    The selected network zone is marked as the default.

## <span id="Specify2"></span>Specify TM Server communication ports and IP address for protocol servers on SecureTransport Edge

The `Private` network zone is the only network zone defined on the SecureTransport Edge server. You cannot delete it or define more network zones.

Use the `Private` network zone to specify the ports and IP address that the protocol servers and the Administration Tool server listen on for connections from TM Servers. The `Private` network zone defines one node named `Host`.

1.  Select **Setup > Network Zones**.  
    The *Network Zone List* page is displayed.
2.  In the list, click `Private`.  
    The *Edit Network Zone entry* page is displayed.
3.  In the *Node List*, click `Host`.  
    The *Edit Network Zone Node* page is displayed.
4.  For each enabled protocol server, enter the protocol server listens on for connections from TM Servers.  
    For a connection to be successful, the SecureTransport Edge server must allow connection from this SecureTransport Server, there must be a network zone on a SecureTransport Server with these same ports configured for the host name or IP address of this SecureTransport Edge server and the certificate must be trusted on the SecureTransport Server. See [Specify allowed SecureTransport Servers on SecureTransport Edge](#specify) and [Create a network zone to define communications with SecureTransport Edge servers](#create).
5.  Under *Addresses*, Click the Edit icon (![Edit](SaveIcon_13x13.png)) for the `localhost` entry.
6.  In the **Address** field, enter the IP address of the interface that the servers listen on for connections from TM Servers.
7.  Click the Save icon (![Save](SaveIcon_13x13.png)).
8.  Click **OK** to save your changes.

## <span id="Secure"></span>Secure the communication between the TM server and the protocol servers

You can use SSL to secure the communication between the TM server running on SecureTransport Server and the protocol servers running on SecureTransport Edge.

In a streaming deployment, the protocol servers on SecureTransport Edge have the role of server because the TM server on SecureTransport Server connects to them and the TM server on SecureTransport Server has the role of client because it connects to the protocol servers on SecureTransport Edge.

1.  Generate or obtain the following certificates:
    -   The TM server client certificate with `extendedKeyUsage` = `clientAuth` and
        `keyUsage` = `digitalSignature`
    -   The protocol servers server certificate with `extendedKeyUsage` = `serverAuth` and
        `keyUsage` = `digitalSignature`, `keyEncipherment`
2.  On SecureTransport Edge:
    1.  Import into the trusted CAs the public part of the certificate for the CA used to generate the TM server client certificate.
    2.  Add to the `Streaming.TrustedAliases` server configuration parameter the alias you specified when you imported the certificate in step a.
    3.  Import into the local certificates the protocol servers server certificate.
    4.  In the `Private` network zone, open the *Edit Network Node* page and, to secure the SSL communication for a protocol, select the **SSL Key Alias** you specified when you imported the certificate in step c.
3.  On SecureTransport Server:
    1.  Import into the trusted CAs the public part of the certificate for the CA used to generate the protocol servers server certificate.
    2.  Add to the `Streaming.TrustedAliases` server configuration parameter the alias you specified when you imported the certificate in step a.
    3.  Import into the local certificates the TM server client certificate.
    4.  In the network zone you created to define communications with SecureTransport Edge servers, open the *Edit Network Node* page and, to secure the SSL communication for a protocol, select the **SSL Key Alias** you specified when you imported the certificate in step c.

## Specify the SecureTransport Edge load-balancing policy

When a client establishes a user session to a protocol server running on SecureTransport Edge, the load-balancing policy that SecureTransport Edge uses to allocate a Transaction Manager connection to that session is specified by the `Streaming.LoadBalancingPolicy` server configuration parameter. The valid values are:

-   **`Round-Robin` –** SecureTransport Edge directs connections to connected Transaction Managers in a circular sequence and allocates the least-used connection to that Transaction Manager to the session.
-   **`Random` –** SecureTransport Edge randomly selects a connection from all the connections to all the connected Transaction Managers and allocates it to the session.
-   **`Blacklist-Round-Robin` –** SecureTransport Edge directs connections to connected Transaction Managers in a circular sequence and allocates the least-used connection (but filters bad connections) to that Transaction Manager to the session. `Blacklist-Round-Robin` is the default and recommended value.
-   **`Blacklist-Random` –** SecureTransport Edge randomly selects a connection from all the connections ( but filters bad connections) to all the connected Transaction Managers and allocates it to the session.

In all cases, the user session uses the allocated connection until it terminates.

## <span id="Specify"></span>Specify allowed SecureTransport Servers on SecureTransport Edge

The SOCKS5 proxy on a SecureTransport Edge server accepts connections for server-initiated transfers only from the SecureTransport Servers listed. There is no HTTP proxy on the SecureTransport Edge server. The Transaction Manager on any SecureTransport Server can connect to a protocol server on any SecureTransport Edge server.

1.  Select **Setup > Allowed ST Servers**.  
    A page is displayed with the server list.
2.  Under *ST Servers*, list the host names or IP address of the SecureTransport Servers that are allowed to connect to this SecureTransport Edge server, either to a protocol server or to a SOCKS5 or HTTP proxy.
3.  Click **Update**.
4.  Restart the SOCKS proxy on the SecureTransport Edge server.
