{
    "title": "Certifications and compliance",
    "linkTitle": "Certifications and compliance",
    "weight": "40"
}## Compliance

### FIPS 140-2

The current version of this product (Gateway {{< Gateway/componentlongversion  >}}) is FIPS 140-2 level 1 compliant. This compliance is valid on the following platforms:

-   Linux-x86-32
-   Linux-x86-64
-   Sun-sparc-32
-   Aix-power-32
-   Aix-power-64
-   Hp-IA-64

### About FIPS

Federal Information Processing Standards (FIPS) are standards and guidelines that the National Institute of Standards and Technology (NIST) issues for use in United States federal government computer systems.

The Federal Information Processing Standard 140–2 (FIPS 140–2) defines security requirements for cryptographic modules that are used within a security system protecting sensitive but unclassified information, in computer and telecommunication systems. FIPS 140-2 requires organizations that do business with a US Government agency or department that requires the exchange of sensitive information, to ensure that they meet the FIPS 140-2 security standards.

The standard provides four increasing, qualitative levels of security intended to cover a wide range of potential applications and environments. The security requirements cover areas related to the secure design and implementation of a cryptographic module. These areas include:

-   cryptographic module specification,
-   cryptographic module ports and interfaces,
-   roles, services, and authentication,
-   finite state model;
-   physical security;
-   operational environment;
-   cryptographic key management;
-   electromagnetic interference/electromagnetic compatibility (EMI/EMC);
-   self-tests;
-   design assurance;
-   mitigation of other attacks.

For more information, read [SECURITY REQUIREMENTS FOR CRYPTOGRAPHIC MODULES](http://csrc.nist.gov/publications/fips/fips140-2/fips1402.pdf) (a publication of Information Technology Laboratory - National Institute of Standards and Technology)

### Gateway FIPS compliance

Gateway falls under the “Cryptographic key management” area of the FIPS 140-2 standard. As such, when in FIPS mode, Gateway applies restrictions for random number and key generation, key establishment, key distribution, key entry/output, key storage, and key zeroization.

Gateway Server uses the OpenSSL library for encryption. When FIPS mode is enabled, the OpenSSL library is used in FIPS mode.

The Secure Relay Master Agent module included in Gateway Server uses the Entrust FIPS-compliant cryptography provider.

When FIPS mode is enabled, any encryption operation performed within Gateway Server (of either transferred or persisted data) is compliant with the FIPS 140-2 standard.

To ensure this compliance, some restrictions apply in the way Gateway security-related objects are configured, as well as in the execution of the data transfers.

For more information about Gateway and FIPS, refer to the *Gateway [User Guide](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm)*.

Links to documentation set for Axway Gateway {{< Gateway/releasenumber  >}}:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
