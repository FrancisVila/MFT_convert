{
    "title": "iblksize",
    "linkTitle": "iblksize",
    "weight": "1500"
}### <span id="iblksize"></span>iblksize

#### COPYFILE

\[IBLKSIZE = {block size of the
input file | n}\]

{0...65535}

Defines input file block size in bytes. The value must be greater than
the value of the [ilrecl](../ilrecl) parameter.

The table indicates  if the iblksize parameter
is used.

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p>OS </p>
</th>
         <th>
            <p>IBLKSIZE </p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td valign="top" width="19%">
            <p>MVS (z/OS)</p>
         </td>
         <td valign="top" width="51.155%">
            <p>YES </p>
         </td>
      </tr>
      <tr>
         <td valign="top" width="19%">
            <p>OS400 </p>
         </td>
         <td valign="top" width="51.155%">
            <p>YES </p>
         </td>
      </tr>
      <tr>
         <td valign="top" width="19%">
            <p>UNIX </p>
         </td>
         <td valign="top" width="51.155%">
            <p>NO </p>
         </td>
      </tr>
      <tr>
         <td valign="top" width="19%">
            <p>VMS </p>
         </td>
         <td valign="top" width="51.155%">
            <p>NO </p>
         </td>
      </tr>
      <tr>
         <td valign="top" width="19%">
            <p>Windows </p>
         </td>
         <td valign="top" width="51.155%">
            <p>NO </p>
         </td>
      </tr>
   </tbody>
</table>

[Return to Command index](../../)
