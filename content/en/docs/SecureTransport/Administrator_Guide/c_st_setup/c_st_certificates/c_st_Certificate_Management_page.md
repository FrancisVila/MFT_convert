{
    "title": "Certificate Management page",
    "linkTitle": "Certificate Management page",
    "weight": "100"
}To access the *Certificate Management* page, select **Setup &gt; Certificates**.

> **Note:**
>
> In SecureTransport 5.5, regardless of installation type (either fresh install or upgrade from previous version), trusted certificates come with a jdk label in the certificate alias. This indicates that they are imported from JRE and does not affect the SecureTransport operations.

Use the *Certificate Management* page to perform the following certificate management functions:

-   Import certificates
-   Delete certificates
-   Generate self-issued local certificates and certificate signing requests (CSRs)
-   View certificates
-   Export certificates to a file
-   View, delete, or finish pending CSRs

> **Note:**
>
> Because SecureTransport stores the trusted and local certificates and the protocol server configuration in the database and recreates them in the file system when a server starts, you must import certificates into the database using the Administration Tool. You cannot install a certificate by copying it into a directory as you could in previous releases.

**Related topics:**

-   [Certificate types](../r_st_certificate_types)
-   [Repository encryption certificate](../t_st_repository_encryption_certificate)
-   [Manage local certificates and certificate signing requests](../t_st_localcertificatesandcsrs)
-   [Manage trusted CAs](../t_st_trustedcas)
-   [Manage the internal CA](../t_st_internalca)
-   [Change the certificate keystore password](../t_st_certificatekeystorepasswordca)
-   [Certificates to generate during initial setup](../r_st_certificatestogenerate)
-   [Store certificates in a hardware security module](../t_st_storecertificatesinhsm)
