{
    "title": "Change the certificate keystore password",
    "linkTitle": "Change the certificate keystore password",
    "weight": "150"
}{{< SecureTransport/componentshortname  >}} stores all the available certificates for the system in the Certificate Keystore and the database.

1.  Select **Setup > Certificates**.
2.  Click the **Keystore Password** tab.
3.  Type the old and new passwords, confirming the new one a second time. Leave the **Old Password** field empty if this is the first time you are changing the keystore password and {{< SecureTransport/componentshortname >}} uses the default.
4.  Click **Update**.

> **Note:**
>
> Before you change the password the first time, you do not need to type the old password, because SecureTransport supplies the default value.

**Related topics:**

-   [Certificate types](../r_st_certificate_types)
-   [Certificate Management page](../c_st_certificate_management_page)
-   [Repository encryption certificate](../t_st_repository_encryption_certificate)
-   [Manage local certificates and certificate signing requests](../t_st_localcertificatesandcsrs)
-   [Manage trusted CAs](../t_st_trustedcas)
-   [Manage the internal CA](../t_st_internalca)
-   [Certificates to generate during initial setup](../r_st_certificatestogenerate)
-   [Store certificates in a hardware security module](../t_st_storecertificatesinhsm)
