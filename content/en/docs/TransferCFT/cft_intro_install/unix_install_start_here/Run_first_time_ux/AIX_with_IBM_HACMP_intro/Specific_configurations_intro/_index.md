{
    "title": "Unix-specific  values",
    "linkTitle": "Specific Transfer CFT configurations",
    "weight": "230"
}This topic summarizes <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> characteristics that differ from
other operating systems:

-   specific values
-   default files
-   filename extensions

## Specific values tables

<table>
   <th>
      <tr>
<th>Notation         </th>
<th>Object         </th>
<th>Value         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>char_file </p>         </td>
         <td><p>Prefix to logical names </p>         </td>
         <td><p>_ (underlined) </p>         </td>
      </tr>
      <tr>
         <td><p>char_mask </p>         </td>
         <td><p>Wild card character </p>         </td>
         <td><p>? </p>         </td>
      </tr>
      <tr>
         <td><p>char_unit </p>         </td>
         <td><p>Separator (volume) </p>         </td>
         <td><p>none </p>         </td>
      </tr>
      <tr>
         <td><p>char_symb </p>         </td>
         <td><p>Prefix to symbolic variables </p>         </td>
         <td><p>&amp; </p>         </td>
      </tr>
      <tr>
         <td><p>char_directory </p>         </td>
         <td><p>Character introduced in the path name of the FNAME parameter
(CFTRECV) from which a tree structure can be created </p>         </td>
         <td><p>+ </p>         </td>
      </tr>
      <tr>
         <td><p>file_symb </p>         </td>
         <td><p>Character introducing a file name sent to CFTUTIL in parameter
form </p>         </td>
         <td><p>@ </p>         </td>
      </tr>
   </tbody>
</table>

## Names of default files used by CFTUTIL

<table>
   <th>
      <tr>
<th><p><strong>Objet</strong> </p>         </th>
<th><p><span style="font-weight: bold;">Default name</span> </p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Parameters file </p>         </td>
         <td><p>_CFTPARM </p>         </td>
      </tr>
      <tr>
         <td><p>Partners file </p>         </td>
         <td><p>_CFTPART </p>         </td>
      </tr>
      <tr>
         <td><p>Catalogc file </p>         </td>
         <td><p>_CFTCATA </p>         </td>
      </tr>
      <tr>
         <td><p>Log file </p>         </td>
         <td><p>_CFTLOG </p>         </td>
      </tr>
      <tr>
         <td><p>Communication media </p>         </td>
         <td><p>_CFTCOM  </p>         </td>
      </tr>
      <tr>
         <td><p>statistics file </p>         </td>
         <td><p>_CFTACNT </p>         </td>
      </tr>
      <tr>
         <td><p>Preferred media </p>         </td>
         <td><p>File </p>         </td>
      </tr>
   </tbody>
</table>
