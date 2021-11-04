{
    "title": "Security-related HTTP headers and policies",
    "linkTitle": "Security-related HTTP headers and policies",
    "weight": "150"
}This topic presents a list of the most important security-related HTTP headers and their dedicated configuration options in <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>. Setting up these headers in the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> server configuration protects you against many common attacks, including cross-site request forgery, cross-site scripting, clickjacking, etc. Some of these options are not enabled by default as they are not always appropriate and should be configured per business case.

> **Note:**
>
> Changing the value of a configuration option for the Administration Tool server requires Admin service restart to take effect; changing the value of a configuration option for an HTTP server requires HTTP server restart to take effect.

### Referer header validation

Referer is an optional request header that contains the address of the source page from which a request is coming. To defend against CSRF attacks, you can configure <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> to validate the Referer header in incoming HTTP requests against a whitelist of trusted domains. To enable the Referer validation, specify the acceptable header values in the following configuration options:

-   `WebServices.Admin.Referer.Whitelist` - whitelist for Admin API web services
-   `WebServices.Public.Referer.Whitelist` - whitelist for Public API web services

Both configuration options accept regular expressions. The default value for both is **""** (empty), meaning any referrer is allowed.

Also, you can use the `Http.Security.ReferrerPolicy` configuration option to specify the value of the Referrer-Policy header for the HTTP daemon. This header determines what information is sent in the Referer header in an outgoing request. The accepted values are: no-referrer, no-referrer-when-downgrade, origin, origin-when-cross-origin, same-origin, strict-origin, strict-origin-when-cross-origin, unsafe-url. When no value is set, the browser's default is used.

