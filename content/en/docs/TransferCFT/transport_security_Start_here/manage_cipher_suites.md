{
    "title": "Manage cipher suites",
    "linkTitle": "Manage cipher suites",
    "weight": "200"
}This section describes how to define the cipher suites that can be used for secure file transfers, governance exchanges (Central Governance, Sentinel, etc.), and when Transfer CFT is server (for example, when acting as an API server).

## Supported cipher suites

Transfer CFT supports the cipher suites listed below, and prioritizes them as displayed in the **Order used** column (the Transfer CFT order overrides your cipher suite order). The order, between two approximate levels of security, favors the cipher suite that provides a better level of performance.

<table data-cellspacing="0">
<thead>
<tr class="header">
<th><p>Suite </p></th>
<th><p>Order used</p></th>
<th><p>Authentication </p></th>
<th><p>Confidentiality </p></th>
<th><p>Integrity </p></th>
</tr>
</thead>
<tbody>
<tr class="odd" data-valign="middle">
<td data-valign="top" width="9%">49199 **</td>
<td>1</td>
<td data-valign="top">ECDHE + RSA authentication</td>
<td data-valign="top" width="20%">AES-128 GCM</td>
<td data-valign="top" width="27%">SHA-256</td>
</tr>
<tr class="even" data-valign="middle">
<td data-valign="top" width="9%">49200 **</td>
<td>2</td>
<td data-valign="top">ECDHE + RSA authentication</td>
<td data-valign="top" width="20%">AES-256 GCM</td>
<td data-valign="top" width="27%">SHA-384</td>
</tr>
<tr class="odd" data-valign="middle">
<td data-valign="top" width="9%">49191 **</td>
<td>3</td>
<td data-valign="top"><p>ECDHE + RSA authentication</p></td>
<td data-valign="top" width="20%">AES-128</td>
<td data-valign="top" width="27%">SHA-256</td>
</tr>
<tr class="even" data-valign="middle">
<td data-valign="top" width="9%">49192**</td>
<td>4</td>
<td data-valign="top">ECDHE + RSA authentication</td>
<td data-valign="top" width="20%">AES-256</td>
<td data-valign="top" width="27%">SHA-384</td>
</tr>
<tr class="odd" data-valign="middle">
<td data-valign="top" width="9%">156 **</td>
<td>5</td>
<td data-valign="top">RSA authentication</td>
<td data-valign="top" width="20%">AES 128 GCM</td>
<td data-valign="top" width="27%">SHA-256</td>
</tr>
<tr class="even" data-valign="middle">
<td data-valign="top" width="9%">157 **</td>
<td>6</td>
<td data-valign="top">RSA authentication</td>
<td data-valign="top" width="20%">AES 256 GCM</td>
<td data-valign="top" width="27%">SHA-384</td>
</tr>
<tr class="odd" data-valign="middle">
<td data-valign="top" width="9%">60*</td>
<td>7</td>
<td data-valign="top">RSA authentication (512, 1024, 2048, or 4096)</td>
<td data-valign="top" width="20%">AES-128</td>
<td data-valign="top" width="27%">SHA-256</td>
</tr>
<tr class="even" data-valign="middle">
<td data-valign="top" width="9%">61*</td>
<td>8</td>
<td data-valign="top">RSA authentication (512, 1024, 2048, or 4096)</td>
<td data-valign="top" width="20%">AES-256</td>
<td data-valign="top" width="27%">SHA-256</td>
</tr>
<tr class="odd" data-valign="middle">
<td data-valign="top" width="9%">47</td>
<td>9</td>
<td data-valign="top">RSA authentication (512, 1024, 2048, or 4096)</td>
<td data-valign="top" width="20%">AES-128</td>
<td data-valign="top" width="27%">SHA-1</td>
</tr>
<tr class="even" data-valign="middle">
<td data-valign="top" width="9%">53</td>
<td>10</td>
<td data-valign="top">RSA authentication (512, 1024, 2048, or 4096)</td>
<td data-valign="top" width="20%">AES-256</td>
<td data-valign="top" width="27%">SHA-1</td>
</tr>
<tr class="odd" data-valign="middle">
<td data-valign="top" width="9%">10</td>
<td>11</td>
<td data-valign="top">RSA authentication (512, 1024, 2048, or 4096)</td>
<td data-valign="top" width="20%">Triple DES</td>
<td data-valign="top" width="27%">SHA-1</td>
</tr>
<tr class="even" data-valign="middle">
<td data-valign="top" width="9%">5</td>
<td>12</td>
<td data-valign="top">RSA authentication (512, 1024, 2048, or 4096)</td>
<td data-valign="top" width="20%">RC4</td>
<td data-valign="top" width="27%">SHA-1</td>
</tr>
<tr class="odd" data-valign="middle">
<td data-valign="top" width="9%">4</td>
<td>13</td>
<td data-valign="top">RSA authentication (512, 1024, 2048, or 4096)</td>
<td data-valign="top" width="20%">RC4</td>
<td data-valign="top" width="27%">MD5</td>
</tr>
<tr class="even" data-valign="middle">
<td data-valign="top" width="9%">59*</td>
<td>14</td>
<td data-valign="top">RSA authentication (512, 1024, 2048, or 4096)</td>
<td data-valign="top" width="20%">None</td>
<td data-valign="top" width="27%">SHA-256</td>
</tr>
<tr class="odd" data-valign="middle">
<td data-valign="top" width="9%">2</td>
<td>15</td>
<td data-valign="top">RSA authentication (512, 1024, 2048, or 4096)</td>
<td data-valign="top" width="20%">None</td>
<td data-valign="top" width="27%">SHA-1</td>
</tr>
<tr class="even" data-valign="middle">
<td data-valign="top" width="9%">1</td>
<td>16</td>
<td data-valign="top">RSA authentication (512, 1024, 2048, or 4096) </td>
<td data-valign="top" width="20%">None</td>
<td data-valign="top" width="27%">MD5</td>
</tr>
</tbody>
</table>

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note  &lt;/b&gt;" data-valign="top">* To comply with security standards, as of Transfer CFT version 3.2.0 the use of the cipher suites 59, 60, and 61 is restricted to TLS 1.2 exclusively. This means that you cannot negotiate a session with another partner (monitor) that is using a TLS version lower than 1.2 with these cipher suites.</td>
</tr>
</tbody>
</table>

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note  &lt;/b&gt;" data-valign="top">** These cipher suites are only available for Transfer CFT 3.2.2 and higher and are restricted to use with TLS 1.2.</td>
</tr>
</tbody>
</table>

