{
    "title": "Enable host names for access control",
    "linkTitle": "Enable host names for access control",
    "weight": "280"
}To use host names in the **Address** field of rules that control access to the Administration Tool, FTP, HTTP, and SSH servers, enable reverse DNS lookup for those severs.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Enabling reverse DNS lookup might reduce the server’s performance because DNS lookups involve a series of requests through the DNS name server tree.         </td>
      </tr>
</table>

To enable DNS lookups for FTP, HTTP, and SSH servers, use **Reverse DNS Lookups** on the *Miscellaneous Options* page.

The following topics provide how-to instructions for enabling reverse DNS lookups:

-   [Enable reverse DNS lookups for the Administration Tool server](#enable_admin)
-   [Enable reverse DNS lookups for the FTP, HTTP, or SSH server](#enable_ftp)

**Related topics:**

-   [Access rule order](../c_st_access_rule_order)
-   [Manage protocol server access](../t_st_administrationtoolandprotocolserveraccess)

## <span id="Enable_Admin"></span>Enable reverse DNS lookups for the Administration Tool server

Use the following procedure to enable reverse DNS lookups for the Administration Tool server.

1.  Select **Operations > Server Configuration**.  
    The *Server Configuration* page is displayed.
2.  To enable reverse DNS lookups for the Administration Tool server, search for the `Admin.ReverseDNSLookup` parameter and set it to `true`.
3.  Bounce the server.

## <span id="Enable_FTP"></span>Enable reverse DNS lookups for the FTP, HTTP, or SSH server

Use the following procedure to enable reverse DNS lookups for the FTP, HTTP, or SSH servers.

1.  Select **Setup > Miscellaneous**.  
    The *Miscellaneous Options* page is displayed.
2.  In the **Reverse DNS Lookups** list, select `Reverse DNS lookups enabled`.
3.  Click **Apply**.
