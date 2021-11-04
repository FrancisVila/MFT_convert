{
    "title": "User related EL for AR",
    "linkTitle": "User related EL for AR",
    "weight": "360"
}The following table provides the user related EL expressions.

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
         <td><p>DXAGENT_LOGINNAME</p>         </td>
         <td><p>account.user.loginName</p>         </td>
         <td><code>${account.user.loginName.matches('.*usert.*') ? 1 : 0}</code>
- will return 1         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_USERTYPE</p>         </td>
         <td><p>account.user.type</p>         </td>
         <td><code>${account.user.type.matches('virtual') }</code>
- will return true         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_USERCLASS</p>         </td>
         <td><p>account.user.className</p>         </td>
         <td><code>${account.user.class eq 'AdClass'}</code>         </td>
      </tr>
      <tr>
         <td><p>DXAGENT_NATIVEUSER</p>         </td>
         <td><p>account.user.<br />
nativeUserName</p>         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><p>DXAGENT_USERGID</p>         </td>
         <td><p>account.user.uid</p>         </td>
         <td><p><code>${account.user.uid gt '1000'}</code></p>         </td>
      </tr>
   </tbody>
</table>

**Related topics:**

-   <a href="../r_st_session_related" class="MCXref xref">Session related EL for AR</a>
-   <a href="../r_st_predefined_el_functions" class="MCXref xref">Predefined EL functions for AR</a>
-   <a href="../r_st_account_related" class="MCXref xref">Account related EL for AR</a>
-   <a href="../r_st_ldap_related" class="MCXref xref">LDAP related EL for AR</a>
-   <a href="../r_st_pesit_related" class="MCXref xref">PeSIT related EL for AR</a>
-   <a href="../r_st_routing_related" class="MCXref xref">Routing related EL for AR</a>
-   <a href="../r_st_special_routing_variables" class="MCXref xref">Special routing EL variables for AR</a>
-   <a href="../r_st_stfs_pesit_related" class="MCXref xref">STFS PeSIT related EL for AR</a>
-   <a href="../r_st_transfer_related" class="MCXref xref">Transfer related EL for AR</a>
-   <a href="../r_st_http_headers" class="MCXref xref">HTTP headers related EL for AR</a>
