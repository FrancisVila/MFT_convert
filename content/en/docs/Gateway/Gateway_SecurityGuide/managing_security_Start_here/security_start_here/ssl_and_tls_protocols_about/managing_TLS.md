{
    "title": "Managing TLS",
    "linkTitle": "Managing TLS",
    "weight": "210"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Security

[Accepted authorities list](#Accepted_authorities_list)

[Certificate chain management](#Certificate_chain_management)

[Server authentication policy](#Server_authentication_policy)

[Client authentication policy](#Client_authentication_policy)

[Defining User Certificate list](#Defining_User_Certificate_list)

[Using security without certificates](#Using_security_without_certificates)

[Disabling close notify messages in TLS](#Disabling_close_notify_messages_in_TLS)

[Secure renegotiation in TLS](#Secure)

[Certification path building mode in TLS](#Certification_path_building_mode)

<span id="Accepted_authorities_list"></span>

## Accepted authorities list

### Building a list

To send a trusted authorities DN list to the client, the server refers to the current profile and builds the list according to the corresponding parameters. Each accepted authority is referenced by its local name (its authority certificate must be present in the local database). For each name given, the Security server finds the corresponding certificate and DER-encodes its subject name. It then sends the resulting buffer to the client.

### Receiving a list

When the Security server receives the accepted authorities distinguished names list from the server, it parses its local database and determines whether each corresponding authority certificate is present or not. If the authority certificate is present, the certificate reference is memorized for later use when the certification path to send is built. If it is not present, this means that the authority is unknown and cannot be trusted. The distinguished name is ignored.

<span id="Certificate_chain_management"></span>

## Certificate chain management

### Sending a certificate chain

#### Server case

The server can send any of the current Security Profile user certificates. If the server can send more than one user certificate, it selects the first certificate in the Security Profile (sprof) <span style="font-weight: bold;">UserCertificate</span> field.

The Security server builds the corresponding certificate chain step by step. For each certificate, it identifies its issuer certificate and so on, until it reaches a root certificate.

Each certificate must be activated before you can send it. Otherwise, an error occurs.

To optimize performance, there are no signature, validity, or other checks made on the certificate chain that the server sends. The receiver is responsible for verifying that the certificate chain is correct.

#### Client case

The client builds a certificate chain that matches the received distinguished name list of accepted authorities received. The available authority references that correspond to those sent are stored in the memory. The Security server refers to the user certificates defined in the current Profile. For each user certificate, the Security server locates the root authority that this certificate is linked to and sends the first matching authority of the known accepted authorities.

### Checking a certificate chain

For each received certificate, the Security server checks for the validity of the whole chain. It checks:

-   Each signature
-   The time validity of each certificate
-   Whether matching criteria are defined in the Profile (template matching). Each received certificate must verify one or more of them.
-   The root certificate that ends the certificate chain is known and present in the local database. If not, the received certificate chain is considered invalid.

<span id="Server_authentication_policy"></span>

## Server authentication policy

Since the TLS protocol indicates that the server must send a certificate whenever the agreed-upon key exchange is not anonymous, the <span class="code" style="font-weight: bold;">server\_auth\_policy</span> Security Profile field is meaningless. As a result, whatever its value in the Security Profile for the current secured connection, it will be internally forced to <span style="font-style: italic;">TLS\_AUT\_MANDATORY</span>.

For compatibility purposes, this field is still mandatory when you create a new Security Profile. It is recommended to set this parameter to <span style="font-style: italic;">TLS\_AUT\_MANDATORY</span> in the text file that describes the Security Profile.

<span id="Client_authentication_policy"></span>

## Client authentication policy

This section describes Gateway behavior depending on the value of the <span style="font-weight: bold;">client\_auth\_policy</span> field in the current TLS (or SSL) connection Security Profile.

### Client side

As a client, <span style="font-weight: bold;">client\_auth\_policy</span> is taken into account and comes from the Remote Site outgoing Security Profile.

If you set <span style="font-weight: bold;">client\_auth\_policy</span> to <span style="font-style: italic;">TLS\_AUT\_OPTIONAL</span>, and if it is not possible to build a local certification path from one of the available user certificates (defined in the <span style="font-weight: bold;">UserLocalCertificate</span> section of the current Profile) to one of the accepted authorities list previously received from the server, then an alert (SSL V3) or an empty certification path (TLS V1) is sent to the server. The server is then responsible for closing the connection or continuing the handshake phase.

If you set the <span style="font-weight: bold;">client\_auth\_policy</span> field to <span style="font-style: italic;">TLS\_AUT\_MANDATORY</span>, Gateway sends an alert (handshake failure) and closes the connection if no valid certification path can be built according to the accepted authorities list received from the server. In this case, connection closure (on the client side) occurs regardless of the client authentication policy on the server side. This option is useful if you want reciprocal authentication for both incoming and outgoing connections (secured with TLS or SSL).

### Server side

As a server, the <span style="font-weight: bold;">client\_auth\_policy</span> field is taken into account and comes from the Security Profile selected depending on the selected Network Profile (<span style="font-style: italic;">netprof)</span> field.

If you set <span style="font-weight: bold;">client\_auth\_policy</span> to <span style="font-style: italic;">TLS\_AUT\_OPTIONAL</span>, the server will not close the current connection, regardless of whether the client has succeeded its authentication or not. The TLS (or SSL) handshake phase will continue.

If you set <span style="font-weight: bold;">client\_auth\_policy</span> to <span style="font-style: italic;">TLS\_AUT\_MANDATORY</span>, the server closes the current TLS (or SSL) connection if no valid certificate (matching one of the locally accepted authorities list) is received from the client.

In addition, Gateway implements another control after the protocol connection. At this stage, the TLS (or SSL) handshake is finished and Gateway knows whether the current connection client is authenticated or not. Gateway checks the <span style="font-weight: bold;">client\_auth\_policy</span> attribute of the Remote Site (corresponding to the connected client) incoming Security Profile. If this parameter is set to <span style="font-style: italic;">TLS\_AUT\_MANDATORY</span> and if the client failed its authentication, the server closes the connection and aborts the transfer.

<span style="font-weight: bold;">Note:</span> The incoming Security Profile parameter in the Remote Site is an optional field. If you do not set a value for this field, no additional control is processed.

<span id="Defining_User_Certificate_list"></span>

## Defining User Certificate list

This section describes the rules applied when you use several user certificates in Gateway Security Profile configuration.

Public Key Infrastructure technology and certificate-based authentication are relevant for securing data exchanges over the Internet. This means that it may be useful for a TLS client to have several user certificates for its authentication and to select which user certificate to send depending on the accepted authorities list received from the server.

Gateway enables you to define a user certificate list via the Security Profile <span class="code">UserLocalCertificate</span> section definition.

### Example



    name = "SPROFTEST"
    type = CLIENT
    cache_enabled = Y
    renegotiate_enabled = Y
    exit_scheduling = N
    client_auth_policy = TLS_AUT_MANDATORY
    server_auth_policy = TLS_AUT_MANDATORY
    tls_versions = TLSv1 SSLv3
    path_depth = 7
    cipher_suites = RSA_WITH_3DES_EDE_CBC_SHA
    [UserLocalCertificate]
    certificate_name = "USER1"
    certificate_name = "USER2"
    [AcceptedAuthorities]

In this sample, the <span style="font-weight: bold;">User1</span> certificate is linked to the root certificate <span style="font-weight: bold;">ROOT1</span> and the <span style="font-weight: bold;">User2</span> certificate is linked to the root certificate <span style="font-weight: bold;">ROOT2</span>.

### Server Side

The TLS (or SSL) server sends its accepted authorities list.

### Client Side

If <span style="font-weight: bold;">ROOT1</span> is included in the accepted authorities list received from the server whereas <span style="font-weight: bold;">ROOT2</span> is refused, the <span style="font-weight: bold;">User1</span> certificate will be sent.

If the server refuses <span style="font-weight: bold;">ROOT1</span> and accepts <span style="font-weight: bold;">ROOT2</span>, the<span style="font-weight: bold;"> User2</span> certificate is sent.

If the server accepts both <span style="font-weight: bold;">ROOT1</span> and <span style="font-weight: bold;">ROOT2</span>, the first valid user certificate chain is sent, in this case <span style="font-weight: bold;">User1</span>.

<span style="font-weight: bold;">Note:</span> When you use a CLIENT\_AND\_SERVER Security Profile, the server sends the first certificate of the <span class="code">UserLocalCertificate</span> section, since there are no constraints on the server sending one particular certificate rather than another for its authentication.

<span id="Using_security_without_certificates"></span>

## Using security without certificates

This feature enables TLS-secured communications with encrypted and MAC-controlled data without requiring any X.509 certificates. The client and server are both anonymous. This method uses an RSA anonymous key exchange algorithm. To configure this feature in Security Profiles, use the new set of cipher suites known as <span style="font-weight: bold;">TLS\_RSA\_ANON\_WITH\_xxx\_yyy</span>.

Using security without certificates provides the same high level of encryption and MAC-checking on the data flow, while avoiding the certificate management process.

### Principles

An RSA public key provided by the server implements the RSA anonymous key exchange, rather than the RSA key included in the server certificate.

The "ServerKeyExchange" handshake message transmits the server public key used to encrypt the session key (premaster secret) sent by the client. All certificate-related messages are discarded (Certificate, CertificateRequest and CertificateVerify).

Supported server RSA key lengths: 512, 1024, 2048 4096 and 8192 bits.

### New cipher suites

The binary values of the RSA anonymous cipher suites are:



    RSA_ANON_WITH_NULL_MD5 { 0xFF, 0x01 }
    RSA_ANON_WITH_NULL_SHA { 0xFF, 0x02 }
    RSA_ANON_WITH_RC4_128_MD5 { 0xFF, 0x04 }
    RSA_ANON_WITH_RC4_128_SHA { 0xFF, 0x05 }
    RSA_ANON_WITH_DES_CBC_SHA { 0xFF, 0x09 }
    RSA_ANON_WITH_3DES_EDE_CBC_SHA { 0xFF, 0x0A }
    RSA_ANON_WITH_AES_128_CBC_SHA { 0xFF, 0x2F }

### Security Profile sample

#### Client side:



    name = "PROFILE_CLIENT_1"
    type = CLIENT
    tls_versions = TLSv1
    cache_enabled = Y
    renegotiate_enabled = N
    exit_scheduling = N
    client_auth_policy = TLS_AUT_ANONYMOUS
    server_auth_policy = TLS_AUT_ANONYMOUS
    path_depth = 2
    cipher_suites = RSA_ANON_WITH_AES_128_CBC_SHA
    [UserLocalCertificate]
    [AcceptedAuthorities]

#### Server side:



    name = " PROFILE_SERVER_1"
    type = SERVER
    tls_versions = TLSv1
    cache_enabled = Y
    renegotiate_enabled = N
    exit_scheduling = N
    client_auth_policy = TLS_AUT_ANONYMOUS
    server_auth_policy = TLS_AUT_ANONYMOUS
    path_depth = 2
    cipher_suites = RSA_ANON_WITH_AES_128_CBC_SHA
    [UserLocalCertificate]
    [AcceptedAuthorities]

### Restrictions

This feature is fully compliant with the TLS specification in RFC 2246. However, it is specific to Axway Transfer products and may not interoperate with other TLS products.

Users should be aware that the lack of authentication may make an attack easier, especially those known as "man in the middle" attacks. As a result, this feature is mostly intended for the case where the overlaying protocol or application provides an authentication or login mechanism.

<span id="Disabling_close_notify_messages_in_TLS"></span>

## Disabling close notify messages in TLS

This is a workaround for TLS interoperability. Some FTP clients (CuteFTP for example) report an error when they receive a close notify alert message on the data connection. This message is supposed to be exchanged before closing a connection (refer to <span style="font-style: italic;">RFC 2246</span>), thus ensuring that the TLS session parameters can be cached by peers.

The workaround consists in closing TLS connections without sending the close notify message.

However, if a close notify message is received, it is acknowledged with another close notify message.

To <span style="font-style: italic;">disable</span> close notify messages, set the parameter <span class="code" style="font-weight: bold;">close\_notify\_disabled</span> in the <span style="font-style: italic;">sprof</span> files to Y.

close\_notify\_disabled = 'Y'

secadm import\_sprof  -sprof\_file &lt;<span style="font-style: italic;">filename</span>&gt;

To <span style="font-style: italic;">enable</span> close notify messages (default mode), set the parameter to N.

close\_notify\_disabled = 'N'

secadm import\_sprof  -sprof\_file &lt;<span style="font-style: italic;">filename</span>&gt;

<span id="Secure"></span>

## Secure renegotiation in TLS

A TLS renegotiation vulnerability has been discovered in the TLS and the SSL 3.0 protocols which allows a man-in-the-middle (MITM) attacker to inject an unauthenticated request of his choice as a prefix to a victim's session. Different studies show that protocols on top of TLS like HTTP, FTP or SMTP are all affected to varying degrees, but most of the attacks are documented on HTTPS. The fix for this issue was proposed by the engineering task force as a TLS extension described in the RFC 5746 document.

Gateway fully supports RFC 5746 and the changes can be seen at the Security Profile level and at the Log level as detailed below. The extension will always be active in Gateway since there are no consequences to interoperating with implementations without the upgrade.

### Security Profile level

There is one additional TLS profile parameter 'Refuse legacy partners' (or <span class="code">sp\_un-upgraded\_partner\_refused</span> in command line tools) which allows a user to close a connection from a TLS un-upgraded partner from the start (from the initial TLS handshake).

In addition, there is a redesigned parameter - 'Renegotiation enabled' (or <span class="code">sp\_renegotiate\_enabled</span> in the command line tools) which has increased the number of values from a Boolean type (with yes or no as possible options) to a 4-option type: disabled, unrestricted, secure and legacy.

When dealing with an upgraded partner, the only situation where renegotiation is refused is when it is disabled from the TLS profile.

On the other hand, if connecting to an un-upgraded partner, for compatibility reasons, the response to a renegotiation request will depend on the 'Renegotiation enabled' flag from the TLS profile (although in this case RFC 5746 recommends refusing renegotiations):

-   **disabled, secure**: Refuse renegotiation (send the `no_renegotiation` warning alert) and continue the connection.
-   **unrestricted**: Both in client and server mode, accept renegotiation handshake. The connection is vulnerable to attacks.
-   **legacy**: This option means that Gateway in client mode will accept renegotiation requests, although the connection is vulnerable to attacks. In server mode, Gateway will refuse renegotiation and continue the connection. This setting will force partners to upgrade their client applications to be able to renegotiate with Gateway, but will not interrupt renegotiation when Gateway is in client mode connection to a legacy server.

> Although refusing renegotiation is a TLS alert at warning level and the connection can continue afterwards, some implementations are geared towards security with a lack of compatibility and choose to end the connection.

Related topics

<a href="../tls_security_profiles__gui_" class="MCXref xref">Managing TLS Security Profiles</a>

## DHE key exchange in TLS

When using DHE cipher suites in server security profiles, Gateway, as TLS server, needs a \[P,G\] pair of Diffie-Hellman parameters for the ephemeral DH keys generation. The way in which Gateway obtains these parameters is configurable through the command line, using the <span class="code">peluconf </span>command.

The configuration parameters related to DH params generation are as follows:

<span class="code" style="font-style: normal;">\[monitor\]secs\_dh\_params\_mode</span>

Values are from *0* to *2*. Default value is *2*. Meaning of values are:

-   *0* - DH params are generated at Gateway startup, using the bitsize indicated in the parameter <span class="code">\[monitor\]secs\_dh\_params\_bitnum\_idx</span> (see below).  
    **Caution**: even for minimum-size DH parameters, Gateway's SECS process may be blocked a long time at Gateway start, depending on the hosts entropy. This option is **to be used with care**.
-   *1* - DH params are loaded from a file indicated by the parameter <span class="code">\[monitor\]secs\_dh\_params\_file</span>.
-   *2* - DH params are provided from OpenSSL, and the used values are specified in a RFC (it is the 2048/256 MODP group in http://www.ietf.org/rfc/rfc5114)  

<span class="code" style="font-style: normal;">\[monitor\]secs\_dh\_params\_bitnum\_idx</span>

Values are from *0* to *2*. Default value is <span class="code" style="font-weight: bold;">2</span>. Parameter has a meaning only if <span class="code">\[monitor\]secs\_dh\_params\_mode</span>=*0* (generated DH params). Meaning of values are:

-   *0* - 1024 bits for P
-   *1* - 2048 bits for P
-   *2* - 4096 bits for P

Value for DH generator (G) will be 2 or 5, as these are the only supported values in OpenSSL.  
**Note**: the generation in Gateway of parameters longer than 1024 bits may take a very long time (minutes for 2048 bits, or even hours for 4096 bits).

*\[monitor\]secs\_dh\_params\_file*

*This parameter indicates the file where Gateway is to find the DH params at startup. The file MUST be in <span class="code">DER </span>*format.

-   This parameter has a meaning only if <span class="code">\[monitor\]secs\_dh\_params\_mode</span>=*1*, meaning DH mode is *load DH params from file*.

    Note: If error occurs when loading/generating DH params, DHE ciphers cannot be used in TLS server mode.

    Note2: If DHE ciphers are to be used in client mode only, there is no need for DH params, as the client will use the server communicated DH params to generate the client ephemeral keys.

<span class="code" style="font-style: normal;">\[monitor\]secs\_dh\_params\_file</span>

This parameter indicates the file where Gateway is to find the DH params at startup. The file MUST be in <span class="code">DER </span>format.

-   Note: If error occurs when loading/generating DH params, DHE ciphers cannot be used in TLS server mode.
-   Note2: If DHE ciphers are to be used in client mode only, there is no need for DH params, as the client will use the server communicated DH params to generate the client ephemeral keys.

<span id="Avoiding_weak_crypto"></span>

### Avoiding weak cryptography

Using DHE parameters of 2048 bits or larger is strongly recommended. To enforce this security recommendation, Gateway has added a configuration parameter: `[tls]enable_weak_crypto`. This parameter, when set to `no`, effectively prevents the TLS DHE key exchange with an insecure (less than 2048 bits) DHE key size.

If Gateway encounters DH key generation parameters with a P parameter of less than the recommended size:

-   a message is logged
-   added to that, if `[tls]enable_weak_crypto` is set to `no`, the TLS\_DHE ciphers cannot be used in TLS server mode.

> **Note:**
>
> For compatibility reasons, the parameter’s default value is yes. We strongly recommend to set \[tls\]enable\_weak\_crypto to no, and to set DH key generation configuration parameters accordingly.

> **Note:**
>
> If DHE ciphers are to be used in client mode, Gateway will apply the \[tls\]enable\_weak\_crypto parameter on the server communicated DH parameters.

<span id="Certification_path_building_mode"></span>

## Certification path building mode in TLS

Gaetway has a new way of building certificate paths, both in server and client mode. It is an implementation of the Internet X.509 Public Key Infrastructure: Certification Path Building specification, also known as RFC4158.

This mode of operation can be configured on individual security profiles using the attribute `sprof_path_build_mode`, (short version `sppbm `), having 2 possible values:

-   *legacy*
-   *rfc4158*

The purpose of this algorithm is to support multiple PKI structures as well as easy certificate renewal across all levels of the certification path. Note that when renewing a certificate, as long as the legacy one is valid, it will continue to be used for securing TLS connections (to ease the transition to the new RFC4158). This however depends on the order in which the certificates are selected on the security profile (this is valid for end user certificates). Renewed intermediary or root certificates are handled transparently when the certification path is built. Basically once one of the certificates expires, it will be ignored by the path building algorithm and the product will attempt to use (re)new(ed) certificates.

One mandatory requirement of this mode of operation is that all certificates MUST have the subject key identifier and authority key identifier extensions (the second extension is optional on root and self signed user certificates). This is not enforced by the product to allow users to operate the product with certificates that might not have these extensions (using the legacy path building mode). If the certificates already present in the product have these extensions, it is possible to use them with the new path building mode.

### Local certificates on negotiated cipher: only if compatible

On a negotiated cipher, Gateway selects a local certificate **only** if its key is compatible with the key exchange algorithm of the negotiated cipher.

This allows for multiple-certificate configurations, covering different security requirements: old software that only supports RSA ciphers, alongside new software supporting elliptic curve cryptography.

If Gateway finds no matching certificate, a warning is logged, and the connection continues only if the authentication policy configured on the security profile is optional.

Related topics

<a href="../tls_security_profiles__gui_" class="MCXref xref">Managing TLS Security Profiles</a>

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
