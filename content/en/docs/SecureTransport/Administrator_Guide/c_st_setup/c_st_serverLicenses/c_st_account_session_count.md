{
    "title": "Account session count",
    "linkTitle": "Account session count",
    "weight": "210"
}The number of accounts in the core server license controls the number of connections allowed to the server. An account license is considered in use when a user logs in. A license is also considered in use when used for a site that is initiating transfers. The license is considered in use for 60 days after the initial login or site transfer. The Folder Monitor, AS2 receiving, and asynchronous AS2 MDN receiving are excluded from license counting.

Account licenses apply to all protocols. To limit the number of concurrent users who can connect to the SecureTransport FTP and HTTP servers, see [User limits](../../../c_st_accesscontrol/c_st_userlimits).

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top"><span>SecureTransport</span> does not perform DNS lookups. Therefore a single site referred to in one place by name and another place by IP address is counted as two sites.         </td>
      </tr>
</table>

**Related topics:**

-   [Ad hoc user licenses](../c_st_adhoc_user_licenses)
-   [Updating SecureTransport licenses](../t_st_serverlicenses)
