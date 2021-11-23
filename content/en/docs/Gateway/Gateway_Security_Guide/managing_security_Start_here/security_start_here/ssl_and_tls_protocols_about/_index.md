{
    "title": "TLS protocol",
    "linkTitle": "TLS",
    "weight": "190"
}{{< Gateway/componentlongname  >}}: Managing Security

[About the TLS protocols](#About_SSL_and_TLS_protocols)

[Using the TLS with transfer protocols](#Using_SSL_or_TLS_with_transfer_protocols)

[TLS instance](#TLS_instance)

[Incoming connection](#Incoming_connection)

[Outgoing connection](#Outgoing_connection)

[TLS Extensions](#TLSextentions)

Related topics

[Managing TLS](managing_tls)

[Using TLS](using_tls)

[Managing TLS Security Profiles](tls_security_profiles__gui_)

[Managing TLS Security Profiles (command line)](managing_tls_security_profiles_cli)

<span id="About_SSL_and_TLS_protocols"></span>

## About the TLS protocol

These TLS protocol operates between network protocol layers (for example, TCP/IP...) and application protocol layers (for example, HTTP). They both provide the following services:

-   [Authentication](../../../security_features/ov_gw_security_features#Authentication)
-   [Integrity](../../../security_features/ov_gw_security_features#Integrity)
-   [Privacy](../../../security_features/ov_gw_security_features#Privacy)

TLS is based on four protocols:

-   **Handshake Protocol**: sets up the client and server session
-   <span style="font-weight: bold;">Change Cipher Spec Protocol</span>: establishes new agreement on the cipher suite used for the session
-   <span style="font-weight: bold;">Alert Protocol</span>: transmits warning and error messages between client and server
-   <span style="font-weight: bold;">Record Protocol</span>: comprises the above protocols and the application protocols

### Protocol stack

When you use, the protocol stack can be represented as follows:

<table>
         
         
         
         
         
   
   <tbody>
      <tr>
         <td><p>Handshake</p>         </td>
         <td><p>Change Cipher Spec Protocol</p>         </td>
         <td><p>Alert Protocol</p>         </td>
         <td><p>Application Protocols<br />
(FTP, ...)</p>         </td>
      </tr>
      <tr>
         <td><p>Record Protocol</p>         </td>
      </tr>
      <tr>
         <td><p>Network Protocols (TCP/IP ...)</p>         </td>
      </tr>
   </tbody>
</table>

The <span style="font-weight: bold;">Record Protocol layer</span> is responsible for:

-   Splitting data (maximum data block size is 16 KB)
-   Compressing data (optional)
-   Adding an integrity checksum (MAC)
-   Encrypting data

To establish a TLS connection, the connection procedure:

-   Sets up the record protocol layer: the layer is initialized with no integrity check and no encryption method (record layer state is then referred to as <span style="font-style: italic;">null with null null</span>)
-   Executes the "handshake" protocol: client and server exchange their certificates and agree on an encryption method
-   Executes the "change cipher" protocol: following this exchange, the record layer is reconfigured using the security parameters exchanged during the handshake

To test the connection, a <span style="font-style: italic;">finish</span> message is sent to test the established security parameters. The message contains a checksum of all the data sent since the beginning of the "handshake".

### Payload splitting

Gateway supports payload splitting for the following TLS handshake messages:

-   <span class="code">CERTIFICATE, </span>containing as payload Certificate Chains
-   <span class="code">CERTIFICATE REQUEST, </span>containing as payload Authority DN lists

<span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> can thus handle messages of this type with payloads up to 64KB. The payload is split into several TLS handshake messages sent (or received) in a row, each carrying a fragment of the total payload not more than 16KB in size.

> **Note:**
>
> Gateway does not support TLS Handshake messages longer than 16KB, that are not RFC-compliant. Be aware of the fact that current versions of multiple third party software such as openSSL, fileZilla, Mozilla and others, implement support for long (>16KB) Certificate Chains and Authority DN lists, by using handshake messages longer than 16KB in order to accommodate the entire size of the payload.

<span id="Using_SSL_or_TLS_with_transfer_protocols"></span>

## Using TLS with transfer protocols

Use of TLS is transparent for application protocols (for example, HTTPS, FTP, OFTP, and PeSIT). In most cases the TLS negotiation is triggered as soon as network connection is established.

<span style="font-weight: bold;">Note:</span> To secure a protocol with TLS you must use a different <span style="font-weight: bold;">SAP</span> (Service Access Point) than used for a connection in that protocol that is not secure.

<span id="TLS_SSL_and_FTP"></span>

### TLS and FTP

FTP implements the use of TLS by introducing commands that start a TLS session on both the client and the server.

You can configure Gateway to use TLS in implicit and explicit mode for an FTP connection using the parameter <span class="code" style="font-weight: bold;">ft\_sec\_option</span>. In the implicit mode the session starts directly in a secured mode.

An FTP session involves two connections:

-   Control connection
-   Data connection

Both connections must be secured.

You can establish the data connection in either of the two following modes:

-   Passive mode (the client initiates it)
-   Active mode (the server initiates it)

In passive mode, the data connection:

-   Uses TLS session caching
-   Reuses the security parameters negotiated for the control connection (there is a single handshake for both control and data connections)

<span id="TLS_SSL_and_SMTP_POP3"></span>

### TLS and SMTP/POP3

SMTP implements the use of TLS by introducing commands that start a TLS session on both the client and the server.

SMTP servers are usually secured using TLS explicitly and most will not accept an implicit TLS connection. However an implicit TLS connection is possible with some SMTP servers. As well, SMTP servers for a proxy mailer may impose TLS in implicit mode.

You can configure Gateway to use TLS in implicit and explicit mode for an SMTP or POP3 connection using the parameter <span class="code" style="font-weight: bold;">-ft\_sec\_option</span>.

POP3 can be secured using implicit TLS if the server requires it. Since implicit TLS connections are established during the protocol connection, immediate TLS negotiation is imposed.

<span id="Secure_protocols"></span>

### TLS and secure protocols

Some protocols are already secured. If you use TLS with those protocols, then the machine load is increased, but security is not increased. Recent protocols (or recent protocol extensions) implement the use of TLS by introducing commands that start a TLS session on both the client and the server (for example, SMTP, FTP). When you use TLS with FTP, all sessions (control and data) are encrypted, and, if possible, security parameters are reused to avoid a completely new handshake.

<span id="TLS_instance"></span>

## TLS instance

As described in the TLS protocol, a TLS session involves two steps:

-   A handshake session, where the communicating partners exchange security parameters
-   The data transfer itself

You can configure cryptographic and authentication parameters via the TLS Profile object. Gateway selects the Profile to use for a TLS session depending on the way the connection between the partners is established (incoming or outgoing connection).

### TLS handshake protocol initialization

You can impose the following handshake parameters via the <span style="font-weight: bold;">TLS Security Profile</span> configuration:

-   Negotiation/Renegotiation
-   Cache
-   Cipher suites
-   Protocol version

<span id="Incoming_connection"></span>

## Incoming connection

An incoming connection in TLS has a minimum of two levels of verification. The first is identification of a corresponding Network Profile object and the second is the identification and check of the Remote Site object and its parameters.

<span id="Retrieving_the_Network_Profile_object"></span>

### Retrieving the Network Profile object (netprof)

For incoming connections, the network parameters are used to retrieve a Network Profile object. The <span style="font-style: normal;">Network Profile</span> object indicates:

-   Whether to use TLS for this connection (<span style="font-weight: bold;">Network security</span> option set to <span style="font-weight: bold;">TLS</span>)
-   The name of the Security Profile to use

<span id="Checking_the_Remote_Site"></span>

### Checking the Remote Site

Following the TLS Handshake and the protocol connection, Gateway locates the Remote Site object involved in the current transfer.

Gateway then checks that the parameters negotiated during the TLS Handshake and the incoming Security Profile fields of the located Site (<span class="code">tls\_sprof\_in</span>) match. If the <span class="code">tls\_sprof\_in</span> parameter value is empty, no additional control is processed. If this control fails, the transfer is aborted.

Matching the Security Profile relies on:

-   Security Profile type (always server for incoming connections)
-   Exit scheduling value
-   Client and server authentication
-   Cipher suite used
-   Protocol used (TLSV1 or SSLV3)
-   User certificate sent
-   Remote certification chain received

The following diagram illustrates how Gateway implements security for incoming TLS connections:

<img src="/Images/Gateway/TLS_CheckSite.png" class="maxWidth" />

<span id="Outgoing_connection"></span>

## Outgoing connection

The Remote Site configuration determines whether or not to secure an outgoing connection.

If you specified a Security Profile in the outgoing Security Profile field (<span class="code" style="font-weight: bold;">tls\_sprof\_out</span>) of the Site, then this Security Profile is used to secure the connection.

The following diagram schematically illustrates how Gateway implements security for outgoing TLS connections:

<img src="/Images/Gateway/TLS_OutgoingConnection.png" class="mediumWidth" />

<span id="TLSextentions"></span>

## TLS Extensions

When connecting as a client, <span class="mc-variable suite_variables.GatewayName variable">Gateway</span> uses the host name of the remote partner as the value for the Server Name Indication extension, as specified by the [RFC6606](https://tools.ietf.org/html/rfc6066) from the IETF.

<span class="mc-variable suite_variables.GatewayName variable">Gateway</span> uses this value as is, as long as it doesn't resemble an IP address (IPV4 or IPV6), and as long as it is exclusively written with ASCII characters. Also, the RFC requires that the value sent with this extension must be the fully qualified domain name of the server.

Restrictions:

-   In server mode, this extension is ignored.
-   This extension is sent only when Gateway attempts to negotiate version 1.2 of TLS.
-   The `server_name` extension is not added if TLS is done in <span class="mc-variable suite_variables.SecureRelayName variable">Secure Relay</span> (XSR termination for outgoing connections)

Related topics

<a href="managing_tls" class="MCXref xref">Managing TLS</a>

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
