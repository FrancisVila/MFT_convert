{
    "title": "Repository encryption certificate",
    "linkTitle": "Repository encryption certificate",
    "weight": "120"
}Repository encryption increases SecureTransport security by avoiding storing unencrypted files. Repository encryption can be enabled on different levels (for example, per account). When you enable repository encryption, SecureTransport encrypts (according to the activated repository encryption level) each file that it pulls from a partner site or that a client pushes to it. When SecureTransport pushes a file to a partner site or a client pulls a file from it, SecureTransport decrypts the file. SecureTransport encrypts and decrypts each file dynamically in memory as it receives and sends it, so the files never exist unencrypted in the storage of the host system.

1.  Generate a self-issued local certificate or import a PKCS#12 file. See [Generate a self-issued server certificate](../t_st_localcertificatesandcsrs) and [Import a local certificate](../t_st_localcertificatesandcsrs).

2.  Set the value of the `Stfs.Encryption.CertAlias` server configuration parameter to the alias of the certificate. SecureTransport uses this certificate to encrypt and decrypt files. See [View and change server configuration parameters](../../../operations_menu/c_st_serverconfiguration/t_st_serverconfigurationparameters).  
    SecureTransport prevents you from deleting the certificate referenced by `Stfs.Encryption.CertAlias`.  
    

    <table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">If <code>Stfs.Encryption.CertAlias</code> is not set, Repository Encryption will not be enabled.         </td>
      </tr>
</table>

3.  To choose the encryption algorithm, set the value of the `Stfs.Encryption.Algorithm` server configuration parameter to one of the following values:
    -   `AES128` (default)
    -   `AES256`
    -   `3DES`

      
    See [View and change server configuration parameters](../../../operations_menu/c_st_serverconfiguration/t_st_serverconfigurationparameters).

4.  To configure SecureTransport to compute the MD5 checksum for an uploaded file dynamically as the file is uploaded, set the value of the `Stfs.Hash.HashOnUpload` server configuration parameter to `true`. When the value is `false`, the default value, SecureTransport computes the MD5 checksum after the file transfer is complete.

5.  Create a user class named `EncryptClass`. Files transferred by users in this class are encrypted. See [Add a user class](../../../c_st_accesscontrol/c_st_userclasses/t_st_userclasses).

6.  Restart the TM Server. See [Start and stop servers](t_st_mange_server-ops.htm#start).

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">For server-initiated transfers, the user class is defined by the UID and GID only. If you define the <code>EncryptClass</code> using user name or other attributes, there are limitation on server-initiated transfers. See <a href="../../../c_st_advancedaccountadministration/c_st_clientinitiatedandserverinitiatedtransfers/c_st_encryption_server-initiated_transfers" xrefformat="{paratext}">Encryption and server-initiated transfers</a>.         </td>
      </tr>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Repository encryption can also be enabled on an individual account basis. When the setting is specified in the account, the user class is ignored.         </td>
      </tr>
</table>

**Related topics:**

-   [Certificate types](../r_st_certificate_types)
-   [Certificate Management page](../c_st_certificate_management_page)
-   [Manage local certificates and certificate signing requests](../t_st_localcertificatesandcsrs)
-   [Manage trusted CAs](../t_st_trustedcas)
-   [Manage the internal CA](../t_st_internalca)
-   [Change the certificate keystore password](../t_st_certificatekeystorepasswordca)
-   [Certificates to generate during initial setup](../r_st_certificatestogenerate)
-   [Store certificates in a hardware security module](../t_st_storecertificatesinhsm)
