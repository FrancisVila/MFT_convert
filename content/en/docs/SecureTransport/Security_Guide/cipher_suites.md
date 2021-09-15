{
    "title": "SecureTransport cipher suites",
    "linkTitle": "SecureTransport cipher suites",
    "weight": "110"
}This topic lists all ciphers, cipher suites, or algorithms supported by SecureTransport 5.5.

-   [TLS cipher suites](#tls)
-   [SSH ciphers, KEX and MAC algorithms](#ssh)

## <span id="TLS"></span>TLS cipher suites

This section lists all TLS cipher suites supported by SecureTransport for protocol servers, the Admin and the TM daemons, as well as streaming communication:

-   [HTTPS, FTPS, AS2, and PeSIT](#https,)
-   [Administration Tool server](#admin)
-   [Axway Sentinel](#sentinel)
-   [Transaction Manager](#streamin)
-   [Internode communication in a Standard cluster](#standard)

 

### <span id="HTTPS,"></span>HTTPS, FTPS, AS2, and PeSIT

The section lists the cipher suites that are supported by SecureTransport for secure connections and SIT transfers using HTTPS, FTP, AS2, and PeSIT over TLS.

The enabled cipher suites for each protocol are defined by two server configuration options for the protocol server (daemon) and SIT, respectively.

<table cellspacing="0">
   <col/>
   <col/>
   <tbody>
      <tr>
         <td>AS2 daemon         </td>
         <td><code>As2.Listeners.Ssl.enabledCipherSuites</code>
         </td>
      </tr>
      <tr>
         <td>AS2 SIT         </td>
         <td><code>As2.SIT.Ciphers</code>
         </td>
      </tr>
      <tr>
         <td>FTP daemon          </td>
         <td><code>Ftp.Listeners.Ssl.enabledCipherSuites</code>
         </td>
      </tr>
      <tr>
         <td>FTP SIT         </td>
         <td><code>Ftps.SIT.Ciphers</code>
         </td>
      </tr>
      <tr>
         <td>HTTP daemon         </td>
         <td><code>Http.Ssl.EnabledCipherSuites</code>
         </td>
      </tr>
      <tr>
         <td>HTTP SIT         </td>
         <td><code>Https.SIT.Ciphers</code>
         </td>
      </tr>
      <tr>
         <td>PeSIT daemon         </td>
         <td><code>Pesit.Listeners.Ssl.enabledCipherSuites</code>
         </td>
      </tr>
      <tr>
         <td>PeSIT SIT         </td>
         <td><span>Pesit.SIT.Ciphers</span>
         </td>
      </tr>
   </tbody>
</table>

The following are the supported ciphers for the daemons and SITs with HTTPS, FTP, AS2, and PeSIT protocols.

-   TLS\_DHE\_DSS\_WITH\_3DES\_EDE\_CBC\_SHA
-   TLS\_DHE\_DSS\_WITH\_AES\_128\_CBC\_SHA
-   TLS\_DHE\_DSS\_WITH\_AES\_128\_CBC\_SHA256
-   TLS\_DHE\_DSS\_WITH\_AES\_128\_GCM\_SHA256
-   TLS\_DHE\_DSS\_WITH\_AES\_256\_CBC\_SHA
-   TLS\_DHE\_DSS\_WITH\_AES\_256\_CBC\_SHA256
-   TLS\_DHE\_DSS\_WITH\_AES\_256\_GCM\_SHA384
-   TLS\_DHE\_RSA\_WITH\_3DES\_EDE\_CBC\_SHA
-   TLS\_DHE\_RSA\_WITH\_AES\_128\_CBC\_SHA
-   TLS\_DHE\_RSA\_WITH\_AES\_128\_CBC\_SHA256
-   TLS\_DHE\_RSA\_WITH\_AES\_128\_CCM
-   TLS\_DHE\_RSA\_WITH\_AES\_128\_CCM\_8
-   TLS\_DHE\_RSA\_WITH\_AES\_128\_GCM\_SHA256
-   TLS\_DHE\_RSA\_WITH\_AES\_256\_CBC\_SHA
-   TLS\_DHE\_RSA\_WITH\_AES\_256\_CBC\_SHA256
-   TLS\_DHE\_RSA\_WITH\_AES\_256\_CCM
-   TLS\_DHE\_RSA\_WITH\_AES\_256\_CCM\_8
-   TLS\_DHE\_RSA\_WITH\_AES\_256\_GCM\_SHA384
-   TLS\_DHE\_RSA\_WITH\_CHACHA20\_POLY1305\_SHA256
-   TLS\_ECDHE\_ECDSA\_WITH\_3DES\_EDE\_CBC\_SHA
-   TLS\_ECDHE\_ECDSA\_WITH\_AES\_128\_CBC\_SHA
-   TLS\_ECDHE\_ECDSA\_WITH\_AES\_128\_CBC\_SHA256
-   TLS\_ECDHE\_ECDSA\_WITH\_AES\_128\_CCM
-   TLS\_ECDHE\_ECDSA\_WITH\_AES\_128\_CCM\_8
-   TLS\_ECDHE\_ECDSA\_WITH\_AES\_128\_GCM\_SHA256
-   TLS\_ECDHE\_ECDSA\_WITH\_AES\_256\_CBC\_SHA
-   TLS\_ECDHE\_ECDSA\_WITH\_AES\_256\_CBC\_SHA384
-   TLS\_ECDHE\_ECDSA\_WITH\_AES\_256\_CCM
-   TLS\_ECDHE\_ECDSA\_WITH\_AES\_256\_CCM\_8
-   TLS\_ECDHE\_ECDSA\_WITH\_AES\_256\_GCM\_SHA384
-   TLS\_ECDHE\_ECDSA\_WITH\_CHACHA20\_POLY1305\_SHA256
-   TLS\_ECDHE\_ECDSA\_WITH\_NULL\_SHA
-   TLS\_ECDHE\_RSA\_WITH\_3DES\_EDE\_CBC\_SHA
-   TLS\_ECDHE\_RSA\_WITH\_AES\_128\_CBC\_SHA
-   TLS\_ECDHE\_RSA\_WITH\_AES\_128\_CBC\_SHA256
-   TLS\_ECDHE\_RSA\_WITH\_AES\_128\_GCM\_SHA256
-   TLS\_ECDHE\_RSA\_WITH\_AES\_256\_CBC\_SHA
-   TLS\_ECDHE\_RSA\_WITH\_AES\_256\_CBC\_SHA384
-   TLS\_ECDHE\_RSA\_WITH\_AES\_256\_GCM\_SHA384
-   TLS\_ECDHE\_RSA\_WITH\_CHACHA20\_POLY1305\_SHA256
-   TLS\_ECDHE\_RSA\_WITH\_NULL\_SHA
-   TLS\_RSA\_WITH\_3DES\_EDE\_CBC\_SHA
-   TLS\_RSA\_WITH\_AES\_128\_CBC\_SHA
-   TLS\_RSA\_WITH\_AES\_128\_CBC\_SHA256
-   TLS\_RSA\_WITH\_AES\_128\_CCM
-   TLS\_RSA\_WITH\_AES\_128\_CCM\_8
-   TLS\_RSA\_WITH\_AES\_128\_GCM\_SHA256
-   TLS\_RSA\_WITH\_AES\_256\_CBC\_SHA
-   TLS\_RSA\_WITH\_AES\_256\_CBC\_SHA256
-   TLS\_RSA\_WITH\_AES\_256\_CCM
-   TLS\_RSA\_WITH\_AES\_256\_CCM\_8
-   TLS\_RSA\_WITH\_AES\_256\_GCM\_SHA384
-   TLS\_RSA\_WITH\_NULL\_SHA
-   TLS\_RSA\_WITH\_NULL\_SHA256

#### Secure (recommended) cipher suites

Axway recommends the following TLS 1.2 cipher suites:

-   TLS\_DHE\_RSA\_WITH\_AES\_128\_CBC\_SHA
-   TLS\_DHE\_RSA\_WITH\_AES\_128\_CBC\_SHA256
-   TLS\_DHE\_RSA\_WITH\_AES\_128\_GCM\_SHA256
-   TLS\_DHE\_RSA\_WITH\_AES\_128\_CCM
-   TLS\_DHE\_RSA\_WITH\_AES\_256\_CBC\_SHA
-   TLS\_DHE\_RSA\_WITH\_AES\_256\_CBC\_SHA256
-   TLS\_DHE\_RSA\_WITH\_AES\_256\_GCM\_SHA384
-   TLS\_DHE\_RSA\_WITH\_AES\_256\_CCM
-   TLS\_ECDHE\_RSA\_WITH\_AES\_128\_CBC\_SHA
-   TLS\_ECDHE\_RSA\_WITH\_AES\_128\_CBC\_SHA256
-   TLS\_ECDHE\_RSA\_WITH\_AES\_128\_GCM\_SHA256
-   TLS\_ECDHE\_RSA\_WITH\_AES\_256\_CBC\_SHA
-   TLS\_ECDHE\_RSA\_WITH\_AES\_256\_CBC\_SHA384
-   TLS\_ECDHE\_RSA\_WITH\_AES\_256\_GCM\_SHA384
-   TLS\_ECDHE\_ECDSA\_WITH\_AES\_128\_CCM
-   TLS\_ECDHE\_ECDSA\_WITH\_AES\_256\_CCM
-   TLS\_RSA\_WITH\_AES\_128\_CBC\_SHA
-   TLS\_RSA\_WITH\_AES\_128\_CBC\_SHA256
-   TLS\_RSA\_WITH\_AES\_128\_GCM\_SHA256
-   TLS\_RSA\_WITH\_AES\_128\_CCM
-   TLS\_RSA\_WITH\_AES\_256\_CBC\_SHA
-   TLS\_RSA\_WITH\_AES\_256\_CBC\_SHA256
-   TLS\_RSA\_WITH\_AES\_256\_GCM\_SHA384
-   TLS\_RSA\_WITH\_AES\_256\_CCM
-   TLS\_DHE\_DSS\_WITH\_AES\_128\_CBC\_SHA
-   TLS\_DHE\_DSS\_WITH\_AES\_128\_CBC\_SHA256
-   TLS\_DHE\_DSS\_WITH\_AES\_128\_GCM\_SHA256
-   TLS\_DHE\_DSS\_WITH\_AES\_256\_CBC\_SHA
-   TLS\_DHE\_DSS\_WITH\_AES\_256\_CBC\_SHA256
-   TLS\_DHE\_DSS\_WITH\_AES\_256\_GCM\_SHA384

#### Backward compatibility

If you need backward compatibility, the following ciphers (TLS 1.0, 1.1) suites are supported but their use is not recommended.

-   TLS\_DHE\_RSA\_WITH\_AES\_128\_CBC\_SHA
-   TLS\_DHE\_RSA\_WITH\_AES\_256\_CBC\_SHA
-   TLS\_ECDHE\_RSA\_WITH\_AES\_128\_CBC\_SHA
-   TLS\_ECDHE\_RSA\_WITH\_AES\_256\_CBC\_SHA
-   TLS\_RSA\_WITH\_AES\_128\_CBC\_SHA
-   TLS\_RSA\_WITH\_AES\_256\_CBC\_SHA
-   TLS\_DHE\_DSS\_WITH\_AES\_128\_CBC\_SHA
-   TLS\_DHE\_DSS\_WITH\_AES\_256\_CBC\_SHA

### <span id="Admin"></span>Administration Tool server

The cipher suites used for secure connections to the Administration tool are determined by the `Admin.EnabledCipherSuites` server configuration option.

The supported cipher suites are:

-   TLS\_ECDHE\_ECDSA\_WITH\_AES\_256\_GCM\_SHA384
-   TLS\_ECDHE\_RSA\_WITH\_AES\_256\_GCM\_SHA384
-   TLS\_ECDHE\_RSA\_WITH\_AES\_256\_CBC\_SHA384
-   TLS\_ECDHE\_ECDSA\_WITH\_AES\_256\_CBC\_SHA384
-   TLS\_ECDHE\_ECDSA\_WITH\_AES\_128\_GCM\_SHA256
-   TLS\_ECDHE\_ECDSA\_WITH\_AES\_128\_CBC\_SHA256
-   TLS\_ECDHE\_RSA\_WITH\_AES\_128\_GCM\_SHA256
-   TLS\_ECDHE\_RSA\_WITH\_AES\_128\_CBC\_SHA256
-   TLS\_DHE\_RSA\_WITH\_AES\_256\_GCM\_SHA384
-   TLS\_DHE\_DSS\_WITH\_AES\_256\_GCM\_SHA384
-   TLS\_DHE\_DSS\_WITH\_AES\_256\_CBC\_SHA256
-   TLS\_DHE\_RSA\_WITH\_AES\_256\_CBC\_SHA256
-   TLS\_DHE\_RSA\_WITH\_AES\_128\_GCM\_SHA256
-   TLS\_DHE\_DSS\_WITH\_AES\_128\_GCM\_SHA256
-   TLS\_DHE\_DSS\_WITH\_AES\_128\_CBC\_SHA256
-   TLS\_DHE\_RSA\_WITH\_AES\_128\_CBC\_SHA256
-   TLS\_RSA\_WITH\_AES\_256\_CBC\_SHA256

### <span id="Sentinel"></span>Axway Sentinel

The cipher suites used for secure connections to Sentinel are determined by the `AxwaySentinel.SecureConnection.EnabledCipherSuites` server configuration option.

The supported cipher suites are:

-   TLS\_ECDHE\_ECDSA\_WITH\_AES\_256\_GCM\_SHA384
-   TLS\_ECDHE\_RSA\_WITH\_AES\_256\_GCM\_SHA384
-   TLS\_ECDHE\_RSA\_WITH\_AES\_256\_CBC\_SHA384
-   TLS\_ECDHE\_ECDSA\_WITH\_AES\_256\_CBC\_SHA384
-   TLS\_ECDHE\_ECDSA\_WITH\_AES\_128\_GCM\_SHA256
-   TLS\_ECDHE\_ECDSA\_WITH\_AES\_128\_CBC\_SHA256
-   TLS\_ECDHE\_RSA\_WITH\_AES\_128\_GCM\_SHA256
-   TLS\_ECDHE\_RSA\_WITH\_AES\_128\_CBC\_SHA256
-   TLS\_DHE\_RSA\_WITH\_AES\_256\_GCM\_SHA384
-   TLS\_DHE\_DSS\_WITH\_AES\_256\_GCM\_SHA384
-   TLS\_DHE\_DSS\_WITH\_AES\_256\_CBC\_SHA256
-   TLS\_DHE\_RSA\_WITH\_AES\_256\_CBC\_SHA256
-   TLS\_DHE\_RSA\_WITH\_AES\_128\_GCM\_SHA256
-   TLS\_DHE\_DSS\_WITH\_AES\_128\_GCM\_SHA256
-   TLS\_DHE\_DSS\_WITH\_AES\_128\_CBC\_SHA256
-   TLS\_DHE\_RSA\_WITH\_AES\_128\_CBC\_SHA256
-   TLS\_RSA\_WITH\_AES\_256\_CBC\_SHA256
-   TLS\_RSA\_WITH\_AES\_256\_CBC\_SHA

### <span id="Streamin"></span>Transaction Manager

The cipher suites used by the Transaction Manager server are determined by the following server configuration options:

<table cellspacing="0">
   <col/>
   <col/>
   <tbody>
      <tr>
         <td>Transaction Manager          </td>
         <td><code>Tm.CipherSuites</code>
         </td>
      </tr>
      <tr>
         <td>Streaming connections from the TM to  protocol daemons (Admin, FTP, HTTP, and so forth)         </td>
         <td><code>Streaming.EnabledCipherSuites</code>
         </td>
      </tr>
   </tbody>
</table>

The default value of both options is TLS\_RSA\_WITH\_AES\_256\_CBC\_SHA256. Axway recommends that you do not change it.

### <span id="Standard"></span>Internode communication in a Standard cluster

The cipher suite used for internode communication in a Standard cluster is determined by the `Cluster.Listeners.Ssl.enabledCipherSuites` server configuration option. Default value: TLS\_RSA\_WITH\_AES\_256\_CBC\_SHA256.

Axway recommends that you do not change the default cipher suite.

## <span id="SSH"></span>SSH ciphers, KEX and MAC algorithms

The following server configuration options control the enabled cipher algorithms for the SSH daemon and for the SSH client used for server initiated transfers (SIT), respectively.

<table cellspacing="0">
   <col/>
   <col/>
   <tbody>
      <tr>
         <td>SSH daemon supported ciphers         </td>
         <td><code>Ssh.Ciphers</code>
         </td>
      </tr>
      <tr>
         <td>SSH daemon allowed MACs         </td>
         <td><code>Ssh.AllowedMacs</code>
         </td>
      </tr>
      <tr>
         <td>SSH daemon supported KEXs         </td>
         <td><code>Ssh.KeyExchangeAlgorithms</code>
         </td>
      </tr>
      <tr>
         <td>SSH daemon  supported public keys         </td>
         <td><code>Ssh.PublicKeys</code>
         </td>
      </tr>
      <tr>
         <td>SSH SIT supported ciphers         </td>
         <td><code>Ssh.SIT.Ciphers</code>
         </td>
      </tr>
      <tr>
         <td>SSH SIT allowed MACs         </td>
         <td><code>Ssh.SIT.AllowedMacs</code>
         </td>
      </tr>
      <tr>
         <td>SSH SIT supported KEXs         </td>
         <td><code>Ssh.SIT.KeyExchangeAlgorithms</code>
         </td>
      </tr>
      <tr>
         <td>SSH SIT supported public keys         </td>
         <td><code>Ssh.SIT.PublicKeys</code>
         </td>
      </tr>
   </tbody>
</table>

The value of these options is a comma-delimeted list of cipher, in which the first one is the most preferred cipher.

The following are the supported ciphers, HMAC and key exchange (KEX) algorithms for both the SSH daemon and SSH SITs.

### Default (SSH2) ciphers

-   aes128-ctr
-   aes192-ctr
-   aes256-ctr
-   3des-cbc
-   blowfish-cbc
-   aes128-cbc
-   aes192-cbc
-   aes256-cbc
-   arcfour
-   arcfour128
-   arcfour256
-   3des-ctr
-   aes128-gcm@openssh.com
-   aes256-gcm@openssh.com

### SSH1 ciphers

-   ssh1-des
-   ssh1-3des

### Message Authentication Codes

-   hmac-sha1
-   hmac-md5
-   hmac-sha1-96
-   hmac-md5-96
-   hmac-sha256
-   hmac-sha256@ssh.com
-   hmac-sha512
-   hmac-sha512@ssh.com
-   hmac-sha2-256
-   hmac-sha2-512
-   hmac-sha2-512-etm@openssh.com
-   hmac-ripemd160-etm@openssh.com
-   hmac-md5-etm@openssh.com
-   hmac-sha2-256-etm@openssh.com
-   hmac-sha2-256-96
-   hmac-sha1-etm@openssh.com
-   hmac-ripemd160
-   hmac-ripemd160@openssh.com
-   hmac-sha2-512-96

### Public keys

-   ssh-dss
-   ssh-rsa
-   x509v3-sign-rsa
-   x509v3-sign-dss
-   x509v3-sign-rsa-sha1
-   x509v3-ssh-rsa
-   x509v3-ssh-dss
-   x509v3-ecdsa-sha2-nistp256
-   x509v3-ecdsa-sha2-nistp384
-   x509v3-ecdsa-sha2-nistp521
-   x509v3-rsa2048-sha256
-   ssh-rsa-cert-v01@openssh.com
-   ssh-dss-cert-v01@openssh.com
-   ecdsa-sha2-nistp256-cert-v01@openssh.com
-   ecdsa-sha2-nistp384-cert-v01@openssh.com
-   ecdsa-sha2-nistp521-cert-v01@openssh.com
-   ecdsa-sha2-nistp256
-   ecdsa-sha2-nistp384
-   ecdsa-sha2-nistp521
-   rsa-sha2-256
-   rsa-sha2-512

### Key Exchange Algorithms

-   ecdh-sha2-nistp256
-   ecdh-sha2-nistp384
-   ecdh-sha2-nistp512
-   diffie-hellman-group14-sha256
-   diffie-hellman-group15-sha512
-   diffie-hellman-group-exchange-sha1
-   diffie-hellman-group18-sha512
-   diffie-hellman-group14-sha1
-   diffie-hellman-group17-sha512
-   diffie-hellman-group-exchange-sha256
-   diffie-hellman-group16-sha512
-   diffie-hellman-group1-sha1
-   curve25519-sha256@libssh.org
-   rsa1024-sha1
-   rsa2048-sha256
