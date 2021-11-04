{
    "title": "Generate or import a certificate authority",
    "linkTitle": "Generate or import a certificate authority",
    "weight": "70"
}Setup step 3 requires you to create or import a new internal certificate authority (CA) before you can generate certificates for services.

## Generate a permanent internal CA

<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> uses digital certificates for many security functions. These certificates can either be self-issued, meaning they are issued by the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server or signed by a third party, such as an external company like Verisign or a corporate CA. During the installation process, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> installs a default self-issued CA.

This step regenerates the self-signed Internal CA with a new password and with Distinguished Name (DN) attributes specific to an organization. You can use the Internal CA to sign local certificates that you generate in Step 4.

> **Note:**
>
> When you log in to the Administration Tool using the admin account, you can access this page by selecting Setup &gt; Certificates &gt; Internal CA.

1.  Select **Configure > 3-Generate CA**.  
    <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> displays the *Internal CA* pane.  
    <img src="/Images/SecureTransport/generate_CA.png" class="maxWidth" alt="Generate CA - Internal CA" />
2.  Click **Generate New CA**.  
    <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> displays *Generate Internal CA* page.  
    <img src="/Images/SecureTransport/generate_internal_CA.png" class="mediumWidth" alt="Generate Internal CA" />
3.  Enter the required information for the internal certificate.  
    Internal certificates require the **Certificate Subject** information. For internal certificates, enter the following information:
    -   **Validity in days** – the number of days the certificate is valid. The default is 365 days.
    -   **CA key password** – the private key password used to unlock the certificate.
    -   **Confirm CA key password** – the private key password must be entered again for confirmation.
    -   **Key Size** – a number representing the size of the generated key, expressed in bits. Possible values are 1024, 2048 (default), 3072, or 4096 bits.
    -   **Signature Algorithm** – the selection of the signature signing hashing algorithm. Possible values are SHA1withRSA, SHA256withRSA (default), SHA384withRSA, and SHA512withRSA.
    -   **Common Name** – a description of the certificate. Do not use the host name or the fully qualified domain name (FQDN) of the server without additional identifying text.
    -   **Department** – the organizational unit represented by the CA.
    -   **Company** – the organization represented by the CA.
    -   **City** – the name of the locality where the CA is located.
    -   **State** – the name of the state or province where the CA is located.
    -   **Country** – the name of the country where the CA is located.
4.  Click **Generate**.

## Import an external CA

Optionally, you can also import an external certificate. Ensure the certificate is valid and configured to validate certificates before you import it. <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> does not check the validity of the certificate.

A X509 certificate can be imported as a trusted CA in the form of a X509 DER or PEM encoded file.

> **Note:**
>
> SecureTransport protocol servers and services do not require restart after importing, overwriting, or deleting a trusted certificate.

1.  Select **Configure > 3-Generate CA**.  
    <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> displays the *Internal CA* pane.
2.  Click **Import CA**.  
    <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> displays the *Import Certificate* page.  
    <img src="/Images/SecureTransport/import_certificate.png" class="mediumWidth" alt="Import Certificate" />
3.  Enter a password in the field provided. The password is required.  
    If the CA certificate requires a pass phrase, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> uses this password. If the certificate does not require a pass phrase, the password is ignored. <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> also uses this password to encrypt the CA private key in the keystore stored in the database and file system.
4.  Specify the certificate by browsing to the PKCS#12 (PEM/DER) file.
5.  Click **Import**.

Now, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> uses the imported certificate as Internal CA and signs all certificates generated using that CA.

> **Note:**
>
> For more information, refer to the topic on importing an external CA in the SecureTransport Administrator's Guide.
