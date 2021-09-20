{
    "title": "User access control (authorization)",
    "linkTitle": "User access control (authorization)",
    "weight": "180"
}Regardless of the type of client, access control is always performed by SecureTransport, which uses SiteMinder rules to obtain the user’s read/write authority to a particular resource. The SSO portal cannot perform access control for SecureTransport resources.

After a user is authenticated, SecureTransport sends an authorization request to SiteMinder to determine whether the user has read/write access to the requested resource. If SiteMinder grants the appropriate access level, SecureTransport proceeds with the file operation.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The SiteMinder SSO portal must be accessed using FQDN because SiteMinder uses domain cookies and it is possible that different browsers can handle the conversion from partial name to FQDN in an incorrect manner. In the latter case, access to the SSO portal can be denied.         </td>
      </tr>
</table>

The following topics describe the SiteMinder authorization rules and provide an authorization request example:

-   [SiteMinder authorization rules](#siteminder)
-   [Example authorization request](#example)

**Related topics:**

-   [Web client (HTTP and HTTPS) user authentication](../c_st_web_client_user_authentication)
-   [Command line client (FTP, FTPS, HTTPS, and SSH) user authentication](../c_st_command_line_client_user_authentication)

## <span id="SiteMinder"></span>SiteMinder authorization rules

Configure the SiteMinder authorization rules to accommodate SecureTransport authorization requests. A SecureTransport authorization request contains the following elements:

-   **Resource Path** – The absolute URI of the resource being accessed by the user. SecureTransport determines the actual file path and uses that file path as the URI. This URI can be modified (section removed or prefix added) based on the **File Storage Root Path** and **SiteMinder Path Prefix** in the SecureTransport SiteMinder settings. (For details, see [Configure SiteMinder settings in SecureTransport](../../t_st_sitemindersecuretransportconfiguration).) For Windows systems, backslashes (\\) in the file path are replaced with forward slashes (/) before the file path is modified as described above.
-   **Command** – Either `GET` or `PUT` depending on whether the user is requesting a read or write operation.

## <span id="Example"></span>Example authorization request

The following example shows how SecureTransport would construct an authorization request to SiteMinder.

Assume a user requests a listing for the following resource:

`/mnt/data/SecureTransport/MyDirectory`

If the **File Storage Root Path** (in the SecureTransport SiteMinder settings) is configured as:

`/mnt/data/SecureTransport`

and the **SiteMinder Path Prefix** (in the SecureTransport SiteMinder settings) is configured as:

`/ST`

the authorization request for this file operation would be:

`GET /ST/MyDirectory/`

In this example, SiteMinder authorization rule would be configured to allow or deny the `GET` command to access the `/ST/MyDirectory/` resource. When SiteMinder is enabled, all SecureTransport users must have `GET` access to the path specified in the **SiteMinder Path Prefix** to successfully log in. If the **SiteMinder Path Prefix** setting is left blank, then users must have `GET` access to the / directory. The SiteMinder Policy Server must be set accordingly.