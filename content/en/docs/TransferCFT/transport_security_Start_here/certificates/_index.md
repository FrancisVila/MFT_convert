{
    "title": "Managing  certificates",
    "linkTitle": "Managing certificates",
    "weight": "170"
}<span id="What_you_will_find_in_this_book"></span>This topic
describes security certificates, and the following security concepts:

-   [Overview
    of certificate standards](#Overview_of_Certificate_Standards)
-   [Database
    protection](#Database_protection)

## Central Governance certificate management

When using Transfer CFT with Central Governance, certificate management is performed by {{< TransferCFT/centralgovernancename  >}}. See [ {{< TransferCFT/centralgovernancename  >}} registration concepts](../../governance_services_intro/cg_register_overview) for details on certificates during installation and registration.

## What is a certificate?

A certificate is an electronic document used to identify an individual,
a server, a company, or other entity and to associate that identity with
a public key.

While communicating with any remote party, you need to be sure of the
correspondent’s identity before dealing with the data integrity and confidentiality.
In other words, forbidding the access to data and verifying that the data
received has not been modified is meaningless if you are not  sure
of the other party’s identity. Certificates help prevent the use of fake
public keys for impersonation. Only the public key certified by the certificate
will work with the corresponding private key possessed by the entity identified
by the certificate.

A certificate, more precisely a X509 certificate as defined by ISO,
is a data set that provides information about the owner and links them
it to his public key. To ensure that this information is correct, the
whole certificate is signed (data is hashed and the generated hash is
ciphered using an asymmetric algorithm such as RSA) by a third
party called the Certificate Authority (CA) which itself owns a public/private
key pair. It uses its private key to create the certificate signature
and makes its public key, which necessary to decrypt the signature, available
to anyone through its own certificate.

<span id="Overview_of_Certificate_Standards"></span>

## Certificate standards overview

The following sections give an overview of certificate fields as defined
by ISO in the X509 standard.

Users don't usually need to be concerned about
the exact contents of a certificate. However, system administrators working
with certificates should be familiar with the information listed below
in this topic.

### Distinguished names

An X.509 v3 certificate binds a Distinguished Name
(DN) to a public key. A DN is a series of name-value pairs,
such as `uid=dupont`, that uniquely identify an entity. In
this case, it is called the certificate
subject.

For example, this could be a typical DN for a Axway employee:

uid=dupont,e=dupont@Axway.com,cn=Albert Dupont ,o=Axway Corp.,c=FR

The abbreviations before each equal sign in this example have the following
meanings:

-   `uid`:
    User ID
-   `e`:
    Mail address
-   `cn`:The
    user's common name
-   `o`:
    Organization
-   `c`:
    Country

DNs may include a variety of other name/value pairs. They are used to
identify both certificate subjects and entries in directories that support
the Lightweight Directory
Access Protocol,
LDAP, the protocol generally used to access X.500 directories.

<span id="Certificate_fields"></span>

### Certificate fields

Every certificate consists of two sections, the data section and the
signature section as described below.

#### Certificate file description

#### Signature description

The signature provides the following information:

-   The cryptographic
    algorithm or cipher used by the issuing CA to create its own digital signature
-   The CA's digital
    signature obtained by hashing all of the data in the certificate together
    and encrypting it with the CA's private key

Example

This displays the data and signature sections of a certificate in human-readable
format:

<span id="Database_protection"></span>

## Database protection

A database record corresponds to a certificate, regardless of whether
it is from a root authority, an intermediate authority, or a user. In
the case of a user, the record also includes the private key associated
with the certificate's public key.

Records containing authority certificates, either root or intermediate,
are in plain format and simply sealed. Sealing is used to detect fraudulent
modifications, other than by the PKIUTIL utility.

Records containing user certificates are in plain format for the certificate
and encrypted for the private key. They are also sealed.

Private key encryption is based on a password that must be passed as
an argument in the PKICER command.

## Complete CA certificate chains

In {{< TransferCFT/transfercftname  >}} 3.1.3 and lower, you can perform a SSL transfer even if the certificate chain is not complete (not signed by a ROOT CA). However, for {{< TransferCFT/transfercftname  >}} 3.2.0 and higher, the certificate chain must be complete for a transfer to succeed.

For more information, see <a href="../../troubleshoot_intro/admin_troubleshooting_server/troubleshoot_security#Unknown" class="MCXref xref">Unknown CA leads to a failed certificate verification</a>
