{
    "title": "Secure by default configuration",
    "linkTitle": "Secure by default configuration",
    "weight": "130"
}{{< SecureTransport/componentshortname  >}} is secured by default after initial setup and configuration. You must explicitly assign a certificate alias for the protocol servers you need secured. The default configuration for TLS protocols and ciphers is secure and should not be changed unless specifically instructed.

{{< SecureTransport/componentshortname  >}} supports the TLSv1, TLSv1.1, TLSv1.2, and TLSv1.3 protocols. Axway strongly recommends using TLS 1.2 or TLSv1.3. TLSv1.3 is enabled by default on fresh installations of SecureTransport 5.5-20210930 or later. On upgraded instances, it is disabled and must be enabled manually following the [procedure](../enable-tls13). Note that for a successful handshake between the server and the client, both must have a matching TLS protocol and at least one cipher suite affiliated with that protocol.

{{< SecureTransport/componentshortname  >}} has a variety of configuration options that you can use to set up HTTP security headers, redirect and referrer validation, and thus, protect against cross-site scripting (XSS), clickjacking, and other code injection attacks. For more information, see <a href="../security_policies" class="MCXref xref">Security-related HTTP headers and policies</a>.
