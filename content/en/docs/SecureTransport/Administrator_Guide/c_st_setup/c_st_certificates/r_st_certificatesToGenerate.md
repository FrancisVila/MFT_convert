{
    "title": "Certificates to generate during initial setup",
    "linkTitle": "Certificates to generate during initial setup",
    "weight": "160"
}For <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge and <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server installations, generate an `admind` SSL server certificate for users connecting to the Administration Tool. This certificate may be signed by the internal <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> CA.

> **Note:**
>
> If this certificate or any of the CA certificates in its certification paths (certificate chains) are expired or otherwise not valid, the Administration Tool server does not start.

To use repository encryption or MDN receipts, generate a repository encryption certificate or an `mdn` certificate, respectively. For information about the repository encryption certificate, see <a href="../t_st_repository_encryption_certificate#top" class="MCXref xref">Repository encryption certificate</a>.

To be able to enable FTPS, HTTPS, AS2 using SSL, SFTP, SCP, or PeSIT over a secured socket, generate the required certificates.

When you set up FTPS, HTTPS, AS2 (SSL), SSH, PeSIT, or <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge communication with the Transaction Manager on the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server, you select a key alias to specify the certificate to use to secure the communications. You created the alias when you generated the certificate. For a list of certificates commonly used with <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>, refer to the <span class="redirect_st_gs" cshid="gs" data-version="5.3.5">*<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Getting Started Guide*</span>.

> **Note:**
>
> For more information about the post-installation setup process, refer to the SecureTransport Getting Started Guide.

**Related topics:**

-   <a href="../r_st_certificate_types" class="MCXref xref">Certificate types</a>
-   <a href="../c_st_certificate_management_page" class="MCXref xref">Certificate Management page</a>
-   <a href="../t_st_repository_encryption_certificate" class="MCXref xref">Repository encryption certificate</a>
-   <a href="../t_st_localcertificatesandcsrs" class="MCXref xref">Manage local certificates and certificate signing requests</a>
-   <a href="../t_st_trustedcas" class="MCXref xref">Manage trusted CAs</a>
-   <a href="../t_st_internalca" class="MCXref xref">Manage the internal CA</a>
-   <a href="../t_st_certificatekeystorepasswordca" class="MCXref xref">Change the certificate keystore password</a>
-   <a href="../t_st_storecertificatesinhsm" class="MCXref xref">Store certificates in a hardware security module</a>
