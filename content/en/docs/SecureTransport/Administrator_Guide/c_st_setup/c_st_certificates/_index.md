{
    "title": "Certificates",
    "linkTitle": "Certificates",
    "weight": "70"
}This topic describes the different types of certificates used in {{< SecureTransport/componentshortname  >}} and how to import, export, and generate certificates and certificate signing requests.

{{< SecureTransport/componentshortname  >}} uses digital certificates for many security functions. These certificates can either be signed by a self-signed Internal Certificate Authority (CA), that is, issued by the {{< SecureTransport/componentshortname  >}} Server; signed by an imported internal CA; or signed by a third party, such as an external company like Verisign or a corporate CA. During the installation process, {{< SecureTransport/componentshortname  >}} installs a default self-signed CA (valid for one month) that you should replace during the initial setup procedures. For details about initial setup procedures for certificates, refer to the . You can also import an external CA to serve as the {{< SecureTransport/componentshortname  >}} internal CA so that certificates signed by {{< SecureTransport/componentshortname  >}} are trusted by clients that trust that CA.

The following topics describe the certificate types and provide how-to instructions for managing certificates.

-   [Certificate types](r_st_certificate_types)
-   [Certificate Management page](c_st_certificate_management_page)
-   [Repository encryption certificate](t_st_repository_encryption_certificate)
-   [Manage local certificates and certificate signing requests](t_st_localcertificatesandcsrs)
-   [Manage trusted CAs](t_st_trustedcas)
-   [Manage the internal CA](t_st_internalca)
-   [Change the certificate keystore password](t_st_certificatekeystorepasswordca)
-   [Certificates to generate during initial setup](r_st_certificatestogenerate)
-   [Store certificates in a hardware security module](t_st_storecertificatesinhsm)
