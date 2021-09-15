{
    "title": "LDAP related EL for AR",
    "linkTitle": "LDAP related EL for AR",
    "weight": "300"
}The following table provides the LDAP related EL expressions.

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Agent Env Variable </th>
         <th>Routing EL expression</th>
         <th>Example</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p>STSESSION_LDAP_DOMAIN_ID</p>
         </td>
         <td>
            <p>ldap.domainId</p>
         </td>
         <td><code>${ldap.domainId == '&lt;domain id&gt;'}</code>
         </td>
      </tr>
      <tr>
         <td>
            <p>STSESSION_LDAP_DOMAIN_NAME</p>
         </td>
         <td>
            <p>ldap.domainName</p>
         </td>
         <td><code>${ldap.domainName eq 'ad'}</code> 
- will return true         </td>
      </tr>
      <tr>
         <td>
            <p>STSESSION_LDAP_DN</p>
         </td>
         <td>
            <p>ldap.dn</p>
         </td>
         <td><code>${ldap.dn.toLowerCase().matches('.*dc=st1.*')}</code> 
- will return true         </td>
      </tr>
      <tr>
         <td>
            <p>STSESSION_LDAP_AUTH_BY_EMAIL</p>
         </td>
         <td>
            <p>ldap.authByEmail</p>
         </td>
         <td><code>${ldap.authByEmail gt 0}</code>
         </td>
      </tr>
      <tr>
         <td>
            <p>STSESSION_LDAP_DIR.*</p>
         </td>
         <td>
            <p>ldap.attributes.*</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>STSESSION_LDAP_DIR_mail</p>
         </td>
         <td>
            <p>ldap.attributes.mail</p>
         </td>
         <td><code>${ldap.attributes.mail.<br/>matches('usert.*') ? 1 : 0}</code> 
- will return 1         </td>
      </tr>
   </tbody>
</table>

**Related topics:**

-   [Session related EL for AR](../r_st_session_related)
-   [Predefined EL functions for AR](../r_st_predefined_el_functions)
-   [Account related EL for AR](../r_st_account_related)
-   [PeSIT related EL for AR](../r_st_pesit_related)
-   [Routing related EL for AR](../r_st_routing_related)
-   [Special routing EL variables for AR](../r_st_special_routing_variables)
-   [STFS PeSIT related EL for AR](../r_st_stfs_pesit_related)
-   [Transfer related EL for AR](../r_st_transfer_related)
-   [User related EL for AR](../r_st_user_related)
-   [HTTP headers related EL for AR](../r_st_http_headers)
