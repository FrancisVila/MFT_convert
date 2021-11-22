{
    "title": "Repository encryption certificate",
    "linkTitle": "Repository encryption certificate",
    "weight": "110"
}Repository encryption increases {{< SecureTransport/componentshortname  >}} security by avoiding storing unencrypted files. Repository encryption can be enabled on different levels (for example, per account). When you enable repository encryption, SecureTransport encrypts (according to the activated repository encryption level) each file that it pulls from a partner site or that a client pushes to it. When {{< SecureTransport/componentshortname  >}} pushes a file to a partner site or a client pulls a file from it, {{< SecureTransport/componentshortname  >}} decrypts the file. {{< SecureTransport/componentshortname  >}} encrypts and decrypts each file dynamically in memory as it receives and sends it, so the files never exist unencrypted in the storage of the host system.

1.  Generate a self-issued local certificate or import a PKCS#12 file. See <a href="../t_st_localcertificatesandcsrs#Generate" class="MCXref xref">Generate a self-issued server certificate</a> and <a href="../t_st_localcertificatesandcsrs#Import" class="MCXref xref">Import a local certificate</a>.

2.  Set the value of the `Stfs.Encryption.CertAlias` server configuration parameter to the alias of the certificate. {{< SecureTransport/componentshortname >}} uses this certificate to encrypt and decrypt files. See <a href="../../../operations_menu/c_st_serverconfiguration/t_st_serverconfigurationparameters#top" class="MCXref xref">View and change server configuration parameters</a>.  
    {{< SecureTransport/componentshortname >}} prevents you from deleting the certificate referenced by `Stfs.Encryption.CertAlias`.  

    > **Note:**
    >
    > If Stfs.Encryption.CertAlias is not set, Repository Encryption will not be enabled.

3.  To choose the encryption algorithm, set the value of the `Stfs.Encryption.Algorithm` server configuration parameter to one of the following values:
    -   `AES128` (default)
    -   `AES256`
    -   `3DES`

      
    See <a href="../../../operations_menu/c_st_serverconfiguration/t_st_serverconfigurationparameters#top" class="MCXref xref">View and change server configuration parameters</a>.

4.  To configure {{< SecureTransport/componentshortname >}} to compute the MD5 checksum for an uploaded file dynamically as the file is uploaded, set the value of the `Stfs.Hash.HashOnUpload` server configuration parameter to `true`. When the value is `false`, the default value, {{< SecureTransport/componentshortname >}} computes the MD5 checksum after the file transfer is complete.

5.  Create a user class named `EncryptClass`. Files transferred by users in this class are encrypted. See <a href="../../../c_st_accesscontrol/c_st_userclasses/t_st_userclasses#Add" class="MCXref xref">Add a user class</a>.

6.  Restart the TM Server. See <a href="#Start" class="MCXref xref">Start and stop servers</a>.

> **Note:**
>
> If you enable repository encryption, the following SecureTransport functions are not supported: resume PeSIT transfers and pause and resume transfers when SecureTransport is the server.

> **Note:**
>
> When changing the repository encryption certificate, the Transaction Manager should be restarted in order for the changes to be applied.

**Related topics:**

-   <a href="../r_st_certificate_types" class="MCXref xref">Certificate types</a>
-   <a href="../c_st_certificate_management_page" class="MCXref xref">Certificate Management page</a>
-   <a href="../t_st_localcertificatesandcsrs" class="MCXref xref">Manage local certificates and certificate signing requests</a>
-   <a href="../t_st_trustedcas" class="MCXref xref">Manage trusted CAs</a>
-   <a href="../t_st_internalca" class="MCXref xref">Manage the internal CA</a>
-   <a href="../t_st_certificatekeystorepasswordca" class="MCXref xref">Change the certificate keystore password</a>
-   <a href="../r_st_certificatestogenerate" class="MCXref xref">Certificates to generate during initial setup</a>
-   <a href="../t_st_storecertificatesinhsm" class="MCXref xref">Store certificates in a hardware security module</a>
