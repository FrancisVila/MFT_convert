{
    "title": "Secure Socket Layer access",
    "linkTitle": "Secure Socket Layer access",
    "weight": "190"
}The Secure Socket Layer (SSL) is the security protocol used by SecureTransport to encrypt communication between the server and its clients. SSL requires the server to have a certificate, which is exchanged with the client during the SSL handshake. SSL allows the client to have a certificate that is presented to the server and can be used to authenticate the SecureTransport user as an alternative to authenticating the user through a password. SSL is also used by SecureTransport to transfer files securely.

Based on user class, encryption (SSL) can be set as optional or mandatory.

-   If SSL is mandatory, the SecureTransport Server only accepts SSL connections. If SSL is not enabled at the client end, SecureTransport refuses the connection.
-   If SSL is optional, then both SSL and non-SSL connections are enabled. If the client requests an SSL connection, then it is negotiated. Otherwise, SecureTransport accepts the connection to proceed without encryption. If the client certificate verification is enabled, SecureTransport checks the validity and authenticity of the certificate presented by the client. If SSL is optional and the client requests SSL, but the client certificate verification fails, the client is allowed to log in with a user name and password.

If your SecureTransport deployment includes SecureTransport Edge servers in a peripheral network (DMZ), you should configure SSL access exactly the same on both SecureTransport Edge and SecureTransport Server.

The following topics describe SSL and SSH authentication and provide how-to instructions for managing SSL access:

-   [SSL and SSH](c_st_ssl_ssh_new) - Describe SSL and SSH authentication.
-   [Manage SSL access](t_st_sslaccess_new) - Provides how-to instructions for managing SSL access.