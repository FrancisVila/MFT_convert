{
    "title": "Security configuration",
    "linkTitle": "Security configuration",
    "weight": "120"
}For information on how to configure SecureTransport security, refer to the *Setup* chapter in the <span cshid="admin" data-version="5.3.5">*SecureTransport Administrator's Guide*</span>.

## How to implement connection with Transfer CFT over PeSIT (SSL)

In order to configure PeSIT over SSL connection between Transfer CFT and SecureTransport, a cipher suite supported by Transfer CFT has to be enabled. For example: `TLS_RSA_WITH_AES_256_CBC_SHA`

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Remember to keep all cipher suites separated by commas.         </td>
      </tr>
</table>

1.  In the Administration Tool, navigate to **Operations > Server Configurations**.
2.  Search for parameter: `Pesit.Listeners.Ssl.enabledCipherSuites`
3.  Click the **Edit** (![](SaveIcon.png)) icon.
4.  Add `TLS_RSA_WITH_AES_256_CBC_SHA` at the end of the cipher suite list.
5.  Click the **Save** (![](SaveIcon.png)) icon.
6.  Restart the PeSIT service.

For Server Initiated Transfers, the cipher also has to be added to the `Pesit.SIT.Ciphers` parameter.

## How to implement connection with an older version of SecureTransport

In order to implement a connection with an older version of SecureTransport at least one cipher on SecureTransport 5.5 must match with the ciphers on the older version of SecureTransport.

**For server-initiated transfers:**

1.  In the Administration Tool, navigate to **Operations > Server Configurations**.
2.  Search for parameter based on the protocol used (FTP, HTTP, AS2, PeSIT): `<protocol>.SIT.Ciphers`
3.  Click the **Edit** (![](SaveIcon.png)) icon.
4.  Add a cipher in common with the older version of SecureTransport at the end of the cipher suite list.
5.  Click the **Save** (![](SaveIcon.png)) icon.
6.  Restart Transaction Manager.

Optionally, for SecureTransport servers using MD5 with RSA signature algorithm for local certificates, go to the `java.securty` file and enable the use of signature certificates.

**For client-initiated transfers:**

1.  In the Administration Tool, navigate to **Operations > Server Configurations**.
2.  Search for parameter based on the protocol used (FTP, HTTP, AS2, PeSIT): `<protocol>.Listeners.Ssl.enabledCipherSuites`
3.  Click the **Edit** (![](SaveIcon.png)) icon.
4.  Add a cipher in common with the older version of SecureTransport at the end of the cipher suite list.
5.  Click the **Save** (![](SaveIcon.png)) icon.
6.  Restart the protocol service.

Optionally, for SecureTransport servers using MD5 with RSA signature algorithm for local certificates, go to the `java.securty` file and enable the use of signature certificates.
