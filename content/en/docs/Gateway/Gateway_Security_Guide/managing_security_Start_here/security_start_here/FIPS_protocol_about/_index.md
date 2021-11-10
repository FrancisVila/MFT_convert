{
    "title": "FIPS standard",
    "linkTitle": "FIPS",
    "weight": "200"
}<span id="About_FIPS"></span>

## About FIPS

<span id="Application-level_protocols"></span>

### Application-level protocols

The application-level protocols subject to FIPS compliance are SFTP, FTPS, HTTPS, AS1, AS2, AS3, OFTP, POP3, SMTP, RosettaNet, PeSIT.

The restrictions apply both in the configuration of these protocols and in the data transfer execution.

#### Transport-level protocols

The transport-level protocols subject to FIPS compliance are: TLS, SSH.

The restrictions apply both in the configuration of these protocols and in the data transfer execution.

<span id="Keys_and_certificates_management"></span>

### Keys and certificates management

In FIPS mode, it is forbidden to import in Gateway keys or certificates which do not comply with FIPS 140-2 standard.

The non-compliant keys and certificates imported prior to the activation of the FIPS mode are marked as FIPS restricted and cannot be referenced by other security-related objects (security profiles, Remote Sites, etc).

If the security-related objects created prior to the activation of the FIPS mode and referencing non-compliant keys or certificates are being used in data transfers, those transfers will fail.

<span id="Interoperability_with_other_Axway_products"></span>

### Interoperability with other Axway products

When FIPS mode is enabled, the secure communication between <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> and <span class="mc-variable suite_variables.PassPortName variable">PassPort</span> (AM, PM, PS) is FIPS compliant.

Note: when FIPS mode is enabled, it is recommended to use PassPort PS as a PKI.

### For more information...

For more information about Gateway and FIPS, refer to Gateway [User Guide](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm).

For more information, read [SECURITY REQUIREMENTS FOR CRYPTOGRAPHIC MODULES](http://csrc.nist.gov/publications/fips/fips140-2/fips1402.pdf), a publication of Information Technology Laboratory - National Institute of Standards and Technology.

Related topics:  
<a href="using_fips" class="MCXref xref">Using FIPS</a>  
<a href="../ssl_and_tls_protocols_about/tls_cipher_suites" class="MCXref xref">TLS cipher suites</a>

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
