{
    "title": "Command line client (FTP, FTPS, HTTPS, and SSH) user authentication",
    "linkTitle": "Command line client (FTP, FTPS, HTTPS, and SSH) user authentication",
    "weight": "160"
}Command line clients log on to {{< SecureTransport/componentshortname  >}} directly, not through the SSO portal. If the client presents a user name and password or a certificate, {{< SecureTransport/componentshortname  >}} first tries to authenticate the user by comparing it to the existing user profiles. In case {{< SecureTransport/componentshortname  >}} cannot authenticate the user, it passes the user name and password to SiteMinder for authentication. If all authentication attempts fail, the user receives an error message and is disconnected.

> **Note:**
>
> The SecureTransport command line client does not work through a Web gateway or proxy (even when using HTTPS). So, SecureTransport Server must be made directly accessible to command line clients.

**Related topics:**

-   [Web client (HTTP and HTTPS) user authentication](../c_st_web_client_user_authentication)
-   [User access control (authorization)](../c_st_user_access_control)
