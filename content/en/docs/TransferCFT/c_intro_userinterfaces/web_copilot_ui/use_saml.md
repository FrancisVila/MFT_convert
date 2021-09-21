{
    "title": "SSO using SAML",
    "linkTitle": "SSO using SAML",
    "weight": "130"
}Transfer CFT supports a web browser single sign-on, SSO, profile that enables users to use the same logging details for Transfer CFT as other Axway products (for example, Flow Manager), eliminating the need to log in multiple times on different web-based UIs.

## Single sign-on using SAML

Single sign-on is a session/user authentication process that can be used to enhance interoperability. The SAML 2.0 standard describes how to exchange authentication and authorization data between entities.

### Security Assertion Markup Language

The Security Assertion Markup Language, SAML, is an XML-based solution for exchanging user security information (authentication, authorization) between an Identity Provider and a Service Provider. SAML is a product of the OASIS Security Services Technical Committee.

### Service Provider

A Service Provider, SP, protects access to requested resources, such as web sites and applications by applying a security policy. For example, the SP blocks all access to an unauthenticated user and routes the request to the Identity Provider. As such, Transfer CFT acts as an SP.

### Identity Provider

An Identity Provider, IdP, is a system that creates, maintains, and manages identity information for users, services, or systems, and provides authentication to other service providers (applications) within a network. An IdP is a trusted entity that users and servers can rely on when they are establishing a dialog that must be authenticated. The IdP sends an attribute assertion containing trusted information about the user to the SP. In an Axway deployment, the IdP is a third-party product.

### User agent

A user agent is usually a web browser. The person who uses the browser can be referred to as a user or as a principal.

## Limitations

-   SAML is not presently available on OpenVMS platforms.
-   You cannot log on Transfer CFT via CFTUTIL if you are using SAML (am.type=saml).

## Prerequisites

To configure and use SAML SSO with Transfer CFT, you must:

-   Have a third-party IdP, such as Keycloak, installed and running.
-   Map the user roles between the IdP and Transfer CFT roles ([CFTROLE](../conf_intro/cftrole)). To view the CFTROLES/CFTPRIV sample, click [here](roles-smp.conf), or navigate locally in your Transfer CFT installation to:
    -   distrib/template/conf/roles-smp.conf
    -   runtime/conf/roles-smp.conf
-   If you use Transfer CFT with Flow Manager, you must manually set the uconf parameter am.type=saml on each Transfer CFT after registering.
-   If you use Transfer CFT with Central Governance, you must manually set the uconf parameter am.type=saml on each Transfer CFT and import all Transfer CFT roles and privileges (CFTROLE and CFTPRIV, respectively) after registering.

## Parameters

This section describes the UCONF parameter settings required for SAML implementation. To set SAML parameters during installation, refer to the settings as indicated in the initialize.properties file page that corresponds with your operating system. The examples below were based on a setup with Keycloak as the IdP.

## Set up SAML 

Configure the Transfer CFT REST API server, as Transfer CFT UI relies on the REST API. See [Configure the REST API server](../../../app_integration_intro/using_apis/api_intro/api_configure).

Insert the IdP certificate, used to sign SAML messages, in the PKI database:  
PKIUTIL PKICER id=idp, iname=&lt;path to the idp certificate>

