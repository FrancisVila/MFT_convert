{
    "title": "Security features",
    "linkTitle": "Security features",
    "weight": "70"
}This product contains the following security features:

-   Secure connections, see <a href="#Secure" class="MCXref xref">Secure connections</a>
-   Password management, see <a href="#Password" class="MCXref xref">Password management</a>
-   Certificate management, see <a href="#Certific" class="MCXref xref">Certificate management</a>
-   Identity and access management, see <a href="#Identity" class="MCXref xref">Identity and Access Management</a>
-   Other security features, see <a href="#Other" class="MCXref xref">Other security features</a>

<span id="Secure"></span>

## Secure connections

The following secure connections are available:

-   Connections between the UI and the server are TLS secured.

-   Outbound connection over any supported protocols (FTP, HTTP, AS2, PeSIT) can be TLS secured. SFTP and SCP implement Forward Secrecy and are secured via the SSH protocol by default.  

    > **Note:**
    >
    > Cookies issued over HTTPS use the HTTP Strict Transport Security (HSTS) flag. Additionally, HSTS and HTTPOnly headers are added to the issued cookies for the administrator and end-user HTTP listeners.

-   Inbound connections over any supported protocols can be TLS secured. SFTP and SCP use transport security by default and don’t need to be secured explicitly.

-   Connections to LDAP servers can be TLS secured.

-   Connections to ICAP servers can be TLS secured.

-   Connection to <span class="mc-variable suite_variables.SentinelName variable">Sentinel</span> can be TLS secured.

-   Connections to external Microsoft MSSQL 2014, Oracle 11g, and Oracle 12c databases are TLS secured.

<span id="Password"></span>

## Password management

The following password features are available:

-   Locally stored passwords for administrators and end users are stored hashed using the PBKDF2 key derivation function. The number of iterations can be set using the `Security.Passwords.PBKDF2.Iterations` server configuration option. Default value: 1000.
-   The passwords for transfer sites, and internal servers integrated with SecureTransport like LDAP, external database, Sentinel server, SSO server, ICAP server, etc. are encrypted using the secret (taeh) file.

<span id="Certific"></span>

## Certificate management

Certificate management can either be performed internally in the product or using a supported Hardware Security Module (HSM) with several limitations.

### HSM

<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> supports HSM key management of local certificates. Storing any other type of certificates on HSM is not supported. Only the FTP and HTTP protocol servers can be configured with HSM support.

### When not using HSM

Certificates are stored in JKS keystore persisted in the database.

-   The revocation list and certificate path are not checked.

<span id="Identity"></span>

## Identity and Access Management

Identity and Access Management can either be performed internally in the product using SSO (SiteMinder) or LDAP.

### Internally

The following features are available:

-   Passwords are stored internally in the database and are hashed using PBKDF2.
-   Flexible access restrictions and permission can be configured on per user basis or on a larger scale – user classes and group id.

### SiteMinder

<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> can be integrated into a SiteMinder SSO environment and use SiteMinder to authenticate and authorize all supported client protocols. For more information, refer to the *SiteMinder integration* chapter in the <span class="redirect_st_ag" cshid="admin" data-version="5.3.5">*<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Administrator's Guide*</span>.

<img src="/Images/SecureTransport/SiteMinder_SampleIntegrationModel.png" class="maxWidth" alt="SiteMinder - Sample Integration Model" />

### LDAP

<span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> can be configured to use Lightweight Directory Access Protocol (LDAP) servers to authenticate users and to set up the user session. For more information, refer to the *LDAP integration* chapter in the <span class="redirect_st_ag" cshid="admin" data-version="5.3.5">*<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Administrator's Guide*</span>.

<span id="Other"></span>

## Other security features

The following features are available:

-   ICAP - For more information, refer to the *ICAP settings* section in the *Setup* chapter of the <span class="redirect_st_ag" cshid="admin" data-version="5.3.5">*<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Administrator's Guide*</span>.
-   Email/SNMP/Sentinel notifications on various events - For more information, refer to the *Manage accounts* chapter in the <span class="redirect_st_ag" cshid="admin" data-version="5.3.5">*<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Administrator's Guide*</span>.
-   DMZ support - For additional information, refer to the *Transaction Manager protocol and proxy server communication section* in the *Setup* chapter of the <span class="redirect_st_ag" cshid="admin" data-version="5.3.5">*<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Administrator's Guide*</span>.