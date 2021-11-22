{
    "title": "Manage login certificates",
    "linkTitle": "Manage login certificates",
    "weight": "170"
}{{< SecureTransport/componentshortname  >}} uses login certificates when the respective (currently active) account logs in to a {{< SecureTransport/componentshortname  >}} Server using a certificate or SSH Key.

You can view, generate, import and delete login certificates for the active account from the **Login Certificates** tab. It displays automatically when you click the **Certificate** tab in the *User Account* page.

<span id="Export_login"></span>

## View and export a login certificate

Use the following procedure to export a login certificate.

1.  Select **Accounts > User Accounts**.
2.  Click the name of the account for which you want to view the certificate.  
    The *User Account Settings* page is displayed with details for the selected account.
3.  Click the **Certificates** tab, and then click **Partner Certificates.**  
    A list of partner certificates for the selected account is displayed on the *Partner Certificates* page.
4.  Click the **View** link corresponding to the certificate you want to export.  
    Certificate information for the certificate you selected is displayed in a *View Certificate* dialog box.
5.  In the *View Certificate* dialog box, click **Export**.  
    The file is automatically downloaded and saved in your default download location.

<span id="Generate_login"></span>

## Generate a login certificate

{{< SecureTransport/componentshortname  >}} generates only X509 login certificates.

1.  In the **Login Certificates** tab, click **Generate**.  
    The *Generate Certificate* dialog box is displayed.
2.  Type the necessary information in the *Generate Certificate* dialog box, and then click **Generate**.  
    **Validity in days** and **Common Name (CN)** are required fields.

<span id="Import_X509"></span>

## Import a login certificate

Before the user attempts to log in using an imported certificate, ensure that the CA referenced in the certificate is include in the trusted CAs for the {{< SecureTransport/componentshortname  >}} server. For details, see <a href="../../../c_st_setup/c_st_certificates/t_st_trustedcas#top" class="MCXref xref">Manage trusted CAs</a>.

{{< SecureTransport/componentshortname  >}} generates only X509 login certificates, but you are allowed to import both X509 and SSH Key certificates.

> **Note:**
>
> The SSH login public key may not be unique. SecureTransport supports the use of both DSA and RSA SSH keys as SSH login public keys.

> **Note:**
>
> The Login X509 certificates must be unique.

Use the following procedure to import an X509 login certificate or an SSH login public key:

1.  Go to **Accounts > User Accounts**, and select an account.
2.  On the *User Account* page, click the **Certificates** tab.  
    The list of login certificates for the selected account is displayed.
3.  Click **Import**.  
    The *Import Certificate/Key* dialog box is displayed.

-   To import a X509 certificate: Choose **X509 Certificate**. In the displayed *Import Certificate/Key* dialog box, paste the certificate content directly in the provided space, or import the certificate from a file. To import from file, type the file path or click **Browse** to browse for the file.  

-   <img src="/Images/SecureTransport/Account_LoginCert_Import.png" class="mediumWidth" alt="Import Certificate/Key - X509 Certificate" />

-   To import an SSH login public key, select **SSH Key**. In the displayed *Import Certificate/Key* dialog box, type the necessary information. **Validity in days** is a required fields. Paste the SSH public key directly in the provided space, or import the SSH public key from a file. To import from file, type the file path or click **Browse** to browse for the file containing the key.  
    <img src="/Images/SecureTransport/Account_LoginCert_ImportSSH.png" class="mediumWidth" alt="Import Certificate/Key - SSH Key" />  

    > **Note:**
    >
    > CA Key Password and Common Name (CN) are not a required fields. When a SSH key is imported (without providing the internal CA key password), the key will be stored as X.509 certificate and signed with temporarily generated certificate. As a result, the SSH key will be stored as X.509 self-signed certificated.

Click **Import**.

<span id="Delete_login"></span>

### Delete one or more login certificates

Use the following procedure to delete one or more login certificates.

1.  Go to **Accounts > User Accounts**, and click the account name whose certificate you want to delete.
2.  On the *User Account* page, click the **Certificates** tab.  
    The list of login certificates for the selected account is displayed.
3.  Select the check box next to the certificate you want to delete, and then click **Delete**.
4.  Click **OK** to confirm the deletion of the certificate. Otherwise, click **Cancel**. If **OK** is clicked, the selected certificate will be deleted and cannot be recovered.

**Related topics:**

-   <a href="../manage-user-partner-certificates" class="MCXref xref">Manage partner certificates</a>
-   <a href="../manage-user-private-certificates" class="MCXref xref">Manage private certificates</a>