For more information on each directive and its meaning, see [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Referrer-Policy) and [Google Developers](https://developers.google.com/web/updates/2020/07/referrer-policy-new-chrome-default).

### CSRF token protection

Using a CSRF token (also known as synchronizer token) is one of the most popular and recommended methods to prevent Cross-site Request Forgery. <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> has built-in protection: it generates a CSRF token for each active user session and verifies that the token in the received request matches the token stored in the session. By default, the CSRF token protection is disabled. To enable it, set the following options to `true`:

-   `Webservices.Admin.CsrfToken.enabled` for the Administration Tool server
-   `Webservices.Http.CsrfToken.enabled` for the HTTP server

When CSRF token protection is enabled, in order to use the REST API while reusing the same session, you need to make an authentication request to the `/myself` resource to obtain the CSRF token from the `csrfToken `response header. The token must be passed with every subsequent request for the current session using the `csrfToken` header.

### Redirect validation

For additional protection against Open Redirect vulnerabilities, you can configure <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> to allow redirection only to a specified list of domains. To enable this feature, specify the domains that you consider trusted in the `Http.RedirectWhiteList` option. You can either list them explicitly or use a regular expression. Adding a domain to the whitelist results in redirects to this domain and its sub-domains being allowed. The default value of the option is `(^/)`, meaning all domains starting with / are allowed. Redirects to domains that are not whitelisted will be rejected with a 403 error message.

### Host header validation

Host is a mandatory request header that specifies the domain name of the server to which the request is being sent. To mitigate Host header injection attacks, you can configure <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> to check the Host header against a whitelist of permitted domains and reject any requests for unrecognized hosts. To enable this feature, specify a list of acceptable Host header values in the following configuration options:

-   `Webservices.Admin.Host.Whitelist` - list of acceptable Host header values for Admin web services.
-   `Webservices.Public.Host.Whitelist` - list of acceptable Host header values for Public web services.

Both configuration options accept exact values and regular expressions.

Usage examples:

-   If the server configuration value is set to `hostname1, hostname2` that will allow requests that match either of the hostname1 or the hostname2 header.
-   The regular expression `hostname*` will match all Host headers containing a host name in the beginning; `[a-zA-z]+` will match the host names composed of all letters (regardless of case).

### SameSite cookie attribute

The SameSite attribute of the Set-Cookie HTTP response header can be used to disable third-party usage for a specific cookie. To configure the attribute, edit the following configuration options:

-   `Admin.Security.SameSite` for the Administration Tool server. The possible values are `Lax, Unset, None, Strict`, the default is `Lax`.
-   `Http.Security.SameSite` for the default HTTP server. The possible values are `Lax, None, Strict`, the default is `Lax`.

For more information on each directive and its meaning, see [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Set-Cookie/SameSite) and [The Chromium Projects](https://www.chromium.org/updates/same-site).

The SameSite attribute for each newly added HTTP server is set to `Lax` by default. You can change this value by updating the [server's settings](../../../administrator_guide/operations_menu/extended_server_control/ext_servercontrol-add-http#Edit) via either the Administration tool or the REST API.

> **Note:**
>
> Internet Explorer 11 does not support the SameSite cookie attribute.

### X-XSS-Protection

According to how this header is set, if a cross-site scripting attack is detected, the browser will either sanitize the page (remove the unsafe parts) or prevent rendering of the page. To specify the X-XSS-Protection header in server responses, edit the following configuration options to specify an appropriate value:

-   `Admin.Security.XSSProtection` for the Administration Tool server
-   `Http.Security.XSSProtection` for the HTTP server

Possible values:

-   `0` – Disables the XSS filtering.
-   `1` – Enables the XSS filtering. If a cross-site scripting attack is detected, the browser will sanitize the page (remove the unsafe parts).
-   `1; mode=block` – Enables XSS filtering. Instead of sanitizing, the browser will prevent rendering of the page if an attack is detected.
-   `1; report=<report-uri>` – Enables XSS filtering. If a cross-site scripting attack is detected, the browser will sanitize the page and report the violation using the CSP report-uri directive.

### Cache-Control

This header lets you control the caching of specific web pages. In <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>, you can define the caching policy for the Administration Tool pages via the `Admin.ControlCaching` server configuration option. It accepts the following values:

-   `true`– Default; The request cashing is enabled.
-   `false`– The Cache-Control directive is set to `no-cache, no-store` on all static and non-static requests.

> **Note:**
>
> When requests are not being cached, performance degradation may occur.

### Server

The Server header may expose information like your server platform and software. You can remove or limit the content of the header by editing the following server configuration options:

-   `Admin.ServerHeaderTokens` for the Administration Tool server
-   `Http.ServerHeaderTokens`for the HTTP server

Possible values:

-   `Full`– Default; The header field shows the product name, build number, and the operating system (with the result being, for example, `Server: SecureTransport 5.5 (build: 1111) - Linux).`
-   `Prod`– The header field shows the product name, *SecureTransport*.
-   `OS`– The header field shows the operating system on which SecureTransport is running (with the result being, for example, `Server: Linux`)
-   `None`– Depending on the Jetty version, the Server header is not displayed or its field is empty.

### Content-Security-Policy

This header defines content sources that are approved, permitting the browser to load them. To configure your server to return the Content-Security-Policy HTTP header, use the following server configuration options:

-   `Admin.Security.ContentSecurityPolicy` for the Administration Tool server
-   `Http.Security.ContentSecurityPolicy` for the HTTP server

Possible values for both configuration options are:

-   `default-src 'self'`
-   `style-src 'self' 'unsafe-inline'`
-   `script-src 'self' 'unsafe-eval' 'unsafe-inline'`

With `Http.Security.ContentSecurityPolicy`, you can also add the "nonce" attribute in header's `script-src` directive.

For more information on each directive, see the [CSP Quick Reference Guide](https://content-security-policy.com/).

> **Note:**
>
> Content Security Policy is not supported in Internet Explorer 11.

<span id="Strict-T"></span>

### Strict-Transport-Security (HSTS)

This header forces the browser to use only secure (HTTPS) connections. To set the HSTS on <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>, use the following server configuration options:

-   `Admin.Security.Hsts.enabled` – Enables/disables HSTS for the Administration Tool server. Boolean, the default is `true`.
-   `Admin.Security.Hsts.max-age` –The max-age directive in the HSTS header for the Administration Tool server, in seconds. The default is `15768000` (6 months).

<!-- -->

-   `Http.Security.Hsts.enabled` – Shows whether HSTS is enabled for the HTTP Server or not. The value of this configuration option depends on the selection of the **Enable HSTS** checkbox in **Operations->Server Control**. Boolean, the default is `true` which means that HSTS is enabled and an HSTS response will always be sent, redirecting the plain HTTP connection to HTTPS.
-   `Http.Security.Hsts.max-age` – The max-age directive in the HSTS header for the HTTP server, in seconds. The default is `15768000` (6 months).

### X-Frame-Options

This header provides clickjacking protection by not allowing the loading of a page within a frame or iframe. To configure <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> to send the X-Frame-Options header, set the <span class="code">Admin.Security.FrameOptions</span> configuration option to one of the following values:

-   `deny`– The browser will block the resource from loading in a frame.
-   `sameorigin`– The browser will only load the resource in a frame if the request originated from the same site

### X-Content-Type-Options

Configuring your server to return the X-Content-Type-Options response header set to <span class="code">nosniff </span>will instruct browsers that support MIME sniffing to use the server-provided Content-Type and not interpret the content as a different content type. Use the following configuration options:

-   `Admin.Security.ContentTypeOptions` for the Administration Tool server

<!-- -->

-   `Http.Security.ContentTypeOptions` for the HTTP server

### Expect-CT

The Expect-CT header identifies the usage of wrongly issued certificates for a site and allows sites to decide on reporting and/or enforcement of [Certificate Transparency](https://www.certificate-transparency.org/) requirements. The header has effect on HTTPS connections only.

To configure the SecureTransport Administration Tool and ST Web Client to respond with Expect-CT header, use their corresponding server configuration options:

-   `Admin.Security.ExpectCT` for the Administration Tool server
-   `Http.Security.ExpectCT` for the HTTP server

Both options accept a semicolon- (;) or comma-separated list of the [Expect-CT header directives](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Expect-CT): `max-age=<age>;` `enforce`; `report-uri=<uri>`. The `report-uri=<uri>` and `enforce` directives are optional. Depending on their presence, Expect-CT will only report violations, enforce compliance to the Certificate Transparency policy, or both report and enforce.

Examples:

-   To enforce Certificate Transparency for an hour, set the server configuration value to `max-age=3600; enforce`.
-   To enforce Certificate Transparency for 12 hours and report violations to www.st-report.com, set the server configuration value to:
-   `max-age=43200; enforce; report-uri="https://www.st-report.com/"`
