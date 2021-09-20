{
    "title": "User certificates",
    "linkTitle": "User certificates",
    "weight": "160"
}SecureTransport supports the following types of certificates for use across the system:

-   PGP and X509 certificates.
-   Server certificates apply to all of the SecureTransport Server and fall into the following three types:
    -   **Local** – Contains a private key and is used by SecureTransport Servers.
    -   **Trusted CA** – Used for verification of remote certificates when creating secure connections.
    -   **Internal CA** – a Server Certificate Authority.
-   **User certificates** – These certificates are managed on a "per account" basis from the **Accounts** menu in the Administration Tool. They are generated, imported, exported, and deleted for the respective account. They fall into the following three types:
    -   **Login** – They do not have a private key and are used for logging to SecureTransport Servers. Their private key is exported during the generation of the certificate.
    -   **Partner** – They only have a public key and are used for encrypting PGP and AS2 data to an account and verifying the signature of data from the account.
    -   **Private** – They have a private key and are used for decryption and signing of PGP and AS2 data.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">By default, <span>SecureTransport</span> <span>5.5</span> does not allow you to  import  certificates that violate ITU-T X.690 standards. To be able to import such certificates, add the following Java option in &lt;<code>FILEDRIVEHOME&gt;/bin/start_admin</code>: <br/><code>JAVA_OPTS="-Dorg.bouncycastle.asn1.allow_unsafe_integer=true $JAVA_OPTS"</code> <br/>and restart the Admin daemon.<br/>Note that Axway does not recommend the import of such certificates as they can cause encoding issues.          </td>
      </tr>
</table>

 

The following topics provide how-to instructions for managing user certificates:

-   [Manage login certificates](t_st_usercertificates)
-   [Manage partner certificates](manage-user-partner-certificates)
-   [Manage private certificates](manage-user-private-certificates)
