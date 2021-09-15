{
    "title": "Single Sign-On (SSO) configuration",
    "linkTitle": "Single Sign-On (SSO) configuration",
    "weight": "150"
}Prior configuring SecureTransport to use SSO, install and configure your selected [Single Sign-On (SSO)](../../overview5/r_st_axway_and_third-party_software_support).

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">In a SecureTransport deployment, consisting of both backend and edge nodes, SSO must be configured and enabled on all nodes even if users are only logging in through the edge. On the edge, you must enable SSO for end-users.         </td>
      </tr>
</table>

## <span id="Configur"></span>SecureTransport Single Sign-On (SSO) configuration prerequisites

1.  Navigate to **Operations > Server Configuration**. Click on **Configuration Files**.
2.  To download the SSO Configuration Files click on **SSO Configuration Files**. You will be prompted to save the `SSO-configuration-export.zip` file on your file system.
3.  Unzip the `SSO-configuration-export.zip` file.

The default SSO configuration files are:

-   `sso-admin.xml` – Configure the SSO for administrator component. For a sample of a `sso-admin.xml` file, refer [Sample SSO configuration file for administrators](../../r_st_sample_admin).
-   `sso-enduser.xml` – Configure the SSO for end-user component. For a sample of a `sso-enduser.xml` file, refer to [Sample SSO configuration file for end-users](../../r_st_sample_end-users).
-   `krb5-login.conf` – A Kerberos configuration file.
-   `sample-kerberos.keytab` – A Kerberos `.keytab` file.

## Single Sign-On (SSO) configuration files overview

The main SSO configuration files (`sso-admin.xml` for administrators and `sso-enduser.xml` for end-users) are considered mandatory for configuring the SSO functionality in SecureTransport for the respective components.

For the sample SSO configuration files, refer to [Sample SSO configuration file for administrators](../../r_st_sample_admin) and [Sample SSO configuration file for end-users](../../r_st_sample_end-users).

The main SSO configuration file contains the following elements:

-   `<SSOConfiguration>` element – This is the root element of the configuration descriptor. This section contains one `<CertificateValidation>` element (optional), one `<ServiceProvider>` element (required) and one `<IdentityProviders>` element (required).  
    

    <table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">You can specify only one <code>&lt;ServiceProvider&gt;</code> element.         </td>
      </tr>
</table>

-   `<CertificateValidation>` element – Describes the certificate validation. Configures certificate validation. Validates the Service Provider and Identity Providers certificates specified in its configuration. Validation happens at start-up and at regular intervals. This element is optional. Possible attributes for this element:
    -   `trustStoreInitializer` – Set `com.axway.st.server.sso.impl.TrustStoreInitializer` value for `trustStoreInitializer` in order to use SecureTransport trust store.
    -   `delayBetweenValidations` – Defines at which interval certificates validation occurs, in hours. Default value is 3 hours.

-   `<ServiceProvider>` element – Configures the Service Provider. This element is required. Main attributes for this element:
    -   `entityId` – Sets the unique identifier of the Service Provider. This identifier is sent to the Identity Provider so it can know who is requesting an authentication or a logout. This identifier is used by the Identity Provider to differentiate what Service Provider is requesting an authentication or a logout.
    -   `filteredUri `– Specifies the URI of the authentication process entry point. The value must be `/*` for both administrators and end-users.
    -   `logoutUri` – Specifies the URI which triggers logout process. The value must be `/logout` for both administrators and end-users.
    -   `logoutRedirectUri` – Specifies the URI to redirect to the initial logout message generated. In turn that message will be redirected to an Identity Provider. The value must be:
        -   For end-users the required value is `/logoutRedirect`.
        -   For administrators the required value is `/coreadmin`.
    -   `keystoreInitializer` – Configures key store to use. That key store keeps key-pairs taking part in authentication process. Set `com.axway.st.server.sso.impl.KeyStoreInitializer` as value in order to use the SecureTransport local key store.
    -   `keyAlias` – Specifies key alias of the private key used to decrypt SAML messages and assertions and to sign SAML messages and assertions.
    -   `sessionIdCookieName` – Sets the name of the cookie to store the SSO session identifier if sessions are managed by the SSO module.

-   `<AssertionConsumerService>` element – Specifies an entry point for receiving SAML Assertions from the Identity Provider.

