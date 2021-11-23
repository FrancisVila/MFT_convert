{
    "title": "Password management",
    "linkTitle": "Password management",
    "weight": "130"
}The following password features are available:

Passwords stored in CGate/SGate objects can be stored hashed in the database. To activate password hashing, configuration parameters \[monitor\]disable\_password\_regex='yes' and \[monitor\]cgate\_hashed\_password='yes' should be used.

Passwords to access certificates and keys when importing them in Gateway’s local PKI are used only at import time and they are not stored.

All objects databases can be encrypted using AES128 (see database encryption).

All passwords used to access other products are stored encrypted on the disk using PKCS5 standard. These passwords are:

-   Passwords to client certificates used for securing connections between products ({{< Gateway/passportname >}} AM, Secure Relay, Navigator to Gateway server)
-   Passwords for authenticating Gateway as client in other products ({{< Gateway/passportname >}} PM, {{< Gateway/passportname >}} PS)
-   Password for authenticating remote command line clients to Gateway server

For each of these passwords, three files are stored on disk and path to these files is configured in Gateway:

-   A salt file
-   A derived key file
-   An encrypted password file

Access to these files should be restricted at operating system level only to those users allowed to manage Gateway passwords.

When access management is enabled, the same mechanism is used to encrypt commands (command line utility, exits, scripts). The administration user, decryption key file pathname and encrypted password file pathname are stored in the `p_cs_username, p_cs_dk_file `and `p_cs_encpass_file` environment variables, respectively; access to the decryption key file and encrypted password file should be restricted at operating system level.

The encrypted password files are created with a Gateway tool named `pelencpass`. For more information about creating encrypted password files, refer to [Password Management](../../managing_security_start_here/password_management) .

For partner management, {{< Gateway/passportname  >}} PM can be used in combination with Gateway. In this case, partner passwords and server side passwords (passwords to check) will be stored in the {{< Gateway/passportname  >}} database. Passwords will be provided to Gateway at request together with the rest of the partner information (connection to {{< Gateway/passportname  >}} PM can be TLS secured).

For access management, {{< Gateway/passportname  >}} AM can be used. In {{< Gateway/passportname  >}} AM we can define password policies to meet the company’s requirements for security. User passwords are stored in the {{< Gateway/passportname  >}} AM database. At login time, user login and password are sent to {{< Gateway/passportname  >}} AM for authentication. It is recommended that the connection to {{< Gateway/passportname  >}} AM be TLS secured.

 

Links to documentation set for Axway Gateway {{< Gateway/releasenumber  >}}:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
