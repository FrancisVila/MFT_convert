{
    "title": "Certificate restrictions",
    "linkTitle": "Certificate restrictions",
    "weight": "190"
}{{< Gateway/componentlongname  >}}: Managing Security

[Certificate types](#Certificate_types)

[Supported certificate content (X.509)](#Supported_certificate_content_X509)

[Signature algorithms](#Signature_algorithms)

[Certificate extension](#Certificate_extension)

[Import formats](#Import_formats)

[Activation flag](#Activation_flag)

<span id="Certificate_types"></span>

## Certificate types

The **Security server** certificate database stores both certificates and private keys used during secure file transfers with TLS/SSL or SSH.

Certificate Records fall into four categories:

-   <span style="font-weight: bold;">Users:</span> End entity certificate whose private key is available
-   <span style="font-weight: bold;">Others:</span> End entity certificate whose private key is unknown
-   <span style="font-weight: bold;">Intermediary CA:</span> Authority certificate (not self-signed)
-   <span style="font-weight: bold;">Root CA:</span> Authority self-signed certificate

<span id="Automatic_detection_type"></span>

### Automatic type detection

When you import a certificate into the database, the server automatically detects the types to assign to the certificate, by:

-   <span style="font-style: italic;">comparing</span> the Certificate Issuer name with the subject name, to determine whether this certificate is a root certificate or not.
-   <span style="font-style: italic;">reading</span> the Basic Constraints Extension (if present), to determine whether the certificate is an authority certificate or not.
-   <span style="font-style: italic;">detecting</span> a Private Key: if a private key is provided with the certificate that you import, by default the server assigns the type <span style="font-weight: bold;">User</span> to the certificate.

<span id="Supported_certificate_content_X509"></span>

## Supported certificate content (X.509)

This section provides an overview of certificate fields as defined by ISO in the X.509 standard.

Users do not typically need to know the exact contents of a certificate. However, system administrators working with certificates may require some familiarity with the information provided here.

### Version

Only X.509 certificates are supported. The certificate version may be any of those defined by the X.509 standard (V1 or V3).

<span style="font-weight: bold;">Note:</span> To automatically determine the type of the certificate to import into the database, the server first compares its subject and issuer name and then looks for the Basic Constraints Extension (only present in X.509 V3 certificates). That means that if the certificate that you import is V1, you will probably have to force the certificate type while importing it.

### Validity period

Two formats are used to represent time values in X.509 certificates. These are UTC Time and generalized time. (Refer to X.509). Currently, only UTC Time format is supported. (You must take this into account before you import any certificate).

### Distinguished names

For purposes of DN manageability, only the following AVA types are supported:

#### Distinguished Names: attributes and values

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Component         </th>
<th class="HeadE-Column1-Header1">Representation Symbol         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Country Name</p>         </td>
         <td><p>C</p>         </td>
         <td><p>The two-letter international country code (specified in ISO 3166)</p>         </td>
      </tr>
      <tr>
         <td><p>Organization</p>         </td>
         <td><p>O</p>         </td>
         <td><p>The organization for which the certificate is issued</p>
<p>Example: Axway</p>         </td>
      </tr>
      <tr>
         <td><p>Organizational Unit- Name</p>         </td>
         <td><p>OU</p>         </td>
         <td><p>The division of the organization for which the certificate is issued</p>         </td>
      </tr>
      <tr>
         <td><p>StateOrProvince Name</p>         </td>
         <td><p>SP</p>         </td>
         <td><p>The state or province in which the certificate owner is located</p>         </td>
      </tr>
      <tr>
         <td><p>Locality Name</p>         </td>
         <td><p>L</p>         </td>
         <td><p>The locality in which the certificate owner is located</p>         </td>
      </tr>
      <tr>
         <td><p>Common Name</p>         </td>
         <td><p>CN</p>         </td>
         <td><p>The name of the certificate owner that can be either a person such as "Robert Dupont" or a business role such as "technical manager"</p>         </td>
      </tr>
      <tr>
         <td><p>Email address</p>
<p>(deprecated)</p>         </td>
         <td><p>E</p>         </td>
         <td><p>The certificate owner email address</p>
<p>Example: "asmith@axway.com"</p>         </td>
      </tr>
   </tbody>
</table>

In addition, for internal purposes, the Security server follows the RFC 1485 syntax for representing a distinguished name as a character string. The string is limited to 512 characters.

<span id="Signature_algorithms"></span>

## Signature algorithms

Only RSA-based signature algorithms are supported. Currently, two Hash algorithms are available and can be associated with RSA:

-   MD5
-   SHA-1

Supported RSA key lengths are 512, 1024, 2048, 4096 and 8192 bits.

<span id="Certificate_extension"></span>

## Certificate extension

Extensions can only be present in X.509 V3 certificates. As described above, the Basic Constraint Extension, which indicates whether the certificate is an authority certificate or not, is the only extension used to automatically detect the certificate type.

This extension is not mandatory because X.509 V1 certificates are supported. However, automatic detection does not work for Intermediary CA in these cases (you may need to force the certificate type).

<span id="Import_formats"></span>

## Import formats

Five distinct formats of certificates are supported:

<span style="font-weight: bold;">Simple DER format:</span> This is the most commonly used certificate format and corresponds to the DER-encoded certificate structure.

<span style="font-weight: bold;">[Base 64](../#Base_64_encoding):</span> This format consists of a simple DER certificate or a DER PKCS8 key, Base 64 encoded.

<span style="font-weight: bold;">[PKCS7](../#PKCS7_standard):</span> This format (DER-encoded) allows you to import certificates from PKCS7.  
As described in the [PKCS7 standard](../#PKCS7_standard), only the simplified case, where the structure contains signed data, is taken into account. In this instance, only the first certificate in the chain is imported.

<span style="font-weight: bold;">[PKCS8](../#PKCS8_Standard):</span> This format describes syntax for private-key information. It includes private keys that may be encrypted, and additional attributes. The supported encryption method is PKCS#5 V1.5. This format is used to import a certificate and its associated private key separately.

<span style="font-weight: bold;">[PKCS12](../#PKCS12_standard):</span> This format (DER-encoded) allows a one-shot import of a user certificate and its associated private key. The supported deciphering algorithms are:

-   RC2 CBC 40 bits
-   3 DES CBC 128 bits

For more information on transferring cryptographic data, such as Certificates and Private keys, refer to [Syntax and formats](../#Syntax_and_formats).

<span id="Activation_flag"></span>

## Activation flag

You can enable or disable every certificate in the local database using the GUI or the command line interface.

Check the activation flag when you define the certificate chain that you want to send. Your selection is also taken into account when you define the list of accepted authorities. To inhibit a certificate, you must remove it from the corresponding Security Profile or update the certificate database record with the status flag disabled.

You cannot send a disabled certificate in a certificate chain.

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