-   `<SingleLogoutService>` element - Specifies the Identity Provider URL where the logout responses are sent.  
    

    <table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The recommended values for both <code>&lt;AssertionConsumerService&gt;</code> and <code>&lt;SingleLogoutService&gt;</code> are listed in <a href="../../r_st_sample_admin">Sample SSO configuration file for administrators</a> and <a href="../../r_st_sample_end-users">Sample SSO configuration file for end-users</a>.         </td>
      </tr>
</table>

-   `<Features>` element - The SSO agent can be fine-tuned by using an extra configuration features. In most cases, the values of these features don't have to be modified. The recommended features are:
    -   `<Feature key="secure-cookie" value="true" />` - Configures the session cookie whether to be set with Secure flag. Recommended value is true.
    -   `<Feature key="uid-generator" value="com.axway.st.server.sso.impl.UIDGenerator" />` - Type of unique identifier generator to use to assign ids to SAML messages. The value must be `com.axway.st.server.sso.impl.UIDGenerator`.
        -   `<IdentityProviderResolution>` - For more information, refer to [Multiple Identity Provider configuration](../c_st_multi_idp).
        -   `<TenantResolution>` - For more information, refer to [Multiple Identity Provider configuration](../c_st_multi_idp).

-   `<IdentityProviders>` element - Identity provider definitions. Configures various aspects of interaction with Identity Providers. This element is required. The main attributes for this element are:
    -   `entityId` – Sets the unique identifier of the Service Provider. This identifier is sent to the Identity Provider so it can know who is requesting an authentication or a logout. For SAML-based Identity provider add here `<EntityDescriptor>` element `entityID` attribute value, from the Identity provider metadata file.
    -   `metadataUrl` – Specify the relative location of the Identity provider metadata file. Use only for SAML-based Identity provider.
    -   `configurationUrl` – Specify the configuration file absolute path. Use only for Kerberos-based Identity provider.
    -   `verifyAssertionExpiration` - Turn on/off verification of the validity period of assertions. Consider to set to false if Service Provider and Identity Provider times are not synchronized. Default value is true.
    -   `sign` - If set to true, all SAML messages and their assertions sent by the Service Provider will be signed. There are a couple of features (see below) for fine-grained control of signing. Optional - if not present, default value is false.
    -   `userNameAttribute` - Sets the name of the Identity Provider attribute that provides the user name.

