{
    "title": "Predefined variables",
    "linkTitle": "Predefined variables",
    "weight": "290"
}<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> supports the following predefined variables:

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Name         </th>
<th class="HeadE-Column1-Header1">Syntax         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Time Stamp         </td>
         <td><code>${timestamp}</code>         </td>
         <td>Returns the UNIX epoch time in milliseconds as a decimal integer.         </td>
      </tr>
      <tr>
         <td>PGP Embedded File Name         </td>
         <td><code>${embedded}</code>         </td>
         <td>The original file name embedded in the PGP encoded file. This value is defined after a PGP encoded file is decrypted. If the file was not PGP encoded, returns an empty string.         </td>
      </tr>
   </tbody>
</table>

## Predefined variable examples

The following table shows examples of the predefined variables:

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Name         </th>
<th class="HeadE-Column1-Header1">Example usage         </th>
<th class="HeadD-Column1-Header1">Example return value         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Time Stamp         </td>
         <td><code>${timestamp}</code>         </td>
         <td><code>1345652729052</code>         </td>
      </tr>
      <tr>
         <td>PGP Embedded File Name         </td>
         <td><code>${embedded}</code>         </td>
         <td><code>original-file-name.txt</code>         </td>
      </tr>
   </tbody>
</table>
