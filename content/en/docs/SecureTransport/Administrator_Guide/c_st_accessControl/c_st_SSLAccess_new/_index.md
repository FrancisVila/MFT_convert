{
    "title": "Secure Socket Layer access",
    "linkTitle": "Secure Socket Layer access",
    "weight": "180"
}The Secure Socket Layer (SSL) is the security protocol used by <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> to encrypt communication between the server and its clients. SSL requires the server to have a certificate, which is exchanged with the client during the SSL handshake. SSL allows the client to have a certificate that is presented to the server and can be used to authenticate the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> user as an alternative to authenticating the user through a password. SSL is also used by <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> to transfer files securely.

Based on user class, encryption (SSL) can be set as optional or mandatory.

-   If SSL is mandatory, the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server only accepts SSL connections. If SSL is not enabled at the client end, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> refuses the connection.
-   If SSL is optional, then both SSL and non-SSL connections are enabled. If the client requests an SSL connection, then it is negotiated. Otherwise, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> accepts the connection to proceed without encryption. If the client certificate verification is enabled, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> checks the validity and authenticity of the certificate presented by the client. If SSL is optional and the client requests SSL, but the client certificate verification fails, the client is allowed to log in with a user name and password.

If your <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> deployment includes <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge servers in a peripheral network (DMZ), you should configure SSL access exactly the same on both <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge and <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server.

The following topics describe SSL and SSH authentication and provide how-to instructions for managing SSL access:

-   <a href="c_st_ssl_ssh_new" class="MCXref xref">SSL and SSH</a> - Describe SSL and SSH authentication.
-   <a href="t_st_sslaccess_new" class="MCXref xref">Manage SSL access</a> - Provides how-to instructions for managing SSL access.
