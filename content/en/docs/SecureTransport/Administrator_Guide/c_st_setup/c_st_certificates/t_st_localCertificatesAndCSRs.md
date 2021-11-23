{
    "title": "Manage local certificates and certificate signing requests",
    "linkTitle": "Manage local certificates and certificate signing requests",
    "weight": "120"
}Use the *Certificate Management* page to generate local, self-issued server certificates or to generate certificate signing requests. Generated certificates are assigned RSA or DSA keys.

A certificate signing request is an unsigned copy of a certificate that you submit to a CA when requesting a signed certificate. Based on the information in the CSR, the CA creates a new signed certificate for your use. After receiving the signed certificate from the CA, you must import it into {{< SecureTransport/componentshortname  >}}. For details, see [Import a new certificate for a pending certificate signing request](#Import2).

The following topics describe and provide how-to instructions managing local certificates and certificate signing requests:

-   [View local certificates](#View_loc_cert)
-   [Generate a self-issued server certificate](#Generate)
-   [Generate a certificate signing request](#Generate_cert_sign)
-   [Import a new certificate for a pending certificate signing request](#Import2)
-   [Delete a pending certificate signing request](#Delete_pend_cert_sign)
-   [Export a local certificate](#Export)
-   [Import a local certificate](#Import)
-   [Import an SSH key](#Import_SSH)
-   [Delete a local certificate](#Delete_loc_cert)

<span id="View_loc_cert"></span>

## View local certificates

You can view a list of all the local certificates or view the details of a specific certificate.

1.  Select **Setup > Certificates**.
2.  Click the **Local Certificates** tab.
3.  Select a certificate alias from the list.

The *View Certificate* page displays the detailed information about the certificate.

<span id="Generate"></span>

## Generate a self-issued server certificate

Use the following procedure to generate a self-issued server certificate.

1.  Select **Setup > Certificates**.
2.  Click the **Local Certificates** tab.
3.  Click **Generate**.
4.  Select **Self-issued Certificate**.
5.  Type the required information for the self-issued certificate, including the fields that are displayed below the **Certificate Signing Request** option.  
    The alias name should contain only lower case letters, digits, and hyphens (`-`). It must be at most 80 characters long. If the alias name you type is already assigned to another certificate, you are prompted to overwrite the existing certificate or cancel the operation.  
    You can overwrite any existing certificate including the default {{< SecureTransport/componentshortname >}} `admind` server certificate.
6.  Click **Generate**.

> **Note:**
>
> When regenerating or overwriting the admind certificate or any certificate used in the daemons configuration, all services must be restarted.

<span id="Generate_cert_sign"></span>

## Generate a certificate signing request

A certificate signing request (CSR) is a request to an external CA to sign a certificate.

1.  Select **Setup > Certificates**.
2.  Click the **Local Certificates** tab.
3.  Click **Generate**.
4.  Select **Certificate Signing Request (CSR)**.
5.  Type the required information for the certificate signing request.  
    The **Common Name (CN)** field must be the FQDN to be secured by the CA-signed certificate.
6.  Click **Generate**.  
    A message is displayed that explains how to download the CSR and send it to your CA.

The CSR is displayed in the list of Pending Local Certificates where it remains until you delete it or import the signed certificate you receive from the CA. You cannot use the new CA-signed certificate until you import it into {{< SecureTransport/componentshortname  >}}.

<span id="Import2"></span>

## Import a new certificate for a pending certificate signing request

Use the following procedure to import a new certificate for pending certificate signing request.

1.  Select **Setup > Certificates**.
2.  Click the **Local Certificates** tab.
3.  Click **Finish** beside the appropriate CSR in the Pending Local Certificates list.
4.  In the **Certificate Alias** box, type an alias.
5.  Identify the certificate to import using one of the following methods:
    -   Click **Import CA signed certificate from file** and specify the file name.
    -   Click **Paste CA signed certificate in space below** and paste the certificate text in the box.
6.  Click **Finish**.  
    The certificate is displayed in the list of local certificates.

After you have imported the certificate, to use the certificate for a protocol server, set the Key Alias to the certificate alias and restart the protocol server. You can also use the certificate for other purposes, for example, as a login certificate for a transfer site or as an encryption or signing certificate for an AS2 transfer site.

<span id="Delete_pend_cert_sign"></span>

## Delete a pending certificate signing request

Use the following procedure to delete a pending certificate signing request.

1.  Select **Setup > Certificates**.
2.  Click the **Local Certificates** tab.
3.  Click **Delete** beside the appropriate CSR in the Pending Local Certificates list.

<span id="Export"></span>

## Export a local certificate

Use the following procedure to export a local certificate.

1.  Select **Setup > Certificates**.
2.  Click the **Local Certificates** tab.
3.  Click the alias of the certificate to export.  
    The *View Certificate* window displays the certificate details.
4.  To export a PGP certificate:
    1.  Click **Export**.
    2.  In the *Export Certificate* window, click **Export** to save the certificate as an ASCII-Armored (`.asc`) file, or select **Export private key**, type and confirm a password, and click **Export** to save the certificate as an `.asc` file with the private key.
5.  To export a PGP certificate:
    1.  Click **Export**.
    2.  In the *Export Certificate* window, click **Export** to save the certificate as an ASCII-Armored (`.asc`) file, or select **Export private key**, type and confirm a password, and click **Export** to save the certificate as an `.asc` file with the private key.
6.  To export an X509 certificate:
    1.  Click **Export**.
    2.  In the *Export Certificate* window, click **Export** to save the certificate as a PEM-encoded certificate (`.crt`) file, or select **Export private key**, type and confirm a password, and click **Export** to save the certificate as a PKCS#12 (`.p12`) file.
7.  To export an X509 certificate public key:
    1.  Click **Export**.
    2.  In the *Export Certificate* window, click **Export SSH Public Key** to save the public key as a `.pub` file.

<span id="Import"></span>

## Import a local certificate

You can import a private key and the corresponding certificate in **Local Certificates** as a PKCS#12 (`.p12`) file. You can then use it where you need a certificate that a remote client or system must trust, for example as the HTTPS SSL key alias.

1.  Select **Setup > Certificates**.
2.  Click the **Local Certificates** tab.
3.  Click **Import**.  
    The *Import Certificate/Key* window is displayed.
4.  Select **X509 Certificate** or **PGP key**.
5.  In the **Alias** field, type an alias name for the certificate.  
    If the alias name is already assigned to another certificate, you are prompted to either overwrite the existing certificate or cancel the operation.
6.  If the PKCS#12 (`.p12`) file being imported is password protected, type the password. You can also import PGP certificate files (`.asc` files).
7.  Select **Import certificate from file** and type or browse to the file name or select **Paste certificate in space below** and paste the certificate text into the text field.
8.  Click **Import**.

> **Note:**
>
> For specific requirements for certificates used to secure the SSL communication between the TM Server and the other servers, see Secure the communication between the TM server and the protocol servers.

<span id="Import_SSH"></span>

## Import an SSH key

Use the following procedure to import an SSH key. RSA and DSA keys in SSH2 format can be imported.

1.  Select **Setup > Certificates**.

2.  Click the **Local Certificates** tab.

3.  Click **Import**.  
    The *Import Certificate/Key* window is displayed.

4.  Select **SSH key**.

5.  Type the **CA Key Password** specified during the certificate generation.  

    > **Note:**
    >
    > Imported SSH Keys are stored as X509 certificates.

    > **Note:**
    >
    > CA Key Password is not a required field. When a SSH key is imported (without providing the internal CA key password), the key will be stored as X.509 certificate and signed with temporarily generated certificate. As a result, the SSH key will be stored as X.509 self-signed certificate.

6.  Type the information necessary to import the key. **Alias** and **Validity in days** are required fields.

7.  Paste the certificate content directly in the provided space, or import the certificate from a file. To import from file, type the file path or click **Browse** to browse for the file.

8.  Click **Import**.

<span id="Delete_loc_cert"></span>

## Delete a local certificate

Use the following procedure to delete a local certificate.

1.  Select **Setup > Certificates**.
2.  Click the **Local Certificates** tab.
3.  Select the checkboxes for the certificates to delete or select the check box in the table header to select all certificates.
4.  Click **Delete**.
5.  Confirm the deletion.

Do not delete the certificate with the `admind` alias which is implicitly assigned to the Administration Tool server. {{< SecureTransport/componentshortname  >}} prevents you from deleting a certificate that is in use, for example, a server certificate configured as the SSL key alias the AS2, FTP, HTTP, or SSH server or configured as the repository encryption certificate.

 

**Related topics:**

-   [Certificate types](../r_st_certificate_types)
-   [Certificate Management page](../c_st_certificate_management_page)
-   [Repository encryption certificate](../t_st_repository_encryption_certificate)
-   [Manage trusted CAs](../t_st_trustedcas)
-   [Manage the internal CA](../t_st_internalca)
-   [Change the certificate keystore password](../t_st_certificatekeystorepasswordca)
-   [Certificates to generate during initial setup](../r_st_certificatestogenerate)
-   [Store certificates in a hardware security module](../t_st_storecertificatesinhsm)
