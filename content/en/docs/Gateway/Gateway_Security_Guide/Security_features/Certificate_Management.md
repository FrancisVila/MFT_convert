{
    "title": "Certificate Management",
    "linkTitle": "Certificate Management",
    "weight": "140"
}## Certificate Management

Certificate management can either be performed internally in the product or using PassPort PS.

### PassPort PS

The following features are available:

-   The product can be connected to PassPort PS to fully manage certificates. When using PassPort, a full validation of the certificates is done (CRL or OSCP server, full chain validation).
-   Local private keys are stored in the database AES 256 encrypted. The key used to perform this encryption uses a key derived from the password provided at installation time. This password can be changed at any time using the administration UI.
-   The local private keys can also be stored in an HSM (nCipher nShield, WebSentry).
-   CSR can be imported or generated to create a certificate in association with an external CA.

See the <span class="mc-variable suite_variables.PassPortName variable">PassPort</span> documentation for a complete list of features in this product.

### When not using PassPort

The following features are available / not available:

-   The revocation list are not checked  
    Reason: that feature is not available
-   Certificate path are checked.
-   Keys and certificates are stored in a local file database. The database can be encrypted using AES128 by activating object database encryption. The key to encrypt is generated based on a passphrase given at encryption time. The passphrase can be changed at any time from Gateway configuration tools (command line).
-   Certificates with RSA keys up to 8192 bits length can be imported in Gateway (PEM and DER formats are supported).
-   RSA keys up to 4096 bits length can be imported in Gateway (PEM and DER formats are supported)
-   DSS(DSA) keys up to 1024 bits length can be imported in Gateway (PEM/DER)
-   X.509 Certificates can be imported in Gateway (PEM, DER, P12 – single cert or chain). X.509 certificates with RSA or ECDSA keys are supported.
-   At import time, each key or certificate are given an internal name (an alias). When referring to keys or certificates in Gateway store, the <span class="code">Secs alias </span>object type must be used.

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
