{
    "title": "Using FIPS",
    "linkTitle": "Using FIPS",
    "weight": "220"
}<a href="#Installing_FIPS_support" class="MCXref xref">Installing FIPS support</a>

<a href="#Configuring_security-related_objects_to_be_FIPS_compliant" class="MCXref xref">Configuring security-related objects to be FIPS compliant</a>

<span id="Installing_FIPS_support"></span>

## Installing FIPS support

FIPS mode cannot be toggled from the Gateway configuration panel. You must provide a FIPS-enabled license key which will enable FIPS mode on Gateway.

On an existing Gateway instance, after upgrade to a newer, FIPS compliant release, you must replace the existing license key with a FIPS-enabled one, by running the Configure tool you can find in the installation root.

<span id="Configuring_security-related_objects_to_be_FIPS_compliant"></span>

## Configuring security-related objects to be FIPS compliant

### Keys

In FIPS mode, the following restrictions apply when importing new keys (public or private) in Gateway:

-   the keys of the following types are not accepted by Gateway (the “FIPS restricted” user message is displayed and logged):
    -   ED25519 keys
    -   DSS and RSA keys with lengths up to 1024  
        Note: Gateway supports DSS keys up to 1024 bits only. As a result, DSS keys are no longer usable in Gateway in FIPS mode.  
-   In case of legacy keys (keys imported before FIPS-enablement), if the key does not meet the FIPS 140-2 standard, it is marked in Navigator GUI with a **FIPS restricted** label and icon.

### Certificates

In FIPS mode, the following restrictions apply when importing new certificates (public or private) in Gateway:

-   In case of legacy certificates (imported before FIPS-enablement), if the certificate does not meet the FIPS 140-2 standard, it is marked in Navigator GUI with a “FIPS restricted” label and icon.

### SSH Profiles

In FIPS mode, the following restrictions apply when creating a new SSH Profile in Navigator GUI:

-   the following MAC algorithms are not available: HMAC\_MD5, HMAC\_MD5\_96, HMAC\_SHA\_96

In command line, if you will not be able to

-   create an SSH Profile referring one of the restricted security functions listed above
-   modify an SSH Profile to refer one of the restricted security functions listed above

In case of legacy SSH Profiles (profiles created before FIPS-enablement), if they contain one or more FIPS restricted security functions from the ones listed above, they are not removed from the Profile, they are greyed out in Navigator GUI, but they are not used in data transfer.

If an SSH Profile contains only FIPS-restricted security functions, or if it refers a FIPS restricted public or private key, the execution of any data transfer involving that Profile object will fail.

To remove the non-FIPS settings from an SSH Profile, modify it using the online commands. It is not possible to modify the non-FIPS settings of a legacy SSH Profile from Navigator GUI.

### TLS Profiles

In FIPS mode, the following restrictions apply when creating a new TLS Profile in Navigator GUI:

-   some cipher suites are not available in the **Accepted cipher suites** list. Refer to the *Available in FIPS mode* column of <a href="../../ssl_and_tls_protocols_about/tls_cipher_suites" class="MCXref xref">TLS cipher suites</a>

In command line, you will not be able to

-   create a TLS Profile referring one of the restricted security functions listed above
-   modify a TLS Profile to refer one of the restricted security functions listed above

In case of legacy TLS Profiles (profiles created before FIPS-enablement), if they contain one or more FIPS restricted security functions from the ones listed above, they are not removed from the Profile, they are greyed out in Navigator GUI, but they are not used in data transfer.

If a TLS Profile contains only FIPS-restricted security functions, the execution of any data transfer involving that Profile object will fail.

To remove the non-FIPS settings from a TLS Profile, modify it using the online commands. It is not possible to modify the non-FIPS settings of a legacy SSH Profile from Navigator GUI.

### CGates

In FIPS mode, the following restrictions apply when creating a new CGate object in Navigator GUI:

-   on the **Security** tab, in the **SSH remote authentication** section, the Public key alias list does not contain the FIPS restricted keys
-   on the **Security** tab, in the **TLS and SSH remote certificate filter** section the Subject certificate alias list does not contain the FIPS restricted certificates

In case of legacy CGate objects that refer to FIPS restricted keys or certificates, these are not automatically removed from the CGate object, but any data transfer involving that CGate object will fail.

### Remote Sites

All Remote Site objects having a “Net security” tab to configure are subject to the following restrictions when creating or modifying the Remote Site:

• if the TLS option is selected, the Subject certificate alias list does not contain the FIPS restricted certificates.

In case of legacy Remote Sites referring FIPS-restricted certificates, these are not automatically removed from the Remote Site object, but any data transfer involving that Remote Site object will fail.

Additional restrictions apply to Remote Site objects for specific protocols when creating or modifying the Remote Site, as follows:

#### SFTP

-   in the **Parameters to connect to Remote Site** section:
    -   the Private key alias list does not contain the FIPS-restricted keys
    -   the Certificate alias list does not contain the FIPS-restricted certificates
-   in the **Remote Site authentication** section:
    -   the Public key alias list does not contain the FIPS-restricted keys
    -   the Subject certificate alias list does not contain the FIPS-restricted certificates

If a legacy SFTP Remote Site refers FIPS-restricted keys or certificates, these are not automatically removed from the Remote Site object, but any data transfer involving that Remote Site object will fail.

#### POP3, AS1\_POP3, RosettaNet POP3

-   on the POP3 tab, the “Apop” and “Cram” authentication methods are not available.

If a legacy Remote Site refers one of the “Apop” or “Cram” authentication methods, this setting is not automatically removed from the Remote Site object, but any data transfer involving that Remote Site object will fail.

### Trading Partners

All Trading Partners (except for the SYSTEM\_MESSAGES type) are subject to the following restrictions in the FIPS mode:

-   the Certificate Name list(s) do not contain the FIPS-restricted certificates

If a legacy Trading Partner object refers a FIPS-restricted certificate(s), these are not automatically removed from the Trading Partner object, but any data transfer involving that Trading Partner object will fail.

Related topics  
<a href="../" class="MCXref xref">FIPS standard</a>  
<a href="../../ssl_and_tls_protocols_about/tls_cipher_suites" class="MCXref xref">TLS cipher suites</a>  

 

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
