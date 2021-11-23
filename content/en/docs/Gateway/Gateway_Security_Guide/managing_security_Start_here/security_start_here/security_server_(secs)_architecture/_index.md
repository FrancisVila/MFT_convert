{
    "title": "Security Server (SECS) architecture",
    "linkTitle": "Security Server",
    "weight": "150"
}{{< Gateway/componentlongname  >}}: Managing Security

TLS/SSL and SSH protocol implementation is divided into three parts:

-   [TLS and SSL protocols](../ssl_and_tls_protocols_about)
-   [SSH protocol](../ssh_protocol_about)
-   Security server

As shown in the illustration below, TLS/SSL and SSH protocols are implemented in the network entity so that they are transparent for application protocols. The independent **Security server** (or <span style="font-weight: bold;">SECS</span>) groups the security elements in its database to perform the tasks relating to remote communicating partner mutual authentication (providing/verifying certificates, signing, encrypting/decrypting data). The Security server can operate using an internal manager or external exits.

### Security Implementation within Gateway

The following diagram illustrates security implementation within Gateway.

<img src="/Images/Gateway/Security_architecture.png" class="mediumWidth" />

To operate correctly, the Security server requires at least two kinds of object:

-   <span style="font-weight: bold;">[Network Profiles](../network_profiles_start_here/network_profiles_(gui))</span> that match incoming connections and retrieve the Security Profile to use
-   <span style="font-weight: bold;">Security Profiles</span> that determine security configuration for connections. They can be either:
    -   [TLS Profiles](../ssl_and_tls_protocols_about/tls_security_profiles__gui_)
    -   [SSH Profiles](../ssh_protocol_about/ssh_security_profiles__gui_)

The <span style="font-weight: bold;">Security Profiles</span> store your and your partner’s authentication information. When you use the internal manager, and depending on the level of security you require, you may need any or all of the following:

-   Key exchange algorithms (SSH only)
-   Public key algorithms
    -   X.509 certificates
    -   RSA public key (SSH only)
    -   DSA public key (SSH only)
    -   ECDSA\_NISTP256 public key (SSH only)
    -   ECDSA\_NISTP384 public key (SSH only)
    -   ECDSA\_NISTP521 public key (SSH only)
-   Encryption algorithms
-   MAC algorithms

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
