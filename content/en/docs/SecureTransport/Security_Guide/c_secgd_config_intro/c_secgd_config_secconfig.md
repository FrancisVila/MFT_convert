{
    "title": "Security configuration",
    "linkTitle": "Security configuration",
    "weight": "120"
}For information on how to configure <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> security, refer to the *Setup* chapter in the <span class="redirect_st_ag" cshid="admin" data-version="5.3.5">*<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Administrator's Guide*</span>.

## How to implement connection with Transfer CFT over PeSIT (TLS)

In order to configure PeSIT over TLS connection between Transfer CFT and <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>, a cipher suite supported by Transfer CFT has to be enabled. For example: `TLS_RSA_WITH_AES_256_CBC_SHA`

> **Note:**
>
> Remember to keep all cipher suites separated by commas.

1.  In the Administration Tool, navigate to **Operations > Server Configurations**.
2.  Search for parameter: `Pesit.Listeners.Ssl.enabledCipherSuites`
3.  Click the **Edit** (![](/Images/SecureTransport/EditIcon.png)) icon.
4.  Add `TLS_RSA_WITH_AES_256_CBC_SHA` at the end of the cipher suite list.
5.  Click the **Save** (![](/Images/SecureTransport/SaveIcon.png)) icon.
6.  Restart the PeSIT service.

For Server Initiated Transfers, the cipher also has to be added to the `Pesit.SIT.Ciphers` parameter.

## How to implement connection with an older version of <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>

In order to implement a connection with an older version of <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> at least one cipher on <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> <span class="mc-variable axway_variables.Release_Number variable">5.5</span> must match with the ciphers on the older version of <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>.

**For server-initiated transfers:**

1.  In the Administration Tool, navigate to **Operations > Server Configurations**.
2.  Search for parameter based on the protocol used (FTP, HTTP, AS2, PeSIT): `<protocol>.SIT.Ciphers`
3.  Click the **Edit** (![](/Images/SecureTransport/EditIcon.png)) icon.
4.  Add a cipher in common with the older version of <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> at the end of the cipher suite list.
5.  Click the **Save** (![](/Images/SecureTransport/SaveIcon.png)) icon.
6.  Restart Transaction Manager.

Optionally, for <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> servers using MD5 with RSA signature algorithm for local certificates, go to the `java.securty` file and enable the use of signature certificates.

**For client-initiated transfers:**

1.  In the Administration Tool, navigate to **Operations > Server Configurations**.
2.  Search for parameter based on the protocol used (FTP, HTTP, AS2, PeSIT): `<protocol>.Listeners.Ssl.enabledCipherSuites`
3.  Click the **Edit** (![](/Images/SecureTransport/EditIcon.png)) icon.
4.  Add a cipher in common with the older version of <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> at the end of the cipher suite list.
5.  Click the **Save** (![](/Images/SecureTransport/SaveIcon.png)) icon.
6.  Restart the protocol service.

Optionally, for <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> servers using MD5 with RSA signature algorithm for local certificates, go to the `java.securty` file and enable the use of signature certificates.
