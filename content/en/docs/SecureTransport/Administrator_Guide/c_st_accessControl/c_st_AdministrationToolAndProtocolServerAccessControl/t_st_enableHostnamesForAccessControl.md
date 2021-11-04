{
    "title": "Enable host names for access control",
    "linkTitle": "Enable host names for access control",
    "weight": "270"
}To use host names in the **Address** field of rules that control access to the Administration Tool, FTP, HTTP, and SSH servers, enable reverse DNS lookup for those severs.

> **Note:**
>
> Enabling reverse DNS lookup might reduce the server’s performance because DNS lookups involve a series of requests through the DNS name server tree.

To enable DNS lookups for FTP, HTTP, and SSH servers, use **Reverse DNS Lookups** on the *Miscellaneous Options* page.

The following topics provide how-to instructions for enabling reverse DNS lookups:

-   <a href="#Enable_Admin" class="MCXref xref">Enable reverse DNS lookups for the Administration Tool server</a>
-   <a href="#Enable_FTP" class="MCXref xref">Enable reverse DNS lookups for the FTP, HTTP, or SSH server</a>

**Related topics:**

-   <a href="../c_st_access_rule_order" class="MCXref xref">Access rule order</a>
-   <a href="../t_st_administrationtoolandprotocolserveraccess" class="MCXref xref">Manage protocol server access</a>

<span id="Enable_Admin"></span>

## Enable reverse DNS lookups for the Administration Tool server

Use the following procedure to enable reverse DNS lookups for the Administration Tool server.

1.  Select **Operations > Server Configuration**.  
    The *Server Configuration* page is displayed.
2.  To enable reverse DNS lookups for the Administration Tool server, search for the `Admin.ReverseDNSLookup` parameter and set it to `true`.
3.  Bounce the server.

<span id="Enable_FTP"></span>

## Enable reverse DNS lookups for the FTP, HTTP, or SSH server

Use the following procedure to enable reverse DNS lookups for the FTP, HTTP, or SSH servers.

1.  Select **Setup > Miscellaneous**.  
    The *Miscellaneous Options* page is displayed.
2.  In the **Reverse DNS Lookups** list, select `Reverse DNS lookups enabled`.
3.  Click **Apply**.
