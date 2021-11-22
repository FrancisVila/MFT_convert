{
    "title": "Single Sign-On SSO authentication flows",
    "linkTitle": "Single Sign-On (SSO) authentication flows",
    "weight": "210"
}The supported Single Sign-on (SSO) and Single Logout (SLO) authentication flows for SecureTransport are:

-   <a href="#Service" class="MCXref xref">Service Provider initiated Single Sign-On (SSO) authentication flow</a>
-   <a href="#Identity" class="MCXref xref">Identity Provider initiated Single Sign-On (SSO) authentication flow</a>
-   <a href="#Service2" class="MCXref xref">Service Provider initiated Single Logout (SLO) authentication flow</a>
-   <a href="#Identity2" class="MCXref xref">Identity Provider initiated Single Logout (SLO) authentication flow</a>

<span id="Service"></span>

## Service Provider initiated Single Sign-On (SSO) authentication flow

The Service Provider initiated Single Sign-On (SSO) authentication flow describes the following behavior, when administrator or end-user access the protected resource directly on a {{< SecureTransport/securetransportname  >}} site without being logged on. The user account is not managed on the {{< SecureTransport/componentshortname  >}} side, it’s managed by a third-party Identity Provider (IdP). The {{< SecureTransport/componentshortname  >}} sends an authentication request to the Identity Provider. Practically, the authentication for the admin or user is done by an external agent. After authentication the IdP sends the response to {{< SecureTransport/componentshortname  >}}, containing the result of the authentication process and mapped user-specific attributes. {{< SecureTransport/securetransportname  >}} uses these attributes in various scenarios.

<span id="Identity"></span>

## Identity Provider initiated Single Sign-On (SSO) authentication flow

The Identity Provider initiated flow describes the behavior when administrator or end-user chooses the Identity Provider that will be used for the authentication flow. This is configurable through the browser accessing the URL which is provided from the IdP. For that purpose, the Identity Provider first should be configured with specialized links that refer to the desired Service Provider ({{< SecureTransport/componentshortname  >}} in our case).

<span id="Service2"></span>

## Service Provider initiated Single Logout (SLO) authentication flow

The Service Provider initiated flow describes the behavior when the administrator or end-user, has already accessed Service Provider ({{< SecureTransport/componentshortname  >}}) and the authentication is successful. In this case, {{< SecureTransport/componentshortname  >}} initiates logout request that is sent to the IdP. After receiving the logout request from {{< SecureTransport/componentshortname  >}}, the Identity Provider sends a logout response to every other Service Provider which was connected, forcing them to effectively logout the current user. After successful logout, the admin or end-user is redirected to the original IdP login page.

<span id="Identity2"></span>

## Identity Provider initiated Single Logout (SLO) authentication flow

The Identity Provider initiated Single Logout (SLO) flow describes the behavior when the administrator or the end-user, has already accessed the Service Provider ({{< SecureTransport/componentshortname  >}}) and the authentication is successful. Then, IdP request for the logout is executed, and sends a logout request to every other Service Provider which was connected. The logout operation is performed and the administrator or end-user is successfully logged out. After successful logout, the admin or end-user is redirected to the original IdP login page.
