{
    "title": "HTTP headers related EL for AR",
    "linkTitle": "HTTP headers related EL for AR",
    "weight": "380"
}The following table provides the HTTP header EL expressions.

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
            <p>DXAGENT_HTTP_*</p>
         </td>
         <td>
            <p>http.headers.<br/>HEADER_NAME</p>
         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>
            <p>DXAGENT_HTTP_HOST</p>
         </td>
         <td>
            <p>http.headers.<br/>HOST</p>
         </td>
         <td><code>${http.headers.HOST.matches('.*')}</code>
         </td>
      </tr>
      <tr>
         <td>
            <p>DXAGENT_HTTP_USER_AGENT</p>
         </td>
         <td>
            <p>http.headers.<br/>USER_AGENT</p>
         </td>
         <td><code>${extract(http.headers.USER_AGENT,'/',1) eq 'Mozilla'}</code>
         </td>
      </tr>
      <tr>
         <td>
            <p>DXAGENT_HTTP_REFERER</p>
         </td>
         <td>
            <p>http.headers.<br/>REFERER</p>
         </td>
         <td><code>${concat(concat('https://',http.headers.HOST),':444').<br/>matches(http.headers.REFERER)} </code>
         </td>
      </tr>
      <tr>
         <td>
            <p>DXAGENT_HTTP_CONTENT_LENGTH</p>
         </td>
         <td>
            <p>http.headers.<br/>CONTENT_LENGTH</p>
         </td>
         <td>
            <p><code>${http.headers.CONTENT_LENGTH eq transfer.transferredBytes}</code>
</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>DXAGENT_HTTP_CONTENT_TYPE</p>
         </td>
         <td>
            <p>http.headers.<br/>CONTENT_TYPE</p>
         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>
            <p>DXAGENT_HTTP_ACCEPT_LANGUAGE</p>
         </td>
         <td>
            <p>http.headers.<br/>ACCEPT_LANGUAGE</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>DXAGENT_HTTP_FEATURES</p>
         </td>
         <td>
            <p>http.headers.<br/>FEATURES</p>
         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>
            <p>DXAGENT_HTTP_CONTENT_RANGE</p>
         </td>
         <td>
            <p>http.headers.<br/>CONTENT_RANGE</p>
         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>
            <p><code>DXAGENT_HTTP_ACCEPT</code>
</p>
         </td>
         <td>
            <p>http.headers.<br/>ACCEPT</p>
         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>
            <p>DXAGENT_HTTP_ORIGIN</p>
         </td>
         <td>
            <p>http.headers.<br/>ORIGIN</p>
         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>
            <p>DXAGENT_HTTP_CONNECTION</p>
         </td>
         <td>
            <p>http.headers.<br/>CONNECTION</p>
         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>
            <p>DXAGENT_HTTP_ACCEPT_ENCODING</p>
         </td>
         <td>
            <p>http.headers.<br/>ACCEPT_ENCODING</p>
         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>
            <p>DXAGENT_HTTP_CONTENT_DISPOSITION
                        </p>
         </td>
         <td>
            <p>http.headers.<br/>CONTENT_DISPOSITION</p>
         </td>
         <td>          </td>
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
-   [User related EL for AR](../r_st_user_related)
