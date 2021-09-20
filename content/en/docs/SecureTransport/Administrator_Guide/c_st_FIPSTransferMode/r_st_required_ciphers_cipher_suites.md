{
    "title": "Advertised ciphers and cipher suites",
    "linkTitle": "Advertised ciphers and cipher suites",
    "weight": "240"
}In Federal Information Processing Standard (FIPS) transfer mode, SecureTransport 5.5 advertises the following ciphers, cipher suites, or algorithms in the order given. The remote system must use one of them for the file transfer to succeed.

### <span id="FIPS_TLS_csuites"></span>FIPS-compliant TLS cipher suites

In FIPS mode, SecureTransport supports the following ciphers suites for communication over FTPS, HTTPS, AS2, and PeSIT protocols:

-   TLS\_DHE\_DSS\_WITH\_3DES\_EDE\_CBC\_SHA
-   TLS\_DHE\_DSS\_WITH\_AES\_128\_CBC\_SHA
-   TLS\_DHE\_DSS\_WITH\_AES\_128\_CBC\_SHA256
-   TLS\_DHE\_DSS\_WITH\_AES\_128\_GCM\_SHA256
-   TLS\_DHE\_DSS\_WITH\_AES\_256\_CBC\_SHA
-   TLS\_DHE\_DSS\_WITH\_AES\_256\_CBC\_SHA256
-   TLS\_DHE\_DSS\_WITH\_AES\_256\_GCM\_SHA384
-   TLS\_ECDHE\_ECDSA\_WITH\_3DES\_EDE\_CBC\_SHA
-   TLS\_ECDHE\_ECDSA\_WITH\_AES\_128\_CBC\_SHA
-   TLS\_ECDHE\_ECDSA\_WITH\_AES\_128\_CBC\_SHA256
-   TLS\_ECDHE\_ECDSA\_WITH\_AES\_128\_GCM\_SHA256
-   TLS\_ECDHE\_ECDSA\_WITH\_AES\_256\_CBC\_SHA
-   TLS\_ECDHE\_ECDSA\_WITH\_AES\_256\_CBC\_SHA384
-   TLS\_ECDHE\_ECDSA\_WITH\_AES\_256\_GCM\_SHA384
-   TLS\_ECDHE\_RSA\_WITH\_3DES\_EDE\_CBC\_SHA
-   TLS\_ECDHE\_RSA\_WITH\_AES\_128\_CBC\_SHA
-   TLS\_ECDHE\_RSA\_WITH\_AES\_128\_CBC\_SHA256
-   TLS\_ECDHE\_RSA\_WITH\_AES\_128\_GCM\_SHA256
-   TLS\_ECDHE\_RSA\_WITH\_AES\_256\_CBC\_SHA
-   TLS\_RSA\_WITH\_3DES\_EDE\_CBC\_SHA
-   TLS\_RSA\_WITH\_AES\_128\_CBC\_SHA
-   TLS\_RSA\_WITH\_AES\_128\_CBC\_SHA256
-   TLS\_RSA\_WITH\_AES\_128\_CCM
-   TLS\_RSA\_WITH\_AES\_128\_GCM\_SHA256
-   TLS\_RSA\_WITH\_AES\_256\_CBC\_SHA
-   TLS\_RSA\_WITH\_AES\_256\_CBC\_SHA256
-   TLS\_RSA\_WITH\_AES\_256\_CCM
-   TLS\_RSA\_WITH\_AES\_256\_GCM\_SHA384

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">From the list of supported algorithms, some are considered as not secure enough and are listed in the <code>&lt;FILEDRIVEHOME&gt;/jre/lib/security/java.security</code> file. If you insist on using any of them, you must manually remove their corresponding entries under <code>jdk.tls.disabledAlgorithms</code> and restart the node.         </td>
      </tr>
</table>

### FIPS-compliant ciphers and algorithms for SSH communication

In FIPS mode, SecureTransport supports the following ciphers and algorithms for the SSH daemon and server-initiated transfers:

#### <span id="Fips_SSh_ciphers"></span>FIPS-compliant ciphers

-   aes128-ctr
-   aes192-ctr
-   aes256-ctr
-   aes128-gcm@openssh.com
-   aes256-gcm@openssh.com

#### <span id="Fips_SSh_KEX"></span>FIPS-compliant key exchange algorithms

-   diffie-hellman-group-exchange-sha256
-   diffie-hellman-group14-sha256
-   diffie-hellman-group15-sha512
-   diffie-hellman-group16-sha512
-   diffie-hellman-group17-sha512
-   diffie-hellman-group18-sha512
-   rsa2048-sha256
-   ecdh-sha2-nistp384

#### <span id="Fips_SSh_MAC"></span>FIPS-compliant MAC algorithms

-   hmac-sha256
-   hmac-sha256@ssh.com
-   hmac-sha2-256
-   hmac-sha2-256-etm@openssh.com
-   hmac-sha512
-   hmac-sha512@ssh.com
-   hmac-sha2-512
-   hmac-sha2-512-etm@openssh.com

#### <span id="Fips_SSh_keys"></span>FIPS-compliant public key algorithms

-   ssh-rsa
-   x509v3-rsa2048-sha256
-   rsa-sha2-256
-   rsa-sha2-512
