{
    "title": "Multiple Identity Provider configuration",
    "linkTitle": "Multiple Identity Provider configuration",
    "weight": "180"
}SecureTransport supports the multiple Identity Provider configuration. First, you should configure every Identity Provider. Then, for every Identity provider follow the steps described for administrators and end-users. Refer to [Enable Single Sign-On (SSO) for administrators](../c_st_enable_sso_admin) and [Enable Single Sign-On (SSO) for end-users](../c_st_enable_sso_endusers).

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">For both administrators and end-users every Identity Provider should be in a different Identity Provider element. For a SAML-based Identity Provider you should use the <code>&lt;SamlIdentityProvider&gt;</code> element and for Kerberos you should use the <code>&lt;KerberosIdentityProvider&gt;</code> element.         </td>
      </tr>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">For every Identity Provider defined in either the <code>sso-admin.xml</code> or <code>sso-enduser.xml</code> file, you should have a different Identity Provider metadata file. When uploading the SSO Configuration Files ZIP file, make sure that all required files are in the ZIP.         </td>
      </tr>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The client name has to be the same on all Identity Providers, <span>SecureTransport</span> only supports one service provider per component (Administrator and End-user).         </td>
      </tr>
</table>

## Identity Provider resolution

Identity Provider resolution provides support for choosing the right Identity Provider based on server configuration and run-time metadata. If such resolution is not present, the first Identity Provider is selected by default, among ones specified under `<IdentityProviders>` element.

For both `sso-enduser.xml` and `sso-admin.xml` configuration files the element to edit is `<IdentityProviderResolution>` element under `<ServiceProvider>` element. The mapping can be done in either one of the following ways:

1.  Query parameter – Identity provider mapping using a query parameter. The name of query parameter resolution will be searched for among request parameters during runtime and its value should match to the Identity Provider alias.
2.  Header - Header value provided by a user request. The name of header resolution will be searched for among request header during runtime and its value should match to the Identity Provider alias.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Only one of these mappings can be done.         </td>
      </tr>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">By default, if no Identity Provider ID is set, the first listed Identity Provider in the configuration file is used.         </td>
      </tr>
</table>

## Identity Provider resolution for administrators

To configure Identity provider resolution for administrators, open the `sso-admin.xml `and edit the `<IdentityProviderResolution>` element under the `<ServiceProvider>` element.

**Query parameter resolution example:**

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><pre xml:space="preserve"><span>&lt;QueryParameter name="idp_id"&gt;
    &lt;Mapping value="keycloakIdp" entityId="https://st.keycloak.axway.int/" /&gt;
    &lt;Mapping value="shibbolethIdp" entityId="https://st.shibboleth.axway.int/" /&gt;
&lt;/QueryParameter&gt;</span>
</pre>
         </td>
      </tr>
   </tbody>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The value of name attribute in the <code>&lt;QueryParameter&gt;</code> element should match the Server configuration option <code>LoginSettings.Admin.SSO.idpResolverKey</code> value. The default value is <code>idp_id</code>.         </td>
      </tr>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Ensure the name of the query parameter/header is different than <span>SecureTransport</span> configuration option <code>LoginSettings.Admin.SSO.localIdpId</code> to be able to configure the selection of <span>SecureTransport</span> as local authentication provider and SSO Identity Provider. For more information on how to use SecureTransport as Identity provider, refer to <a href="../c_st_identity_provider">SecureTransport as an Identity Provider</a>.         </td>
      </tr>
</table>

In the example above we already have 2 identity providers defined in `sso-admin.xml `file.

Suppose we have the following request:

-   `https://<ST>/?idp_id=shibbolethIdp`, where `<ST>` is the IP of the running SecureTransport instance.

SecureTransport will choose the Identity Provider with an e`ntityId=’https://st.shibboleth.axway.int/’`. If no such Identity Provider is found, the login will be effectively rejected.

**Header resolution example:**

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><pre xml:space="preserve"><span>&lt;Header name="idp_id"&gt;
    &lt;Mapping value="keycloakIdp" entityId="https://st.keycloak.axway.int/" /&gt;
    &lt;Mapping value="shibbolethIdp" entityId="https://st.shibboleth.axway.int/" /&gt;
&lt;/Header&gt;</span>
</pre>
         </td>
      </tr>
   </tbody>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The value of name attribute in <code>&lt;Header&gt;</code> element should match the <span>SecureTransport</span> configuration option <code>LoginSettings.Admin.SSO.idpResolverKey</code> value. The default value is <code>idp_id</code>.         </td>
      </tr>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Ensure that the name of the query parameter/header is different than <span>SecureTransport</span> configuration option <code>LoginSettings.Admin.SSO.localIdpId</code> in order to be able to configure selection of SecureTransport as local authentication provider and SSO Identity Provider. For more information on how to use SecureTransport as Identity Provider, refer to <a href="../c_st_identity_provider">SecureTransport as an Identity Provider</a>.         </td>
      </tr>
