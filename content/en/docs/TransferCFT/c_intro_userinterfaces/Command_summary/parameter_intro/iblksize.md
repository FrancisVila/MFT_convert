{
    "title": "iblksize",
    "linkTitle": "iblksize",
    "weight": "1470"
}<span id="iblksize"></span>

### iblksize

#### COPYFILE

\[IBLKSIZE = {block size of the
input file | n}\]

{0...65535}

Defines input file block size in bytes. The value must be greater than
the value of the [ilrecl](../ilrecl) parameter.

The table indicates  if the iblksize parameter
is used.

<table>
   <th>
      <tr>
<th><p>OS </p>         </th>
<th><p>IBLKSIZE </p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>MVS (z/OS)</p>         </td>
         <td><p>YES </p>         </td>
      </tr>
      <tr>
         <td><p>OS400 </p>         </td>
         <td><p>YES </p>         </td>
      </tr>
      <tr>
         <td><p>UNIX </p>         </td>
         <td><p>NO </p>         </td>
      </tr>
      <tr>
         <td><p>VMS </p>         </td>
         <td><p>NO </p>         </td>
      </tr>
      <tr>
         <td><p>Windows </p>         </td>
         <td><p>NO </p>         </td>
      </tr>
   </tbody>
</table>

[Return to Command index](../../)
