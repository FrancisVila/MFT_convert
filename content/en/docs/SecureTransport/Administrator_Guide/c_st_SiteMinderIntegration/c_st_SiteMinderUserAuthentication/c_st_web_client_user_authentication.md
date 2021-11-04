{
    "title": "Web client (HTTP and HTTPS) user authentication",
    "linkTitle": "Web client (HTTP and HTTPS) user authentication",
    "weight": "150"
}Web clients can log in to <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> directly or through the SiteMinder Single Sign-On (SSO) portal. Depending on the SiteMinder configuration, when a web client logs in, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> can require a client certificate, which it presents to SiteMinder for authentication.

When a web client logs on through the SiteMinder SSO portal, the portal authenticates the user and provides the client with a SiteMinder session cookie. When the client tries to access a <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> resource, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> presents the user’s session cookie to SiteMinder for authentication.

> **Note:**
>
> Session cookies are by domain, so the SiteMinder SSO portal must be in the same domain as the SecureTransport Server.

> **Note:**
>
> The SiteMinder SSO portal must be accessed using a fully-qualified domain name (FQDN) because SiteMinder uses domain cookies, and it is possible that different browsers can handle the conversion from partial name to FQDN incorrectly. In the latter case, access to the SSO portal can be denied.

**Related topics:**

-   <a href="../c_st_command_line_client_user_authentication" class="MCXref xref">Command line client (FTP, FTPS, HTTPS, and SSH) user authentication</a>
-   <a href="../c_st_user_access_control" class="MCXref xref">User access control (authorization)</a>