-   `<Mappings>` element:
    -   `<FilterMapping>` - This mapping creates output attributes when a filter matches the input attributes from the Identity Provider. For more information about the Filter Mapping syntax, refer to [SSO filter mapping](../../r_st_sso_filter_mapping).
    -   `<RenameMapping>` - With this mapping, you can rename an attribute from the Identity Provider, keeping its value. For more information, refer to [Accessing Single Sign-On (SSO) attributes](#accessin).

-   `<Features>` element - Features control specific behavior of SAML message processing. The recommended features are:
    -   `<Feature key="saml-allow-http-connection" value="false"/>` - Allows interaction with the IdP by plain HTTP. Default value is false.
    -   `<Feature key="saml-allow-unsigned-assertion" value="false"/>` - Allows unsigned assertions in messages received from the Identity Provider. Default value is false.
    -   `<Feature key="saml-verify-metadata-signature" value="false"/>` - Enable or disable the signature verification of the metadata file and the certification path of the certificate used to sign. Set to false if metadata file is not signed. Default value is true.
    -   `<Feature key="saml-sign-authnrequest" value="true"/>` - Enable or disable signing of Authentication Request messages. Presence of this feature and its value overrides the meaning of the sign attribute of `IdentityProvider` element.
    -   `<Feature key="saml-sign-logoutrequest" value="true"/>` - Enable or disable signing of Logout Request messages. Presence of this feature and its value overrides the meaning of the sign attribute of `IdentityProvider` element.
    -   `<Feature key="saml-sign-logoutresponse" value="true"/>` - Enable or disable signing of Logout Response messages. Presence of this feature and its value overrides the meaning of sign attribute of `IdentityProvider` element above.
    -   `<Feature key="saml-allow-unsigned-assertion" value="false"/>` - Allows unsigned assertions in messages received from the Identity Provider. Default value is false.
    -   `<Feature key="saml-response-binding" value="urn:oasis:names:tc:SAML:2.0:bindings:HTTP-Redirect"/>` - Sets the default response binding value to be `urn:oasis:names:tc:SAML:2.0:bindings:HTTP-Redirect`.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">SecureTransport supports signature and decryption of SAML requests. Adding an extra security layer is highly recommended. Enable SSL by setting <code>&lt;Feature key="saml-allow-http-connection" value="false"/&gt;</code> in the <code>sso-admin.xml</code> and <code>sso-enduser.xml</code> SSO configuration files.         </td>
      </tr>
</table>

## <span id="Accessin"></span>Accessing Single Sign-On (SSO) attributes

When your SSO login is successful, your Identity Provider will forward a set of user attributes to the requested Service Provider (SecureTransport). The SSO attributes are used by SecureTransport to configure user account instances, agent sessions, and advanced routing attributes.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Accessing Single Sign-On (SSO) attributes is not possible when using SSO with Kerberos authentication protocol. It is possible only with SAML.         </td>
      </tr>
</table>

There are several system attributes that are considered important for SecureTransport and there are custom mappings for the attributes:

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Attribute name (Identity Provider)</th>
         <th>Attribute name in SecureTransport*</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><code>email</code>
         </td>
         <td><code>fdxEmail</code>
         </td>
      </tr>
      <tr>
         <td><code>uid</code>
         </td>
         <td><code>fdxUid</code>
         </td>
      </tr>
      <tr>
         <td><code>gid</code>
         </td>
         <td><code>fdxGid</code>
         </td>
      </tr>
      <tr>
         <td><code>homeDir</code>
         </td>
         <td><code>fdxHomeDir</code>
         </td>
      </tr>
   </tbody>
</table>

\*The expected SecureTransport attribute name in order for the attribute to be mapped correctly.

For more information about the SSO attributes, refer to [SSO filter mapping](../../r_st_sso_filter_mapping).

## Access the system attributes

1.  Access the SSO system attributes in an Advanced Routing environment:  
    

    <table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Attribute name</th>
         <th>Expression syntax</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><code>email</code>
         </td>
         <td><code>${sso.email}</code>
         </td>
      </tr>
      <tr>
         <td><code>uid</code>
         </td>
         <td><code>${sso.uid}</code>
         </td>
      </tr>
      <tr>
         <td><code>gid</code>
         </td>
         <td><code>${sso.gid}</code>
         </td>
      </tr>
      <tr>
         <td><code>homeDir</code>
         </td>
         <td><code>${sso.homeDir}</code>
         </td>
      </tr>
      <tr>
         <td><code>tenant</code>
         </td>
         <td><code>${sso.tenant}</code>
         </td>
      </tr>
      <tr>
         <td><code>idpId</code>
         </td>
         <td><code>${sso.idpId}</code>
         </td>
      </tr>
      <tr>
         <td><code>userName</code>
         </td>
         <td><code>${sso.userName}</code>
         </td>
      </tr>
   </tbody>
</table>

2.  Access the SSO system attributes from a Session:  
    

    <table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Attribute name</th>
         <th>Expression syntax</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><code>email</code>
         </td>
         <td><code>${sess.STSESSION_SSO.email}</code>
         </td>
      </tr>
      <tr>
         <td><code>uid</code>
         </td>
         <td><code>${sess.STSESSION_SSO.uid}</code>
         </td>
      </tr>
      <tr>
         <td><code>gid</code>
         </td>
         <td><code>${sess.STSESSION_SSO.gid}</code>
         </td>
      </tr>
      <tr>
         <td><code>homeDir</code>
         </td>
         <td><code>${sess.STSESSION_SSO.homeDir}</code>
         </td>
      </tr>
      <tr>
         <td><code>tenant</code>
         </td>
         <td><code>${sess.STSESSION_SSO.tenant}</code>
         </td>
      </tr>
      <tr>
         <td><code>idpId</code>
         </td>
         <td><code>${sess.STSESSION_SSO.idpId}</code>
         </td>
      </tr>
      <tr>
         <td><code>userName</code>
         </td>
         <td><code>${sess.STSESSION_SSO.userName}</code>
         </td>
      </tr>
   </tbody>
</table>

3.  Access the custom SSO attributes. If we have a custom attribute with name `customAttribute`, you can access the first value in the following manner:
    1.  From a Session:
        1.  `${sess.STSESSION_SSO.customAttribute[0]}`
    2.  From an Advanced Routing environment:
        1.  `${sso.attributes[‘customAttribute’][0]}`
