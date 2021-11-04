{
    "title": "Security architecture",
    "linkTitle": "Security architecture",
    "weight": "90"
}## Security architecture

![](/Images/Gateway/gw_sg_sec_arch.png)
![Gateway Security Architecture diagram](/Images/Gateway/Security_architecture_576x408.png)

![Gateway security diagram - legend](/Images/Gateway/Security_architecture_368x165.jpg)

 

<span id="SecurityConfiguration"></span>

## Security configuration

### Creating an SSL/TLS connection

-   Server role  
    For SSL/TLS securing the server role on one of the supported TCP protocols, the user must:
    -   Create a SERVER type SSL/TLS security profile object with details about the TLS
        version to use, cipher suites and algorithms supported, client authentication policy, certificate to use for server
        authentication, trust policy, trusted CAs, extensions used, control and data connection security policies (especially for
        FTP and AS3)
    -   Attach the SERVER SSL/TLS security profile created previously at the network profile
        object attached to the listen port for that protocol and set the network security type to TLS
-   Client role  
    For SSL/TLS securing the client role on one of the supported protocols over TCP, the user must:
    -   Create a CLIENT type SSL/TLS security profile
    -   In the remote site used for connecting to a partner, set the network security to TLS
        and attach the CLIENT SSL/TLS profile as the profile used for outgoing connections
    -   Optionally, if the remote site is used also for handling incoming connection, a SERVER
        SSL/TLS profile can be attached for the incoming connections

### Creating an SFTP connection

#### Server side

For a server side SFTP (SSH) connection, proceed as follows:

-   Create a SERVER type SSH security profile where to specify the algorithms (HMAC,
    public key, encryption etc) supported, the key to use, the trust policy
-   On the network profile for the SFTP listen port, to set the network security type to
    SSH and attach the SERVER SSH profile

#### Client side

  

For a client side SFTP (SSH) connection, proceed as follows:

-   Create a CLIENT type SSH security profile
-   In the remote site used for connecting to a partner, attach the CLIENT SSH profile. If
    no profile is attached to the remote site, Gateway will look by default to a SSH client profile named SFTP\_OUT

### Importing certificates and keys

-   From command line
    -   For importing keys, use `secadm import_key `command

    <!-- -->

    -   RSA keys up to 4096 bits can be imported (DER or PEM format)
    -   DSA keys up to 1024 bits can be imported (DER or PEM format)
    -   ECDSA nistp256, nistp384 and nistp521 keys can be imported (DER or PEM format)

    <!-- -->

    -   For importing certificates use <span class="code">secadm import\_cert </span>command

    <!-- -->

    -   Certificates in PKCS12, DER, PEM(BASE64) or PKCS7 formats are supported
    -   Private keys can be in the same container or in a separate file; formats DER, PEM
        (BASE64), PKCS8 and CR\_PKCS8 are supported
    -   RSA and ECDSA key based certificates are supported
-   From GUI
    -   For importing keys, right click on Security Management->Transfer Security
        Management->Key and select Import
    -   For importing certificates, right click on Security Management->Transfer Security
        Management->Certificate and select Import
-   Auto import keys and certificates
    -   During the SSH and SSL/TLS handshake, partner keys and certificates can be auto imported in Gateway store if the security
        profile is configured for auto-import
    -   Keys and certificates are imported in <span class="code">disabled </span>state and the first handshake attempt fails
    -   Enabling the imported keys and certificates requires user action and should be done only after partner validation

### Associating keys and certificates to partners

-   Keys
    -   Keys alone are used only in the SFTP protocol
    -   If the trust state of a key (the fact that it is imported and enabled) is not secure enough with respect to the company
        policies, the key alias can be attached to a remote site handling the incoming connection as a remote site authentication
        parameter. In this way, the key is associated to the partner corresponding to that remote site
-   Certificates  
    Certificates can be used:
    -   For TLS/SSL authentication

    <!-- -->

    -   If the trust state of a certificate (imported, enabled and having a trusted
        certification path) is not enough, the certificate alias can be attached to a remote site handling the incoming connection
        as a remote certificate filter. In this way the certificate is associated to the partner corresponding to that remote
        site

    <!-- -->

    -   For CMS authentication (OFTP v2)

    <!-- -->

    -   The certificate used for the CMS authentication in OFTPv2 case is selected in the OFTP
        tab of the remote site corresponding to the partner

    <!-- -->

    -   For payload signature and encryption

    <!-- -->

    -   The certificate/certificates used for payload signature and encryption (EDI protocols
        – AS1, AS2, AS3, SMIME mail, OFTPv2 and RosettaNet over mail and HTTP) are selected by their alias in the trading partners
        used in the flow

### Securing the GUI connection to Gateway server

For securing the Navigator connection to Gateway server, do the following:

1.  From the server configuration (in Gateway Navigator), select **Connectivity**->**Navigator server** and check the **Use TLS** option.
    Indicate which user certificate to use for the server. The password for accessing the p12 certificate must be stored using the
    PKCS5 standard (see the chapter about <a href="../../security_features/password_management" class="MCXref xref">Password management</a>)
2.  **Or**, from the command line set <span class="code" xmlns="http://www.w3.org/1999/xhtml">\[cstcp\]TlsActive=’1’</span> , <span class="code" xmlns="http://www.w3.org/1999/xhtml">\[cstcp\]TlsServerCertificateFile</span> and <span class="code" xmlns="http://www.w3.org/1999/xhtml">\[cstcp\]TlsPasswordFile</span> parameters..
3.  When connecting from Navigator and setting up the server connection, check also the **TLS** option and add the appropriate
    certificate for validating the server certificate (the server CA).

### Securing the connection to Passport

Connections to Passport (AM, PM and PS) are not secured by default. Security can be activated at installation time or later
and security parameters must be provided.

-   Passport AM and PM
    -   For Passport version 4.4 and higher, a mutual authenticated TLS connection can be used

        At installation time (or later if necessary) a path to a client certificate used for mutual authentication and the
        password to access this certificate are provided. The client certificate does not exist at this moment.

        At Gateway first start, the product self-registers to Passport. A key-pair is generated and the public key is sent to
        Passport in a Certificate Signing Request. Passport signs the certificate and returns it to Gateway. Then, using the
        private part of the key and the provided password, the certificate is packaged into a P12 format certificate. This
        resulting certificate will be stored in the configured location and will be used for mutual authentication.

    -   For Passport versions below 4.4, only server side authenticated TLS connection can be
        used. In this case, the user must authenticate to Passport using login and password.

        For server side authentication, only the Passport SSL CA certificate, provided with Gateway installation, a user login
        and a password are necessary to connect to Passport in a secure manner.

-   Passport PS

    For securing the Passport PS connection, only server side authenticated TLS connection is available. Connection is not
    secured by default.

    For connecting to Passport PS in a secure way, the Passport SSL CA certificate (provided in Gateway installation), a
    user login and a password are necessary.

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