Set the following UCONF parameters.

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>UCONF value</th>
         <th>Default</th>
         <th>Description</th>
         <th>Example</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>am.saml.client_id         </td>
         <td>$(cft.instance_id)         </td>
         <td>SAML request issuer. This should match the IdP configuration.         </td>
         <td>ITEM-AX12345_tcrieux         </td>
      </tr>
      <tr>
         <td>am.saml.idp.sign_on_service         </td>
         <td> -         </td>
         <td>
            <p>SAML endpoint for  AuthnRequest (HTTP-Redirect binding) requests.</p>
         </td>
         <td>
            <p> https://authserver.host/auth/realms/{realm-name}/protocol/saml</p>
            <p>For example: am.saml.idp.sign_on = https://slnxcftsyncg.int:8443/auth/realms/synapses/protocol/saml</p>
         </td>
      </tr>
      <tr>
         <td>am.saml.idp.logout_service         </td>
         <td>$(am.saml.idp.sign_on_service)         </td>
         <td>
            <p>Endpoint for SAML LogoutRequest (HTTP-Redirect binding) requests.</p>
         </td>
         <td>
            <p> https://authserver.host/auth/realms/{realm-name}/protocol/saml</p>
            <p>For example: am.saml.idp.logout_service = https://slnxcftsyncg.int:8443/auth/realms/synapses/protocol/saml</p>
         </td>
      </tr>
      <tr>
         <td>am.saml.idp.cert_id         </td>
         <td>-         </td>
         <td>Certificate ID (stored in the internal PKI base), which is used to verify the SAML IdP server's signatures.         </td>
         <td>idp         </td>
      </tr>
      <tr>
         <td>am.type         </td>
         <td>-         </td>
         <td>
            <p>Set the am.type=saml</p>
            <p>&amp;&amp;&amp; ïïï ùùù</p>
         </td>
         <td>saml         </td>
      </tr>
   </tbody>
</table>

Define the roles that you require for your Transfer CFT users. To view the CFTROLES sample, click [here](roles-smp.conf), and edit using your favorite text editor.

Start the Copilot server.

<span id="step6"></span>Export the SAML SP (Transfer CFT) metadata.

-   From a web browser, enter the URL https://\[Transfer CFT host\]:\[REST API port\]/saml2/metadata to extract the XML configuration data required to configure your IdP.
-   Save the displayed XML content in a file.

Create your Transfer CFT client in the IdP by importing the saved XML file. Remember that you must create a client for each Transfer CFT.   
**Note**: If you are using Keycloak, set the **Front Channel Logout** option to **OFF**.

Set up the single logout.   
When the IdP connects to Transfer CFT using an HTTPS connection, it validates the Transfer CFT’s certificate to ensure it is connecting to a trusted server. This is necessary in order to prevent man-in-the-middle attacks.

-   Put the Transfer CFT certificate, or the CA that signed the certificate, in the truststore used by the IdP.
-   Refer the specific IdP documentation for more information. For Keycloak details, go to [www.keycloak.org/docs/latest/server\_installation/index.html](https://www.keycloak.org/docs/latest/server_installation/index.html#_truststore).

## Test

From a web browser, enter the URL https://\[Transfer CFT host\]:\[REST API port\]/cft/ui - you are redirected to your IdP and prompted to enter your ID and credentials.

## Revoked user rights

If, as a Transfer CFT administrator or super user, you revoke the rights of a user who is currently logged in, this user can continue their session until they log out or the token expires, unless you expressly revoke all tokens for this user. This is true for both UI and REST API usage.

## Signed SAML headers

Access tokens and SAML headers are signed using the key associated with the certificates referenced by `copilot.ssl.sslcertfile`. If this parameter is not set, but Central Governance or FM is enabled, the governance certificate is used. If you change the certificate that is referenced in `copilot.ssl.sslcertfile` or you modify the   `cg.certificate.governance.key_len `value, the impact is that the corresponding private key changes. This means that once the new key is generated, access tokens and SAML exchanges with the SAML IDP no longer work.

You can see the [Change the private key length](../../../governance_services_intro/cg_postregister) section for details.

If you change the private key, you must repeat the steps 6 - 8 as described [above](#step6).

## Troubleshooting

Error from IDP

After performing the "Set up SAML" steps, sometimes the exported SAML SP (Transfer CFT) metadata is incorrect when imported into the IDP (for example Keycloak) generating an error from the IDP.

Solution: This issue seems to occur when using Firefox. We recommend that you check using another internet browser, such as Chrome.