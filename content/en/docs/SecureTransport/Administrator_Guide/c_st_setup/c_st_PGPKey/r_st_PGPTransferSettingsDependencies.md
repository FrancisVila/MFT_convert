{
    "title": "PGP transfer settings dependencies",
    "linkTitle": "PGP transfer settings dependencies",
    "weight": "110"
}The following PGP transfer settings dependency matrix shows different configurations and scenarios for PGP-encrypted transfers depending on the transfer settings, accessible from the *Subscription* page.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Incoming file         </th>
<th class="HeadE-Column1-Header1">Encryption required         </th>
<th class="HeadE-Column1-Header1">Signature required         </th>
<th class="HeadE-Column1-Header1">Server action         </th>
<th class="HeadE-Column1-Header1">Result         </th>
<th class="HeadD-Column1-Header1">Transfer status         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Signed only         </td>
         <td>ON         </td>
         <td>ON         </td>
         <td>{{< SecureTransport/componentshortname  >}} attempts decryption and verification.         </td>
         <td>Decryption fails, because the file is not encrypted, and therefore no verification is performed.         </td>
         <td>Unsuccessful         </td>
      </tr>
      <tr>
         <td>Encrypted only         </td>
         <td>ON         </td>
         <td>ON         </td>
         <td>{{< SecureTransport/componentshortname  >}} attempts decryption and verification.         </td>
         <td>Decryption is successful, but verification fails, because the file is not signed.         </td>
         <td>Unsuccessful         </td>
      </tr>
      <tr>
         <td>Signed and Encrypted         </td>
         <td>ON         </td>
         <td>ON         </td>
         <td>{{< SecureTransport/componentshortname  >}} attempts decryption and verification.         </td>
         <td>Decryption and verification are successful, and the signature is removed.         </td>
         <td>Successful         </td>
      </tr>
      <tr>
         <td>Plain text         </td>
         <td>ON         </td>
         <td>ON         </td>
         <td>{{< SecureTransport/componentshortname  >}} attempts decryption and verification.         </td>
         <td>Decryption fails because the file is not encrypted, and no verification is performed.         </td>
         <td>Unsuccessful         </td>
      </tr>
      <tr>
         <td>Signed only         </td>
         <td>ON         </td>
         <td>OFF         </td>
         <td>{{< SecureTransport/componentshortname  >}} attempts decryption without verification.         </td>
         <td>Decryption fails because the file is not encrypted, and no verification is performed.         </td>
         <td>Unsuccessful         </td>
      </tr>
      <tr>
         <td>Encrypted only         </td>
         <td>ON         </td>
         <td>OFF         </td>
         <td>{{< SecureTransport/componentshortname  >}} attempts decryption without verification.         </td>
         <td>Decryption is successful, and no verification is performed.         </td>
         <td>Successful         </td>
      </tr>
      <tr>
         <td>Signed and Encrypted         </td>
         <td>ON         </td>
         <td>OFF         </td>
         <td>{{< SecureTransport/componentshortname  >}} attempts decryption without verification.         </td>
         <td>Decryption is successful, and no verification is performed, but the signature is removed.         </td>
         <td>Successful         </td>
      </tr>
      <tr>
         <td>Plain text         </td>
         <td>ON         </td>
         <td>OFF         </td>
         <td>{{< SecureTransport/componentshortname  >}} attempts decryption without verification.         </td>
         <td>Decryption fails because the file is not encrypted, and no verification is performed.         </td>
         <td>Unsuccessful         </td>
      </tr>
      <tr>
         <td>Signed only         </td>
         <td>OFF         </td>
         <td>ON         </td>
         <td>{{< SecureTransport/componentshortname  >}} attempts verification without decryption.         </td>
         <td>No decryption is performed. Verification is successful and the signature is removed.         </td>
         <td>Successful         </td>
      </tr>
      <tr>
         <td>Encrypted only         </td>
         <td>OFF         </td>
         <td>ON         </td>
         <td>{{< SecureTransport/componentshortname  >}} attempts decryption (to get to the signature) and verification.         </td>
         <td>Decryption is successful, but verification fails, because the file is not signed.         </td>
         <td>Unsuccessful         </td>
      </tr>
      <tr>
         <td>Signed and Encrypted         </td>
         <td>OFF         </td>
         <td>ON         </td>
         <td>{{< SecureTransport/componentshortname  >}} attempts decryption (to get to the signature) and verification.         </td>
         <td>Decryption and verification are successful.         </td>
         <td>Successful         </td>
      </tr>
      <tr>
         <td>Plain text         </td>
         <td>OFF         </td>
         <td>ON         </td>
         <td>{{< SecureTransport/componentshortname  >}} attempts verification without decryption.         </td>
         <td>No decryption is performed. Verification fails because the file is not signed.         </td>
         <td>Unsuccessful         </td>
      </tr>
   </tbody>
</table>
