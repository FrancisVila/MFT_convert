{
    "title": "Manage the internal CA",
    "linkTitle": "Manage the internal CA",
    "weight": "140"
}Each {{< SecureTransport/componentshortname  >}} installation maintains its own copy of the internal CA. During the initial post-installation setup procedure, an internal CA is generated. All {{< SecureTransport/componentshortname  >}} Servers in a cluster share the same internal CA. If you have a disaster recovery site, the DR cluster should use the same internal CA, replicated from the primary production site.

> **Note:**
>
> For security reasons, client certificates should only be stored inside the SecureTransport home folder or within a sub-folder of the home folder.

The internal CA can be used to generate server or client certificates. It provides a convenient alternative to using a third-party CA. It is used implicitly in the following cases:

-   Generating a local certificate. For detail, see [Manage local certificates and certificate signing requests](../t_st_localcertificatesandcsrs#top).
-   Generating an account certificate. For detail, see [Manage login certificates](../../../accounts/c_st_usercertificates/t_st_usercertificates#AccountsMenu_2253641766_1090701).
-   Signing imported SSH Keys. For detail, see [Manage login certificates](../../../accounts/c_st_usercertificates/t_st_usercertificates#Import).

The internal CA key is protected with a password. Any operation that involves use of the internal CA require that password. This password cannot be retrieved if it is lost. Contact {{< SecureTransport/companyname  >}} Global Support for more information. For contact information, see [Get more help]().

In addition to issuing certificates signed by internal CA, {{< SecureTransport/componentshortname  >}} supports a few management operations for the internal CA. These operations include:

-   Viewing the internal CA certificate
-   Generating a new internal CA
-   Importing an internal CA
-   Exporting the internal CA

> **Note:**
>
> If you attempt to delete the internal CA, an alert dialog box is displayed. If the certificate of the internal CA is deleted the Validation Status of all X509 local certificates, as well as imported SSH keys (because they are converted to X509 certificates during the import,) become Not chained to a trusted root. This has critical impact on the generated Login Certificates because users are no longer able to log into the SecureTransport Server.

The following topics provide how-to instructions for managing the internal CA:

-   [View the internal CA](#View_internal)
-   [Generate an internal CA](#Generate_internal)
-   [Import an external CA](#Import_external)
-   [Export the internal CA](#Export)

<span id="View_internal"></span>

## View the internal CA

1.  Select **Setup > Certificates**.
2.  Click the **Internal CA** tab.  
    Basic certificate information is displayed including the validation status.

<span id="Generate_internal"></span>

## Generate an internal CA

There are a number of reasons why you might want to generate an internal CA. The most common reason is that the current CA is nearing its expiration date.

1.  Select **Setup > Certificates**.
2.  Click the **Internal CA** tab.
3.  Click **Generate New CA**.  
    The *Generate Internal CA* dialog box is displayed.
4.  Provide the required information for the internal certificate.  
    Internal certificates require the Certificate Subject information. For internal certificates, provide following information:
    -   **Validity in days** – the number of days the certificate is valid.

    -   **CA key password** – the password to protect internal CA. This password is requested when generating certificate signed by the internal CA.

    -   **Confirm CA key password** – the key password must be entered again for confirmation.

    -   **Key Size** – a number representing the size of the generated key, expressed in bits. Possible values are 1024, 2048 (default), 3072, or 4096 bits.

    -   **Signature Algorithm** – the selection of the signature signing hashing algorithm. Possible values are SHA1withRSA, SHA256withRSA (default), SHA384withRSA, and SHA512withRSA.

    -   **Note:**
        >
        > SHA1withRSA is available for backwards compatibility, but its usage is not recommended.

    -   **Common Name** – the name that identifies the certificate.

    -   **Department** – the name of department that the certificate is issued.

    -   **Company** – the name of the company that the certificate is issued.

    -   **City** – the name of the city where the location of the certification is located.

    -   **State** – the name of the state where the location of the certification is located.

    -   **Country** – the name of the country where the location of the certification is located.
5.  Click **Generate**.

Generating a new internal CA does not automatically invalidate the certificate issued by the previous CA. When you generate an internal CA, {{< SecureTransport/componentshortname  >}} adds the certificate to the Trusted CAs list under alias `ca`. The previous internal CA certificate is still in the Trusted CAs list under an alias of the form `ca-old-<serialNumber>`. When you do not want to accept certificates issued by the old internal CA, you can delete the `ca-old-<serialNumber>` aliases from the Trusted CAs list. For detail, see [Delete a trusted CA certificate](../t_st_trustedcas#Delete).

Once the new internal CA is generated, all certificates generated from that point on are signed by the new internal CA. Unless the new internal CA is added to the list of trusted certificates on the remote host, the host might reject the new certificates. An internal CA can be exported into a file that in turn can be used to add the CA to the list of trusted CAs.

<span id="Import_external"></span>

## Import an external CA

Optionally, you can also import an external certificate. Make sure the certificate is valid and configured to validate certificates before you import it. The CA attribute in the X509v3 extension section of the certificate must be true.

1.  On the *Generate CA* page, click **Import CA**.  
    {{< SecureTransport/componentshortname >}} displays *Import Certificate* page.
2.  Type a password in the field provided. The password is required.  
    If the CA certificate requires a pass phrase, {{< SecureTransport/componentshortname >}} uses this password. If the certificate does not require a pass phrase, the password is ignored. {{< SecureTransport/componentshortname >}} also uses this password to encrypt the CA private key in the keystore stored in the database and file system.
3.  Specify the certificate by typing the path to the PKCS#12 (`.p12`) file in the field or by browsing to the file.
4.  Click **Import**.  
    {{< SecureTransport/componentshortname >}} reports if the import was successful.

Now, {{< SecureTransport/componentshortname  >}} uses the imported certificate as the internal CA and signs all certificates generated using that CA. To make sure that a remote host accepts those certificates, add the certificate for this CA to the list of trusted certificates on that host. To export the certificate for import on another system, see [Export the internal CA](#Export).

Generating or importing an internal CA does not automatically invalidate the certificate issued by the previous CA. When you generate or import an internal CA, {{< SecureTransport/componentshortname  >}} adds the certificate to the Trusted CAs list under alias `ca`. The previous internal CA certificate is still in the Trusted CAs list under an alias of the form `ca-old-<serialNumber>`, where `<serialNumber>` is the value of the certificate serialNumber field. When you do not want to accept certificates issued by the old internal CA, you can delete the `ca-old-<serialNumber>` aliases from the Trusted CAs list. For detail, see [Delete a trusted CA certificate](../t_st_trustedcas#Delete).

Once the internal CA is imported, all certificates generated from that point on are signed by the new internal CA. Unless the new internal CA is added to the list of trusted certificates on the remote host, the host might reject the new certificates. An internal CA can be exported into a file that in turn can be used to add the CA to the list of trusted CAs.

After you import a certificate authority, you might need to update the `CertificateStores.CertificateAuthority.serialNo` server configuration parameter. {{< SecureTransport/componentshortname  >}} uses this parameter as a serial number and then increments it every time it generates a certificate. If the imported CA has been used by another {{< SecureTransport/componentshortname  >}} server, set the parameter to the value from that server for consistency. To propagate the change, restart all {{< SecureTransport/componentshortname  >}} servers in the cluster.

<span id="Export"></span>

## Export the internal CA

You can export the internal CA public certificate using the Administration Tool. You can also copy the certificate files from the server file system.

1.  Select **Setup > Certificates**.
2.  Click the **Trusted CAs** tab.
3.  In the Alias column, click **ca**.  
    The *View Certificate* page for the internal CA is displayed.
4.  Click Export to export the public certificate for the internal CA as a `.crt` file.

> **Note:**
>
> The internal CA files are located in the &lt;FILEDRIVEHOME>/lib/certs/db directory as .pem files. The public certificate is ca-crt.pem. The private key is ca-key.pem.

 

**Related topics:**

-   [Certificate types](../r_st_certificate_types)
-   [Certificate Management page](../c_st_certificate_management_page)
-   [Repository encryption certificate](../t_st_repository_encryption_certificate)
-   [Manage local certificates and certificate signing requests](../t_st_localcertificatesandcsrs)
-   [Manage trusted CAs](../t_st_trustedcas)
-   [Change the certificate keystore password](../t_st_certificatekeystorepasswordca)
-   [Certificates to generate during initial setup](../r_st_certificatestogenerate)
-   [Store certificates in a hardware security module](../t_st_storecertificatesinhsm)
