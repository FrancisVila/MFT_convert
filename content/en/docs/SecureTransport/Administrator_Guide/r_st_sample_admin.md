{
    "title": "Sample SSO configuration file for administrators",
    "linkTitle": "Sample SSO configuration file for administrators",
    "weight": "310"
}<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><pre xml:space="preserve">&lt;?xml version="1.0" encoding="UTF-8" standalone="yes"?&gt;
&lt;!-- This is a sample file for SSO configuration for Admin component. --&gt;
&lt;SSOConfiguration&gt;</pre><pre xml:space="preserve">    &lt;!-- 
         Configures certificate validation. Validates the Service Provider and 
Identity Providers certificates specified in its configuration. Validation 
happens at start-up and at regular intervals. Optional. 
    --&gt;
    &lt;!-- 
         Attributes:
         1) trustStoreInitializer - Set 
com.axway.st.server.sso.impl.TrustStoreInitializer value for 
trustStoreInitializer in order to use SecureTransport trust store. Recommended 
value: com.axway.st.server.sso.impl.TrustStoreInitializer
         2) delayBetweenValidations - Defines at which interval certificates 
validation occurs, in hours. Default value is 3 hours.
    --&gt;
    &lt;CertificateValidation
            trustStoreInitializer="com.axway.st.server.sso.impl.TrustStoreInitializer"
            delayBetweenValidations="3"&gt; 
    &lt;/CertificateValidation&gt;</pre><pre xml:space="preserve">    &lt;!-- Configures the service provider. --&gt;
    &lt;!-- 
    Main attributes:
        entityId - Sets the unique identifier of the service provider. This 
identifier is sent to the Identity Provider so it can know who is requesting an 
authentication or a logout. This identifier is used by the Identity Provider to 
differentiate what Service Provider is requesting an authentication or a 
logout.
        filteredUri - Specifies the URI of the authentication process entry 
