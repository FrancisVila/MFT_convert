{
    "title": "User certificates",
    "linkTitle": "User certificates",
    "weight": "150"
}<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> supports the following types of certificates for use across the system:

-   PGP and X509 certificates.
-   Server certificates apply to all of the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server and fall into the following three types:
    -   **Local** – Contains a private key and is used by <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Servers.
    -   **Trusted CA** – Used for verification of remote certificates when creating secure connections.
    -   **Internal CA** – a Server Certificate Authority.
-   **User certificates** – These certificates are managed on a "per account" basis from the **Accounts** menu in the Administration Tool. They are generated, imported, exported, and deleted for the respective account. They fall into the following three types:
    -   **Login** – They do not have a private key and are used for logging to <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Servers. Their private key is exported during the generation of the certificate.
    -   **Partner** – They only have a public key and are used for encrypting PGP and AS2 data to an account and verifying the signature of data from the account.
    -   **Private** – They have a private key and are used for decryption and signing of PGP and AS2 data.

> **Note:**
>
> By default, SecureTransport 5.5 does not allow you to import certificates that violate ITU-T X.690 standards. To be able to import such certificates, add the following Java option in &lt;FILEDRIVEHOME>/bin/start\_admin: JAVA\_OPTS="-Dorg.bouncycastle.asn1.allow\_unsafe\_integer=true $JAVA\_OPTS" and restart the Admin daemon.Note that Axway does not recommend the import of such certificates as they can cause encoding issues.

 

The following topics provide how-to instructions for managing user certificates:

-   <a href="t_st_usercertificates" class="MCXref xref">Manage login certificates</a>
-   <a href="manage-user-partner-certificates" class="MCXref xref">Manage partner certificates</a>
-   <a href="manage-user-private-certificates" class="MCXref xref">Manage private certificates</a>
