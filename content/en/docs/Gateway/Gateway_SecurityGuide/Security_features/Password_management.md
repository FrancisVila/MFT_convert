{
    "title": "Password management",
    "linkTitle": "Password management",
    "weight": "130"
}The following password features are available:

Passwords stored in CGate/SGate objects can be stored hashed in the database. To activate password hashing, configuration parameters \[monitor\]disable\_password\_regex='yes' and \[monitor\]cgate\_hashed\_password='yes' should be used.

Passwords to access certificates and keys when importing them in Gateway’s local PKI are used only at import time and they are not stored.

All objects databases can be encrypted using AES128 (see database encryption).

All passwords used to access other products are stored encrypted on the disk using PKCS5 standard. These passwords are:

-   Passwords to client certificates used for securing connections between products (<span class="mc-variable suite_variables.PassPortName variable">PassPort</span> AM, Secure Relay, Navigator to Gateway server)
-   Passwords for authenticating Gateway as client in other products (<span class="mc-variable suite_variables.PassPortName variable">PassPort</span> PM, <span class="mc-variable suite_variables.PassPortName variable">PassPort</span> PS)
-   Password for authenticating remote command line clients to Gateway server

For each of these passwords, three files are stored on disk and path to these files is configured in Gateway:

-   A salt file
-   A derived key file
-   An encrypted password file

Access to these files should be restricted at operating system level only to those users allowed to manage Gateway passwords.

When access management is enabled, the same mechanism is used to encrypt commands (command line utility, exits, scripts). The administration user, decryption key file pathname and encrypted password file pathname are stored in the <span class="code">p\_cs\_username, p\_cs\_dk\_file </span>and <span class="code">p\_cs\_encpass\_file</span> environment variables, respectively; access to the decryption key file and encrypted password file should be restricted at operating system level.

The encrypted password files are created with a Gateway tool named `pelencpass`. For more information about creating encrypted password files, refer to [Password Management](../../managing_security_start_here/password_management) .

For partner management, <span class="mc-variable suite_variables.PassPortName variable">PassPort</span> PM can be used in combination with Gateway. In this case, partner passwords and server side passwords (passwords to check) will be stored in the <span class="mc-variable suite_variables.PassPortName variable">PassPort</span> database. Passwords will be provided to Gateway at request together with the rest of the partner information (connection to <span class="mc-variable suite_variables.PassPortName variable">PassPort</span> PM can be TLS secured).

For access management, <span class="mc-variable suite_variables.PassPortName variable">PassPort</span> AM can be used. In <span class="mc-variable suite_variables.PassPortName variable">PassPort</span> AM we can define password policies to meet the company’s requirements for security. User passwords are stored in the <span class="mc-variable suite_variables.PassPortName variable">PassPort</span> AM database. At login time, user login and password are sent to <span class="mc-variable suite_variables.PassPortName variable">PassPort</span> AM for authentication. It is recommended that the connection to <span class="mc-variable suite_variables.PassPortName variable">PassPort</span> AM be TLS secured.

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