</table>

In the example above we already have two Identity Providers defined in the `sso-admin.xml` file.

Suppose we have request to the running SecureTransport instance that contains the following Header:

-   `keycloakIdp : https://st.keycloak.axway.int/`

SecureTransport will choose the Identity Provider with an `entityId= ‘https://st.keycloak.axway.int/’`. If no such Identity Provider is found, the login will be effectively rejected.

## Identity provider resolution for end-users

To configure Identity provider resolution for end-users, open the `sso-enduser.xml `file and edit the `<IdentityProviderResolution>` element under the `<ServiceProvider>` element.

**Query parameter resolution example:**

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><pre xml:space="preserve"><span>&lt;QueryParameter name="idp_id"&gt;
    &lt;Mapping value="keycloakIdp" entityId="https://st.keycloak.axway.int/" /&gt;
    &lt;Mapping value="shibbolethIdp" entityId="https://st.shibboleth.axway.int/" /&gt;
    &lt;Mapping value="kerbIdP" entityId="kerberos" /&gt;
&lt;/QueryParameter&gt;</span>
</pre>
         </td>
      </tr>
   </tbody>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The name attribute in <code>&lt;QueryParameter&gt;</code> element should match the <span>SecureTransport</span> configuration option <code>LoginSettings.EndUser.SSO.idpResolverKey</code> value. The default value is <code>idp_id</code>.         </td>
      </tr>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Ensure that the name of the query parameter/header is different than <span>SecureTransport</span> configuration option <code>LoginSettings.EndUser.SSO.localIdpId</code> to be able to configure selection of <span>SecureTransport</span> as local authentication provider and SSO Identity Provider. For more information on how to use <span>SecureTransport</span> as Identity provider, refer to <a href="../c_st_identity_provider">SecureTransport as an Identity Provider</a>.         </td>
      </tr>
</table>

In the example above we already have three Identity Providers defined in `sso-enduser.xml` file.

Suppose we have the following request:

-   `https://<ST>/?idp_id=shibbolethIdp`, where `<ST>` is the IP of the SecureTransport instance.

SecureTransport will choose the Identity provider with an `entityId=’https://st.shibboleth.axway.int/’`. If no such Identity Provider is found, the login will be effectively rejected.

**Header resolution example:**

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><pre xml:space="preserve"><span>&lt;Header name="idp_id"&gt;
    &lt;Mapping value="keycloakIdp" entityId="https://st.keycloak.axway.int/" /&gt;
    &lt;Mapping value="shibbolethIdp" entityId="https://st.shibboleth.axway.int/" /&gt;
    &lt;Mapping value="kerbIdP" entityId="kerberos" /&gt;
&lt;/Header&gt;</span>
</pre>
         </td>
      </tr>
   </tbody>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The name attribute in <code>&lt;Header&gt;</code> element should match the Server configuration option <code>LoginSettings.EndUser.SSO.idpResolverKey</code> value. The default value is <code>idp_id</code>.         </td>
      </tr>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Ensure that the name of the query parameter/header is different than <span>SecureTransport</span> configuration option <code>LoginSettings.EndUser.SSO.localIdpId</code> in order to be able to configure selection of <span>SecureTransport</span> as a local authentication provider and SSO Identity Provider. For more information on how to use <span>SecureTransport</span> as Identity Provider, refer to <a href="../c_st_identity_provider">SecureTransport as an Identity Provider</a>.         </td>
      </tr>
</table>

In the example above we already have 3 identity providers defined in the `sso-enduser.xml` file.

Suppose we have request to SecureTransport instance that contains the following Header:

-   `keycloakIdp : https://st.keycloak.axway.int/`

SecureTransport will choose the Identity Provider with an `entityId= ‘https://st.keycloak.axway.int/’`. If no such Identity provider is found, the login will be effectively rejected.

## Tenant resolution

Tenant resolution provides a support of multiple identity providers. If not present tenant is null. The supported ways to do that are by:

1.  Query parameter
2.  Header

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Only one of the ways can be completed.         </td>
      </tr>
</table>

The tenant resolution is the same as the Identity Provider resolution in terms of syntax and meaning. However, the precedence is to take the Identity Provider resolution first. Header mapping, if present, will always be the first choice, no matter where it is placed; in the Identity Provider resolution or in tenant resolution.
