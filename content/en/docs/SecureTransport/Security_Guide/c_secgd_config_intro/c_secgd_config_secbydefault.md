{
    "title": "Secure by default configuration",
    "linkTitle": "Secure by default configuration",
    "weight": "130"
}SecureTransport is secured by default after initial setup and configuration. You must explicitly assign a certificate alias for the protocol servers you need secured. The default configuration for TLS protocols and ciphers is secure and should not be changed unless specifically instructed. Currently, SecureTransport supports the TLSv1, TLSv1.1, and TLSv1.2 protocols. For a successful handshake between the server and the client, both must have a matching TLS protocol and at least one ciphersuite affiliated with that protocol.

SecureTransport has a variety of configuration options that you can use to set up HTTP security headers, redirect and referrer validation, and thus, protect against cross-site scripting (XSS), clickjacking and other code injection attacks. For more information, see [Security-related HTTP headers and policies](../security_policies).