## Set the cipher suites for file transfers

Refer to *Transport security in CFTSSL* for details on how to specify the cipher suites for file transfers.

## Set the cipher suites for governance

This section describes how to specify the cipher suites for governance or when Transfer CFT is acting as an API server:

-   ssl.ciphersuites
-   copilot.ssl.sslciphersuites

**Procedure**

<span id="cipher_suites"></span>You can use these UCONF parameters to define the cipher suites:

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>Parameter</th>
<th>Description</th>
<th>Type</th>
<th>Possible values</th>
<th>Default value</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>ssl.ciphersuites</td>
<td>Defines the cipher suite to be used between the Transfer CFT connectors.</td>
<td>int_list</td>
<td>See the table below</td>
<td>49200, 49199, 156, 157, 60, 61, 47, 53</td>
</tr>
<tr class="even">
<td><p>copilot.ssl.sslciphersuites</p></td>
<td><p>Defines the cipher suite to be used between the Transfer CFT UI client and UI server.</p></td>
<td>int_list</td>
<td>See the table below</td>
<td>$(ssl.ciphersuites)</td>
</tr>
</tbody>
</table>

## <span id="Perfect"></span>Perfect Forward Secrecy support

Transfer CFT supports Perfect Forward Secrecy (PFS) with ECDHE\_RSA cipher suites. PFS ensures that sessions using long-term public and private keys will not be compromised if one of the private keys is compromised in the future. With PFS, systems can negotiate new keys for every communication, and if a key is compromised only that specific session is vulnerable.

For more information, refer to [www.perfectforwardsecrecy.com](https://www.perfectforwardsecrecy.com/)
