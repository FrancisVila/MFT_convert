{
    "title": "Manage cipher suites",
    "linkTitle": "Manage cipher suites",
    "weight": "190"
}This section describes how to define the cipher suites that can be used for secure file transfers, governance exchanges (<span class="mc-variable Primary.CG or_UM variable">Central Governance</span>, Sentinel, etc.), and when Transfer CFT is server (for example, when acting as an API server).

## Supported cipher suites

<span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> supports the cipher suites listed below, and prioritizes them as displayed in the **Order used** column (the <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> order overrides your cipher suite order). The order, between two approximate levels of security, favors the cipher suite that provides a better level of performance.

<table>
   <th>
      <tr>
<th><p>Suite </p>         </th>
<th><p>Order used</p>         </th>
<th><p>Authentication </p>         </th>
<th><p>Confidentiality </p>         </th>
<th><p>Integrity </p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>49199 **         </td>
         <td>1         </td>
         <td>ECDHE + RSA authentication         </td>
         <td>AES-128 GCM         </td>
         <td>SHA-256         </td>
      </tr>
      <tr>
         <td>49200 **         </td>
         <td>2         </td>
         <td>ECDHE + RSA authentication         </td>
         <td>AES-256 GCM         </td>
         <td>SHA-384         </td>
      </tr>
      <tr>
         <td>49191 **         </td>
         <td>3         </td>
         <td><p>ECDHE + RSA authentication</p>         </td>
         <td>AES-128         </td>
         <td>SHA-256         </td>
      </tr>
      <tr>
         <td>49192**         </td>
         <td>4         </td>
         <td>ECDHE + RSA authentication         </td>
         <td>AES-256         </td>
         <td>SHA-384         </td>
      </tr>
      <tr>
         <td>156 **         </td>
         <td>5         </td>
         <td>RSA authentication         </td>
         <td>AES 128 GCM         </td>
         <td>SHA-256         </td>
      </tr>
      <tr>
         <td>157 **         </td>
         <td>6         </td>
         <td>RSA authentication         </td>
         <td>AES 256 GCM         </td>
         <td>SHA-384         </td>
      </tr>
      <tr>
         <td>60*         </td>
         <td>7         </td>
         <td>RSA authentication (512, 1024, 2048, or 4096)         </td>
         <td>AES-128         </td>
         <td>SHA-256         </td>
      </tr>
      <tr>
         <td>61*         </td>
         <td>8         </td>
         <td>RSA authentication (512, 1024, 2048, or 4096)         </td>
         <td>AES-256         </td>
         <td>SHA-256         </td>
      </tr>
      <tr>
         <td>47         </td>
         <td>9         </td>
         <td>RSA authentication (512, 1024, 2048, or 4096)         </td>
         <td>AES-128         </td>
         <td>SHA-1         </td>
      </tr>
      <tr>
         <td>53         </td>
         <td>10         </td>
         <td>RSA authentication (512, 1024, 2048, or 4096)         </td>
         <td>AES-256         </td>
         <td>SHA-1         </td>
      </tr>
      <tr>
         <td>10         </td>
         <td>11         </td>
         <td>RSA authentication (512, 1024, 2048, or 4096)         </td>
         <td>Triple DES         </td>
         <td>SHA-1         </td>
      </tr>
      <tr>
         <td>5         </td>
         <td>12         </td>
         <td>RSA authentication (512, 1024, 2048, or 4096)         </td>
         <td>RC4         </td>
         <td>SHA-1         </td>
      </tr>
      <tr>
         <td>4         </td>
         <td>13         </td>
         <td>RSA authentication (512, 1024, 2048, or 4096)         </td>
         <td>RC4         </td>
         <td>MD5         </td>
      </tr>
      <tr>
         <td>59*         </td>
         <td>14         </td>
         <td>RSA authentication (512, 1024, 2048, or 4096)         </td>
         <td>None         </td>
         <td>SHA-256         </td>
      </tr>
      <tr>
         <td>2         </td>
         <td>15         </td>
         <td>RSA authentication (512, 1024, 2048, or 4096)         </td>
         <td>None         </td>
         <td>SHA-1         </td>
      </tr>
      <tr>
         <td>1         </td>
         <td>16         </td>
         <td>RSA authentication (512, 1024, 2048, or 4096)          </td>
         <td>None         </td>
         <td>MD5         </td>
      </tr>
   </tbody>
</table>

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>* To comply with security standards, as of Transfer CFT version 3.2.0 the use of the cipher suites 59, 60, and 61 is restricted to TLS 1.2 exclusively. This means that you cannot negotiate a session with another partner (monitor) that is using a TLS version lower than 1.2 with these cipher suites.         </td>
      </tr>
   </tbody>
</table>

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>** These cipher suites are only available for Transfer CFT 3.2.2 and higher and are restricted to use with TLS 1.2.         </td>
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

<table>
   <th>
      <tr>
<th>Parameter         </th>
<th>Description         </th>
<th>Type         </th>
<th>Possible values         </th>
<th>Default value         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>ssl.ciphersuites         </td>
         <td>Defines the cipher suite to be used between the Transfer CFT connectors.         </td>
         <td>int_list         </td>
         <td>See the table below         </td>
         <td>49200, 49199, 156, 157, 60, 61, 47, 53         </td>
      </tr>
      <tr>
         <td><p>copilot.ssl.sslciphersuites</p>         </td>
         <td><p>Defines the cipher suite to be used between the Transfer CFT UI client and UI server.</p>         </td>
         <td>int_list         </td>
         <td>See the table below         </td>
         <td>$(ssl.ciphersuites)         </td>
      </tr>
   </tbody>
</table>

<span id="Perfect"></span>

## Perfect Forward Secrecy support

Transfer CFT supports Perfect Forward Secrecy (PFS) with ECDHE\_RSA cipher suites. PFS ensures that sessions using long-term public and private keys will not be compromised if one of the private keys is compromised in the future. With PFS, systems can negotiate new keys for every communication, and if a key is compromised only that specific session is vulnerable.

For more information, refer to [www.perfectforwardsecrecy.com](https://www.perfectforwardsecrecy.com/)
