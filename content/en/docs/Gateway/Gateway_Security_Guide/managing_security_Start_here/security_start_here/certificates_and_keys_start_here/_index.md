{
    "title": "Certificates and keys",
    "linkTitle": "Certificates and Keys",
    "weight": "160"
}{{< Gateway/componentlongname  >}}: Managing Security

[About certificates and keys](#About_certificates)

[Certificate fields](#Certificate_fields)

[Distinguished Names](#Distinguished_names)

[Establishing a trust relationship](#Establishing_a_trust_relationship)

[Certificate Authority (CA) hierarchy](#Certificate_Authority__CA__hierarchy)

[Certificate chains](#Certificate_chains)

[Syntax and formats](#Syntax_and_formats)

#### Related topics

[Certificate restrictions](certificate_restrictions)

[Managing certificates](certificate_management_(gui))

[Managing keys](key_management_(gui))

[Managing certificates (command line)](managing_certificates_cli)

[Managing keys (command line)](managing_certificates_cli/managing_keys_cli)

<span id="About_certificates"></span>

## About certificates and keys

A certificate is an electronic document that:

-   Identifies an individual, a server, a company, or some other entity
-   Associates that identity with a public key

When you communicate with any remote party, you must first determine the identity of that correspondent, before dealing with data integrity and confidentiality. In other words, forbidding access to data and verifying that the data received has not been modified is meaningless if you are not sure of the identity of the other party. Certificates help prevent the use of fake public keys for impersonation. Only the public key certified by the certificate works with the corresponding private key that belongs to the entity identified by the certificate.

A certificate (more precisely, an X.509 certificate as defined by ISO) is a data set that:

-   Provides information about the owner
-   Links the owner to a public key

To ensure that this information is correct, a third party referred to as the *Certificate Authority*, or *CA*, signs the whole certificate. In other words, data is hashed and the generated hash is encrypted using an asymmetric algorithm such as DSA or RSA. The CA owns a public/private key pair. It uses its private key to create the certificate signature and makes its public key (required to decrypt the signature) available to anyone through its own certificate.

<span id="Certificate_fields"></span>

## Certificate fields

Every certificate comprises:

-   [Data section](#Data_section)
-   [Signature section](#Signature_section)

<span id="Data_section"></span>

### Data section

The **data section** includes the following information:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Field</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Version</p>         </td>
         <td><p>Version of the encoded certificate value for X.509 V3 is <span style="font-weight: bold;">2</span>.</p>         </td>
      </tr>
      <tr>
         <td><p>Serial Number</p>         </td>
         <td><p>An integer assigned by the CA. The issuer name and serial number must identify a unique certificate.</p>         </td>
      </tr>
      <tr>
         <td><p>Issuer Signature Algorithm</p>         </td>
         <td><p>The signature algorithm identifier used by the CA to sign the certificate (for example, RSA with SHA-1).</p>         </td>
      </tr>
      <tr>
         <td><p>Issuer Distinguished Name</p>         </td>
         <td><p>The DN of the entity that signed and issued the certificate.</p>         </td>
      </tr>
      <tr>
         <td><p>Validity Period</p>         </td>
         <td><p>The validity period for the certificate.</p>         </td>
      </tr>
      <tr>
         <td><p>Subject Distinguished Name</p>         </td>
         <td><p>The entity associated with the public key stored in the public key field for the Subject.</p>         </td>
      </tr>
      <tr>
         <td><p>Subject Public Key Information</p>         </td>
         <td><p>The public key and the identifier algorithm used with the key.</p>         </td>
      </tr>
      <tr>
         <td><p>Extensions</p>
<p>(<span style="font-style: italic;">optional</span>)</p>         </td>
         <td><p>Extensions are additional information about the certificate. Extensions comprise three fields: type, criticality, and value.</p>
<ul>
<li>Type field is the ASN.1 data type (for example, text string, numerical, date).</li>
<li>The criticality flag is either critical or non-critical. If the PKI client application cannot process a critical extension, the certificate is rejected.</li>
<li>The actual value is the value associated with the extension.</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

<span id="Signature_section"></span>

### Signature section

The <span style="font-weight: bold;">signature section</span> includes the following information:

-   Type of cryptographic algorithm or cipher that the issuing CA uses to create its own digital signature.
-   Digital signature for the CA, obtained by hashing all of the data in the certificate and encrypting it with the CA private key.

The following example shows the data and signature sections of a certificate in human-readable format:


    Certificate:
    Data:
    Version: v3 (0x2)
    Serial Number: 3 (0x3)
    Signature Algorithm: PKCS #1 MD5 With RSA Encryption
    Issuer: OU=Sopra Certificate Authority, O=Sopra, C=US
    Validity:
    Not Before: Fri Oct 17 18:36:25 1997
    Not After: Sun Oct 17 18:36:25 1999
    Subject: CN=Albert Dupont, OU=Marketing, O=Sopra, C=US
    Subject Public Key Info:
    Algorithm: PKCS #1 RSA Encryption
    Public Key:
    Modulus:
    00:ca:fa:79:98:8f:19:f8:d7:de:e4:49:80:48:e6:2a:2a:86:
    ed:27:40:4d:86:b3:05:c0:01:bb:50:15:c9:de:dc:85:19:22:
    43:7d:45:6d:71:4e:17:3d:f0:36:4b:5b:7f:a8:51:a3:a1:00:
    98:ce:7f:47:50:2c:93:36:7c:01:6e:cb:89:06:41:72:b5:e9:
    73:49:38:76:ef:b6:8f:ac:49:bb:63:0f:9b:ff:16:2a:e3:0e:
    9d:3b:af:ce:9a:3e:48:65:de:96:61:d5:0a:11:2a:a2:80:b0:
    7d:d8:99:cb:0c:99:34:c9:ab:25:06:a8:31:ad:8c:4b:aa:54:
    91:f4:15
    Public Exponent: 65537 (0x10001)
    Extensions:
    Identifier: Certificate Type
    Critical: no
    Certified Usage:
    SSL Client
    Identifier: Authority Key Identifier
    Critical: no
    Key Identifier:
    f2:f2:06:59:90:18:47:51:f5:89:33:5a:31:7a:e6:5c:fb:36:
    26:c9
    Signature:
    Algorithm: PKCS #1 MD5 With RSA Encryption
    Signature:
    6d:23:af:f3:d3:b6:7a:df:90:df:cd:7e:18:6c:01:69:8e:54:65:fc:06:
    30:43:34:d1:63:1f:06:7d:c3:40:a8:2a:82:c1:a4:83:2a:fb:2e:8f:fb:
    f0:6d:ff:75:a3:78:f7:52:47:46:62:97:1d:d9:c6:11:0a:02:a2:e0:cc:
    2a:75:6c:8b:b6:9b:87:00:7d:7c:84:76:79:ba:f8:b4:d2:62:58:c3:c5:
    b6:c1:43:ac:63:44:42:fd:af:c8:0f:2f:38:85:6d:d6:59:e8:41:42:a5:
    4a:e5:26:38:ff:32:78:a1:38:f1:ed:dc:0d:31:d1:b0:6d:67:e9:46:a8:
    dd:c4

<span id="Distinguished_names"></span>

## Distinguished Names

An X.509 certificate binds a <span style="font-weight: bold;">Distinguished Name (DN)</span> to a public key. A DN is a series of name-value pairs, such as cn=Albert Dupont, that uniquely identify an entity. In this case, it is referred to as the <span style="font-weight: bold;">certificate subject</span>.

For example, a typical DN for an Axway employee could be:

e=dupont@axway.com,cn=Albert Dupont ,o=Axway Corp.,c=FR

where:

-   <span style="font-style: italic;">e</span> = Email address
-   <span style="font-style: italic;">cn</span> = Common name for this user
-   <span style="font-style: italic;">o</span> = Organization
-   <span style="font-style: italic;">c</span> = Country

DNs may include a variety of other name-value pairs, used to identify both certificate subjects and entries in directories that support the Lightweight Directory Access Protocol (LDAP: protocol generally used to access X.500 directories).

As defined by the X.500 standard, a Distinguished Name is a set of Relative Distinguished Names, each of which comprises an Attribute and Value set (<span style="font-weight: bold;">AVA</span>).

<span style="font-weight: bold;">Note:</span> Each Relative Distinguished Name (<span style="font-weight: bold;">RDN</span>) typically contains only one AVA. If more than one AVA is present, an error occurs when you import the corresponding certificate.

<span id="Establishing_a_trust_relationship"></span>

## Establishing a trust relationship

Certificate authorities (CAs) are entities that validate identities and issue certificates. They can either be independent third parties or organizations running their own certificate-issuing server software.

Any client or server software that supports certificates maintains a collection of <span style="font-weight: bold;">trusted CA certificates</span>. These CA certificates determine which other certificates the software can validate, in other words, which issuers of certificates the software can trust. In the simplest case, the software can only validate certificates issued by one of the CAs for which it has a certificate.

A trusted CA certificate can also be part of a chain of CA certificates, each one issued by the CA above it in a certificate hierarchy.

<span id="Certificate_Authority__CA__hierarchy"></span>

## Certificate Authority (CA) hierarchy

In large organizations, it may be appropriate to delegate the responsibility for issuing certificates to several different certificate authorities. For example, the number of certificates required may be too large for a single CA to maintain. Different organizational units may have different policy requirements, or it may be important for a CA to be physically located in the same geographic area as the people to whom it is issuing certificates.

You can delegate certificate-issuing responsibilities to subordinate CAs. The X.509 standard includes a model for setting up a CA hierarchy, as illustrated in the following diagram:

#### CA hierarchy

<img src="/Images/Gateway/CA_Hierarchy_756x474.png" class="maxWidth" />

In this model, the root CA is at the top of the hierarchy. The certificate of the root CA is a <span style="font-weight: bold;">self-signed certificate</span>. That is, the certificate is digitally signed by the same entity, the root CA, that the certificate identifies. The CAs that are directly subordinate to the root CA have CA certificates signed by the root CA. CAs under the subordinate CAs in the hierarchy have their CA certificates signed by the higher-level subordinate CAs.

Organizations have a great deal of flexibility in terms of the way they set up their CA hierarchies. The above illustration shows just one example, but many other arrangements are possible.

<span id="Certificate_chains"></span>

## Certificate chains

CA hierarchies are reflected in certificate chains. A <span style="font-weight: bold;">certification path</span> is an ordered sequence of certificates between the end entity (a leaf) and the trusted point in the hierarchy (the root). The result forms a certificate chain that begins at the end entity and ends at the root CA.

A certificate chain traces a path of certificates from a branch to the root of the hierarchy. A certificate chain is formed as follows:

-   Each certificate is followed by the certificate of its issuer.
-   Each certificate contains the name (DN) of the issuer of that certificate, which is the same as the subject name of the next certificate in the chain.

#### Certificate chains

<img src="/Images/Gateway/Certificate_Chains_756x638.png" class="maxWidth" />

In the illustration above, the Engineering CA certificate contains the DN of the CA (European CA), that issued that certificate. The DN of the European CA is also the subject name of the next certificate in the chain.

Each certificate is signed with the private key of its issuer. The signature can be verified with the public key in the certificate from the issuer (which is the next certificate in the chain).

In the illustration above, the public key in the certificate for the European CA can be used to verify the digital signature of the European CA on the certificate for the Engineering CA.

<span id="Verifying_a_certificate_chain"></span>

### Verifying a certificate chain

Certificate chain verification is the process of making sure a given certificate chain is well-formed, valid, properly signed, and trustworthy. The verification process:

1.  Checks the certificate validity period against the current time on the system clock of the verifier.
2.  Locates the certificate of the issuer. The source can either be the local certificate database for the verifier (on that client or server), or the certificate chain provided by the subject (for example, over an SSL connection).
3.  Uses the public key in the issuer’s certificate to verify the certificate signature.
4.  Stops successfully at this point if the certificate of the issuer is trusted in the certificate database for the verifier. Otherwise, the verification procedure must verify the certificate of the issuer. The verification process returns to step 1) to verify this new certificate.

<span id="Syntax_and_formats"></span>

## Syntax and formats

X.509 certificates are defined in <span style="font-style: italic;">ISO x509</span> and correspond to a descriptive syntax known as <span style="font-weight: bold;">ASN1</span> (<span style="font-style: italic;">Abstract Syntax Notation One</span>). The purpose of this syntax is to provide a system with an independent object description tool. In other words, this syntax allows you to describe objects used by applications in heterogeneous environments.

This document does not describe ASN1. For more information, refer to ISO/IEC8824-1. To be exploitable by a remote application (supported by any kind of machine), transmitted data (described with ASN1) must be encoded. The encoding rule must be the same on each communicating application, but the way this encoding rule is implemented is case-dependant (hardware-dependent, OS-dependent, and so on).

<span style="font-weight: bold;">D</span>istinguished <span style="font-weight: bold;">E</span>ncoding <span style="font-weight: bold;">R</span>ule (<span style="font-weight: bold;">DER</span>) is the encoding rule commonly used by applications that deal with X.509 certificates and public key infrastructures. The purpose of DER is to reduce ambiguities by providing a unique encoded value for a data set described with ASN1 syntax.

<span id="RSA_public_key_cryptography_standards"></span>

### RSA public key cryptography standards

RSA laboratories defined various standards for security material, based on ASN1 descriptions. The purpose of these standards is to enable systems that participate in Public Key Infrastructures to inter-operate.

In addition, RSA provides a complete description of two data structures (PKCS7 and PKCS12). These data structures are useful when you want to transfer Certificate Information.

<span id="PKCS7_standard"></span>

### PKCS7 standard

Basically, the PKCS7 standard defines an envelope for transferring all kinds of data. This transfer may include cryptographic parameters, since data may be encrypted, signed, and so on. The cryptographic information could include:

-   the encryption algorithm used to encode the data
-   the tools required to authenticate the identity of the sender when data is signed: the user certificate and the whole certification chain

In a simplified case, when the PKCS7 structure data field is empty, it provides a means of distributing certificates.

A commonly used file extension for this standard is <span class="code">p7s</span>.

<span id="PKCS8_Standard"></span>

### PKCS8 Standard

The PKCS8 standard defines a structure used to store private key information. Private key information includes a private key for a public-key algorithm and a set of attributes. Only the PBE-MD5-DES password-based algorithm may be used to encrypt the key. The password is usually communicated offline.

<span id="PKCS12_standard"></span>

### PKCS12 standard

After processing the certification operation (which generally consists in generating a pair of keys, signing the user certificate and sending the requested information back to the user), the certificate authority requires a secure way to send the user both the generated certificate and the private key. In the same way as PKCS7, the PKCS12 standard defines an envelope. This envelope contains password-based encrypted data.

To open the envelope and access the data, you must give the password required to generate a symmetric key used for deciphering. The password is usually communicated offline.

A commonly used file extension for this standard is <span class="code">p12</span>.

<span id="Base_64_encoding"></span>

### Base 64 encoding

When you use email to transfer data, you may need to encode it with printable character representation only. Base 64 encoding converts binary data to printable characters. This enables you to DER-encode a certificate or a key and to encode the result using base 64. Base 64 is mandatory for compatibility with MIME.

A commonly-used file extension is <span class="code">.pem</span>.

**Note**: Gateway does not support the import of DER-encoded keys protected by passphrase.

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
