{
    "title": "User related EL\u00a0for AR",
    "linkTitle": "User related EL\u00a0for AR",
    "weight": "370"
}The following table provides the user related EL expressions.

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Agent Env Variable</th>
         <th>Routing EL expression</th>
         <th>Example</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p>DXAGENT_LOGINNAME</p>
         </td>
         <td>
            <p>account.user.loginName</p>
         </td>
         <td><code>${account.user.loginName.<br/>matches('.*usert.*') ? 1 : 0}</code> 
- will return 1         </td>
      </tr>
      <tr>
         <td>
            <p>DXAGENT_USERTYPE</p>
         </td>
         <td>
            <p>account.user.type</p>
         </td>
         <td><code>${account.user.type.matches('virtual') }</code> 
- will return true         </td>
      </tr>
      <tr>
         <td>
            <p>DXAGENT_USERCLASS</p>
         </td>
         <td>
            <p>account.user.className</p>
         </td>
         <td><code>${account.user.class eq 'AdClass'}</code>
         </td>
      </tr>
      <tr>
         <td>
            <p>DXAGENT_NATIVEUSER</p>
         </td>
         <td>
            <p>account.user.<br/>nativeUserName</p>
         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>
            <p>DXAGENT_USERGID</p>
         </td>
         <td>
            <p>account.user.uid</p>
         </td>
         <td>
            <p><code>${account.user.uid gt '1000'}</code>
</p>
         </td>
      </tr>
   </tbody>
</table>

**Related topics:**

-   [Session related EL for AR](../r_st_session_related)
-   [Predefined EL functions for AR](../r_st_predefined_el_functions)
-   [Account related EL for AR](../r_st_account_related)
-   [LDAP related EL for AR](../r_st_ldap_related)
-   [PeSIT related EL for AR](../r_st_pesit_related)
-   [Routing related EL for AR](../r_st_routing_related)
-   [Special routing EL variables for AR](../r_st_special_routing_variables)
-   [STFS PeSIT related EL for AR](../r_st_stfs_pesit_related)
-   [Transfer related EL for AR](../r_st_transfer_related)
-   [HTTP headers related EL for AR](../r_st_http_headers)
