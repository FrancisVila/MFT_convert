{
    "title": "User access control (authorization)",
    "linkTitle": "User access control (authorization)",
    "weight": "170"
}Regardless of the type of client, access control is always performed by <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>, which uses SiteMinder rules to obtain the user’s read/write authority to a particular resource. The SSO portal cannot perform access control for <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> resources.

After a user is authenticated, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> sends an authorization request to SiteMinder to determine whether the user has read/write access to the requested resource. If SiteMinder grants the appropriate access level, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> proceeds with the file operation.

> **Note:**
>
> The SiteMinder SSO portal must be accessed using FQDN because SiteMinder uses domain cookies and it is possible that different browsers can handle the conversion from partial name to FQDN in an incorrect manner. In the latter case, access to the SSO portal can be denied.

The following topics describe the SiteMinder authorization rules and provide an authorization request example:

-   <a href="#SiteMinder" class="MCXref xref">SiteMinder authorization rules</a>
-   <a href="#Example" class="MCXref xref">Example authorization request</a>

**Related topics:**

-   <a href="../c_st_web_client_user_authentication" class="MCXref xref">Web client (HTTP and HTTPS) user authentication</a>
-   <a href="../c_st_command_line_client_user_authentication" class="MCXref xref">Command line client (FTP, FTPS, HTTPS, and SSH) user authentication</a>

<span id="SiteMinder"></span>

## SiteMinder authorization rules

Configure the SiteMinder authorization rules to accommodate <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> authorization requests. A <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> authorization request contains the following elements:

-   **Resource Path** – The absolute URI of the resource being accessed by the user. <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> determines the actual file path and uses that file path as the URI. This URI can be modified (section removed or prefix added) based on the **File Storage Root Path** and **SiteMinder Path Prefix** in the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> SiteMinder settings. (For details, see <a href="../../t_st_sitemindersecuretransportconfiguration#SiteMinder_3654860350_1021080" class="MCXref xref">Configure SiteMinder settings in SecureTransport</a>.) For Windows systems, backslashes (\\) in the file path are replaced with forward slashes (/) before the file path is modified as described above.
-   **Command** – Either `GET` or `PUT` depending on whether the user is requesting a read or write operation.

<span id="Example"></span>

## Example authorization request

The following example shows how <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> would construct an authorization request to SiteMinder.

Assume a user requests a listing for the following resource:

`/mnt/data/SecureTransport/MyDirectory`

If the **File Storage Root Path** (in the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> SiteMinder settings) is configured as:

`/mnt/data/SecureTransport`

and the **SiteMinder Path Prefix** (in the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> SiteMinder settings) is configured as:

`/ST`

the authorization request for this file operation would be:

`GET /ST/MyDirectory/`

In this example, SiteMinder authorization rule would be configured to allow or deny the `GET` command to access the `/ST/MyDirectory/` resource. When SiteMinder is enabled, all <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> users must have `GET` access to the path specified in the **SiteMinder Path Prefix** to successfully log in. If the **SiteMinder Path Prefix** setting is left blank, then users must have `GET` access to the / directory. The SiteMinder Policy Server must be set accordingly.