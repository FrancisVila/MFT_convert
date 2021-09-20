{
    "title": "Configure client certificate authentication settings",
    "linkTitle": "Configure client certificate authentication settings",
    "weight": "180"
}Instead of logging on through the SSO portal, web clients and command line clients can log on to SecureTransport directly and request authentication using a client certificate. SecureTransport then presents the client certificate to SiteMinder for authentication. To configure SecureTransport to perform client certificate authentication using SiteMinder, complete these steps:

1.  Import into SecureTransport the trusted Certificate Authority (CA) certificates for the client certificates to be authenticated. Client certificates are authenticated using indirect trust. For instructions on importing trusted CA certificates, refer to [Import a trusted CA certificate](../../c_st_setup/c_st_certificates/t_st_trustedcas).
2.  Restart the SSH Server.
3.  Bounce the SecureTransport Servers.