{
    "title": "Multiple Identity Provider configuration",
    "linkTitle": "Multiple Identity Provider configuration",
    "weight": "170"
}<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> supports the multiple Identity Provider configuration. First, you should configure every Identity Provider. Then, for every Identity provider follow the steps described for administrators and end-users. Refer to <a href="../c_st_enable_sso_admin#Enable" class="MCXref xref">Enable Single Sign-On (SSO) for administrators</a> and <a href="../c_st_enable_sso_endusers#Enable2" class="MCXref xref">Enable Single Sign-On (SSO) for end-users</a>.

> **Note:**
>
> For both administrators and end-users every Identity Provider should be in a different Identity Provider element. For a SAML-based Identity Provider you should use the &lt;SamlIdentityProvider> element and for Kerberos you should use the &lt;KerberosIdentityProvider> element.

> **Note:**
>
> For every Identity Provider defined in either the sso-admin.xml or sso-enduser.xml file, you should have a different Identity Provider metadata file. When uploading the SSO Configuration Files ZIP file, make sure that all required files are in the ZIP.

> **Note:**
>
> The client name has to be the same on all Identity Providers, SecureTransport only supports one service provider per component (Administrator and End-user).

## Identity Provider resolution

Identity Provider resolution provides support for choosing the right Identity Provider based on server configuration and run-time metadata. If such resolution is not present, the first Identity Provider is selected by default, among ones specified under `<IdentityProviders>` element.

For both `sso-enduser.xml` and `sso-admin.xml` configuration files the element to edit is `<IdentityProviderResolution>` element under `<ServiceProvider>` element. The mapping can be done in either one of the following ways:

1.  Query parameter – Identity provider mapping using a query parameter. The name of query parameter resolution will be searched for among request parameters during runtime and its value should match to the Identity Provider alias.
2.  Header - Header value provided by a user request. The name of header resolution will be searched for among request header during runtime and its value should match to the Identity Provider alias.

> **Note:**
>
> Only one of these mappings can be done.

> **Note:**
>
> By default, if no Identity Provider ID is set, the first listed Identity Provider in the configuration file is used.

## Identity Provider resolution for administrators

To configure Identity provider resolution for administrators, open the `sso-admin.xml `and edit the `<IdentityProviderResolution>` element under the `<ServiceProvider>` element.

**Query parameter resolution example:**


    <QueryParameter name="idp_id">
        <Mapping value="keycloakIdp" entityId="https://st.keycloak.axway.int/" />
        <Mapping value="shibbolethIdp" entityId="https://st.shibboleth.axway.int/" />
    </QueryParameter>

> **Note:**
>
> The value of name attribute in the &lt;QueryParameter> element should match the Server configuration option LoginSettings.Admin.SSO.idpResolverKey value. The default value is idp\_id.

> **Note:**
>
> Ensure the name of the query parameter/header is different than SecureTransport configuration option LoginSettings.Admin.SSO.localIdpId to be able to configure the selection of SecureTransport as local authentication provider and SSO Identity Provider. For more information on how to use SecureTransport as Identity provider, refer to SecureTransport as an Identity Provider.

In the example above we already have 2 identity providers defined in `sso-admin.xml `file.

Suppose we have the following request:

-   `https://<ST>/?idp_id=shibbolethIdp`, where `<ST>` is the IP of the running <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> instance.

<span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> will choose the Identity Provider with an e`ntityId=’https://st.shibboleth.axway.int/’`. If no such Identity Provider is found, the login will be effectively rejected.

**Header resolution example:**


    <Header name="idp_id">
        <Mapping value="keycloakIdp" entityId="https://st.keycloak.axway.int/" />
        <Mapping value="shibbolethIdp" entityId="https://st.shibboleth.axway.int/" />
    </Header>

> **Note:**
>
> The value of name attribute in &lt;Header> element should match the SecureTransport configuration option LoginSettings.Admin.SSO.idpResolverKey value. The default value is idp\_id.

