{
    "title": "Account related EL for AR",
    "linkTitle": "Account related EL for AR",
    "weight": "290"
}The following table provides the account related EL expressions.

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th><span>Agent Env Variable</span>
</th>
         <th>Routing EL expression</th>
         <th>Example</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p>
<nobr>DXAGENT_ACCOUNT_ATTR_*</nobr>
</p>
         </td>
         <td>
            <p>account.attributes['ATTRIBUTE_NAME']</p>
         </td>
         <td>
            <p><code>${account.attributes['templateClass'].toUpperCase() eq 'AdClass'.toUpperCase()}</code> - returns true</p>
            <p><code>${account.attributes['transfersWebServiceAllowed']}</code> - returns either false or true</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>DXAGENT_ACCOUNT_DELIVERY_METHOD</p>
         </td>
         <td>
            <p>account.deliveryMethod</p>
         </td>
         <td><code>${account.deliveryMethod.toLowerCase() == 'custom' }</code>
         </td>
      </tr>
      <tr>
         <td>
            <p>DXAGENT_ACCOUNT_DISABLED</p>
         </td>
         <td>
            <p>account.disabled</p>
         </td>
         <td><code>${account.disabled != '0'}</code> - returns true         </td>
      </tr>
      <tr>
         <td>
            <p>DXAGENT_ACCOUNT_EMAIL</p>
         </td>
         <td>
            <p>account.email</p>
         </td>
         <td><code>${!empty account.email}</code>
         </td>
      </tr>
      <tr>
         <td>
            <p>DXAGENT_ACCOUNT_ENROLLMENT</p>
         </td>
         <td>
            <p>account.enrollment</p>
         </td>
         <td>
            <p><code>${account.enrollment.toLowerCase() eq 'existing_account'}</code>
</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>DXAGENT_ACCOUNT_HTMLTEMPLATE</p>
         </td>
         <td>
            <p>account.htmlTemplate</p>
         </td>
         <td><code>${account.htmlTemplate.substring(11,14) eq 'sm6'}</code>
         </td>
      </tr>
      <tr>
         <td>
            <p>DXAGENT_ACCOUNT_ID</p>
         </td>
         <td>
            <p>account.id</p>
         </td>
         <td>
            <p><code>${ !empty account.id}</code>
</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>DXAGENT_BUSINESS_UNIT_NAME</p>
         </td>
         <td>
            <p>account.businessUnit.name</p>
         </td>
         <td><code>${account.businessUnit.name eq 'bu'}</code> - returns true         </td>
      </tr>
      <tr>
         <td>
            <p>DXAGENT_BUSINESS_UNIT_ID</p>
         </td>
         <td>
            <p>account.businessUnit.id</p>
         </td>
         <td><code>${ !empty account.businessUnit.id}</code>
         </td>
      </tr>
      <tr>
         <td>
            <p>DXAGENT_ACCOUNT_NAME</p>
         </td>
         <td>
            <p>account.name</p>
         </td>
         <td><code>${account.name eq 'template-routes'}</code> - returns true         </td>
      </tr>
      <tr>
         <td>
            <p>DXAGENT_ACCOUNT_NOTES</p>
         </td>
         <td>
            <p>account.notes</p>
         </td>
         <td><code>${ !empty account.notes}</code>
         </td>
      </tr>
      <tr>
         <td>
            <p>DXAGENT_ACCOUNT_PHONE</p>
         </td>
         <td>
            <p>account.phone</p>
         </td>
         <td><code>${ !empty account.phone}</code>
         </td>
      </tr>
      <tr>
         <td>
            <p>DXAGENT_ACCOUNT_TYPE</p>
         </td>
         <td>
            <p>account.type</p>
         </td>
         <td>
            <p><code>${account.type eq 'template'}</code>
</p>
            <p><code>${account.type != 'service'}</code>
</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>DXAGENT_HOMEDIR</p>
         </td>
         <td>
            <p>account.home</p>
         </td>
         <td><code>${parentFolder(transfer.targetDirFull) eq account.home}</code>
         </td>
      </tr>
      <tr>
         <td>
            <p>DXAGENT_ACCOUNT_IMPLICIT_ENROLLMENT</p>
         </td>
         <td>
            <p>account.implicitEnrollment</p>
         </td>
         <td><code>${account.implicitEnrollment.toLowerCase().matches('.*account')}</code>
         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>
            <p>account.attributes['userVars.xxx']</p>
         </td>
         <td>Access additional attribute of an account with name <code>xxx</code>.         </td>
      </tr>
   </tbody>
</table>

**Related topics:**

-   [Session related EL for AR](../r_st_session_related)
-   [Predefined EL functions for AR](../r_st_predefined_el_functions)
-   [LDAP related EL for AR](../r_st_ldap_related)
-   [PeSIT related EL for AR](../r_st_pesit_related)
-   [Routing related EL for AR](../r_st_routing_related)
-   [Special routing EL variables for AR](../r_st_special_routing_variables)
-   [STFS PeSIT related EL for AR](../r_st_stfs_pesit_related)
-   [Transfer related EL for AR](../r_st_transfer_related)
-   [User related EL for AR](../r_st_user_related)
-   [HTTP headers related EL for AR](../r_st_http_headers)
