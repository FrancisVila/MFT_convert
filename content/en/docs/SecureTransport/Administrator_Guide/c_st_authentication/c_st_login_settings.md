{
    "title": "Login settings",
    "linkTitle": "Login settings",
    "weight": "250"
}You can use the *Login Settings* page to disable or require Single Sign-On (SSO), enable or disable certificate authentication and to specify client certificate authentication for administrators, enable or disable password authentication and set LDAP and SiteMinder authentication levels for end-users.

The following topics describe the end-user and administrator login options:

-   [End-user login options](#end-user)
-   [Administrator login options](#administ)

## <span id="End-user"></span>End-user login options

You can use the end-user login options to disable or require end-user Single Sign-On (SSO), check the current pluggable authentication status, enable or disable password authentication, or specify for which classes it will be applied, and set LDAP and SiteMinder authentication levels.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The end-user login options Password, LDAP, and SiteMinder are not available on the <span>SecureTransport</span> Edges.         </td>
      </tr>
</table>

### Disable or require end-user Single Sign-On (SSO)

Use the following procedure to disable or require end-user Single Sign-On (SSO).

1.  Select **Authentication > Login Settings**.  
    The *Login Settings* page is displayed.
2.  Under *End-user login options* in the **SSO** drop-down menu, select one of the following values:
    -   **Disabled** - SSO will not be used.

    -   **Required** - Redirection to Identity provider will always be performed. If the authentication with the Identity Provider (IdP) fails, the login will be rejected. This state will override any of the existing authentication methods via HTTP(s) for end-user - Certificate for HTTPS, LDAP with HTTP(s) and SiteMinder.

    -   <table cellpadding="0" cellspacing="0">   <col/>   <col/>   <col/>      <tr>         <td valign="top">         </td>         <td valign="top"><span><b>Note</b></span>         </td>         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Requires Transaction Manager service restart on back-end.         </td>      </tr></table>

        <table cellpadding="0" cellspacing="0">   <col/>   <col/>   <col/>      <tr>         <td valign="top">         </td>         <td valign="top"><span><b>Note</b></span>         </td>         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">SSO login option is applicable only for HTTP(s).         </td>      </tr></table>
3.  Click **Save**.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">In order to configure SSO go to: <em>Server Configuration Files</em> edit page.         </td>
      </tr>
</table>

For information on editing and updating the server configuration files, refer to [Single Sign-On (SSO) and Single Logout (SLO)](../c_st_about_sso).

### Pluggable authentication

Shows the Pluggable authentication status and provides a link to the Server Configuration option related with the end-user's available deployed custom plug-ins list.

For information, refer to [Pluggable authentication](../pluggable_authentication).

### End-user password authentication

This option allows you to specify whether the end users need to provide a password in addition to authenticating with a certificate. The *Client Certificate* option can be configured per server. For information, refer to [Server control](../../operations_menu/extended_server_control).

Use the following procedure to specify password authentication for end-users.

1.  Select **Authentication > Login Settings**.  
    
    The *Login Settings* page is displayed.
2.  Under *End-user login options*, select one of the three options in the **Password** drop-down menu to specify password authentication for end-users.  
    **Optional** - A password is required only if a certificate is not presented.  
    **Required** - A password is required in addition to certificate authentication option for users from all user classes.  
    **Required for user classes** - A password is required in addition to certificate authentication option only for one or more comma-separated user classes inserted in the text field. User classes are case sensitive.
3.  Click **Save**.

### Enable or disable LDAP

Use the following procedure to enable or disable LDAP.

1.  Select **Authentication > Login Settings**.  
    The *Login Settings* page is displayed.
2.  Under *End-user login options* in the **LDAP** drop-down menu, select one of the following values:  
    **Disabled** - The LDAP will not be used.  
    **Optional** - SecureTransport searches the SecureTransport database before it searches the LDAP databases in the default domains. If no such user is found in SecureTransport and LDAP databases, then the login will be rejected.  
    **Required** - An LDAP user will be required. If no such user exists, the login will be rejected.  
    For details, see [LDAP logins](../c_st_ldap_logins).
3.  Click **Save**.
4.  Restart the TM Server.

You must create one or more domains before SecureTransport can use LDAP to authenticate users. For information on creating LDAP domains, refer to [Create an LDAP domain](../t_st_ldapsettings/t_st_create_domain).

### Enable or disable SiteMinder

Use the following procedure to enable or disable SiteMinder.

1.  Select **Authentication > Login Settings**.  
    The *Login Settings* page is displayed.
2.  Under *End-user login options* in the **SiteMinder** drop-down menu, select one of the following values:  
    **Disabled** - The SiteMinder configuration will not be used.  
    **Optional** - The SiteMinder configuration may be used.
3.  Click **Save**.

You must configure SiteMinder before you can use SiteMinder to authenticate users. For information on configuring SiteMinder, refer to [SiteMinder integration configuration](../t_st_siteminderintegrationconfiguration).

## <span id="Administ"></span>Administrator login options

You can use the administrator login options to enable or disable administrator Single Sign-On (SSO), check the current pluggable authentication status, and to enable or disable administrator certificate requirements.

### Enable or disable administrator Single Sign-On (SSO)

Use the following procedure to enable or disable administrator Single Sign-On (SSO).

1.  Select **Authentication > Login Settings**.  
    The *Login Settings* page is displayed.
2.  Under *Administrator login options* in the **SSO** drop-down menu, select one of the following values:
    -   **Disabled** - SSO will not be used.
    -   **Required** - Redirection to the Identity Provider (IdP) will always be performed. If the authentication with the IdP fails, the login will be rejected.
3.  Click **Save**.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">User classes with a comma inside their 'Class Name' should not be used due to the comma being a delimiter.         </td>
      </tr>
</table>

For information on editing and updating the server configuration files, refer to [Update configuration files](../../operations_menu/c_st_serverconfiguration/t_st_serverconfigurationfiles).

### Pluggable authentication

Shows the Pluggable authentication status and provides link to the Server Configuration option related with the end-user's available deployed custom plug-ins list.

For information, refer to [Pluggable authentication](../pluggable_authentication).

### Configure administrator certificate requirement and level

Set the certificate settings to allow administrators to log in by using a client certificate or to use dual authentication with both a certificate and a password. You can enable the ability to login with a client certificate, determine whether the certificate is optional or required, select the certificate issuer, and set the certificate chain limit.

When you want to access the Administration Tool and you have enabled client certificates, you are prompted to select the certificate you are using. Once the certificate is verified, you are logged in unless dual authentication is required. If certificates are optional and you do not select one, the login page is displayed. If SecureTransport cannot verify the certificate, or certificates are required and you did not select one, a connection error displays and you cannot log in.

If you are unable to successfully log in when using a certificate, clear the browser's SSL state, or close the browser and try again with a new browser instance.

1.  Select **Authentication > Login Settings**.
2.  The *Login Settings* page is displayed.
3.  Under *Administrator login options*, select **Certificate** to allow administrators to log in using client certificates.  
    The *Client Certificate Settings* pane and the remaining fields are displayed.
4.  Select either **Optional** or **Required** in the **Client certificates** drop-down menu. If you select **Optional**, administrators do not need a certificate. If you select **Required**, each administrator must have a client certificate set up. If certificates are required, all administrators must be mapped to a certificate, and all users must present a valid trusted certificate to gain access to the login page.
5.  Select one of the following choices from the **Accept certificates issued by** drop-down menu:
    -   **internal issuer only** – The certificate must be issued by the internal CA. See [Manage the internal CA](../../c_st_setup/c_st_certificates/t_st_internalca).
    -   **any trusted issuer** – The certificate must be issued by a CA that is trusted by one of the CAs listed as a trusted CA. See [Manage trusted CAs](../../c_st_setup/c_st_certificates/t_st_trustedcas).
    -   **issuer file or path** – The certificate must be issued by a CA whose certificate is in a file you specify.
6.  If you select **issuer file or path:**, the following fields are displayed:
    -   A field that you use to specify the location of the certificate PEM-encoded (`.pem`) file or a directory that contains the PEM-encoded files.
    -   You can type either a fully qualified file or path names or a file or path names relative to &lt;`FILEDRIVEHOME>`. Do not put the PEM-encoded files in the keystore directory, `<FILEDRIVEHOME>/lib/certs/issuers`, because the certificates in that directory are regenerated from the database when servers start.
    -   A **Limit certificate chain depth to** field. Type a number that sets the maximum number of levels for SecureTransport to go through in validating the certificate up to a trusted root. For example, if you set the chain depth to 1, then only a certificate issued directly by a trusted root is allowed and a certificate issued by an intermediate CA is rejected.
7.  Click **Save**.
8.  Restart the Administration Tool server using the `stop_admin` and `start_admin` commands. If you are running on Windows, you can also use the **Services** console to restart the `admin` service.

If you choose to use certificates for administrator logins, a **Certificate DN** field displays in the *New Administrator* and *Edit Administrator* pages where you must provide the certificate domain name information. For more information, see [Add an administrator account](../../c_st_advancedaccountadministration/c_st_manageadministratoraccounts/t_st_add_administrator_account).

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">To enable or disable password authentication for Specific user classes from REST API you must update both configuration options.         </td>
      </tr>
</table>
