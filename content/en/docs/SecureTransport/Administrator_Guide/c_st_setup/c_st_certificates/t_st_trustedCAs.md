{
    "title": "Manage trusted CAs",
    "linkTitle": "Manage trusted CAs",
    "weight": "140"
}Trusted CAs represent the list of root and intermediate CAs used to build the certificate chain for client and server certificates.

The following topics provide how-to instructions for managing trusted CAs:

-   [View a trusted CA certificate](#view_trusted)
-   [Export a trusted CA certificate](#export_trusted)
-   [Import a trusted CA certificate](#import)
-   [Delete a trusted CA certificate](#delete)

## <span id="View_trusted"></span>View a trusted CA certificate

Use the following procedure to view a trusted CA certificate.

1.  Select **Setup > Certificates**.
2.  Click the **Trusted CAs** tab.  
    The list of trusted certificates is displayed.
3.  Navigate to the page that lists the certificate to view.
4.  Click the alias from the list.  
    The *View Certificate* page displays the detailed information about the certificate.

## <span id="Export_trusted"></span>Export a trusted CA certificate

Use the following procedure to export a trusted CA certificate.

1.  Select **Setup > Certificates**.
2.  Click the **Trusted CAs** tab.
3.  Navigate to the page that lists the certificate to export.
4.  Click the alias of the certificate to export.
5.  On the *View Certificate* page, click **Export** and save the certificate file in the desired location.

## <span id="Import"></span>Import a trusted CA certificate

A X509 certificate can be imported as a trusted CA in the form of a X509 DER or PEM encoded file. SecureTransport checks the certificate fingerprint before importing. If a certificate with the same fingerprint already exists on the server, the new certificate won't be imported and a failure message will be logged in the Server Log.  

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top"><span>SecureTransport</span> protocol servers and services does not require restart after importing, overwriting, or deleting a trusted certificate.         </td>
      </tr>
</table>

1.  Select **Setup > Certificates**.
2.  Click the **Trusted CAs** tab.
3.  Click **Import**.
4.  Type an alias for the certificate in the **Alias** box.  
    If you use an alias that is already assigned to another certificate, the imported certificate overwrites the original one. Be sure that you are entering the appropriate alias for the new certificate.
5.  Identify the certificate to import using one of the following methods:
    -   Click **Import certificate from file** and type the file name.
    -   Click **Paste certificate in space below** and paste the certificate text in the box.
6.  Click **Import**.

## <span id="Delete"></span>Delete a trusted CA certificate

Use the following procedure to delete a trusted CA certificate.

1.  Select **Setup > Certificates**.
2.  Click the **Trusted CAs** tab.
3.  Navigate to the page that lists the certificates to delete.
4.  Select the checkboxes for the certificates to delete.
5.  Click **Delete**.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">If an end user has a certificate issued by a trusted CA that was deleted, the user can no longer authenticate using that certificate.         </td>
      </tr>
</table>

 

**Related topics:**

-   [Certificate types](../r_st_certificate_types)
-   [Certificate Management page](../c_st_certificate_management_page)
-   [Repository encryption certificate](../t_st_repository_encryption_certificate)
-   [Manage local certificates and certificate signing requests](../t_st_localcertificatesandcsrs)
-   [Manage the internal CA](../t_st_internalca)
-   [Change the certificate keystore password](../t_st_certificatekeystorepasswordca)
-   [Certificates to generate during initial setup](../r_st_certificatestogenerate)
-   [Store certificates in a hardware security module](../t_st_storecertificatesinhsm)