> **Note:**
>
> Ensure that the name of the query parameter/header is different than SecureTransport configuration option LoginSettings.Admin.SSO.localIdpId in order to be able to configure selection of SecureTransport as local authentication provider and SSO Identity Provider. For more information on how to use SecureTransport as Identity Provider, refer to SecureTransport as an Identity Provider.

In the example above we already have two Identity Providers defined in the `sso-admin.xml` file.

Suppose we have request to the running <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> instance that contains the following Header:

-   `keycloakIdp : https://st.keycloak.axway.int/`

<span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> will choose the Identity Provider with an `entityId= ‘https://st.keycloak.axway.int/’`. If no such Identity Provider is found, the login will be effectively rejected.

## Identity provider resolution for end-users

To configure Identity provider resolution for end-users, open the `sso-enduser.xml `file and edit the `<IdentityProviderResolution>` element under the `<ServiceProvider>` element.

**Query parameter resolution example:**


    <QueryParameter name="idp_id">
        <Mapping value="keycloakIdp" entityId="https://st.keycloak.axway.int/" />
        <Mapping value="shibbolethIdp" entityId="https://st.shibboleth.axway.int/" />
        <Mapping value="kerbIdP" entityId="kerberos" />
    </QueryParameter>

> **Note:**
>
> The name attribute in &lt;QueryParameter> element should match the SecureTransport configuration option LoginSettings.EndUser.SSO.idpResolverKey value. The default value is idp\_id.

> **Note:**
>
> Ensure that the name of the query parameter/header is different than SecureTransport configuration option LoginSettings.EndUser.SSO.localIdpId to be able to configure selection of SecureTransport as local authentication provider and SSO Identity Provider. For more information on how to use SecureTransport as Identity provider, refer to SecureTransport as an Identity Provider.

In the example above we already have three Identity Providers defined in `sso-enduser.xml` file.

Suppose we have the following request:

-   `https://<ST>/?idp_id=shibbolethIdp`, where `<ST>` is the IP of the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> instance.

<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> will choose the Identity provider with an `entityId=’https://st.shibboleth.axway.int/’`. If no such Identity Provider is found, the login will be effectively rejected.

**Header resolution example:**


    <Header name="idp_id">
        <Mapping value="keycloakIdp" entityId="https://st.keycloak.axway.int/" />
        <Mapping value="shibbolethIdp" entityId="https://st.shibboleth.axway.int/" />
        <Mapping value="kerbIdP" entityId="kerberos" />
    </Header>

> **Note:**
>
> The name attribute in &lt;Header> element should match the Server configuration option LoginSettings.EndUser.SSO.idpResolverKey value. The default value is idp\_id.

> **Note:**
>
> Ensure that the name of the query parameter/header is different than SecureTransport configuration option LoginSettings.EndUser.SSO.localIdpId in order to be able to configure selection of SecureTransport as a local authentication provider and SSO Identity Provider. For more information on how to use SecureTransport as Identity Provider, refer to SecureTransport as an Identity Provider.

In the example above we already have 3 identity providers defined in the `sso-enduser.xml` file.

Suppose we have request to SecureTransport instance that contains the following Header:

-   `keycloakIdp : https://st.keycloak.axway.int/`

<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> will choose the Identity Provider with an `entityId= ‘https://st.keycloak.axway.int/’`. If no such Identity provider is found, the login will be effectively rejected.

## Tenant resolution

Tenant resolution provides a support of multiple identity providers. If not present tenant is null. The supported ways to do that are by:

1.  Query parameter
2.  Header

> **Note:**
>
> Only one of the ways can be completed.

The tenant resolution is the same as the Identity Provider resolution in terms of syntax and meaning. However, the precedence is to take the Identity Provider resolution first. Header mapping, if present, will always be the first choice, no matter where it is placed; in the Identity Provider resolution or in tenant resolution.
