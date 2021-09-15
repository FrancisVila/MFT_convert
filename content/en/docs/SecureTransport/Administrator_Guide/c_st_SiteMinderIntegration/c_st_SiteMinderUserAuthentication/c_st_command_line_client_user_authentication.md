{
    "title": "Command line client (FTP, FTPS, HTTPS, and SSH) user authentication",
    "linkTitle": "Command line client (FTP, FTPS, HTTPS, and SSH) user authentication",
    "weight": "170"
}Command line clients log on to SecureTransport directly, not through the SSO portal. If the client presents a user name and password or a certificate, SecureTransport first tries to authenticate the user by comparing it to the existing user profiles. In case SecureTransport cannot authenticate the user, it passes the user name and password to SiteMinder for authentication. If all authentication attempts fail, the user receives an error message and is disconnected.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The <span>SecureTransport</span> command line client does not work through a Web gateway or proxy (even when using HTTPS). So, <span>SecureTransport</span> Server must be made directly accessible to command line clients.         </td>
      </tr>
</table>

**Related topics:**

-   [Web client (HTTP and HTTPS) user authentication](../c_st_web_client_user_authentication)
-   [User access control (authorization)](../c_st_user_access_control)
