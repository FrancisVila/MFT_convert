{
    "title": "Manage private certificates",
    "linkTitle": "Manage private certificates",
    "weight": "200"
}SecureTransport uses private certificates to log in to remote transfer sites for this account, as well as for decrypting and signing PGP and AS2 data.

You can view, generate, import and delete private certificates for the active account from the *Private Certificates* page.

## View a private certificate

1.  Select **Accounts > User Accounts**.
2.  Click the name of the account for which you want to view the certificate.  
    The *User Account Settings* page is displayed with details for the selected account.
3.  Click the **Certificates** tab, and then click **Private Certificates.**  
    A list of private certificates for the selected account is displayed on the *Private Certificates* page.
4.  Click the name of the certificate you want to view.  
    Private certificate information is displayed in the *View Certificate* dialog box.

## <span id="Export_SSH"></span>Export the SSH public key of an X509 private certificate

Use the following procedure to export the SSH public key of an X509 private certificate.

1.  Select **Accounts > User Accounts**.
2.  Click the name of the account containing the certificate.  
    The *User Account Settings* page is displayed with details for the selected account.
3.  Click the **Certificates** tab, and then click **Private Certificates.**  
    A list of private certificates for the selected account is displayed on the *Private Certificates* page.
4.  Click the name of the certificate you want to export.  
    Private certificate information is displayed in the *View Certificate* dialog box.
5.  Click **Export SSH Public Key**.
6.  When prompted, save the file containing the key on your file system.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">An SSH Key can be exported for each X509 certificate. In <span>SecureTransport</span>, all certificates are stored as X509 or PGP ones. Imported SSH Keys are also stored as X509 certificates.         </td>
      </tr>
</table>

## <span id="Generate_X509_priv"></span>Generate private certificates

SecureTransport generates X509, SSH, and PGP private certificates.

### Generate an X509 private certificate

Use the following procedure to generate an X509 certificate.

1.  Select **Accounts > User Accounts**.
2.  Click the name of the account where you want to add the certificate.  
    The *User Account Settings* page is displayed with details for the selected account.
3.  Click the **Certificates** tab, and then click **Private Certificates.**  
    A list of private certificates for the selected account is displayed on the *Private Certificates* page.
4.  Click **Generate**.  
    The *Generate Certificate* page is displayed.
5.  Select the **X509 Certificate / SSH key** radio button.
6.  Select either a **Self-issued Certificate** or a **Certificate Signing Request (CSR)**.
7.  Depending on your choice, type the necessary information.  
    **Alias**, **Validity in days**, and **Common Name (CN)** are required fields. The value you specify in the **Alias** field cannot exceed 50 characters in length.
8.  Click **Generate**.

### <span id="Generate2"></span>Generate a PGP private certificate

Use the following procedure to generate a PGP private certificate.

1.  Select **Accounts > User Accounts**.
2.  Click the name of the account where you want to add the certificate.  
    The *User Account Settings* page is displayed with details for the selected account.
3.  Click the **Certificates** tab, and then click **Private Certificates.**  
    A list of private certificates for the selected account is displayed on the *Private Certificates* page.
4.  Click **Generate**.  
    The *Generate Certificate* page is displayed.
5.  Select the **PGP Certificate** radio button.
6.  Type the necessary information and click **Generate**.  
    **Alias**, **Validity in Days**, and **Full Name** are required fields. The value you specify in the **Alias** field cannot exceed 50 characters in length.

## Import a private certificate

SecureTransport imports X509, PGP, and SSH private certificates.

### <span id="Import3"></span>Import an X509 or PGP private certificate

Use the following procedure to import an X509 or PGP private certificate.

1.  Select **Accounts > User Accounts**.
2.  Click the name of the account where you want to import the certificate.  
    The *User Account Settings* page is displayed with details for the selected account.
3.  Click the **Certificates** tab, and then click **Private Certificates.**  
    A list of private certificates for the selected account is displayed on the *Private Certificates* page.
4.  Click **Import**.  
    The *Import Certificate/Key* page is displayed.  
    
    1.  Select the type of the certificate you want to import: **X509** or **PGP**.
    2.  Type the certificate **Alias**. The value you specify in the **Alias** field cannot exceed 50 characters in length.
    3.  Type the certificate **Password**, if one was specified during the certificate generation.
    4.  Paste the certificate content directly in the provided space, or import the certificate from a file. To import from file, type the file path or click **Browse** to browse for the file.
5.  Click **Import**.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">If you select <strong>Certificate Signing Request (CSR)</strong>, the field below the<strong>Self-issued Certificate</strong> option are disabled for editing.         </td>
      </tr>
</table>

### <span id="Import_SSH_priv"></span>Import an SSH private certificate

Use the following procedure to import an SSH private certificate.

1.  Select **Accounts > User Accounts**.

2.  Click the name of the account where you want to import the certificate.  
    The *User Account Settings* page is displayed with details for the selected account.

3.  Click the **Certificates** tab, and then click **Private Certificates**.  
    A list of private certificates for the selected account is displayed on the *Private Certificates* page.

4.  Click **Import**.  
    The *Import Certificate/Key* page is displayed.

5.  Select the certificate type of the certificate you want to import: **SSH Key**.

6.  Type the **CA Key Password** specified during the certificate generation.  
    

    <table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The PGP keys imported for use with an account must specify signing algorithms.         </td>
      </tr>
</table>

7.  Type the information necessary to import the key.  
    **Alias** and **Validity in days** are required fields. The value you specify in the **Alias** field cannot exceed 50 characters in length.

8.  Paste the certificate content directly in the provided space, or import the certificate from a file. To import from file, type the file path or click **Browse** to browse for the file.

9.  Click **Import**.

## <span id="Delete_private"></span>Delete one or more private certificates

Use the following procedure to delete one or more private certificates.

1.  Select **Accounts > User Accounts**.
2.  Click the name of the account containing the certificate.  
    The *User Account Settings* page is displayed with details for the selected account.
3.  Click the **Certificates** tab, and then click **Private Certificates.**  
    A list of private certificates for the selected account is displayed on the *Private Certificates* page.
4.  Select the checkboxes next to the certificates you want to delete, and then click **Delete**.
5.  Click **OK** to confirm the deletion of the certificate. Otherwise, click **Cancel**. If **OK** is clicked, the selected certificate will be deleted and cannot be recovered.

**Related topics:**

-   [Manage login certificates](../t_st_usercertificates)
-   [Manage partner certificates](../manage-user-partner-certificates)
