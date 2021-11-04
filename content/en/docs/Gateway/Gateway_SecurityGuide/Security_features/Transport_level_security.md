{
    "title": "Transport level security",
    "linkTitle": "Transport level security",
    "weight": "90"
}At the transport level, Gateway provides support for:

Protocol and network translation

SSL (Secure Socket Layer) / TLS (Transport Layer Security) on incoming and outgoing connections

## SSL/TLS protocol

Most protocols supported in Gateway can be secured using SSL/TLS, but connections are not secured by default. Protocols that can be secured are:

-   HTTP <span style="font-family: Wingdings;">à</span> HTTPS
-   FTP <span style="font-family: Wingdings;">à</span> FTPS (implicit or explicit)
-   EDIINT protocols: AS1, AS2, AS3
-   RosettaNet
-   OFTP
-   PeSIT D and PeSIT E
-   PEL
-   SMTP
-   POP3

To add SSL/TLS for incoming connections, a server SSL/TLS profile object must be created and attached to the network profile corresponding to the protocol listen point. In the security profile object you can specify

-   The client authentication type
-   The version of TLS to use
-   The accepted cipher suites – Gateway currently supports only RSA and ECDSA based cipher suites, but the list can be extended in combination with Secure Relay and security termination  
    **Note:** several cipher suites are marked as “weak”, and cannot be used unless the configuration parameter <span class="code">\[tls\]enable\_weak\_ciphers</span> is set to <span class="code">yes</span>. These cipher suites could be removed in a future version. We recommend against using weak cipher suites.  
    For more information regarding the accepted cipher suites, refer to [TLS cipher suites](../../managing_security_start_here/security_start_here/ssl_and_tls_protocols_about/tls_cipher_suites)
-   Accepted authorities
-   Certificate for server side authentication (local PKI or PassportPS)
-   Different options for TLS protocol: session cache, key renegotiation, close notify exchange etc

To add SSL/TLS for outgoing connections, a client SSL/TLS profile object must be created and attached to the remote site used for connecting to partners

## SSH/SFTP protocol

Authentication: The claimed identity of the client user is checked via a private/public key pair or user/password.

Supported key algorithms: DSA, RSA, ECDSA (NISTP256, NISTP384, NISTP521), x.509v3 certificate (RSA keys only)

Supported key exchange algorithms: Diffie-Hellman key exchange with SHA-1 and Oakley Group 2 (diffie-hellman-group1-sha1), Diffie-Hellman Group and Key Exchange with SHA-1 (diffie-hellman-group-exchange-sha1), Diffie-Hellman Group and Key Exchange with SHA-256 (diffie-hellman-group-exchange-sha256), Diffie-Hellman key exchange with SHA-1 as HASH and Oakley Group 14 (diffie-hellman-group14-sha1), and ephemeral-ephemeral elliptic curve Diffie-Hellman on nistp256 with SHA-256 (ecdh-sha2-nistp256), nistp384 with SHA-384 (ecdh-sha2-nistp384) and nistp521 with SHA-512 (ecdh-sha2-nistp521). **Note**: Gateway does not support Kerberos or GSSAPI authentication in either SFTP server or client mode.

Supported encryption algorithms: AES128\_CBC, 3DES\_CBC, AES256\_CBC, AES128\_CTR, AES256\_CTR

Supported MAC algorithms: SHA1, MD5, SHA1\_96, MD5\_96, SHA256

Security features:

-   Integrity: Adds a message abstract (also referred to as a hash code or message digest) to the data to ensure that it arrives at its destination intact. In SSH the hash code, referred to as MAC (Message Authentication Code), is added to each message sent using the negotiated MAC algorithm. Refer to Certificates and keys.
-   Confidentiality (also referred to as Privacy): Prevents third parties from accessing data that is not intended for them. Typically, data is protected using either symmetrical or asymmetrical encryption techniques. Refer to Axway Gateway security features.
-   Authentication: The claimed identity of the client user is checked via a private/public key pair or user/password.
-   For more details see User guide > [SFTP](#)

For detailed information please refer to <a href="../" class="MCXref xref">Security features</a>

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
