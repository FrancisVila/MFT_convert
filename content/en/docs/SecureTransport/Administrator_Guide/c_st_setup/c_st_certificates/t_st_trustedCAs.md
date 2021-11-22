{
    "title": "Manage trusted CAs",
    "linkTitle": "Manage trusted CAs",
    "weight": "130"
}Trusted CAs represent the list of root and intermediate CAs used to build the certificate chain for client and server certificates.

The following topics provide how-to instructions for managing trusted CAs:

-   <a href="#View_trusted" class="MCXref xref">View a trusted CA certificate</a>
-   <a href="#Export_trusted" class="MCXref xref">Export a trusted CA certificate</a>
-   <a href="#Import" class="MCXref xref">Import a trusted CA certificate</a>
-   <a href="#Delete" class="MCXref xref">Delete a trusted CA certificate</a>

<span id="View_trusted"></span>

## View a trusted CA certificate

Use the following procedure to view a trusted CA certificate.

1.  Select **Setup > Certificates**.
2.  Click the **Trusted CAs** tab.  
    The list of trusted certificates is displayed.
3.  Navigate to the page that lists the certificate to view.
4.  Click the alias from the list.  
    The *View Certificate* page displays the detailed information about the certificate.

<span id="Export_trusted"></span>

## Export a trusted CA certificate

Use the following procedure to export a trusted CA certificate.

1.  Select **Setup > Certificates**.
2.  Click the **Trusted CAs** tab.
3.  Navigate to the page that lists the certificate to export.
4.  Click the alias of the certificate to export.
5.  On the *View Certificate* page, click **Export** and save the certificate file in the desired location.

<span id="Import"></span>

## Import a trusted CA certificate

A X509 certificate can be imported as a trusted CA in the form of a X509 DER or PEM encoded file. {{< SecureTransport/componentshortname  >}} checks the certificate fingerprint before importing. If a certificate with the same fingerprint already exists on the server, the new certificate won't be imported and a failure message will be logged in the Server Log.  

> **Note:**
>
> SecureTransport protocol servers and services does not require restart after importing, overwriting, or deleting a trusted certificate.

1.  Select **Setup > Certificates**.
2.  Click the **Trusted CAs** tab.
3.  Click **Import**.
4.  Type an alias for the certificate in the **Alias** box.  
    If you use an alias that is already assigned to another certificate, the imported certificate overwrites the original one. Be sure that you are entering the appropriate alias for the new certificate.
5.  Identify the certificate to import using one of the following methods:
    -   Click **Import certificate from file** and type the file name.
    -   Click **Paste certificate in space below** and paste the certificate text in the box.
6.  Click **Import**.

<span id="Delete"></span>

## Delete a trusted CA certificate

Use the following procedure to delete a trusted CA certificate.

1.  Select **Setup > Certificates**.
2.  Click the **Trusted CAs** tab.
3.  Navigate to the page that lists the certificates to delete.
4.  Select the checkboxes for the certificates to delete.
5.  Click **Delete**.

> **Note:**
>
> If an end user has a certificate issued by a trusted CA that was deleted, the user can no longer authenticate using that certificate.

 

**Related topics:**

-   <a href="../r_st_certificate_types" class="MCXref xref">Certificate types</a>
-   <a href="../c_st_certificate_management_page" class="MCXref xref">Certificate Management page</a>
-   <a href="../t_st_repository_encryption_certificate" class="MCXref xref">Repository encryption certificate</a>
-   <a href="../t_st_localcertificatesandcsrs" class="MCXref xref">Manage local certificates and certificate signing requests</a>
-   <a href="../t_st_internalca" class="MCXref xref">Manage the internal CA</a>
-   <a href="../t_st_certificatekeystorepasswordca" class="MCXref xref">Change the certificate keystore password</a>
-   <a href="../r_st_certificatestogenerate" class="MCXref xref">Certificates to generate during initial setup</a>
-   <a href="../t_st_storecertificatesinhsm" class="MCXref xref">Store certificates in a hardware security module</a>
