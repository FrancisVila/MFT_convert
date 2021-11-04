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

-   <a href="../r_st_certificate_types" class="MCXref xref">Certificate types</a>
-   <a href="../t_st_repository_encryption_certificate" class="MCXref xref">Repository encryption certificate</a>
-   <a href="../t_st_localcertificatesandcsrs" class="MCXref xref">Manage local certificates and certificate signing requests</a>
-   <a href="../t_st_trustedcas" class="MCXref xref">Manage trusted CAs</a>
-   <a href="../t_st_internalca" class="MCXref xref">Manage the internal CA</a>
-   <a href="../t_st_certificatekeystorepasswordca" class="MCXref xref">Change the certificate keystore password</a>
-   <a href="../r_st_certificatestogenerate" class="MCXref xref">Certificates to generate during initial setup</a>
-   <a href="../t_st_storecertificatesinhsm" class="MCXref xref">Store certificates in a hardware security module</a>
