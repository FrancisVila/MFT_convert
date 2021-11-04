{
    "title": "Generate certificates",
    "linkTitle": "Generate certificates",
    "weight": "80"
}Step 4 requires you to generate the server certificates that <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> uses.

Select **Configure &gt; 4-Generate Certs** to generate local, self-issued server certificates. Generated certificates are assigned RSA keys.

<img src="/Images/SecureTransport/generate_certs.png" class="maxWidth" alt="Generate Certificates - Local Certificates" />

> **Note:**
>
> When you log in to the Administration Tool using the admin account, you can access this page by selecting Setup &gt; Certificates &gt; Local Certificates. To import a certificate, refer to the SecureTransport Administrator's Guide.

<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> can use certificates for multiple purposes. For example, the FTPD certificate is commonly used for securing FTPS connections. Separate certificates and aliases can be used for each protocol. The httpd certificate is commonly signed by a public CA so that external users, especially those using a web browser to access the system, will trust the certificate. The other certificates are either internal to the product or only used by the Administrators; they can be signed by the internal CA. A temporary admind certificate is generated as part of the installation process so you can log in for initial setup.

To use a certificate signed by an external CA, refer to the <span class="redirect_st_ag" cshid="admin" data-version="5.3.5">*<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Administrator's Guide*</span> for information about the Import function.

## <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> certificates

The following tables list the certificates commonly used with <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>, although the default <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> configuration only requires that the `admind` and `mdn` certificates use those aliases.

For a <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server installation, generate the following certificates as needed:

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Alias         </th>
<th class="HeadD-Column1-Header1">Certificate use         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><code>admind</code>         </td>
         <td>An SSL server certificate for users connecting to the web administration system. Replaces the temporary one generated during installation.         </td>
      </tr>
      <tr>
         <td><code>ftpd</code>         </td>
         <td>An SSL server certificate for users connecting to transfer files.         </td>
      </tr>
      <tr>
         <td><code>httpd</code>         </td>
         <td>An SSL server certificate for users connecting to transfer files.         </td>
      </tr>
      <tr>
         <td><code>mdn</code>         </td>
         <td>A certificate used to sign the MDN receipts. The MDN alias must be named <code>mdn</code>. This certificate is not required to run <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server. The <code>mdn</code> alias is used by the AS2 protocol for sending receipts. <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> also generates MDN receipts for transfers for other protocols, but retains them locally and does not send the receipts to the customer.         </td>
      </tr>
      <tr>
         <td><code>repencrypt </code>(or other)         </td>
         <td>A certificate used to encrypt and decrypt <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> repository data. For more information, refer to the <span class="redirect_st_ag" data-cshid="admin" data-version="5.3.5"><em><span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Administrator's Guide</em></span>.         </td>
      </tr>
      <tr>
         <td><code>streaming</code>         </td>
         <td>A certificate used to secure the streaming between the server and the edge.         </td>
      </tr>
   </tbody>
</table>

For a <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge installation, generate the following certificates:

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Alias         </th>
<th class="HeadD-Column1-Header1">Certificate use         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><code>admind</code>         </td>
         <td>An SSL server certificate for users connecting to the web administration system. Replaces the temporary one generated during installation.         </td>
      </tr>
      <tr>
         <td><code>ftpd</code>         </td>
         <td>An SSL server certificate for users connecting to transfer files.         </td>
      </tr>
      <tr>
         <td><code>httpd</code>         </td>
         <td>An SSL server certificate for users connecting to transfer files.         </td>
      </tr>
      <tr>
         <td><code>streaming</code>         </td>
         <td>A certificate used to secure the streaming between the server and the edge.         </td>
      </tr>
   </tbody>
</table>

These certificates can be signed by the internal <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> CA, generated in the previous setup step. For more information, see <a href="../generate_or_import_ca" class="MCXref xref">Generate or import a certificate authority</a>.

The following procedure is used to generate a self-issued certificate. For information about generating a Certificate Signing Request (CSR), refer to the <span class="redirect_st_ag" cshid="admin" data-version="5.3.5">*<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Administrator's Guide*</span>.

1.  Select **Configure > 4-Generate Certs**.
2.  Click **Generate** to create a certificate.  
    <img src="/Images/SecureTransport/generate_certificate.png" class="mediumWidth" alt="Generate Certificate - Self-issued certificate" />
3.  Select the certificate type: **X509 Certificate / SSH key**.
4.  Enter the **CA key password** – the password of the Internal CA private key.
5.  Select **Self-issued Certificate**. Enter the required information for the self-issued certificates.  
    Self-issued certificates require the **Certificate Subject** information. For self-issued certificates, enter the following information:
    -   **Alias** – the name that identifies the certificate.
    -   If an alias that is already assigned to another certificate is used, a dialog box is displayed asking if you want to overwrite the original certificate. Be sure to enter the appropriate alias for the new certificate. If you are sure you want to replace the original certificate with the new one, click **Overwrite**. Click **Cancel** to discard the new certificate and keep the original one. You are returned to the **Generate Certificate** dialog box to make changes.
    -   **Validity in days** – the number of days the certificate is valid.
    -   **Key Size** – a number representing the size of the generated key, expressed in bits. Possible values are 1024, 2048 (default), 3072, or 4096 bits.
    -   **Signature Algorithm** – the selection of the signature signing hashing algorithm. Possible values are SHA1withRSA, SHA256withRSA (default), SHA384withRSA, and SHA512withRSA.
    -   **Common Name** – a description of the certificate. Should be the external address that the users will access to ensure that browsers recognize it as a valid certificate. It can be the address itself but it also can be a load-balancer (LB) address. Do not use the same CN as is used in the Certificate Authority.
    -   **Department** – the organizational unit represented by the certificate.
    -   **Company** – the organization represented by the certificate.
    -   **City** – the name of the locality where the certificate is located.
    -   **State** – the name of the state or province where the certificate is located.
    -   **Country** – the name of the country where the certificate is located.

      
    If you want to create a Certificate Signing Request (CSR), refer to the <span class="redirect_st_ag" cshid="admin" data-version="5.3.5">*<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Administrator's Guide*</span> for more information.
6.  Click **Generate**.
    1.  If you are generating a certificate with the same alias as an existing certificate, confirm that you want to overwrite the existing one.
    2.  (Optional) Select **Save backup of private key to file** if you want to save a copy of the private key.
    3.  <img src="/Images/SecureTransport/backup_certificate.png" class="mediumWidth" alt="Backup and/or save PKCS#12 file" />
    4.  Enter a password in the **Password** field, enter it again in the **Confirm Password** field, and click **Continue**.
    5.  When asked to open or save the file, click **Save** and select a location on the local file system.
    6.  A message displays indicating that the certificate was successfully saved.
7.  Click **Close**.

After generating a new `admind` certificate, you must restart the admin service.

> **Note:**
>
> Never delete the admind certificate, instead overwrite it when you need to replace it. The admind certificate must be present, valid, and chained to a trusted root or the admind service will not start.
