{
    "title": "Predefined variables",
    "linkTitle": "Predefined variables",
    "weight": "300"
}SecureTransport supports the following predefined variables:

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Name</th>
         <th>Syntax</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Time Stamp         </td>
         <td><code>${timestamp}</code>
         </td>
         <td>Returns the UNIX epoch time in milliseconds as a decimal integer.         </td>
      </tr>
      <tr>
         <td>PGP Embedded File Name         </td>
         <td><code>${embedded}</code>
         </td>
         <td>The original file name embedded in the PGP encoded file. This value is defined after a PGP encoded file is decrypted. If the file was not PGP encoded, returns an empty string.         </td>
      </tr>
   </tbody>
</table>

## Predefined variable examples

The following table shows examples of the predefined variables:

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Name</th>
         <th>Example usage</th>
         <th>Example return value</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Time Stamp         </td>
         <td><code>${timestamp}</code>
         </td>
         <td><code>1345652729052</code>
         </td>
      </tr>
      <tr>
         <td>PGP Embedded File Name         </td>
         <td><code>${embedded}</code>
         </td>
         <td><code>original-file-name.txt</code>
         </td>
      </tr>
   </tbody>
</table>
