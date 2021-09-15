{
    "title": "Web client (HTTP and HTTPS) user authentication",
    "linkTitle": "Web client (HTTP and HTTPS) user authentication",
    "weight": "160"
}Web clients can log in to SecureTransport directly or through the SiteMinder Single Sign-On (SSO) portal. Depending on the SiteMinder configuration, when a web client logs in, SecureTransport can require a client certificate, which it presents to SiteMinder for authentication.

When a web client logs on through the SiteMinder SSO portal, the portal authenticates the user and provides the client with a SiteMinder session cookie. When the client tries to access a SecureTransport resource, SecureTransport presents the user’s session cookie to SiteMinder for authentication.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Session cookies are by domain, so the SiteMinder SSO portal must be in the same domain as the <span>SecureTransport</span> Server.         </td>
      </tr>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The SiteMinder SSO portal must be accessed using a fully-qualified domain name (FQDN) because SiteMinder uses domain cookies, and it is possible that different browsers can handle the conversion from partial name to FQDN incorrectly. In the latter case, access to the SSO portal can be denied.         </td>
      </tr>
</table>

**Related topics:**

-   [Command line client (FTP, FTPS, HTTPS, and SSH) user authentication](../c_st_command_line_client_user_authentication)
-   [User access control (authorization)](../c_st_user_access_control)
