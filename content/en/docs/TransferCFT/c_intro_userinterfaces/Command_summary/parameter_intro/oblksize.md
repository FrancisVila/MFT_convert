{
    "title": "oblksize",
    "linkTitle": "oblksize",
    "weight": "2400"
}### <span id="oblksize"></span>oblksize

#### COPYFILE

\[OBLKSIZE = {IBLKSIZE value | n }\]

Output file block size, in bytes. The value indicated must be greater
than the value of the OLRECL parameter.  
The following table indicates for each system if the parameter
must be defined.

<table data-cellspacing="0" width="90%">
   <tbody>
      <tr class="odd">
         <td data-bgcolor="#C0C0C0" data-valign="top" width="19%">            <p><strong>OS</strong></p>         </td>
         <td data-bgcolor="#C0C0C0" data-valign="top" width="81%">            <p><strong>OBLKSIZE</strong> </p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="19%">            <p>z/OS (MVS)</p>         </td>
         <td data-valign="top" width="81%">            <p>YES </p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="19%">            <p>OS400 </p>         </td>
         <td data-valign="top" width="81%">            <p>NO </p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="19%">            <p>UNIX </p>         </td>
         <td data-valign="top" width="81%">            <p>NO </p>         </td>
      </tr>
      <tr class="odd">
         <td data-valign="top" width="19%">            <p>VMS </p>         </td>
         <td data-valign="top" width="81%">            <p>NO </p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="19%">            <p>Windows </p>         </td>
         <td data-valign="top" width="81%">            <p>NO</p>         </td>
      </tr>
   </tbody>
</table>

[Return to Command index](../)
