{
    "title": "Single Sign-On (SSO) and Single Logout (SLO)",
    "linkTitle": "Single Sign-On (SSO) and Single Logout (SLO)",
    "weight": "140"
}Single Sign-On (SSO) is a user authentication process that authenticates the user for all the applications they have been given rights to and eliminates further prompts when they switch applications during a particular session. Essentially, it removes the need for your users to log into multiple applications in a particular browser session. Once they log into one system, it exchanges authentication data with another service you have SSO set up with and automatically logs the user in.

SecureTransport supports signed authentication response assertions and this is transparent to SecureTransport as long as correct configuration is supplied. A signed response proves it is sent from an intended Identity Provider. Adding an extra security layer by disabling plain SAML connections is highly recommended, and it ensures confidentiality. SAML profiles are configured by means of SAML bindings.

The Single Logout (SLO) profile enables a user to log out of all participating sites in a created session nearly simultaneously. The user may log out globally from any site, whether Service Provider (SP) or Identity Provider (IdP), as determined by respective Web applications. The associated IdP deployment handles all logout requests and responses for participating sites.

SecureTransport implements:

-   Single Sign-On (SSO)
-   Single Logout (SLO)

Supported protocols:

-   SAML 2.0 for Administrators and End-users
-   Kerberos 5 for End-users

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">SSO authentication using SAML 2.0 and Kerberos is only applicable for the HTTP protocol.         </td>
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
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">When <span>SecureTransport</span> is behind a reverse proxy/load balancer, the HOST header needs to be modified to match the hostname of the proxy, not the host where the request is proxied to. For Apache this is achieved by setting the <code>ProxyPreserveHost</code> property to <strong>On</strong>. For additional information, refer to <a href="https://httpd.apache.org/docs/2.4/mod/mod_proxy.html#proxypreservehost">https://httpd.apache.org/docs/2.4/mod/mod_proxy.html#proxypreservehost</a>.         </td>
      </tr>
</table>

It also supports user attribute mapping and authentication decisions on attribute maps.

The SSO authentication process is owned and managed by an Identity Provider (IdP). The IdP provides a token authentication object consisting of a user name and a map of attributes. The SecureTransport filters and re-maps the attributes and prepares them to be consumed by SecureTransport.
