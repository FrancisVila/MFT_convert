{
    "title": "Certificate types",
    "linkTitle": "Certificate types",
    "weight": "90"
}{{< SecureTransport/componentshortname  >}} uses the following types of certificates overall:

-   **Local Certificates** – Local certificates are used for server authentication. They are also used to decrypt incoming documents and sign documents and receipts. The {{< SecureTransport/securetransportname >}} administrator can generate self-issued local certificates, import local certificates signed by a third-party certificate authority, and export certificate public keys and private keys to a file. For example, if you have a certificate signed by a widely-trusted CA such as Verisign, you can import it as a local certificate and use it for the HTTPS SSL key alias so browsers do not require the user to accept a certificate which they cannot validate. You manage server-scoped local certificates from the Setup menu. For more information, see [Manage local certificates and certificate signing requests](../t_st_localcertificatesandcsrs#top).
-   **Trusted Certificate Authority (CA) Certificates** – CA certificates are used for indirect trust of SSL client or server certificates. {{< SecureTransport/componentshortname >}} includes a set of commonly used CA certificates. For {{< SecureTransport/componentshortname >}} to use imported local certificates, the trusted CA certificates must include certificates for all CAs in their certification paths (certificate chains). CA certificates are only server-scoped, and there are no account‑specific CA certificates.
-   **Internal CA** – A CA is the authority that issues, manages, revokes, and renews certificates, and assists people with performing certificate life cycle tasks such as retrieving, renewing, revoking, and so on. CAs are represented by a certificate that contains the name of the issuer and they are used to sign end-user certificates. An internal CA represents the company that you work for or a company that you pay to issue you a certificate.
-   **Login Certificates** – Client authentication certificates are assigned to a specific user and are required for logging in to {{< SecureTransport/componentshortname >}}. You can use {{< SecureTransport/componentshortname >}} to generate X509 login certificates and to import X509 login certificates and SSH keys. You can manage user certificates from the **Accounts** menu. For more information, see[Manage login certificates](../../../accounts/c_st_usercertificates/t_st_usercertificates#View)[Manage login certificates](../../../accounts/c_st_usercertificates/t_st_usercertificates).
-   **Partner Certificates** – Account-specific public certificates are used for encrypting PGP and AS2 data before sending to the respective account and for verifying the signature of data from the account. Account‑specific certificates can be managed using the **Accounts** menu. For details, see [Manage partner certificates](../../../accounts/c_st_usercertificates/manage-user-partner-certificates) .
-   **Private Certificates** – Account-specific certificates used to decrypt incoming documents and sign documents and receipts. The Certificate Manager can generate self-issued private certificates, import private certificates signed by a third-party certificate authority, and export certificate public keys and private keys to a file. You manage account-specific private certificates from the **Accounts** menu. For more information, see [Manage private certificates](../../../accounts/c_st_usercertificates/manage-user-private-certificates).

**Related topics:**

-   [Certificate Management page](../c_st_certificate_management_page)
-   [Repository encryption certificate](../t_st_repository_encryption_certificate)
-   [Manage local certificates and certificate signing requests](../t_st_localcertificatesandcsrs)
-   [Manage trusted CAs](../t_st_trustedcas)
-   [Manage the internal CA](../t_st_internalca)
-   [Change the certificate keystore password](../t_st_certificatekeystorepasswordca)
-   [Certificates to generate during initial setup](../r_st_certificatestogenerate)
-   [Store certificates in a hardware security module](../t_st_storecertificatesinhsm)