point. The value must be /*
        logoutUri - Specifies the URI which triggers logout process. The value 
must be /logout.
        logoutRedirectUri - Specifies the URI to redirect to the initial logout 
message generated. In turn that message will be redirected to a Identity 
Provider. The value must be /coreadmin/.
        keystoreInitializer - Configures key store to use. That key store keeps 
key-pairs taking part in authentication process. Set 
com.axway.st.server.sso.impl.KeyStoreInitializer value in order to use 
SecureTransport local key store.
        keyAlias - Specifies key alias of the private key used to decrypt SAML 
messages and assertions and to sign SAML messages and assertions.
        sessionIdCookieName - Sets the name of the cookie to store the SSO 
session identifier if sessions are managed by the SSO module.
     --&gt;
    &lt;ServiceProvider
            entityId="st.sso.admin"
            filteredUri="/*"
            logoutUri="/logout"
            logoutRedirectUri="/coreadmin"            
keystoreInitializer="com.axway.st.server.sso.impl.KeyStoreInitializer"
            keyAlias="ssokey"
            sessionIdCookieName="STAdminSsoCookie"
            useAppSessions="false"
            &gt;</pre><pre xml:space="preserve">        &lt;!-- Specifies an entry points for receiving SAML Assertions from the 
Identity Provider. The below tags are recommended. --&gt;
        &lt;AssertionConsumerService 
binding="urn:oasis:names:tc:SAML:2.0:bindings:HTTP-POST" 
location="/saml2/sso/post/j_security_check"/&gt;
        &lt;AssertionConsumerService 
binding="urn:oasis:names:tc:SAML:2.0:bindings:HTTP-Redirect" 
location="/saml2/sso/redirect/j_security_check"/&gt;
        &lt;AssertionConsumerService 
binding="urn:oasis:names:tc:SAML:2.0:bindings:HTTP-PAOS" 
location="/saml2/sso/paos/j_security_check"/&gt;
        &lt;SingleLogoutService 
binding="urn:oasis:names:tc:SAML:2.0:bindings:HTTP-POST" 
location="/saml2/slo/post/j_security_check"/&gt;
        &lt;SingleLogoutService 
binding="urn:oasis:names:tc:SAML:2.0:bindings:HTTP-Redirect" 
location="/saml2/slo/redirect/j_security_check"/&gt;</pre><pre xml:space="preserve">        &lt;!-- Features tag is optional - Here are the default values --&gt;
        &lt;Features&gt;</pre><pre xml:space="preserve">            &lt;!-- Configures the session cookie whether to be set with Secure 
flag. Recommended value: true. --&gt;
            &lt;Feature key="secure-cookie" value="true" /&gt;</pre><pre xml:space="preserve">            &lt;!-- 
                 Type of unique identifier generator to use to assign ids to 
SAML messages. The value must be com.axway.st.server.sso.impl.UIDGenerator
            --&gt;
            &lt;Feature key="uid-generator" 
value="com.axway.st.server.sso.impl.UIDGenerator" /&gt; 
        &lt;/Features&gt;</pre><pre xml:space="preserve">        &lt;!--
            Identity Provider resolution provides support for choosing the 
right Identity Provider based on configuration and run-time metadata. If such 
resolution is not present, the first Identity Provider is selected among ones 
specified under IdentityProviders element below.
            The supported ways to do that are by:
            1) Query parameter provided by a user request (see the example 
below).
            2) Header value provided by a user request. An example follow:
                &lt;Header name="idp_id"&gt;
                    &lt;Mapping value="keycloakIdp" 
entityId="https://st.keycloak.axway.int/" /&gt;
                    &lt;Mapping value="shibbolethIdp" 
entityId="https://st.shibboleth.axway.int/" /&gt;
                &lt;/Header&gt;
                In the example above if a user authentication request has 
header with name 'idp_id' and corresponding value equals to 'keycloakIdp', then 
Identity Provider with entityId equals to https://st.keycloak.axway.int/ will 
be chosen to authenticate the user agent.
           Note: Only one of these way can be done.
        --&gt;
        &lt;IdentityProviderResolution&gt;
            &lt;!-- 
                 Identity provider mapping using a query parameter. The name of 
query parameter resolution will be searched for in request parameters during 
runtime and its value should match to the value attribute of a Mapping element. 
If both query parameter name and value match, then corresponding entityId is 
used to select Identity Provider.
                 Examples:
                         1) https://localhost/?idp_id=keycloakIdp in the below 
case will match the Identity provider with 
entityId=https://st.keycloak.axway.int/
                         2) https://localhost/?idp_id=shibbolethIdp in the 
below case will match the Identity provider with 
entityId=https://st.shibboleth.axway.int/
             --&gt;
            &lt;QueryParameter name="idp_id"&gt; 
                &lt;!-- Note: The name of the query parameter/header should match 
the value of the ST configuration option 
LoginSettings.Admin.SSO.idpResolverKey. --&gt;
                &lt;!-- Note: Ensure the name of the query parameter/header to be 
different than ST configuration option LoginSettings.Admin.SSO.localIdpId in 
order to be able to configure selection of ST as local authentication provider 
and SSO Identity Providers. --&gt;
                &lt;Mapping value="keycloakIdp" 
entityId="https://st.keycloak.axway.int/" /&gt;
                &lt;Mapping value="shibbolethIdp" 
entityId="https://st.shibboleth.axway.int/" /&gt;
            &lt;/QueryParameter&gt;
        &lt;/IdentityProviderResolution&gt;</pre><pre xml:space="preserve">        &lt;!--
            This element is optional.
            Tenant resolution provides support for choosing the right Identity 
Provider based on configuration and run-time metadata. If both tenant 
resolution and identity provider resolutions are present, then tenant 
resolution takes precedence. Tenants are defined inside Identity Providers so 
resolving the IdP in turn will resolve a tenant.
            The supported ways to do that are by:
            1) QueryParameter
                &lt;QueryParameter name="idp_id"&gt;
                    &lt;Mapping tenant="Axway" 
entityId="https://st.keycloak.axway.int/" /&gt;
                    &lt;Mapping tenant="Sopra" 
entityId="https://st.shibboleth.axway.int/" /&gt;
                &lt;/QueryParameter&gt;
            2) Header (example below)
            Notes: 
                  1) Only one of these way can be done.
                  2) Header evaluation takes precedence on query parameter one.
                  3) If mapping is not present, IdentityProviderResolution is 
used. 
                     If IdentityProviderResolution is not present first listed 
IdP is used.
        --&gt;
        &lt;TenantResolution&gt;
            &lt;!-- Note: The name of the query parameter/header should match the 
value of the ST configuration option LoginSettings.Admin.SSO.idpResolverKey. --
&gt;
            &lt;!-- Note: Ensure the name of the query parameter/header to be 
different than ST configuration option LoginSettings.Admin.SSO.localIdpId in 
order to be able to configure selection of ST as local authentication provider 
and SSO Identity Providers. --&gt;
            &lt;Header name="idp_id"&gt;
                &lt;Mapping tenant="Axway" 
entityId="https://st.keycloak.axway.int/" /&gt;
                &lt;Mapping tenant="Sopra" 
entityId="https://st.shibboleth.axway.int/" /&gt;
            &lt;/Header&gt;
        &lt;/TenantResolution&gt;
    &lt;/ServiceProvider&gt;</pre><pre xml:space="preserve">
    &lt;!-- Identity provider definitions. Configures various aspects of 
interaction with identity providers. --&gt;
    &lt;IdentityProviders&gt;
        &lt;!-- A SAML sample IdP definition. --&gt;
        &lt;!-- 
        Main attributes:
            entityId - Sets the unique identifier of the service provider. This 
identifier is sent to the Identity Provider so it can know who is requesting an 
authentication or a logout. Add here EntityDescriptor entityID value, from the 
idpMetadata.xml
            metadataUrl - Specify the relative location of the metadata file. 
Specifies a relative location of the metadata file to sso-admin.xml file.
                      NOTE: ST does not support the metadata URL to be a HTTP 
site.
            verifyAssertionExpiration - Turn on/off verification of the 
validity period of assertions. Consider to set to false if service provider and 
identity provider times are not synchronized. Default: true.
            sign - If set to true, all SAML messages and their assertions sent 
by the service provider will be signed. There are a couple of features (see 
below) for fine-grained control of signing. Optional - if not present, default 
value is false.
            userNameAttribute - Sets the name of the identity provider 
attribute that provides the user name.
         --&gt;</pre><pre xml:space="preserve">         &lt;!-- Sample Keycloak Identity provider definition. --&gt;
        &lt;SamlIdentityProvider
                entityId="https://st.keycloak.axway.int/"
                metadataUrl="./keycloak-idp-metadata.xml"
                verifyAssertionExpiration="false"
                sign="true"&gt;</pre><pre xml:space="preserve">            &lt;!-- Mappings tag is optional --&gt;
            &lt;Mappings&gt;
                &lt;!-- NOTE: SecureTransport does not support the attribute 
mapping for Admin component. --&gt;
            &lt;/Mappings&gt;</pre><pre xml:space="preserve">            &lt;!-- Features control specific behavior of SAML message processing. --&gt;
            &lt;Features&gt;
                &lt;!-- Allows interaction with the IdP by plain HTTP. Default: 
false. --&gt;
                &lt;Feature key="saml-allow-http-connection" value="false"/&gt;</pre><pre xml:space="preserve">
                &lt;!-- Allows unsigned assertions in messages received from the 
Identity Provider. Default: false. --&gt;
                &lt;Feature key="saml-allow-unsigned-assertion" value="false"/&gt;</pre><pre xml:space="preserve">                &lt;!-- 
                    Enable or disable the signature verification of the 
metadata file and the certification path of the certificate used to sign. Set 
to false if metadata file is not signed. Default: true.
                --&gt;
                &lt;Feature key="saml-verify-metadata-signature" value="false"/&gt;</pre><pre xml:space="preserve">                &lt;!-- 
                    Enable or disable signing of Authentication Request 
messages. Presence of this feature and its value overrides the meaning of sign 
attribute of IdentityProvider element above.
                --&gt;
                &lt;Feature key="saml-sign-authnrequest" value="true"/&gt;</pre><pre xml:space="preserve">                &lt;!-- 
                    Enable or disable signing of Logout Request messages. 
Presence of this feature and its value overrides the meaning of sign attribute 
of IdentityProvider element above.
                 --&gt;
                &lt;Feature key="saml-sign-logoutrequest" value="true"/&gt;</pre><pre xml:space="preserve">                &lt;!-- 
                    Enable or disable signing of Logout Response messages. 
Presence of this feature and its value overrides the meaning of sign attribute 
of IdentityProvider element above.
                --&gt;
                &lt;Feature key="saml-sign-logoutresponse" value="true"/&gt;</pre><pre xml:space="preserve">
            &lt;/Features&gt;
        &lt;/SamlIdentityProvider&gt;</pre><pre xml:space="preserve">        &lt;!-- Sample Shibboleth Identity provider definition. --&gt;
        &lt;SamlIdentityProvider
                entityId="https://st.shibboleth.axway.int/"
                metadataUrl="./shibboleth-idp-metadata.xml"
                verifyAssertionExpiration="false" 
                userNameAttribute="urn:oid:0.9.2342.19200300.100.1.1"
                sign="true" &gt;</pre><pre xml:space="preserve">            &lt;!-- Mappings tag is optional --&gt;
            &lt;Mappings&gt;
                &lt;!-- NOTE: SecureTransport does not support the attribute 
mapping for Admin component. --&gt;
            &lt;/Mappings&gt;</pre><pre xml:space="preserve">            &lt;!-- Features control specific behaviour of SAML message 
processing. --&gt;
            &lt;Features&gt;
                &lt;!-- Allows interaction with the IdP by plain HTTP. Default: 
false. --&gt;
                &lt;Feature key="saml-allow-http-connection" value="false"/&gt;</pre><pre xml:space="preserve">                &lt;!-- Allows unsigned assertions in messages received from the 
Identity Provider. Default: false. --&gt;
                &lt;Feature key="saml-allow-unsigned-assertion" value="false"/&gt;</pre><pre xml:space="preserve">                &lt;!-- 
                    Enable or disable the signature verification of the 
metadata file and the certification path of the certificate used to sign. Set 
to false if metadata file is not signed. Default: true.
                --&gt;
                &lt;Feature key="saml-verify-metadata-signature" value="false"/&gt;</pre><pre xml:space="preserve">                &lt;!-- 
                    Enable or disable signing of Authentication Request 
messages. Presence of this feature and its value overrides the meaning of sign 
attribute of IdentityProvider element above.
                --&gt;
                &lt;Feature key="saml-sign-authnrequest" value="true"/&gt;</pre><pre xml:space="preserve">                &lt;!-- 
                    Enable or disable signing of Logout Request messages. 
Presence of this feature and its value overrides the meaning of sign attribute 
of IdentityProvider element above.
                 --&gt;
                &lt;Feature key="saml-sign-logoutrequest" value="true"/&gt;</pre><pre xml:space="preserve">                &lt;!-- 
                    Enable or disable signing of Logout Response messages. 
Presence of this feature and its value overrides the meaning of sign attribute 
of IdentityProvider element above.
                --&gt;
                &lt;Feature key="saml-sign-logoutresponse" value="true"/&gt;</pre><pre xml:space="preserve">
            &lt;/Features&gt;
        &lt;/SamlIdentityProvider&gt;</pre><pre xml:space="preserve">    &lt;/IdentityProviders&gt;
&lt;/SSOConfiguration&gt;</pre>
         </td>
      </tr>
   </tbody>
</table>
