{
    "title": "Encryption options",
    "linkTitle": "Encryption options",
    "weight": "200"
}<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> can encrypt a file before transferring it. You can specify the following options for files you are uploading:

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Encryption setting         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Encrypt File As         </td>
         <td>Determines if the file should be encrypted and if the encrypted file is saved to a different name, location, or both. You can use a file name expression.         </td>
      </tr>
      <tr>
         <td>Encrypt Using PGP Key         </td>
         <td>Determines if <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> uses PGP to encrypt the file and which PGP key it uses.         </td>
      </tr>
      <tr>
         <td>Sign Using PGP Key         </td>
         <td>Determines if <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> signs the file using a PGP key and which PGP key it uses.         </td>
      </tr>
      <tr>
         <td>Compression         </td>
         <td><p>Determines what type of compression is used. Choose from ZIP, ZLIB, or BZIP2. You can also choose to use no compression or to use preferred compression. Preferred compression methods and order of preference are determined by examining the recipient’s PGP key.</p>
<p>If the data compression method you choose is not among the recipient’s preferred methods, it is possible that the recipient will not be able to access the data.</p>
<p>You must also select the compression level: Fast, Normal, Good, or Best.</p>         </td>
      </tr>
      <tr>
         <td>Encode Using ASCII Armor         </td>
         <td>Determines if <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> uses ASCII armor encoding. ASCII armor refers to using binary-to-text encoding for plain text data.         </td>
      </tr>
      <tr>
         <td>Keep Original As         </td>
         <td>Determines if the original unencrypted file is saved to a different name, location, or both. You can use a file name expression.         </td>
      </tr>
   </tbody>
</table>

You can also choose to decrypt encrypted files when you download them. Decryption includes the following options:

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Decryption setting         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Decrypt PGP File As         </td>
         <td>Determines if the file should be decrypted and is the decrypted file is saved to a different name, location or both. You can use a file name expression.         </td>
      </tr>
      <tr>
         <td>Require Trusted Signature         </td>
         <td>Requires that the file contains a trusted signature or the transfer fails.         </td>
      </tr>
      <tr>
         <td>Require Encryption         </td>
         <td>Requires that the file is encrypted or the transfer fails.         </td>
      </tr>
      <tr>
         <td>Keep Original As         </td>
         <td>Determines if the original encrypted file is saved to a different name, location, or both. You can use a file name expression.         </td>
      </tr>
   </tbody>
</table>

> **Note:**
>
> Files that were encrypted using ASCII armoring or data compression are automatically decrypted and decompressed when you decrypt the PGP file.

**Related topics:**

-   <a href="../r_st_post_transmission_actions" class="MCXref xref">Post-transmission actions</a>
-   <a href="../t_st_subscriptions" class="MCXref xref">Manage subscriptions</a>
