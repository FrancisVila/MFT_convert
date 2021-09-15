{
    "title": "Certificates to generate during initial setup",
    "linkTitle": "Certificates to generate during initial setup",
    "weight": "170"
}For SecureTransport Edge and SecureTransport Server installations, generate an `admind` SSL server certificate for users connecting to the Administration Tool. This certificate may be signed by the internal SecureTransport CA.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">If this certificate or any of the CA certificates in its certification paths (certificate chains) are expired or otherwise not valid, the Administration Tool server does not start.         </td>
      </tr>
</table>

To use repository encryption or MDN receipts, generate a repository encryption certificate or an `mdn` certificate, respectively. For information about the repository encryption certificate, see [Repository encryption certificate](../t_st_repository_encryption_certificate).

To be able to enable FTPS, HTTPS, AS2 using SSL, SFTP, SCP, or PeSIT over a secured socket, generate the required certificates.

When you set up FTPS, HTTPS, AS2 (SSL), SSH, PeSIT, or SecureTransport Edge communication with the Transaction Manager on the SecureTransport Server, you select a key alias to specify the certificate to use to secure the communications. You created the alias when you generated the certificate. For a list of certificates commonly used with SecureTransport, refer to the <span cshid="gs" data-version="5.3.5">*SecureTransport Getting Started Guide*</span>.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">For more information about the post-installation setup process, refer to the <span data-cshid="gs" data-version="5.3.5"><em><span>SecureTransport</span> Getting Started Guide</em></span>.         </td>
      </tr>
</table>

**Related topics:**

-   [Certificate types](../r_st_certificate_types)
-   [Certificate Management page](../c_st_certificate_management_page)
-   [Repository encryption certificate](../t_st_repository_encryption_certificate)
-   [Manage local certificates and certificate signing requests](../t_st_localcertificatesandcsrs)
-   [Manage trusted CAs](../t_st_trustedcas)
-   [Manage the internal CA](../t_st_internalca)
-   [Change the certificate keystore password](../t_st_certificatekeystorepasswordca)
-   [Store certificates in a hardware security module](../t_st_storecertificatesinhsm)
