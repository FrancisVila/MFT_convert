{
    "title": "UCONF: Copilot server",
    "linkTitle": "Transfer CFT UI server",
    "weight": "290"
}UNIX

Refer to the [UCONF parameters](../uconf_directory) table for information on `copilot.*.unix `parameters.

Alias management

You can access customized file system directories via the {{< TransferCFT/componentshortname  >}} user interface HTTP server using aliases.

To add a new alias, access the Unified Configuration uconf and configure the following:

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">ID         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>copilot.http.aliases         </td>
         <td>List of enabled alias-id         </td>
      </tr>
      <tr>
         <td>copilot.http.aliases.(alias-id) alias         </td>
         <td>Name of the alias         </td>
      </tr>
      <tr>
         <td>copilot.http.aliases.(alias-id).path         </td>
         <td>Path that replaces the alias in the URL         </td>
      </tr>
   </tbody>
</table>

Security for Cop**i**lot GUI

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Parameter         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>copilot.http.onlyssl         </td>
         <td>Enter Yes to restrict the access of the {{< TransferCFT/componentshortname  >}} UI with https.         </td>
      </tr>
   </tbody>
</table>

View available drives

To view available drives from the **Edit a file** icon in the graphical user interface, define the following:

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Parameter         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Options         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>copilot.nt.rootdrives         </td>
         <td>@REMOVABLE_DRIVES         </td>
         <td>To view removable drives such as a USB key, CD, and so on.         </td>
      </tr>
      <tr>
         <td>@LOCAL_DRIVES         </td>
         <td>To view hard drives.         </td>
      </tr>
      <tr>
         <td>@NET_DRIVES         </td>
         <td>To view network drives.         </td>
      </tr>
   </tbody>
</table>

Client keep-alive

Use this parameter to define the keep-alive interval in seconds for a client session. By default this occurs every 60 seconds.

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Parameter         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Value         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>copilot.misc.client_keep_alive_delay         </td>
         <td><p>Enter an integer for the delay in seconds.</p>
<p>60 = default</p>
<p>0 = no keep-alive</p>         </td>
      </tr>
   </tbody>
</table>

Client timeout

Use this parameter to define the client timeout in minutes. The default value is 30 minutes.

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Parameter         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Value         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>copilot.misc.ClientTimeout         </td>
         <td><p>Enter an integer for the timeout in minutes.</p>
<p>30 = default</p>
<p>0 = no timeout</p>         </td>
      </tr>
   </tbody>
</table>

Web services

Use this parameter to define the {{< TransferCFT/componentshortname  >}} Web Services. See also [Setting up Web Services]().

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Parameter         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Value         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Former value         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>copilot.webservices.wsicomplience         </td>
         <td>(bool) No         </td>
         <td>[WEBSERVICES] WsiComplience         </td>
      </tr>
      <tr>
         <td>copilot.webservices.upload_directory         </td>
         <td>(dir) $(cft.runtime_dir)/conf/ws_upload         </td>
         <td>NA         </td>
      </tr>
   </tbody>
</table>

Configure Copilot with HTTPS

This section describes how to install the certificates that are required to enable HTTPS connections for Copilot. The basic steps are:

-   Install a certificate on the server side
-   Install a certificate on the client side

### Install a certificate on the server side

The following tables describe the UCONF parameters that determine the certificates used by the Transfer CFT UI server to authenticate itself.

You can use the following certificate and private key formats, where the format of the certificate may differ from that of the key.

The certificate type is dictated by the file name extension (.p12, .pkcs12, .der, .pem, for example `my_certificate.pem`).

*For native files in a z/OS or IBM i environment*, if the format cannot be determined (the file suffix used as the extension), Transfer CFT derives the value from these uconf settings:

