{
    "title": "Manage partner certificates ",
    "linkTitle": "Manage partner certificates",
    "weight": "180"
}{{< SecureTransport/componentshortname  >}} uses partner certificates as public certificates for encrypting PGP and AS2 data to the respective account and for verification of the signature of data from the account.

You can view, generate, import and delete partner certificates for the active account from the *Partner Certificates* tab page.

## View and export a partner certificate

1.  Select **Accounts > User Accounts**.
2.  Click the name of the account for which you want to view the certificate.  
    The *User Account Settings* page is displayed with details for the selected account.
3.  Click the **Certificates** tab, and then click **Partner Certificates.**  
    A list of partner certificates for the selected account is displayed on the *Partner Certificates* page.
4.  Click the alias name of the partner certificate you want to view or export.  
    Partner certificate information is displayed in the *View Certificate* dialog box.
5.  Click **Export**.

## Generate a partner certificate

{{< SecureTransport/componentshortname  >}} generates X509 and SSH partner certificates.

### Generate an X509 partner certificate

Use the following procedure to generate an X509 partner certificate.

1.  Select **Accounts > User Accounts**.
2.  Click the name of the account where you want to add the certificate.  
    The *User Account Settings* page is displayed with details for the selected account.
3.  Click the **Certificates** tab, and then click **Partner Certificates.**  
    A list of partner certificates for the selected account is displayed on the *Partner Certificates* page.
4.  Click **Generate**.  
    The *Generate Certificate* dialog box is displayed.
5.  Select **X509 Certificate**.
6.  Type the necessary information in the *Generate Certificate* dialog box.  
    **Alias**, **Validity in days**, and **Common Name (CN)** are required fields. The value you specify in the **Alias** field cannot exceed 50 characters in length.
7.  Click **Generate**.

### Generate a PGP partner certificate

Use the following procedure generate a PGP partner certificate.

1.  Select **Accounts > User Accounts**.
2.  Click the name of the account where you want to add the certificate.  
    The *User Account Settings* page is displayed with details for the selected account.
3.  Click the **Certificates** tab, and then click **Partner Certificates.**  
    A list of partner certificates for the selected account is displayed on the *Partner Certificates* page.
4.  Click **Generate**.  
    The *Generate Certificate* dialog box is displayed.
5.  Select **PGP Certificate**.
6.  Type the necessary information in the *Generate Certificate* dialog box.  
    **Alias**, **Validity in days**, and **Full Name** are required fields. The value you specify in the **Alias** field cannot exceed 50 characters in length.
7.  Click **Generate**.

## Import a partner certificate

{{< SecureTransport/componentshortname  >}} imports X509 and PGP partner certificates.

<span id="Import"></span>Use the following procedure to import a partner certificate.

1.  Select **Accounts > User Accounts**.
2.  Click the name of the account where you want to import the certificate.  
    The *User Account Settings* page is displayed with details for the selected account.
3.  Click the **Certificates** tab, and then click **Partner Certificates.**  
    A list of partner certificates for the selected account is displayed on the *Partner Certificates* page.
4.  Click **Import** button.  
    The *Import Certificate/Key* dialog box is displayed.
5.  Select the certificate type of the certificate you want to import: **X509** or **PGP**.
6.  Type the necessary information in the *Import Certificate/Key* dialog box.  
    Paste the certificate content directly in the provided space, or import the certificate from a file. To import from file, type the file path or click **Browse** to browse for the file.
7.  Click **Import**.

> **Note:**
>
> The PGP keys imported for use with an account must specify signing algorithms.

## Delete one or more partner certificates

Use the following procedure to delete one or more partner certificates.

1.  Select **Accounts > User Accounts**. The *User Accounts* page is displayed.
2.  Click the name of the account containing the certificate.  
    The *User Account Settings* page is displayed with details for the selected account.
3.  Click the **Certificates** tab, and then click **Partner Certificates.**  
    A list of partner certificates for the selected account is displayed on the *Partner Certificates* page.
4.  Select the check box next to the certificate you want to delete, and then click **Delete**.
5.  Click **OK** to confirm the deletion of the certificate. Otherwise, click **Cancel**. If **OK** is clicked, the selected certificate will be deleted and cannot be recovered.

**Related topics:**

-   [Manage login certificates](../t_st_usercertificates)
-   [Manage private certificates](../manage-user-private-certificates)
