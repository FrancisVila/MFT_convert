{
    "title": "Certificates",
    "linkTitle": "Certificates",
    "weight": "70"
}This topic describes the different types of certificates used in <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> and how to import, export, and generate certificates and certificate signing requests.

<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> uses digital certificates for many security functions. These certificates can either be signed by a self-signed Internal Certificate Authority (CA), that is, issued by the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server; signed by an imported internal CA; or signed by a third party, such as an external company like Verisign or a corporate CA. During the installation process, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> installs a default self-signed CA (valid for one month) that you should replace during the initial setup procedures. For details about initial setup procedures for certificates, refer to the <span class="redirect_st_gs" cshid="gs" data-version="5.3.5">*<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Getting Started Guide*</span>. You can also import an external CA to serve as the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> internal CA so that certificates signed by <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> are trusted by clients that trust that CA.

The following topics describe the certificate types and provide how-to instructions for managing certificates.

-   <a href="r_st_certificate_types" class="MCXref xref">Certificate types</a>
-   <a href="c_st_certificate_management_page" class="MCXref xref">Certificate Management page</a>
-   <a href="t_st_repository_encryption_certificate" class="MCXref xref">Repository encryption certificate</a>
-   <a href="t_st_localcertificatesandcsrs" class="MCXref xref">Manage local certificates and certificate signing requests</a>
-   <a href="t_st_trustedcas" class="MCXref xref">Manage trusted CAs</a>
-   <a href="t_st_internalca" class="MCXref xref">Manage the internal CA</a>
-   <a href="t_st_certificatekeystorepasswordca" class="MCXref xref">Change the certificate keystore password</a>
-   <a href="r_st_certificatestogenerate" class="MCXref xref">Certificates to generate during initial setup</a>
-   <a href="t_st_storecertificatesinhsm" class="MCXref xref">Store certificates in a hardware security module</a>