-   `copilot.ssl.sslkeyfile=<not set>` and `copilot.ssl.sslcertpassword=<set>`, then the format is PKCS12
-   `copilot.ssl.sslkeyfile= <set>` and `copilot.ssl.sslcertpassword=<not set>`, then the format is PEM

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Supported format         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Type         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Extension         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Certificate         </td>
         <td>PKCS#12         </td>
         <td>p12, pfx, pkcs12         </td>
      </tr>
      <tr>
         <td>PEM         </td>
         <td>pem         </td>
      </tr>
      <tr>
         <td>DER         </td>
         <td>der         </td>
      </tr>
      <tr>
         <td>Private key         </td>
         <td>PEM         </td>
         <td>pem         </td>
      </tr>
      <tr>
         <td>DER         </td>
         <td>der         </td>
      </tr>
      <tr>
         <td>PKCS#8         </td>
         <td>key,
pem         </td>
      </tr>
   </tbody>
</table>

How to define a PKCS#12 certificate

This example uses a single PKCS#12 certificate where you only require the file name and password.

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Parameter</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1"><p>Value</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>copilot.ssl.SslCertFile</p>         </td>
         <td><p>conf/pki/&lt;my_certificate&gt;.p12</p>         </td>
      </tr>
      <tr>
         <td><p>copilot.ssl.SslCertPassword</p>         </td>
         <td><p>Certificate password</p>         </td>
      </tr>
      <tr>
         <td><p>copilot.ssl.SslKeyFile</p>         </td>
         <td><p>Not used</p>         </td>
      </tr>
      <tr>
         <td><p>copilot.ssl.SslKeyPassword</p>         </td>
         <td><p>Not used</p>         </td>
      </tr>
   </tbody>
</table>

How to define a DER or PEM certificate

This example uses a DER(or PEM) certificate with the private key in a separate DER file, where you define the key as well as the certificate.

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Parameter</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1"><p>Value</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>copilot.ssl.SslCertFile</p>         </td>
         <td><p>conf/pki /&lt;my_certificate&gt;.der <em>or</em> .pem</p>         </td>
      </tr>
      <tr>
         <td><p>copilot.ssl.SslCertPassword</p>         </td>
         <td><p>Not used</p>         </td>
      </tr>
      <tr>
         <td><p>copilot.ssl.SslKeyFile</p>         </td>
         <td><p>conf/pki /&lt;my_key&gt;.der <em>or</em> .pem</p>         </td>
      </tr>
      <tr>
         <td><p>copilot.ssl.SslKeyPassword</p>         </td>
         <td><p>Key password, which is mandatory if the key file is encrypted PKCS#8</p>         </td>
      </tr>
   </tbody>
</table>

#### Additional HTTPS parameters

There are two additional UCONF parameters to use for HTTPS connections:

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Parameter</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1"><p>Value</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>copilot.http.onlyssl</p>         </td>
         <td><ul>
<li>No: Default value.</li>
<li>Yes: Restricts access to the Transfer CFT Copilot server to HTTPS secured connections only.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span id="copilot.ssl.SslCipherSuites"></span>copilot.ssl.SslCipherSuites</p>
<p> </p>         </td>
         <td><p>A comma separated list of cipher suites accepted by the Transfer CFT Copilot server.</p>
<ul>
<li>“47, 10, 9, 2”: Default value.</li>
</ul>
<p> </p>
<p>List of supported cipher suites:</p>
<ul>
<li>1 = RSA_WITH_NULL_MD5</li>
<li>2 = RSA_WITH_NULL_SHA</li>
<li>4 = RSA_WITH_RC4_MD5</li>
<li>5 = RSA_WITH_RC4_SHA</li>
<li>9 = RSA_WITH_DES_CBC_SHA1</li>
<li>10 = RSA_WITH_3DES_EDE_CBC_SHA</li>
<li>47 = RSA_WITH_AES_128_CBC_SHA</li>
<li>53 = RSA_WITH_AES_256_CBC_SHA</li>
<li>59 = RSA_WITH_NULL_SHA256</li>
<li></li>
<li></li>
</ul>         </td>
      </tr>
      <tr>
         <td>copilot.ssl.version_min         </td>
         <td><p>Indicates the minimum version of SSL that the Copilot and the REST API server accept.</p>
<ul>
<li>Default: tls_1.0</li>
<li>Possible values are: ssl_3.0 (not recommended), tls_1.0, tls_1.0, tls_1.2</li>
</ul>         </td>
      </tr>
   </tbody>
</table>
