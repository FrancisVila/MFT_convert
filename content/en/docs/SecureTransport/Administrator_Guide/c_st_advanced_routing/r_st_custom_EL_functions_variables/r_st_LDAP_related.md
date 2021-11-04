{
    "title": "LDAP related EL for AR",
    "linkTitle": "LDAP related EL for AR",
    "weight": "290"
}The following table provides the LDAP related EL expressions.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Agent Env Variable         </th>
<th class="HeadE-Column1-Header1">Routing EL expression         </th>
<th class="HeadD-Column1-Header1">Example         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>STSESSION_LDAP_DOMAIN_ID</p>         </td>
         <td><p>ldap.domainId</p>         </td>
         <td><code>${ldap.domainId == '&lt;domain id&gt;'}</code>         </td>
      </tr>
      <tr>
         <td><p>STSESSION_LDAP_DOMAIN_NAME</p>         </td>
         <td><p>ldap.domainName</p>         </td>
         <td><code>${ldap.domainName eq 'ad'}</code>
- will return true         </td>
      </tr>
      <tr>
         <td><p>STSESSION_LDAP_DN</p>         </td>
         <td><p>ldap.dn</p>         </td>
         <td><code>${ldap.dn.toLowerCase().matches('.*dc=st1.*')}</code>
- will return true         </td>
      </tr>
      <tr>
         <td><p>STSESSION_LDAP_AUTH_BY_EMAIL</p>         </td>
         <td><p>ldap.authByEmail</p>         </td>
         <td><code>${ldap.authByEmail gt 0}</code>         </td>
      </tr>
      <tr>
         <td><p>STSESSION_LDAP_DIR.*</p>         </td>
         <td><p>ldap.attributes.*</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>STSESSION_LDAP_DIR_mail</p>         </td>
         <td><p>ldap.attributes.mail</p>         </td>
         <td><code>${ldap.attributes.mail.matches('usert.*') ? 1 : 0}</code>
- will return 1         </td>
      </tr>
   </tbody>
</table>

**Related topics:**

-   <a href="../r_st_session_related" class="MCXref xref">Session related EL for AR</a>
-   <a href="../r_st_predefined_el_functions" class="MCXref xref">Predefined EL functions for AR</a>
-   <a href="../r_st_account_related" class="MCXref xref">Account related EL for AR</a>
-   <a href="../r_st_pesit_related" class="MCXref xref">PeSIT related EL for AR</a>
-   <a href="../r_st_routing_related" class="MCXref xref">Routing related EL for AR</a>
-   <a href="../r_st_special_routing_variables" class="MCXref xref">Special routing EL variables for AR</a>
-   <a href="../r_st_stfs_pesit_related" class="MCXref xref">STFS PeSIT related EL for AR</a>
-   <a href="../r_st_transfer_related" class="MCXref xref">Transfer related EL for AR</a>
-   <a href="../r_st_user_related" class="MCXref xref">User related EL for AR</a>
-   <a href="../r_st_http_headers" class="MCXref xref">HTTP headers related EL for AR</a>
